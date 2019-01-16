---
title: "Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (14 décembre 2018)"
description: "Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version actuelle de Microsoft Dynamics 365 for Talent Core HR."
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 844c23fc908c962203e644f1154cc480425d830b
ms.openlocfilehash: 7d2866923efd7f115ad5290f35ed4fcac5e47573
ms.contentlocale: fr-fr
ms.lasthandoff: 12/18/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-14-2018"></a><span data-ttu-id="4437c-103">Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (14 décembre 2018)</span><span class="sxs-lookup"><span data-stu-id="4437c-103">What's new or changed in Dynamics 365 for Talent Core HR (December 14, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4437c-104">**Version 8.1.2085**</span><span class="sxs-lookup"><span data-stu-id="4437c-104">**Build 8.1.2085**</span></span>

<span data-ttu-id="4437c-105">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.</span><span class="sxs-lookup"><span data-stu-id="4437c-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="4437c-106">Modifications</span><span class="sxs-lookup"><span data-stu-id="4437c-106">Changes</span></span>

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a><span data-ttu-id="4437c-107">États-Unis - Prise en charge de la Loi sur les soins abordables (ACA) pour les formulaires 1095-B et 1095-C de l'exercice fiscal 2018</span><span class="sxs-lookup"><span data-stu-id="4437c-107">US - ACA (Affordable Care Act) support for tax year 2018 1095-B and 1095-C forms</span></span>

