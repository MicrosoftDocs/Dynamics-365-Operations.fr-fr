---
title: Créer et affecter une stratégie de comportement des coûts à une unité de contrôle des coûts
description: Le comportement de coûts est la classification des coûts comme fixe ou variable.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e923bd4e8f89aa9398b6327fe28998f845218d4
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144402"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a><span data-ttu-id="4039e-103">Créer et affecter une stratégie de comportement des coûts à une unité de contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="4039e-103">Create and assign a cost behavior policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4039e-104">Le comportement de coûts est la classification des coûts comme fixe ou variable.</span><span class="sxs-lookup"><span data-stu-id="4039e-104">Cost behavior is the classification of costs as either fixed or variable.</span></span> <span data-ttu-id="4039e-105">Une stratégie et les règles correspondantes doivent être affectées à une unité de contrôle des coûts pour que la stratégie prenne effet.</span><span class="sxs-lookup"><span data-stu-id="4039e-105">A policy and the corresponding rules have to be assigned to a cost control unit for the policy to become effective.</span></span> <span data-ttu-id="4039e-106">Utilisez cette procédure pour créer une stratégie et l'affecter à une unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="4039e-106">Use this procedure to create a policy and then assign the policy to a cost control unit.</span></span>


## <a name="create-a-cost-behavior-hierarchy"></a><span data-ttu-id="4039e-107">Créer une hiérarchie de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="4039e-107">Create a cost behavior hierarchy</span></span>
1. <span data-ttu-id="4039e-108">Accédez à Contrôle de gestion > Dimensions > Hiérarchies des dimensions.</span><span class="sxs-lookup"><span data-stu-id="4039e-108">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="4039e-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4039e-109">Click New.</span></span>
3. <span data-ttu-id="4039e-110">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="4039e-110">Click Create.</span></span>
4. <span data-ttu-id="4039e-111">Dans le champ Nom de la hiérarchie des dimensions, tapez « Hiérarchie de comportement de coûts ».</span><span class="sxs-lookup"><span data-stu-id="4039e-111">In the Dimension hierarchy name field, type 'Cost behavior hierarchy'.</span></span>
5. <span data-ttu-id="4039e-112">Dans le champ Dimension, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-112">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="4039e-113">Sélectionnez Éléments de coût.</span><span class="sxs-lookup"><span data-stu-id="4039e-113">Select Cost elements.</span></span>  
6. <span data-ttu-id="4039e-114">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4039e-114">Click Save.</span></span>
7. <span data-ttu-id="4039e-115">Cliquez sur Afficher la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="4039e-115">Click View hierarchy.</span></span>
8. <span data-ttu-id="4039e-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4039e-116">Click New.</span></span>
9. <span data-ttu-id="4039e-117">Dans le champ Nom du nœud, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-117">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="4039e-118">Entrez le coût fixe.</span><span class="sxs-lookup"><span data-stu-id="4039e-118">Enter Fixed cost.</span></span>  
10. <span data-ttu-id="4039e-119">Dans l'arborescence, sélectionnez « Hiérarchie de comportement de coûts ».</span><span class="sxs-lookup"><span data-stu-id="4039e-119">In the tree, select 'Cost behavior hierarchy'.</span></span>
11. <span data-ttu-id="4039e-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4039e-120">Click New.</span></span>
12. <span data-ttu-id="4039e-121">Dans le champ Nom du nœud, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-121">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="4039e-122">Entrez le coût variable.</span><span class="sxs-lookup"><span data-stu-id="4039e-122">Enter Variable cost.</span></span>  
13. <span data-ttu-id="4039e-123">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4039e-123">Click Save.</span></span>
14. <span data-ttu-id="4039e-124">Dans l'arborescence, sélectionnez « Hiérarchie de comportement de coûts\Coût fixe ».</span><span class="sxs-lookup"><span data-stu-id="4039e-124">In the tree, select 'Cost behavior hierarchy\Fixed cost'.</span></span>
15. <span data-ttu-id="4039e-125">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4039e-125">Click New.</span></span>
16. <span data-ttu-id="4039e-126">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4039e-126">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="4039e-127">Dans le champ Membre de la dimension de départ, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-127">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="4039e-128">La plage des membres de dimension peut contenir des écarts, mais les membres ne peuvent pas se chevaucher.</span><span class="sxs-lookup"><span data-stu-id="4039e-128">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
18. <span data-ttu-id="4039e-129">Dans le champ Membre de la dimension de fin, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-129">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="4039e-130">La plage des membres de dimension peut contenir des écarts, mais les membres ne peuvent pas se chevaucher.</span><span class="sxs-lookup"><span data-stu-id="4039e-130">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
19. <span data-ttu-id="4039e-131">Dans l'arborescence, sélectionnez « Hiérarchie de comportement de coûts\Coût variable ».</span><span class="sxs-lookup"><span data-stu-id="4039e-131">In the tree, select 'Cost behavior hierarchy\Variable cost'.</span></span>
20. <span data-ttu-id="4039e-132">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4039e-132">Click New.</span></span>
21. <span data-ttu-id="4039e-133">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4039e-133">In the list, mark the selected row.</span></span>
22. <span data-ttu-id="4039e-134">Dans le champ Membre de la dimension de départ, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-134">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="4039e-135">La plage des membres de dimension peut contenir des écarts, mais les membres ne peuvent pas se chevaucher.</span><span class="sxs-lookup"><span data-stu-id="4039e-135">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
23. <span data-ttu-id="4039e-136">Dans le champ Membre de la dimension de fin, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-136">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="4039e-137">La plage des membres de dimension peut contenir des écarts, mais les membres ne peuvent pas se chevaucher.</span><span class="sxs-lookup"><span data-stu-id="4039e-137">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
24. <span data-ttu-id="4039e-138">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4039e-138">Click Save.</span></span>

