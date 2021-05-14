---
title: Créer un plan de matériaux pour des coproduits
description: Le responsable de production organise les besoins en matières pour les articles qui sont des coproduits de formules.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b51e4b4d00da2babb5128d8c4c22139b0c1853d4
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920727"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="d5800-103">Créer un plan de matériaux pour des coproduits</span><span class="sxs-lookup"><span data-stu-id="d5800-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d5800-104">Le responsable de production organise les besoins en matières pour les articles qui sont des coproduits de formules.</span><span class="sxs-lookup"><span data-stu-id="d5800-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="d5800-105">La société fictive de démonstration utilisée pour créer cette procédure est USP2.</span><span class="sxs-lookup"><span data-stu-id="d5800-105">The demo data company used to create this procedure is USP2.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="d5800-106">Créer une demande pour un coproduit</span><span class="sxs-lookup"><span data-stu-id="d5800-106">Create requirement for a co-product</span></span>

1. <span data-ttu-id="d5800-107">Accédez à **Ventes et marketing \> Espaces de travail \> Traitement et recherche de commande client**.</span><span class="sxs-lookup"><span data-stu-id="d5800-107">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="d5800-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d5800-108">Select **New**.</span></span>
1. <span data-ttu-id="d5800-109">Sélectionnez **Commandes client**.</span><span class="sxs-lookup"><span data-stu-id="d5800-109">Select **Sales order**.</span></span>
1. <span data-ttu-id="d5800-110">Dans le champ **Compte client**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d5800-110">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="d5800-111">Exemple : US-001</span><span class="sxs-lookup"><span data-stu-id="d5800-111">Example: US-001</span></span>  
1. <span data-ttu-id="d5800-112">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5800-112">Select **OK**.</span></span>
1. <span data-ttu-id="d5800-113">Dans le champ **Numéro d’article**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d5800-113">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="d5800-114">Exemple : P6003</span><span class="sxs-lookup"><span data-stu-id="d5800-114">Example: P6003</span></span>  
1. <span data-ttu-id="d5800-115">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="d5800-115">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="d5800-116">Exemple : 50000</span><span class="sxs-lookup"><span data-stu-id="d5800-116">Example: 50000</span></span>  
1. <span data-ttu-id="d5800-117">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d5800-117">Select **Save**.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="d5800-118">Créer un plan matières pour des coproduits</span><span class="sxs-lookup"><span data-stu-id="d5800-118">Create a material plan for co-products</span></span>

1. <span data-ttu-id="d5800-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d5800-119">Close the page.</span></span>
1. <span data-ttu-id="d5800-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d5800-120">Close the page.</span></span>
1. <span data-ttu-id="d5800-121">Sélectionnez **Planification**.</span><span class="sxs-lookup"><span data-stu-id="d5800-121">Select **Master planning**.</span></span>
1. <span data-ttu-id="d5800-122">Dans le champ **Régime**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="d5800-122">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
1. <span data-ttu-id="d5800-123">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5800-123">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="d5800-124">Exemple : Programme</span><span class="sxs-lookup"><span data-stu-id="d5800-124">Example: MasterPlan</span></span>  
1. <span data-ttu-id="d5800-125">Sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d5800-125">Select **Run**.</span></span>
1. <span data-ttu-id="d5800-126">Développez ou réduisez la section **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="d5800-126">Expand or collapse the **Records to include** section.</span></span>
1. <span data-ttu-id="d5800-127">Sélectionnez **Filtrer**.</span><span class="sxs-lookup"><span data-stu-id="d5800-127">Select **Filter**.</span></span>
1. <span data-ttu-id="d5800-128">Dans la liste, sélectionnez la ligne pour **Champ** = *Numéro d’article*.</span><span class="sxs-lookup"><span data-stu-id="d5800-128">In the list, select the row for **Field** = *Item number*.</span></span>
1. <span data-ttu-id="d5800-129">Tapez une valeur dans le champ **Critères**.</span><span class="sxs-lookup"><span data-stu-id="d5800-129">In the **Criteria** field, type a value.</span></span>
    * <span data-ttu-id="d5800-130">Exemple : P6003</span><span class="sxs-lookup"><span data-stu-id="d5800-130">Example: P6003</span></span>  
