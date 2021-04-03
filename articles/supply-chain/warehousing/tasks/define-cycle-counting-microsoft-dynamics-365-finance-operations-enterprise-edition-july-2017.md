---
title: Définir l’inventaire tournant
description: L’inventaire tournant est un processus d’entrepôt qui permet d’auditer les articles en stock disponibles.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountThreshold, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSParameters, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a0b94bcc1c33889f336541f3dd8ba4782fac0261
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238988"
---
# <a name="define-cycle-counting"></a><span data-ttu-id="5884e-103">Définir l’inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="5884e-103">Define cycle counting</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5884e-104">L’inventaire tournant est un processus d’entrepôt qui permet d’auditer les articles en stock disponibles.</span><span class="sxs-lookup"><span data-stu-id="5884e-104">Cycle counting is a warehouse process that you can use to audit on-hand inventory items.</span></span> <span data-ttu-id="5884e-105">Cet enregistrement de tâche indique comment paramétrer la priorité par défaut du travail d’inventaire, activer une option de menu d’appareil mobile pour traiter à la fois les opérations de prélèvement et d’inventaire, activer un déclencheur de seuil de comptage lorsqu’un emplacement devient vide et activer un plan d’inventaire tournant pour un article spécifique dans un entrepôt particulier.</span><span class="sxs-lookup"><span data-stu-id="5884e-105">This task recording shows how to set up the default counting work priority, enable a mobile device menu item to process both picking and counting operations, enable a counting threshold trigger when a location becomes empty, and enable a cycle counting plan for a specific item in a specific warehouse.</span></span> <span data-ttu-id="5884e-106">Ces tâches sont généralement effectuées par un gestionnaire d’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="5884e-106">Typically, these tasks are performed by a warehouse manager.</span></span> <span data-ttu-id="5884e-107">Vous pouvez exécuter cette procédure avec la société fictive de démonstration USMF ou avec vos propres données.</span><span class="sxs-lookup"><span data-stu-id="5884e-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="set-the-priority-of-counting-work"></a><span data-ttu-id="5884e-108">Définir la priorité du travail d’inventaire</span><span class="sxs-lookup"><span data-stu-id="5884e-108">Set the priority of counting work</span></span>
1. <span data-ttu-id="5884e-109">Dans le **Volet de navigation**, allez dans **Modules > Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="5884e-109">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="5884e-110">Cliquez sur l’onglet **Inventaire tournant**.</span><span class="sxs-lookup"><span data-stu-id="5884e-110">Click the **Cycle counting** tab.</span></span>
3. <span data-ttu-id="5884e-111">Entrez un nombre dans le champ **Priorité de travail d’inventaire tournant par défaut**.</span><span class="sxs-lookup"><span data-stu-id="5884e-111">In the **Default cycle count work priority** field, enter a number.</span></span> <span data-ttu-id="5884e-112">Cette étape modifie la priorité du travail d’inventaire tournant par rapport à d’autres types de travail dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="5884e-112">This step changes the priority of cycle counting work compared to other types of work in the warehouse.</span></span> <span data-ttu-id="5884e-113">Si vous entrez un nombre plus faible que celui pour d’autres types de travail, vous élevez la priorité du travail d’inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="5884e-113">By entering a number that is lower than the number for other types of work, you raise the priority of the cycle counting work.</span></span>  
4. <span data-ttu-id="5884e-114">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5884e-114">Click **Save**.</span></span>
5. <span data-ttu-id="5884e-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5884e-115">Close the page.</span></span>

