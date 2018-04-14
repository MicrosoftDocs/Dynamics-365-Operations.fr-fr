--- 
title: "Définir l'inventaire tournant"
description: "L'inventaire tournant est un processus d'entrepôt qui permet d'auditer les articles en stock disponibles."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 5a95f63efe3d78dc371cacdc09734490a601b1b8
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="define-cycle-counting"></a><span data-ttu-id="964b8-103">Définir l'inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="964b8-103">Define cycle counting</span></span> 

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="964b8-104">L'inventaire tournant est un processus d'entrepôt qui permet d'auditer les articles en stock disponibles.</span><span class="sxs-lookup"><span data-stu-id="964b8-104">Cycle counting is a warehouse process that you can use to audit on-hand inventory items.</span></span> <span data-ttu-id="964b8-105">Cet enregistrement de tâche indique comment paramétrer la priorité par défaut du travail d'inventaire, activer une option de menu d'appareil mobile pour traiter à la fois les opérations de prélèvement et d'inventaire, activer un déclencheur de seuil de comptage lorsqu'un emplacement devient vide et activer un plan d'inventaire tournant pour un article spécifique dans un entrepôt particulier.</span><span class="sxs-lookup"><span data-stu-id="964b8-105">This task recording shows how to set up the default counting work priority, enable a mobile device menu item to process both picking and counting operations, enable a counting threshold trigger when a location becomes empty, and enable a cycle counting plan for a specific item in a specific warehouse.</span></span> <span data-ttu-id="964b8-106">Ces tâches sont généralement effectuées par un gestionnaire d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="964b8-106">Typically, these tasks are performed by a warehouse manager.</span></span> <span data-ttu-id="964b8-107">Vous pouvez exécuter cette procédure avec la société fictive de démonstration USMF ou avec vos propres données.</span><span class="sxs-lookup"><span data-stu-id="964b8-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="set-the-priority-of-counting-work"></a><span data-ttu-id="964b8-108">Définir la priorité du travail d'inventaire</span><span class="sxs-lookup"><span data-stu-id="964b8-108">Set the priority of counting work</span></span>
1. <span data-ttu-id="964b8-109">Acccédez à Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="964b8-109">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="964b8-110">Cliquez sur l'onglet Inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="964b8-110">Click the Cycle counting tab.</span></span>
3. <span data-ttu-id="964b8-111">Dans le champ Priorité de travail d'inventaire tournant par défaut, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="964b8-111">In the Default cycle count work priority field, enter a number.</span></span>
    * <span data-ttu-id="964b8-112">Cette étape modifie la priorité du travail d'inventaire tournant par rapport à d'autres types de travail dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="964b8-112">This step changes the priority of cycle counting work compared to other types of work in the warehouse.</span></span> <span data-ttu-id="964b8-113">Si vous entrez un nombre plus faible que celui pour d'autres types de travail, vous élevez la priorité du travail d'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="964b8-113">By entering a number that is lower than the number for other types of work, you raise the priority of the cycle counting work.</span></span>  
4. <span data-ttu-id="964b8-114">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="964b8-114">Click Save.</span></span>
5. <span data-ttu-id="964b8-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="964b8-115">Close the page.</span></span>

## <a name="enable-the-mobile-device"></a><span data-ttu-id="964b8-116">Activer l'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="964b8-116">Enable the mobile device</span></span>
1. <span data-ttu-id="964b8-117">Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="964b8-117">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="964b8-118">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="964b8-118">Click New.</span></span>
3. <span data-ttu-id="964b8-119">Saisissez une valeur dans le champ Nom de l'option de menu.</span><span class="sxs-lookup"><span data-stu-id="964b8-119">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="964b8-120">Tapez une valeur dans le champ Titre.</span><span class="sxs-lookup"><span data-stu-id="964b8-120">In the Title field, type a value.</span></span>
5. <span data-ttu-id="964b8-121">Dans le champ Mode, Sélectionnez « Travail ».</span><span class="sxs-lookup"><span data-stu-id="964b8-121">In the Mode field, select 'Work'.</span></span>
6. <span data-ttu-id="964b8-122">Définissez l'option Utiliser un travail existant sur Oui.</span><span class="sxs-lookup"><span data-stu-id="964b8-122">Set the Use existing work option to Yes.</span></span>
    * <span data-ttu-id="964b8-123">Lorsque vous définissez cette option sur Oui, le système recherchera les travaux existants lorsque l'option de menu d'appareil mobile est utilisée.</span><span class="sxs-lookup"><span data-stu-id="964b8-123">When you set this option to Yes, the system will look for existing work when the mobile device menu item is used.</span></span>  
