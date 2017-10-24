--- 
title: "Importer une configuration dans Lifecycle Services pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut créer une configuration pour la génération d'états électronique (ER) et la charger dans Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: d24679a380ec824fe08c56aacb4bc348ff40440a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="upload-a-configuration-into-lifecycle-services-for-electronic-reporting-er"></a><span data-ttu-id="b138e-103">Importer une configuration dans Lifecycle Services pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="b138e-103">Upload a configuration into Lifecycle Services for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b138e-104">Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut créer une configuration pour la génération d'états électronique (ER) et la charger dans Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b138e-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration and upload it into Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="b138e-105">Dans cet exemple, vous allez créer une configuration et la télécharger dans LCS pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les configurations ER sont partagées entre les sociétés.</span><span class="sxs-lookup"><span data-stu-id="b138e-105">In this example, you will create a configuration and upload it to LCS for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="b138e-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="b138e-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="b138e-107">L'accès à LCS est également requis pour réaliser ces étapes.</span><span class="sxs-lookup"><span data-stu-id="b138e-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="b138e-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="b138e-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="b138e-109">Sélectionnez « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="b138e-109">Select ‘Litware, Inc.’</span></span> <span data-ttu-id="b138e-110">et définissez-le comme actif.</span><span class="sxs-lookup"><span data-stu-id="b138e-110">and set it as active.</span></span>
3. <span data-ttu-id="b138e-111">Cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="b138e-111">Click Configurations.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="b138e-112">Créer une configuration de modèle de données</span><span class="sxs-lookup"><span data-stu-id="b138e-112">Create a new data model configuration</span></span>
1. <span data-ttu-id="b138e-113">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b138e-113">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="b138e-114">Vous allez créer une configuration qui contient un modèle de données pour les paiements électroniques.</span><span class="sxs-lookup"><span data-stu-id="b138e-114">You will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="b138e-115">Cette configuration de modèle de données sera téléchargée dans LCS ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="b138e-115">This data model configuration will be uploaded into LCS later.</span></span>  
2. <span data-ttu-id="b138e-116">Tapez « Exemple de configuration de modèle » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="b138e-116">In the Name field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="b138e-117">Exemple de configuration de modèle</span><span class="sxs-lookup"><span data-stu-id="b138e-117">Sample model configuration</span></span>  
3. <span data-ttu-id="b138e-118">Tapez « Exemple de configuration de modèle » dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="b138e-118">In the Description field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="b138e-119">Exemple de configuration de modèle</span><span class="sxs-lookup"><span data-stu-id="b138e-119">Sample model configuration</span></span>  
4. <span data-ttu-id="b138e-120">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="b138e-120">Click Create configuration.</span></span>
5. <span data-ttu-id="b138e-121">Cliquez sur Concepteur de modèles.</span><span class="sxs-lookup"><span data-stu-id="b138e-121">Click Model designer.</span></span>
6. <span data-ttu-id="b138e-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="b138e-122">Click New.</span></span>
7. <span data-ttu-id="b138e-123">Tapez « Point d'entrée » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="b138e-123">In the Name field, type 'Entry point'.</span></span>
    * <span data-ttu-id="b138e-124">Point d'entrée</span><span class="sxs-lookup"><span data-stu-id="b138e-124">Entry point</span></span>  
8. <span data-ttu-id="b138e-125">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b138e-125">Click Add.</span></span>
9. <span data-ttu-id="b138e-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="b138e-126">Click Save.</span></span>
10. <span data-ttu-id="b138e-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b138e-127">Close the page.</span></span>
11. <span data-ttu-id="b138e-128">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="b138e-128">Click Change status.</span></span>
12. <span data-ttu-id="b138e-129">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="b138e-129">Click Complete.</span></span>
13. <span data-ttu-id="b138e-130">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b138e-130">Click OK.</span></span>

## <a name="register-a-new--repository"></a><span data-ttu-id="b138e-131">Enregistrez un nouveau référentiel.</span><span class="sxs-lookup"><span data-stu-id="b138e-131">Register a new  repository</span></span>
1. <span data-ttu-id="b138e-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b138e-132">Close the page.</span></span>
2. <span data-ttu-id="b138e-133">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="b138e-133">Click Repositories.</span></span>
    * <span data-ttu-id="b138e-134">Cela vous permet d'ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="b138e-134">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
3. <span data-ttu-id="b138e-135">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b138e-135">Click Add to open the drop dialog.</span></span>
    * <span data-ttu-id="b138e-136">Cela vous permet d'ajouter un référentiel.</span><span class="sxs-lookup"><span data-stu-id="b138e-136">This allows you to add a new repository.</span></span>  
4. <span data-ttu-id="b138e-137">Sélectionnez LCS dans le champ Type du référentiel de configuration.</span><span class="sxs-lookup"><span data-stu-id="b138e-137">In the Configuration repository type field, select LCS.</span></span>
5. <span data-ttu-id="b138e-138">Cliquez sur Créer un référentiel.</span><span class="sxs-lookup"><span data-stu-id="b138e-138">Click Create repository.</span></span>
6. <span data-ttu-id="b138e-139">Dans le champ Projet, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b138e-139">In the Project field, enter or select a value.</span></span>
    * <span data-ttu-id="b138e-140">Sélectionnez le projet LCS souhaité.</span><span class="sxs-lookup"><span data-stu-id="b138e-140">Select the desired LCS project.</span></span> <span data-ttu-id="b138e-141">Vous devez avoir accès au projet.</span><span class="sxs-lookup"><span data-stu-id="b138e-141">You must have access to the project.</span></span>  
7. <span data-ttu-id="b138e-142">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b138e-142">Click OK.</span></span>
    * <span data-ttu-id="b138e-143">Effectuez une nouvelle entrée de référentiel.</span><span class="sxs-lookup"><span data-stu-id="b138e-143">Complete a new repository entry.</span></span>  
