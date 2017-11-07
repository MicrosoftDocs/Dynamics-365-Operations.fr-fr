---
title: "Destinations des états électroniques"
description: "Vous pouvez configurer une destination pour chaque configuration de génération d'états électroniques (ER) et son composant de sortie (un dossier ou un fichier). Les utilisateurs qui disposent des droits d’accès appropriés peuvent également modifier les paramètres de destination au moment de l’exécution. Cet article explique la gestion des destinations des états électroniques, les types de destinations pris en charge et des considérations sur la sécurité."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dedabf13044be30a67a945ff4ca2ecfb1eea8150
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="electronic-reporting-destinations"></a>Destinations des états électroniques

[!include[banner](../includes/banner.md)]


Vous pouvez configurer une destination pour chaque configuration de génération d'états électroniques (ER) et son composant de sortie (un dossier ou un fichier). Les utilisateurs qui disposent des droits d’accès appropriés peuvent également modifier les paramètres de destination au moment de l’exécution. Cet article explique la gestion des destinations des états électroniques, les types de destinations pris en charge et des considérations sur la sécurité.

Les configurations de format des états électroniques contiennent généralement au moins un composant de sortie : un fichier. En règle générale, les configurations contiennent plusieurs composants de sortie de fichiers de différents types (par exemple, XML, TXT ou XLSX) qui sont regroupés dans un dossier unique ou dans plusieurs dossiers. La gestion des destinations des états électroniques vous permet de préconfigurer ce qui se produit lors de l’exécution de chaque composant. Par défaut, lorsqu'une configuration est exécutée, une boîte de dialogue s'affiche pour permettre à l'utilisateur d'enregistrer ou d'ouvrir le fichier. Le même comportement est également utilisé lorsque vous importez une configuration d'état électronique et que vous ne configurez pas de destinations spécifiques pour lui. Après la création d’une destination pour un composant de sortie principal, cette destination remplace le comportement par défaut et le dossier ou le fichier est envoyé en fonction des paramètres de la destination.

## <a name="availability-and-general-prerequisites"></a>Disponibilité et conditions préalables générales
La fonctionnalité des destinations d'états électroniques n’est pas disponible dans Microsoft Dynamics AX 7.0 (février 2016). Par conséquent, vous devez installer Microsoft Dynamics 365 for Operations version 1611 (novembre 2016) pour utiliser toutes les fonctions décrites dans cette rubrique. Vous pouvez également installer l'un des éléments requis suivants. Toutefois, notez que ces solutions de remplacement offrent une expérience plus limitée.

