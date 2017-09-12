---
title: "Réinitialiser le magasin de données d'états financiers après avoir restauré une base de données"
description: "Cette rubrique décrit la procédure de réinitialisation d'un magasin de données d'états financiers après avoir restauré une base de données Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 9953d2f29a67b35f4bb43f577df1c4d910e379a1
ms.openlocfilehash: 08a420a776f47119a5dc47f9119545aa448ffdbd
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a><span data-ttu-id="b2e1d-103">Réinitialiser le magasin de données d'états financiers après avoir restauré une base de données</span><span class="sxs-lookup"><span data-stu-id="b2e1d-103">Reset the financial reporting data mart after restoring a database</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b2e1d-104">Cette rubrique décrit la procédure de réinitialisation d'un magasin de données d'états financiers après avoir restauré une base de données Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-104">This topic describes how to reset the financial reporting data mart after restoring a Microsoft Dynamics 365 for Finance and Operations database.</span></span>

<span data-ttu-id="b2e1d-105">Si vous restaurez votre base de données Finance and Operations à partir d'une sauvegarde ou copiez la base de données à partir d'un autre environnement, vous devez suivre les étapes de cette rubrique pour vous assurer que le magasin de données d'états financiers utilise correctement la base de données Finance and Operations restaurée.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-105">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this topic to ensure that the financial reporting data mart is correctly using the restored Finance and Operations database.</span></span> 
<!--If you have questions about resetting the financial reporting data mart for a reason outside of restoring a Finance and Operations database, refer to the [Resetting the Management Reporter data mart](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) for more information. -->
> [!Note] 
> <span data-ttu-id="b2e1d-106">Les étapes de ce processus sont prises en charge pour la version de mai 2016 de Dynamics 365 for Operations (version app 7.0.1265.23014 et reporting financier version 7.0.10000.4) et versions plus récentes.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-106">The steps in this process are supported for Dynamics 365 for Operation May 2016 release (App build 7.0.1265.23014 and financial reporting build 7.0.10000.4) and newer releases.</span></span> <span data-ttu-id="b2e1d-107">Si vous avez une version antérieure de Finance and Operations, contactez notre équipe de support pour l'assistance.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-107">If you have an earlier release of Finance and Operations, contact our Support team for assistance.</span></span>

## <a name="export-report-definitions"></a><span data-ttu-id="b2e1d-108">Exporter des définitions d'état</span><span class="sxs-lookup"><span data-stu-id="b2e1d-108">Export report definitions</span></span>
<span data-ttu-id="b2e1d-109">Premièrement, exportez les créations de rapports situées dans le Concepteur de rapports, en utilisant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2e1d-109">First, export the report designs located in the Report Designer, using the following steps:</span></span>

1.  <span data-ttu-id="b2e1d-110">Dans le Concepteur de rapports, accédez à **Société** &gt; **Groupes de blocs élémentaires**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-110">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="b2e1d-111">Sélectionnez le groupe de blocs élémentaires à exporter, puis cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-111">Select the building block group to export, and click **Export**.</span></span> 
    > [!Note] 
    > <span data-ttu-id="b2e1d-112">Pour Finance and Operations, un seul groupe de blocs élémentaires est pris en charge, **Valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-112">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
3.  <span data-ttu-id="b2e1d-113">Sélectionnez des définitions de rapport à exporter :</span><span class="sxs-lookup"><span data-stu-id="b2e1d-113">Select the report definitions to export:</span></span>
    -   <span data-ttu-id="b2e1d-114">Pour exporter toutes vos définitions de rapport et les blocs élémentaires associés, cliquez sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-114">To export all your report definitions and the associated building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="b2e1d-115">Pour exporter des rapports, lignes, colonnes, organigrammes ou ensembles de dimensions spécifiques, cliquez sur l'onglet approprié et sélectionnez les éléments à exporter.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-115">To export specific reports, rows, columns, trees, or dimension sets, click the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="b2e1d-116">Maintenez la touche CTRL enfoncée pour sélectionner plusieurs éléments dans un onglet.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-116">Press and hold the Ctrl key to select multiple items in a tab.</span></span> <span data-ttu-id="b2e1d-117">Lorsque vous sélectionnez des rapports à exporter, les lignes, colonnes, organigrammes et ensembles de dimensions associés doivent être sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-117">When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4.  <span data-ttu-id="b2e1d-118">Cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-118">Click **Export**.</span></span>