## <a name="create-the-policy-and-rules"></a><span data-ttu-id="4039e-139">Créer la stratégie et les règles</span><span class="sxs-lookup"><span data-stu-id="4039e-139">Create the policy and rules</span></span>
1. <span data-ttu-id="4039e-140">Accédez à Contrôle de gestion > Stratégies > Stratégies de comportement de coûts.</span><span class="sxs-lookup"><span data-stu-id="4039e-140">Go to Cost accounting > Policies > Cost behavior policies.</span></span>
2. <span data-ttu-id="4039e-141">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4039e-141">Click New.</span></span>
3. <span data-ttu-id="4039e-142">Dans le champ Nom de la stratégie, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-142">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="4039e-143">Dans le champ Hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-143">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="4039e-144">Sélectionnez la hiérarchie de stratégie que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="4039e-144">Select the policy hierarchy that you just created.</span></span>  
5. <span data-ttu-id="4039e-145">Dans le champ Hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-145">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="4039e-146">Sélectionnez Organisation.</span><span class="sxs-lookup"><span data-stu-id="4039e-146">Select Organization.</span></span>  
6. <span data-ttu-id="4039e-147">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4039e-147">Click Save.</span></span>
7. <span data-ttu-id="4039e-148">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4039e-148">Click New.</span></span>
8. <span data-ttu-id="4039e-149">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4039e-149">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="4039e-150">Dans le champ Nœud de hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-150">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="4039e-151">Développez la hiérarchie pour sélectionner Coût variable.</span><span class="sxs-lookup"><span data-stu-id="4039e-151">Expand the hierarchy to select Variable cost.</span></span>  
10. <span data-ttu-id="4039e-152">Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-152">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="4039e-153">Par défaut, le pourcentage variable est 100 %.</span><span class="sxs-lookup"><span data-stu-id="4039e-153">By default, the variable percentage is 100 percent.</span></span>  
11. <span data-ttu-id="4039e-154">Cliquez sur Affectations de stratégie pour l'unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="4039e-154">Click Policy assignments for cost control unit.</span></span>
12. <span data-ttu-id="4039e-155">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4039e-155">Click New.</span></span>
13. <span data-ttu-id="4039e-156">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4039e-156">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="4039e-157">Dans le champ Valide à partir de la date comptable, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="4039e-157">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="4039e-158">Les règles ont une date d'effet, et un utilisateur ou le système peut faire expirer une règle si une version plus récente est créée.</span><span class="sxs-lookup"><span data-stu-id="4039e-158">The rules are date-effective, and a user or the system can expire a rule if a newer version is created.</span></span>  
15. <span data-ttu-id="4039e-159">Dans le champ Unité de contrôle des coûts, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4039e-159">In the Cost control unit field, enter or select a value.</span></span>
16. <span data-ttu-id="4039e-160">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4039e-160">Click Save.</span></span>

