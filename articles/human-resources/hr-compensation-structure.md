---
title: Développer une structure de rémunération
description: Cet article décrit la création d’un régime de rémunération fixe et l’inscription des employés au régime par le biais de règles d’admissibilité.
author: andreabichsel
manager: tfehr
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5030203877ebdf885fb55c7946bfd4ee0c883c2e
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465676"
---
# <a name="develop-a-compensation-structure"></a><span data-ttu-id="f703e-103">Développer une structure de rémunération</span><span class="sxs-lookup"><span data-stu-id="f703e-103">Develop a compensation structure</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f703e-104">Cet article décrit la création d’un régime de rémunération fixe et l’inscription des employés au régime par le biais de règles d’admissibilité.</span><span class="sxs-lookup"><span data-stu-id="f703e-104">This article walks you through creating a fixed compensation plan and enrolling employees in the plan through eligibility rules.</span></span> <span data-ttu-id="f703e-105">Cet article utilise les données de démonstration USMF et s’adresse aux gestionnaires des rémunérations et avantages.</span><span class="sxs-lookup"><span data-stu-id="f703e-105">This article uses the USMF demo data and applies to Compensation and Benefits Managers.</span></span>

## <a name="create-a-fixed-compensation-plan"></a><span data-ttu-id="f703e-106">Création d’un régime de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="f703e-106">Create a fixed compensation plan</span></span>

1. <span data-ttu-id="f703e-107">Sélectionnez **Gestion des rémunérations**.</span><span class="sxs-lookup"><span data-stu-id="f703e-107">Select **Compensation management**.</span></span>

2. <span data-ttu-id="f703e-108">Sélectionnez **Régimes de rémunération fixe**.</span><span class="sxs-lookup"><span data-stu-id="f703e-108">Select **Fixed compensation plans**.</span></span>

3. <span data-ttu-id="f703e-109">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f703e-109">Select **New**.</span></span>

4. <span data-ttu-id="f703e-110">Dans le champ **Régime**, entrer une valeur.</span><span class="sxs-lookup"><span data-stu-id="f703e-110">In the **Plan** field, enter a value.</span></span>

5. <span data-ttu-id="f703e-111">Dans le champ **Description**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f703e-111">In the **Description** field, enter a value.</span></span>

6. <span data-ttu-id="f703e-112">Entrez une date dans le champ **Date d’effet**.</span><span class="sxs-lookup"><span data-stu-id="f703e-112">In the **Effective date** field, enter a date.</span></span>

7. <span data-ttu-id="f703e-113">Dans le champ **Type**, choisissez si le régime de rémunération fixe est un régime de type **Structure**, **Niveau** ou **Échelon**.</span><span class="sxs-lookup"><span data-stu-id="f703e-113">In the **Type** field, select whether the fixed compensation plan is a **Band**, **Grade**, or **Step** plan.</span></span>

8. <span data-ttu-id="f703e-114">La case à cocher **Recommandation autorisée** sert de valeur par défaut pour toutes les actions ajoutées à ce régime dans un événement de processus.</span><span class="sxs-lookup"><span data-stu-id="f703e-114">The **Recommendation allowed** checkbox acts as a default value for any actions added to this plan in a Process event.</span></span> <span data-ttu-id="f703e-115">Le fait d’autoriser les recommandations vous permet d’ignorer le montant indicatif calculé lors du traitement de la rémunération.</span><span class="sxs-lookup"><span data-stu-id="f703e-115">Allowing recommendations enables you to override the calculated guideline amount when processing compensation.</span></span>