5.  <span data-ttu-id="b2e1d-119">Entrez un nom et sélectionnez un emplacement sûr où vous souhaitez enregistrer les définitions de rapport exportées.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-119">Enter a file name and select a secure location where you want to save the exported report definitions.</span></span>
6.  <span data-ttu-id="b2e1d-120">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-120">Click **Save**.</span></span>

<span data-ttu-id="b2e1d-121">Le fichier peut être copié ou téléchargé à un emplacement sûr, lui permettant d'être importé dans un environnement différent à tout moment.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-121">The file can be copied or uploaded to a secure location, allowing it to be imported into a different environment at another time.</span></span> <span data-ttu-id="b2e1d-122">Les informations relatives à l'utilisation d'un compte de stockage Microsoft Azure se trouvent dans le champ [Transférer les données avec l'utilitaire de ligne de commande AzCopy](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="b2e1d-122">Information about using a Microsoft Azure storage account can be found in [Transfer data with the AzCopy Command-Line Utility](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy).</span></span> 
> [!NOTE]
> <span data-ttu-id="b2e1d-123">Microsoft ne fournit pas un compte de stockage dans le cadre de l'accord Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-123">Microsoft doesn’t provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="b2e1d-124">Vous devez acheter un compte de stockage ou utiliser le compte de stockage d'un abonnement Azure distinct.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-124">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span> 
> [!WARNING]
> <span data-ttu-id="b2e1d-125">Tenez compte du comportement du lecteur D sur les machines virtuelles Azure.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-125">Be aware of the behavior of the D drive on Azure Virtual Machines.</span></span> <span data-ttu-id="b2e1d-126">N'utilisez pas les groupes de blocs élémentaires exportés ici définitivement.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-126">Do not keep your exported building block groups here permanently.</span></span> <span data-ttu-id="b2e1d-127">Pour plus d'informations sur les lecteurs temporaires, voir [Comprendre le lecteur temporaire sur les machines virtuelles Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="b2e1d-127">For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

## <a name="stop-services"></a><span data-ttu-id="b2e1d-128">Arrêter les services</span><span class="sxs-lookup"><span data-stu-id="b2e1d-128">Stop services</span></span>
<span data-ttu-id="b2e1d-129">Utilisez l'ordinateur Bureau à distance pour vous connecter à tous les ordinateurs dans l'environnement et pour arrêter les services Windows suivants à l'aide de services.msc :</span><span class="sxs-lookup"><span data-stu-id="b2e1d-129">Use Remote Desktop to connect to all the computers in the environment and stop the following Windows services by using services.msc:</span></span>

-   <span data-ttu-id="b2e1d-130">Le service de publication World Wide Web (sur tous les ordinateurs AOS)</span><span class="sxs-lookup"><span data-stu-id="b2e1d-130">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="b2e1d-131">Service de gestion des traitements par lots Microsoft Dynamics 365 for Finance and Operations (sur les ordinateurs AOS non privés uniquement)</span><span class="sxs-lookup"><span data-stu-id="b2e1d-131">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="b2e1d-132">Service de traitement Management Reporter 2012 (sur les ordinateurs BI uniquement)</span><span class="sxs-lookup"><span data-stu-id="b2e1d-132">Management Reporter 2012 Process Service (on BI computers only)</span></span>

<span data-ttu-id="b2e1d-133">Ces services maintiendront les connexions ouvertes dans la base de données Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-133">These services will have open connections to the Finance and Operations database.</span></span>

## <a name="reset"></a><span data-ttu-id="b2e1d-134">Rétablir</span><span class="sxs-lookup"><span data-stu-id="b2e1d-134">Reset</span></span>
#### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="b2e1d-135">Rechercher et télécharger le package MinorVersionDataUpgrade.zip le plus récent</span><span class="sxs-lookup"><span data-stu-id="b2e1d-135">Locate and download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="b2e1d-136">Localisez le package MinorVersionDataUpgrade.zip le plus récent à l'aide des instructions disponibles dans [Télécharger le dernier package déployable de mise à niveau des données](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-package).</span><span class="sxs-lookup"><span data-stu-id="b2e1d-136">Locate the latest MinorVersionDataUpgrade.zip package using the directions found in [Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-package).</span></span> <span data-ttu-id="b2e1d-137">Les instructions expliquent comment trouver et télécharger la version correcte du package de mise à niveau des données.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-137">The directions explain how to locate and download the correct version of the data upgrade package.</span></span> <span data-ttu-id="b2e1d-138">Une mise à niveau n'est pas nécessaire pour télécharger le package MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-138">An upgrade is not required to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="b2e1d-139">Vous devez uniquement effectuer les étapes de la section « Télécharger le dernier package déployable de mise à niveau des données » sans effectuer les autres étapes de l'article pour récupérer une copie du package MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-139">You only need to complete the steps in the “Download the latest data upgrade deployable package” section without performing any of the other steps in the article to retrieve a copy of the MinorVersionDataUpgrade.zip package.</span></span>

#### <a name="execute-scripts-against-finance-and-operations-database"></a><span data-ttu-id="b2e1d-140">Exécuter les scripts par rapport à la base de données Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b2e1d-140">Execute scripts against Finance and Operations database</span></span>

<span data-ttu-id="b2e1d-141">Exécuter les scripts suivants par rapport à la base de données Finance and Operations (et non par rapport à la base de données d'états financiers).</span><span class="sxs-lookup"><span data-stu-id="b2e1d-141">Run the following scripts against the Finance and Operations database (not against the financial reporting database).</span></span>

-   <span data-ttu-id="b2e1d-142">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="b2e1d-142">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
-   <span data-ttu-id="b2e1d-143">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="b2e1d-143">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="b2e1d-144">Ces scripts garantissent que les utilisateurs, les rôles et les paramètres de suivi de modifications sont corrects.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-144">These scripts ensure that the users, roles, and change tracking settings are correct.</span></span>

#### <a name="execute-powershell-command-to-reset-database"></a><span data-ttu-id="b2e1d-145">Exécuter la commande PowerShell pour réinitialiser la base de données</span><span class="sxs-lookup"><span data-stu-id="b2e1d-145">Execute PowerShell command to reset database</span></span>

<span data-ttu-id="b2e1d-146">Exécutez la commande suivante, directement sur l'ordinateur AOS, pour réinitialiser l'intégration entre Finance and Operations et les états financiers :</span><span class="sxs-lookup"><span data-stu-id="b2e1d-146">Execute the following command, directly on the AOS computer, to reset the integration between Finance and Operations and financial reporting:</span></span>

1.  <span data-ttu-id="b2e1d-147">Ouvrez Windows PowerShell en tant qu'administrateur.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-147">Open Windows PowerShell as Administrator.</span></span>
2.  <span data-ttu-id="b2e1d-148">Exécutez : F:</span><span class="sxs-lookup"><span data-stu-id="b2e1d-148">Execute: F:</span></span>
3.  <span data-ttu-id="b2e1d-149">Exécutez : cd F:\\MRApplicationService\\MRInstallDirectory</span><span class="sxs-lookup"><span data-stu-id="b2e1d-149">Execute: cd F:\\MRApplicationService\\MRInstallDirectory</span></span>
4.  <span data-ttu-id="b2e1d-150">Exécutez : Import-Module .\\Server\\MRDeploy\\MRDeploy.psd1</span><span class="sxs-lookup"><span data-stu-id="b2e1d-150">Execute: Import-Module .\\Server\\MRDeploy\\MRDeploy.psd1</span></span>
5.  <span data-ttu-id="b2e1d-151">Exécutez : Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;my reason for resetting&gt;”</span><span class="sxs-lookup"><span data-stu-id="b2e1d-151">Execute: Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;my reason for resetting&gt;”</span></span>
    -   <span data-ttu-id="b2e1d-152">Vous êtes invité à saisir « Y » pour confirmer.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-152">You will be asked to enter “Y” to confirm.</span></span>

<span data-ttu-id="b2e1d-153">Explication des paramètres :</span><span class="sxs-lookup"><span data-stu-id="b2e1d-153">Explanation of parameters:</span></span>

-   <span data-ttu-id="b2e1d-154">Les valeurs valides pour - les motifs sont : SERVICING, BADDATA, OTHER.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-154">The valid values for -Reason are: SERVICING, BADDATA, OTHER.</span></span>
-   <span data-ttu-id="b2e1d-155">Le paramètre ReasonDetail est texte libre.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-155">The -ReasonDetail parameter is free text.</span></span>
-   <span data-ttu-id="b2e1d-156">Les paramètres reason et reasonDetail sont stockés dans le contrôle de télémétrie/d'environnement.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-156">The reason and reasonDetail will be recorded in telemetry/environment monitoring.</span></span>

## <a name="start-services"></a><span data-ttu-id="b2e1d-157">Démarrer les services</span><span class="sxs-lookup"><span data-stu-id="b2e1d-157">Start services</span></span>
<span data-ttu-id="b2e1d-158">Utilisez services.msc pour redémarrer les services que vous avez arrêtés précédemment :</span><span class="sxs-lookup"><span data-stu-id="b2e1d-158">Use services.msc to restart the services that you stopped earlier:</span></span>

-   <span data-ttu-id="b2e1d-159">Le service de publication World Wide Web (sur tous les ordinateurs AOS)</span><span class="sxs-lookup"><span data-stu-id="b2e1d-159">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="b2e1d-160">Service de gestion des traitements par lots Microsoft Dynamics 365 for Finance and Operations (sur les ordinateurs AOS non privés uniquement)</span><span class="sxs-lookup"><span data-stu-id="b2e1d-160">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="b2e1d-161">Service de traitement Management Reporter 2012 (sur les ordinateurs BI uniquement)</span><span class="sxs-lookup"><span data-stu-id="b2e1d-161">Management Reporter 2012 Process Service (on BI computers only)</span></span>

## <a name="import-report-definitions"></a><span data-ttu-id="b2e1d-162">Importer des définitions d'état</span><span class="sxs-lookup"><span data-stu-id="b2e1d-162">Import report definitions</span></span>
<span data-ttu-id="b2e1d-163">Importez vos créations de rapports dans le Concepteur de rapports, à l'aide du fichier créé lors de l'exportation :</span><span class="sxs-lookup"><span data-stu-id="b2e1d-163">Import your report designs from the Report Designer, using the file created during the export:</span></span>

1.  <span data-ttu-id="b2e1d-164">Dans le Concepteur de rapports, accédez à **Société** &gt; **Groupes de blocs élémentaires**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-164">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="b2e1d-165">Sélectionnez le groupe de blocs élémentaires à exporter, puis cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-165">Select the building block group to export, and click **Export**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="b2e1d-166">Pour Finance and Operations, un seul groupe de blocs élémentaires est pris en charge, **Valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-166">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="b2e1d-167">Sélectionnez le bloc élémentaire **Valeur par défaut**, puis cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-167">Select the **Default** building block and click **Import**.</span></span>
4.  <span data-ttu-id="b2e1d-168">Sélectionnez le fichier contenant les définitions de rapport exportées, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-168">Select the file containing the exported report definitions and click **Open**.</span></span>
5.  <span data-ttu-id="b2e1d-169">Dans la boîte de dialogue Importer, sélectionnez les définitions de rapport à importer :</span><span class="sxs-lookup"><span data-stu-id="b2e1d-169">In the Import dialog box, select the report definitions to import:</span></span>
    -   <span data-ttu-id="b2e1d-170">Pour importer toutes les définitions de rapport et les blocs élémentaires pris en charge, cliquez sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-170">To import all the report definitions and the supporting building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="b2e1d-171">Pour importer des rapports, lignes, colonnes, organigrammes ou ensembles de dimensions spécifiques, sélectionnez les rapports, lignes, colonnes, organigrammes ou ensembles de dimensions à importer.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-171">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6.  <span data-ttu-id="b2e1d-172">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="b2e1d-172">Click **Import**.</span></span>





