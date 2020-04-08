---
title: Entités Common Data Service
description: Microsoft Dynamics 365 Human Resources utilise Common Data Service pour permettre des scénarios d'extensibilité et d'intégration.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: c8e0288da16829c04a9b97c0a52caa8bd27cddf8
ms.sourcegitcommit: fde8045ea49d0cf26d5e7ac5a0da5c0d3d69d5bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2020
ms.locfileid: "3166496"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="65394-103">Entités Common Data Service</span><span class="sxs-lookup"><span data-stu-id="65394-103">Common Data Service entities</span></span>

<span data-ttu-id="65394-104">Microsoft Dynamics 365 Human Resources utilise Common Data Service pour permettre des scénarios d'extensibilité et d'intégration.</span><span class="sxs-lookup"><span data-stu-id="65394-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="65394-105">Pour plus d'informations sur Common Data Service, voir [Qu'est-ce que Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="65394-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="65394-106">Les entités Human Resources suivantes sont disponibles dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="65394-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="65394-107">Entités Avantage</span><span class="sxs-lookup"><span data-stu-id="65394-107">Benefit entities</span></span>

| <span data-ttu-id="65394-108">Nom</span><span class="sxs-lookup"><span data-stu-id="65394-108">Name</span></span> | <span data-ttu-id="65394-109">Entité</span><span class="sxs-lookup"><span data-stu-id="65394-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="65394-110">Fréquence de calcul des avantages</span><span class="sxs-lookup"><span data-stu-id="65394-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="65394-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="65394-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="65394-112">Fréquence de calcul des avantages de la période de rémunération</span><span class="sxs-lookup"><span data-stu-id="65394-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="65394-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="65394-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="65394-114">Taux de calcul des avantages</span><span class="sxs-lookup"><span data-stu-id="65394-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="65394-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="65394-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="65394-116">Détails du taux de calcul des avantages</span><span class="sxs-lookup"><span data-stu-id="65394-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="65394-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="65394-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="65394-118">Option d'avantage</span><span class="sxs-lookup"><span data-stu-id="65394-118">Benefit Option</span></span> | <span data-ttu-id="65394-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="65394-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="65394-120">Plan d'avantages</span><span class="sxs-lookup"><span data-stu-id="65394-120">Benefit Plan</span></span> | <span data-ttu-id="65394-121">cdm_benefitplan (Non activé pour la prise en charge des champs personnalisés)</span><span class="sxs-lookup"><span data-stu-id="65394-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="65394-122">Type d'avantage</span><span class="sxs-lookup"><span data-stu-id="65394-122">Benefit Type</span></span> | <span data-ttu-id="65394-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="65394-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="65394-124">Entités de tâches de processus d'entreprise</span><span class="sxs-lookup"><span data-stu-id="65394-124">Business process tasks entities</span></span>

| <span data-ttu-id="65394-125">Nom</span><span class="sxs-lookup"><span data-stu-id="65394-125">Name</span></span> | <span data-ttu-id="65394-126">Entité</span><span class="sxs-lookup"><span data-stu-id="65394-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="65394-127">Calendrier pour le processus d'entreprise</span><span class="sxs-lookup"><span data-stu-id="65394-127">Business Process Calendar</span></span> | <span data-ttu-id="65394-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="65394-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="65394-129">Affectation du groupe de processus d'entreprise</span><span class="sxs-lookup"><span data-stu-id="65394-129">Business Process Group Assignment</span></span> | <span data-ttu-id="65394-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="65394-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="65394-131">Groupe de tâches de la bibliothèque de processus d'entreprise</span><span class="sxs-lookup"><span data-stu-id="65394-131">Business Process Library Task Group</span></span> | <span data-ttu-id="65394-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="65394-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="65394-133">Phase du processus d'entreprise</span><span class="sxs-lookup"><span data-stu-id="65394-133">Business Process Stage</span></span> | <span data-ttu-id="65394-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="65394-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="65394-135">En-tête de modèle de liste de contrôle</span><span class="sxs-lookup"><span data-stu-id="65394-135">Checklist Template Header</span></span> | <span data-ttu-id="65394-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="65394-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="65394-137">Tâche du modèle de liste de contrôle</span><span class="sxs-lookup"><span data-stu-id="65394-137">Checklist Template Task</span></span> | <span data-ttu-id="65394-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="65394-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="65394-139">Entités de rémunération</span><span class="sxs-lookup"><span data-stu-id="65394-139">Compensation entities</span></span>