<span data-ttu-id="4437c-108">Chaque année, les ALE (Grands employeurs applicables) doivent fournir à chaque employé à temps plein un formulaire 1095-C.</span><span class="sxs-lookup"><span data-stu-id="4437c-108">Each year, Applicable Large Employers (ALEs) must provide each full-time employees with a 1095-C.</span></span> <span data-ttu-id="4437c-109">De plus, si l'employeur fournit une couverture personnelle, il doit fournir le formulaire 1095-C (s'il s'agit d'un ALE) et un formulaire 1095-B (s'il s'agit d'une petite société) à tous les employés, à temps plein ou à temps partiel, couvert par l'un leurs plans de santé.</span><span class="sxs-lookup"><span data-stu-id="4437c-109">In addition, if the employer provides self-insured coverage they must provide the 1095-C (if they are an ALE) and a 1095-B (if they are a small employer) to any employee, full-time or part-time, covered under one of their offered health plans.</span></span> <span data-ttu-id="4437c-110">Cette fonctionnalité fournit des écrans imprimables pour les formulaires 1095-C et 1095-B.</span><span class="sxs-lookup"><span data-stu-id="4437c-110">This feature provides printable forms for both the 1095-C and 1095-B.</span></span>

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a><span data-ttu-id="4437c-111">Pendant l'importation, le champ SubmittedByPersonId sur HcmPerfJournalEntity est ignoré</span><span class="sxs-lookup"><span data-stu-id="4437c-111">During import SubmittedByPersonId field on HcmPerfJournalEntity is ignored</span></span>

<span data-ttu-id="4437c-112">Lors de l'importation/exportation des entrées du journal de performances, le champ **Soumis par** est ignoré.</span><span class="sxs-lookup"><span data-stu-id="4437c-112">When importing/exporting performance journal entries, the **Submitted by** field is ignored.</span></span> <span data-ttu-id="4437c-113">Avec cette modification, la valeur **importé/exporté** reflète la valeur dans le tableau pendant l'exportation, lorsque l'importation du système est mis à jour avec la valeur fournie dans le fichier d'importation.</span><span class="sxs-lookup"><span data-stu-id="4437c-113">With this change, the value **imported/exported** will reflect the value in the table during the export, when importing the system will be updated with the value supplied in the import file.</span></span>

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a><span data-ttu-id="4437c-114">L'onglet Analyses de l'espace de travail « Congés et absences » affiche l'erreur « OpenConnectionError » pour les rôles d'administrateur non système</span><span class="sxs-lookup"><span data-stu-id="4437c-114">Analytics tab on 'Leave and absence' workspace displays "OpenConnectionError" error for non-system Admin roles</span></span>

<span data-ttu-id="4437c-115">Avec cette mise à jour, aucune erreur n'est émise lorsque vous ouvrez l'onglet **Analyses** de l'espace de travail **Congés et absences**.</span><span class="sxs-lookup"><span data-stu-id="4437c-115">With this update, no errors will be issued when opening the **Analytics** tab on the **Leave and Absence** workspace.</span></span>

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="4437c-116">L'exploration de Libre-service employé, Hiérarchie des postes, depuis la vignette échoue à obtenir un nœud parent</span><span class="sxs-lookup"><span data-stu-id="4437c-116">Employee self-service, Position Hierarchy drill-down from tile fails to get parent node</span></span>

<span data-ttu-id="4437c-117">Une modification a été apportée pour corriger l'erreur « L'obtention du nœud parent a échoué » lorsque la hiérarchie des postes a été personnalisée pour s'afficher sur un espace de travail existant et qu'un poste est sélectionné dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="4437c-117">A change has been made to correct the error "Getting the parent node failed" when the position hierarchy has been personalized to appear on an existing workspace and a position is selected in the hierarchy.</span></span>  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a><span data-ttu-id="4437c-118">Doit être administrateur système pour afficher l'onglet Paie sur la page Poste</span><span class="sxs-lookup"><span data-stu-id="4437c-118">Must be System Admin to see the Payroll tab in the Position page</span></span>

<span data-ttu-id="4437c-119">Une modification a été apportée pour inclure les éléments de sécurité corrects dans le privilège existant : « Tenir à jour les détails sur les collaborateurs et les postes de la paie ».</span><span class="sxs-lookup"><span data-stu-id="4437c-119">A change has been made to include the correct security elements in the existing privilege: "Maintain payroll worker and position detail".</span></span> <span data-ttu-id="4437c-120">Avec cette modification, par défaut, l'administrateur de paie a accès aux champs Paie de la page Poste.</span><span class="sxs-lookup"><span data-stu-id="4437c-120">With this change, by default, the Payroll Administrator will have access to the Payroll fields on the Position page.</span></span>

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a><span data-ttu-id="4437c-121">Erreur lors de la soumission de l'évaluation des performances au responsable et l'espace réservé %Reviews.PerfPeriod% est utilisé dans les instructions de soumission</span><span class="sxs-lookup"><span data-stu-id="4437c-121">Error when submitting performance review to manager and the %Reviews.PerfPeriod% placeholder is used in the Submission instructions</span></span>

<span data-ttu-id="4437c-122">Une modification a été apportée pour corriger l'erreur « Référence null » lors de l'utilisation de l'espace réservé %Reviews.PerfPeriod% dans les instructions de soumission.</span><span class="sxs-lookup"><span data-stu-id="4437c-122">A change has been made that corrects the "Null Reference" error when using the %Reviews.PerfPeriod% placeholder in the Submission instructions.</span></span>

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a><span data-ttu-id="4437c-123">l'état Power BI sur la main-d'œuvre affiche une erreur lorsque la date d'ancienneté du collaborateur est un jour intercalaire</span><span class="sxs-lookup"><span data-stu-id="4437c-123">Workforce Power BI report shows error when worker seniority date is a leap day</span></span>

<span data-ttu-id="4437c-124">Avec cette modification, les jours intercalaires sont maintenant pris en charge dans Power BI.</span><span class="sxs-lookup"><span data-stu-id="4437c-124">With this change, leap days are now supported in Power BI.</span></span>

### <a name="integration-between-core-hr-and-attract"></a><span data-ttu-id="4437c-125">Intégration entre Core HR et Attract</span><span class="sxs-lookup"><span data-stu-id="4437c-125">Integration between Core HR and Attract</span></span>

<span data-ttu-id="4437c-126">Une modification a été apportée pour mettre à jour l'intégration entre Core HR et Attract concernant les candidats à embaucher.</span><span class="sxs-lookup"><span data-stu-id="4437c-126">A change has been made to update the integration between Core HR and Attract related to candidates to hire.</span></span> <span data-ttu-id="4437c-127">Pour que les candidats à embaucher soient visibles dans l'espace de travail **Gestion du personnel**, les entités CDS pour les applications (CDS 2.0) suivantes sont utilisés :</span><span class="sxs-lookup"><span data-stu-id="4437c-127">For candidates to hire to be visible in the **Personnel Management** workspace, the following CDS for Apps (CDS 2.0) entities are used:</span></span>

<span data-ttu-id="4437c-128">Candidature</span><span class="sxs-lookup"><span data-stu-id="4437c-128">Job Application</span></span>
- <span data-ttu-id="4437c-129">La raison du statut doit être définie sur Offre acceptée</span><span class="sxs-lookup"><span data-stu-id="4437c-129">Status Reason needs to be set to Offer Accepted</span></span>
-   <span data-ttu-id="4437c-130">Fournit le candidat et l'offre d'emploi</span><span class="sxs-lookup"><span data-stu-id="4437c-130">Provides Candidate and Job Opening</span></span>

<span data-ttu-id="4437c-131">Candidat</span><span class="sxs-lookup"><span data-stu-id="4437c-131">Candidate</span></span>
-   <span data-ttu-id="4437c-132">Fournit des informations sur le candidat</span><span class="sxs-lookup"><span data-stu-id="4437c-132">Provides Candidate information</span></span>

<span data-ttu-id="4437c-133">Offre d'emploi</span><span class="sxs-lookup"><span data-stu-id="4437c-133">Job Opening</span></span>
-   <span data-ttu-id="4437c-134">Fournit l'ID de l'offre d'emploi et les participants à l'offre d'emploi</span><span class="sxs-lookup"><span data-stu-id="4437c-134">Provides Job Opening ID and Job Opening Participants</span></span>

<span data-ttu-id="4437c-135">Participants à l'offre d'emploi</span><span class="sxs-lookup"><span data-stu-id="4437c-135">Job Opening Participants</span></span>
-   <span data-ttu-id="4437c-136">Fournit le responsable de l'embauche</span><span class="sxs-lookup"><span data-stu-id="4437c-136">Provides Hiring Manager</span></span>

<span data-ttu-id="4437c-137">Lorsqu'un candidat est ajouté à Gestion du personnel, le candidat peuvent être désormais également ignoré à l'aide d'une nouvelle option disponible sur la fiche du candidat.</span><span class="sxs-lookup"><span data-stu-id="4437c-137">When a candidate is added to Personnel Management, the candidate can now also be dismissed using a new option available on the candidate card.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="4437c-138">Prochainement</span><span class="sxs-lookup"><span data-stu-id="4437c-138">Coming soon</span></span>

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a><span data-ttu-id="4437c-139">Congés et absences : Futurs soldes et prévisions de congés</span><span class="sxs-lookup"><span data-stu-id="4437c-139">Leave and absence: Future leave and forecasting leave balances</span></span>

<span data-ttu-id="4437c-140">Les modifications apportées pour autoriser les employés à prévoir des congés et à faire de futures demandes de congés sans répercussion sur leur solde actuel de congés modifient également la façon dont les soldes de congés sont affichés.</span><span class="sxs-lookup"><span data-stu-id="4437c-140">With the changes being made to allow for employees to forecast time off and request future time off requests without impacting their current time off balances, the way the time off balances are displayed is also changing.</span></span> 

<span data-ttu-id="4437c-141">Le solde disponible affiché actuellement correspond à la quantité de congés disponible pour les demandes, y compris les régularisations à ce jour et toutes les demandes de congés approuvées à la fin du temps.</span><span class="sxs-lookup"><span data-stu-id="4437c-141">The available balance currently displayed is the amount of time off available for requests including accruals through today and all approved leave requests to the end of time.</span></span> 

<span data-ttu-id="4437c-142">Lorsque la capacité à prévoir sera activée, le solde affiché deviendra le solde actuel de congés, y compris les régularisations à ce jour et les demandes à ce jour.</span><span class="sxs-lookup"><span data-stu-id="4437c-142">When the ability to forecast is released, the balance displayed changes to  be the current balance of time off including accruals through today and requests through today.</span></span> <span data-ttu-id="4437c-143">Les employés et les responsables verront ces soldes mis à jour dans le libre-service employé et responsable sur la fiche **Congés** et la fenêtre **Soldes des congés**.</span><span class="sxs-lookup"><span data-stu-id="4437c-143">Employees and managers will see these updated balances in employee and manager self-service on the **Time off** card and in the **Time off balances** window.</span></span> <span data-ttu-id="4437c-144">Les responsables des RH auront accès à ces soldes mis à jour dans l'espace de travail **Personnes** et dans la fenêtre **Plans de congés affectés** de l'employé.</span><span class="sxs-lookup"><span data-stu-id="4437c-144">HR managers will see these updated balances in the **People** workspace and in the employee’s **Assigned leave plans** window.</span></span>

## <a name="known-issue"></a><span data-ttu-id="4437c-145">Problème connu</span><span class="sxs-lookup"><span data-stu-id="4437c-145">Known issue</span></span>

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a><span data-ttu-id="4437c-146">Erreurs de mise en correspondance dans l'intégration à Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4437c-146">Mapping errors in the integration with Finance and Operations</span></span>

<span data-ttu-id="4437c-147">Les problèmes suivants ont été identifiés dans le modèle actuel d'intégration de Talent à Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4437c-147">The following issues have been identified in the current template for integrating Talent with Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="4437c-148">Un nouveau modèle sera publié prochainement et appliqué à tous les nouveaux projets d'intégration qui seront créés.</span><span class="sxs-lookup"><span data-stu-id="4437c-148">A new template will be published soon and will be applied to all new integration projects that are created.</span></span> <span data-ttu-id="4437c-149">Pour les projets d'intégration existants, les mises en correspondance de tâches peuvent être mises à jour.</span><span class="sxs-lookup"><span data-stu-id="4437c-149">For existing integration projects, the task mappings can be updated.</span></span> <span data-ttu-id="4437c-150">Pour plus d'informations sur les mises en correspondance mises à jour, voir le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="4437c-150">Refer to the following table for updated mappings.</span></span> 

>[!NOTE]
> <span data-ttu-id="4437c-151">La tâche Attribution de postes d'une mission au poste parent des missions n'intègre pas les données.</span><span class="sxs-lookup"><span data-stu-id="4437c-151">The Job Positions to Positions Parent Job Assignment task does not integrate data.</span></span> <span data-ttu-id="4437c-152">Il s'agit d'un problème qui fait actuellement l'objet de recherches.</span><span class="sxs-lookup"><span data-stu-id="4437c-152">This is an issue that is currently being researched.</span></span> <span data-ttu-id="4437c-153">Il n'existe aucune solution dans la mise en correspondance actuelle.</span><span class="sxs-lookup"><span data-stu-id="4437c-153">There is no workaround in the current mapping.</span></span> 

<span data-ttu-id="4437c-154">La tâche Départements à unité opérationnelle nécessite que les mises en correspondance suivantes soient mises à jour.</span><span class="sxs-lookup"><span data-stu-id="4437c-154">The Departments to Operating unit task needs the following mappings updated.</span></span>

| <span data-ttu-id="4437c-155">Champ source existant</span><span class="sxs-lookup"><span data-stu-id="4437c-155">Existing source field</span></span>          | <span data-ttu-id="4437c-156">Nouveau champ source</span><span class="sxs-lookup"><span data-stu-id="4437c-156">New source field</span></span> |
| -------------------------------|------------------|
| <span data-ttu-id="4437c-157">cdm_description (Description)</span><span class="sxs-lookup"><span data-stu-id="4437c-157">cdm_description (Description)</span></span>  | <span data-ttu-id="4437c-158">cdm_name (Nom)</span><span class="sxs-lookup"><span data-stu-id="4437c-158">cdm_name (Name)</span></span>  |

<span data-ttu-id="4437c-159">Une mise en correspondance supplémentaire doit également être ajoutée.</span><span class="sxs-lookup"><span data-stu-id="4437c-159">An additional mapping also needs to be added.</span></span> <span data-ttu-id="4437c-160">Sélectionnez le dernier champ **Aucun** pour ajouter la mise en correspondance suivante.</span><span class="sxs-lookup"><span data-stu-id="4437c-160">Select the last **None** field to add the following mapping.</span></span>

| <span data-ttu-id="4437c-161">Champ source</span><span class="sxs-lookup"><span data-stu-id="4437c-161">Source field</span></span>                   | <span data-ttu-id="4437c-162">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="4437c-162">Destination field</span></span>    |
| -------------------------------|----------------------|
| <span data-ttu-id="4437c-163">cdm_description (Description)</span><span class="sxs-lookup"><span data-stu-id="4437c-163">cdm_description (Description)</span></span>  | <span data-ttu-id="4437c-164">NAMEALIAS (NAMEALIAS)</span><span class="sxs-lookup"><span data-stu-id="4437c-164">NAMEALIAS (NAMEALIAS)</span></span>|

<span data-ttu-id="4437c-165">Les mises en correspondance mises à jour doivent ressembler à l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="4437c-165">The updated mappings should look like the following image.</span></span>

![Tâche Départements à unités opérationnelles](./media/DepartmentMapping.png)


<span data-ttu-id="4437c-167">La tâche Missions à Détail de la mission nécessite que les mises en correspondance suivantes soient mises à jour.</span><span class="sxs-lookup"><span data-stu-id="4437c-167">The Jobs to Job Detail task needs the following mappings updated.</span></span>

| <span data-ttu-id="4437c-168">Champ source existant</span><span class="sxs-lookup"><span data-stu-id="4437c-168">Existing source field</span></span>          | <span data-ttu-id="4437c-169">Nouveau champ source</span><span class="sxs-lookup"><span data-stu-id="4437c-169">New source field</span></span>                   |
| -------------------------------|------------------------------------|
| <span data-ttu-id="4437c-170">cdm_name (Nom)</span><span class="sxs-lookup"><span data-stu-id="4437c-170">cdm_name (Name)</span></span>                | <span data-ttu-id="4437c-171">cdm_description (Description)</span><span class="sxs-lookup"><span data-stu-id="4437c-171">cdm_description (Description)</span></span>      |
| <span data-ttu-id="4437c-172">cdm_name (Description)</span><span class="sxs-lookup"><span data-stu-id="4437c-172">cdm_name (Description)</span></span>         | <span data-ttu-id="4437c-173">cdm_jobdescription(Description de la mission)</span><span class="sxs-lookup"><span data-stu-id="4437c-173">cdm_jobdescription(Job Description)</span></span>|


<span data-ttu-id="4437c-174">Les mises en correspondance mises à jour doivent ressembler à l'illustration ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4437c-174">The updated mappings should look like the image below.</span></span>

![Tâches Mission à Détails de la mission](./media/JobMapping.png)

<span data-ttu-id="4437c-176">La tâche Collaborateurs à Travail nécessite que les mises en correspondance suivantes soient mises à jour.</span><span class="sxs-lookup"><span data-stu-id="4437c-176">The Workers to Work task needs the following mappings updated.</span></span>

| <span data-ttu-id="4437c-177">Champ source existant</span><span class="sxs-lookup"><span data-stu-id="4437c-177">Existing source field</span></span>                 | <span data-ttu-id="4437c-178">Nouveau champ source</span><span class="sxs-lookup"><span data-stu-id="4437c-178">New source field</span></span>                               |
| --------------------------------------|------------------------------------------------|
| <span data-ttu-id="4437c-179">cdm_emailaddress1 (Adresse e-mail 1)</span><span class="sxs-lookup"><span data-stu-id="4437c-179">cdm_emailaddress1 (Email Address 1)</span></span>   | <span data-ttu-id="4437c-180">cdm_primaryemailaddress (Adresse e-mail principale)</span><span class="sxs-lookup"><span data-stu-id="4437c-180">cdm_primaryemailaddress (Primary Email Address</span></span> |
| <span data-ttu-id="4437c-181">cdm_telephone1 (Téléphone 1)</span><span class="sxs-lookup"><span data-stu-id="4437c-181">cdm_telephone1 (Telephone 1)</span></span>          | <span data-ttu-id="4437c-182">cdm_primarytelephone (Téléphone principal)</span><span class="sxs-lookup"><span data-stu-id="4437c-182">cdm_primarytelephone (Primary Telephone)</span></span>       |

<span data-ttu-id="4437c-183">La transformation du champ Sexe doit également être mise à jour.</span><span class="sxs-lookup"><span data-stu-id="4437c-183">The Gender field transform also needs to be updated.</span></span> <span data-ttu-id="4437c-184">Sélectionnez le type de mise en correspondance **fn** (fonction) pour Sexe et mettez à jour les mises en correspondance de valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="4437c-184">Select the **fn** (function) map type for Gender and update the following value mappings.</span></span>

| <span data-ttu-id="4437c-185">Valeur CDS</span><span class="sxs-lookup"><span data-stu-id="4437c-185">CDS value</span></span>                   | <span data-ttu-id="4437c-186">Valeur Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4437c-186">Finance and Operations value</span></span>                     |
| ----------------------------|--------------------------------------------------|
| <span data-ttu-id="4437c-187">75440000</span><span class="sxs-lookup"><span data-stu-id="4437c-187">75440000</span></span>                    | <span data-ttu-id="4437c-188">Masculin</span><span class="sxs-lookup"><span data-stu-id="4437c-188">Male</span></span>                                             |
| <span data-ttu-id="4437c-189">75440001</span><span class="sxs-lookup"><span data-stu-id="4437c-189">75440001</span></span>                    | <span data-ttu-id="4437c-190">Féminin</span><span class="sxs-lookup"><span data-stu-id="4437c-190">Female</span></span>                                           |
| <span data-ttu-id="4437c-191">75440002</span><span class="sxs-lookup"><span data-stu-id="4437c-191">75440002</span></span>                    | <span data-ttu-id="4437c-192">Aucune</span><span class="sxs-lookup"><span data-stu-id="4437c-192">None</span></span>                                             | 
| <span data-ttu-id="4437c-193">75440003</span><span class="sxs-lookup"><span data-stu-id="4437c-193">75440003</span></span>                    | <span data-ttu-id="4437c-194">NonSpecific</span><span class="sxs-lookup"><span data-stu-id="4437c-194">NonSpecific</span></span>                                      |

<span data-ttu-id="4437c-195">Les mises en correspondance mises à jour doivent ressembler aux illustrations suivantes.</span><span class="sxs-lookup"><span data-stu-id="4437c-195">The updated mappings should look like the following images.</span></span>

![Tâche Collaborateurs à Collaborateurs](./media/WorkerMapping.png)

![Transformation du champ Sexe](./media/WorkerTransform.png)

