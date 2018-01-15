--- 
title: "Créer des activités de processus pour la lean manufacturing"
description: "Créez une activité de processus pour la lean manufacturing."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: dd77c20b622fd8a14e1cdf77883043699f9a6317
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-process-activities-for-lean-manufacturing"></a><span data-ttu-id="2243a-103">Créer des activités de processus pour la lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="2243a-103">Create process activities for lean manufacturing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2243a-104">Créez une activité de processus pour la lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="2243a-104">Create a process activity for lean manufacturing.</span></span> 

<span data-ttu-id="2243a-105">Conditions préalables :</span><span class="sxs-lookup"><span data-stu-id="2243a-105">Prerequisites:</span></span> 

1. <span data-ttu-id="2243a-106">Un flux de production et une version non actifs doivent être créés.</span><span class="sxs-lookup"><span data-stu-id="2243a-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="2243a-107">Une cellule de travail doit être créée.</span><span class="sxs-lookup"><span data-stu-id="2243a-107">A work cell must be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="2243a-108">Cherchez la version du flux de production.</span><span class="sxs-lookup"><span data-stu-id="2243a-108">Find the production flow version</span></span>
1. <span data-ttu-id="2243a-109">Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.</span><span class="sxs-lookup"><span data-stu-id="2243a-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="2243a-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2243a-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2243a-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2243a-111">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="2243a-112">Créer une nouvelle activité</span><span class="sxs-lookup"><span data-stu-id="2243a-112">Create a new activity</span></span>
1. <span data-ttu-id="2243a-113">Cliquez sur Activités.</span><span class="sxs-lookup"><span data-stu-id="2243a-113">Click Activities.</span></span>
    * <span data-ttu-id="2243a-114">Vérifiez que le flux de production sélectionné a une version à l'état de brouillon, et sélectionnez celle-ci.</span><span class="sxs-lookup"><span data-stu-id="2243a-114">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="2243a-115">Cliquez sur Créer une nouvelle activité de plan.</span><span class="sxs-lookup"><span data-stu-id="2243a-115">Click Create new plan activity.</span></span>
3. <span data-ttu-id="2243a-116">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="2243a-116">Click Next.</span></span>
4. <span data-ttu-id="2243a-117">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="2243a-117">In the Name field, type a value.</span></span>
5. <span data-ttu-id="2243a-118">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="2243a-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="2243a-119">Notez que le nom doit être unique pour un flux de production donné pour toutes les versions.</span><span class="sxs-lookup"><span data-stu-id="2243a-119">Note that the name must be unique for a given production flow for all versions.</span></span>  
6. <span data-ttu-id="2243a-120">Dans le champ Quantité à traiter, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="2243a-120">In the Process quantity field, enter a number.</span></span>
    * <span data-ttu-id="2243a-121">Notez que, indépendamment de la quantité qui sera traitée, c'est la quantité minimale par tâche qui sert à calculer le coût de travail.</span><span class="sxs-lookup"><span data-stu-id="2243a-121">Note that no matter what job quantity will be processed, this is the minimum quantity per job to calculate the labor cost.</span></span> <span data-ttu-id="2243a-122">Si les quantités de tâche dévient de cette quantité, l'écart de coût du travail est créé.</span><span class="sxs-lookup"><span data-stu-id="2243a-122">If job quantities deviate from this quantity, labor cost variance will be created.</span></span>  
7. <span data-ttu-id="2243a-123">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="2243a-123">Click Next.</span></span>

## <a name="select-the-work-cell"></a><span data-ttu-id="2243a-124">Sélectionner la cellule de travail</span><span class="sxs-lookup"><span data-stu-id="2243a-124">Select the work cell</span></span>
1. <span data-ttu-id="2243a-125">Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="2243a-125">In the Work cell field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="2243a-126">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2243a-126">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="2243a-127">Définir les mises à jour de stock</span><span class="sxs-lookup"><span data-stu-id="2243a-127">Define the inventory updates</span></span>
1. <span data-ttu-id="2243a-128">Activez ou désactivez la case à cocher Mettre à jour la réception disponible.</span><span class="sxs-lookup"><span data-stu-id="2243a-128">Select or clear the Update on hand receipt check box.</span></span>
    * <span data-ttu-id="2243a-129">Si Mise à jour disponible = Non, vous pouvez définir l'activité de manière à recevoir un produit semi-fini (l'activité n'atteint pas le niveau de nomenclature suivant).</span><span class="sxs-lookup"><span data-stu-id="2243a-129">If Update On hand = No, you can define the activity to receive a semi-finished product (the activity does not reach the next BOM level).</span></span>    <span data-ttu-id="2243a-130">Vous pouvez également choisir de consommer des produits semi-finis.</span><span class="sxs-lookup"><span data-stu-id="2243a-130">You can also select to consume semi-finished products.</span></span>  

