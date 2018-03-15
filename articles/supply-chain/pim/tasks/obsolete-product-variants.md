--- 
title: "Rechercher les variantes de produit obsolètes"
description: "Cette procédure décrit comment rechercher des produits ou des variantes de produits lancés obsolètes et comment associer un état du cycle de vie des produits aux produits obsolètes."
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d445ea2f2362f146a1e3e7bcf747898dc2cc89ba
ms.openlocfilehash: 3a59f988de5290d1d69d013b762f87d0cce10e39
ms.contentlocale: fr-fr
ms.lasthandoff: 02/08/2018

---
# <a name="find-obsolete-product-variants"></a><span data-ttu-id="4cfed-103">Rechercher les variantes de produit obsolètes</span><span class="sxs-lookup"><span data-stu-id="4cfed-103">Find obsolete product variants</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4cfed-104">Cette procédure décrit comment rechercher des produits ou des variantes de produits lancés obsolètes et comment associer un état du cycle de vie des produits aux produits obsolètes.</span><span class="sxs-lookup"><span data-stu-id="4cfed-104">This procedure shows how to find obsolete released products or product variants and how to associate a product lifecycle state to the obsolete products.</span></span> <span data-ttu-id="4cfed-105">Conditions préalables : vous devez définir au moins un état du cycle de vie des produits qui est inactif pour la planification avant de lire ce guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="4cfed-105">Prerequisite: You need to define at least one product lifecycle state that is inactive for planning before you can play this task guide.</span></span>


## <a name="run-a-simulation"></a><span data-ttu-id="4cfed-106">Exécuter une simulation</span><span class="sxs-lookup"><span data-stu-id="4cfed-106">Run a simulation</span></span>
1. <span data-ttu-id="4cfed-107">Accédez à Gestion des informations sur les produits > Tâches périodiques > Modifier l'état du cycle de vie des produits obsolètes.</span><span class="sxs-lookup"><span data-stu-id="4cfed-107">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
2. <span data-ttu-id="4cfed-108">Dans le champ Nouvel état du cycle de vie des produits, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4cfed-108">In the New product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="4cfed-109">Sélectionnez Oui dans le champ Exécuter la simulation sans mettre à jour les données du produit.</span><span class="sxs-lookup"><span data-stu-id="4cfed-109">Select Yes in the Run simulation without updating product data field.</span></span>
4. <span data-ttu-id="4cfed-110">Dans le champ Exclure les produits créés dans ce nombre de jours, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="4cfed-110">In the Exclude products created within this number of days field, enter a number.</span></span>
5. <span data-ttu-id="4cfed-111">Dans le champ Exclure les produits utilisés dans les transactions (en nombre de jours), entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="4cfed-111">In the Exclude products used in transactions (in number of days) field, enter a number.</span></span>
6. <span data-ttu-id="4cfed-112">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="4cfed-112">Expand the Records to include section.</span></span>
7. <span data-ttu-id="4cfed-113">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="4cfed-113">Click Filter.</span></span>
8. <span data-ttu-id="4cfed-114">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4cfed-114">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="4cfed-115">Tapez une valeur dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="4cfed-115">In the Criteria field, type a value.</span></span>
10. <span data-ttu-id="4cfed-116">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4cfed-116">Click OK.</span></span>
11. <span data-ttu-id="4cfed-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4cfed-117">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="4cfed-118">Nous vous recommandons d'exécuter la simulation par lots si vous comptez rechercher un grand nombre de produits.</span><span class="sxs-lookup"><span data-stu-id="4cfed-118">It is recommended to run the simulation in batch if you expect to search a large number of products.</span></span> <span data-ttu-id="4cfed-119">En outre, vérifiez que la simulation n'est pas exécutée pendant le temps de travail le plus actif de la société.</span><span class="sxs-lookup"><span data-stu-id="4cfed-119">Also, make sure that the simulation is not run during the most active working time of the company.</span></span>  

## <a name="review-the-simulation-results"></a><span data-ttu-id="4cfed-120">Examiner les résultats de la simulation</span><span class="sxs-lookup"><span data-stu-id="4cfed-120">Review the simulation results</span></span>
1. <span data-ttu-id="4cfed-121">Accédez à Gestion des informations sur les produits > Recherches et états > Historique de maintenance de l'état du cycle de vie des produits.</span><span class="sxs-lookup"><span data-stu-id="4cfed-121">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>
   
> [!NOTE]
> <span data-ttu-id="4cfed-122">Sur cette page, vous pouvez examiner les résultats de la simulation et effectuer une évaluation du nombre de produits et de variantes de produit à associer à un nouvel état du cycle de vie des produits lors de l'exécution de la mise à jour sans simulation.</span><span class="sxs-lookup"><span data-stu-id="4cfed-122">On this page, you can review the simulation results and make an assessment of how many products and product variants will be associated with a new product lifecycle state when running the update without simulation.</span></span>  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a><span data-ttu-id="4cfed-123">Exécuter la mise à jour de l'état du cycle de vie des produits pour les produits obsolètes</span><span class="sxs-lookup"><span data-stu-id="4cfed-123">Run the update of the Product lifecycle state for obsolete products</span></span>
1. <span data-ttu-id="4cfed-124">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4cfed-124">Close the page.</span></span>
2. <span data-ttu-id="4cfed-125">Accédez à Gestion des informations sur les produits > Tâches périodiques > Modifier l'état du cycle de vie des produits obsolètes.</span><span class="sxs-lookup"><span data-stu-id="4cfed-125">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
3. <span data-ttu-id="4cfed-126">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="4cfed-126">Expand the Records to include section.</span></span>

> [!NOTE]
> <span data-ttu-id="4cfed-127">Notez que la dernière sélection a été enregistrée.</span><span class="sxs-lookup"><span data-stu-id="4cfed-127">Note that the last selection has been saved.</span></span>  

4. <span data-ttu-id="4cfed-128">Sélectionnez Non dans le champ Exécuter la simulation sans mettre à jour les données du produit.</span><span class="sxs-lookup"><span data-stu-id="4cfed-128">Select No in the Run simulation without updating product data field.</span></span>
5. <span data-ttu-id="4cfed-129">Développez la section Exécuter à l'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="4cfed-129">Expand the Run in the background section.</span></span>

> [!NOTE]
> <span data-ttu-id="4cfed-130">Selon le nombre de produits et de variantes de produit affectés, envisagez d'exécuter cette tâche par lots.</span><span class="sxs-lookup"><span data-stu-id="4cfed-130">Depending on how many products and product variants are affected, consider running this job in batch.</span></span> <span data-ttu-id="4cfed-131">Vérifiez que vous n'exécutez pas une tâche de mise à jour volumineuse pendant les heures de travail les plus actives de la société.</span><span class="sxs-lookup"><span data-stu-id="4cfed-131">Make sure that you are not running a large update job during the most active working hours in the company.</span></span>  

6. <span data-ttu-id="4cfed-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4cfed-132">Click OK.</span></span>
7. <span data-ttu-id="4cfed-133">Accédez à Gestion des informations sur les produits > Recherches et états > Historique de maintenance de l'état du cycle de vie des produits.</span><span class="sxs-lookup"><span data-stu-id="4cfed-133">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>

> [!NOTE]
> <span data-ttu-id="4cfed-134">Examinez les modifications des produits et des variantes de produits lancés.</span><span class="sxs-lookup"><span data-stu-id="4cfed-134">Review the changed released products and product variants.</span></span>  

8. <span data-ttu-id="4cfed-135">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="4cfed-135">In the list, find and select the desired record.</span></span>


