---
title: Tables Dataverse
description: Microsoft Dynamics 365 Human Resources utilise Dataverse pour permettre des scénarios d’extensibilité et d’intégration.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: caf8b0a5d0b24ef3619f45a6d236acae6d29c8ab
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465220"
---
# <a name="dataverse-tables"></a><span data-ttu-id="3e8ca-103">Tables Dataverse</span><span class="sxs-lookup"><span data-stu-id="3e8ca-103">Dataverse tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3e8ca-104">Microsoft Dynamics 365 Human Resources utilise Dataverse pour permettre des scénarios d’extensibilité et d’intégration.</span><span class="sxs-lookup"><span data-stu-id="3e8ca-104">Microsoft Dynamics 365 Human Resources uses Dataverse to enable extensibility and integration scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="3e8ca-105">Les entités Human Resources correspondent aux tables Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3e8ca-105">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="3e8ca-106">Pour plus d’informations sur Dataverse (auparavant Common Data Service) et les mises à jour terminologiques, voir [Qu’est-ce que Microsoft Dataverse ?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="3e8ca-106">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="3e8ca-107">Les tables Dataverse suivantes sont disponibles dans les entités Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3e8ca-107">The following Dataverse tables are available based on Human Resources entities.</span></span>

## <a name="benefit-tables"></a><span data-ttu-id="3e8ca-108">Tables des avantages</span><span class="sxs-lookup"><span data-stu-id="3e8ca-108">Benefit tables</span></span>

| <span data-ttu-id="3e8ca-109">Nom</span><span class="sxs-lookup"><span data-stu-id="3e8ca-109">Name</span></span> | <span data-ttu-id="3e8ca-110">Table</span><span class="sxs-lookup"><span data-stu-id="3e8ca-110">Table</span></span> |
| --- | --- |
| <span data-ttu-id="3e8ca-111">Fréquence de calcul des avantages</span><span class="sxs-lookup"><span data-stu-id="3e8ca-111">Benefit Calculation Frequency</span></span> | <span data-ttu-id="3e8ca-112">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="3e8ca-112">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="3e8ca-113">Fréquence de calcul des avantages de la période de rémunération</span><span class="sxs-lookup"><span data-stu-id="3e8ca-113">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="3e8ca-114">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="3e8ca-114">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="3e8ca-115">Taux de calcul des avantages</span><span class="sxs-lookup"><span data-stu-id="3e8ca-115">Benefit Calculation Rate</span></span> | <span data-ttu-id="3e8ca-116">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="3e8ca-116">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="3e8ca-117">Détails du taux de calcul des avantages</span><span class="sxs-lookup"><span data-stu-id="3e8ca-117">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="3e8ca-118">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="3e8ca-118">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="3e8ca-119">Option d’avantage</span><span class="sxs-lookup"><span data-stu-id="3e8ca-119">Benefit Option</span></span> | <span data-ttu-id="3e8ca-120">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="3e8ca-120">cdm_benefitoption</span></span> |
| <span data-ttu-id="3e8ca-121">Plan d’avantages</span><span class="sxs-lookup"><span data-stu-id="3e8ca-121">Benefit Plan</span></span> | <span data-ttu-id="3e8ca-122">cdm_benefitplan (Non activé pour la prise en charge des champs personnalisés)</span><span class="sxs-lookup"><span data-stu-id="3e8ca-122">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="3e8ca-123">Type d’avantage</span><span class="sxs-lookup"><span data-stu-id="3e8ca-123">Benefit Type</span></span> | <span data-ttu-id="3e8ca-124">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="3e8ca-124">cdm_benefittype</span></span> |

## <a name="business-process-tasks-tables"></a><span data-ttu-id="3e8ca-125">Tables des tâches de processus d’entreprise</span><span class="sxs-lookup"><span data-stu-id="3e8ca-125">Business process tasks tables</span></span>