1. <span data-ttu-id="d5800-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5800-131">Select **OK**.</span></span>
1. <span data-ttu-id="d5800-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5800-132">Select **OK**.</span></span>
1. <span data-ttu-id="d5800-133">Sélectionnez **Ordres prévisionnels**.</span><span class="sxs-lookup"><span data-stu-id="d5800-133">Select **Planned orders**.</span></span>
1. <span data-ttu-id="d5800-134">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="d5800-134">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d5800-135">Par exemple, filtrez su le champ **Numéro d’article** avec une valeur de « P6000 ».</span><span class="sxs-lookup"><span data-stu-id="d5800-135">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="d5800-136">Filtrez par élément de formule ayant comme coproduit de l’article pour lequel vous avez créé une commande client.</span><span class="sxs-lookup"><span data-stu-id="d5800-136">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
1. <span data-ttu-id="d5800-137">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5800-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d5800-138">Sélectionnez n’importe quelle ligne renvoyée par le filtre.</span><span class="sxs-lookup"><span data-stu-id="d5800-138">Select any of the rows returned by the filter.</span></span>  
1. <span data-ttu-id="d5800-139">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5800-139">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="d5800-140">Développez la section **Origine des besoins**.</span><span class="sxs-lookup"><span data-stu-id="d5800-140">Expand the **Pegging** section.</span></span>
1. <span data-ttu-id="d5800-141">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5800-141">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="d5800-142">L’ordre prévisionnel est chevillé à la commande client du coproduit.</span><span class="sxs-lookup"><span data-stu-id="d5800-142">The planned order is pegged to the sales order for the co-product.</span></span>  
1. <span data-ttu-id="d5800-143">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d5800-143">Close the page.</span></span>

## <a name="create-a-second-requirement-for-a-co-product"></a><span data-ttu-id="d5800-144">Créer une deuxième demande pour un coproduit</span><span class="sxs-lookup"><span data-stu-id="d5800-144">Create a second requirement for a co-product</span></span>

1. <span data-ttu-id="d5800-145">Accédez à **Ventes et marketing \> Espaces de travail \> Traitement et recherche de commande client**.</span><span class="sxs-lookup"><span data-stu-id="d5800-145">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="d5800-146">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d5800-146">Select **New**.</span></span>
1. <span data-ttu-id="d5800-147">Sélectionnez **Commandes client**.</span><span class="sxs-lookup"><span data-stu-id="d5800-147">Select **Sales order**.</span></span>
1. <span data-ttu-id="d5800-148">Dans le champ **Compte client**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d5800-148">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="d5800-149">Exemple : US-001</span><span class="sxs-lookup"><span data-stu-id="d5800-149">Example: US-001</span></span>  
1. <span data-ttu-id="d5800-150">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5800-150">Select **OK**.</span></span>
1. <span data-ttu-id="d5800-151">Dans le champ **Numéro d’article**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d5800-151">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="d5800-152">Exemple : P6003</span><span class="sxs-lookup"><span data-stu-id="d5800-152">Example: P6003</span></span>  
1. <span data-ttu-id="d5800-153">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="d5800-153">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="d5800-154">Exemple : 50000</span><span class="sxs-lookup"><span data-stu-id="d5800-154">Example: 50000</span></span>  
1. <span data-ttu-id="d5800-155">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d5800-155">Select **Save**.</span></span>

## <a name="create-a-second-material-plan-for-co-products"></a><span data-ttu-id="d5800-156">Créer un deuxième plan matières pour des co-produits</span><span class="sxs-lookup"><span data-stu-id="d5800-156">Create a second material plan for co-products</span></span>