## <a name="enable-the-mobile-device"></a><span data-ttu-id="5884e-116">Activer l’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="5884e-116">Enable the mobile device</span></span>
1. <span data-ttu-id="5884e-117">Dans le **Volet de navigation**, allez dans **Modules > Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="5884e-117">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="5884e-118">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5884e-118">Click **New**.</span></span>
3. <span data-ttu-id="5884e-119">Dans le champ **Nom de l’option de menu**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5884e-119">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="5884e-120">Dans le champ **Titre**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5884e-120">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="5884e-121">Dans le champ **Mode**, sélectionnez « Travail ».</span><span class="sxs-lookup"><span data-stu-id="5884e-121">In the **Mode** field, select 'Work'.</span></span>
6. <span data-ttu-id="5884e-122">Définissez l’option **Utiliser un travail existant** sur Oui.</span><span class="sxs-lookup"><span data-stu-id="5884e-122">Set the **Use existing work** option to Yes.</span></span> <span data-ttu-id="5884e-123">Lorsque vous définissez cette option sur Oui, le système recherchera les travaux existants lorsque l’option de menu d’appareil mobile est utilisée.</span><span class="sxs-lookup"><span data-stu-id="5884e-123">When you set this option to Yes, the system will look for existing work when the mobile device menu item is used.</span></span>  
7. <span data-ttu-id="5884e-124">Dans le champ **Dirigé par**, sélectionnez « Système dirigé ».</span><span class="sxs-lookup"><span data-stu-id="5884e-124">In the **Directed by** field, select 'System directed'.</span></span> <span data-ttu-id="5884e-125">Lorsque l’option « Dirigé par le système » est sélectionnée, le magasinier sera dirigé vers le travail en cours qui se trouve dans les classes de travail définies.</span><span class="sxs-lookup"><span data-stu-id="5884e-125">When "System directed" is selected, the warehouse worker will be directed to open work that is in defined work classes.</span></span> <span data-ttu-id="5884e-126">(Nous créerons ces classes de travail par la suite.)</span><span class="sxs-lookup"><span data-stu-id="5884e-126">(We will create these work classes next.)</span></span>  
8. <span data-ttu-id="5884e-127">Développez le raccourci **Classes de travail**.</span><span class="sxs-lookup"><span data-stu-id="5884e-127">Expand the **Work classes** fastTab.</span></span> <span data-ttu-id="5884e-128">Ensuite, nous créerons deux classes de travail qui seront utilisées avec cette option de menu d’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="5884e-128">Next, we will create two work classes that will be used with this mobile device menu item.</span></span> <span data-ttu-id="5884e-129">Lorsque l’option de menu est utilisée, ces classes de travail sont interrogées, et le travail ayant la priorité la plus élevée est affiché à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5884e-129">When the menu item is used, these work classes will be queried, and the work that has the highest priority will be shown to the user.</span></span>  
9. <span data-ttu-id="5884e-130">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5884e-130">Click **New**.</span></span>
10. <span data-ttu-id="5884e-131">Sélectionnez une valeur dans le champ **ID classe de travail**.</span><span class="sxs-lookup"><span data-stu-id="5884e-131">In the **Work class ID** field, select a value.</span></span>
11. <span data-ttu-id="5884e-132">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5884e-132">Click **New**.</span></span>
12. <span data-ttu-id="5884e-133">Sélectionnez une valeur dans le champ **ID classe de travail**.</span><span class="sxs-lookup"><span data-stu-id="5884e-133">In the **Work class ID** field, select a value.</span></span>
13. <span data-ttu-id="5884e-134">Cliquez sur **Enregistrer** dans le volet **Actions**.</span><span class="sxs-lookup"><span data-stu-id="5884e-134">In the **Action Pane**, click **Save**.</span></span>
14. <span data-ttu-id="5884e-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5884e-135">Close the page.</span></span>
15. <span data-ttu-id="5884e-136">Dans le **Volet de navigation**, allez dans **Modules > Gestion des entrepôts > Configuration > Appareil mobile > menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="5884e-136">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
16. <span data-ttu-id="5884e-137">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="5884e-137">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="5884e-138">Dans l’arborescence, sélectionnez l’option de menu que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="5884e-138">In the tree, select 'the menu item that you just created'.</span></span>
18. <span data-ttu-id="5884e-139">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="5884e-139">Click **Edit**.</span></span>
19. <span data-ttu-id="5884e-140">Cliquez sur la flèche pour ajouter l’option de menu au menu.</span><span class="sxs-lookup"><span data-stu-id="5884e-140">Click the arrow to add the menu item to the menu.</span></span>
20. <span data-ttu-id="5884e-141">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5884e-141">Click **Save**.</span></span>

## <a name="create-a-counting-threshold"></a><span data-ttu-id="5884e-142">Créer un seuil d’inventaire</span><span class="sxs-lookup"><span data-stu-id="5884e-142">Create a counting threshold</span></span>
1. <span data-ttu-id="5884e-143">Dans le **Volet de navigation**, allez dans **Modules > Gestion de l’entrepôt > Paramétrage > Inventaire tournant > Seuils d’inventaire tournant**.</span><span class="sxs-lookup"><span data-stu-id="5884e-143">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Cycle counting > Cycle count thresholds**.</span></span>
2. <span data-ttu-id="5884e-144">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5884e-144">Click **New**.</span></span>
3. <span data-ttu-id="5884e-145">Entrez une valeur dans le champ **ID seuil d’inventaire tournant**.</span><span class="sxs-lookup"><span data-stu-id="5884e-145">In the **Cycle counting threshold ID** field, type a value.</span></span>
4. <span data-ttu-id="5884e-146">Définissez l’option **Traiter immédiatement l’inventaire tournant** sur Oui.</span><span class="sxs-lookup"><span data-stu-id="5884e-146">Set the **Process cycle counting immediately** option to Yes.</span></span>
5. <span data-ttu-id="5884e-147">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="5884e-147">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="5884e-148">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5884e-148">Click **Save**.</span></span>
7. <span data-ttu-id="5884e-149">Cliquez sur **Sélectionner des emplacements**.</span><span class="sxs-lookup"><span data-stu-id="5884e-149">Click **Select locations**.</span></span>
8. <span data-ttu-id="5884e-150">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5884e-150">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="5884e-151">Sélectionnez une valeur dans le champ **Critère**.</span><span class="sxs-lookup"><span data-stu-id="5884e-151">In the **Criteria** field, select a value.</span></span>
10. <span data-ttu-id="5884e-152">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5884e-152">Click **OK**.</span></span>
11. <span data-ttu-id="5884e-153">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5884e-153">Close the page.</span></span>

