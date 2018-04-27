--- 
title: "Paramétrer les grilles de rémunération"
description: "Les grilles de rémunération permettent de définir et de tenir à jour les structures de paie pour les régimes de rémunération fixe."
author: kherr75
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d507224004bdf319f9bf13ba07ed07ef29cc85dc
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-compensation-grids"></a><span data-ttu-id="9bcf7-103">Paramétrer les grilles de rémunération</span><span class="sxs-lookup"><span data-stu-id="9bcf7-103">Set up compensation grids</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9bcf7-104">Les grilles de rémunération permettent de définir et de tenir à jour les structures de paie pour les régimes de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-104">Compensation grids are used to define and maintain the pay structures for fixed compensation plans.</span></span> <span data-ttu-id="9bcf7-105">Les grilles de rémunération peuvent être partagées entre plusieurs régimes ou être copiées lors de la création d'un régime de rémunération.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-105">Compensation grids can be shared between multiple plans or copied when creating a new compensation plan.</span></span>  <span data-ttu-id="9bcf7-106">Avant de créer une grille de rémunération, vous devez configurer les niveaux et les points de référence.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-106">Before creating a compensation grid, Levels and Reference points must be set up.</span></span> <span data-ttu-id="9bcf7-107">Cet exemple crée un type de catégorie de grille de rémunération en utilisant des données de démonstration pour les niveaux et les points de référence.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-107">This example will create a new Grade type of compensation grid using demo data for the Levels and Reference points.</span></span> <span data-ttu-id="9bcf7-108">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-information-about-the-compensation-grid"></a><span data-ttu-id="9bcf7-109">Paramétrer les informations sur la grille de rémunération</span><span class="sxs-lookup"><span data-stu-id="9bcf7-109">Set up information about the compensation grid</span></span>
1. <span data-ttu-id="9bcf7-110">Accédez à Ressources humaines > Rémunération > Rémunération fixe > Grilles de rémunération.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-110">Go to Human resources > Compensation > Fixed compensation > Compensation grids.</span></span>
2. <span data-ttu-id="9bcf7-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-111">Click New.</span></span>
3. <span data-ttu-id="9bcf7-112">Dans le champ Grille, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-112">In the Grid field, type a value.</span></span>
4. <span data-ttu-id="9bcf7-113">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9bcf7-114">Sélectionnez une option dans le champ Type.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-114">In the Type field, select an option.</span></span>
6. <span data-ttu-id="9bcf7-115">Dans le champ Paramétrage de référence, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-115">In the Reference setup field, enter or select a value.</span></span>
7. <span data-ttu-id="9bcf7-116">Dans le champ Devise, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-116">In the Currency field, enter or select a value.</span></span>
8. <span data-ttu-id="9bcf7-117">Tapez une valeur dans le champ Devise.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-117">In the Currency field, type a value.</span></span>
9. <span data-ttu-id="9bcf7-118">Entrez une date dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-118">In the Effective date field, enter a date.</span></span>

## <a name="add-levels-to-the-compensation-structure"></a><span data-ttu-id="9bcf7-119">Ajouter des niveaux à la structure de rémunération</span><span class="sxs-lookup"><span data-stu-id="9bcf7-119">Add levels to the compensation structure</span></span>
1. <span data-ttu-id="9bcf7-120">Cliquez sur Structure des rémunérations.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-120">Click Compensation structure.</span></span>
2. <span data-ttu-id="9bcf7-121">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="9bcf7-122">Dans le champ Niveau, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-122">In the Level field, enter or select a value.</span></span>
4. <span data-ttu-id="9bcf7-123">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-123">Click New.</span></span>
5. <span data-ttu-id="9bcf7-124">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-124">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="9bcf7-125">Dans le champ Niveau, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-125">In the Level field, enter or select a value.</span></span>
7. <span data-ttu-id="9bcf7-126">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-126">Click New.</span></span>
8. <span data-ttu-id="9bcf7-127">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-127">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="9bcf7-128">Dans le champ Niveau, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-128">In the Level field, enter or select a value.</span></span>
10. <span data-ttu-id="9bcf7-129">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-129">Click New.</span></span>
11. <span data-ttu-id="9bcf7-130">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-130">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="9bcf7-131">Dans le champ Niveau, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-131">In the Level field, enter or select a value.</span></span>
13. <span data-ttu-id="9bcf7-132">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-132">Click New.</span></span>
14. <span data-ttu-id="9bcf7-133">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-133">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="9bcf7-134">Dans le champ Niveau, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-134">In the Level field, enter or select a value.</span></span>

