---
title: Générer des rapports sur la Loi sur les soins abordables dans l'espace de travail Gestion des avantages
description: Ces rubriques décrivent comment Gestion des avantages vous aide à suivre les informations qui sont déclarées sur le formulaire 1095-B et le formulaire 1095-C pour le mandat de l'employeur de la Loi sur les soins abordables (ACA).
author: andreabichsel
manager: tfehr
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 2e4b250f4a059719067a9e19bbf3ce4aecc9bb1f
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112564"
---
# <a name="generate-aca-reports-in-benefits-management"></a><span data-ttu-id="5374f-103">Générer des rapports ACA dans Gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="5374f-103">Generate ACA reports in Benefits management</span></span>

<span data-ttu-id="5374f-104">Gestion des avantages vous aide à suivre les informations qui sont déclarées sur le formulaire 1095-B et le formulaire 1095-C pour le mandat de l'employeur de la Loi sur les soins abordables (ACA).</span><span class="sxs-lookup"><span data-stu-id="5374f-104">Benefits management helps you track information that is reported on Form 1095-B and Form 1095-C for the Affordable Care Act (ACA) employer mandate.</span></span> <span data-ttu-id="5374f-105">Comme la fonctionnalité de génération d’états ACA dans l'ancien espace de travail **Avantages**, cette fonctionnalité s'applique uniquement aux entités juridiques aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="5374f-105">Like the ACA reporting capability in the old **Benefits** workspace, this functionality applies only to legal entities in the United States.</span></span>