## <a name="create-a-cycle-count-plan"></a><span data-ttu-id="5884e-154">Créer un plan d’inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="5884e-154">Create a cycle count plan</span></span>
1. <span data-ttu-id="5884e-155">Dans le **Volet de navigation**, allez dans **Modules > Gestion de l’entrepôt > Paramétrage > Inventaire tournant > Plans d’inventaire tournant**.</span><span class="sxs-lookup"><span data-stu-id="5884e-155">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Cycle counting > Cycle count plans**.</span></span>
2. <span data-ttu-id="5884e-156">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5884e-156">Click **New**.</span></span>
3. <span data-ttu-id="5884e-157">Entrez une valeur dans le champ **ID plan d’inventaire tournant**.</span><span class="sxs-lookup"><span data-stu-id="5884e-157">In the **Cycle counting plan ID** field, type a value.</span></span>
4. <span data-ttu-id="5884e-158">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="5884e-158">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="5884e-159">Entrez un nombre dans le champ **Nombre maximal d’inventaires tournants**.</span><span class="sxs-lookup"><span data-stu-id="5884e-159">In the **Maximum number of cycle counts** field, enter a number.</span></span>
6. <span data-ttu-id="5884e-160">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5884e-160">Click **Save**.</span></span>
7. <span data-ttu-id="5884e-161">Cliquez sur **Sélectionner des emplacements**.</span><span class="sxs-lookup"><span data-stu-id="5884e-161">Click **Select locations**.</span></span>
8. <span data-ttu-id="5884e-162">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5884e-162">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="5884e-163">Sélectionnez une valeur dans le champ **Critère**.</span><span class="sxs-lookup"><span data-stu-id="5884e-163">In the **Criteria** field, select a value.</span></span>
10. <span data-ttu-id="5884e-164">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5884e-164">Click **OK**.</span></span>
11. <span data-ttu-id="5884e-165">Entrez un nombre dans le champ **Jours entre les inventaires tournants**.</span><span class="sxs-lookup"><span data-stu-id="5884e-165">In the **Days between cycle counting** field, enter a number.</span></span> <span data-ttu-id="5884e-166">Par exemple, si le champ **Jours entre les inventaires tournants** est défini sur 5, le travail d’inventaire tournant sera créé tous les cinq jours.</span><span class="sxs-lookup"><span data-stu-id="5884e-166">For example, if the **Days between cycle counting** field is set to 5, cycle counting work will be created every five days.</span></span> <span data-ttu-id="5884e-167">Toutefois, si le travail d’inventaire tournant est traité le troisième jour, le travail d’inventaire tournant suivant sera créé cinq jours après le traitement du dernier inventaire tournant, le 8ème jour.</span><span class="sxs-lookup"><span data-stu-id="5884e-167">However, if cycle counting work is processed on day three, the next cycle counting work will be created five days after the last cycle counting was processed, on day 8.</span></span>  
12. <span data-ttu-id="5884e-168">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5884e-168">Click **Save**.</span></span>
13. <span data-ttu-id="5884e-169">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5884e-169">Click **New**.</span></span>
14. <span data-ttu-id="5884e-170">Entrez un nombre dans le champ **Numéro de souche**.</span><span class="sxs-lookup"><span data-stu-id="5884e-170">In the **Sequence number** field, enter a number.</span></span> <span data-ttu-id="5884e-171">Le tri s’effectue du plus petit nombre au plus grand nombre.</span><span class="sxs-lookup"><span data-stu-id="5884e-171">The sort is from the smallest number to the largest number.</span></span> <span data-ttu-id="5884e-172">La valeur doit être supérieure à 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="5884e-172">The value must be more than 0 (zero).</span></span>  
15. <span data-ttu-id="5884e-173">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5884e-173">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="5884e-174">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="5884e-174">In the **Description** field, type a value.</span></span>
17. <span data-ttu-id="5884e-175">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5884e-175">Click **Save**.</span></span>
18. <span data-ttu-id="5884e-176">Cliquez sur **Définir le produit**.</span><span class="sxs-lookup"><span data-stu-id="5884e-176">Click **Define product** query.</span></span>
19. <span data-ttu-id="5884e-177">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5884e-177">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="5884e-178">Dans le champ **Critères**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5884e-178">In the **Criteria** field, enter or select a value.</span></span>
21. <span data-ttu-id="5884e-179">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5884e-179">Click **OK**.</span></span>
22. <span data-ttu-id="5884e-180">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5884e-180">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]