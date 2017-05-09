---
title: "Réinitialiser le magasin de données d&quot;états financiers après avoir restauré une base de données"
description: "Cette rubrique décrit la procédure de réinitialisation d&quot;un magasin de données d&quot;états financiers après avoir restauré une base de données Microsoft Dynamics 365 for Operations."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-08 16 - 20 - 13
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 3967cbb869fbb23d5d7716f619e4c22b4a273921
ms.lasthandoff: 03/29/2017


---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Réinitialiser le magasin de données d'états financiers après avoir restauré une base de données

Cette rubrique décrit la procédure de réinitialisation d'un magasin de données d'états financiers après avoir restauré une base de données Microsoft Dynamics 365 for Operations. 

Il existe plusieurs scénarios où vous devrez peut-être restaurer votre base de données Dynamics 365 for Operations à partir d'une sauvegarde ou copier la base de données d'un autre environnement. Dans ce cas, vous devez également suivre les étapes appropriées pour garantir que le magasin de données d'états financiers utilise correctement la base de données Dynamics 365 for Operations. Si vous avez des questions sur la réinitialisation du magasin de données d'états financiers pour une raison autre que la restauration d'une base de données Dynamics 365 for Operations, reportez-vous à [Réinitialisation du magasin de données d'états financiers](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) pour plus d'informations. Notez que les étapes de ce processus sont prises en charge pour Dynamics 365 for Operations Publication de mai 2016 (version app 7.0.1265.23014 et reporting financier version 7.0.10000.4) et versions plus récentes. Si vous avez une version antérieure de Dynamics 365 for Operations, veuillez contacter notre équipe de Support pour l'assistance.

## <a name="export-report-definitions"></a>Exporter des définitions d'état
Premièrement, exportez les créations de rapports situées dans le Concepteur de rapports, en utilisant les étapes suivantes :

1.  Dans le Concepteur de rapports, accédez à **Société** &gt; **Groupes de blocs élémentaires**.
2.  Sélectionnez le groupe de blocs élémentaires à exporter, puis cliquez sur **Exporter**. **Remarque :** Pour Dynamics 365 for Operations, un seul groupe de blocs élémentaires est pris en charge, **Valeur par défaut**.
3.  Sélectionnez des définitions de rapport à exporter :
    -   Pour exporter toutes vos définitions de rapport et les blocs élémentaires associés, cliquez sur **Sélectionner tout**.
    -   Pour exporter des rapports, lignes, colonnes, organigrammes ou ensembles de dimensions spécifiques, cliquez sur l'onglet approprié et sélectionnez les éléments à exporter. Maintenez la touche CTRL enfoncée pour sélectionner plusieurs éléments dans un onglet. Lorsque vous sélectionnez des rapports à exporter, les lignes, colonnes, organigrammes et ensembles de dimensions associés doivent être sélectionnés.

4.  Cliquez sur **Exporter**.
5.  Entrez un nom et sélectionnez un emplacement sûr où vous souhaitez enregistrer les définitions de rapport exportées.
6.  Cliquez sur **Enregistrer**.

