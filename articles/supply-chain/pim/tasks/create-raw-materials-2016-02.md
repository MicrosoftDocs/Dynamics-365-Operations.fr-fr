---
title: Créer des matières premières (février 2016)
description: Cette tâche consiste à créer les composants de produits finis et semi-finis.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e20abf8a1b211bff2bc73d1a36a1e5c917ffaab
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844583"
---
# <a name="create-raw-materials-february-2016"></a><span data-ttu-id="a83e0-103">Créer des matières premières (février 2016)</span><span class="sxs-lookup"><span data-stu-id="a83e0-103">Create raw materials (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a83e0-104">Cette tâche consiste à créer les composants de produits finis et semi-finis.</span><span class="sxs-lookup"><span data-stu-id="a83e0-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="a83e0-105">Il s'agit de la troisième tâche dans la série de calculs des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="a83e0-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="a83e0-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="a83e0-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="a83e0-107">Créer le premier matériau</span><span class="sxs-lookup"><span data-stu-id="a83e0-107">Create the first material</span></span>
1. <span data-ttu-id="a83e0-108">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="a83e0-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="a83e0-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a83e0-109">Click New.</span></span>
3. <span data-ttu-id="a83e0-110">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="a83e0-111">Pour cet exemple, entrez ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="a83e0-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="a83e0-112">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="a83e0-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-113">Sélectionnez STD.</span><span class="sxs-lookup"><span data-stu-id="a83e0-113">Select STD.</span></span> <span data-ttu-id="a83e0-114">STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="a83e0-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="a83e0-115">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-116">Par exemple, sélectionnez Audio.</span><span class="sxs-lookup"><span data-stu-id="a83e0-116">For example, select Audio.</span></span> <span data-ttu-id="a83e0-117">Cela n'a aucun impact sur les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="a83e0-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="a83e0-118">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="a83e0-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-119">Sélectionnez SiteWH.</span><span class="sxs-lookup"><span data-stu-id="a83e0-119">Select SiteWH.</span></span> <span data-ttu-id="a83e0-120">Seul Site et entrepôt sera utilisé pour la démonstration.</span><span class="sxs-lookup"><span data-stu-id="a83e0-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="a83e0-121">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="a83e0-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-122">Les dimensions de suivi ne seront pas utilisées pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="a83e0-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="a83e0-123">Sélectionnez Aucun.</span><span class="sxs-lookup"><span data-stu-id="a83e0-123">Select None.</span></span>  
8. <span data-ttu-id="a83e0-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a83e0-124">Click OK.</span></span>
9. <span data-ttu-id="a83e0-125">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="a83e0-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="a83e0-126">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="a83e0-126">Click Default order settings.</span></span>
11. <span data-ttu-id="a83e0-127">Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-128">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="a83e0-129">Dans le champ Site de stock, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-130">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="a83e0-131">Dans le champ Site de vente, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-132">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="a83e0-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a83e0-133">Close the page.</span></span>
15. <span data-ttu-id="a83e0-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a83e0-134">Close the page.</span></span>
16. <span data-ttu-id="a83e0-135">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a83e0-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a83e0-136">Cliquez sur ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="a83e0-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="a83e0-137">Développez la section Gérer les coûts.</span><span class="sxs-lookup"><span data-stu-id="a83e0-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="a83e0-138">Dans le champ Groupe de coûts, taper une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="a83e0-139">Pour cet exemple, tapez M2.</span><span class="sxs-lookup"><span data-stu-id="a83e0-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="a83e0-140">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="a83e0-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="a83e0-141">Cliquez sur Prix de l'article.</span><span class="sxs-lookup"><span data-stu-id="a83e0-141">Click Item price.</span></span>
21. <span data-ttu-id="a83e0-142">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a83e0-142">Click New.</span></span>
22. <span data-ttu-id="a83e0-143">Dans le champ Version, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-144">Pour cet exemple, sélectionnez 10, qui est le type d'évaluation des coûts pour un coût standard.</span><span class="sxs-lookup"><span data-stu-id="a83e0-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="a83e0-145">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="a83e0-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-146">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="a83e0-147">Dans le champ Prix, saisissez un numéro.</span><span class="sxs-lookup"><span data-stu-id="a83e0-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="a83e0-148">Pour cet exemple, tapez 10.</span><span class="sxs-lookup"><span data-stu-id="a83e0-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="a83e0-149">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a83e0-149">Click Save.</span></span>
26. <span data-ttu-id="a83e0-150">Cliquez sur Activer le ou les prix en attente.</span><span class="sxs-lookup"><span data-stu-id="a83e0-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="a83e0-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a83e0-151">Close the page.</span></span>
28. <span data-ttu-id="a83e0-152">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a83e0-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="a83e0-153">Créer le deuxième matériau</span><span class="sxs-lookup"><span data-stu-id="a83e0-153">Create the second material</span></span>
1. <span data-ttu-id="a83e0-154">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a83e0-154">Click New.</span></span>
2. <span data-ttu-id="a83e0-155">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="a83e0-156">Pour cet exemple, tapez ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="a83e0-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="a83e0-157">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="a83e0-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-158">Sélectionnez STD.</span><span class="sxs-lookup"><span data-stu-id="a83e0-158">Select STD.</span></span> <span data-ttu-id="a83e0-159">STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="a83e0-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="a83e0-160">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-161">Par exemple, sélectionnez Audio.</span><span class="sxs-lookup"><span data-stu-id="a83e0-161">For example, select Audio.</span></span> <span data-ttu-id="a83e0-162">Cela n'a aucun impact sur les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="a83e0-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="a83e0-163">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="a83e0-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-164">Sélectionnez SiteWH.</span><span class="sxs-lookup"><span data-stu-id="a83e0-164">Select SiteWH.</span></span> <span data-ttu-id="a83e0-165">Seul Site et entrepôt sera utilisé pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="a83e0-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="a83e0-166">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="a83e0-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-167">Les dimensions de suivi ne seront pas utilisées pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="a83e0-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="a83e0-168">Sélectionnez Aucun.</span><span class="sxs-lookup"><span data-stu-id="a83e0-168">Select None.</span></span>  
7. <span data-ttu-id="a83e0-169">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a83e0-169">Click OK.</span></span>
8. <span data-ttu-id="a83e0-170">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="a83e0-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="a83e0-171">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="a83e0-171">Click Default order settings.</span></span>
10. <span data-ttu-id="a83e0-172">Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-173">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="a83e0-174">Dans le champ Site de stock, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-175">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="a83e0-176">Dans le champ Site de vente, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-177">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="a83e0-178">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a83e0-178">Close the page.</span></span>
14. <span data-ttu-id="a83e0-179">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a83e0-179">Close the page.</span></span>
15. <span data-ttu-id="a83e0-180">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a83e0-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a83e0-181">Cliquer sur ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="a83e0-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="a83e0-182">Développez la section Gérer les coûts.</span><span class="sxs-lookup"><span data-stu-id="a83e0-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="a83e0-183">Dans le champ Groupe de coûts, taper une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="a83e0-184">Pour cet exemple, tapez M2.</span><span class="sxs-lookup"><span data-stu-id="a83e0-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="a83e0-185">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="a83e0-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="a83e0-186">Cliquez sur Prix de l'article.</span><span class="sxs-lookup"><span data-stu-id="a83e0-186">Click Item price.</span></span>
20. <span data-ttu-id="a83e0-187">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a83e0-187">Click New.</span></span>
21. <span data-ttu-id="a83e0-188">Dans le champ Version, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-189">Pour cet exemple, sélectionnez 10.</span><span class="sxs-lookup"><span data-stu-id="a83e0-189">For this example, select 10.</span></span> <span data-ttu-id="a83e0-190">Il s'agit du type d'évaluation des coûts pour un coût standard.</span><span class="sxs-lookup"><span data-stu-id="a83e0-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="a83e0-191">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="a83e0-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-192">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="a83e0-193">Dans le champ Prix, saisissez un numéro.</span><span class="sxs-lookup"><span data-stu-id="a83e0-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="a83e0-194">Pour la démonstration, entrez 10.</span><span class="sxs-lookup"><span data-stu-id="a83e0-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="a83e0-195">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a83e0-195">Click Save.</span></span>
25. <span data-ttu-id="a83e0-196">Cliquez sur Activer le ou les prix en attente.</span><span class="sxs-lookup"><span data-stu-id="a83e0-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="a83e0-197">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a83e0-197">Close the page.</span></span>
27. <span data-ttu-id="a83e0-198">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a83e0-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="a83e0-199">Créer le troisième matériau</span><span class="sxs-lookup"><span data-stu-id="a83e0-199">Create the third material</span></span>
1. <span data-ttu-id="a83e0-200">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a83e0-200">Click New.</span></span>
2. <span data-ttu-id="a83e0-201">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="a83e0-202">Pour la démonstration, entrez ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="a83e0-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="a83e0-203">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="a83e0-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-204">Sélectionnez STD.</span><span class="sxs-lookup"><span data-stu-id="a83e0-204">Select STD.</span></span> <span data-ttu-id="a83e0-205">STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="a83e0-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="a83e0-206">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-207">Par exemple, sélectionnez Audio.</span><span class="sxs-lookup"><span data-stu-id="a83e0-207">For example, select Audio.</span></span> <span data-ttu-id="a83e0-208">Cela n'a aucun impact sur les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="a83e0-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="a83e0-209">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="a83e0-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-210">Sélectionnez SiteWH.</span><span class="sxs-lookup"><span data-stu-id="a83e0-210">Select SiteWH.</span></span> <span data-ttu-id="a83e0-211">Seul Site et entrepôt sera utilisé pour la démonstration.</span><span class="sxs-lookup"><span data-stu-id="a83e0-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="a83e0-212">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="a83e0-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-213">Les dimensions de suivi ne seront pas utilisées pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="a83e0-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="a83e0-214">Sélectionnez Aucun.</span><span class="sxs-lookup"><span data-stu-id="a83e0-214">Select None.</span></span>  
7. <span data-ttu-id="a83e0-215">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a83e0-215">Click OK.</span></span>
8. <span data-ttu-id="a83e0-216">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="a83e0-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="a83e0-217">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="a83e0-217">Click Default order settings.</span></span>
10. <span data-ttu-id="a83e0-218">Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-219">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="a83e0-220">Dans le champ Site de stock, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-221">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="a83e0-222">Dans le champ Site de vente, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-223">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="a83e0-224">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a83e0-224">Close the page.</span></span>
14. <span data-ttu-id="a83e0-225">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a83e0-225">Close the page.</span></span>
15. <span data-ttu-id="a83e0-226">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a83e0-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a83e0-227">Cliquez sur ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="a83e0-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="a83e0-228">Développez la section Gérer les coûts.</span><span class="sxs-lookup"><span data-stu-id="a83e0-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="a83e0-229">Dans le champ Groupe de coûts, taper une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="a83e0-230">Pour cet exemple, tapez M1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="a83e0-231">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="a83e0-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="a83e0-232">Cliquez sur Prix de l'article.</span><span class="sxs-lookup"><span data-stu-id="a83e0-232">Click Item price.</span></span>
20. <span data-ttu-id="a83e0-233">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a83e0-233">Click New.</span></span>
21. <span data-ttu-id="a83e0-234">Dans le champ Version, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a83e0-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-235">Pour cet exemple, sélectionnez 10.</span><span class="sxs-lookup"><span data-stu-id="a83e0-235">For this example, select 10.</span></span> <span data-ttu-id="a83e0-236">Il s'agit du type d'évaluation des coûts pour un coût standard.</span><span class="sxs-lookup"><span data-stu-id="a83e0-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="a83e0-237">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="a83e0-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="a83e0-238">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="a83e0-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="a83e0-239">Dans le champ Prix, saisissez un numéro.</span><span class="sxs-lookup"><span data-stu-id="a83e0-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="a83e0-240">Pour cet exemple, tapez 10.</span><span class="sxs-lookup"><span data-stu-id="a83e0-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="a83e0-241">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a83e0-241">Click Save.</span></span>
25. <span data-ttu-id="a83e0-242">Cliquez sur Activer le ou les prix en attente.</span><span class="sxs-lookup"><span data-stu-id="a83e0-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="a83e0-243">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a83e0-243">Close the page.</span></span>
27. <span data-ttu-id="a83e0-244">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a83e0-244">Close the page.</span></span>