| <span data-ttu-id="65394-140">Nom</span><span class="sxs-lookup"><span data-stu-id="65394-140">Name</span></span> | <span data-ttu-id="65394-141">Entité</span><span class="sxs-lookup"><span data-stu-id="65394-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="65394-142">Régime de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="65394-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="65394-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="65394-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="65394-144">Grille de rémunération</span><span class="sxs-lookup"><span data-stu-id="65394-144">Compensation Grid</span></span> | <span data-ttu-id="65394-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="65394-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="65394-146">Niveau de rémunération</span><span class="sxs-lookup"><span data-stu-id="65394-146">Compensation Level</span></span> | <span data-ttu-id="65394-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="65394-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="65394-148">Fréquence de paiement de la rémunération</span><span class="sxs-lookup"><span data-stu-id="65394-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="65394-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="65394-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="65394-150">Paramétrage des points de référence de rémunération</span><span class="sxs-lookup"><span data-stu-id="65394-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="65394-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="65394-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="65394-152">Ligne de paramétrage des points de référence de rémunération</span><span class="sxs-lookup"><span data-stu-id="65394-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="65394-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="65394-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="65394-154">Région de rémunération</span><span class="sxs-lookup"><span data-stu-id="65394-154">Compensation Region</span></span> | <span data-ttu-id="65394-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="65394-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="65394-156">Structure des rémunérations</span><span class="sxs-lookup"><span data-stu-id="65394-156">Compensation Structure</span></span> | <span data-ttu-id="65394-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="65394-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="65394-158">Régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="65394-158">Compensation Variable Plan</span></span> | <span data-ttu-id="65394-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="65394-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="65394-160">Niveau du régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="65394-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="65394-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="65394-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="65394-162">Type du régime rémunération variable</span><span class="sxs-lookup"><span data-stu-id="65394-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="65394-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="65394-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="65394-164">Événement de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="65394-164">Fixed Compensation Event</span></span> | <span data-ttu-id="65394-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="65394-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="65394-166">Règle d'acquisition</span><span class="sxs-lookup"><span data-stu-id="65394-166">Vesting Rule</span></span> | <span data-ttu-id="65394-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="65394-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="65394-168">Rémunération fixe du collaborateur</span><span class="sxs-lookup"><span data-stu-id="65394-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="65394-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="65394-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="65394-170">Entités Organisation</span><span class="sxs-lookup"><span data-stu-id="65394-170">Organization entities</span></span>