| <span data-ttu-id="3e8ca-126">Nom</span><span class="sxs-lookup"><span data-stu-id="3e8ca-126">Name</span></span> | <span data-ttu-id="3e8ca-127">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="3e8ca-127">Table</span></span> |
| --- | --- |
| <span data-ttu-id="3e8ca-128">Calendrier pour le processus d’entreprise</span><span class="sxs-lookup"><span data-stu-id="3e8ca-128">Business Process Calendar</span></span> | <span data-ttu-id="3e8ca-129">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="3e8ca-129">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="3e8ca-130">Affectation du groupe de processus d’entreprise</span><span class="sxs-lookup"><span data-stu-id="3e8ca-130">Business Process Group Assignment</span></span> | <span data-ttu-id="3e8ca-131">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="3e8ca-131">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="3e8ca-132">Groupe de tâches de la bibliothèque de processus d’entreprise</span><span class="sxs-lookup"><span data-stu-id="3e8ca-132">Business Process Library Task Group</span></span> | <span data-ttu-id="3e8ca-133">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="3e8ca-133">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="3e8ca-134">Phase du processus d’entreprise</span><span class="sxs-lookup"><span data-stu-id="3e8ca-134">Business Process Stage</span></span> | <span data-ttu-id="3e8ca-135">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="3e8ca-135">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="3e8ca-136">En-tête de modèle de liste de contrôle</span><span class="sxs-lookup"><span data-stu-id="3e8ca-136">Checklist Template Header</span></span> | <span data-ttu-id="3e8ca-137">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="3e8ca-137">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="3e8ca-138">Tâche du modèle de liste de contrôle</span><span class="sxs-lookup"><span data-stu-id="3e8ca-138">Checklist Template Task</span></span> | <span data-ttu-id="3e8ca-139">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="3e8ca-139">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-tables"></a><span data-ttu-id="3e8ca-140">Tables de rémunération</span><span class="sxs-lookup"><span data-stu-id="3e8ca-140">Compensation tables</span></span>

| <span data-ttu-id="3e8ca-141">Nom</span><span class="sxs-lookup"><span data-stu-id="3e8ca-141">Name</span></span> | <span data-ttu-id="3e8ca-142">Table</span><span class="sxs-lookup"><span data-stu-id="3e8ca-142">Table</span></span> |
| --- | --- |
| <span data-ttu-id="3e8ca-143">Régime fixe de rémunération</span><span class="sxs-lookup"><span data-stu-id="3e8ca-143">Compensation Fixed Plan</span></span> | <span data-ttu-id="3e8ca-144">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="3e8ca-144">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="3e8ca-145">Grille de rémunération</span><span class="sxs-lookup"><span data-stu-id="3e8ca-145">Compensation Grid</span></span> | <span data-ttu-id="3e8ca-146">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="3e8ca-146">cdm_compensationgrid</span></span> |
| <span data-ttu-id="3e8ca-147">Niveau de rémunération</span><span class="sxs-lookup"><span data-stu-id="3e8ca-147">Compensation Level</span></span> | <span data-ttu-id="3e8ca-148">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="3e8ca-148">cdm_compensationlevel</span></span> |
| <span data-ttu-id="3e8ca-149">Fréquence de paiement de la rémunération</span><span class="sxs-lookup"><span data-stu-id="3e8ca-149">Compensation Pay Frequency</span></span> | <span data-ttu-id="3e8ca-150">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="3e8ca-150">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="3e8ca-151">Paramétrage des points de référence de rémunération</span><span class="sxs-lookup"><span data-stu-id="3e8ca-151">Compensation Reference Point Setup</span></span> | <span data-ttu-id="3e8ca-152">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="3e8ca-152">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="3e8ca-153">Ligne de paramétrage des points de référence de rémunération</span><span class="sxs-lookup"><span data-stu-id="3e8ca-153">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="3e8ca-154">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="3e8ca-154">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="3e8ca-155">Région de rémunération</span><span class="sxs-lookup"><span data-stu-id="3e8ca-155">Compensation Region</span></span> | <span data-ttu-id="3e8ca-156">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="3e8ca-156">cdm_compensationregion</span></span> |
| <span data-ttu-id="3e8ca-157">Structure des rémunérations</span><span class="sxs-lookup"><span data-stu-id="3e8ca-157">Compensation Structure</span></span> | <span data-ttu-id="3e8ca-158">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="3e8ca-158">cdm_compensationstructure</span></span> |
| <span data-ttu-id="3e8ca-159">Régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="3e8ca-159">Compensation Variable Plan</span></span> | <span data-ttu-id="3e8ca-160">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="3e8ca-160">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="3e8ca-161">Niveau du régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="3e8ca-161">Compensation Variable Plan Level</span></span> | <span data-ttu-id="3e8ca-162">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="3e8ca-162">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="3e8ca-163">Type du régime rémunération variable</span><span class="sxs-lookup"><span data-stu-id="3e8ca-163">Compensation Variable Plan Type</span></span> | <span data-ttu-id="3e8ca-164">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="3e8ca-164">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="3e8ca-165">Événement de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="3e8ca-165">Fixed Compensation Event</span></span> | <span data-ttu-id="3e8ca-166">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="3e8ca-166">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="3e8ca-167">Règle d’acquisition</span><span class="sxs-lookup"><span data-stu-id="3e8ca-167">Vesting Rule</span></span> | <span data-ttu-id="3e8ca-168">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="3e8ca-168">cdm_vestingrule</span></span> |
| <span data-ttu-id="3e8ca-169">Rémunération fixe du collaborateur</span><span class="sxs-lookup"><span data-stu-id="3e8ca-169">Worker Fixed Compensation</span></span> | <span data-ttu-id="3e8ca-170">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="3e8ca-170">cdm_workerfixedcompensation</span></span> |

