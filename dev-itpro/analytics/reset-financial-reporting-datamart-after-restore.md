---
title: "Permet de réinitialiser le mini-data warehouse d&quot;états financiers après avoir restauré une base de données"
description: "Cette rubrique décrit la procédure de réinitialiser le mini-data warehouse d&quot;états financiers après avoir restauré Microsoft Dynamics 365 pour la base de données d&quot;opérations."
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

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Permet de réinitialiser le mini-data warehouse d'états financiers après avoir restauré une base de données

Cette rubrique décrit la procédure de réinitialiser le mini-data warehouse d'états financiers après avoir restauré Microsoft Dynamics 365 pour la base de données d'opérations. 

Il existe plusieurs cas où vous deviez restaurer votre Dynamics 365 pour la base de données d'opérations d'une sauvegarde ou copier la base de données d'un autre environnement. Dans ce cas, vous devez également suivre les étapes appropriées pour garantir que le mini-data warehouse d'états financiers utilise correctement Dynamics restauré 365 pour la base de données d'opérations. Si vous avez des questions sur réinitialiser le mini-data warehouse d'états financiers pour un motif en dehors de restaurer Dynamics 365 pour la base de données d'opérations, reportez-vous à [redéfinissant la le mini-data warehouse de Management Reporter] (https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) pour plus d'informations. Notez que les étapes de ce processus sont prises en charge pour Dynamics 365 pour opération le lancement en mai 2016 (version 7.0.1265.23014 d'application et la version 7.0.10000.4 d'états financiers) et les nouveaux versions. Si vous avez une version antérieure de Dynamics 365 pour les opérations, contactez-vous notre équipe de supports pour le pointage.

## <a name="export-report-definitions"></a>Exportez les définitions de rapport
Premièrement, exportez les créations de rapports situées dans le Concepteur de rapports, en utilisant les étapes suivantes :

1.  Dans le Concepteur de rapports, passez ** société ** &gt; ** aux groupes de blocs élémentaires **.
2.  Permet de sélectionner le groupe à exporter, puis cliquez sur ** exportation **. ** Remarque : ** Pour Dynamics 365 pour les opérations, seul un groupe de blocs élémentaires est pris en charge, ** valeur par défaut **.
3.  Permet de sélectionner des définitions de rapport pour exporter :
    -   Pour exporter toutes vos définitions de rapport et les blocs élémentaires associés, cliquez sur **Sélectionner tout**.
    -   Pour exporter des rapports, lignes, colonnes, organigrammes ou ensembles de dimensions spécifiques, cliquez sur l'onglet approprié et sélectionnez les éléments à exporter. Maintenez la touche CTRL enfoncée pour sélectionner plusieurs éléments dans un onglet. Lorsque vous sélectionnez des rapports à exporter, les lignes, les colonnes, les arborescences, et les ensembles de dimensions associés sont sélectionnés.

4.  Cliquez sur ** exportation **.
5.  Entrez un nom et sélectionnez un emplacement sûr où vous souhaitez enregistrer les définitions de rapport exportées.
6.  Click **Save**.

Le fichier peut être copiés ou téléchargé dans un emplacement sûr, le permettant à importer dans un environnement différent à une autre heure. Les informations relatives utiliser un compte azuré de stockage Microsoft se trouvent dans le champ [des données de transfert avec l'utilitaire de Commande- requise d'AzCopy] (https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy). ** Remarque : ** Microsoft ne fournit pas un compte de stockage dans le cadre de votre Dynamics 365 pour l'accord d'opérations. Vous devez acheter un compte de stockage ou utiliser un compte de stockage d'un abonnement azuré distinct. ** Important : ** Tenez compte du comportement du lecteur de D sur les ordinateurs virtuels azurés. N'utilisez pas les groupes de blocs élémentaires exportés ici définitivement. Pour plus d'informations sur les lecteurs temporaires, voir [comprenant le lecteur temporaire sur ordinateurs virtuels azurés Windows] (https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Permet d'arrêter les services
L'ordinateur Bureau à distance pour se connecter à tous les ordinateurs dans l'environnement et pour arrêter les services suivants de Windows à l'aide de services.msc :