## <a name="define-the-picking-activities"></a><span data-ttu-id="2243a-131">Définir les activités de prélèvement</span><span class="sxs-lookup"><span data-stu-id="2243a-131">Define the picking activities</span></span>
1. <span data-ttu-id="2243a-132">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="2243a-132">Click Next.</span></span>
2. <span data-ttu-id="2243a-133">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2243a-133">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2243a-134">Une activité de prélèvement par défaut est créée pour l'emplacement d'entrée de la cellule de travail sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2243a-134">A default picking activity is created for the input location of the selected work cell.</span></span>  
3. <span data-ttu-id="2243a-135">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="2243a-135">Click Add.</span></span>
    * <span data-ttu-id="2243a-136">Vous pouvez créer des activités de prélèvement supplémentaires pour des produits spécifiques, qui ne sont pas intermédiaires dans l'activité d'entrée de la cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="2243a-136">You can create additional picking activities for specific products, that are not staged at the work cell input activity.</span></span>  
4. <span data-ttu-id="2243a-137">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2243a-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="2243a-138">Tapez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="2243a-138">In the Item number field, type a value.</span></span>
6. <span data-ttu-id="2243a-139">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="2243a-139">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2243a-140">Avec cette définition, toutes les matières consommées dans l'activité sont prélevées dans l'entrepôt et l'emplacement d'entrée par défaut, à l'exception de l'article qui est défini dans la deuxième activité de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="2243a-140">With this definition, all materials consumed in the activity are picked from the default input warehouse and location except the item that is defined in the second picking activity.</span></span> <span data-ttu-id="2243a-141">Cet article sera prélevé à partir d'un entrepôt et d'un emplacement différents.</span><span class="sxs-lookup"><span data-stu-id="2243a-141">This item will be picked from a different warehouse and location.</span></span>  
7. <span data-ttu-id="2243a-142">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2243a-142">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="2243a-143">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2243a-143">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2243a-144">Activez ou désactivez la case à cocher Enregistrer le rebut.</span><span class="sxs-lookup"><span data-stu-id="2243a-144">Select or clear the Register scrap check box.</span></span>
10. <span data-ttu-id="2243a-145">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="2243a-145">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="2243a-146">Définir les durées d'activité</span><span class="sxs-lookup"><span data-stu-id="2243a-146">Define the activity times</span></span>
1. <span data-ttu-id="2243a-147">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2243a-147">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2243a-148">La définition d'un Délai d'exécution est requise.</span><span class="sxs-lookup"><span data-stu-id="2243a-148">The definition of a Runtime is required.</span></span> <span data-ttu-id="2243a-149">Le délai d'exécution est utilisé pour calculer les coûts et les délais de débit des tâches de kanban.</span><span class="sxs-lookup"><span data-stu-id="2243a-149">The Runtime is used to calculate costs and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="2243a-150">Les délais d'exécution ne sont pas utilisés pour calculer la charge de la capacité et la consommation ; celles-ci sont calculées par durée de cycle, dérivée de la tâche de version du flux de production.</span><span class="sxs-lookup"><span data-stu-id="2243a-150">Runtimes are not used to calculate capacity load and consumption, this is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="2243a-151">Entrez un nombre dans le champ Durée.</span><span class="sxs-lookup"><span data-stu-id="2243a-151">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="2243a-152">Dans le champ Unité, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2243a-152">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="2243a-153">Sélectionnez l'Unité de temps.</span><span class="sxs-lookup"><span data-stu-id="2243a-153">Select the Time unit.</span></span>
5. <span data-ttu-id="2243a-154">Dans le champ Par quantité, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="2243a-154">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="2243a-155">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2243a-155">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2243a-156">Les temps d'attente sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="2243a-156">Queue times are optional.</span></span>  
7. <span data-ttu-id="2243a-157">Entrez un nombre dans le champ Durée.</span><span class="sxs-lookup"><span data-stu-id="2243a-157">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="2243a-158">Dans le champ Unité, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2243a-158">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="2243a-159">Sélectionnez l'Unité de temps.</span><span class="sxs-lookup"><span data-stu-id="2243a-159">Select the Time unit.</span></span>
10. <span data-ttu-id="2243a-160">Dans le champ Par quantité, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="2243a-160">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="2243a-161">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="2243a-161">Click Next.</span></span>
12. <span data-ttu-id="2243a-162">Cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="2243a-162">Click Finish.</span></span>
13. <span data-ttu-id="2243a-163">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2243a-163">Close the page.</span></span>

