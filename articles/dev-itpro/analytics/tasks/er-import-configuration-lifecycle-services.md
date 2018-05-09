--- 
title: "Importer une configuration à partir de Lifecycle Services pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut importer une nouvelle version d'une configuration pour la génération d'états électroniques (ER) à partir de Microsoft Lifecycle Services (LCS)."
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 30345e74146dd8cc1dab5c4acfaf117ee604fb7f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="import-a-configuration-from-lifecycle-services-for-electronic-reporting-er"></a><span data-ttu-id="5da1f-103">Importer une configuration à partir de Lifecycle Services pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="5da1f-103">Import a configuration from Lifecycle Services for electronic reporting (ER)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5da1f-104">Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut importer une nouvelle version d'une configuration pour la génération d'états électroniques (ER) à partir de Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="5da1f-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="5da1f-105">Dans cet exemple, vous allez sélectionner la version souhaitée de la configuration ER et l'importer pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les configurations ER sont partagées entre les sociétés.</span><span class="sxs-lookup"><span data-stu-id="5da1f-105">In this example, you will select the desired version of the ER configuration and import it for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="5da1f-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Charger une configuration ER dans Lifecycle Services ».</span><span class="sxs-lookup"><span data-stu-id="5da1f-106">To complete these steps, you must first complete the steps in the “Upload an ER configuration into Lifecycle Services” procedure.</span></span> <span data-ttu-id="5da1f-107">L'accès à LCS est également requis pour réaliser ces étapes.</span><span class="sxs-lookup"><span data-stu-id="5da1f-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="5da1f-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="5da1f-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="5da1f-109">Cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="5da1f-109">Click Configurations.</span></span>

## <a name="delete-a-shared-version-of-data-model-configuration"></a><span data-ttu-id="5da1f-110">Supprimer une version partagée de la configuration du modèle de données</span><span class="sxs-lookup"><span data-stu-id="5da1f-110">Delete a shared version of data model configuration</span></span>
1. <span data-ttu-id="5da1f-111">Dans l'arborescence, sélectionnez « Exemple de configuration de modèle ».</span><span class="sxs-lookup"><span data-stu-id="5da1f-111">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="5da1f-112">La première version d'un exemple de configuration de modèle de données a été créée et publiée dans LCS durant la procédure « Charger une configuration ER dans Lifecycle Services ».</span><span class="sxs-lookup"><span data-stu-id="5da1f-112">The first version of a sample data model configuration has been created and published to LCS during the “Upload an ER configuration into Lifecycle Services” procedure.</span></span> <span data-ttu-id="5da1f-113">Dans cette procédure, vous supprimerez cette version de la configuration ER.</span><span class="sxs-lookup"><span data-stu-id="5da1f-113">In this procedure, you will delete this version of the ER configuration.</span></span> <span data-ttu-id="5da1f-114">Cette version d'un exemple de configuration de modèle de données sera importée ultérieurement à partir de LCS.</span><span class="sxs-lookup"><span data-stu-id="5da1f-114">This version of a sample data model configuration will be imported later from LCS.</span></span>  
2. <span data-ttu-id="5da1f-115">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="5da1f-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5da1f-116">Sélectionnez la version de cette configuration dont le statut est « Partagé ».</span><span class="sxs-lookup"><span data-stu-id="5da1f-116">Select the version of this configuration that is in the ‘Shared’ status.</span></span> <span data-ttu-id="5da1f-117">Ce statut indique que la configuration a été publiée dans LCS.</span><span class="sxs-lookup"><span data-stu-id="5da1f-117">This status indicates that the configuration has been published to LCS.</span></span>  
3. <span data-ttu-id="5da1f-118">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="5da1f-118">Click Change status.</span></span>
4. <span data-ttu-id="5da1f-119">Cliquez sur Interrompre.</span><span class="sxs-lookup"><span data-stu-id="5da1f-119">Click Discontinue.</span></span>
    * <span data-ttu-id="5da1f-120">Faites passer le statut de la version sélectionnée de « Partagé » à « Interrompu » pour le rendre disponible pour la suppression.</span><span class="sxs-lookup"><span data-stu-id="5da1f-120">Change the status of the selected version from ‘Shared’ to ‘Discontinued’ to make it available for deletion.</span></span>  