<span data-ttu-id="5374f-106">Pour utiliser cette fonctionnalité, vous devez d'abord activer **Gestion avancée des avantages**.</span><span class="sxs-lookup"><span data-stu-id="5374f-106">To use this functionality, you must first turn on **Advanced Benefits Management**.</span></span> <span data-ttu-id="5374f-107">Pour plus d'informations, y compris des mises en garde importantes sur la Gestion des avantages, voir [Activer ou désactiver la gestion des avantages](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span><span class="sxs-lookup"><span data-stu-id="5374f-107">For more information, including important caveats about Benefits management, see [Enable or disable Benefits management](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5374f-108">Vous pouvez utiliser la génération d’états ACA uniquement à partir de l'espace de travail **Gestion des avantages** ou de l'ancien espace de travail **Avantages**, pas les deux.</span><span class="sxs-lookup"><span data-stu-id="5374f-108">You can use ACA reporting only from either the **Benefits management** workspace or the old **Benefits** workspace, not from both.</span></span> <span data-ttu-id="5374f-109">Par exemple, si vous êtes passé à la Gestion des avantages, la génération d’états ACA est disponible uniquement à partir de l'espace de travail **Gestion des avantages**, pas de l'ancien espace de travail **Avantages**.</span><span class="sxs-lookup"><span data-stu-id="5374f-109">For example, if you switched to Benefits management, ACA reporting is available only from the **Benefits management** workspace, not from the old **Benefits** workspace.</span></span>
>
> <span data-ttu-id="5374f-110">Si vous passez à la Gestion des avantages au milieu d'une année d'inscription, vous devez configurer correctement les données des employés pour toute l'année dans la Gestion des avantages.</span><span class="sxs-lookup"><span data-stu-id="5374f-110">If you switch to Benefits management in the middle of an enrollment year, you must correctly configure employee data for the whole year in Benefits management.</span></span> <span data-ttu-id="5374f-111">De cette manière, vous avez la garantie de recevoir des informations de génération d’états précises pour toute l'année.</span><span class="sxs-lookup"><span data-stu-id="5374f-111">In this way, you ensure that you will receive accurate reporting information for the whole year.</span></span>

## <a name="getting-started"></a><span data-ttu-id="5374f-112">Mise en route</span><span class="sxs-lookup"><span data-stu-id="5374f-112">Getting started</span></span>

<span data-ttu-id="5374f-113">Pour suivre les informations sur les formulaires 1095, vous devez d'abord créer un ou plusieurs groupes de couverture liés à la Loi sur les soins abordables.</span><span class="sxs-lookup"><span data-stu-id="5374f-113">To track information for 1095 forms, first create one or more Affordable Care coverage groups.</span></span> <span data-ttu-id="5374f-114">Ces groupes indiquent les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5374f-114">These groups indicate the following information:</span></span>

- <span data-ttu-id="5374f-115">L'offre de protection qui a été fournie à un employé</span><span class="sxs-lookup"><span data-stu-id="5374f-115">The offer of coverage that was provided to an employee</span></span>
- <span data-ttu-id="5374f-116">La part de l'employé sur la prime mensuelle la moins coûteuse, si le coût est supérieur au seuil de pauvreté fédéral</span><span class="sxs-lookup"><span data-stu-id="5374f-116">The employee's share of the lowest-cost monthly premium, if the cost is above the federal poverty line</span></span>
- <span data-ttu-id="5374f-117">La mesure Safe Harbor utilisée par l'employeur, le cas échéant</span><span class="sxs-lookup"><span data-stu-id="5374f-117">The safe harbor that is used by the employer, if applicable</span></span>

<span data-ttu-id="5374f-118">Les groupes de couverture de soins abordables vous aident à gérer ces informations pour plusieurs dossiers d'employés qui présentent les mêmes conditions.</span><span class="sxs-lookup"><span data-stu-id="5374f-118">Affordable Care coverage groups help you manage this information for multiple employee records that have the same conditions.</span></span> <span data-ttu-id="5374f-119">Vous pouvez facilement attribuer des groupes à un ou plusieurs employés.</span><span class="sxs-lookup"><span data-stu-id="5374f-119">You can easily assign groups to one or more employees.</span></span>

### <a name="create-or-edit-an-affordable-care-coverage-group"></a><span data-ttu-id="5374f-120">Créer ou modifier un groupe de couverture de soins abordables</span><span class="sxs-lookup"><span data-stu-id="5374f-120">Create or edit an Affordable Care coverage group</span></span>

1. <span data-ttu-id="5374f-121">Dans l'espace de travail **Gestion des avantages**, sélectionnez **Groupe de couverture de soins abordables**.</span><span class="sxs-lookup"><span data-stu-id="5374f-121">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>

    ![Sélection d'un groupe de couverture de soins abordables](./media/hr-benefits-management-aca-coverage-group.png)

2. <span data-ttu-id="5374f-123">Sélectionnez **Nouveau** pour créer un nouveau groupe de couverture de soins abordables ou **Modifier** pour modifier un groupe existant.</span><span class="sxs-lookup"><span data-stu-id="5374f-123">Select **New** to create a new Affordable Care coverage group or **Edit** to change an existing group.</span></span>

    ![Sélectionner Nouveau ou Modifier](./media/hr-benefits-management-aca-new.png)

3. <span data-ttu-id="5374f-125">Définisse les champs suivants.</span><span class="sxs-lookup"><span data-stu-id="5374f-125">Set the following fields.</span></span>

    | <span data-ttu-id="5374f-126">Champ</span><span class="sxs-lookup"><span data-stu-id="5374f-126">Field</span></span> | <span data-ttu-id="5374f-127">Description </span><span class="sxs-lookup"><span data-stu-id="5374f-127">Description</span></span> |
    |---|---|
    | <span data-ttu-id="5374f-128">Nom</span><span class="sxs-lookup"><span data-stu-id="5374f-128">Name</span></span> | <span data-ttu-id="5374f-129">Entrez un nom pour le groupe.</span><span class="sxs-lookup"><span data-stu-id="5374f-129">Enter a name for the group.</span></span> |
    | <span data-ttu-id="5374f-130">Description </span><span class="sxs-lookup"><span data-stu-id="5374f-130">Description</span></span> | <span data-ttu-id="5374f-131">Permet d’entrer une description du groupe.</span><span class="sxs-lookup"><span data-stu-id="5374f-131">Enter a description of the group.</span></span> |
    | <span data-ttu-id="5374f-132">Offre de couverture</span><span class="sxs-lookup"><span data-stu-id="5374f-132">Offer of coverage</span></span> | <span data-ttu-id="5374f-133">La protection offerte aux employés, à leur conjoint ou partenaire et à leurs personnes à charge.</span><span class="sxs-lookup"><span data-stu-id="5374f-133">The coverage that is offered to employees, their spouse or partner, and their dependents.</span></span> |
    | <span data-ttu-id="5374f-134">Part de coût de l'employé</span><span class="sxs-lookup"><span data-stu-id="5374f-134">Employee share of cost</span></span> | <span data-ttu-id="5374f-135">Le montant qui incombe à l'employé.</span><span class="sxs-lookup"><span data-stu-id="5374f-135">The amount that the employee is responsible for.</span></span> |
    | <span data-ttu-id="5374f-136">Mesures Safe Harbor section 4980H applicables</span><span class="sxs-lookup"><span data-stu-id="5374f-136">Applicable section 4980H safe harbor</span></span> | <span data-ttu-id="5374f-137">La sphère de sécurité 4980H ou le code de secours de transition.</span><span class="sxs-lookup"><span data-stu-id="5374f-137">The 4980H safe harbor or transition relief code.</span></span> |
    | <span data-ttu-id="5374f-138">Mois de début du plan</span><span class="sxs-lookup"><span data-stu-id="5374f-138">Plan start month</span></span> | <span data-ttu-id="5374f-139">Sélectionnez le mois civil où commence l'année de votre régime de prestations.</span><span class="sxs-lookup"><span data-stu-id="5374f-139">Select the calendar month when your benefit plan year begins.</span></span> |
    | <span data-ttu-id="5374f-140">Groupe valable à partir de</span><span class="sxs-lookup"><span data-stu-id="5374f-140">Group valid from</span></span> | <span data-ttu-id="5374f-141">La première date à laquelle cet enregistrement est valide.</span><span class="sxs-lookup"><span data-stu-id="5374f-141">The first date when this record is valid.</span></span> |
    | <span data-ttu-id="5374f-142">Groupe valable jusqu'en</span><span class="sxs-lookup"><span data-stu-id="5374f-142">Group valid through</span></span> | <span data-ttu-id="5374f-143">La dernière date à laquelle cet enregistrement est valide.</span><span class="sxs-lookup"><span data-stu-id="5374f-143">The last date when this record is valid.</span></span> <span data-ttu-id="5374f-144">S'il n'y a pas de date d'expiration, saisissez **Jamais**.</span><span class="sxs-lookup"><span data-stu-id="5374f-144">If there is no expiration date, enter **Never**.</span></span> |

    ![Création d'un groupe de couverture](./media/hr-benefits-management-aca-new-group.png)

4. <span data-ttu-id="5374f-146">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5374f-146">Select **Save**.</span></span>

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a><span data-ttu-id="5374f-147">Affecter plusieurs employés à un groupe de couverture de soins abordables</span><span class="sxs-lookup"><span data-stu-id="5374f-147">Assign multiple employees to an Affordable Care coverage group</span></span>

1. <span data-ttu-id="5374f-148">Dans l'espace de travail **Gestion des avantages**, sélectionnez **Groupe de couverture de soins abordables**.</span><span class="sxs-lookup"><span data-stu-id="5374f-148">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>
2. <span data-ttu-id="5374f-149">Sélectionnez le groupe auquel affecter les employés.</span><span class="sxs-lookup"><span data-stu-id="5374f-149">Select the group to assign employees to.</span></span>
3. <span data-ttu-id="5374f-150">Sélectionnez **Affectation en masse**.</span><span class="sxs-lookup"><span data-stu-id="5374f-150">Select **Mass assignment**.</span></span>

    ![Sélection d'Affectation en masse](./media/hr-benefits-management-aca-mass-assignment.png)

4. <span data-ttu-id="5374f-152">Sélectionnez les employés dans la liste, puis sélectionnez **Attribuer**.</span><span class="sxs-lookup"><span data-stu-id="5374f-152">Select employees in the list, and then select **Assign**.</span></span>

    ![Affectation des employés sélectionnés à un groupe](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a><span data-ttu-id="5374f-154">Tenir à jour plusieurs versions des options de couverture</span><span class="sxs-lookup"><span data-stu-id="5374f-154">Maintain multiple versions of coverage options</span></span>

<span data-ttu-id="5374f-155">Vous pouvez tenir à jour plusieurs versions d'un groupe de couverture quelconque.</span><span class="sxs-lookup"><span data-stu-id="5374f-155">You can maintain multiple versions of any coverage group.</span></span> <span data-ttu-id="5374f-156">Lorsque quelque chose change dans votre organisation ou les avantages offerts, vous pouvez garder les informations du groupe à jour sans avoir à créer de nouveau groupe et à y réaffecter des employés.</span><span class="sxs-lookup"><span data-stu-id="5374f-156">When something changes in your organization or the benefits that are offered, you can keep the group's information up to date without having to create a new group and reassign employees to it.</span></span>

<span data-ttu-id="5374f-157">Une fois que vous avez créé des groupes de couverture de soins abordables, vous pouvez leur affecter en masse des employés.</span><span class="sxs-lookup"><span data-stu-id="5374f-157">After you've created Affordable Care coverage groups, you can mass-assign employees to them.</span></span> <span data-ttu-id="5374f-158">Vous pouvez également affecter individuellement des employés à des groupes et indiquer si les informations ACA font l'objet d'un suivi et d'une déclaration.</span><span class="sxs-lookup"><span data-stu-id="5374f-158">You can also individually assign employees to groups, and indicate whether ACA information is tracked and reported.</span></span>

<span data-ttu-id="5374f-159">Si vous n'avez pas à suivre et à signaler les informations ACA pour un employé, vous pouvez définir l'option **Couverture d'état** sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="5374f-159">If you don't have to track and report ACA information for an employee, you can set the **Report coverage** option to **No**.</span></span> <span data-ttu-id="5374f-160">Par exemple, vous pourriez avoir des employés à temps partiel qui n'ont pas besoin de rapports ACA.</span><span class="sxs-lookup"><span data-stu-id="5374f-160">For example, you might have part-time employees who don't require ACA reporting.</span></span>

### <a name="override-default-values-for-an-employee"></a><span data-ttu-id="5374f-161">Remplacer les valeurs par défaut pour un employé</span><span class="sxs-lookup"><span data-stu-id="5374f-161">Override default values for an employee</span></span>

<span data-ttu-id="5374f-162">Pour les employés affectés à un groupe de couverture de soins abordables, vous pouvez modifier les options suivantes pour tous les mois qui nécessitent des valeurs différentes :</span><span class="sxs-lookup"><span data-stu-id="5374f-162">For employees who are assigned to an Affordable Care coverage group, you can change the following options for any months that require different values:</span></span>

- <span data-ttu-id="5374f-163">Offre de couverture</span><span class="sxs-lookup"><span data-stu-id="5374f-163">Offer of coverage</span></span>
- <span data-ttu-id="5374f-164">Part de coût de l'employé</span><span class="sxs-lookup"><span data-stu-id="5374f-164">Employee share of cost</span></span>
- <span data-ttu-id="5374f-165">Mesures Safe Harbor section 4980H applicables</span><span class="sxs-lookup"><span data-stu-id="5374f-165">Applicable section 4980H safe harbor</span></span>

> [!NOTE]
> <span data-ttu-id="5374f-166">Pour les rapports ACA 2020, vous devez déclarer les codes postaux professionnels et personnels sur le formulaire 1095-C.</span><span class="sxs-lookup"><span data-stu-id="5374f-166">For 2020 ACA reports, you must report both work and home ZIP Codes on Form 1095-C.</span></span> <span data-ttu-id="5374f-167">Les valeurs sont automatiquement renseignées, en fonction des emplacements actifs actuels.</span><span class="sxs-lookup"><span data-stu-id="5374f-167">Values are automatically filled in, based on current active locations.</span></span> <span data-ttu-id="5374f-168">Si l'un des deux emplacements était différent pendant une partie de l'année, vous devez remplacer la valeur.</span><span class="sxs-lookup"><span data-stu-id="5374f-168">If either location was different during any part of the year, you must override the value.</span></span> <span data-ttu-id="5374f-169">Le champ **Code postal** (ligne 17) du rapport 1095-C est renseigné uniquement si le code **Offre de couverture** va de **1 L** à **1Q**, comme suit :</span><span class="sxs-lookup"><span data-stu-id="5374f-169">The **ZIP Code** field (line 17) of the 1095-C report is filled in only if the **Offer of coverage** code contains **1L** through **1Q**, as follows:</span></span>
>
> - <span data-ttu-id="5374f-170">**1L, 1M ou 1N :** Le code postal de la résidence principale</span><span class="sxs-lookup"><span data-stu-id="5374f-170">**1L, 1M, or 1N:** The primary residence ZIP Code</span></span>
> - <span data-ttu-id="5374f-171">**1O, 1P, 1Q :** Le code postal de l'emploi principal</span><span class="sxs-lookup"><span data-stu-id="5374f-171">**1O, 1P, 1Q:** The primary work ZIP Code</span></span>

<span data-ttu-id="5374f-172">Pour saisir des exceptions pour les valeurs d'un groupe de couverture de soins abordables, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5374f-172">To enter exceptions for any values of an Affordable Care coverage group, follow these steps.</span></span>

1. <span data-ttu-id="5374f-173">Dans l’espace de travail **Gestion du personnel**, sélectionnez **Liens**, puis **Collaborateurs**.</span><span class="sxs-lookup"><span data-stu-id="5374f-173">In the **Personnel management** workspace, select **Links**, and then select **Workers**.</span></span>
2. <span data-ttu-id="5374f-174">Sélectionnez l'employé dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5374f-174">Select the employee in the list.</span></span>
3. <span data-ttu-id="5374f-175">Sur l'onglet **Emploi**, dans la section **Plus d'information**, sélectionnez **Couverture de soins abordables**.</span><span class="sxs-lookup"><span data-stu-id="5374f-175">On the **Employment** tab, in the **More information** section, select **Affordable Care coverage**.</span></span>

    ![Changer les options pour un employé](./media/hr-benefits-management-aca-change-single-employee.png)

4. <span data-ttu-id="5374f-177">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="5374f-177">Select **Edit**.</span></span>
5. <span data-ttu-id="5374f-178">Pour chaque mois nécessitant des modifications, activez la case à cocher **Remplacer par défaut**, puis modifiez les autres valeurs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="5374f-178">For each month that requires changes, select the **Override default** check box, and then change the other values as required.</span></span>

    ![Remplacer les valeurs par défaut](./media/hr-benefits-management-aca-override-default.png)

6. <span data-ttu-id="5374f-180">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5374f-180">Select **Save**.</span></span>

## <a name="report-health-care-coverage"></a><span data-ttu-id="5374f-181">État sur la couverture des soins de santé</span><span class="sxs-lookup"><span data-stu-id="5374f-181">Report health care coverage</span></span>

<span data-ttu-id="5374f-182">Vous devez suivre toute couverture de soins de santé auto-assurée parrainée par l'employeur pour les employés à temps plein et à temps partiel.</span><span class="sxs-lookup"><span data-stu-id="5374f-182">You must track any employer-sponsored, self-insured health care coverage for full-time and part-time employees.</span></span> <span data-ttu-id="5374f-183">Vous devez inclure chaque employé, ainsi que leurs personnes à charge, sur le rapport 1095-C pour les mois où ils étaient couverts.</span><span class="sxs-lookup"><span data-stu-id="5374f-183">Include each employee, together with their dependents, on the 1095-C report for the months when they were covered.</span></span>

<span data-ttu-id="5374f-184">Pour indiquer si un régime de prestations sociales doit être déclaré, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5374f-184">To indicate whether a benefit plan must be reported, follow these steps.</span></span>

1. <span data-ttu-id="5374f-185">Dans l'espace de travail **Gestion des avantages**, sélectionnez **Régimes de prestations**.</span><span class="sxs-lookup"><span data-stu-id="5374f-185">In the **Benefits management** workspace, select **Benefit plans**.</span></span>
2. <span data-ttu-id="5374f-186">Sélectionnez le régime de prestations à signaler.</span><span class="sxs-lookup"><span data-stu-id="5374f-186">Select the benefit plan to report.</span></span>
3. <span data-ttu-id="5374f-187">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="5374f-187">Select **Edit**.</span></span>
4. <span data-ttu-id="5374f-188">Définissez l'option **Déclaré en vertu de la Loi sur les soins abordables** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="5374f-188">Set the **Reported under the Affordable Care Act** option to **Yes**.</span></span>

    ![Génération d'états sur la couverture des soins de santé](./media/hr-benefits-management-aca-report-coverage.png)

5. <span data-ttu-id="5374f-190">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5374f-190">Select **Save**.</span></span>

<span data-ttu-id="5374f-191">Si un employé choisit la couverture des soins de santé pour une personne à charge, la période de couverture de la personne à charge est déterminée selon la date à laquelle elle a été inscrite ou retirée.</span><span class="sxs-lookup"><span data-stu-id="5374f-191">If an employee chooses health care coverage for a dependent, the dependent's coverage period is determined by the date when the dependent was enrolled or removed.</span></span> <span data-ttu-id="5374f-192">Les dates de couverture pour les personnes à charge sont automatiquement calculées en fonction de la période pendant laquelle la personne à charge était admissible et active dans un régime au cours de l'année d'adhésion.</span><span class="sxs-lookup"><span data-stu-id="5374f-192">Coverage dates for dependents are automatically calculated based on the period when the dependent was eligible and active in a plan during the enrollment year.</span></span>

## <a name="generate-1095-b-and-1095-c-forms"></a><span data-ttu-id="5374f-193">Générer des formulaires 1095-B et 1095-C</span><span class="sxs-lookup"><span data-stu-id="5374f-193">Generate 1095-B and 1095-C forms</span></span>

<span data-ttu-id="5374f-194">Vous pouvez générer les formulaires ACA 1095-B et 1095-C et les distribuer à chacun de vos employés.</span><span class="sxs-lookup"><span data-stu-id="5374f-194">You can generate ACA 1095-B and 1095-C forms, and then distribute them to each of your employees.</span></span> <span data-ttu-id="5374f-195">Vous pouvez également générer électroniquement le formulaire 1095-C et les fichiers de transmission 1094-C correspondants à envoyer à l'Internal Revenue Service (IRS).</span><span class="sxs-lookup"><span data-stu-id="5374f-195">You can also electronically generate Form 1095-C and the corresponding 1094-C transmittal files to send to the Internal Revenue Service (IRS).</span></span>

1. <span data-ttu-id="5374f-196">Dans l'espace de travail **Gestion des avantages**, sélectionnez **Formulaire ACA 1095-B** ou **Formulaire ACA 1095-C**.</span><span class="sxs-lookup"><span data-stu-id="5374f-196">In the **Benefits management** workspace, select **ACA 1095-B form** or **ACA 1095-C form**.</span></span>
2. <span data-ttu-id="5374f-197">Modifiez les paramètres selon vos besoins, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5374f-197">Change the parameters as required, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5374f-198">Si vous imprimez des formulaires 1095-C pour plus de 500 employés, vous recevrez plusieurs fichiers PDF.</span><span class="sxs-lookup"><span data-stu-id="5374f-198">If you're printing 1095-C forms for more than 500 employees, you will receive more than one PDF file.</span></span> <span data-ttu-id="5374f-199">Nous vous recommandons d'augmenter la valeur du champ **Taille maximale du fichier en mégaoctets** sur la page **Paramètres de gestion des documents** sur **150**.</span><span class="sxs-lookup"><span data-stu-id="5374f-199">We recommend that you increase the value of the **Maximum file size in megabytes** field on the **Document management parameters** page to **150**.</span></span> <span data-ttu-id="5374f-200">(Pour ouvrir rapidement cette page, vous pouvez utiliser le champ de recherche de la barre de navigation.)</span><span class="sxs-lookup"><span data-stu-id="5374f-200">(To quickly open that page, you can use the search field on the navigation bar.)</span></span>
    >
    > ![Modification de la taille maximale du fichier](./media/hr-benefits-management-aca-maximum-file-size.png)

3. <span data-ttu-id="5374f-202">Pour vérifier l'état de vos rapports et les afficher, utilisez le champ de recherche de la barre de navigation pour ouvrir la page **Tâches de gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="5374f-202">To check the status of your reports and view them, use the search field on the navigation bar to open the **Electronic reporting jobs** page.</span></span>

    ![Recherche de la page Tâches de gestion des états électroniques](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. <span data-ttu-id="5374f-204">Sélectionnez le rapport à afficher, puis sélectionnez **Afficher les fichiers**.</span><span class="sxs-lookup"><span data-stu-id="5374f-204">Select the report to view, and then select **Show files**.</span></span>

    ![Affichage des fichiers](./media/hr-benefits-management-aca-show-files.png)

5. <span data-ttu-id="5374f-206">Cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="5374f-206">Select **Open**.</span></span>

    ![Ouverture d'un fichier](./media/hr-benefits-management-aca-open-file.png)

6. <span data-ttu-id="5374f-208">Dans la barre de notification qui apparaît au bas de la fenêtre du navigateur, ouvrez le fichier zip, puis sélectionnez le rapport.</span><span class="sxs-lookup"><span data-stu-id="5374f-208">From the Notification bar that appears at the bottom of the browser window, open the zip file, and then select the report.</span></span> <span data-ttu-id="5374f-209">Vous pouvez afficher ou imprimer le fichier PDF.</span><span class="sxs-lookup"><span data-stu-id="5374f-209">You can view or print the PDF file.</span></span>

    ![Exemple de formulaire 1095-C](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a><span data-ttu-id="5374f-211">Afficher les informations de couverture ACA</span><span class="sxs-lookup"><span data-stu-id="5374f-211">View ACA coverage information</span></span>

<span data-ttu-id="5374f-212">La page **Couverture du collaborateur en matière de soins abordables** affiche les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5374f-212">The **Worker Affordable Care coverage** page shows the following information:</span></span>

- <span data-ttu-id="5374f-213">Employés affectés à chaque groupe de protection</span><span class="sxs-lookup"><span data-stu-id="5374f-213">Employees who are assigned to each coverage group</span></span>
- <span data-ttu-id="5374f-214">Employés qui ne doivent pas être inclus dans un rapport</span><span class="sxs-lookup"><span data-stu-id="5374f-214">Employees who don't have to be included on a report</span></span>
- <span data-ttu-id="5374f-215">Employés non affectés</span><span class="sxs-lookup"><span data-stu-id="5374f-215">Unassigned employees</span></span>

<span data-ttu-id="5374f-216">Pour afficher ces informations, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5374f-216">To view this information, follow these steps.</span></span>

1. <span data-ttu-id="5374f-217">Dans l'espace de travail **Gestion des avantages**, sélectionnez **Couverture du collaborateur en matière de soins abordables**.</span><span class="sxs-lookup"><span data-stu-id="5374f-217">In the **Benefits management** workspace, select **Worker Affordable Care coverage**.</span></span>
2. <span data-ttu-id="5374f-218">Sélectionnez un groupe dans le champ **Nom de groupe**.</span><span class="sxs-lookup"><span data-stu-id="5374f-218">In the **Group name** field, select a group.</span></span>

    ![Affichage de la couverture ACA](./media/hr-benefits-management-aca-view-coverage.png)

<span data-ttu-id="5374f-220">Si l'une des valeurs par défaut du groupe de couverture lié aux soins abordables est remplacée, un astérisque apparaît en regard de la valeur modifiée.</span><span class="sxs-lookup"><span data-stu-id="5374f-220">If any default values from the Affordable Care coverage group have been overridden, an asterisk appears next to the value that was changed.</span></span> <span data-ttu-id="5374f-221">Si les valeurs des 12 mois sont identiques et ne sont pas remplacées, la valeur apparaît dans la colonne **Tous les 12 mois**.</span><span class="sxs-lookup"><span data-stu-id="5374f-221">If the values for all 12 months are the same and haven't been overridden, the value appears in the **All 12 months** column.</span></span>

<span data-ttu-id="5374f-222">Vous pouvez afficher les employés qui sont marqués comme non déclarables à l'ACA et qui n'auront pas besoin d'un formulaire 1095-C.</span><span class="sxs-lookup"><span data-stu-id="5374f-222">You can view employees who are marked as not ACA-reportable, and who won't require a Form 1095-C.</span></span> <span data-ttu-id="5374f-223">Dans le champ **Filtrer par**, sélectionnez **À ne pas déclarer dans le cadre de la loi sur les soins abordables**.</span><span class="sxs-lookup"><span data-stu-id="5374f-223">In the **Filter by** field, select **Not ACA reportable**.</span></span>

<span data-ttu-id="5374f-224">Vous pouvez afficher les employés qui ne sont pas affectés à un groupe ou qui sont affectés à un groupe expiré.</span><span class="sxs-lookup"><span data-stu-id="5374f-224">You can view employees who aren't assigned to a group, or who are assigned to an expired group.</span></span> <span data-ttu-id="5374f-225">Dans le champ **Filtrer par**, sélectionnez **Groupe non attribué ou expiré**.</span><span class="sxs-lookup"><span data-stu-id="5374f-225">In the **Filter by** field, select **Unassigned or expired group**.</span></span>

### <a name="export-to-excel"></a><span data-ttu-id="5374f-226">Exporter vers Excel</span><span class="sxs-lookup"><span data-stu-id="5374f-226">Export to Excel</span></span>

<span data-ttu-id="5374f-227">Pour exporter l'une des listes vers Microsoft Excel, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5374f-227">To export any of the lists to Microsoft Excel, follow these steps.</span></span>

1. <span data-ttu-id="5374f-228">Sélectionnez le bouton **Ouvrir dans Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="5374f-228">Select the **Open in Microsoft Office** button.</span></span>
2. <span data-ttu-id="5374f-229">Sélectionnez **Table temporaire HCM Human Resources à usage interne**.</span><span class="sxs-lookup"><span data-stu-id="5374f-229">Select **HCM Human Resources temporary table for internal use**.</span></span>
3. <span data-ttu-id="5374f-230">Sélectionnez **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="5374f-230">Select **Download**.</span></span>

### <a name="view-aca-reportable-dependents"></a><span data-ttu-id="5374f-231">Afficher les personnes à charge déclarables à l'ACA</span><span class="sxs-lookup"><span data-stu-id="5374f-231">View ACA-reportable dependents</span></span>

<span data-ttu-id="5374f-232">Si vous devez déclarer des personnes prises en charge par une couverte personnelle employeur, vous pouvez également consulter qui sont couvertes par les régimes d'avantages sociaux avec la mention **Déclarer dans le cadre de la loi sur les soins abordables**.</span><span class="sxs-lookup"><span data-stu-id="5374f-232">If you must report covered individuals because you provide self-insured coverage, you can view dependents who are covered under benefit plans that are marked as **ACA reportable**.</span></span> <span data-ttu-id="5374f-233">Sélectionnez **Afficher la couverture des personnes à charge** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="5374f-233">On the Action Pane, select **View Dependent coverage**.</span></span>

![Affichage de la couverture des personnes à charge](./media/hr-benefits-management-aca-view-dependent-coverage.png)

<span data-ttu-id="5374f-235">Les informations de couverture pour les personnes à charge de l'employé sont affichées.</span><span class="sxs-lookup"><span data-stu-id="5374f-235">Coverage information for the employee's dependents is shown.</span></span>

![Couverture des personnes à charge](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> <span data-ttu-id="5374f-237">La page affiche uniquement les régimes d'avantages qui sont marqués comme **ACA déclarables**.</span><span class="sxs-lookup"><span data-stu-id="5374f-237">The page shows only benefits plans that are marked as **ACA reportable**.</span></span>