9. <span data-ttu-id="f703e-116">Le champ **Tolérance Hors de portée** vous permet de spécifier la manière dont vous souhaitez gérer les montants de rémunération se trouvant en dehors de la plage de structure de rémunération spécifiée pour le niveau donné.</span><span class="sxs-lookup"><span data-stu-id="f703e-116">The **Out of range tolerance** field allows you to specify how you want to handle compensation amounts that fall outside of the specified compensation structure range for the given level.</span></span> <span data-ttu-id="f703e-117">La définition du champ **Tolérance hors plage** sur **Aucun** vous permet d’utiliser n’importe quel montant de rémunération.</span><span class="sxs-lookup"><span data-stu-id="f703e-117">Setting the **Out of range tolerance** field to **None** allows you to use any compensation amount.</span></span> <span data-ttu-id="f703e-118">Si la tolérance est définie sur **Souple**, les utilisateurs sont avertis si le montant de rémunération est inférieur au montant minimal ou supérieur au montant maximal de point de référence pour ce niveau.</span><span class="sxs-lookup"><span data-stu-id="f703e-118">**Soft tolerance** warns users if the compensation amount is less than the minimum or greater than the maximum reference point amounts for that level.</span></span> <span data-ttu-id="f703e-119">Les utilisateurs peuvent ignorer l’avertissement et continuer.</span><span class="sxs-lookup"><span data-stu-id="f703e-119">Users can ignore the warning and continue.</span></span> <span data-ttu-id="f703e-120">Si la tolérance est définie sur **Absolu**, une erreur est générée si la rémunération de l’employé est en dehors des points de référence minimum et maximum pour ce niveau et la rémunération de l’employé est automatiquement ajustée pour se situer dans la marge.</span><span class="sxs-lookup"><span data-stu-id="f703e-120">**Hard tolerance** generates an error if an employee's compensation is outside the minimum and maximum reference points for the level and will automatically adjust the employee's compensation to fall within the range.</span></span>

10. <span data-ttu-id="f703e-121">Le champ **Règle d’embauche** calcule la rémunération d’un employé lors d’un événement de processus.</span><span class="sxs-lookup"><span data-stu-id="f703e-121">The **Hire rule** field calculates an employee's compensation during a process event.</span></span> <span data-ttu-id="f703e-122">Une **Règle d’embauche** en **Pourcentage** calcule une augmentation au prorata de la durée pendant laquelle le travailleur a été employé dans le cycle.</span><span class="sxs-lookup"><span data-stu-id="f703e-122">A **Hire rule** of **Percent** calculates an increase that's prorated for the length of the time the worker has been employed in the cycle.</span></span>

11. <span data-ttu-id="f703e-123">Tapez une valeur dans le champ **Devise**.</span><span class="sxs-lookup"><span data-stu-id="f703e-123">In the **Currency** field, type a value.</span></span>

12. <span data-ttu-id="f703e-124">Saisissez ou sélectionnez une valeur dans le champ **Conversion de taux de salaire**.</span><span class="sxs-lookup"><span data-stu-id="f703e-124">In the **Pay rate conversion** field, enter or select a value.</span></span>

13. <span data-ttu-id="f703e-125">Développez la section **Matrice d’utilisation de tranche**.</span><span class="sxs-lookup"><span data-stu-id="f703e-125">Expand the **Range utilization matrix** section.</span></span> <span data-ttu-id="f703e-126">Vous pouvez éventuellement ajouter des enregistrements d’utilisation de tranche pour que les employés atteignent la valeur médiane plus rapidement et atteignent le maximum de leur tranche moins vite.</span><span class="sxs-lookup"><span data-stu-id="f703e-126">Optionally, add range utilization records to get employees to their midpoint faster and slow them from reaching the maximum of their range.</span></span>

14. <span data-ttu-id="f703e-127">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f703e-127">Select **Save**.</span></span> <span data-ttu-id="f703e-128">Cela active le bouton **Paramétrer la rémunération**. Vous pouvez continuer à définir votre structure de rémunération pour le régime.</span><span class="sxs-lookup"><span data-stu-id="f703e-128">This enables the **Set up compensation** button and continue defining your compensation structure for the plan.</span></span>

15. <span data-ttu-id="f703e-129">Sélectionnez **Paramétrer la rémunération**.</span><span class="sxs-lookup"><span data-stu-id="f703e-129">Select **Set up compensation**.</span></span> <span data-ttu-id="f703e-130">Vous pouvez créer une structure de rémunération en utilisant l’une des trois méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f703e-130">You can create a compensation structure by using one of these three methods:</span></span>

    - <span data-ttu-id="f703e-131">Créer une structure entièrement nouvelle en sélectionnant un ensemble de points de référence et en ajoutant des niveaux pour créer votre propre structure.</span><span class="sxs-lookup"><span data-stu-id="f703e-131">Create a completely new structure by selecting a set of reference points and adding the levels to create your own structure.</span></span>
    - <span data-ttu-id="f703e-132">Copier une structure de rémunération en utilisant un plan existant comme point de départ et la modifier pour le nouveau plan.</span><span class="sxs-lookup"><span data-stu-id="f703e-132">Copy a compensation structure from an existing plan as a starting point and modify it for the new plan.</span></span>
    - <span data-ttu-id="f703e-133">Sélectionner une grille de rémunération existante.</span><span class="sxs-lookup"><span data-stu-id="f703e-133">Select an existing compensation grid.</span></span> <span data-ttu-id="f703e-134">Si un autre régime utilise déjà la grille de rémunération, l’autre régime reflète également les modifications apportées à la grille.</span><span class="sxs-lookup"><span data-stu-id="f703e-134">If another plan already uses the compensation grid, the other plan also reflects any changes you make to the grid.</span></span>

