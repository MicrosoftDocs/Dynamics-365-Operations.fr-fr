---
title: Créer un plan de matériaux pour des coproduits
description: Le responsable de production organise les besoins en matières pour les articles qui sont des coproduits de formules.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2958f1e5c2e8a0cfa9cc6312f688d3b11b8e013c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555998"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="f3deb-103">Créer un plan de matériaux pour des coproduits</span><span class="sxs-lookup"><span data-stu-id="f3deb-103">Create a material plan for co products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f3deb-104">Le responsable de production organise les besoins en matières pour les articles qui sont des coproduits de formules.</span><span class="sxs-lookup"><span data-stu-id="f3deb-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="f3deb-105">La société fictive de démonstration utilisée pour créer cette procédure est USP2.</span><span class="sxs-lookup"><span data-stu-id="f3deb-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="f3deb-106">Créer une demande pour un coproduit</span><span class="sxs-lookup"><span data-stu-id="f3deb-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="f3deb-107">Allez dans le Tableau de bord par défaut.</span><span class="sxs-lookup"><span data-stu-id="f3deb-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="f3deb-108">Cliquez sur Traitement et recherche de commande client.</span><span class="sxs-lookup"><span data-stu-id="f3deb-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="f3deb-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f3deb-109">Click New.</span></span>
4. <span data-ttu-id="f3deb-110">Cliquez sur Commande client.</span><span class="sxs-lookup"><span data-stu-id="f3deb-110">Click Sales order.</span></span>
5. <span data-ttu-id="f3deb-111">Tapez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="f3deb-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="f3deb-112">Exemple : US-001</span><span class="sxs-lookup"><span data-stu-id="f3deb-112">Example: US-001</span></span>  
6. <span data-ttu-id="f3deb-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f3deb-113">Click OK.</span></span>
7. <span data-ttu-id="f3deb-114">Tapez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="f3deb-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="f3deb-115">Exemple : P6003</span><span class="sxs-lookup"><span data-stu-id="f3deb-115">Example: P6003</span></span>  
8. <span data-ttu-id="f3deb-116">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="f3deb-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="f3deb-117">Exemple : 50000</span><span class="sxs-lookup"><span data-stu-id="f3deb-117">Example: 50000</span></span>  
9. <span data-ttu-id="f3deb-118">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f3deb-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="f3deb-119">Créer un plan matières pour des coproduits</span><span class="sxs-lookup"><span data-stu-id="f3deb-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="f3deb-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f3deb-120">Close the page.</span></span>
2. <span data-ttu-id="f3deb-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f3deb-121">Close the page.</span></span>
3. <span data-ttu-id="f3deb-122">Cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="f3deb-122">Click Master planning.</span></span>
4. <span data-ttu-id="f3deb-123">Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="f3deb-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="f3deb-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f3deb-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f3deb-125">Exemple : Programme</span><span class="sxs-lookup"><span data-stu-id="f3deb-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="f3deb-126">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="f3deb-126">Click Run.</span></span>
7. <span data-ttu-id="f3deb-127">Développez ou réduisez la section Enregistrements à inclure.</span><span class="sxs-lookup"><span data-stu-id="f3deb-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="f3deb-128">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="f3deb-128">Click Filter.</span></span>
9. <span data-ttu-id="f3deb-129">Dans la liste, sélectionnez la ligne pour Champ = Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="f3deb-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="f3deb-130">Tapez une valeur dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="f3deb-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="f3deb-131">Exemple : P6003</span><span class="sxs-lookup"><span data-stu-id="f3deb-131">Example: P6003</span></span>  
11. <span data-ttu-id="f3deb-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f3deb-132">Click OK.</span></span>
12. <span data-ttu-id="f3deb-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f3deb-133">Click OK.</span></span>
13. <span data-ttu-id="f3deb-134">Cliquez sur Ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="f3deb-134">Click Planned orders.</span></span>
14. <span data-ttu-id="f3deb-135">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="f3deb-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="f3deb-136">Par exemple, filtrez su le champ Numéro d'article avec une valeur de « P6000 ».</span><span class="sxs-lookup"><span data-stu-id="f3deb-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="f3deb-137">Filtrez par élément de formule ayant comme coproduit de l'article pour lequel vous avez créé une commande client.</span><span class="sxs-lookup"><span data-stu-id="f3deb-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="f3deb-138">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f3deb-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f3deb-139">Sélectionnez n'importe quelle ligne renvoyée par le filtre.</span><span class="sxs-lookup"><span data-stu-id="f3deb-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="f3deb-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f3deb-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="f3deb-141">Développez ou réduisez la section Origine des besoins.</span><span class="sxs-lookup"><span data-stu-id="f3deb-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="f3deb-142">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f3deb-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f3deb-143">L'ordre prévisionnel est chevillé à la commande client du coproduit.</span><span class="sxs-lookup"><span data-stu-id="f3deb-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="f3deb-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f3deb-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="f3deb-145">Créer une demande pour un coproduit</span><span class="sxs-lookup"><span data-stu-id="f3deb-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="f3deb-146">Allez dans le Tableau de bord par défaut.</span><span class="sxs-lookup"><span data-stu-id="f3deb-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="f3deb-147">Cliquez sur Traitement et recherche de commande client.</span><span class="sxs-lookup"><span data-stu-id="f3deb-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="f3deb-148">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f3deb-148">Click New.</span></span>
4. <span data-ttu-id="f3deb-149">Cliquez sur Commande client.</span><span class="sxs-lookup"><span data-stu-id="f3deb-149">Click Sales order.</span></span>
5. <span data-ttu-id="f3deb-150">Tapez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="f3deb-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="f3deb-151">Exemple : US-001</span><span class="sxs-lookup"><span data-stu-id="f3deb-151">Example: US-001</span></span>  
6. <span data-ttu-id="f3deb-152">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f3deb-152">Click OK.</span></span>
7. <span data-ttu-id="f3deb-153">Tapez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="f3deb-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="f3deb-154">Exemple : P6003</span><span class="sxs-lookup"><span data-stu-id="f3deb-154">Example: P6003</span></span>  
8. <span data-ttu-id="f3deb-155">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="f3deb-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="f3deb-156">Exemple : 50000</span><span class="sxs-lookup"><span data-stu-id="f3deb-156">Example: 50000</span></span>  
9. <span data-ttu-id="f3deb-157">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f3deb-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="f3deb-158">Créer un plan matières pour des coproduits</span><span class="sxs-lookup"><span data-stu-id="f3deb-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="f3deb-159">Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="f3deb-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="f3deb-160">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f3deb-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f3deb-161">Exemple : Programme</span><span class="sxs-lookup"><span data-stu-id="f3deb-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="f3deb-162">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="f3deb-162">Click Run.</span></span>
4. <span data-ttu-id="f3deb-163">Développez ou réduisez la section Enregistrements à inclure.</span><span class="sxs-lookup"><span data-stu-id="f3deb-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="f3deb-164">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="f3deb-164">Click Filter.</span></span>
6. <span data-ttu-id="f3deb-165">Dans la liste, sélectionnez la ligne pour Champ = Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="f3deb-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="f3deb-166">Tapez une valeur dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="f3deb-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="f3deb-167">Exemple : P6003</span><span class="sxs-lookup"><span data-stu-id="f3deb-167">Example: P6003</span></span>  
8. <span data-ttu-id="f3deb-168">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f3deb-168">Click OK.</span></span>
9. <span data-ttu-id="f3deb-169">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f3deb-169">Click OK.</span></span>
10. <span data-ttu-id="f3deb-170">Cliquez sur Ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="f3deb-170">Click Planned orders.</span></span>
11. <span data-ttu-id="f3deb-171">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="f3deb-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="f3deb-172">Par exemple, filtrez su le champ Numéro d'article avec une valeur de « P6000 ».</span><span class="sxs-lookup"><span data-stu-id="f3deb-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="f3deb-173">Filtrez par élément de formule ayant comme coproduit de l'article pour lequel vous avez créé une commande client.</span><span class="sxs-lookup"><span data-stu-id="f3deb-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="f3deb-174">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f3deb-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f3deb-175">Sélectionnez n'importe quelle ligne renvoyée par le filtre.</span><span class="sxs-lookup"><span data-stu-id="f3deb-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="f3deb-176">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f3deb-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="f3deb-177">Développez ou réduisez la section Origine des besoins.</span><span class="sxs-lookup"><span data-stu-id="f3deb-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="f3deb-178">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f3deb-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f3deb-179">L'ordre prévisionnel est chevillé à la commande client du coproduit.</span><span class="sxs-lookup"><span data-stu-id="f3deb-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="f3deb-180">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f3deb-180">Close the page.</span></span>
17. <span data-ttu-id="f3deb-181">Cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="f3deb-181">Click Master planning.</span></span>
18. <span data-ttu-id="f3deb-182">Accédez à Planification > Paramétrage > Paramètres de planification.</span><span class="sxs-lookup"><span data-stu-id="f3deb-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="f3deb-183">Sélectionnez Non dans le champ Désactiver tous les processus de planification.</span><span class="sxs-lookup"><span data-stu-id="f3deb-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="f3deb-184">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f3deb-184">Close the page.</span></span>