-   World Wide Web qui émet le service (sur tous les ordinateurs AOS)
-   Microsoft Dynamics 365 pour le service de gestion de lot Opérations (sur des ordinateurs non privés d'AOS uniquement)
-   Service traitement Management Reporter 2012 (sur les ordinateurs BI uniquement)

Ces services entretiendront les relations en cours à Dynamics 365 pour la base de données d'opérations.

## <a name="reset"></a>Rétablir
#### <a name="locate-the-latest-dataupgradezip-package"></a>Localisez le dernier module de DataUpgrade.zip

Localisez le dernier module de DataUpgrade.zip à l'aide de les directions disponibles dans le champ [chargez le script de DataUpgrade.zip (].\migration-mise à niveau\upgrade-data-to-latest-update.md). Les directions expliquent comment trouver la version correcte du module de mise à niveau des données pour votre environnement.

#### <a name="execute-scripts-against-dynamics-365-for-operations-database"></a>Exécution des scripts avec Dynamics 365 pour la base de données d'opérations

Exécution des scripts suivants pour Dynamics 365 pour la base de données d'opérations (et non par rapport à la base de données d'états financiers).

-   Scripts\\ConfigureAxReportingIntegration.sql de DataUpgrade.zip\\AosService\\
-   Scripts\\GrantAzViewChangeTracking.sql de DataUpgrade.zip\\AosService\\

Ces scripts garantissent que les utilisateurs, les rôles, et la modification des paramètres de suivi sont corrects.

#### <a name="execute-powershell-command-to-reset-database"></a>Exécutez la commande PowerShell de réinitialiser la base de données

Exécutez la commande suivante, directement sous l'ordinateur de l'AOS, de réinitialiser l'intégration entre Dynamics 365 pour les opérations et des états financiers :

1.  Fenêtres ouvertes PowerShell tant qu'administrateur.
2.  Exécutez : F :
3.  Exécutez : f cd :\\MRApplicationService\\MRInstallDirectory
4.  Exécutez : Importation-module. serveur\\MRDeploy\\MRDeploy.psd1 d'\\
5.  Exécutez : Remise - DatamartIntegration - Motif ELSE - ReasonDetail « &lt;mon motif pour réinitialiser&gt; »
    -   Vous êtes invité à entrer « Y » pour confirmer.

Explication des paramètres :

-   Les valeurs valides pour - Le motif sont : ENTRETIEN, BADDATA, ELSE.
-   - Le paramètre de ReasonDetail est texte libre.
-   Le motif et le reasonDetail sont stockés dans le contrôle de télémétrie/environnement.

## <a name="start-services"></a>Services de début
Utilisez services.msc pour redémarrer services que vous avez arrêtés précédente :

-   World Wide Web qui émet le service (sur tous les ordinateurs AOS)
-   Microsoft Dynamics 365 pour le service de gestion de lot Opérations (sur des ordinateurs non privés d'AOS uniquement)
-   Service traitement Management Reporter 2012 (sur les ordinateurs BI uniquement)

## <a name="import-report-definitions"></a>Importez les définitions de rapport
Importez les créations de rapports dans le Concepteur de rapports, à l'aide de le fichier créé lors de l'exportation :

1.  Dans le Concepteur de rapports, passez ** société ** &gt; ** aux groupes de blocs élémentaires **.
2.  Permet de sélectionner le groupe à exporter, puis cliquez sur ** exportation **. ** Remarque : ** Pour Dynamics 365 pour les opérations, seul un groupe de blocs élémentaires est pris en charge, ** valeur par défaut **.
3.  Sélectionnez ** valeur par défaut ** le bloc élémentaire et cliquez sur ** importation **.
4.  Permet de sélectionner le fichier contenant les définitions de rapport exportées et cliquez sur ** ouvert **.
5.  Dans la boîte de dialogue Importer, sélectionnez les définitions de rapport à importer :
    -   Pour importer toutes les définitions de rapport et les blocs élémentaires pris en charge, cliquez sur **Sélectionner tout**.
    -   Pour importer des rapports, lignes, colonnes, organigrammes ou ensembles de dimensions spécifiques, sélectionnez les rapports, lignes, colonnes, organigrammes ou ensembles de dimensions à importer.

6.  Click **Import**.