1. <span data-ttu-id="d5800-157">Dans le champ **Régime**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="d5800-157">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="d5800-158">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5800-158">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="d5800-159">Exemple : Programme</span><span class="sxs-lookup"><span data-stu-id="d5800-159">Example: MasterPlan</span></span>  
3. <span data-ttu-id="d5800-160">Sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d5800-160">Select **Run**.</span></span>
4. <span data-ttu-id="d5800-161">Développez ou réduisez la section **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="d5800-161">Expand or collapse the **Records to include** section.</span></span>
5. <span data-ttu-id="d5800-162">Sélectionnez **Filtrer**.</span><span class="sxs-lookup"><span data-stu-id="d5800-162">Select **Filter**.</span></span>
6. <span data-ttu-id="d5800-163">Dans la liste, sélectionnez la ligne pour **Champ** = *Numéro d’article*.</span><span class="sxs-lookup"><span data-stu-id="d5800-163">In the list, select the row for **Field** = *Item number*.</span></span>
7. <span data-ttu-id="d5800-164">Tapez une valeur dans le champ *Critères*.</span><span class="sxs-lookup"><span data-stu-id="d5800-164">In the *Criteria* field, type a value.</span></span>
    * <span data-ttu-id="d5800-165">Exemple : P6003</span><span class="sxs-lookup"><span data-stu-id="d5800-165">Example: P6003</span></span>  
8. <span data-ttu-id="d5800-166">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5800-166">Select **OK**.</span></span>
9. <span data-ttu-id="d5800-167">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5800-167">Select **OK**.</span></span>
10. <span data-ttu-id="d5800-168">Sélectionnez **Ordres prévisionnels**.</span><span class="sxs-lookup"><span data-stu-id="d5800-168">Select **Planned orders**.</span></span>
11. <span data-ttu-id="d5800-169">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="d5800-169">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d5800-170">Par exemple, filtrez su le champ **Numéro d’article** avec une valeur de « P6000 ».</span><span class="sxs-lookup"><span data-stu-id="d5800-170">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="d5800-171">Filtrez par élément de formule ayant comme coproduit de l’article pour lequel vous avez créé une commande client.</span><span class="sxs-lookup"><span data-stu-id="d5800-171">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="d5800-172">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5800-172">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d5800-173">Sélectionnez n’importe quelle ligne renvoyée par le filtre.</span><span class="sxs-lookup"><span data-stu-id="d5800-173">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="d5800-174">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5800-174">In the list, select the link in the selected row.</span></span>
14. <span data-ttu-id="d5800-175">Développez ou réduisez la section **Origine des besoins**.</span><span class="sxs-lookup"><span data-stu-id="d5800-175">Expand or collapse the **Pegging** section.</span></span>
15. <span data-ttu-id="d5800-176">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5800-176">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="d5800-177">L’ordre prévisionnel est chevillé à la commande client du coproduit.</span><span class="sxs-lookup"><span data-stu-id="d5800-177">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="d5800-178">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d5800-178">Close the page.</span></span>
17. <span data-ttu-id="d5800-179">Sélectionnez **Planification**.</span><span class="sxs-lookup"><span data-stu-id="d5800-179">Select **Master planning**.</span></span>
18. <span data-ttu-id="d5800-180">Accédez à **Planification \> Paramétrage \> Paramètres de planification**.</span><span class="sxs-lookup"><span data-stu-id="d5800-180">Go to **Master planning \> Setup \> Master planning parameters**.</span></span>
19. <span data-ttu-id="d5800-181">Sélectionnez *Non* dans le champ **Désactiver tous les processus de planification**.</span><span class="sxs-lookup"><span data-stu-id="d5800-181">Select *No* in the **Disable all planning processes** field.</span></span>
20. <span data-ttu-id="d5800-182">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d5800-182">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]