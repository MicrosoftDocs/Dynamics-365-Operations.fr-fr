---
title: "Destinations des états électroniques"
description: "Vous pouvez configurer une destination pour chaque configuration de génération d&quot;états électroniques (ER) et son composant de sortie (un dossier ou un fichier). Les utilisateurs qui disposent des droits d’accès appropriés peuvent également modifier les paramètres de destination au moment de l’exécution. Cet article explique la gestion des destinations des états électroniques, les types de destinations pris en charge et des considérations sur la sécurité."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: d38d05fe445bf0326d408038dff84ccf8c0ff64c
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-destinations"></a>Destinations des états électroniques

Vous pouvez configurer une destination pour chaque configuration de génération d'états électroniques (ER) et son composant de sortie (un dossier ou un fichier). Les utilisateurs qui disposent des droits d’accès appropriés peuvent également modifier les paramètres de destination au moment de l’exécution. Cet article explique la gestion des destinations des états électroniques, les types de destinations pris en charge et des considérations sur la sécurité.

Les configurations de format des états électroniques contiennent généralement au moins un composant de sortie : un fichier. En règle générale, les configurations contiennent plusieurs composants de sortie de fichiers de différents types (par exemple, XML, TXT ou XLSX) qui sont regroupés dans un dossier unique ou dans plusieurs dossiers. La gestion des destinations des états électroniques vous permet de préconfigurer ce qui se produit lors de l’exécution de chaque composant. Par défaut, lorsqu'une configuration est exécutée, une boîte de dialogue qui permet à l'utilisateur enregistrer ou pour ouvrir le fichier. Le même comportement est également utilisé lorsque vous importez une configuration d'état électronique et que vous ne configurez pas de destinations spécifiques pour lui. Après la création d’une destination pour un composant de sortie principal, cette destination remplace le comportement par défaut et le dossier ou le fichier est envoyé en fonction des paramètres de la destination.

## <a name="availability-and-general-prerequisites"></a>Disponibilité et conditions préalables générales
La fonctionnalité de destination d'ER n'est pas disponible dans Microsoft Dynamics 365 pour la publication des opérations 7,0 (février 2016). Par conséquent, vous devez installer Microsoft Dynamics 365 pour les opérations (novembre 2016 lancement) à utiliser toutes les tâches décrites dans cette rubrique. Sinon, vous pouvez installer une des conditions préalables suivantes. Toutefois, notez que ces l'autre fournissent une expérience plus limitée de destination d'ER.

