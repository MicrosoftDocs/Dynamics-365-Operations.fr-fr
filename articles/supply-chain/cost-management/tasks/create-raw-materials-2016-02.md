---
title: Créer les matières premières (février 2016 uniquement)
description: Cette tâche consiste à créer les composants de produits finis et semi-finis.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 869acddf6f7e9754bb4952176ded4b22c74eaffd
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "327295"
---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="203af-103">Créer les matières premières (février 2016 uniquement)</span><span class="sxs-lookup"><span data-stu-id="203af-103">Create raw materials (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="203af-104">Cette tâche consiste à créer les composants de produits finis et semi-finis.</span><span class="sxs-lookup"><span data-stu-id="203af-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="203af-105">Il s'agit de la troisième tâche dans la série de calculs des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="203af-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="203af-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="203af-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="203af-107">Créer le premier matériau</span><span class="sxs-lookup"><span data-stu-id="203af-107">Create the first material</span></span>
1. <span data-ttu-id="203af-108">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="203af-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="203af-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="203af-109">Click New.</span></span>
3. <span data-ttu-id="203af-110">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="203af-111">Pour cet exemple, entrez ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="203af-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="203af-112">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="203af-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-113">Sélectionnez STD.</span><span class="sxs-lookup"><span data-stu-id="203af-113">Select STD.</span></span> <span data-ttu-id="203af-114">STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="203af-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="203af-115">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-116">Par exemple, sélectionnez Audio.</span><span class="sxs-lookup"><span data-stu-id="203af-116">For example, select Audio.</span></span> <span data-ttu-id="203af-117">Cela n'a aucun impact sur les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="203af-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="203af-118">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="203af-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-119">Sélectionnez SiteWH.</span><span class="sxs-lookup"><span data-stu-id="203af-119">Select SiteWH.</span></span> <span data-ttu-id="203af-120">Seul Site et entrepôt sera utilisé pour la démonstration.</span><span class="sxs-lookup"><span data-stu-id="203af-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="203af-121">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="203af-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-122">Les dimensions de suivi ne seront pas utilisées pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="203af-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="203af-123">Sélectionnez Aucun.</span><span class="sxs-lookup"><span data-stu-id="203af-123">Select None.</span></span>  
8. <span data-ttu-id="203af-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="203af-124">Click OK.</span></span>
9. <span data-ttu-id="203af-125">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="203af-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="203af-126">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="203af-126">Click Default order settings.</span></span>
11. <span data-ttu-id="203af-127">Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-128">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="203af-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="203af-129">Dans le champ Site de stock, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-130">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="203af-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="203af-131">Dans le champ Site de vente, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-132">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="203af-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="203af-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="203af-133">Close the page.</span></span>
15. <span data-ttu-id="203af-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="203af-134">Close the page.</span></span>
16. <span data-ttu-id="203af-135">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="203af-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="203af-136">Cliquez sur ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="203af-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="203af-137">Développez la section Gérer les coûts.</span><span class="sxs-lookup"><span data-stu-id="203af-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="203af-138">Dans le champ Groupe de coûts, taper une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="203af-139">Pour cet exemple, tapez M2.</span><span class="sxs-lookup"><span data-stu-id="203af-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="203af-140">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="203af-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="203af-141">Cliquez sur Prix de l'article.</span><span class="sxs-lookup"><span data-stu-id="203af-141">Click Item price.</span></span>
21. <span data-ttu-id="203af-142">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="203af-142">Click New.</span></span>
22. <span data-ttu-id="203af-143">Dans le champ Version, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-144">Pour cet exemple, sélectionnez 10, qui est le type d'évaluation des coûts pour un coût standard.</span><span class="sxs-lookup"><span data-stu-id="203af-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="203af-145">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="203af-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-146">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="203af-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="203af-147">Dans le champ Prix, saisissez un numéro.</span><span class="sxs-lookup"><span data-stu-id="203af-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="203af-148">Pour cet exemple, tapez 10.</span><span class="sxs-lookup"><span data-stu-id="203af-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="203af-149">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="203af-149">Click Save.</span></span>
26. <span data-ttu-id="203af-150">Cliquez sur Activer le ou les prix en attente.</span><span class="sxs-lookup"><span data-stu-id="203af-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="203af-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="203af-151">Close the page.</span></span>
28. <span data-ttu-id="203af-152">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="203af-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="203af-153">Créer le deuxième matériau</span><span class="sxs-lookup"><span data-stu-id="203af-153">Create the second material</span></span>
1. <span data-ttu-id="203af-154">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="203af-154">Click New.</span></span>
2. <span data-ttu-id="203af-155">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="203af-156">Pour cet exemple, tapez ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="203af-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="203af-157">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="203af-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-158">Sélectionnez STD.</span><span class="sxs-lookup"><span data-stu-id="203af-158">Select STD.</span></span> <span data-ttu-id="203af-159">STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="203af-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="203af-160">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-161">Par exemple, sélectionnez Audio.</span><span class="sxs-lookup"><span data-stu-id="203af-161">For example, select Audio.</span></span> <span data-ttu-id="203af-162">Cela n'a aucun impact sur les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="203af-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="203af-163">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="203af-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-164">Sélectionnez SiteWH.</span><span class="sxs-lookup"><span data-stu-id="203af-164">Select SiteWH.</span></span> <span data-ttu-id="203af-165">Seul Site et entrepôt sera utilisé pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="203af-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="203af-166">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="203af-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-167">Les dimensions de suivi ne seront pas utilisées pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="203af-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="203af-168">Sélectionnez Aucun.</span><span class="sxs-lookup"><span data-stu-id="203af-168">Select None.</span></span>  
7. <span data-ttu-id="203af-169">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="203af-169">Click OK.</span></span>
8. <span data-ttu-id="203af-170">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="203af-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="203af-171">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="203af-171">Click Default order settings.</span></span>
10. <span data-ttu-id="203af-172">Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-173">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="203af-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="203af-174">Dans le champ Site de stock, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-175">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="203af-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="203af-176">Dans le champ Site de vente, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-177">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="203af-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="203af-178">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="203af-178">Close the page.</span></span>
14. <span data-ttu-id="203af-179">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="203af-179">Close the page.</span></span>
15. <span data-ttu-id="203af-180">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="203af-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="203af-181">Cliquer sur ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="203af-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="203af-182">Développez la section Gérer les coûts.</span><span class="sxs-lookup"><span data-stu-id="203af-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="203af-183">Dans le champ Groupe de coûts, taper une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="203af-184">Pour cet exemple, tapez M2.</span><span class="sxs-lookup"><span data-stu-id="203af-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="203af-185">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="203af-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="203af-186">Cliquez sur Prix de l'article.</span><span class="sxs-lookup"><span data-stu-id="203af-186">Click Item price.</span></span>
20. <span data-ttu-id="203af-187">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="203af-187">Click New.</span></span>
21. <span data-ttu-id="203af-188">Dans le champ Version, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-189">Pour cet exemple, sélectionnez 10.</span><span class="sxs-lookup"><span data-stu-id="203af-189">For this example, select 10.</span></span> <span data-ttu-id="203af-190">Il s'agit du type d'évaluation des coûts pour un coût standard.</span><span class="sxs-lookup"><span data-stu-id="203af-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="203af-191">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="203af-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-192">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="203af-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="203af-193">Dans le champ Prix, saisissez un numéro.</span><span class="sxs-lookup"><span data-stu-id="203af-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="203af-194">Pour la démonstration, entrez 10.</span><span class="sxs-lookup"><span data-stu-id="203af-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="203af-195">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="203af-195">Click Save.</span></span>
25. <span data-ttu-id="203af-196">Cliquez sur Activer le ou les prix en attente.</span><span class="sxs-lookup"><span data-stu-id="203af-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="203af-197">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="203af-197">Close the page.</span></span>
27. <span data-ttu-id="203af-198">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="203af-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="203af-199">Créer le troisième matériau</span><span class="sxs-lookup"><span data-stu-id="203af-199">Create the third material</span></span>
1. <span data-ttu-id="203af-200">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="203af-200">Click New.</span></span>
2. <span data-ttu-id="203af-201">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="203af-202">Pour la démonstration, entrez ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="203af-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="203af-203">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="203af-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-204">Sélectionnez STD.</span><span class="sxs-lookup"><span data-stu-id="203af-204">Select STD.</span></span> <span data-ttu-id="203af-205">STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="203af-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="203af-206">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-207">Par exemple, sélectionnez Audio.</span><span class="sxs-lookup"><span data-stu-id="203af-207">For example, select Audio.</span></span> <span data-ttu-id="203af-208">Cela n'a aucun impact sur les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="203af-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="203af-209">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="203af-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-210">Sélectionnez SiteWH.</span><span class="sxs-lookup"><span data-stu-id="203af-210">Select SiteWH.</span></span> <span data-ttu-id="203af-211">Seul Site et entrepôt sera utilisé pour la démonstration.</span><span class="sxs-lookup"><span data-stu-id="203af-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="203af-212">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="203af-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-213">Les dimensions de suivi ne seront pas utilisées pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="203af-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="203af-214">Sélectionnez Aucun.</span><span class="sxs-lookup"><span data-stu-id="203af-214">Select None.</span></span>  
7. <span data-ttu-id="203af-215">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="203af-215">Click OK.</span></span>
8. <span data-ttu-id="203af-216">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="203af-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="203af-217">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="203af-217">Click Default order settings.</span></span>
10. <span data-ttu-id="203af-218">Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-219">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="203af-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="203af-220">Dans le champ Site de stock, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-221">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="203af-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="203af-222">Dans le champ Site de vente, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-223">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="203af-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="203af-224">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="203af-224">Close the page.</span></span>
14. <span data-ttu-id="203af-225">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="203af-225">Close the page.</span></span>
15. <span data-ttu-id="203af-226">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="203af-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="203af-227">Cliquez sur ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="203af-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="203af-228">Développez la section Gérer les coûts.</span><span class="sxs-lookup"><span data-stu-id="203af-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="203af-229">Dans le champ Groupe de coûts, taper une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="203af-230">Pour cet exemple, tapez M1.</span><span class="sxs-lookup"><span data-stu-id="203af-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="203af-231">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="203af-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="203af-232">Cliquez sur Prix de l'article.</span><span class="sxs-lookup"><span data-stu-id="203af-232">Click Item price.</span></span>
20. <span data-ttu-id="203af-233">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="203af-233">Click New.</span></span>
21. <span data-ttu-id="203af-234">Dans le champ Version, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="203af-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-235">Pour cet exemple, sélectionnez 10.</span><span class="sxs-lookup"><span data-stu-id="203af-235">For this example, select 10.</span></span> <span data-ttu-id="203af-236">Il s'agit du type d'évaluation des coûts pour un coût standard.</span><span class="sxs-lookup"><span data-stu-id="203af-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="203af-237">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="203af-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="203af-238">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="203af-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="203af-239">Dans le champ Prix, saisissez un numéro.</span><span class="sxs-lookup"><span data-stu-id="203af-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="203af-240">Pour cet exemple, tapez 10.</span><span class="sxs-lookup"><span data-stu-id="203af-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="203af-241">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="203af-241">Click Save.</span></span>
25. <span data-ttu-id="203af-242">Cliquez sur Activer le ou les prix en attente.</span><span class="sxs-lookup"><span data-stu-id="203af-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="203af-243">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="203af-243">Close the page.</span></span>
27. <span data-ttu-id="203af-244">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="203af-244">Close the page.</span></span>