## <a name="organization-tables"></a><span data-ttu-id="3e8ca-171">Tables d’organisation</span><span class="sxs-lookup"><span data-stu-id="3e8ca-171">Organization tables</span></span>

| <span data-ttu-id="3e8ca-172">Nom</span><span class="sxs-lookup"><span data-stu-id="3e8ca-172">Name</span></span> | <span data-ttu-id="3e8ca-173">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="3e8ca-173">Table</span></span> |
| --- | --- |
| <span data-ttu-id="3e8ca-174">Département</span><span class="sxs-lookup"><span data-stu-id="3e8ca-174">Department</span></span> | <span data-ttu-id="3e8ca-175">cdm_department</span><span class="sxs-lookup"><span data-stu-id="3e8ca-175">cdm_department</span></span> |
| <span data-ttu-id="3e8ca-176">Emploi</span><span class="sxs-lookup"><span data-stu-id="3e8ca-176">Employment</span></span> | <span data-ttu-id="3e8ca-177">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="3e8ca-177">cdm_employment</span></span> |
| <span data-ttu-id="3e8ca-178">Société</span><span class="sxs-lookup"><span data-stu-id="3e8ca-178">Company</span></span> | <span data-ttu-id="3e8ca-179">cdm_company</span><span class="sxs-lookup"><span data-stu-id="3e8ca-179">cdm_company</span></span> |
| <span data-ttu-id="3e8ca-180">Mission</span><span class="sxs-lookup"><span data-stu-id="3e8ca-180">Job</span></span> | <span data-ttu-id="3e8ca-181">cdm_job</span><span class="sxs-lookup"><span data-stu-id="3e8ca-181">cdm_job</span></span> |
| <span data-ttu-id="3e8ca-182">Fonction de tâche</span><span class="sxs-lookup"><span data-stu-id="3e8ca-182">Job Function</span></span> | <span data-ttu-id="3e8ca-183">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="3e8ca-183">cdm_jobfunction</span></span> |
| <span data-ttu-id="3e8ca-184">Poste</span><span class="sxs-lookup"><span data-stu-id="3e8ca-184">Job Position</span></span> | <span data-ttu-id="3e8ca-185">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="3e8ca-185">cdm_jobposition</span></span> |
| <span data-ttu-id="3e8ca-186">Type de poste</span><span class="sxs-lookup"><span data-stu-id="3e8ca-186">Position Type</span></span> | <span data-ttu-id="3e8ca-187">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="3e8ca-187">cdm_positiontype</span></span> |
| <span data-ttu-id="3e8ca-188">Affectation du collaborateur au poste</span><span class="sxs-lookup"><span data-stu-id="3e8ca-188">Position Worker Assignment</span></span> | <span data-ttu-id="3e8ca-189">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="3e8ca-189">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="3e8ca-190">Dimension du poste</span><span class="sxs-lookup"><span data-stu-id="3e8ca-190">Job Position Dimension</span></span> | <span data-ttu-id="3e8ca-191">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="3e8ca-191">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="3e8ca-192">Type de poste</span><span class="sxs-lookup"><span data-stu-id="3e8ca-192">Job Type</span></span> | <span data-ttu-id="3e8ca-193">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="3e8ca-193">cdm_jobtype</span></span> |
| <span data-ttu-id="3e8ca-194">Langue</span><span class="sxs-lookup"><span data-stu-id="3e8ca-194">Language</span></span> | <span data-ttu-id="3e8ca-195">cdm_language</span><span class="sxs-lookup"><span data-stu-id="3e8ca-195">cdm_language</span></span> |
| <span data-ttu-id="3e8ca-196">Titre</span><span class="sxs-lookup"><span data-stu-id="3e8ca-196">Title</span></span> | <span data-ttu-id="3e8ca-197">cdm_title</span><span class="sxs-lookup"><span data-stu-id="3e8ca-197">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="3e8ca-198">Les dimensions financières pour **Type de poste**, **Affectation du collaborateur au poste** et **Emploi** fournissent une intégration unidirectionnelle vers Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3e8ca-198">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Dataverse.</span></span> <span data-ttu-id="3e8ca-199">Les mises à jour des dimensions financières ne peuvent actuellement pas se synchroniser de Dataverse vers Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3e8ca-199">Financial dimensions updates currently can't synchronize from Dataverse to Human Resources.</span></span> 

