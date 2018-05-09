--- 
title: "Créer des nomenclatures (février 2016 uniquement)"
description: "Cette tâche consiste à créer la structure d'une nomenclature pour un produit fini et un produit semi-fini."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 6c5473a0786ba0348701e8e106de46f811571f07
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="create-boms-february-2016-only"></a><span data-ttu-id="859d2-103">Créer des nomenclatures (février 2016 uniquement)</span><span class="sxs-lookup"><span data-stu-id="859d2-103">Create BOMs (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="859d2-104">Cette tâche consiste à créer la structure d'une nomenclature pour un produit fini et un produit semi-fini.</span><span class="sxs-lookup"><span data-stu-id="859d2-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="859d2-105">Il s'agit de la quatrième tâche de la série de calculs des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="859d2-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="859d2-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="859d2-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="859d2-107">Créer une nomenclature pour un produit semi-fini</span><span class="sxs-lookup"><span data-stu-id="859d2-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="859d2-108">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="859d2-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="859d2-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="859d2-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="859d2-110">Sélectionnez le numéro d'article BOM_2.</span><span class="sxs-lookup"><span data-stu-id="859d2-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="859d2-111">Cliquez sur Ingénieur dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="859d2-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="859d2-112">Cliquez sur Versions de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="859d2-112">Click BOM versions.</span></span>
5. <span data-ttu-id="859d2-113">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="859d2-113">Click New.</span></span>
6. <span data-ttu-id="859d2-114">Cliquez sur Nomenclature et version de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="859d2-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="859d2-115">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="859d2-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="859d2-116">Entrez BOM_2, par exemple.</span><span class="sxs-lookup"><span data-stu-id="859d2-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="859d2-117">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="859d2-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="859d2-118">Pour cet exemple, entrez ou sélectionnez le site 1.</span><span class="sxs-lookup"><span data-stu-id="859d2-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="859d2-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="859d2-119">Click OK.</span></span>
10. <span data-ttu-id="859d2-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="859d2-120">Click New.</span></span>
11. <span data-ttu-id="859d2-121">Tapez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="859d2-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="859d2-122">Pour cet exemple, tapez ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="859d2-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="859d2-123">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="859d2-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="859d2-124">Pour cet exemple, entrez ou sélectionnez 11</span><span class="sxs-lookup"><span data-stu-id="859d2-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="859d2-125">Cliquez sur En-tête.</span><span class="sxs-lookup"><span data-stu-id="859d2-125">Click Header.</span></span>
14. <span data-ttu-id="859d2-126">Cliquez sur Approbation d'approuver des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="859d2-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="859d2-127">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="859d2-127">Click OK.</span></span>
16. <span data-ttu-id="859d2-128">Cliquez sur Approuver.</span><span class="sxs-lookup"><span data-stu-id="859d2-128">Click Approve.</span></span>
    * <span data-ttu-id="859d2-129">Le bouton Approuver se trouve dans la barre d'outils dans la section de versions de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="859d2-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="859d2-130">S'il est invisible, cliquez sur En-tête dans le coin supérieur droit de la page Nomenclatures afin de le faire apparaître.</span><span class="sxs-lookup"><span data-stu-id="859d2-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="859d2-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="859d2-131">Click OK.</span></span>
18. <span data-ttu-id="859d2-132">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="859d2-132">Click Activate.</span></span>
19. <span data-ttu-id="859d2-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="859d2-133">Close the page.</span></span>
20. <span data-ttu-id="859d2-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="859d2-134">Close the page.</span></span>
21. <span data-ttu-id="859d2-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="859d2-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="859d2-136">Créer une nomenclature pour un produit fini</span><span class="sxs-lookup"><span data-stu-id="859d2-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="859d2-137">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="859d2-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="859d2-138">Sélectionnez le numéro d'article BOM_1.</span><span class="sxs-lookup"><span data-stu-id="859d2-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="859d2-139">Cliquez sur Ingénieur dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="859d2-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="859d2-140">Cliquez sur Versions de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="859d2-140">Click BOM versions.</span></span>
4. <span data-ttu-id="859d2-141">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="859d2-141">Click New.</span></span>
5. <span data-ttu-id="859d2-142">Cliquez sur Nomenclature et version de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="859d2-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="859d2-143">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="859d2-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="859d2-144">Entrez BOM_1, par exemple.</span><span class="sxs-lookup"><span data-stu-id="859d2-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="859d2-145">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="859d2-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="859d2-146">Pour cet exemple, entrez ou sélectionnez le site 1.</span><span class="sxs-lookup"><span data-stu-id="859d2-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="859d2-147">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="859d2-147">Click OK.</span></span>
9. <span data-ttu-id="859d2-148">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="859d2-148">Click New.</span></span>
10. <span data-ttu-id="859d2-149">Tapez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="859d2-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="859d2-150">Pour cet exemple, tapez ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="859d2-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="859d2-151">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="859d2-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="859d2-152">Pour cet exemple, sélectionnez 11.</span><span class="sxs-lookup"><span data-stu-id="859d2-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="859d2-153">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="859d2-153">Click New.</span></span>
13. <span data-ttu-id="859d2-154">Tapez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="859d2-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="859d2-155">Pour cet exemple, tapez ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="859d2-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="859d2-156">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="859d2-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="859d2-157">Pour cet exemple, entrez ou sélectionnez 11</span><span class="sxs-lookup"><span data-stu-id="859d2-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="859d2-158">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="859d2-158">Click New.</span></span>
16. <span data-ttu-id="859d2-159">Tapez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="859d2-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="859d2-160">Pour cet exemple, tapez BOM_2.</span><span class="sxs-lookup"><span data-stu-id="859d2-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="859d2-161">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="859d2-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="859d2-162">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="859d2-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="859d2-163">Pour cet exemple, entrez ou sélectionnez l'entrepôt 11.</span><span class="sxs-lookup"><span data-stu-id="859d2-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="859d2-164">Cliquez sur En-tête.</span><span class="sxs-lookup"><span data-stu-id="859d2-164">Click Header.</span></span>
20. <span data-ttu-id="859d2-165">Cliquez sur Approbation d'approuver des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="859d2-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="859d2-166">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="859d2-166">Click OK.</span></span>
22. <span data-ttu-id="859d2-167">Cliquez sur Approuver.</span><span class="sxs-lookup"><span data-stu-id="859d2-167">Click Approve.</span></span>
    * <span data-ttu-id="859d2-168">Le bouton Approuver se trouve dans la barre d'outils dans la section de versions de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="859d2-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="859d2-169">S'il est invisible, cliquez sur En-tête dans le coin supérieur droit de la page Nomenclatures afin de le faire apparaître.</span><span class="sxs-lookup"><span data-stu-id="859d2-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="859d2-170">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="859d2-170">Click OK.</span></span>
24. <span data-ttu-id="859d2-171">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="859d2-171">Click Activate.</span></span>
25. <span data-ttu-id="859d2-172">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="859d2-172">Close the page.</span></span>
26. <span data-ttu-id="859d2-173">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="859d2-173">Close the page.</span></span>
27. <span data-ttu-id="859d2-174">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="859d2-174">Close the page.</span></span>


