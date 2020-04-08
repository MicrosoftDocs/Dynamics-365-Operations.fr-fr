---
title: ER Charger une configuration à partir de Lifecycle Services
description: Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut importer une nouvelle version d'une configuration pour la génération d'états électroniques (ER) à partir de Microsoft Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable,  ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 67e09e3187ac49e12727116f55066b64a386e2de
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142384"
---
# <a name="er-import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="d7083-103">ER Charger une configuration à partir de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="d7083-103">ER Import a configuration from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d7083-104">Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut importer une nouvelle version d'une configuration pour la génération d'états électroniques (ER) à partir de Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d7083-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="d7083-105">Dans cet exemple, vous allez sélectionner la version souhaitée de la configuration ER et l'importer pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les configurations ER sont partagées entre les sociétés.</span><span class="sxs-lookup"><span data-stu-id="d7083-105">In this example, you will select the desired version of the ER configuration and import it for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="d7083-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Charger une configuration ER dans Lifecycle Services ».</span><span class="sxs-lookup"><span data-stu-id="d7083-106">To complete these steps, you must first complete the steps in the "Upload an ER configuration into Lifecycle Services" procedure.</span></span> <span data-ttu-id="d7083-107">L'accès à LCS est également requis pour réaliser ces étapes.</span><span class="sxs-lookup"><span data-stu-id="d7083-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="d7083-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="d7083-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="d7083-109">Cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="d7083-109">Click Configurations.</span></span>

## <a name="delete-a-shared-version-of-data-model-configuration"></a><span data-ttu-id="d7083-110">Supprimer une version partagée de la configuration du modèle de données</span><span class="sxs-lookup"><span data-stu-id="d7083-110">Delete a shared version of data model configuration</span></span>
1. <span data-ttu-id="d7083-111">Dans l'arborescence, sélectionnez « Exemple de configuration de modèle ».</span><span class="sxs-lookup"><span data-stu-id="d7083-111">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="d7083-112">La première version d'un exemple de configuration de modèle de données a été créée et publiée dans LCS durant la procédure « Charger une configuration ER dans Lifecycle Services ».</span><span class="sxs-lookup"><span data-stu-id="d7083-112">The first version of a sample data model configuration has been created and published to LCS during the "Upload an ER configuration into Lifecycle Services" procedure.</span></span> <span data-ttu-id="d7083-113">Dans cette procédure, vous supprimerez cette version de la configuration ER.</span><span class="sxs-lookup"><span data-stu-id="d7083-113">In this procedure, you will delete this version of the ER configuration.</span></span> <span data-ttu-id="d7083-114">Cette version d'un exemple de configuration de modèle de données sera importée ultérieurement à partir de LCS.</span><span class="sxs-lookup"><span data-stu-id="d7083-114">This version of a sample data model configuration will be imported later from LCS.</span></span>  
2. <span data-ttu-id="d7083-115">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d7083-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d7083-116">Sélectionnez la version de cette configuration dont le statut est « Partagé ».</span><span class="sxs-lookup"><span data-stu-id="d7083-116">Select the version of this configuration that is in the 'Shared' status.</span></span> <span data-ttu-id="d7083-117">Ce statut indique que la configuration a été publiée dans LCS.</span><span class="sxs-lookup"><span data-stu-id="d7083-117">This status indicates that the configuration has been published to LCS.</span></span>  
3. <span data-ttu-id="d7083-118">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="d7083-118">Click Change status.</span></span>
4. <span data-ttu-id="d7083-119">Cliquez sur Interrompre.</span><span class="sxs-lookup"><span data-stu-id="d7083-119">Click Discontinue.</span></span>
    * <span data-ttu-id="d7083-120">Faites passer le statut de la version sélectionnée de « Partagé » à « Interrompu » pour le rendre disponible pour la suppression.</span><span class="sxs-lookup"><span data-stu-id="d7083-120">Change the status of the selected version from 'Shared' to 'Discontinued' to make it available for deletion.</span></span>  
