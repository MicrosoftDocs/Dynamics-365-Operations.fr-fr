---
title: "Réinitialiser le magasin de données d'états financiers après avoir restauré une base de données"
description: "Cette rubrique décrit la procédure de réinitialisation d'un magasin de données d'états financiers après avoir restauré une base de données Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261824
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 200b1a03a0ea95ec2d75850f9a8aebda966e38d6
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a><span data-ttu-id="5d72f-103">Réinitialiser le magasin de données d'états financiers après avoir restauré une base de données</span><span class="sxs-lookup"><span data-stu-id="5d72f-103">Reset the financial reporting data mart after restoring a database</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5d72f-104">Cette rubrique décrit la procédure de réinitialisation d'un magasin de données d'états financiers après avoir restauré une base de données Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5d72f-104">This topic describes how to reset the financial reporting data mart after restoring a Microsoft Dynamics 365 for Finance and Operations database.</span></span>

<span data-ttu-id="5d72f-105">Si vous restaurez votre base de données Finance and Operations à partir d'une sauvegarde ou copiez la base de données à partir d'un autre environnement, vous devez suivre les étapes de cette rubrique pour vous assurer que le magasin de données d'états financiers utilise correctement la base de données Finance and Operations restaurée.</span><span class="sxs-lookup"><span data-stu-id="5d72f-105">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this topic to ensure that the financial reporting data mart is correctly using the restored Finance and Operations database.</span></span> 
> [!Note] 
> <span data-ttu-id="5d72f-106">Les étapes de ce processus sont prises en charge pour la version de mai 2016 de Dynamics 365 for Operations (version app 7.0.1265.23014 et reporting financier version 7.0.10000.4) et versions plus récentes.</span><span class="sxs-lookup"><span data-stu-id="5d72f-106">The steps in this process are supported for Dynamics 365 for Operation May 2016 release (App build 7.0.1265.23014 and financial reporting build 7.0.10000.4) and newer releases.</span></span> <span data-ttu-id="5d72f-107">Si vous avez une version antérieure de Finance and Operations, contactez notre équipe de support pour l'assistance.</span><span class="sxs-lookup"><span data-stu-id="5d72f-107">If you have an earlier release of Finance and Operations, contact our Support team for assistance.</span></span>

## <a name="export-report-definitions"></a><span data-ttu-id="5d72f-108">Exporter des définitions d'état</span><span class="sxs-lookup"><span data-stu-id="5d72f-108">Export report definitions</span></span>
<span data-ttu-id="5d72f-109">Premièrement, exportez les créations de rapports situées dans le Concepteur de rapports, en utilisant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="5d72f-109">First, export the report designs located in the Report Designer, using the following steps:</span></span>

1.  <span data-ttu-id="5d72f-110">Dans le Concepteur de rapports, accédez à **Société** &gt; **Groupes de blocs élémentaires**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-110">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="5d72f-111">Sélectionnez le groupe de blocs élémentaires à exporter, puis cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-111">Select the building block group to export, and click **Export**.</span></span> 

    > [!Note] 
    > <span data-ttu-id="5d72f-112">Pour Finance and Operations, un seul groupe de blocs élémentaires est pris en charge, **Valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-112">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="5d72f-113">Sélectionnez des définitions de rapport à exporter :</span><span class="sxs-lookup"><span data-stu-id="5d72f-113">Select the report definitions to export:</span></span>
    -   <span data-ttu-id="5d72f-114">Pour exporter toutes vos définitions de rapport et les blocs élémentaires associés, cliquez sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-114">To export all your report definitions and the associated building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="5d72f-115">Pour exporter des rapports, lignes, colonnes, organigrammes ou ensembles de dimensions spécifiques, cliquez sur l'onglet approprié et sélectionnez les éléments à exporter.</span><span class="sxs-lookup"><span data-stu-id="5d72f-115">To export specific reports, rows, columns, trees, or dimension sets, click the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="5d72f-116">Maintenez la touche Ctrl enfoncée pour sélectionner plusieurs articles dans un onglet. Lorsque vous sélectionnez des rapports à exporter, les lignes, colonnes, arborescences et ensembles de dimensions associés sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="5d72f-116">Press and hold the Ctrl key to select multiple items in a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4.  <span data-ttu-id="5d72f-117">Cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-117">Click **Export**.</span></span>
