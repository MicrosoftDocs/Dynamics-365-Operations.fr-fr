---
title: ER Charger une configuration dans Lifecycle Services
description: Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut créer une configuration pour la génération d'états électronique (ER) et la charger dans Microsoft Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5def757de8fb9d347f5fd0f828039dad5c989c19
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143282"
---
# <a name="er-upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="51a99-103">ER Charger une configuration dans Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="51a99-103">ER Upload a configuration into Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="51a99-104">Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut créer une configuration pour la génération d'états électronique (ER) et la charger dans Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="51a99-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration and upload it into Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="51a99-105">Dans cet exemple, vous allez créer une configuration et la télécharger dans LCS pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les configurations ER sont partagées entre les sociétés.</span><span class="sxs-lookup"><span data-stu-id="51a99-105">In this example, you will create a configuration and upload it to LCS for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="51a99-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="51a99-106">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span> <span data-ttu-id="51a99-107">L'accès à LCS est également requis pour réaliser ces étapes.</span><span class="sxs-lookup"><span data-stu-id="51a99-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="51a99-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="51a99-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="51a99-109">Sélectionnez « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="51a99-109">Select 'Litware, Inc.'</span></span> <span data-ttu-id="51a99-110">et définissez-le comme actif.</span><span class="sxs-lookup"><span data-stu-id="51a99-110">and set it as active.</span></span>
3. <span data-ttu-id="51a99-111">Cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="51a99-111">Click Configurations.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="51a99-112">Créer une configuration de modèle de données</span><span class="sxs-lookup"><span data-stu-id="51a99-112">Create a new data model configuration</span></span>
1. <span data-ttu-id="51a99-113">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="51a99-113">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="51a99-114">Vous allez créer une configuration qui contient un modèle de données pour les paiements électroniques.</span><span class="sxs-lookup"><span data-stu-id="51a99-114">You will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="51a99-115">Cette configuration de modèle de données sera téléchargée dans LCS ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="51a99-115">This data model configuration will be uploaded into LCS later.</span></span>  
2. <span data-ttu-id="51a99-116">Tapez « Exemple de configuration de modèle » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="51a99-116">In the Name field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="51a99-117">Exemple de configuration de modèle</span><span class="sxs-lookup"><span data-stu-id="51a99-117">Sample model configuration</span></span>  
3. <span data-ttu-id="51a99-118">Tapez « Exemple de configuration de modèle » dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="51a99-118">In the Description field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="51a99-119">Exemple de configuration de modèle</span><span class="sxs-lookup"><span data-stu-id="51a99-119">Sample model configuration</span></span>  
4. <span data-ttu-id="51a99-120">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="51a99-120">Click Create configuration.</span></span>
5. <span data-ttu-id="51a99-121">Cliquez sur Concepteur de modèles.</span><span class="sxs-lookup"><span data-stu-id="51a99-121">Click Model designer.</span></span>
6. <span data-ttu-id="51a99-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="51a99-122">Click New.</span></span>
7. <span data-ttu-id="51a99-123">Tapez « Point d'entrée » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="51a99-123">In the Name field, type 'Entry point'.</span></span>
    * <span data-ttu-id="51a99-124">Point d'entrée</span><span class="sxs-lookup"><span data-stu-id="51a99-124">Entry point</span></span>  
8. <span data-ttu-id="51a99-125">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="51a99-125">Click Add.</span></span>
9. <span data-ttu-id="51a99-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="51a99-126">Click Save.</span></span>
10. <span data-ttu-id="51a99-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51a99-127">Close the page.</span></span>
11. <span data-ttu-id="51a99-128">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="51a99-128">Click Change status.</span></span>
12. <span data-ttu-id="51a99-129">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="51a99-129">Click Complete.</span></span>
13. <span data-ttu-id="51a99-130">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="51a99-130">Click OK.</span></span>