## <a name="leave-and-absence-tables"></a><span data-ttu-id="3e8ca-200">Tables de congés et d’absences</span><span class="sxs-lookup"><span data-stu-id="3e8ca-200">Leave and absence tables</span></span>

| <span data-ttu-id="3e8ca-201">Nom</span><span class="sxs-lookup"><span data-stu-id="3e8ca-201">Name</span></span> | <span data-ttu-id="3e8ca-202">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="3e8ca-202">Table</span></span> |
| --- | --- |
| <span data-ttu-id="3e8ca-203">Transaction bancaire de congé</span><span class="sxs-lookup"><span data-stu-id="3e8ca-203">Leave Bank Transaction</span></span> | <span data-ttu-id="3e8ca-204">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="3e8ca-204">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="3e8ca-205">Inscription à un congé</span><span class="sxs-lookup"><span data-stu-id="3e8ca-205">Leave Enrollment</span></span> | <span data-ttu-id="3e8ca-206">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="3e8ca-206">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="3e8ca-207">Plan de congé</span><span class="sxs-lookup"><span data-stu-id="3e8ca-207">Leave Plan</span></span> | <span data-ttu-id="3e8ca-208">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="3e8ca-208">cdm_leaveplan</span></span> |
| <span data-ttu-id="3e8ca-209">Demande de congé</span><span class="sxs-lookup"><span data-stu-id="3e8ca-209">Leave Request</span></span> | <span data-ttu-id="3e8ca-210">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="3e8ca-210">cdm_leaverequest</span></span> |
| <span data-ttu-id="3e8ca-211">Détails de la demande de congés</span><span class="sxs-lookup"><span data-stu-id="3e8ca-211">Leave Request Detail</span></span> | <span data-ttu-id="3e8ca-212">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="3e8ca-212">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="3e8ca-213">Type de congé</span><span class="sxs-lookup"><span data-stu-id="3e8ca-213">Leave Type</span></span> | <span data-ttu-id="3e8ca-214">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="3e8ca-214">cdm_leavetype</span></span> |
| <span data-ttu-id="3e8ca-215">Code motif du type de congé</span><span class="sxs-lookup"><span data-stu-id="3e8ca-215">Leave Type Reason Code</span></span> | <span data-ttu-id="3e8ca-216">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="3e8ca-216">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-tables"></a><span data-ttu-id="3e8ca-217">Tables des salaires</span><span class="sxs-lookup"><span data-stu-id="3e8ca-217">Payroll tables</span></span>