| <span data-ttu-id="65394-171">Nom</span><span class="sxs-lookup"><span data-stu-id="65394-171">Name</span></span> | <span data-ttu-id="65394-172">Entité</span><span class="sxs-lookup"><span data-stu-id="65394-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="65394-173">Département</span><span class="sxs-lookup"><span data-stu-id="65394-173">Department</span></span> | <span data-ttu-id="65394-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="65394-174">cdm_department</span></span> |
| <span data-ttu-id="65394-175">Emploi</span><span class="sxs-lookup"><span data-stu-id="65394-175">Employment</span></span> | <span data-ttu-id="65394-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="65394-176">cdm_employment</span></span> |
| <span data-ttu-id="65394-177">Société</span><span class="sxs-lookup"><span data-stu-id="65394-177">Company</span></span> | <span data-ttu-id="65394-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="65394-178">cdm_company</span></span> |
| <span data-ttu-id="65394-179">Mission</span><span class="sxs-lookup"><span data-stu-id="65394-179">Job</span></span> | <span data-ttu-id="65394-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="65394-180">cdm_job</span></span> |
| <span data-ttu-id="65394-181">Fonction de tâche</span><span class="sxs-lookup"><span data-stu-id="65394-181">Job Function</span></span> | <span data-ttu-id="65394-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="65394-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="65394-183">Poste</span><span class="sxs-lookup"><span data-stu-id="65394-183">Job Position</span></span> | <span data-ttu-id="65394-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="65394-184">cdm_jobposition</span></span> |
| <span data-ttu-id="65394-185">Type de poste</span><span class="sxs-lookup"><span data-stu-id="65394-185">Position Type</span></span> | <span data-ttu-id="65394-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="65394-186">cdm_positiontype</span></span> |
| <span data-ttu-id="65394-187">Affectation du collaborateur au poste</span><span class="sxs-lookup"><span data-stu-id="65394-187">Position Worker Assignment</span></span> | <span data-ttu-id="65394-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="65394-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="65394-189">Dimension du poste</span><span class="sxs-lookup"><span data-stu-id="65394-189">Job Position Dimension</span></span> | <span data-ttu-id="65394-190">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="65394-190">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="65394-191">Type de poste</span><span class="sxs-lookup"><span data-stu-id="65394-191">Job Type</span></span> | <span data-ttu-id="65394-192">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="65394-192">cdm_jobtype</span></span> |
| <span data-ttu-id="65394-193">Langue</span><span class="sxs-lookup"><span data-stu-id="65394-193">Language</span></span> | <span data-ttu-id="65394-194">cdm_language</span><span class="sxs-lookup"><span data-stu-id="65394-194">cdm_language</span></span> |
| <span data-ttu-id="65394-195">Titre</span><span class="sxs-lookup"><span data-stu-id="65394-195">Title</span></span> | <span data-ttu-id="65394-196">cdm_title</span><span class="sxs-lookup"><span data-stu-id="65394-196">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="65394-197">Les dimensions financières pour **Type de poste**, **Affectation du collaborateur au poste** et **Emploi** fournissent une intégration unidirectionnelle vers Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="65394-197">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Common Data Service.</span></span> <span data-ttu-id="65394-198">Les mises à jour des dimensions financières ne peuvent actuellement pas se synchroniser de Common Data Service vers Human Resources.</span><span class="sxs-lookup"><span data-stu-id="65394-198">Financial dimensions updates currently can't synchronize from Common Data Service to Human Resources.</span></span> 

## <a name="leave-and-absence-entities"></a><span data-ttu-id="65394-199">Entités liées aux congés et absences</span><span class="sxs-lookup"><span data-stu-id="65394-199">Leave and absence entities</span></span>

| <span data-ttu-id="65394-200">Nom</span><span class="sxs-lookup"><span data-stu-id="65394-200">Name</span></span> | <span data-ttu-id="65394-201">Entité</span><span class="sxs-lookup"><span data-stu-id="65394-201">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="65394-202">Transaction bancaire de congé</span><span class="sxs-lookup"><span data-stu-id="65394-202">Leave Bank Transaction</span></span> | <span data-ttu-id="65394-203">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="65394-203">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="65394-204">Inscription aux congés</span><span class="sxs-lookup"><span data-stu-id="65394-204">Leave Enrollment</span></span> | <span data-ttu-id="65394-205">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="65394-205">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="65394-206">Plan de congé</span><span class="sxs-lookup"><span data-stu-id="65394-206">Leave Plan</span></span> | <span data-ttu-id="65394-207">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="65394-207">cdm_leaveplan</span></span> |
| <span data-ttu-id="65394-208">Demande de congé</span><span class="sxs-lookup"><span data-stu-id="65394-208">Leave Request</span></span> | <span data-ttu-id="65394-209">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="65394-209">cdm_leaverequest</span></span> |
| <span data-ttu-id="65394-210">Détails de la demande de congés</span><span class="sxs-lookup"><span data-stu-id="65394-210">Leave Request Detail</span></span> | <span data-ttu-id="65394-211">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="65394-211">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="65394-212">Type de congé</span><span class="sxs-lookup"><span data-stu-id="65394-212">Leave Type</span></span> | <span data-ttu-id="65394-213">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="65394-213">cdm_leavetype</span></span> |
| <span data-ttu-id="65394-214">Code motif du type de congé</span><span class="sxs-lookup"><span data-stu-id="65394-214">Leave Type Reason Code</span></span> | <span data-ttu-id="65394-215">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="65394-215">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="65394-216">Entités de paie</span><span class="sxs-lookup"><span data-stu-id="65394-216">Payroll entities</span></span>