5.  <span data-ttu-id="5d72f-118">Entrez un nom et sélectionnez un emplacement sûr où vous souhaitez enregistrer les définitions de rapport exportées.</span><span class="sxs-lookup"><span data-stu-id="5d72f-118">Enter a file name and select a secure location where you want to save the exported report definitions.</span></span>
6.  <span data-ttu-id="5d72f-119">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-119">Click **Save**.</span></span>

<span data-ttu-id="5d72f-120">Le fichier peut être copié ou téléchargé à un emplacement sûr, lui permettant d'être importé dans un environnement différent à tout moment.</span><span class="sxs-lookup"><span data-stu-id="5d72f-120">The file can be copied or uploaded to a secure location, allowing it to be imported into a different environment at another time.</span></span> <span data-ttu-id="5d72f-121">Les informations relatives à l'utilisation d'un compte de stockage Microsoft Azure se trouvent dans le champ [Transférer les données avec l'utilitaire de ligne de commande AzCopy](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="5d72f-121">Information about using a Microsoft Azure storage account can be found in [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span> 
> [!NOTE]
> <span data-ttu-id="5d72f-122">Microsoft ne fournit pas un compte de stockage dans le cadre de l'accord Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5d72f-122">Microsoft doesn’t provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="5d72f-123">Vous devez acheter un compte de stockage ou utiliser le compte de stockage d'un abonnement Azure distinct.</span><span class="sxs-lookup"><span data-stu-id="5d72f-123">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span> 
> [!WARNING]
> <span data-ttu-id="5d72f-124">Tenez compte du comportement du lecteur D sur les machines virtuelles Azure.</span><span class="sxs-lookup"><span data-stu-id="5d72f-124">Be aware of the behavior of the D drive on Azure Virtual Machines.</span></span> <span data-ttu-id="5d72f-125">N'utilisez pas les groupes de blocs élémentaires exportés ici définitivement.</span><span class="sxs-lookup"><span data-stu-id="5d72f-125">Do not keep your exported building block groups here permanently.</span></span> <span data-ttu-id="5d72f-126">Pour plus d'informations sur les lecteurs temporaires, voir [Comprendre le lecteur temporaire sur les machines virtuelles Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="5d72f-126">For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

## <a name="stop-services"></a><span data-ttu-id="5d72f-127">Arrêter les services</span><span class="sxs-lookup"><span data-stu-id="5d72f-127">Stop services</span></span>
<span data-ttu-id="5d72f-128">Utilisez l'ordinateur Bureau à distance pour vous connecter à tous les ordinateurs dans l'environnement et pour arrêter les services Windows suivants à l'aide de services.msc :</span><span class="sxs-lookup"><span data-stu-id="5d72f-128">Use Remote Desktop to connect to all the computers in the environment and stop the following Windows services by using services.msc:</span></span>

-   <span data-ttu-id="5d72f-129">Le service de publication World Wide Web (sur tous les ordinateurs AOS)</span><span class="sxs-lookup"><span data-stu-id="5d72f-129">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="5d72f-130">Service de gestion des traitements par lots Microsoft Dynamics 365 for Finance and Operations (sur les ordinateurs AOS non privés uniquement)</span><span class="sxs-lookup"><span data-stu-id="5d72f-130">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="5d72f-131">Service de traitement Management Reporter 2012 (sur les ordinateurs BI uniquement)</span><span class="sxs-lookup"><span data-stu-id="5d72f-131">Management Reporter 2012 Process Service (on BI computers only)</span></span>

<span data-ttu-id="5d72f-132">Ces services maintiendront les connexions ouvertes dans la base de données Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5d72f-132">These services will have open connections to the Finance and Operations database.</span></span>

## <a name="reset"></a><span data-ttu-id="5d72f-133">Rétablir</span><span class="sxs-lookup"><span data-stu-id="5d72f-133">Reset</span></span>
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="5d72f-134">Rechercher et télécharger le package MinorVersionDataUpgrade.zip le plus récent</span><span class="sxs-lookup"><span data-stu-id="5d72f-134">Locate and download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="5d72f-135">Localisez le package MinorVersionDataUpgrade.zip le plus récent à l'aide des instructions disponibles dans [Télécharger le dernier package déployable de mise à niveau des données](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="5d72f-135">Locate the latest MinorVersionDataUpgrade.zip package using the directions found in [Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="5d72f-136">Les instructions expliquent comment trouver et télécharger la version correcte du package de mise à niveau des données.</span><span class="sxs-lookup"><span data-stu-id="5d72f-136">The directions explain how to locate and download the correct version of the data upgrade package.</span></span> <span data-ttu-id="5d72f-137">Une mise à niveau n'est pas nécessaire pour télécharger le package MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="5d72f-137">An upgrade is not required to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="5d72f-138">Vous devez uniquement effectuer les étapes de la section « Télécharger le dernier package déployable de mise à niveau des données » sans effectuer les autres étapes de l'article pour récupérer une copie du package MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="5d72f-138">You only need to complete the steps in the “Download the latest data upgrade deployable package” section without performing any of the other steps in the article to retrieve a copy of the MinorVersionDataUpgrade.zip package.</span></span>

### <a name="execute-scripts-against-finance-and-operations-database"></a><span data-ttu-id="5d72f-139">Exécuter les scripts par rapport à la base de données Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5d72f-139">Execute scripts against Finance and Operations database</span></span>

<span data-ttu-id="5d72f-140">Exécuter les scripts suivants par rapport à la base de données Finance and Operations (et non par rapport à la base de données d'états financiers).</span><span class="sxs-lookup"><span data-stu-id="5d72f-140">Run the following scripts against the Finance and Operations database (not against the financial reporting database).</span></span>

-   <span data-ttu-id="5d72f-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="5d72f-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
-   <span data-ttu-id="5d72f-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="5d72f-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="5d72f-143">Ces scripts garantissent que les utilisateurs, les rôles et les paramètres de suivi de modifications sont corrects.</span><span class="sxs-lookup"><span data-stu-id="5d72f-143">These scripts ensure that the users, roles, and change tracking settings are correct.</span></span>

### <a name="execute-powershell-command-to-reset-database"></a><span data-ttu-id="5d72f-144">Exécuter la commande PowerShell pour réinitialiser la base de données</span><span class="sxs-lookup"><span data-stu-id="5d72f-144">Execute PowerShell command to reset database</span></span>

<span data-ttu-id="5d72f-145">Sur l'ordinateur AOS, exécutez les commandes suivantes dans PowerShell en tant qu'administrateur pour réinitialiser l'intégration entre Finance and Operations et les états financiers :</span><span class="sxs-lookup"><span data-stu-id="5d72f-145">On the AOS computer, execute the following commands in PowerShell as an Administrator to reset the integration between Finance and Operations and financial reporting:</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> <span data-ttu-id="5d72f-146">Après avoir effectué les commandes, vous devrez entrer « Y » pour confirmer.</span><span class="sxs-lookup"><span data-stu-id="5d72f-146">After executing the commands, you will be asked to enter “Y” to confirm.</span></span>

<span data-ttu-id="5d72f-147">Explication des paramètres :</span><span class="sxs-lookup"><span data-stu-id="5d72f-147">Explanation of parameters:</span></span>

-   <span data-ttu-id="5d72f-148">Les valeurs valides pour - les motifs sont : SERVICING, BADDATA, OTHER.</span><span class="sxs-lookup"><span data-stu-id="5d72f-148">The valid values for -Reason are: SERVICING, BADDATA, OTHER.</span></span>
-   <span data-ttu-id="5d72f-149">Le paramètre ReasonDetail est texte libre.</span><span class="sxs-lookup"><span data-stu-id="5d72f-149">The -ReasonDetail parameter is free text.</span></span>
-   <span data-ttu-id="5d72f-150">Les paramètres reason et reasonDetail sont stockés dans le contrôle de télémétrie/d'environnement.</span><span class="sxs-lookup"><span data-stu-id="5d72f-150">The reason and reasonDetail will be recorded in telemetry/environment monitoring.</span></span>

## <a name="start-services"></a><span data-ttu-id="5d72f-151">Démarrer les services</span><span class="sxs-lookup"><span data-stu-id="5d72f-151">Start services</span></span>
<span data-ttu-id="5d72f-152">Utilisez services.msc pour redémarrer les services que vous avez arrêtés précédemment :</span><span class="sxs-lookup"><span data-stu-id="5d72f-152">Use services.msc to restart the services that you stopped earlier:</span></span>

-   <span data-ttu-id="5d72f-153">Le service de publication World Wide Web (sur tous les ordinateurs AOS)</span><span class="sxs-lookup"><span data-stu-id="5d72f-153">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="5d72f-154">Service de gestion des traitements par lots Microsoft Dynamics 365 for Finance and Operations (sur les ordinateurs AOS non privés uniquement)</span><span class="sxs-lookup"><span data-stu-id="5d72f-154">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="5d72f-155">Service de traitement Management Reporter 2012 (sur les ordinateurs BI uniquement)</span><span class="sxs-lookup"><span data-stu-id="5d72f-155">Management Reporter 2012 Process Service (on BI computers only)</span></span>

## <a name="import-report-definitions"></a><span data-ttu-id="5d72f-156">Importer des définitions d'état</span><span class="sxs-lookup"><span data-stu-id="5d72f-156">Import report definitions</span></span>
<span data-ttu-id="5d72f-157">Importez vos créations de rapports dans le Concepteur de rapports, à l'aide du fichier créé lors de l'exportation :</span><span class="sxs-lookup"><span data-stu-id="5d72f-157">Import your report designs from the Report Designer, using the file created during the export:</span></span>

1.  <span data-ttu-id="5d72f-158">Dans le Concepteur de rapports, accédez à **Société** &gt; **Groupes de blocs élémentaires**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-158">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="5d72f-159">Sélectionnez le groupe de blocs élémentaires à exporter, puis cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-159">Select the building block group to export, and click **Export**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="5d72f-160">Pour Finance and Operations, un seul groupe de blocs élémentaires est pris en charge, **Valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-160">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="5d72f-161">Sélectionnez le bloc élémentaire **Valeur par défaut**, puis cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-161">Select the **Default** building block and click **Import**.</span></span>
4.  <span data-ttu-id="5d72f-162">Sélectionnez le fichier contenant les définitions de rapport exportées, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-162">Select the file containing the exported report definitions and click **Open**.</span></span>
5.  <span data-ttu-id="5d72f-163">Dans la boîte de dialogue Importer, sélectionnez les définitions de rapport à importer :</span><span class="sxs-lookup"><span data-stu-id="5d72f-163">In the Import dialog box, select the report definitions to import:</span></span>
    -   <span data-ttu-id="5d72f-164">Pour importer toutes les définitions de rapport et les blocs élémentaires pris en charge, cliquez sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-164">To import all the report definitions and the supporting building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="5d72f-165">Pour importer des rapports, lignes, colonnes, organigrammes ou ensembles de dimensions spécifiques, sélectionnez les rapports, lignes, colonnes, organigrammes ou ensembles de dimensions à importer.</span><span class="sxs-lookup"><span data-stu-id="5d72f-165">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6.  <span data-ttu-id="5d72f-166">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="5d72f-166">Click **Import**.</span></span>