## <a name="register-a-new--repository"></a><span data-ttu-id="51a99-131">Enregistrez un nouveau référentiel.</span><span class="sxs-lookup"><span data-stu-id="51a99-131">Register a new  repository</span></span>
1. <span data-ttu-id="51a99-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51a99-132">Close the page.</span></span>
2. <span data-ttu-id="51a99-133">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="51a99-133">Click Repositories.</span></span>
    * <span data-ttu-id="51a99-134">Cela vous permet d'ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="51a99-134">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
3. <span data-ttu-id="51a99-135">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="51a99-135">Click Add to open the drop dialog.</span></span>
    * <span data-ttu-id="51a99-136">Cela vous permet d'ajouter un référentiel.</span><span class="sxs-lookup"><span data-stu-id="51a99-136">This allows you to add a new repository.</span></span>  
4. <span data-ttu-id="51a99-137">Sélectionnez LCS dans le champ Type du référentiel de configuration.</span><span class="sxs-lookup"><span data-stu-id="51a99-137">In the Configuration repository type field, select LCS.</span></span>
5. <span data-ttu-id="51a99-138">Cliquez sur Créer un référentiel.</span><span class="sxs-lookup"><span data-stu-id="51a99-138">Click Create repository.</span></span>
6. <span data-ttu-id="51a99-139">Dans le champ Projet, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="51a99-139">In the Project field, enter or select a value.</span></span>
    * <span data-ttu-id="51a99-140">Sélectionnez le projet LCS souhaité.</span><span class="sxs-lookup"><span data-stu-id="51a99-140">Select the desired LCS project.</span></span> <span data-ttu-id="51a99-141">Vous devez avoir accès au projet.</span><span class="sxs-lookup"><span data-stu-id="51a99-141">You must have access to the project.</span></span>  
7. <span data-ttu-id="51a99-142">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="51a99-142">Click OK.</span></span>
    * <span data-ttu-id="51a99-143">Effectuez une nouvelle entrée de référentiel.</span><span class="sxs-lookup"><span data-stu-id="51a99-143">Complete a new repository entry.</span></span>  
8. <span data-ttu-id="51a99-144">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="51a99-144">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="51a99-145">Sélectionnez l'enregistrement Référentiel LCS.</span><span class="sxs-lookup"><span data-stu-id="51a99-145">Select the LCS repository record.</span></span>  
    * <span data-ttu-id="51a99-146">Notez qu'un référentiel enregistré est marqué par le fournisseur actuel, ce qui signifie que seules les configurations détenues par ce fournisseur peuvent être placées dans ce référentiel et donc être chargées dans le projet LCS sélectionné.</span><span class="sxs-lookup"><span data-stu-id="51a99-146">Note that a registered repository is marked by the current provider meaning that the only configurations owned by that provider can be placed to this repository and, consequently, uploaded into the selected LCS project.</span></span>  
9. <span data-ttu-id="51a99-147">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="51a99-147">Click Open.</span></span>
    * <span data-ttu-id="51a99-148">Ouvrez le référentiel pour afficher la liste des configurations d'ER.</span><span class="sxs-lookup"><span data-stu-id="51a99-148">Open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="51a99-149">Elle est vide si ce projet n'a pas encore été utilisé pour le partage de configurations d'ER.</span><span class="sxs-lookup"><span data-stu-id="51a99-149">It will be empty if this project has not yet been used for ER configurations sharing.</span></span>  
10. <span data-ttu-id="51a99-150">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51a99-150">Close the page.</span></span>
11. <span data-ttu-id="51a99-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51a99-151">Close the page.</span></span>