| <span data-ttu-id="65394-217">Nom</span><span class="sxs-lookup"><span data-stu-id="65394-217">Name</span></span> | <span data-ttu-id="65394-218">Entité</span><span class="sxs-lookup"><span data-stu-id="65394-218">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="65394-219">Cycle de paie</span><span class="sxs-lookup"><span data-stu-id="65394-219">Pay Cycle</span></span> | <span data-ttu-id="65394-220">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="65394-220">cdm_paycycle</span></span> |
| <span data-ttu-id="65394-221">Période de rémunération</span><span class="sxs-lookup"><span data-stu-id="65394-221">Pay Period</span></span> | <span data-ttu-id="65394-222">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="65394-222">cdm_payperiod</span></span> |
| <span data-ttu-id="65394-223">Code de rémunération de la paie</span><span class="sxs-lookup"><span data-stu-id="65394-223">Payroll Earning Code</span></span> | <span data-ttu-id="65394-224">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="65394-224">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="65394-225">Décaissements du compte en banque</span><span class="sxs-lookup"><span data-stu-id="65394-225">Bank Account Disbursement</span></span> | <span data-ttu-id="65394-226">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="65394-226">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="65394-227">Zone fiscale</span><span class="sxs-lookup"><span data-stu-id="65394-227">Tax Region</span></span> | <span data-ttu-id="65394-228">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="65394-228">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="65394-229">Entités de collaborateurs</span><span class="sxs-lookup"><span data-stu-id="65394-229">Worker entities</span></span>

| <span data-ttu-id="65394-230">Nom</span><span class="sxs-lookup"><span data-stu-id="65394-230">Name</span></span> | <span data-ttu-id="65394-231">Entité</span><span class="sxs-lookup"><span data-stu-id="65394-231">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="65394-232">Collaborateur</span><span class="sxs-lookup"><span data-stu-id="65394-232">Worker</span></span> | <span data-ttu-id="65394-233">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="65394-233">cdm_worker</span></span> |
| <span data-ttu-id="65394-234">Adresse du collaborateur</span><span class="sxs-lookup"><span data-stu-id="65394-234">Worker Address</span></span> | <span data-ttu-id="65394-235">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="65394-235">cdm_workeraddress</span></span> |
| <span data-ttu-id="65394-236">Détails personnels du collaborateur</span><span class="sxs-lookup"><span data-stu-id="65394-236">Worker Personal Detail</span></span> | <span data-ttu-id="65394-237">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="65394-237">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="65394-238">Numéro d'identification personnel du collaborateur</span><span class="sxs-lookup"><span data-stu-id="65394-238">Worker Person Identification Number</span></span> | <span data-ttu-id="65394-239">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="65394-239">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="65394-240">Type d'identification personnel du collaborateur</span><span class="sxs-lookup"><span data-stu-id="65394-240">Worker Person Identification Type</span></span> | <span data-ttu-id="65394-241">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="65394-241">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="65394-242">Calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="65394-242">Work Calendar</span></span> | <span data-ttu-id="65394-243">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="65394-243">cdm_workcalendar</span></span> |
| <span data-ttu-id="65394-244">Jours de calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="65394-244">Work Calendar Day</span></span> | <span data-ttu-id="65394-245">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="65394-245">cdm_workcalendarday</span></span> |
| <span data-ttu-id="65394-246">Congé du calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="65394-246">Work Calendar Holiday</span></span> |<span data-ttu-id="65394-247">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="65394-247">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="65394-248">Ligne de congé du calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="65394-248">Work Calendar Holiday Line</span></span> | <span data-ttu-id="65394-249">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="65394-249">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="65394-250">Intervalle de temps du calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="65394-250">Work Calendar Time Interval</span></span> | <span data-ttu-id="65394-251">cdm_workcalendartimeinterval (Non activé pour la prise en charge des champs personnalisés)</span><span class="sxs-lookup"><span data-stu-id="65394-251">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="65394-252">Compte bancaire du collaborateur</span><span class="sxs-lookup"><span data-stu-id="65394-252">Worker Bank Account</span></span> | <span data-ttu-id="65394-253">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="65394-253">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="65394-254">Entités de configuration des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="65394-254">Worker setup entities</span></span>