5. <span data-ttu-id="5da1f-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="5da1f-121">Click OK.</span></span>
6. <span data-ttu-id="5da1f-122">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="5da1f-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5da1f-123">Sélectionnez la version de cette configuration dont le statut est « Interrompu ».</span><span class="sxs-lookup"><span data-stu-id="5da1f-123">Select the version of this configuration that has a status of ‘Discontinued’.</span></span>  
7. <span data-ttu-id="5da1f-124">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="5da1f-124">Click Delete.</span></span>
8. <span data-ttu-id="5da1f-125">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="5da1f-125">Click Yes.</span></span>
    * <span data-ttu-id="5da1f-126">Notez que seule la version temporaire 2 de la configuration de modèle de données sélectionnée est disponible.</span><span class="sxs-lookup"><span data-stu-id="5da1f-126">Note that the only draft version 2 of the selected data model configuration is available.</span></span>  
9. <span data-ttu-id="5da1f-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5da1f-127">Close the page.</span></span>

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a><span data-ttu-id="5da1f-128">Importer une version partagée de la configuration du modèle de données à partir de LCS</span><span class="sxs-lookup"><span data-stu-id="5da1f-128">Import a shared version of data model configuration from LCS</span></span>
1. <span data-ttu-id="5da1f-129">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5da1f-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="5da1f-130">Ouvrez la liste des référentiels pour le fournisseur de configuration « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="5da1f-130">Open the list of repositories for the ‘Litware, Inc.’</span></span> <span data-ttu-id="5da1f-131">.</span><span class="sxs-lookup"><span data-stu-id="5da1f-131">configuration provider.</span></span>  
2. <span data-ttu-id="5da1f-132">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="5da1f-132">Click Repositories.</span></span>
3. <span data-ttu-id="5da1f-133">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="5da1f-133">Click Open.</span></span>
    * <span data-ttu-id="5da1f-134">Sélectionnez le référentiel LCS et ouvrez- le.</span><span class="sxs-lookup"><span data-stu-id="5da1f-134">Select the LCS repository and open it.</span></span>  
4. <span data-ttu-id="5da1f-135">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5da1f-135">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="5da1f-136">Sélectionnez la première version « Exemple de configuration de modèle » dans la liste des versions.</span><span class="sxs-lookup"><span data-stu-id="5da1f-136">Select the first version of the 'Sample model configuration' in the versions list.</span></span>  
5. <span data-ttu-id="5da1f-137">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="5da1f-137">Click Import.</span></span>
6. <span data-ttu-id="5da1f-138">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="5da1f-138">Click Yes.</span></span>
    * <span data-ttu-id="5da1f-139">Confirmez l'importation de la version sélectionnée de LCS.</span><span class="sxs-lookup"><span data-stu-id="5da1f-139">Confirm the import of the selected version from LCS .</span></span>  
    * <span data-ttu-id="5da1f-140">Notez que le message d'information (au-dessus de l'écran) confirme la réussite de l'importation de la version sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5da1f-140">Note that the information message (above the form) confirms the successful completion of the import of the selected version.</span></span>  
7. <span data-ttu-id="5da1f-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5da1f-141">Close the page.</span></span>
8. <span data-ttu-id="5da1f-142">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5da1f-142">Close the page.</span></span>
9. <span data-ttu-id="5da1f-143">Cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="5da1f-143">Click Configurations.</span></span>
10. <span data-ttu-id="5da1f-144">Dans l'arborescence, sélectionnez « Exemple de configuration de modèle ».</span><span class="sxs-lookup"><span data-stu-id="5da1f-144">In the tree, select 'Sample model configuration'.</span></span>
11. <span data-ttu-id="5da1f-145">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="5da1f-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5da1f-146">Sélectionnez la version de cette configuration dont le statut est « Partagé ».</span><span class="sxs-lookup"><span data-stu-id="5da1f-146">Select the version of this configuration that has a status of ‘Shared’.</span></span>  
    * <span data-ttu-id="5da1f-147">Notez que seule la version partagée 1 de la configuration de modèle de données sélectionnée est maintenant disponible.</span><span class="sxs-lookup"><span data-stu-id="5da1f-147">Note that the shared version 1 of the selected data model configuration is available now as well.</span></span>  