## <a name="upload-configuration-into-lcs"></a><span data-ttu-id="51a99-152">Téléchargez la configuration dans LCS.</span><span class="sxs-lookup"><span data-stu-id="51a99-152">Upload configuration into LCS</span></span>
1. <span data-ttu-id="51a99-153">Cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="51a99-153">Click Configurations.</span></span>
2. <span data-ttu-id="51a99-154">Dans l'arborescence, sélectionnez « Exemple de configuration de modèle ».</span><span class="sxs-lookup"><span data-stu-id="51a99-154">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="51a99-155">Sélectionnez une configuration qui est déjà terminée.</span><span class="sxs-lookup"><span data-stu-id="51a99-155">Select a created configuration that has been already completed.</span></span>  
3. <span data-ttu-id="51a99-156">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="51a99-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="51a99-157">Sélectionnez la version de la configuration sélectionnée ayant le statut « Terminé ».</span><span class="sxs-lookup"><span data-stu-id="51a99-157">Select the version of the selected configuration with the status of 'Completed'.</span></span>  
4. <span data-ttu-id="51a99-158">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="51a99-158">Click Change status.</span></span>
5. <span data-ttu-id="51a99-159">Cliquez sur Partager.</span><span class="sxs-lookup"><span data-stu-id="51a99-159">Click Share.</span></span>
    * <span data-ttu-id="51a99-160">Le statut de configuration passe de « Terminé » à « Partagé » lorsqu'il est attribué dans LCS.</span><span class="sxs-lookup"><span data-stu-id="51a99-160">The configuration status will change from 'Completed' to 'Shared' when it is published in LCS.</span></span>  
6. <span data-ttu-id="51a99-161">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="51a99-161">Click OK.</span></span>
7. <span data-ttu-id="51a99-162">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="51a99-162">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="51a99-163">Sélectionnez la version de configuration dont le statut est « Partagé ».</span><span class="sxs-lookup"><span data-stu-id="51a99-163">Select the configuration version with the status of 'Shared'.</span></span>  
    * <span data-ttu-id="51a99-164">Notez que le statut de la version sélectionnée est passé de « Terminé » à « Partagé ».</span><span class="sxs-lookup"><span data-stu-id="51a99-164">Note that the status of the selected version has changed from 'Completed' to 'Shared'.</span></span>  
8. <span data-ttu-id="51a99-165">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51a99-165">Close the page.</span></span>
9. <span data-ttu-id="51a99-166">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="51a99-166">Click Repositories.</span></span>
    * <span data-ttu-id="51a99-167">Cela vous permet d'ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="51a99-167">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
10. <span data-ttu-id="51a99-168">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="51a99-168">Click Open.</span></span>
    * <span data-ttu-id="51a99-169">Sélectionnez le référentiel LCS et ouvrez- le.</span><span class="sxs-lookup"><span data-stu-id="51a99-169">Select the LCS repository and open it.</span></span>  
    * <span data-ttu-id="51a99-170">Notez que la configuration sélectionnée est indiquée comme un actif du projet LCS sélectionné.</span><span class="sxs-lookup"><span data-stu-id="51a99-170">Note that the selected configuration is shown as an asset of the selected LCS project.</span></span>  
    * <span data-ttu-id="51a99-171">Ouvrez LCS à l'aide de https://lcs.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="51a99-171">Open LCS using https://lcs.dynamics.com.</span></span> <span data-ttu-id="51a99-172">Ouvrez un projet utilisé précédemment pour l'enregistrement du référentiel, ouvrez la bibliothèque d'actifs de ce projet, et développez le contenu du type d'actif Configuration GER, la configuration ER téléchargée est disponible.</span><span class="sxs-lookup"><span data-stu-id="51a99-172">Open a project that was used earlier for repository registration, open the 'Asset library' of this project, and expand the content of the 'GER configuration' asset type – the uploaded ER configuration will be available.</span></span> <span data-ttu-id="51a99-173">Notez que la configuration LCS téléchargée peut être importée dans une autre instance si les fournisseurs ont accès à ce projet LCS.</span><span class="sxs-lookup"><span data-stu-id="51a99-173">Note that the uploaded LCS configuration can be imported to another instance if providers have access to this LCS project.</span></span>  

