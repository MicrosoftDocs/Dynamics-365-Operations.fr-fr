--- 
title: "Créer les matières premières (février 2016 uniquement)"
description: "Cette tâche consiste à créer les composants de produits finis et semi-finis."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3d77dcc20fe7402af83dd724e7fef848977e5bf8
ms.openlocfilehash: f6af7b93d8d1d9a6f7474f24177b16e5295e90d6
ms.contentlocale: fr-fr
ms.lasthandoff: 11/08/2017

---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="ec888-103">Créer les matières premières (février 2016 uniquement)</span><span class="sxs-lookup"><span data-stu-id="ec888-103">Create raw materials (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ec888-104">Cette tâche consiste à créer les composants de produits finis et semi-finis.</span><span class="sxs-lookup"><span data-stu-id="ec888-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="ec888-105">Il s'agit de la troisième tâche dans la série de calculs des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="ec888-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="ec888-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="ec888-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="ec888-107">Créer le premier matériau</span><span class="sxs-lookup"><span data-stu-id="ec888-107">Create the first material</span></span>
1. <span data-ttu-id="ec888-108">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="ec888-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="ec888-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ec888-109">Click New.</span></span>
3. <span data-ttu-id="ec888-110">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ec888-111">Pour cet exemple, entrez ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="ec888-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="ec888-112">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="ec888-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-113">Sélectionnez STD.</span><span class="sxs-lookup"><span data-stu-id="ec888-113">Select STD.</span></span> <span data-ttu-id="ec888-114">STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec888-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="ec888-115">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-116">Par exemple, sélectionnez Audio.</span><span class="sxs-lookup"><span data-stu-id="ec888-116">For example, select Audio.</span></span> <span data-ttu-id="ec888-117">Cela n'a aucun impact sur les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec888-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="ec888-118">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="ec888-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-119">Sélectionnez SiteWH.</span><span class="sxs-lookup"><span data-stu-id="ec888-119">Select SiteWH.</span></span> <span data-ttu-id="ec888-120">Seul Site et entrepôt sera utilisé pour la démonstration.</span><span class="sxs-lookup"><span data-stu-id="ec888-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="ec888-121">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="ec888-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-122">Les dimensions de suivi ne seront pas utilisées pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="ec888-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="ec888-123">Sélectionnez Aucun.</span><span class="sxs-lookup"><span data-stu-id="ec888-123">Select None.</span></span>  
8. <span data-ttu-id="ec888-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ec888-124">Click OK.</span></span>
9. <span data-ttu-id="ec888-125">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="ec888-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="ec888-126">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="ec888-126">Click Default order settings.</span></span>
11. <span data-ttu-id="ec888-127">Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-128">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="ec888-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="ec888-129">Dans le champ Site de stock, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-130">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="ec888-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="ec888-131">Dans le champ Site de vente, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-132">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="ec888-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="ec888-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ec888-133">Close the page.</span></span>
15. <span data-ttu-id="ec888-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ec888-134">Close the page.</span></span>
16. <span data-ttu-id="ec888-135">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ec888-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ec888-136">Cliquez sur ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="ec888-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="ec888-137">Développez la section Gérer les coûts.</span><span class="sxs-lookup"><span data-stu-id="ec888-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="ec888-138">Dans le champ Groupe de coûts, taper une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="ec888-139">Pour cet exemple, tapez M2.</span><span class="sxs-lookup"><span data-stu-id="ec888-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="ec888-140">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="ec888-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="ec888-141">Cliquez sur Prix de l'article.</span><span class="sxs-lookup"><span data-stu-id="ec888-141">Click Item price.</span></span>
21. <span data-ttu-id="ec888-142">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ec888-142">Click New.</span></span>
22. <span data-ttu-id="ec888-143">Dans le champ Version, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-144">Pour cet exemple, sélectionnez 10, qui est le type d'évaluation des coûts pour un coût standard.</span><span class="sxs-lookup"><span data-stu-id="ec888-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="ec888-145">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="ec888-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-146">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="ec888-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="ec888-147">Dans le champ Prix, saisissez un numéro.</span><span class="sxs-lookup"><span data-stu-id="ec888-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="ec888-148">Pour cet exemple, tapez 10.</span><span class="sxs-lookup"><span data-stu-id="ec888-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="ec888-149">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ec888-149">Click Save.</span></span>
26. <span data-ttu-id="ec888-150">Cliquez sur Activer le ou les prix en attente.</span><span class="sxs-lookup"><span data-stu-id="ec888-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="ec888-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ec888-151">Close the page.</span></span>
28. <span data-ttu-id="ec888-152">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ec888-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="ec888-153">Créer le deuxième matériau</span><span class="sxs-lookup"><span data-stu-id="ec888-153">Create the second material</span></span>
1. <span data-ttu-id="ec888-154">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ec888-154">Click New.</span></span>
2. <span data-ttu-id="ec888-155">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ec888-156">Pour cet exemple, tapez ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="ec888-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="ec888-157">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="ec888-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-158">Sélectionnez STD.</span><span class="sxs-lookup"><span data-stu-id="ec888-158">Select STD.</span></span> <span data-ttu-id="ec888-159">STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec888-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="ec888-160">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-161">Par exemple, sélectionnez Audio.</span><span class="sxs-lookup"><span data-stu-id="ec888-161">For example, select Audio.</span></span> <span data-ttu-id="ec888-162">Cela n'a aucun impact sur les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec888-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="ec888-163">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="ec888-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-164">Sélectionnez SiteWH.</span><span class="sxs-lookup"><span data-stu-id="ec888-164">Select SiteWH.</span></span> <span data-ttu-id="ec888-165">Seul Site et entrepôt sera utilisé pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="ec888-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="ec888-166">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="ec888-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-167">Les dimensions de suivi ne seront pas utilisées pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="ec888-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="ec888-168">Sélectionnez Aucun.</span><span class="sxs-lookup"><span data-stu-id="ec888-168">Select None.</span></span>  
7. <span data-ttu-id="ec888-169">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ec888-169">Click OK.</span></span>
8. <span data-ttu-id="ec888-170">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="ec888-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="ec888-171">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="ec888-171">Click Default order settings.</span></span>
10. <span data-ttu-id="ec888-172">Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-173">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="ec888-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="ec888-174">Dans le champ Site de stock, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-175">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="ec888-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="ec888-176">Dans le champ Site de vente, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-177">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="ec888-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="ec888-178">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ec888-178">Close the page.</span></span>
14. <span data-ttu-id="ec888-179">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ec888-179">Close the page.</span></span>
15. <span data-ttu-id="ec888-180">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ec888-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ec888-181">Cliquer sur ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="ec888-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="ec888-182">Développez la section Gérer les coûts.</span><span class="sxs-lookup"><span data-stu-id="ec888-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="ec888-183">Dans le champ Groupe de coûts, taper une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="ec888-184">Pour cet exemple, tapez M2.</span><span class="sxs-lookup"><span data-stu-id="ec888-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="ec888-185">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="ec888-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="ec888-186">Cliquez sur Prix de l'article.</span><span class="sxs-lookup"><span data-stu-id="ec888-186">Click Item price.</span></span>
20. <span data-ttu-id="ec888-187">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ec888-187">Click New.</span></span>
21. <span data-ttu-id="ec888-188">Dans le champ Version, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-189">Pour cet exemple, sélectionnez 10.</span><span class="sxs-lookup"><span data-stu-id="ec888-189">For this example, select 10.</span></span> <span data-ttu-id="ec888-190">Il s'agit du type d'évaluation des coûts pour un coût standard.</span><span class="sxs-lookup"><span data-stu-id="ec888-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="ec888-191">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="ec888-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-192">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="ec888-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="ec888-193">Dans le champ Prix, saisissez un numéro.</span><span class="sxs-lookup"><span data-stu-id="ec888-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="ec888-194">Pour la démonstration, entrez 10.</span><span class="sxs-lookup"><span data-stu-id="ec888-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="ec888-195">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ec888-195">Click Save.</span></span>
25. <span data-ttu-id="ec888-196">Cliquez sur Activer le ou les prix en attente.</span><span class="sxs-lookup"><span data-stu-id="ec888-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="ec888-197">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ec888-197">Close the page.</span></span>
27. <span data-ttu-id="ec888-198">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ec888-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="ec888-199">Créer le troisième matériau</span><span class="sxs-lookup"><span data-stu-id="ec888-199">Create the third material</span></span>
1. <span data-ttu-id="ec888-200">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ec888-200">Click New.</span></span>
2. <span data-ttu-id="ec888-201">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ec888-202">Pour la démonstration, entrez ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="ec888-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="ec888-203">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="ec888-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-204">Sélectionnez STD.</span><span class="sxs-lookup"><span data-stu-id="ec888-204">Select STD.</span></span> <span data-ttu-id="ec888-205">STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec888-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="ec888-206">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-207">Par exemple, sélectionnez Audio.</span><span class="sxs-lookup"><span data-stu-id="ec888-207">For example, select Audio.</span></span> <span data-ttu-id="ec888-208">Cela n'a aucun impact sur les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec888-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="ec888-209">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="ec888-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-210">Sélectionnez SiteWH.</span><span class="sxs-lookup"><span data-stu-id="ec888-210">Select SiteWH.</span></span> <span data-ttu-id="ec888-211">Seul Site et entrepôt sera utilisé pour la démonstration.</span><span class="sxs-lookup"><span data-stu-id="ec888-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="ec888-212">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="ec888-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-213">Les dimensions de suivi ne seront pas utilisées pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="ec888-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="ec888-214">Sélectionnez Aucun.</span><span class="sxs-lookup"><span data-stu-id="ec888-214">Select None.</span></span>  
7. <span data-ttu-id="ec888-215">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ec888-215">Click OK.</span></span>
8. <span data-ttu-id="ec888-216">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="ec888-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="ec888-217">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="ec888-217">Click Default order settings.</span></span>
10. <span data-ttu-id="ec888-218">Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-219">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="ec888-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="ec888-220">Dans le champ Site de stock, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-221">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="ec888-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="ec888-222">Dans le champ Site de vente, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-223">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="ec888-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="ec888-224">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ec888-224">Close the page.</span></span>
14. <span data-ttu-id="ec888-225">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ec888-225">Close the page.</span></span>
15. <span data-ttu-id="ec888-226">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ec888-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ec888-227">Cliquez sur ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="ec888-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="ec888-228">Développez la section Gérer les coûts.</span><span class="sxs-lookup"><span data-stu-id="ec888-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="ec888-229">Dans le champ Groupe de coûts, taper une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="ec888-230">Pour cet exemple, tapez M1.</span><span class="sxs-lookup"><span data-stu-id="ec888-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="ec888-231">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="ec888-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="ec888-232">Cliquez sur Prix de l'article.</span><span class="sxs-lookup"><span data-stu-id="ec888-232">Click Item price.</span></span>
20. <span data-ttu-id="ec888-233">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ec888-233">Click New.</span></span>
21. <span data-ttu-id="ec888-234">Dans le champ Version, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ec888-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-235">Pour cet exemple, sélectionnez 10.</span><span class="sxs-lookup"><span data-stu-id="ec888-235">For this example, select 10.</span></span> <span data-ttu-id="ec888-236">Il s'agit du type d'évaluation des coûts pour un coût standard.</span><span class="sxs-lookup"><span data-stu-id="ec888-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="ec888-237">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="ec888-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ec888-238">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="ec888-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="ec888-239">Dans le champ Prix, saisissez un numéro.</span><span class="sxs-lookup"><span data-stu-id="ec888-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="ec888-240">Pour cet exemple, tapez 10.</span><span class="sxs-lookup"><span data-stu-id="ec888-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="ec888-241">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ec888-241">Click Save.</span></span>
25. <span data-ttu-id="ec888-242">Cliquez sur Activer le ou les prix en attente.</span><span class="sxs-lookup"><span data-stu-id="ec888-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="ec888-243">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ec888-243">Close the page.</span></span>
27. <span data-ttu-id="ec888-244">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ec888-244">Close the page.</span></span>