## <a name="fill-in-the-compensation-structure-with-values"></a><span data-ttu-id="9bcf7-135">Renseigner la structure de rémunération avec des valeurs</span><span class="sxs-lookup"><span data-stu-id="9bcf7-135">Fill in the compensation structure with values</span></span>
1. <span data-ttu-id="9bcf7-136">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9bcf7-137">À ce stade, vous pouvez saisir les valeurs de rémunération manuellement dans chaque champ de la table, ou utiliser la fonctionnalité de modification en masse pour renseigner facilement plusieurs champs et effectuer des calculs de base.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-137">At this point, compensation values can manually be entered into each field in the table, or the Mass change functionality can be used to easily fill in multiple fields and perform basic calculations.</span></span>  
2. <span data-ttu-id="9bcf7-138">Cliquez sur Modification en masse.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-138">Click Mass change.</span></span>
    * <span data-ttu-id="9bcf7-139">Pour cette grille, nous appliquerons d'abord la valeur médiane du premier niveau à tous les champs de la table.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-139">For this grid, we'll first apply the value for the midpoint of the first level's to all the fields in the table.</span></span> <span data-ttu-id="9bcf7-140">Cela servira de base à la matrice de rémunération.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-140">This will be the basis for the compensation matrix.</span></span>  
3. <span data-ttu-id="9bcf7-141">Dans le champ Type d'ajustement, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-141">In the Adjustment type field, select an option.</span></span>
4. <span data-ttu-id="9bcf7-142">Entrez un numéro dans le champ Montant d'ajustement.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-142">In the Adjustment amount field, enter a number.</span></span>
5. <span data-ttu-id="9bcf7-143">Dans la liste, cochez ou décochez toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-143">In the list, mark or unmark all rows.</span></span>
6. <span data-ttu-id="9bcf7-144">Cliquez sur Appliquer à la grille.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-144">Click Apply to grid.</span></span>
    * <span data-ttu-id="9bcf7-145">Nous emploierons maintenant la fonction de modification en masse pour incrémenter les montants dans chaque niveau suivant par un certain pourcentage ou montant.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-145">Now we'll use the mass change function to increment the amounts in each subsequent level by a certain percentage or amount.</span></span> <span data-ttu-id="9bcf7-146">Dans cet exemple, chaque niveau aura un écart de 12,5 % entre ses valeurs médianes.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-146">In this example, each grade will have a 12.5% spread between their midpoints.</span></span>  
7. <span data-ttu-id="9bcf7-147">Dans le champ Type d'ajustement, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-147">In the Adjustment type field, select an option.</span></span>
8. <span data-ttu-id="9bcf7-148">Entrez un numéro dans le champ Montant d'ajustement.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-148">In the Adjustment amount field, enter a number.</span></span>
9. <span data-ttu-id="9bcf7-149">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-149">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="9bcf7-150">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-150">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="9bcf7-151">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-151">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="9bcf7-152">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-152">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="9bcf7-153">Cliquez sur Appliquer à la grille.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-153">Click Apply to grid.</span></span>
14. <span data-ttu-id="9bcf7-154">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-154">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="9bcf7-155">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-155">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="9bcf7-156">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-156">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="9bcf7-157">Cliquez sur Appliquer à la grille.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-157">Click Apply to grid.</span></span>
18. <span data-ttu-id="9bcf7-158">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-158">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="9bcf7-159">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-159">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="9bcf7-160">Cliquez sur Appliquer à la grille.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-160">Click Apply to grid.</span></span>
21. <span data-ttu-id="9bcf7-161">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-161">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="9bcf7-162">Cliquez sur Appliquer à la grille.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-162">Click Apply to grid.</span></span>
    * <span data-ttu-id="9bcf7-163">Nous emploierons maintenant la fonction de modification en masse pour ajuster les points de référence minimum et maximum pour chaque niveau.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-163">Now we'll use the mass change function to adjust the Minimum and Maximum reference points for each level.</span></span> <span data-ttu-id="9bcf7-164">Cet exemple utilise un écart de 50 %. Le point de référence minimum sera ajusté de -20 % et le point maximum de +20 %.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-164">This example will use a 50% spread so the Minimum reference point will be adjusted -20% and the Maximum will be adjusted +20%.</span></span>  
23. <span data-ttu-id="9bcf7-165">Entrez un numéro dans le champ Montant d'ajustement.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-165">In the Adjustment amount field, enter a number.</span></span>
24. <span data-ttu-id="9bcf7-166">Dans le champ Point de référence, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-166">In the Reference point field, enter or select a value.</span></span>
25. <span data-ttu-id="9bcf7-167">Dans la liste, cochez ou décochez toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-167">In the list, mark or unmark all rows.</span></span>
26. <span data-ttu-id="9bcf7-168">Cliquez sur Appliquer à la grille.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-168">Click Apply to grid.</span></span>
27. <span data-ttu-id="9bcf7-169">Entrez un numéro dans le champ Montant d'ajustement.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-169">In the Adjustment amount field, enter a number.</span></span>
28. <span data-ttu-id="9bcf7-170">Dans le champ Point de référence, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-170">In the Reference point field, enter or select a value.</span></span>
29. <span data-ttu-id="9bcf7-171">Dans la liste, cochez ou décochez toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-171">In the list, mark or unmark all rows.</span></span>
30. <span data-ttu-id="9bcf7-172">Cliquez sur Appliquer à la grille.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-172">Click Apply to grid.</span></span>