-   Microsoft Dynamics 365 pour la version 7.0.1 d'application Opérations (mai 2016)
-   [Correctif d’application](https://fix.lcs.dynamics.com/issue/results/?q=3160213) de gestion des destinations d'états électoniques

Vous pouvez paramétrer des destinations uniquement pour les configurations d'états électroniques qui ont été importées et pour les formats qui sont disponibles sur la page **Configurations des états électroniques**.

## <a name="overview"></a>Vue d'ensemble
La fonctionnalité de gestion de destination d'ER est disponible ** Administration d'organisation ** &gt; ** à la génération d'états électronique **. Ici, vous pouvez remplacer le comportement par défaut pour une configuration. Les configurations importées ne sont pas affichées ici tant que vous ne cliquez pas sur **Nouveau** puis, dans le champ **Référence**, sélectionnez une configuration pour créer des paramètres de destination.

[![sélectionnant une configuration dans le champ Référence (]. /media/ger-destinations-2-1611-1024x574.jpg)](. /media/ger-destinations-2-1611.jpg) 

Après avoir créé une référence, vous pouvez créer une destination de fichier pour chaque incident ou, pour un fichier. 

[![créant une destination de fichier (]. /media/ger-destinations-1611-1024x586.jpg)](. /media/ger-destinations-1611.jpg)

**Remarque :** vous pouvez créer une destination de fichier pour chaque composant de sortie du même format, tel qu'un dossier ou un fichier sélectionné dans le champ **Nom du fichier**. Vous pouvez ensuite activer et désactiver certaines destinations pour la destination du fichier pour ** des paramètres de destination ** la boîte de dialogue. Le bouton **Paramètres** est utilisé pour contrôler l’ensemble des destinations pour une destination de fichier sélectionnée. Dans la boîte de dialogue **Paramètres de destination**, vous pouvez contrôler séparément chaque destination en définissant l'option **Activé** pour celle-ci.

[boîte de dialogue Paramètres de destination![] (. /media/ger-destinations-settings-1611-1024x589.jpg)](. /media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Types de destinations
Différents types de destinations sont pris en charge. Vous pouvez désactiver ou activer tous les types en même temps. De cette façon, vous pouvez soit ne rien faire soit envoyer le composant à toutes les destinations configurées. Les sections suivantes décrivent les destinations qui sont prises en charge.

### <a name="email-destination"></a>Destination du courrier électronique

Définissez **Activé **sur **Oui** pour envoyer un fichier de sortie par courrier électronique. Une fois cette option est activée, vous pouvez spécifier les destinataires d'e-mail, et modifiez le sujet et le corps du message e-mail. Vous pouvez paramétrer des textes constants pour l'objet et le corps d'e-mail, ou vous pouvez utiliser les formules d'ER pour créer dynamiquement les textes d'e-mail. Vous pouvez configurer les adresses e-mail de l'ER de deux manières. La configuration peut être complétée de la même manière que la fonctionnalité de gestion de l'impression dans Dynamics 365 pour les opérations le complète. Sinon, vous pouvez résoudre une adresse e-mail à l'aide d'une référence directe à la configuration d'ER via une formule.

### <a name="email-address-types"></a>Types d'adresse e-mail

Lorsque vous cliquez sur ** modifiez ** pour ** ** ou ** cc ** le champ, ** e-mail ** la boîte de dialogue s'affiche. Vous pouvez ensuite sélectionner le type d'adresse e-mail à utiliser.

[e-mail![à la boîte de dialogue] (. /media/ger-destinations-email-1-1611-1024x588.jpg)](. /media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Gestion de l'impression

Si vous sélectionnez ** e-mail de gestion de l'impression ** type, vous pouvez entrer les adresses e-mail fixes dans ** destination ** le champ. Pour utiliser les adresses e-mail qui ne sont pas résolus, vous devez sélectionner le type de source d'e-mail pour une destination de fichier. Les valeurs suivantes sont prises en charge : ** Client **, ** fournisseur **, ** prospect **, ** contact **, ** concurrent **, ** travailleur **, ** candidat **, ** fournisseur potentiel **, et ** fournisseur non - autorisé **. Après avoir sélectionné un type de source d'e-mail, utilisez le bouton en regard ** envoyez un message e-mail le compte source ** du champ pour ouvrir ** Concepteur de formule ** l'écran. Cet écran permet d'associer une formule qui représente le compte sélectionné de partie à la disposition d'e-mail.

[![configurer le type d'e-mail de gestion de l'impression (]. /media/ger-destinations-email-2-1611-1024x588.jpg)](. /media/ger-destinations-email-2-1611.jpg) 

Notez que les formules sont spécifiques à la configuration de l'état électronique. Dans le champ **Formule**, entrez une référence spécifique au document pour un type de partie Client ou Fournisseur. Au lieu de taper, vous pouvez rechercher un nœud de source de données qui représente le compte client ou fournisseur, puis cliquer sur le bouton **Ajouter une source de données** pour mettre la formule à jour. Par exemple, si vous utilisez la configuration de virement bancaire ISO 20022, le nœud représentant un compte fournisseur est : **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID**. Sinon, entrez une valeur de chaîne, par exemple **DE-001**, pour enregistrer une formule.

[![Formula designer](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

Dans ** e-mail ** la boîte de dialogue, cliquez sur le casier de nouveau en regard ** compte source d'e-mail ** du champ pour supprimer définitivement la formule du compte source d'e-mail. Sinon, ouvrez le Concepteur de formule pour modifier une formule qui a été précédemment enregistrée. Pour affecter les adresses e-mail, cliquez sur ** modifiez ** pour ouvrir ** adresse e-mail d'affecter ** la boîte de dialogue.

[![affectant les adresses e-mail pour une destination d'e-mail (]. /media/ger-destinations-email-3-1611-1024x587.jpg)](. /media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>E-mail de configuration

Utilise ce type d'e-mail si la configuration que vous utilisez a un nœud dans les sources de données qui représente une adresse e-mail. Vous pouvez utiliser des sources de données et les fonctions dans le Concepteur de formule pour obtenir une adresse e-mail correctement mis en forme.

[![affectant une source de données d'adresse e-mail pour une destination d'e-mail (]. /media/ger-destinations-email-4-1611-1024x587.jpg)](. /media/ger-destinations-email-4-1611.jpg) 

**Remarque :** un serveur SMTP (Simple Mail Transfer Protocol) doit être configuré et disponible. Vous pouvez spécifier votre serveur SMTP dans Dynamics 365 pour les opérations, ** Administration du système ** &gt; ** au paramétrage ** &gt; ** e-mail ** &gt; ** les paramètres d'e-mail **.

### <a name="archive-destination"></a>Destination de l'archive

Vous pouvez utiliser cette option pour envoyer la sortie vers un dossier Microsoft SharePoint ou le stockage Microsoft Azure. Définissez **Activé** sur **Oui **pour envoyer la sortie vers une destination définie par le type de document sélectionné. Seuls les types de documents où le groupe est défini sur **Fichier** sont disponibles pour la sélection. Vous pouvez définir des types de documents ** Administration d'organisation ** &gt; ** à la gestion des documents ** &gt; ** des types de documents **. La configuration des destinations d'états électroniques est identique à la configuration du système de gestion des documents.

[page de types de documents![] (. /media/ger_documenttypefile-1024x542.jpg)](. /media/ger_documenttypefile.jpg) 

L’emplacement détermine où le fichier est enregistré. Après ** une archive ** la destination activée, les résultats de l'exécution de configuration peuvent être stockés dans les archives de tâche. Vous pouvez afficher les résultats ** Administration d'organisation ** &gt; ** à la génération d'états électronique ** &gt; ** des tâches archivées par génération d'états électronique **. ** Remarque : ** Vous pouvez sélectionner un type de document pour l'archivage des tâches dans Dynamics 365 pour les opérations, ** Administration d'organisation ** &gt; ** aux espaces de travail ** &gt; ** génération d'états électronique ** &gt; ** des paramètres électroniques de génération d'états **.

#### <a name="sharepoint"></a>SharePoint

Vous pouvez enregistrer un fichier dans un dossier SharePoint désigné. Vous définissez le serveur par défaut SharePoint ** Administration d'organisation ** &gt; ** à la gestion des documents ** &gt; ** les paramètres de gestion des documents **, sous ** SharePoint ** l'onglet. Une fois le dossier de SharePoint soit configuré, vous pouvez le sélectionner comme dossier où la sortie d'ER sera enregistrée pour le type de document. 

[![sélectionnant un dossier de SharePoint (]. /media/ger_sharepointfolderselection-1024x543.jpg)](. /media/ger_sharepointfolderselection.jpg) 

#### <a name="azure-storage"></a>Stockage Azure

Lorsque l’emplacement du type de document est défini sur **Répertoire d'archivage**, vous pouvez enregistrer un fichier dans le stockage Azure.

### <a name="file-destination"></a>Destination du fichier

Si vous définissez ** activé ** sur Oui ** **, une boîte en cours ou sauvegarde de dialogue s'affiche lorsque la configuration est toujours en cours de exécution.

### <a name="screen-destination"></a>Destination d'écran

Si vous définissez ** activé ** sur Oui ** **, un aperçu de la sortie est créé. Vous pouvez afficher certains types de fichiers, tels que XML, TXT, ou PDF, directement dans une fenêtre du navigateur. Pour d'autres types de fichiers, un tel Microsoft Excel ou Word, le service en ligne de Microsoft Office est utilisé.

### <a name="power-bi-destination"></a>Destination BI de courant

Ensemble ** activé ** sur Oui ** ** pour utiliser la configuration d'ER pour réorganiser le transfert des données à partir de votre instance de Dynamics 365 pour les opérations aux services BI de courant de Microsoft. Les fichiers transférés sont enregistrés sur une instance de serveur Microsoft SharePoint qui doit être configurée {{dans:for}} cet objectif. Pour plus d'informations, voir [utilisez une configuration électronique de génération d'états pour fournir au projet BI d'alimentation des données Dynamics 365 pour les opérations] (general-electronic-reporting-report-configuration-get-data-powerbi.md). **Conseil :** pour substituer le comportement par défaut (autrement dit, la boîte de dialogue de configuration), vous pouvez créer une référence de destination et une destination de fichier pour le composant de sortie principal et ensuite désactiver toutes les destinations.

## <a name="security-considerations"></a>Considérations de sécurité
Deux types de privilèges et de droits sont utilisés pour les destinations d'états électroniques. Un type contrôle la capacité de maintenir les destinations générales qui sont configurées pour une entité juridique (c'est-à-dire, elle contrôle l'accès ** les destinations électroniques de génération d'états ** à la page). L’autre type contrôle la capacité de l’utilisateur d’une application à substituer, au moment de l’exécution, les paramètres de destination qui sont configurés par un développeur d'états électroniques ou un consultant fonctionnel d'états électroniques.

| Rôle (nom AOA)                     | Nom de rôle                                  | Droit de douane (nom AOA)                     | Nom de droits de douane                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Développeur d'états électroniques             | ERFormatDestinationConfigure        | Configurer la destination du format des états électroniques                |
| ERFunctionalConsultant              | Consultant fonctionnel des états électroniques | ERFormatDestinationConfigure        | Configurer la destination du format des états électroniques                |
| PaymAccountsPayablePaymentsClerk    | Commis au paiement de la comptabilité fournisseur            | ERFormatDestinationRuntimeConfigure | Configurer la destination du format des états électroniques durant l'exécution |
| PaymAccountsReceivablePaymentsClerk | Commis au paiement de la comptabilité client         | ERFormatDestinationRuntimeConfigure | Configurer la destination du format des états électroniques durant l'exécution |

**Remarque :** deux privilèges sont utilisés dans les droits précédents. Ces privilèges ont les mêmes noms que les droits correspondants : **ERFormatDestinationConfigure** et **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Forum aux questions
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>J’ai importé des configurations électroniques et je les vois sur la page Configurations des états électroniques. À partir de la raison mais je ne les vois pas dans la page e-mail de destination de génération d'états ?

Assurez-vous que vous cliquez sur ** nouveau ** puis sélectionner une configuration dans ** référence ** le champ. Sur la page **Destinations des états électroniques**, vous ne pouvez voir que les configurations pour lesquelles les destinations ont été configurées.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>Existe -t-il une manière de définir que le stockage azuré d'objet blob de compte et d'azur de stockage sont utilisé ?

N° Le stockage azuré par défaut d'objet blob défini et utilisé pour le système de gestion des documents est utilisé.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Quel est l'objet de la destination du fichier dans les paramètres de destination ? Que fait ce paramètre ?

La destination **Fichier** est utilisée pour contrôler une boîte de dialogue. Si vous activez cette destination, ou si aucune destination n'est définie pour une configuration, une zone en cours ou sauvegarde de dialogue après qu'un fichier de sortie est créé.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Pouvez-vous donner un exemple de la formule qui fait référence à un compte fournisseur à laquelle je peux envoyer des courriers électroniques ?

La formule est spécifique à la configuration de l'état électronique. Par exemple, si vous utilisez la configuration du virement ISO 20022, vous pouvez utiliser **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** ou **model. Payments.Creditor.Identification.SourceID** pour obtenir un compte fournisseur associé.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>L'une des configurations de mon format contient plusieurs fichiers qui sont regroupés dans un dossier (par exemple, Folder1 contient fichier1, fichier2 et fichier3). Comment définir des destinations afin que Folder1.zip ne soit pas créé du tout, que fichier1 soit envoyé par courrier électronique, que fichier2 soit envoyé à SharePoint, et que je puisse ouvrir fichier3 immédiatement après l’exécution de la configuration ?

La condition préalable est que votre format doit être disponible dans les configurations d'ER. Si vous avez votre format, ouvrez la page **Destination des états électroniques** et créez une nouvelle référence pour cette configuration. Vous devez ensuite disposer de quatre destinations de fichiers, une pour chaque composant de sortie. Créez la première destination du fichier, donnez-lui un nom tel que **Dossier**, puis sélectionnez un nom de fichier qui représente un dossier dans votre configuration. Puis cliquez sur **Paramètres** et assurez-vous que toutes les destinations sont désactivées. Pour cette destination de fichier, le dossier ne sera pas créé. Par défaut, en raison des relations hiérarchiques entre les fichiers et les dossiers parents, les fichiers se comportent de la même manière. En d’autres termes, ils ne seront envoyés nulle part. Pour remplacer ce comportement par défaut, vous devez créer trois destinations de fichier supplémentaires, une pour chaque fichier. Dans les paramètres de la destination de chacun, vous devez activer la destination à laquelle le fichier doit être envoyé.

# <a name="see-also"></a>Voir également :

[Vue d'ensemble des États électroniques](general-electronic-reporting.md)