16. <span data-ttu-id="f703e-135">Sélectionnez **Créer une nouvelle matrice de rémunération à partir d’une matrice existante**.</span><span class="sxs-lookup"><span data-stu-id="f703e-135">Select **Create new from existing compensation matrix**.</span></span>

17. <span data-ttu-id="f703e-136">Saisissez ou sélectionnez une valeur dans le champ **Copier à partir de la grille**.</span><span class="sxs-lookup"><span data-stu-id="f703e-136">In the **Copy from grid** field, enter or select a value.</span></span> <span data-ttu-id="f703e-137">Vous pouvez éventuellement modifier le nom de la nouvelle grille de rémunération que vous créez en copiant la grille sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f703e-137">Optionally, you can change the name of the new compensation grid that you create by copying the selected grid.</span></span>

18. <span data-ttu-id="f703e-138">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f703e-138">Select **OK**.</span></span>

19. <span data-ttu-id="f703e-139">Sélectionnez **Modification en masse**.</span><span class="sxs-lookup"><span data-stu-id="f703e-139">Select **Mass change**.</span></span> <span data-ttu-id="f703e-140">Les **Modifications en masse** vous permettent de conserver les montants de matrice de rémunération en appliquant un pourcentage ou un montant fixe d’augmentation à un ou plusieurs niveaux ou points de référence.</span><span class="sxs-lookup"><span data-stu-id="f703e-140">**Mass change** allows you to maintain the compensation matrix amounts by applying a percent or flat amount increase to one or more levels or reference points.</span></span>

20. <span data-ttu-id="f703e-141">Entrez un nombre dans le champ **Montant d’ajustement**.</span><span class="sxs-lookup"><span data-stu-id="f703e-141">In the **Adjustment amount** field, enter a number.</span></span>

21. <span data-ttu-id="f703e-142">Dans la liste, cochez ou décochez toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="f703e-142">In the list, mark or unmark all rows.</span></span>

22. <span data-ttu-id="f703e-143">Cliquez sur **Appliquer à la grille**.</span><span class="sxs-lookup"><span data-stu-id="f703e-143">Click **Apply to grid**.</span></span>

23. <span data-ttu-id="f703e-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f703e-144">Close the page.</span></span> <span data-ttu-id="f703e-145">Après avoir créé la structure de rémunération, vous pouvez sélectionner les points de référence à utiliser comme point de contrôle pour le régime de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="f703e-145">After you create the compensation structure, you can select which of the reference points to use as the control point for the fixed compensation plan.</span></span> <span data-ttu-id="f703e-146">Le point de contrôle est utilisé pour calculer le coefficient de comparaison d’un employé.</span><span class="sxs-lookup"><span data-stu-id="f703e-146">The control point is used to calculate an employee's Compa Ratio.</span></span>

24. <span data-ttu-id="f703e-147">Saisissez ou sélectionnez une valeur dans le champ **Point de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="f703e-147">In the **Control point** field, enter or select a value.</span></span>

25. <span data-ttu-id="f703e-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f703e-148">Close the page.</span></span>

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a><span data-ttu-id="f703e-149">Créer une règle d’admissibilité pour le régime de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="f703e-149">Create an eligibility rule for the fixed compensation plan</span></span>

<span data-ttu-id="f703e-150">Vous ne pouvez pas affecter un régime de rémunération fixe à un employé tant que vous n’avez pas défini de règles d’admissibilité pour le régime.</span><span class="sxs-lookup"><span data-stu-id="f703e-150">You can't assign a fixed compensation plan to an employee until you define eligibility rules for the plan.</span></span>  

1. <span data-ttu-id="f703e-151">Sélectionnez **Règles d’admissibilité**.</span><span class="sxs-lookup"><span data-stu-id="f703e-151">Select **Eligibility rules**.</span></span>

