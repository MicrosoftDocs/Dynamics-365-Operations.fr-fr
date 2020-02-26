---
title: Destinations pour la gestion des états électroniques
description: Cette rubrique fournit des informations sur la gestion des destinations de rapport électronique (ER), les types de destinations pris en charge et les considérations de sécurité.
author: nselin
manager: AnnBe
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 2e4c6951afbff367dc93072d20395c3a37fffbcb
ms.sourcegitcommit: 4e62c22b53693c201baa646a8f047edb5a0a2747
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/07/2020
ms.locfileid: "3030771"
---
# <a name="electronic-reporting-er-destinations"></a>Destinations de la gestion des états électroniques

[!include [banner](../includes/banner.md)]

Vous pouvez configurer une destination pour chaque configuration de génération d'états électroniques (ER) et son composant de sortie (un dossier ou un fichier). Les utilisateurs qui disposent des droits d’accès appropriés peuvent également modifier les paramètres de destination au moment de l’exécution. Cette rubrique explique la gestion des destinations des ER, les types de destinations pris en charge et des considérations sur la sécurité.

Les configurations de format des ER contiennent généralement au moins un composant de sortie : un fichier. En règle générale, les configurations contiennent plusieurs composants de sortie de fichiers de différents types (par exemple, XML, TXT, XLSX, DOCX ou PDF) qui sont regroupés dans un dossier unique ou dans plusieurs dossiers. La gestion des destinations des états électroniques vous permet de préconfigurer ce qui se produit lors de l’exécution de chaque composant. Par défaut, lorsqu'une configuration est exécutée, une boîte de dialogue s'affiche pour vous permettre d'enregistrer ou d'ouvrir le fichier. Le même comportement se produit également lorsque vous importez une configuration ER et que vous ne lui configurez pas de destinations spécifiques. Après la création d’une destination pour un composant de sortie principal, cette destination remplace le comportement par défaut et le dossier ou le fichier est envoyé en fonction des paramètres de la destination.

## <a name="availability-and-general-prerequisites"></a>Disponibilité et conditions préalables générales

La fonctionnalité des destinations d'ER n’est pas disponible dans Microsoft Dynamics AX 7.0 (février 2016). Par conséquent, vous devez installer Microsoft Dynamics 365 for Operations version 1611 (novembre 2016) ou ultérieure pour utiliser les types de destination suivants :

- [Courrier électronique](er-destination-type-email.md)
- [Archiver](er-destination-type-archive.md)
- [Fichier](er-destination-type-file.md)
- [Ecran](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)

Vous pouvez également installer l'un des éléments requis suivants. Toutefois, notez que ces solutions de remplacement offrent une expérience de destination ER plus limitée.