| <span data-ttu-id="3e8ca-218">Nom</span><span class="sxs-lookup"><span data-stu-id="3e8ca-218">Name</span></span> | <span data-ttu-id="3e8ca-219">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="3e8ca-219">Table</span></span> |
| --- | --- |
| <span data-ttu-id="3e8ca-220">Cycle de paie</span><span class="sxs-lookup"><span data-stu-id="3e8ca-220">Pay Cycle</span></span> | <span data-ttu-id="3e8ca-221">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="3e8ca-221">cdm_paycycle</span></span> |
| <span data-ttu-id="3e8ca-222">Période de rémunération</span><span class="sxs-lookup"><span data-stu-id="3e8ca-222">Pay Period</span></span> | <span data-ttu-id="3e8ca-223">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="3e8ca-223">cdm_payperiod</span></span> |
| <span data-ttu-id="3e8ca-224">Code de rémunération des salaires</span><span class="sxs-lookup"><span data-stu-id="3e8ca-224">Payroll Earning Code</span></span> | <span data-ttu-id="3e8ca-225">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="3e8ca-225">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="3e8ca-226">Décaissements du compte en banque</span><span class="sxs-lookup"><span data-stu-id="3e8ca-226">Bank Account Disbursement</span></span> | <span data-ttu-id="3e8ca-227">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="3e8ca-227">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="3e8ca-228">Zone fiscale</span><span class="sxs-lookup"><span data-stu-id="3e8ca-228">Tax Region</span></span> | <span data-ttu-id="3e8ca-229">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="3e8ca-229">cdm_taxregion</span></span> |

## <a name="worker-tables"></a><span data-ttu-id="3e8ca-230">Tables des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="3e8ca-230">Worker tables</span></span>

| <span data-ttu-id="3e8ca-231">Nom</span><span class="sxs-lookup"><span data-stu-id="3e8ca-231">Name</span></span> | <span data-ttu-id="3e8ca-232">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="3e8ca-232">Table</span></span> |
| --- | --- |
| <span data-ttu-id="3e8ca-233">Collaborateur</span><span class="sxs-lookup"><span data-stu-id="3e8ca-233">Worker</span></span> | <span data-ttu-id="3e8ca-234">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="3e8ca-234">cdm_worker</span></span> |
| <span data-ttu-id="3e8ca-235">Adresse du collaborateur</span><span class="sxs-lookup"><span data-stu-id="3e8ca-235">Worker Address</span></span> | <span data-ttu-id="3e8ca-236">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="3e8ca-236">cdm_workeraddress</span></span> |
| <span data-ttu-id="3e8ca-237">Détails personnels du collaborateur</span><span class="sxs-lookup"><span data-stu-id="3e8ca-237">Worker Personal Detail</span></span> | <span data-ttu-id="3e8ca-238">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="3e8ca-238">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="3e8ca-239">Numéro d’identification personnel du collaborateur</span><span class="sxs-lookup"><span data-stu-id="3e8ca-239">Worker Person Identification Number</span></span> | <span data-ttu-id="3e8ca-240">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="3e8ca-240">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="3e8ca-241">Type d’identification personnel du collaborateur</span><span class="sxs-lookup"><span data-stu-id="3e8ca-241">Worker Person Identification Type</span></span> | <span data-ttu-id="3e8ca-242">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="3e8ca-242">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="3e8ca-243">Calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="3e8ca-243">Work Calendar</span></span> | <span data-ttu-id="3e8ca-244">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="3e8ca-244">cdm_workcalendar</span></span> |
| <span data-ttu-id="3e8ca-245">Jours de calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="3e8ca-245">Work Calendar Day</span></span> | <span data-ttu-id="3e8ca-246">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="3e8ca-246">cdm_workcalendarday</span></span> |
| <span data-ttu-id="3e8ca-247">Congé du calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="3e8ca-247">Work Calendar Holiday</span></span> |<span data-ttu-id="3e8ca-248">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="3e8ca-248">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="3e8ca-249">Ligne de congé du calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="3e8ca-249">Work Calendar Holiday Line</span></span> | <span data-ttu-id="3e8ca-250">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="3e8ca-250">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="3e8ca-251">Intervalle de temps du calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="3e8ca-251">Work Calendar Time Interval</span></span> | <span data-ttu-id="3e8ca-252">cdm_workcalendartimeinterval (Non activé pour la prise en charge des champs personnalisés)</span><span class="sxs-lookup"><span data-stu-id="3e8ca-252">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="3e8ca-253">Compte bancaire du collaborateur</span><span class="sxs-lookup"><span data-stu-id="3e8ca-253">Worker Bank Account</span></span> | <span data-ttu-id="3e8ca-254">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="3e8ca-254">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-tables"></a><span data-ttu-id="3e8ca-255">Tables de configuration des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="3e8ca-255">Worker setup tables</span></span>