2. <span data-ttu-id="f703e-152">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f703e-152">Select **New**.</span></span>

3. <span data-ttu-id="f703e-153">Saisissez ou sélectionnez une valeur dans le champ **Admissibilité**.</span><span class="sxs-lookup"><span data-stu-id="f703e-153">In the **Eligibility** field, enter a value.</span></span>

4. <span data-ttu-id="f703e-154">Dans le champ **Description**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f703e-154">In the **Description** field, enter a value.</span></span>

5. <span data-ttu-id="f703e-155">Entrez une date dans le champ **Date d’effet**.</span><span class="sxs-lookup"><span data-stu-id="f703e-155">In the **Effective date** field, enter a date.</span></span> <span data-ttu-id="f703e-156">Les régimes de rémunération fixe et variable utilisent des règles d’admissibilité.</span><span class="sxs-lookup"><span data-stu-id="f703e-156">Both fixed and variable compensation plans use eligibility rules.</span></span> <span data-ttu-id="f703e-157">Dans le champ **Type**, sélectionnez le type de régime.</span><span class="sxs-lookup"><span data-stu-id="f703e-157">In the **Type** field, select the type of plan.</span></span>

6. <span data-ttu-id="f703e-158">Dans le champ **Plan**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f703e-158">In the **Plan** field, enter or select a value.</span></span> <span data-ttu-id="f703e-159">Sélectionnez les critères que l’employé doit remplir pour prétendre à l’enregistrement dans un régime de rémunération.</span><span class="sxs-lookup"><span data-stu-id="f703e-159">Select the criteria an employee must meet in order to be eligible for the compensation plan.</span></span> <span data-ttu-id="f703e-160">Les critères peuvent inclure :</span><span class="sxs-lookup"><span data-stu-id="f703e-160">Criteria can include:</span></span>

    - <span data-ttu-id="f703e-161">**Département**</span><span class="sxs-lookup"><span data-stu-id="f703e-161">**Department**</span></span>
    - <span data-ttu-id="f703e-162">**Syndicat**</span><span class="sxs-lookup"><span data-stu-id="f703e-162">**Labor union**</span></span>
    - <span data-ttu-id="f703e-163">**Emplacement** (**Région de rémunération**)</span><span class="sxs-lookup"><span data-stu-id="f703e-163">**Location** (**Compensation region**)</span></span>
    - <span data-ttu-id="f703e-164">**Tâche**</span><span class="sxs-lookup"><span data-stu-id="f703e-164">**Job**</span></span>
    - <span data-ttu-id="f703e-165">**Fonction**</span><span class="sxs-lookup"><span data-stu-id="f703e-165">**Function**</span></span>
    - <span data-ttu-id="f703e-166">**Type de poste**</span><span class="sxs-lookup"><span data-stu-id="f703e-166">**Job type**</span></span>
    - <span data-ttu-id="f703e-167">**Niveau de rémunération**</span><span class="sxs-lookup"><span data-stu-id="f703e-167">**Compensation level**</span></span>
    
    <span data-ttu-id="f703e-168">L’employé doit remplir tous les critères spécifiés pour être admissible dans un régime de rémunération.</span><span class="sxs-lookup"><span data-stu-id="f703e-168">The employee must meet all specified criteria to be eligible for the compensation plan.</span></span> <span data-ttu-id="f703e-169">Si vous ne spécifiez aucun critère, tous les employés sont admissibles pour le régime de rémunération.</span><span class="sxs-lookup"><span data-stu-id="f703e-169">If you don't specify any criteria, all employees are eligible for the compensation plan.</span></span> <span data-ttu-id="f703e-170">Si un employé ne répond pas aux critères spécifiés dans la règle d’admissibilité, ou si une règle d’admissibilité n’a pas été spécifiée pour un régime de rémunération, ce régime de rémunération n’apparaît pas dans la recherche lorsque vous créez un enregistrement de rémunération fixe pour un employé.</span><span class="sxs-lookup"><span data-stu-id="f703e-170">If an employee doesn't meet the criteria specified in the eligibility rule, or an eligibility rule has not been specified for a compensation plan, the compensation plan won't appear in the lookup when you create a fixed compensation record for an employee.</span></span>

7. <span data-ttu-id="f703e-171">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f703e-171">Close the page.</span></span>

8. <span data-ttu-id="f703e-172">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f703e-172">Close the page.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]