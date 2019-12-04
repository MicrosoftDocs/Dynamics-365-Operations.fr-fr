---
title: Spécifier un emplacement personnalisé de stockage pour les documents générés
description: Cette rubrique explique comment étendre la liste des emplacements de stockage pour les documents générés aux formats des états électroniques.
author: NickSelin
manager: AnnBe
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: 2c7ee610c6e3c446a4bcc9d6d46ca72dd71cb23c
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771396"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a>Spécifier un emplacement personnalisé de stockage pour les documents générés

[!include[banner](../includes/banner.md)]

L'API de la structure des états électroniques permet d'étendre la liste des emplacements de stockage pour les documents générés aux formats des états électroniques. Cette rubrique inclut une présentation générale des tâches principales que vous devez effectuer pour ajouter un emplacement de stockage personnalisé.

## <a name="prerequisites"></a>Conditions préalables

Vous devez déployer une topologie prenant en charge l'élaboration continue. (Pour plus d'informations, voir [Déployer des topologies prenant en charge l'élaboration continue et l'automatisation des tests](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) Vous devez avoir accès à cette topologie pour un des rôles suivants :

- Développeur d'états électroniques
- Consultant fonctionnel des états électroniques
- Administrateur système

Vous devez également avoir accès à l'environnement de développement pour cette topologie.

## <a name="create-or-import-an-er-format-configuration"></a>Créer ou importer une configuration au format d'états électroniques

Dans la topologie actuelle, [créez un format d'états électroniques](tasks/er-format-configuration-2016-11.md) pour générer les documents que vous prévoyez pour ajouter un emplacement de stockage personnalisé. Sinon [importez un format d'états électroniques existant dans cette topologie](general-electronic-reporting-manage-configuration-lifecycle.md).