| <span data-ttu-id="3e8ca-256">Nom</span><span class="sxs-lookup"><span data-stu-id="3e8ca-256">Name</span></span> | <span data-ttu-id="3e8ca-257">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="3e8ca-257">Table</span></span> |
| --- | --- |
| <span data-ttu-id="3e8ca-258">Statut de vétéran</span><span class="sxs-lookup"><span data-stu-id="3e8ca-258">Veteran Status</span></span> | <span data-ttu-id="3e8ca-259">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="3e8ca-259">cdm_veteranstatus</span></span> |
| <span data-ttu-id="3e8ca-260">Origine ethnique</span><span class="sxs-lookup"><span data-stu-id="3e8ca-260">Ethnic Origin</span></span> | <span data-ttu-id="3e8ca-261">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="3e8ca-261">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="3e8ca-262">Code motif</span><span class="sxs-lookup"><span data-stu-id="3e8ca-262">Reason Code</span></span> | <span data-ttu-id="3e8ca-263">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="3e8ca-263">cdm_reasoncode</span></span> |
| <span data-ttu-id="3e8ca-264">Agence émettrice de l’identification de la personne</span><span class="sxs-lookup"><span data-stu-id="3e8ca-264">Person Identification Issuing Agency</span></span> | <span data-ttu-id="3e8ca-265">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="3e8ca-265">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-tables"></a><span data-ttu-id="3e8ca-266">Tables des compétences</span><span class="sxs-lookup"><span data-stu-id="3e8ca-266">Competency tables</span></span>

| <span data-ttu-id="3e8ca-267">Nom</span><span class="sxs-lookup"><span data-stu-id="3e8ca-267">Name</span></span> | <span data-ttu-id="3e8ca-268">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="3e8ca-268">Table</span></span> |
| --- | --- |
| <span data-ttu-id="3e8ca-269">Type de qualification</span><span class="sxs-lookup"><span data-stu-id="3e8ca-269">Skill Type</span></span> | <span data-ttu-id="3e8ca-270">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="3e8ca-270">cdm_skilltype</span></span> |

## <a name="table-relationship-models"></a><span data-ttu-id="3e8ca-271">Modèles de relations de table</span><span class="sxs-lookup"><span data-stu-id="3e8ca-271">Table relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="3e8ca-272">Collaborateur</span><span class="sxs-lookup"><span data-stu-id="3e8ca-272">Worker</span></span>

![Collaborateur](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="3e8ca-274">Emploi et poste</span><span class="sxs-lookup"><span data-stu-id="3e8ca-274">Job and Job Position</span></span>

![Emploi et poste](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="3e8ca-276">Avantages</span><span class="sxs-lookup"><span data-stu-id="3e8ca-276">Benefits</span></span>

![Avantages](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="3e8ca-278">Rémunération</span><span class="sxs-lookup"><span data-stu-id="3e8ca-278">Compensation</span></span>

![Rémunération](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="3e8ca-280">Quitter</span><span class="sxs-lookup"><span data-stu-id="3e8ca-280">Leave</span></span>

![Quitter](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="3e8ca-282">Calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="3e8ca-282">Work Calendar</span></span>

![Calendrier de travail](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="3e8ca-284">Voir également :</span><span class="sxs-lookup"><span data-stu-id="3e8ca-284">See also</span></span>

[<span data-ttu-id="3e8ca-285">Choisir une technologie d’intégration de données</span><span class="sxs-lookup"><span data-stu-id="3e8ca-285">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)<br>
[<span data-ttu-id="3e8ca-286">Configuration de l’intégration Dataverse</span><span class="sxs-lookup"><span data-stu-id="3e8ca-286">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)<br>
[<span data-ttu-id="3e8ca-287">Configurer des tables virtuelles Dataverse</span><span class="sxs-lookup"><span data-stu-id="3e8ca-287">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="3e8ca-288">FAQ sur les tables virtuelles Human Resources</span><span class="sxs-lookup"><span data-stu-id="3e8ca-288">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="3e8ca-289">Qu’est-ce que Microsoft Dataverse ?</span><span class="sxs-lookup"><span data-stu-id="3e8ca-289">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="3e8ca-290">Mises à jour de la terminologie</span><span class="sxs-lookup"><span data-stu-id="3e8ca-290">Terminology updates</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]