Le fichier peut être copié ou téléchargé à un emplacement sûr, lui permettant d'être importé dans un environnement différent à tout moment. Les informations relatives à l'utilisation d'un compte de stockage Microsoft Azure se trouvent dans le champ [Transférer les données avec l'utilitaire de ligne de commande AzCopy](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy). **Remarque :** Microsoft ne fournit pas un compte de stockage dans le cadre de l'accord Dynamics 365 for Operations. Vous devez acheter un compte de stockage ou utiliser le compte de stockage d'un abonnement Azure distinct. **Important :** Tenez compte du comportement du lecteur D sur les machines virtuelles Azure. N'utilisez pas les groupes de blocs élémentaires exportés ici définitivement. Pour plus d'informations sur les lecteurs temporaires, voir [Comprendre le lecteur temporaire sur les machines virtuelles Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Arrêter les services
Utilisez l'ordinateur Bureau à distance pour vous connecter à tous les ordinateurs dans l'environnement et pour arrêter les services Windows suivants à l'aide de services.msc :

-   Le service de publication World Wide Web (sur tous les ordinateurs AOS)
-   Service de gestion des traitements par lots Microsoft Dynamics 365 for Operations (sur les ordinateurs AOS non privés uniquement)
-   Service de traitement Management Reporter 2012 (sur les ordinateurs BI uniquement)

Ces services maintiendront les connexions ouvertes dans la base de données Dynamics 365 for Operations.

## <a name="reset"></a>Rétablir
#### <a name="locate-the-latest-dataupgradezip-package"></a>Localiser le dernier module DataUpgrade.zip

Localisez le dernier module DataUpgrade.zip à l'aide des instructions disponibles dans [Télécharger le script DataUpgrade.zip](..\migration-upgrade\upgrade-data-to-latest-update.md). Les instructions expliquent comment trouver la version correcte du module de mise à niveau des données pour votre environnement.

#### <a name="execute-scripts-against-dynamics-365-for-operations-database"></a>Exécuter les scripts par rapport à la base de données Dynamics 365 for Operations

Exécuter les scripts suivants par rapport à la base de données Dynamics 365 for Operations (et non par rapport à la base de données d'états financiers).

-   DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Ces scripts garantissent que les utilisateurs, les rôles et les paramètres de suivi de modifications sont corrects.

#### <a name="execute-powershell-command-to-reset-database"></a>Exécuter la commande PowerShell pour réinitialiser la base de données

Exécutez la commande suivante, directement sur l'ordinateur AOS, pour réinitialiser l'intégration entre Dynamics 365 for Operations et les états financiers :

1.  Ouvrez Windows PowerShell en tant qu'administrateur.
2.  Exécutez : F:
3.  Exécutez : cd F:\\MRApplicationService\\MRInstallDirectory
4.  Exécutez : Import-Module .\\Server\\MRDeploy\\MRDeploy.psd1
5.  Exécutez : Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;my reason for resetting&gt;”
    -   Vous êtes invité à saisir « Y » pour confirmer.

Explication des paramètres :

-   Les valeurs valides pour - les motifs sont : SERVICING, BADDATA, OTHER.
-   Le paramètre ReasonDetail est texte libre.
-   Les paramètres reason et reasonDetail sont stockés dans le contrôle de télémétrie/d'environnement.

## <a name="start-services"></a>Démarrer les services
Utilisez services.msc pour redémarrer les services que vous avez arrêtés précédemment :

-   Le service de publication World Wide Web (sur tous les ordinateurs AOS)
-   Service de gestion des traitements par lots Microsoft Dynamics 365 for Operations (sur les ordinateurs AOS non privés uniquement)
-   Service de traitement Management Reporter 2012 (sur les ordinateurs BI uniquement)

## <a name="import-report-definitions"></a>Importer des définitions d'état
Importez vos créations de rapports dans le Concepteur de rapports, à l'aide du fichier créé lors de l'exportation :

1.  Dans le Concepteur de rapports, accédez à **Société** &gt; **Groupes de blocs élémentaires**.
2.  Sélectionnez le groupe de blocs élémentaires à exporter, puis cliquez sur **Exporter**. **Remarque :** Pour Dynamics 365 for Operations, un seul groupe de blocs élémentaires est pris en charge, **Valeur par défaut**.
3.  Sélectionnez le bloc élémentaire **Valeur par défaut**, puis cliquez sur **Importer**.
4.  Sélectionnez le fichier contenant les définitions de rapport exportées, puis cliquez sur **Ouvrir**.
5.  Dans la boîte de dialogue Importer, sélectionnez les définitions de rapport à importer :
    -   Pour importer toutes les définitions de rapport et les blocs élémentaires pris en charge, cliquez sur **Sélectionner tout**.
    -   Pour importer des rapports, lignes, colonnes, organigrammes ou ensembles de dimensions spécifiques, sélectionnez les rapports, lignes, colonnes, organigrammes ou ensembles de dimensions à importer.

6.  Cliquez sur **Importer**.