![Page Concepteur de formats](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> Le format d'états électroniques que vous créez ou importez doit contenir au moins un des éléments de format suivants :
>
> - Fichier
> - Dossier
> - Fusion
> - Pièce jointe

## <a name="create-a-new-document-type"></a>Création d'un type de document

Pour spécifier comment les documents qu'un format d'états électroniques génère sont acheminés, vous devez configurer [Destinations des états électroniques (ER)](electronic-reporting-destinations.md). Dans chaque destination d'états électroniques configurée pour stocker les documents générés comme fichiers, vous devez préciser un type de document de la structure de gestion des documents. Différents types de document peuvent être utilisés pour acheminer les documents générés par différents formats d'états électroniques.

1. Ajoutez un nouveau [type de document](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) pour le format d'états électroniques que vous avez créé ou importé précédemment. Dans l'illustration ci-après, le type de document est **FileX**.
2. Pour différencier ce type de document d'autres types de documents, incluez un mot clé spécifique dans son nom. Par exemple, dans l'illustration ci-après, le nom est **dossier (LOCAL)**.
3. Dans le champ **Classe**, spécifiez **Fichier joint**.
4. Dans le champ **Groupe**, spécifiez **Fichier**.

![Page Types de documents](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> Les types de documents sont spécifiques à la société. Pour utiliser un format d'états électroniques avec une destination configurée dans plusieurs sociétés, vous devez configurer un type de document distinct dans chaque société.

## <a name="review-source-code"></a>Examiner le code source

Examinez le code de la méthode **insertFile ()** de classe **ERDocuManagement**. Observez que l'événement **AttachingFile ()** est déclenché tandis que le fichier généré est associé à un enregistrement.

```
/// <summary>
/// Inserts file as attachment in Document Management.
/// </summary>
/// <param name = "_owner">A record as the attachment owner.</param>
/// <param name = "_stream">The file stream.</param>
/// <param name = "_filePath">The file path with name.</param>
/// <param name = "_attachmentName">The name of file attachment.</param>
/// <returns>The reference to inserted file.</returns>
[Hookable(false)]
public DocuRef insertFile(
    Common _owner, 
    System.IO.Stream _stream, 
    str _filePath, 
    str _attachmentName, 
    DocuTypeId _docuTypeId)
{
    DocuRef docuRef;
    if (_stream)
    {
        DocuType::createDefaults();
        if (!this.isDocuTypeValid(_docuTypeId))
        {
            throw error(strFmt("@ElectronicReporting:DocuTypeIsNotValid", _docuTypeId));
        }
        var args = ERDocuManagementAttachingFileEventArgs::construct(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        ERDocuManagementEvents::onAttachingFile(args);
        if (args.isHandled())
        {
            docuRef = args.getDocuRef();
        }
        else
        {
            docuRef = this.attachFile(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        }
    }
    return docuRef;
}
```

L'événement **AttachingFile ()** est déclenché lorsque les destinations des états électroniques suivantes sont traitées :

- **Archive** - Lorsque cette destination est utilisée, un nouvel enregistrement pour le format d'états électroniques exécuté est créé dans la table ERFormatMappingRunJobTable. Le champ **Archivé** dans cet enregistrement est défini sur **Faux**. Si le format d'états électroniques est exécuté avec succès, le document généré est joint à cet enregistrement, et l'événement **AttachingFile()** est déclenché. Le type de document sélectionné dans cette destination d'états électroniques détermine l'emplacement de stockage du fichier joint (stockage Microsoft Azure ou dossier Microsoft SharePoint ).
- **Archive Tâche** - Lorsque cette destination est utilisée, un nouvel enregistrement pour le format d'états électronique exécuté est créé dans la table ERFormatMappingRunJobTable. Le champ **Archivé** dans cet enregistrement est défini sur **Vrai**. Si le format d'états électroniques est exécuté avec succès, le document généré est joint à cet enregistrement, et l'événement **AttachingFile()** est déclenché. Le type de document configuré dans les paramètres des états électroniques détermine l'emplacement de stockage du fichier joint (stockage Azure ou dossier Microsoft SharePoint).

![Page Paramètres de la gestion des états électroniques](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a>Configurer une destination des états électroniques

1. Configurez la destination archivée pour un des éléments précédemment mentionnés (fichier, dossier, fusion, ou pièce jointe) du format des états électroniques que vous avez créé ou importé. Pour obtenir de l'aide, voir [États électroniques - Configurer des destinations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).
2. Utilisez le type de document que vous avez ajouté plus tôt pour la destination configurée. (Pour l'exemple dans cette rubrique, le type de document est **FileX**.)

![Boîte de dialogue Paramètres de destination](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a>Modifier le code source

1. Ajoutez une nouvelle classe à votre projet Microsoft Visual Studio, et écrivez du code pour vous abonner à l'événement **AttachingFile()** mentionné précédemment. (Pour plus d'informations sur le modèle d'extensibilité utilisé, voir [Répondre à l'aide de EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) Par exemple, dans la nouvelle classe, écrivez le code qui exécute les actions suivantes :

    1. Enregistrez les fichiers générés dans un dossier du système de fichiers local du serveur qui exécute le service AOS.
    2. Enregistrez ces fichiers générés uniquement lorsque le nouveau type de document (par exemple, le type **FileX** ayant le mot clé « (LOCAL) » dans son nom) est utilisé lorsqu'un fichier est joint à l'enregistrement dans le journal des tâches d'exécution des états électroniques.

    ```
    class ERDocuSubscriptionSample
    {
        void new()
        {
        }
        [SubscribesTo(classStr(ERDocuManagementEvents), 
        staticDelegateStr(ERDocuManagementEvents, 
        attachingFile))]
        public static void ERDocuManagementEvents_attachingFile(ERDocuManagementAttachingFileEventArgs _args)
        {
            if (!_args.isHandled())
            {
                DocuType docuType = DocuType::find(_args.getDocuTypeId());
                if (strContains(docuType.Name, '(LOCAL)'))
                {
                    _args.markAsHandled();
                    var stream = _args.getStream();
                    if (stream.CanSeek)
                    {
                        stream.Seek(0, System.IO.SeekOrigin::Begin);
                    }
                    using (var localStream = System.IO.File::OpenWrite(@'c:\0\' + _args.getAttachmentName()))
                    {
                        stream.CopyTo(localStream);
                    }
                }
            }
        }
    }
    ```

2. Recréez votre projet.

## <a name="run-the-er-format-that-you-created-or-imported"></a>Exécuter le format des états électroniques que vous avez créé ou importé

1. Exécutez le format des états électroniques que vous avez créé ou importé.
2. Accédez à **Administration d'organisation \> États électroniques \> Tâches d'états électroniques**. Recherchez l'enregistrement créé pour cette tâche d'exécution et auquel le fichier généré est joint.
3. Explorez le dossier **C:\\0** local pour trouver le même fichier généré.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Destinations de la gestion des états électroniques](electronic-reporting-destinations.md)
- [Page d'accueil Extensibilité](../extensibility/extensibility-home-page.md)