8. <span data-ttu-id="b138e-144">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b138e-144">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="b138e-145">Sélectionnez l'enregistrement Référentiel LCS.</span><span class="sxs-lookup"><span data-stu-id="b138e-145">Select the LCS repository record.</span></span>  
    * <span data-ttu-id="b138e-146">Notez qu'un référentiel enregistré est marqué par le fournisseur actuel, ce qui signifie que seules les configurations détenues par ce fournisseur peuvent être placées dans ce référentiel et donc être chargées dans le projet LCS sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b138e-146">Note that a registered repository is marked by the current provider meaning that the only configurations owned by that provider can be placed to this repository and, consequently, uploaded into the selected LCS project.</span></span>  
9. <span data-ttu-id="b138e-147">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="b138e-147">Click Open.</span></span>
    * <span data-ttu-id="b138e-148">Ouvrez le référentiel pour afficher la liste des configurations d'ER.</span><span class="sxs-lookup"><span data-stu-id="b138e-148">Open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="b138e-149">Elle est vide si ce projet n'a pas encore été utilisé pour le partage de configurations d'ER.</span><span class="sxs-lookup"><span data-stu-id="b138e-149">It will be empty if this project has not yet been used for ER configurations sharing.</span></span>  
10. <span data-ttu-id="b138e-150">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b138e-150">Close the page.</span></span>
11. <span data-ttu-id="b138e-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b138e-151">Close the page.</span></span>

## <a name="upload-configuration-into-lcs"></a><span data-ttu-id="b138e-152">Téléchargez la configuration dans LCS.</span><span class="sxs-lookup"><span data-stu-id="b138e-152">Upload configuration into LCS</span></span>
1. <span data-ttu-id="b138e-153">Cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="b138e-153">Click Configurations.</span></span>
2. <span data-ttu-id="b138e-154">Dans l'arborescence, sélectionnez « Exemple de configuration de modèle ».</span><span class="sxs-lookup"><span data-stu-id="b138e-154">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="b138e-155">Sélectionnez une configuration qui est déjà terminée.</span><span class="sxs-lookup"><span data-stu-id="b138e-155">Select a created configuration that has been already completed.</span></span>  
3. <span data-ttu-id="b138e-156">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b138e-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b138e-157">Sélectionnez la version de la configuration sélectionnée ayant le statut « Terminé ».</span><span class="sxs-lookup"><span data-stu-id="b138e-157">Select the version of the selected configuration with the status of ‘Completed’.</span></span>  
4. <span data-ttu-id="b138e-158">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="b138e-158">Click Change status.</span></span>
5. <span data-ttu-id="b138e-159">Cliquez sur Partager.</span><span class="sxs-lookup"><span data-stu-id="b138e-159">Click Share.</span></span>
    * <span data-ttu-id="b138e-160">Le statut de configuration passe de « Terminé » à « Partagé » lorsqu'il est attribué dans LCS.</span><span class="sxs-lookup"><span data-stu-id="b138e-160">The configuration status will change from ‘Completed’ to ‘Shared’ when it is published in LCS.</span></span>  
6. <span data-ttu-id="b138e-161">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b138e-161">Click OK.</span></span>
7. <span data-ttu-id="b138e-162">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b138e-162">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b138e-163">Sélectionnez la version de configuration dont le statut est « Partagé ».</span><span class="sxs-lookup"><span data-stu-id="b138e-163">Select the configuration version with the status of 'Shared'.</span></span>  
    * <span data-ttu-id="b138e-164">Notez que le statut de la version sélectionnée est passé de « Terminé » à « Partagé ».</span><span class="sxs-lookup"><span data-stu-id="b138e-164">Note that the status of the selected version has changed from ‘Completed’ to ‘Shared’.</span></span>  
8. <span data-ttu-id="b138e-165">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b138e-165">Close the page.</span></span>
9. <span data-ttu-id="b138e-166">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="b138e-166">Click Repositories.</span></span>
    * <span data-ttu-id="b138e-167">Cela vous permet d'ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="b138e-167">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
10. <span data-ttu-id="b138e-168">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="b138e-168">Click Open.</span></span>
    * <span data-ttu-id="b138e-169">Sélectionnez le référentiel LCS et ouvrez- le.</span><span class="sxs-lookup"><span data-stu-id="b138e-169">Select the LCS repository and open it.</span></span>  
    * <span data-ttu-id="b138e-170">Notez que la configuration sélectionnée est indiquée comme un actif du projet LCS sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b138e-170">Note that the selected configuration is shown as an asset of the selected LCS project.</span></span>  
    * <span data-ttu-id="b138e-171">Ouvrez LCS à l'aide de l'adresse https://lcs.dynamics.com. Ouvrez un projet utilisé précédemment pour l'enregistrement du référentiel, ouvrez la bibliothèque d'actifs de ce projet, et développez le contenu du type d'actif Configuration GER, la configuration ER téléchargée est disponible.</span><span class="sxs-lookup"><span data-stu-id="b138e-171">Open LCS using https://lcs.dynamics.com. Open a project that was used earlier for repository registration, open the ‘Asset library’ of this project, and expand the content of the ‘GER configuration’ asset type – the uploaded ER configuration will be available.</span></span> <span data-ttu-id="b138e-172">Notez que la configuration LCS téléchargée peut être importée dans une autre instance de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition si les fournisseurs ont accès à ce projet LCS.</span><span class="sxs-lookup"><span data-stu-id="b138e-172">Note that the uploaded LCS configuration can be imported to another Microsoft Dynamics 365 for Finance and Operations, Enterprise edition instance if providers have access to this LCS project.</span></span>  


