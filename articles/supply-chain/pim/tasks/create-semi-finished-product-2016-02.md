---
title: Créer un produit semi-fini (février 2016)
description: Cette tâche consiste à créer un produit semi-fini.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9caeae552471eed1cb1d8630f387ca31107fcece
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "362853"
---
# <a name="create-a-semi-finished-product-february-2016"></a><span data-ttu-id="e1f2d-103">Créer un produit semi-fini (février 2016)</span><span class="sxs-lookup"><span data-stu-id="e1f2d-103">Create a semi-finished product (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e1f2d-104">Cette tâche consiste à créer un produit semi-fini.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-104">This task focuses on creating a semi-finished product.</span></span> <span data-ttu-id="e1f2d-105">Il s'agit de la deuxième tâche de la série de calculs des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-105">It is the second task in the BOM calculation series.</span></span> <span data-ttu-id="e1f2d-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="e1f2d-107">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="e1f2d-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-108">Click New.</span></span>
3. <span data-ttu-id="e1f2d-109">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="e1f2d-110">Pour cet exemple, tapez BOM_2.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-110">For this example, type BOM_2.</span></span>  
4. <span data-ttu-id="e1f2d-111">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="e1f2d-112">Sélectionnez STD.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-112">Select STD.</span></span> <span data-ttu-id="e1f2d-113">STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="e1f2d-114">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="e1f2d-115">Par exemple, sélectionnez Audio.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-115">For example, select Audio.</span></span> <span data-ttu-id="e1f2d-116">Cela n'a aucun impact sur les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="e1f2d-117">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e1f2d-118">Sélectionnez SiteWH.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-118">Select SiteWH.</span></span> <span data-ttu-id="e1f2d-119">Seul Site et entrepôt sera utilisé pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-119">Only Site and Warehouse will be used for this example.</span></span>  
7. <span data-ttu-id="e1f2d-120">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e1f2d-121">Les dimensions de suivi ne seront pas utilisées pour cet exemple, sélectionnez Aucun.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="e1f2d-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-122">Click OK.</span></span>
9. <span data-ttu-id="e1f2d-123">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="e1f2d-124">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-124">Click Default order settings.</span></span>
11. <span data-ttu-id="e1f2d-125">Dans le champ Type de commande par défaut, sélectionnez Production.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="e1f2d-126">Comme c'est un produit semi-fini qui sera produit, sélectionnez Production.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-126">Because this is a semi-finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="e1f2d-127">Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="e1f2d-128">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-128">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="e1f2d-129">Dans le champ Site de stock, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="e1f2d-130">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="e1f2d-131">Dans le champ Site de vente, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="e1f2d-132">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="e1f2d-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-133">Close the page.</span></span>
16. <span data-ttu-id="e1f2d-134">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-134">On the Action Pane, click Manage costs.</span></span>
17. <span data-ttu-id="e1f2d-135">Cliquez sur Prix de l'article.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-135">Click Item price.</span></span>
18. <span data-ttu-id="e1f2d-136">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-136">Click New.</span></span>
19. <span data-ttu-id="e1f2d-137">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-137">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="e1f2d-138">Dans le champ Version, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-138">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="e1f2d-139">Pour cet exemple, sélectionnez Version 10.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-139">For this example, select Version 10.</span></span>  
21. <span data-ttu-id="e1f2d-140">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-140">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="e1f2d-141">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-141">For this example, select Site 1.</span></span>  
22. <span data-ttu-id="e1f2d-142">Définissez le prix sur 10</span><span class="sxs-lookup"><span data-stu-id="e1f2d-142">Set Price to '10'.</span></span>
    * <span data-ttu-id="e1f2d-143">Pour cet exemple, entrez un prix de revient de 10.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-143">For this example, type a cost price of 10.</span></span>  
23. <span data-ttu-id="e1f2d-144">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-144">Click Save.</span></span>
24. <span data-ttu-id="e1f2d-145">Cliquez sur Activer le ou les prix en attente.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-145">Click Activate pending price(s).</span></span>
25. <span data-ttu-id="e1f2d-146">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-146">Close the page.</span></span>
26. <span data-ttu-id="e1f2d-147">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-147">Close the page.</span></span>
27. <span data-ttu-id="e1f2d-148">Cliquez sur BOM_2 pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-148">Click BOM_2 to open it.</span></span>
28. <span data-ttu-id="e1f2d-149">Développez la section Gérer les coûts.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-149">Expand the Manage costs section.</span></span>
29. <span data-ttu-id="e1f2d-150">Dans le champ Groupe de coûts, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-150">In the Cost group field, enter or select a value.</span></span>
    * <span data-ttu-id="e1f2d-151">Pour cet exemple, sélectionnez Groupe de coûts M1.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-151">For this example, select Cost group M1.</span></span>  
30. <span data-ttu-id="e1f2d-152">Utilisez le raccourci pour enregistrer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-152">Use the shortcut for saving a record.</span></span>
31. <span data-ttu-id="e1f2d-153">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-153">Close the page.</span></span>