7. <span data-ttu-id="964b8-124">Dans le champ Dirigé par, sélectionnez « Système dirigé ».</span><span class="sxs-lookup"><span data-stu-id="964b8-124">In the Directed by field, select 'System directed'.</span></span>
    * <span data-ttu-id="964b8-125">Lorsque l'option « Dirigé par le système » est sélectionnée, le magasinier sera dirigé vers le travail en cours qui se trouve dans les classes de travail définies.</span><span class="sxs-lookup"><span data-stu-id="964b8-125">When "System directed" is selected, the warehouse worker will be directed to open work that is in defined work classes.</span></span> <span data-ttu-id="964b8-126">(Nous créerons ces classes de travail par la suite.)</span><span class="sxs-lookup"><span data-stu-id="964b8-126">(We will create these work classes next.)</span></span>  
8. <span data-ttu-id="964b8-127">Développez ou réduisez la section Classes de travail.</span><span class="sxs-lookup"><span data-stu-id="964b8-127">Expand or collapse the Work classes section.</span></span>
    * <span data-ttu-id="964b8-128">Ensuite, nous créerons deux classes de travail qui seront utilisées avec cette option de menu d'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="964b8-128">Next, we will create two work classes that will be used with this mobile device menu item.</span></span> <span data-ttu-id="964b8-129">Lorsque l'option de menu est utilisée, ces classes de travail sont interrogées, et le travail ayant la priorité la plus élevée est affiché à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="964b8-129">When the menu item is used, these work classes will be queried, and the work that has the highest priority will be shown to the user.</span></span>  
9. <span data-ttu-id="964b8-130">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="964b8-130">Click New.</span></span>
10. <span data-ttu-id="964b8-131">Dans le champ ID classe de travail, sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="964b8-131">In the Work class ID field, select a value.</span></span>
11. <span data-ttu-id="964b8-132">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="964b8-132">Click New.</span></span>
12. <span data-ttu-id="964b8-133">Dans le champ ID classe de travail, sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="964b8-133">In the Work class ID field, select a value.</span></span>
13. <span data-ttu-id="964b8-134">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="964b8-134">Click Save.</span></span>
14. <span data-ttu-id="964b8-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="964b8-135">Close the page.</span></span>
15. <span data-ttu-id="964b8-136">Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Menu d'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="964b8-136">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
16. <span data-ttu-id="964b8-137">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="964b8-137">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="964b8-138">Dans l'arborescence, sélectionnez l'option de menu que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="964b8-138">In the tree, select 'the menu item that you just created'.</span></span>
18. <span data-ttu-id="964b8-139">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="964b8-139">Click Edit.</span></span>
19. <span data-ttu-id="964b8-140">Cliquez sur la flèche pour ajouter l'option de menu au menu.</span><span class="sxs-lookup"><span data-stu-id="964b8-140">Click the arrow to add the menu item to the menu.</span></span>
20. <span data-ttu-id="964b8-141">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="964b8-141">Click Save.</span></span>

## <a name="create-a-counting-threshold"></a><span data-ttu-id="964b8-142">Créer un seuil d'inventaire</span><span class="sxs-lookup"><span data-stu-id="964b8-142">Create a counting threshold</span></span>
1. <span data-ttu-id="964b8-143">Accédez à Gestion de l'entrepôt > Paramétrage > Inventaire tournant > Seuils d'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="964b8-143">Go to Warehouse management > Setup > Cycle counting > Cycle count thresholds.</span></span>
2. <span data-ttu-id="964b8-144">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="964b8-144">Click New.</span></span>
3. <span data-ttu-id="964b8-145">Dans le champ ID seuil d'inventaire tournant, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="964b8-145">In the Cycle counting threshold ID field, type a value.</span></span>
4. <span data-ttu-id="964b8-146">Définissez l'option Traiter immédiatement l'inventaire tournant sur oui.</span><span class="sxs-lookup"><span data-stu-id="964b8-146">Set the Process cycle counting immediately option to Yes.</span></span>
5. <span data-ttu-id="964b8-147">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="964b8-147">In the Description field, type a value.</span></span>
6. <span data-ttu-id="964b8-148">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="964b8-148">Click Save.</span></span>
7. <span data-ttu-id="964b8-149">Cliquez sur Sélectionner des emplacements.</span><span class="sxs-lookup"><span data-stu-id="964b8-149">Click Select locations.</span></span>
8. <span data-ttu-id="964b8-150">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="964b8-150">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="964b8-151">Sélectionnez une valeur dans le champ Critère.</span><span class="sxs-lookup"><span data-stu-id="964b8-151">In the Criteria field, select a value.</span></span>
10. <span data-ttu-id="964b8-152">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="964b8-152">Click OK.</span></span>
11. <span data-ttu-id="964b8-153">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="964b8-153">Close the page.</span></span>