5. <span data-ttu-id="d7083-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d7083-121">Click OK.</span></span>
6. <span data-ttu-id="d7083-122">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d7083-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d7083-123">Sélectionnez la version de cette configuration dont le statut est « Interrompu ».</span><span class="sxs-lookup"><span data-stu-id="d7083-123">Select the version of this configuration that has a status of 'Discontinued'.</span></span>  
7. <span data-ttu-id="d7083-124">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="d7083-124">Click Delete.</span></span>
8. <span data-ttu-id="d7083-125">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="d7083-125">Click Yes.</span></span>
    * <span data-ttu-id="d7083-126">Notez que seule la version temporaire 2 de la configuration de modèle de données sélectionnée est disponible.</span><span class="sxs-lookup"><span data-stu-id="d7083-126">Note that the only draft version 2 of the selected data model configuration is available.</span></span>  
9. <span data-ttu-id="d7083-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d7083-127">Close the page.</span></span>

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a><span data-ttu-id="d7083-128">Importer une version partagée de la configuration du modèle de données à partir de LCS</span><span class="sxs-lookup"><span data-stu-id="d7083-128">Import a shared version of data model configuration from LCS</span></span>
1. <span data-ttu-id="d7083-129">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d7083-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d7083-130">Ouvrez la liste des référentiels pour le fournisseur de configuration « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="d7083-130">Open the list of repositories for the 'Litware, Inc.'</span></span> <span data-ttu-id="d7083-131">.</span><span class="sxs-lookup"><span data-stu-id="d7083-131">configuration provider.</span></span>  
2. <span data-ttu-id="d7083-132">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="d7083-132">Click Repositories.</span></span>
3. <span data-ttu-id="d7083-133">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="d7083-133">Click Open.</span></span>
    * <span data-ttu-id="d7083-134">Sélectionnez le référentiel LCS et ouvrez- le.</span><span class="sxs-lookup"><span data-stu-id="d7083-134">Select the LCS repository and open it.</span></span>  
4. <span data-ttu-id="d7083-135">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d7083-135">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d7083-136">Sélectionnez la première version « Exemple de configuration de modèle » dans la liste des versions.</span><span class="sxs-lookup"><span data-stu-id="d7083-136">Select the first version of the 'Sample model configuration' in the versions list.</span></span>  
5. <span data-ttu-id="d7083-137">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="d7083-137">Click Import.</span></span>
6. <span data-ttu-id="d7083-138">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="d7083-138">Click Yes.</span></span>
    * <span data-ttu-id="d7083-139">Confirmez l'importation de la version sélectionnée de LCS.</span><span class="sxs-lookup"><span data-stu-id="d7083-139">Confirm the import of the selected version from LCS .</span></span>  
    * <span data-ttu-id="d7083-140">Notez que le message d'information (au-dessus de l'écran) confirme la réussite de l'importation de la version sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d7083-140">Note that the information message (above the form) confirms the successful completion of the import of the selected version.</span></span>  
7. <span data-ttu-id="d7083-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d7083-141">Close the page.</span></span>
8. <span data-ttu-id="d7083-142">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d7083-142">Close the page.</span></span>
9. <span data-ttu-id="d7083-143">Cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="d7083-143">Click Configurations.</span></span>
10. <span data-ttu-id="d7083-144">Dans l'arborescence, sélectionnez « Exemple de configuration de modèle ».</span><span class="sxs-lookup"><span data-stu-id="d7083-144">In the tree, select 'Sample model configuration'.</span></span>
11. <span data-ttu-id="d7083-145">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d7083-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d7083-146">Sélectionnez la version de cette configuration dont le statut est « Partagé ».</span><span class="sxs-lookup"><span data-stu-id="d7083-146">Select the version of this configuration that has a status of 'Shared'.</span></span>  
    * <span data-ttu-id="d7083-147">Notez que seule la version partagée 1 de la configuration de modèle de données sélectionnée est maintenant disponible.</span><span class="sxs-lookup"><span data-stu-id="d7083-147">Note that the shared version 1 of the selected data model configuration is available now as well.</span></span>  