-   Application Microsoft Dynamics AX 7.0.1 (mai 2016)
-   [Correctif d’application](https://fix.lcs.dynamics.com/issue/results/?q=3160213) de gestion des destinations d'états électoniques

Vous pouvez paramétrer des destinations uniquement pour les configurations d'états électroniques qui ont été importées et pour les formats qui sont disponibles sur la page **Configurations des états électroniques**.

## <a name="overview"></a>Vue d'ensemble
La fonctionnalité de gestion des destinations d'états électroniques est disponible dans **Administration d’organisation** &gt; **États électroniques**. Ici, vous pouvez remplacer le comportement par défaut pour une configuration. Les configurations importées ne sont pas affichées ici tant que vous ne cliquez pas sur **Nouveau** puis, dans le champ **Référence**, sélectionnez une configuration pour créer des paramètres de destination.

[![Sélection d'une configuration dans le champ Référence](./media/ger-destinations-2-1611-1024x574.jpg)](./media/ger-destinations-2-1611.jpg) 

Une fois que vous avez créé une référence, vous pouvez créer une destination de fichier pour chaque dossier ou pour un fichier. 

[![Création d'une destination de fichier](./media/ger-destinations-1611-1024x586.jpg)](./media/ger-destinations-1611.jpg)

**Remarque :** vous pouvez créer une destination de fichier pour chaque composant de sortie du même format, tel qu'un dossier ou un fichier sélectionné dans le champ **Nom du fichier**. Vous pouvez ensuite activer et désactiver des destinations individuelles pour la destination de fichier dans la boîte de dialogue **Paramètres de destination**. Le bouton **Paramètres** est utilisé pour contrôler l’ensemble des destinations pour une destination de fichier sélectionnée. Dans la boîte de dialogue **Paramètres de destination**, vous pouvez contrôler séparément chaque destination en définissant l'option **Activé** pour celle-ci.

[![Boîte de dialogue Paramètres de destination](./media/ger-destinations-settings-1611-1024x589.jpg)](./media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Types de destinations
Différents types de destinations sont pris en charge. Vous pouvez désactiver ou activer tous les types en même temps. De cette façon, vous pouvez soit ne rien faire soit envoyer le composant à toutes les destinations configurées. Les sections suivantes décrivent les destinations qui sont prises en charge.

### <a name="email-destination"></a>Destination du courrier électronique

Définissez **Activé** sur **Oui** pour envoyer un fichier de sortie par courrier électronique. Une fois cette option activée, vous pouvez spécifier les destinataires du message et modifier l'objet et le corps du courrier électronique. Vous pouvez paramétrer des textes constants pour l'objet et le corps du courrier électronique, ou vous pouvez utiliser des formules de génération d'états électroniques pour créer dynamiquement les textes de courrier électronique. Vous pouvez configurer les adresses électroniques pour les états électroniques de deux manières. La configuration peut être effectuée de la même manière que la fonctionnalité de gestion de l'impression dans Finance and Operations. Vous pouvez également résoudre une adresse électronique en utilisant une référence directe à la configuration d'états électroniques via une formule.

### <a name="email-address-types"></a>Types d'adresses électroniques

Lorsque vous cliquez sur **Modifier** pour le champ **À** ou **Cc**, la boîte de dialogue **E-mail à** s'affiche. Vous pouvez ensuite sélectionner le type d'adresse électronique à utiliser.

[![Boîte de dialogue E-mail à](./media/ger-destinations-email-1-1611-1024x588.jpg)](./media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Gestion de l'impression

Si vous sélectionnez le type **E-mail de gestion de l'impression**, vous pouvez entrer des adresses électroniques fixes dans le champ **À**. Pour utiliser des adresses électroniques non fixes, vous devez sélectionner le type de source du courrier électronique pour une destination de fichier. Les valeurs suivantes sont prises en charge : **Client**, **Fournisseur**, **Prospect**, **Contact**, **Concurrent**, **Collaborateur**, **Candidat**, **Fournisseur potentiel** et **Fournisseur non autorisé**. Après avoir sélectionné un type de source de courrier électronique, utilisez le bouton en regard **Compte source de l'e-mail** pour ouvrir l'écran **Concepteur de formule**. Cet écran permet d'associer une formule qui représente le compte tiers sélectionné à la destination du courrier électronique.

[![Configurer un type de courrier électronique de gestion de l'impression](./media/ger-destinations-email-2-1611-1024x588.jpg)](./media/ger-destinations-email-2-1611.jpg) 

Notez que les formules sont spécifiques à la configuration de l'état électronique. Dans le champ **Formule**, entrez une référence spécifique au document pour un type de partie Client ou Fournisseur. Au lieu de taper, vous pouvez rechercher un nœud de source de données qui représente le compte client ou fournisseur, puis cliquer sur le bouton **Ajouter une source de données** pour mettre la formule à jour. Par exemple, si vous utilisez la configuration de virement bancaire ISO 20022, le nœud représentant un compte fournisseur est : **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID**. Sinon, entrez une valeur de chaîne, par exemple **DE-001**, pour enregistrer une formule.

[![Concepteur de formule](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

Dans la boîte de dialogue **E-mail à**, cliquez sur la corbeille de recyclage en regard du champ **Compte source de l'e-mail** pour supprimer définitivement la formule pour le compte source du courrier électronique. Vous pouvez également ouvrir le concepteur de formule pour modifier une formule qui a été précédemment enregistrée. Pour affecter des adresses électroniques, cliquez sur **Modifier** pour ouvrir la boîte de dialogue **Affecter des adresses e-mail**.

[![Affectation d'adresses électroniques pour une destination de courrier électronique](./media/ger-destinations-email-3-1611-1024x587.jpg)](./media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>E-mail de configuration

Utilisez ce type de courrier électronique si la configuration que vous utilisez a un nœud dans les sources de données qui représente une adresse électronique. Vous pouvez utiliser les sources et fonctions de données du concepteur de formule pour obtenir une adresse électronique correctement mise en forme.

[![Affectation d'une source de données d'adresse électronique pour une destination de courrier électronique](./media/ger-destinations-email-4-1611-1024x587.jpg)](./media/ger-destinations-email-4-1611.jpg) 

**Remarque :** un serveur SMTP (Simple Mail Transfer Protocol) doit être configuré et disponible. Vous pouvez spécifier votre serveur SMTP dans Finance and Operations sous **Administration système** &gt; **Paramétrage** &gt; **E-mail** &gt; **Paramètres d'e-mail**.

### <a name="archive-destination"></a>Destination de l'archive

Vous pouvez utiliser cette option pour envoyer la sortie vers un dossier Microsoft SharePoint ou le stockage Microsoft Azure. Définissez **Activé** sur **Oui** pour envoyer la sortie vers une destination définie par le type de document sélectionné. Seuls les types de documents où le groupe est défini sur **Fichier** sont disponibles pour la sélection. Vous définissez les types de documents dans **Administration d’organisation** &gt; **Gestion de documents** &gt; **Types de documents**. La configuration des destinations d'états électroniques est identique à la configuration du système de gestion des documents.

[![Page Types de documents](./media/ger_documenttypefile-1024x542.jpg)](./media/ger_documenttypefile.jpg) 

L’emplacement détermine où le fichier est enregistré. Une fois la destination **Archive** activée, les résultats de l'exécution de la configuration peuvent être enregistrés dans l'archive Tâche. Vous pouvez afficher les résultats sous **Administration d'organisation** &gt; **Gestion des états électroniques** &gt; **Tâches de gestion des états électroniques archivées**. **Remarque :** vous pouvez sélectionner un type de document pour l'archive Tâche dans Finance and Operations, sous **Administration d'organisation** &gt; **Espaces de travail** &gt; **Gestion des états électroniques** &gt; **Paramètres de gestion des états électroniques**.

#### <a name="sharepoint"></a>SharePoint

Vous pouvez enregistrer un fichier dans un dossier SharePoint désigné. Définissez le serveur SharePoint par défaut dans **Administration d'organisation** &gt; **Gestion des documents** &gt; **Paramètres de gestion des documents** dans l'onglet **SharePoint**. Une fois le dossier SharePoint configuré, vous pouvez le sélectionner comme dossier où la sortie d'état électronique sera enregistrée pour le type de document. 

[![Sélection d'un dossier SharePoint](./media/ger_sharepointfolderselection-1024x543.jpg)](./media/ger_sharepointfolderselection.jpg) 

#### <a name="azure-storage"></a>Stockage Azure

Lorsque l’emplacement du type de document est défini sur **Répertoire d'archivage**, vous pouvez enregistrer un fichier dans le stockage Azure.

### <a name="file-destination"></a>Destination du fichier

Si vous définissez **Activé** sur **Oui**, une boîte de dialogue Ouvrir ou Enregistrer s'affiche lorsque l'exécution de la configuration est terminée.

### <a name="screen-destination"></a>Destination d'écran

Si vous définissez **Activé** sur **Oui**, un aperçu de la sortie est créé. Vous pouvez afficher certains types de fichiers, tels que XML, TXT ou PDF, directement dans une fenêtre du navigateur. Pour les autres types de fichiers, tels que Microsoft Excel ou Word, le service Microsoft Office Online est utilisé.

### <a name="power-bi-destination"></a>Destination Power BI

Définissez **Activé** sur **Oui** pour utiliser la configuration de génération d'états électroniques pour organiser le transfert des données entre votre instance de Finance and Operations et les services Microsoft Power BI. Les fichiers transférés sont stockés sur une instance Microsoft SharePoint Server qui doit être configurée à cette fin. Pour plus d'informations, voir [Utiliser une configuration de génération d'états électroniques pour fournir à Power BI des données de Finance and Operations](general-electronic-reporting-report-configuration-get-data-powerbi.md). **Conseil :** pour substituer le comportement par défaut (autrement dit, la boîte de dialogue de configuration), vous pouvez créer une référence de destination et une destination de fichier pour le composant de sortie principal et ensuite désactiver toutes les destinations.

## <a name="security-considerations"></a>Considérations de sécurité
Deux types de privilèges et de droits sont utilisés pour les destinations d'états électroniques. Un type contrôle la possibilité de mettre à jour les destinations globales qui sont configurées pour une entité juridique (autrement dit, il contrôle l’accès à la page **Destinations des états électroniques**). L’autre type contrôle la capacité de l’utilisateur d’une application à substituer, au moment de l’exécution, les paramètres de destination qui sont configurés par un développeur d'états électroniques ou un consultant fonctionnel d'états électroniques.

| Rôle (nom AOA)                     | Nom de rôle                                  | Droit de douane (nom AOA)                     | Nom de droits de douane                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Développeur d'états électroniques             | ERFormatDestinationConfigure        | Configurer la destination du format des états électroniques                |
| ERFunctionalConsultant              | Consultant fonctionnel des états électroniques | ERFormatDestinationConfigure        | Configurer la destination du format des états électroniques                |
| PaymAccountsPayablePaymentsClerk    | Commis au paiement de la comptabilité fournisseur            | ERFormatDestinationRuntimeConfigure | Configurer la destination du format des états électroniques durant l'exécution |
| PaymAccountsReceivablePaymentsClerk | Commis au paiement de la comptabilité client         | ERFormatDestinationRuntimeConfigure | Configurer la destination du format des états électroniques durant l'exécution |

**Remarque :** deux privilèges sont utilisés dans les droits précédents. Ces privilèges ont les mêmes noms que les droits correspondants : **ERFormatDestinationConfigure** et **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Forum aux questions
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>J’ai importé des configurations électroniques et je les vois sur la page Configurations des états électroniques. Mais pourquoi je ne les vois pas dans la page Destinations des états électroniques ?

Vérifiez que vous cliquez sur **Nouveau**, puis sélectionnez une configuration dans le champ **Référence**. Sur la page **Destinations des états électroniques**, vous ne pouvez voir que les configurations pour lesquelles les destinations ont été configurées.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>Est-il possible de définir quel compte de stockage Azure et quel stockage d'objets blobs Azure sont utilisés ?

Non. Le stockage d'objets blobs Azure par défaut défini et utilisé pour le système de gestion des documents est utilisé.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Quel est l’objectif de la destination de fichier dans les paramètres de destination ? Que fait ce paramètre ?

La destination **Fichier** est utilisée pour contrôler une boîte de dialogue. Si vous activez cette destination, ou si aucune destination n’est définie pour une configuration, une boîte de dialogue Ouvrir ou Enregistrer s'affiche après la création d’un fichier de sortie.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Pouvez-vous donner un exemple de la formule qui fait référence à un compte fournisseur à laquelle je peux envoyer des courriers électroniques ?

La formule est spécifique à la configuration de l'état électronique. Par exemple, si vous utilisez la configuration du virement ISO 20022, vous pouvez utiliser **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** ou **model. Payments.Creditor.Identification.SourceID** pour obtenir un compte fournisseur associé.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>L'une des configurations de mon format contient plusieurs fichiers qui sont regroupés dans un dossier (par exemple, Folder1 contient fichier1, fichier2 et fichier3). Comment définir des destinations afin que Folder1.zip ne soit pas créé du tout, que fichier1 soit envoyé par courrier électronique, que fichier2 soit envoyé à SharePoint, et que je puisse ouvrir fichier3 immédiatement après l’exécution de la configuration ?

La condition préalable est que le format doit être disponible dans les configurations d'états électroniques. Si vous avez votre format, ouvrez la page **Destination des états électroniques** et créez une nouvelle référence pour cette configuration. Vous devez ensuite disposer de quatre destinations de fichiers, une pour chaque composant de sortie. Créez la première destination du fichier, donnez-lui un nom tel que **Dossier**, puis sélectionnez un nom de fichier qui représente un dossier dans votre configuration. Puis cliquez sur **Paramètres** et assurez-vous que toutes les destinations sont désactivées. Pour cette destination de fichier, le dossier ne sera pas créé. Par défaut, en raison des relations hiérarchiques entre les fichiers et les dossiers parents, les fichiers se comportent de la même manière. En d’autres termes, ils ne seront envoyés nulle part. Pour remplacer ce comportement par défaut, vous devez créer trois destinations de fichier supplémentaires, une pour chaque fichier. Dans les paramètres de la destination de chacun, vous devez activer la destination à laquelle le fichier doit être envoyé.

# <a name="see-also"></a>Voir également :

[Vue d'ensemble des États électroniques](general-electronic-reporting.md)