## <a name="create-a-cycle-count-plan"></a><span data-ttu-id="964b8-154">Créer un plan d'inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="964b8-154">Create a cycle count plan</span></span>
1. <span data-ttu-id="964b8-155">Accédez à Gestion de l'entrepôt > Paramétrage > Inventaire tournant > Plans d'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="964b8-155">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="964b8-156">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="964b8-156">Click New.</span></span>
3. <span data-ttu-id="964b8-157">Dans le champ ID plan d'inventaire tournant, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="964b8-157">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="964b8-158">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="964b8-158">In the Description field, type a value.</span></span>
5. <span data-ttu-id="964b8-159">Dans le champ Nombre maximal d'inventaires tournants, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="964b8-159">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="964b8-160">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="964b8-160">Click Save.</span></span>
7. <span data-ttu-id="964b8-161">Cliquez sur Sélectionner des emplacements.</span><span class="sxs-lookup"><span data-stu-id="964b8-161">Click Select locations.</span></span>
8. <span data-ttu-id="964b8-162">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="964b8-162">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="964b8-163">Sélectionnez une valeur dans le champ Critère.</span><span class="sxs-lookup"><span data-stu-id="964b8-163">In the Criteria field, select a value.</span></span>
10. <span data-ttu-id="964b8-164">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="964b8-164">Click OK.</span></span>
11. <span data-ttu-id="964b8-165">Dans le champ Jours entre les inventaires tournants, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="964b8-165">In the Days between cycle counting field, enter a number.</span></span>
    * <span data-ttu-id="964b8-166">Par exemple, si le champ Jours entre les inventaires tournants est défini sur 5, le travail d'inventaire tournant sera créé tous les cinq jours.</span><span class="sxs-lookup"><span data-stu-id="964b8-166">For example, if the Days between cycle counting field is set to 5, cycle counting work will be created every five days.</span></span> <span data-ttu-id="964b8-167">Toutefois, si le travail d'inventaire tournant est traité le troisième jour, le travail d'inventaire tournant suivant sera créé cinq jours après le traitement du dernier inventaire tournant, le 8ème jour.</span><span class="sxs-lookup"><span data-stu-id="964b8-167">However, if cycle counting work is processed on day three, the next cycle counting work will be created five days after the last cycle counting was processed, on day 8.</span></span>  
12. <span data-ttu-id="964b8-168">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="964b8-168">Click Save.</span></span>
13. <span data-ttu-id="964b8-169">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="964b8-169">Click New.</span></span>
14. <span data-ttu-id="964b8-170">Entrez un nombre dans le champ Numéro de souche.</span><span class="sxs-lookup"><span data-stu-id="964b8-170">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="964b8-171">Le tri s'effectue du plus petit nombre au plus grand nombre.</span><span class="sxs-lookup"><span data-stu-id="964b8-171">The sort is from the smallest number to the largest number.</span></span> <span data-ttu-id="964b8-172">La valeur doit être supérieure à 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="964b8-172">The value must be more than 0 (zero).</span></span>  
15. <span data-ttu-id="964b8-173">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="964b8-173">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="964b8-174">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="964b8-174">In the Description field, type a value.</span></span>
17. <span data-ttu-id="964b8-175">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="964b8-175">Click Save.</span></span>
18. <span data-ttu-id="964b8-176">Cliquez sur Définir une requête de produit.</span><span class="sxs-lookup"><span data-stu-id="964b8-176">Click Define product query.</span></span>
19. <span data-ttu-id="964b8-177">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="964b8-177">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="964b8-178">Dans le champ Critères, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="964b8-178">In the Criteria field, enter or select a value.</span></span>
21. <span data-ttu-id="964b8-179">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="964b8-179">Click OK.</span></span>
22. <span data-ttu-id="964b8-180">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="964b8-180">Close the page.</span></span>