- Application Microsoft Dynamics AX version 7.0.1 (mai 2016)
- [Correctif de l'application de gestion des destinations de rapports électroniques](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

Il y a aussi un type de destination [Impression](er-destination-type-print.md). Pour l'utiliser, vous devez installer Microsoft Dynamics 365 Finance version 10.0.9 (avril 2020).

## <a name="overview"></a>Vue d'ensemble

Vous pouvez paramétrer des destinations uniquement pour les configurations d'ER qui ont été [importées](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) dans l'instance Finance actuelle, et pour les formats qui sont disponibles sur la page **Configurations de la gestion des états électroniques**. Le fonctionnalité pour la gestion de destination des ER est disponible ici : **Administration d'organisation** \> **Gestion des états électroniques** \> **Destination de la gestion des états électroniques**. Sur la page **Destination de la gestion des états électroniques**, vous pouvez remplacer le comportement par défaut d'une configuration. Les configurations importées ne sont pas affichées sur cette page jusqu'à ce que vous sélectionniez **Nouveau** puis, dans le champ **Référence**, une configuration pour créer des paramètres de destination.

[![Sélection d'une configuration dans le champ Référence](./media/ER_Destinations-SelectFormat.png)](./media/ER_Destinations-SelectFormat.png)

Après avoir créé une référence, vous pouvez créer une destination de fichier pour chaque composant de sortie de **Dossier** ou de **Fichier** du format ER référencé.

[![Création d'une destination de fichier](./media/ER_Destinations-ConfigureElementDestination.png)](./media/ER_Destinations-ConfigureElementDestination.png)

Ensuite, dans la boîte de dialogue **Paramètres de destination**, vous pouvez activer et désactiver des destinations individuelles pour la destination de fichier. Le bouton **Paramètres** est utilisé pour contrôler l’ensemble des destinations pour une destination de fichier sélectionnée. Dans la boîte de dialogue **Paramètres de destination**, vous pouvez contrôler séparément chaque destination en définissant l'option **Activé** pour celle-ci.

Dans certaines versions de Finance **avant la version 10.0.9**, vous pouvez créer **une destination de fichier** pour chaque composant de sortie du même format, tel qu'un dossier ou un fichier sélectionné dans le champ **Nom du fichier**. Cependant, dans les **versions 10.0.9 et ultérieures**, vous pouvez créer **plusieurs destinations de fichiers** pour chaque composant de sortie du même format.

Par exemple, vous pouvez utiliser cette fonctionnalité pour configurer des destinations de fichier pour un composant de fichier utilisé pour générer un document sortant au format Excel. Une destination ([Archiver](er-destination-type-archive.md)) peut être configurée pour stocker le fichier Excel d'origine dans l'archive des tâches ER et une autre destination ([Email](er-destination-type-email.md)) peut être configurée pour [convertir](#OutputConversionToPDF) le fichier Excel au format PDF et envoyer le fichier PDF par e-mail.

[![Configuration de plusieurs destinations pour un seul élément de format](./media/ER_Destinations-SampleDestinations.png)](./media/ER_Destinations-SampleDestinations.png)

## <a name="destination-types"></a>Types de destinations

Les destinations suivantes sont actuellement prises en charge pour les formats ER. Vous pouvez désactiver ou activer tous les types en même temps. De cette façon, vous pouvez soit ne rien faire soit envoyer le composant à toutes les destinations configurées.

- [Courrier électronique](er-destination-type-email.md)
- [Archiver](er-destination-type-archive.md)
- [Fichier](er-destination-type-file.md)
- [Ecran](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)
- [Imprimer](er-destination-type-print.md)

## <a name="applicability"></a>Conditions d'application

Vous pouvez paramétrer des destinations uniquement pour les configurations d'états électroniques qui ont été importées et pour les formats qui sont disponibles sur la page **Configurations des états électroniques**.

> [!NOTE]
> Les destinations configurées sont spécifiques à l'entreprise. Si vous prévoyez d'utiliser un format ER dans différentes sociétés de l'instance Finance actuelle, vous devez configurer des destinations pour ce format ER pour chacune de ces sociétés.

Lorsque vous configurez des destinations de fichiers pour un format sélectionné, vous les configurez pour l'ensemble du format.

[![Lien Configuration](./media/ER_Destinations-ConfigurationLink.png)](./media/ER_Destinations-ConfigurationLink.png)

En même temps, vous pouvez avoir plusieurs [versions](general-electronic-reporting.md#component-versioning) du format importé dans l'instance Finance actuelle. Vous pouvez les afficher si vous sélectionnez le lien **Configuration** proposé lorsque vous sélectionnez le champ **Référence**.

[![Versions de configuration](./media/ER_Destinations-ConfigurationVersions.png)](./media/ER_Destinations-ConfigurationVersions.png)

Par défaut, les destinations configurées sont appliquées uniquement lorsque vous exécutez une version au format ER dont l'état est soit **Terminé**, soit **Partagé**. Cependant, vous devez parfois utiliser des destinations configurées lorsque la version préliminaire d'un format ER est exécutée. Par exemple, vous modifiez une version provisoire de votre format et vous souhaitez utiliser des destinations configurées pour tester la manière dont la sortie générée sera livrée. Suivez ces étapes pour appliquer des destinations pour un format ER lorsque la version préliminaire est exécutée.

1. Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l'onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Paramétrez l'option **Utiliser des destinations pour le statut de brouillon** sur **Oui**.

[![Option Utiliser des destinations pour le statut de brouillon](./media/ER_Destinations-UserSetting1.png)](./media/ER_Destinations-UserSetting1.png)

Pour utiliser la version de brouillon d'un format ER, vous devez marquer le format ER en conséquence.

1. Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l'onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Définissez l'option **Exécuter la configuration** sur **Oui**.

[![Option Exécuter la configuration](./media/ER_Destinations-UserSetting2.png)](./media/ER_Destinations-UserSetting2.png)

Une fois cette configuration terminée, l'option **Exécuter le brouillon** devient disponible pour les formats ER que vous modifiez. Définissez cette option sur **Oui** pour commencer à utiliser la version de brouillon du format lorsque le format est exécuté.

[![Option Exécuter le brouillon](./media/ER_Destinations-FormatSetting.png)](./media/ER_Destinations-FormatSetting.png)

## <a name="DestinationFailure"></a>Gestion des échecs de destination

Habituellement, un format ER est exécuté dans le cadre d'un processus métier spécifique. Cependant, la livraison d'un document sortant généré lors de l'exécution d'un format ER doit parfois être considérée comme faisant partie de ce processus métier. Dans ce cas, si la livraison d'un document sortant généré vers une destination configurée échoue, l'exécution du processus métier doit être annulée. Pour configurer la destination ER appropriée, sélectionnez l'option **Arrêter le traitement en cas d'échec**.

Par exemple, vous configurez le traitement des paiements fournisseur afin que le format ER **Transfert de crédit ISO20022** soit exécuté pour générer le fichier de paiement et les documents supplémentaires (par exemple, la lettre explicative et l'état de contrôle). Si un paiement doit être considéré comme ayant été traité avec succès uniquement si la lettre explicative est envoyée avec succès par e-mail, vous devez cocher la case **Arrêter le traitement en cas d'échec** pour le composant **CoveringLetter** dans la destination de fichier appropriée, comme indiqué dans l'illustration suivante. Dans ce cas, le statut du paiement sélectionné pour le traitement passe de **Aucun** à **Expédié** uniquement lorsque la lettre explicative générée est acceptée pour livraison par un fournisseur de messagerie configuré dans l'instance Finance.

[![Configuration de la gestion des processus pour l'échec de destination du fichier](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)

Si vous décochez la case **Arrêter le traitement en cas d'échec** pour le composant **CoveringLetter** dans la destination, un paiement sera considéré comme ayant été traité avec succès même si la lettre explicative n'est pas livrée avec succès par e-mail,. Le statut du paiement sera modifié de **Aucun** à **Expédié** même si la lettre explicative ne peut pas être envoyée car, par exemple, l'adresse e-mail du destinataire ou de l'expéditeur est manquante ou incorrecte.

## <a name="OutputConversionToPDF"></a>Conversion de sortie en PDF

Vous pouvez utiliser l'option de conversion PDF pour convertir la sortie au format Microsoft Office (Excel/Word) au format PDF.

### <a name="make-pdf-conversion-available"></a>Rendre la conversion PDF disponible

Pour rendre l'option de conversion PDF disponible dans l'instance Finance actuelle, ouvrez l'espace de travail **Gestion des fonctionnalités** et activez la fonctionnalité **Convertir les documents sortants de rapports électroniques à partir de formats Microsoft Office au format PDF**.

[![Activation de la fonctionnalité de conversion PDF des documents sortants dans Gestion des fonctionnalités](./media/ER_Destinations-EnablePdfConversionFeature.png)](./media/ER_Destinations-EnablePdfConversionFeature.png)

### <a name="applicability"></a>Conditions d'application

L'option de conversion PDF ne peut être activée que pour les composants de fichier utilisés pour générer une sortie au format Microsoft Office Excel ou Word (**fichier Excel**). Lorsque cette option est activée, la sortie générée au format Office est automatiquement convertie au format PDF.

### <a name="limitations"></a>Limites

> [!NOTE]
> Cette fonctionnalité est une fonctionnalité d'aperçu et est soumise aux conditions d'utilisation décrites dans les [Conditions d'utilisation supplémentaires pour Microsoft Dynamics 365 (préversion)](https://go.microsoft.com/fwlink/?linkid=2105274).

> [!NOTE]
> L'option de conversion PDF n'est disponible que pour les déploiements cloud.
>
> Le PDF produit est limité à un nombre maximum de 300 pages.
>
> À l'heure actuelle, seule l'orientation de la page paysage est prise en charge dans le document PDF produit à partir d'une sortie Excel.
>
> Seules les polices système courantes du système d'exploitation Windows sont utilisées pour la conversion d'une sortie qui ne contient aucune police intégrée.

### <a name="use-the-pdf-conversion-option"></a>Utilisez l'option de conversion PDF

Pour activer la conversion PDF pour une destination de fichier, cochez la case **Convertir en PDF**.

[![Activation de la conversion PDF pour une destination de fichier](./media/ER_Destinations-TurnOnPDFConversion.png)](./media/ER_Destinations-TurnOnPDFConversion.png)

## <a name="security-considerations"></a>Considérations de sécurité

Deux types de privilèges et de droits sont utilisés pour les destinations d'états électroniques. Un type contrôle la possibilité globale d'un utilisateur de mettre à jour les destinations qui sont configurées pour une entité juridique (autrement dit, il contrôle l’accès à la page **Destinations des états électroniques**). L’autre type contrôle la capacité de l'utilisateur d’une application à substituer, au moment de l’exécution, les paramètres de destination qu'un développeur d'états électroniques ou un consultant fonctionnel d'états électroniques a configuré.

| Rôle (nom AOA)                     | Nom de rôle                                  | Droit de douane (nom AOA)                     | Nom de droits de douane                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Développeur d'états électroniques             | ERFormatDestinationConfigure        | Configurer la destination du format des états électroniques                |
| ERFunctionalConsultant              | Consultant fonctionnel des états électroniques | ERFormatDestinationConfigure        | Configurer la destination du format des états électroniques                |
| PaymAccountsPayablePaymentsClerk    | Commis au paiement de la comptabilité fournisseur            | ERFormatDestinationRuntimeConfigure | Configurer la destination du format des états électroniques durant l'exécution |
| PaymAccountsReceivablePaymentsClerk | Commis au paiement de la comptabilité client         | ERFormatDestinationRuntimeConfigure | Configurer la destination du format de gestion des états électroniques durant l'exécution |

> [!NOTE]
> Deux privilèges sont utilisés dans les droits précédents. Ces privilèges ont les mêmes noms que les droits correspondants : **ERFormatDestinationConfigure** et **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>J’ai importé des configurations électroniques et je les vois sur la page Configurations des états électroniques. Mais pourquoi je ne les vois pas dans la page Destinations des états électroniques ?

Vérifiez que vous sélectionnez **Nouveau**, puis sélectionnez une configuration dans le champ **Référence**. La page **Destinations des états électroniques** affiche uniquement les configurations pour lesquelles les destinations ont été configurées.

### <a name="is-there-any-way-to-define-which-microsoft-azure-storage-account-and-azure-blob-storage-are-used"></a>Est-il possible de définir quel compte de stockage Microsoft Azure et quel stockage Blob Azure sont utilisés ?

N° Le stockage Blob Microsoft Azure par défaut défini et utilisé pour le système de gestion des documents est utilisé.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Quel est l’objectif de la destination de fichier dans les paramètres de destination ? Que fait ce paramètre ?

La destination **Fichier** est utilisée pour contrôler une boîte de dialogue. Si vous activez cette destination, ou si aucune destination n’est définie pour une configuration, une boîte de dialogue Ouvrir ou Enregistrer s'affiche après la création d’un fichier de sortie.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Pouvez-vous donner un exemple de la formule qui fait référence à un compte fournisseur à laquelle je peux envoyer des courriers électroniques ?

La formule est spécifique à la configuration de l'état électronique. Par exemple, si vous utilisez la configuration du virement ISO 20022, vous pouvez utiliser **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** ou **model. Payments.Creditor.Identification.SourceID** pour obtenir un compte fournisseur associé.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-grouped-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>L'une des configurations de mon format contient plusieurs fichiers qui sont regroupés dans un dossier (par exemple, Folder1 contient fichier1, fichier2 et fichier3). Comment définir des destinations afin que Folder1.zip ne soit pas créé du tout, que fichier1 soit envoyé par courrier électronique, que fichier2 soit envoyé à SharePoint, et que je puisse ouvrir fichier3 immédiatement après l’exécution de la configuration ?

Votre format doit tout d'abord être disponible dans les configurations d'états électroniques. Si cette condition préalable est remplie, ouvrez la page **Destination des états électroniques** et créez une nouvelle référence pour la configuration. Vous devez ensuite disposer de quatre destinations de fichiers, une pour chaque composant de sortie. Créez la première destination du fichier, donnez-lui un nom tel que **Dossier**, puis sélectionnez un nom de fichier qui représente un dossier dans votre configuration. Puis sélectionnez **Paramètres** et assurez-vous que toutes les destinations sont désactivées. Pour cette destination de fichier, le dossier ne sera pas créé. Par défaut, en raison des relations hiérarchiques entre les fichiers et les dossiers parents, les fichiers se comportent de la même manière. En d’autres termes, ils ne seront envoyés nulle part. Pour remplacer ce comportement par défaut, vous devez créer trois destinations de fichier supplémentaires, une pour chaque fichier. Dans les paramètres de la destination de chacun, vous devez activer la destination à laquelle le fichier doit être envoyé.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des états électroniques (ER)](general-electronic-reporting.md)