| <span data-ttu-id="65394-255">Nom</span><span class="sxs-lookup"><span data-stu-id="65394-255">Name</span></span> | <span data-ttu-id="65394-256">Entité</span><span class="sxs-lookup"><span data-stu-id="65394-256">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="65394-257">Statut d'ancien combattant</span><span class="sxs-lookup"><span data-stu-id="65394-257">Veteran Status</span></span> | <span data-ttu-id="65394-258">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="65394-258">cdm_veteranstatus</span></span> |
| <span data-ttu-id="65394-259">Origine ethnique</span><span class="sxs-lookup"><span data-stu-id="65394-259">Ethnic Origin</span></span> | <span data-ttu-id="65394-260">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="65394-260">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="65394-261">Code motif</span><span class="sxs-lookup"><span data-stu-id="65394-261">Reason Code</span></span> | <span data-ttu-id="65394-262">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="65394-262">cdm_reasoncode</span></span> |
| <span data-ttu-id="65394-263">Administration émettrice de l'identification des personnes</span><span class="sxs-lookup"><span data-stu-id="65394-263">Person Identification Issuing Agency</span></span> | <span data-ttu-id="65394-264">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="65394-264">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="65394-265">Entités de compétence</span><span class="sxs-lookup"><span data-stu-id="65394-265">Competency entities</span></span>

| <span data-ttu-id="65394-266">Nom</span><span class="sxs-lookup"><span data-stu-id="65394-266">Name</span></span> | <span data-ttu-id="65394-267">Entité</span><span class="sxs-lookup"><span data-stu-id="65394-267">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="65394-268">Type de qualification</span><span class="sxs-lookup"><span data-stu-id="65394-268">Skill Type</span></span> | <span data-ttu-id="65394-269">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="65394-269">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="65394-270">Modèles de relation d'entité</span><span class="sxs-lookup"><span data-stu-id="65394-270">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="65394-271">Collaborateur</span><span class="sxs-lookup"><span data-stu-id="65394-271">Worker</span></span>

![Collaborateur](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="65394-273">Emploi et poste</span><span class="sxs-lookup"><span data-stu-id="65394-273">Job and Job Position</span></span>

![Emploi et poste](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="65394-275">Avantages</span><span class="sxs-lookup"><span data-stu-id="65394-275">Benefits</span></span>

![Avantages](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="65394-277">Rémunération</span><span class="sxs-lookup"><span data-stu-id="65394-277">Compensation</span></span>

![Rémunération](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="65394-279">Quitter</span><span class="sxs-lookup"><span data-stu-id="65394-279">Leave</span></span>

![Quitter](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="65394-281">Calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="65394-281">Work Calendar</span></span>

![Calendrier de travail](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="65394-283">Voir également :</span><span class="sxs-lookup"><span data-stu-id="65394-283">See also</span></span>

[<span data-ttu-id="65394-284">Choisir une technologie d'intégration de données</span><span class="sxs-lookup"><span data-stu-id="65394-284">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="65394-285">Configuration de l'intégration Common Data Service</span><span class="sxs-lookup"><span data-stu-id="65394-285">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)
