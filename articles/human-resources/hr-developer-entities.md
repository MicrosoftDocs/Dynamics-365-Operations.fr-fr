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
ms.openlocfilehash: 6879a45dd1fcc1ba718747aaaf0d7936c2eac49f
ms.sourcegitcommit: 3cad15f8ecc257d3a45c1bc1fada7c094ff4bcec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087344"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="10f74-103">Entités Common Data Service</span><span class="sxs-lookup"><span data-stu-id="10f74-103">Common Data Service entities</span></span>

<span data-ttu-id="10f74-104">Microsoft Dynamics 365 Human Resources utilise Common Data Service pour permettre des scénarios d'extensibilité et d'intégration.</span><span class="sxs-lookup"><span data-stu-id="10f74-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="10f74-105">Pour plus d'informations sur Common Data Service, voir [Qu'est-ce que Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="10f74-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="10f74-106">Les entités Human Resources suivantes sont disponibles dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="10f74-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="10f74-107">Entités Avantage</span><span class="sxs-lookup"><span data-stu-id="10f74-107">Benefit entities</span></span>

| <span data-ttu-id="10f74-108">Nom</span><span class="sxs-lookup"><span data-stu-id="10f74-108">Name</span></span> | <span data-ttu-id="10f74-109">Entité</span><span class="sxs-lookup"><span data-stu-id="10f74-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="10f74-110">Fréquence de calcul des avantages</span><span class="sxs-lookup"><span data-stu-id="10f74-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="10f74-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="10f74-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="10f74-112">Fréquence de calcul des avantages de la période de rémunération</span><span class="sxs-lookup"><span data-stu-id="10f74-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="10f74-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="10f74-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="10f74-114">Taux de calcul des avantages</span><span class="sxs-lookup"><span data-stu-id="10f74-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="10f74-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="10f74-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="10f74-116">Détails du taux de calcul des avantages</span><span class="sxs-lookup"><span data-stu-id="10f74-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="10f74-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="10f74-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="10f74-118">Option d'avantage</span><span class="sxs-lookup"><span data-stu-id="10f74-118">Benefit Option</span></span> | <span data-ttu-id="10f74-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="10f74-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="10f74-120">Plan d'avantages</span><span class="sxs-lookup"><span data-stu-id="10f74-120">Benefit Plan</span></span> | <span data-ttu-id="10f74-121">cdm_benefitplan (Non activé pour la prise en charge des champs personnalisés)</span><span class="sxs-lookup"><span data-stu-id="10f74-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="10f74-122">Type d'avantage</span><span class="sxs-lookup"><span data-stu-id="10f74-122">Benefit Type</span></span> | <span data-ttu-id="10f74-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="10f74-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="10f74-124">Entités de tâches de processus d'entreprise</span><span class="sxs-lookup"><span data-stu-id="10f74-124">Business process tasks entities</span></span>

| <span data-ttu-id="10f74-125">Nom</span><span class="sxs-lookup"><span data-stu-id="10f74-125">Name</span></span> | <span data-ttu-id="10f74-126">Entité</span><span class="sxs-lookup"><span data-stu-id="10f74-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="10f74-127">Calendrier pour le processus d'entreprise</span><span class="sxs-lookup"><span data-stu-id="10f74-127">Business Process Calendar</span></span> | <span data-ttu-id="10f74-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="10f74-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="10f74-129">Affectation du groupe de processus d'entreprise</span><span class="sxs-lookup"><span data-stu-id="10f74-129">Business Process Group Assignment</span></span> | <span data-ttu-id="10f74-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="10f74-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="10f74-131">Groupe de tâches de la bibliothèque de processus d'entreprise</span><span class="sxs-lookup"><span data-stu-id="10f74-131">Business Process Library Task Group</span></span> | <span data-ttu-id="10f74-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="10f74-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="10f74-133">Phase du processus d'entreprise</span><span class="sxs-lookup"><span data-stu-id="10f74-133">Business Process Stage</span></span> | <span data-ttu-id="10f74-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="10f74-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="10f74-135">En-tête de modèle de liste de contrôle</span><span class="sxs-lookup"><span data-stu-id="10f74-135">Checklist Template Header</span></span> | <span data-ttu-id="10f74-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="10f74-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="10f74-137">Tâche du modèle de liste de contrôle</span><span class="sxs-lookup"><span data-stu-id="10f74-137">Checklist Template Task</span></span> | <span data-ttu-id="10f74-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="10f74-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="10f74-139">Entités de rémunération</span><span class="sxs-lookup"><span data-stu-id="10f74-139">Compensation entities</span></span>

| <span data-ttu-id="10f74-140">Nom</span><span class="sxs-lookup"><span data-stu-id="10f74-140">Name</span></span> | <span data-ttu-id="10f74-141">Entité</span><span class="sxs-lookup"><span data-stu-id="10f74-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="10f74-142">Régime de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="10f74-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="10f74-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="10f74-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="10f74-144">Grille de rémunération</span><span class="sxs-lookup"><span data-stu-id="10f74-144">Compensation Grid</span></span> | <span data-ttu-id="10f74-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="10f74-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="10f74-146">Niveau de rémunération</span><span class="sxs-lookup"><span data-stu-id="10f74-146">Compensation Level</span></span> | <span data-ttu-id="10f74-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="10f74-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="10f74-148">Fréquence de paiement de la rémunération</span><span class="sxs-lookup"><span data-stu-id="10f74-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="10f74-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="10f74-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="10f74-150">Paramétrage des points de référence de rémunération</span><span class="sxs-lookup"><span data-stu-id="10f74-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="10f74-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="10f74-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="10f74-152">Ligne de paramétrage des points de référence de rémunération</span><span class="sxs-lookup"><span data-stu-id="10f74-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="10f74-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="10f74-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="10f74-154">Région de rémunération</span><span class="sxs-lookup"><span data-stu-id="10f74-154">Compensation Region</span></span> | <span data-ttu-id="10f74-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="10f74-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="10f74-156">Structure des rémunérations</span><span class="sxs-lookup"><span data-stu-id="10f74-156">Compensation Structure</span></span> | <span data-ttu-id="10f74-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="10f74-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="10f74-158">Régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="10f74-158">Compensation Variable Plan</span></span> | <span data-ttu-id="10f74-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="10f74-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="10f74-160">Niveau du régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="10f74-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="10f74-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="10f74-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="10f74-162">Type du régime rémunération variable</span><span class="sxs-lookup"><span data-stu-id="10f74-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="10f74-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="10f74-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="10f74-164">Événement de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="10f74-164">Fixed Compensation Event</span></span> | <span data-ttu-id="10f74-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="10f74-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="10f74-166">Règle d'acquisition</span><span class="sxs-lookup"><span data-stu-id="10f74-166">Vesting Rule</span></span> | <span data-ttu-id="10f74-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="10f74-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="10f74-168">Rémunération fixe du collaborateur</span><span class="sxs-lookup"><span data-stu-id="10f74-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="10f74-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="10f74-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="10f74-170">Entités Organisation</span><span class="sxs-lookup"><span data-stu-id="10f74-170">Organization entities</span></span>

| <span data-ttu-id="10f74-171">Nom</span><span class="sxs-lookup"><span data-stu-id="10f74-171">Name</span></span> | <span data-ttu-id="10f74-172">Entité</span><span class="sxs-lookup"><span data-stu-id="10f74-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="10f74-173">Département</span><span class="sxs-lookup"><span data-stu-id="10f74-173">Department</span></span> | <span data-ttu-id="10f74-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="10f74-174">cdm_department</span></span> |
| <span data-ttu-id="10f74-175">Emploi</span><span class="sxs-lookup"><span data-stu-id="10f74-175">Employment</span></span> | <span data-ttu-id="10f74-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="10f74-176">cdm_employment</span></span> |
| <span data-ttu-id="10f74-177">Société</span><span class="sxs-lookup"><span data-stu-id="10f74-177">Company</span></span> | <span data-ttu-id="10f74-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="10f74-178">cdm_company</span></span> |
| <span data-ttu-id="10f74-179">Mission</span><span class="sxs-lookup"><span data-stu-id="10f74-179">Job</span></span> | <span data-ttu-id="10f74-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="10f74-180">cdm_job</span></span> |
| <span data-ttu-id="10f74-181">Fonction de tâche</span><span class="sxs-lookup"><span data-stu-id="10f74-181">Job Function</span></span> | <span data-ttu-id="10f74-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="10f74-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="10f74-183">Poste</span><span class="sxs-lookup"><span data-stu-id="10f74-183">Job Position</span></span> | <span data-ttu-id="10f74-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="10f74-184">cdm_jobposition</span></span> |
| <span data-ttu-id="10f74-185">Type de poste</span><span class="sxs-lookup"><span data-stu-id="10f74-185">Position Type</span></span> | <span data-ttu-id="10f74-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="10f74-186">cdm_positiontype</span></span> |
| <span data-ttu-id="10f74-187">Affectation du collaborateur au poste</span><span class="sxs-lookup"><span data-stu-id="10f74-187">Position Worker Assignment</span></span> | <span data-ttu-id="10f74-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="10f74-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="10f74-189">Type de tâche</span><span class="sxs-lookup"><span data-stu-id="10f74-189">Job Type</span></span> | <span data-ttu-id="10f74-190">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="10f74-190">cdm_jobtype</span></span> |
| <span data-ttu-id="10f74-191">Langue</span><span class="sxs-lookup"><span data-stu-id="10f74-191">Language</span></span> | <span data-ttu-id="10f74-192">cdm_language</span><span class="sxs-lookup"><span data-stu-id="10f74-192">cdm_language</span></span> |

## <a name="leave-and-absence-entities"></a><span data-ttu-id="10f74-193">Entités liées aux congés et absences</span><span class="sxs-lookup"><span data-stu-id="10f74-193">Leave and absence entities</span></span>

| <span data-ttu-id="10f74-194">Nom</span><span class="sxs-lookup"><span data-stu-id="10f74-194">Name</span></span> | <span data-ttu-id="10f74-195">Entité</span><span class="sxs-lookup"><span data-stu-id="10f74-195">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="10f74-196">Transaction bancaire de congé</span><span class="sxs-lookup"><span data-stu-id="10f74-196">Leave Bank Transaction</span></span> | <span data-ttu-id="10f74-197">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="10f74-197">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="10f74-198">Inscription aux congés</span><span class="sxs-lookup"><span data-stu-id="10f74-198">Leave Enrollment</span></span> | <span data-ttu-id="10f74-199">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="10f74-199">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="10f74-200">Plan de congé</span><span class="sxs-lookup"><span data-stu-id="10f74-200">Leave Plan</span></span> | <span data-ttu-id="10f74-201">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="10f74-201">cdm_leaveplan</span></span> |
| <span data-ttu-id="10f74-202">Demande de congé</span><span class="sxs-lookup"><span data-stu-id="10f74-202">Leave Request</span></span> | <span data-ttu-id="10f74-203">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="10f74-203">cdm_leaverequest</span></span> |
| <span data-ttu-id="10f74-204">Détails de la demande de congés</span><span class="sxs-lookup"><span data-stu-id="10f74-204">Leave Request Detail</span></span> | <span data-ttu-id="10f74-205">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="10f74-205">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="10f74-206">Type de congé</span><span class="sxs-lookup"><span data-stu-id="10f74-206">Leave Type</span></span> | <span data-ttu-id="10f74-207">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="10f74-207">cdm_leavetype</span></span> |
| <span data-ttu-id="10f74-208">Code motif du type de congé</span><span class="sxs-lookup"><span data-stu-id="10f74-208">Leave Type Reason Code</span></span> | <span data-ttu-id="10f74-209">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="10f74-209">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="10f74-210">Entités de paie</span><span class="sxs-lookup"><span data-stu-id="10f74-210">Payroll entities</span></span>

| <span data-ttu-id="10f74-211">Nom</span><span class="sxs-lookup"><span data-stu-id="10f74-211">Name</span></span> | <span data-ttu-id="10f74-212">Entité</span><span class="sxs-lookup"><span data-stu-id="10f74-212">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="10f74-213">Cycle de paie</span><span class="sxs-lookup"><span data-stu-id="10f74-213">Pay Cycle</span></span> | <span data-ttu-id="10f74-214">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="10f74-214">cdm_paycycle</span></span> |
| <span data-ttu-id="10f74-215">Période de rémunération</span><span class="sxs-lookup"><span data-stu-id="10f74-215">Pay Period</span></span> | <span data-ttu-id="10f74-216">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="10f74-216">cdm_payperiod</span></span> |
| <span data-ttu-id="10f74-217">Code de rémunération de la paie</span><span class="sxs-lookup"><span data-stu-id="10f74-217">Payroll Earning Code</span></span> | <span data-ttu-id="10f74-218">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="10f74-218">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="10f74-219">Décaissements du compte en banque</span><span class="sxs-lookup"><span data-stu-id="10f74-219">Bank Account Disbursement</span></span> | <span data-ttu-id="10f74-220">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="10f74-220">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="10f74-221">Zone fiscale</span><span class="sxs-lookup"><span data-stu-id="10f74-221">Tax Region</span></span> | <span data-ttu-id="10f74-222">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="10f74-222">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="10f74-223">Entités de collaborateurs</span><span class="sxs-lookup"><span data-stu-id="10f74-223">Worker entities</span></span>

| <span data-ttu-id="10f74-224">Nom</span><span class="sxs-lookup"><span data-stu-id="10f74-224">Name</span></span> | <span data-ttu-id="10f74-225">Entité</span><span class="sxs-lookup"><span data-stu-id="10f74-225">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="10f74-226">Collaborateur</span><span class="sxs-lookup"><span data-stu-id="10f74-226">Worker</span></span> | <span data-ttu-id="10f74-227">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="10f74-227">cdm_worker</span></span> |
| <span data-ttu-id="10f74-228">Adresse du collaborateur</span><span class="sxs-lookup"><span data-stu-id="10f74-228">Worker Address</span></span> | <span data-ttu-id="10f74-229">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="10f74-229">cdm_workeraddress</span></span> |
| <span data-ttu-id="10f74-230">Détails personnels du collaborateur</span><span class="sxs-lookup"><span data-stu-id="10f74-230">Worker Personal Detail</span></span> | <span data-ttu-id="10f74-231">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="10f74-231">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="10f74-232">Numéro d'identification personnel du collaborateur</span><span class="sxs-lookup"><span data-stu-id="10f74-232">Worker Person Identification Number</span></span> | <span data-ttu-id="10f74-233">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="10f74-233">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="10f74-234">Type d'identification personnel du collaborateur</span><span class="sxs-lookup"><span data-stu-id="10f74-234">Worker Person Identification Type</span></span> | <span data-ttu-id="10f74-235">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="10f74-235">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="10f74-236">Calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="10f74-236">Work Calendar</span></span> | <span data-ttu-id="10f74-237">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="10f74-237">cdm_workcalendar</span></span> |
| <span data-ttu-id="10f74-238">Jours de calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="10f74-238">Work Calendar Day</span></span> | <span data-ttu-id="10f74-239">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="10f74-239">cdm_workcalendarday</span></span> |
| <span data-ttu-id="10f74-240">Congé du calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="10f74-240">Work Calendar Holiday</span></span> |<span data-ttu-id="10f74-241">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="10f74-241">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="10f74-242">Ligne de congé du calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="10f74-242">Work Calendar Holiday Line</span></span> | <span data-ttu-id="10f74-243">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="10f74-243">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="10f74-244">Intervalle de temps du calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="10f74-244">Work Calendar Time Interval</span></span> | <span data-ttu-id="10f74-245">cdm_workcalendartimeinterval (Non activé pour la prise en charge des champs personnalisés)</span><span class="sxs-lookup"><span data-stu-id="10f74-245">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="10f74-246">Compte bancaire du collaborateur</span><span class="sxs-lookup"><span data-stu-id="10f74-246">Worker Bank Account</span></span> | <span data-ttu-id="10f74-247">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="10f74-247">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="10f74-248">Entités de configuration des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="10f74-248">Worker setup entities</span></span>

| <span data-ttu-id="10f74-249">Nom</span><span class="sxs-lookup"><span data-stu-id="10f74-249">Name</span></span> | <span data-ttu-id="10f74-250">Entité</span><span class="sxs-lookup"><span data-stu-id="10f74-250">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="10f74-251">Statut d'ancien combattant</span><span class="sxs-lookup"><span data-stu-id="10f74-251">Veteran Status</span></span> | <span data-ttu-id="10f74-252">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="10f74-252">cdm_veteranstatus</span></span> |
| <span data-ttu-id="10f74-253">Origine ethnique</span><span class="sxs-lookup"><span data-stu-id="10f74-253">Ethnic Origin</span></span> | <span data-ttu-id="10f74-254">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="10f74-254">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="10f74-255">Code motif</span><span class="sxs-lookup"><span data-stu-id="10f74-255">Reason Code</span></span> | <span data-ttu-id="10f74-256">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="10f74-256">cdm_reasoncode</span></span> |
| <span data-ttu-id="10f74-257">Administration émettrice de l'identification des personnes</span><span class="sxs-lookup"><span data-stu-id="10f74-257">Person Identification Issuing Agency</span></span> | <span data-ttu-id="10f74-258">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="10f74-258">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="10f74-259">Entités de compétence</span><span class="sxs-lookup"><span data-stu-id="10f74-259">Competency entities</span></span>

| <span data-ttu-id="10f74-260">Nom</span><span class="sxs-lookup"><span data-stu-id="10f74-260">Name</span></span> | <span data-ttu-id="10f74-261">Entité</span><span class="sxs-lookup"><span data-stu-id="10f74-261">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="10f74-262">Type de qualification</span><span class="sxs-lookup"><span data-stu-id="10f74-262">Skill Type</span></span> | <span data-ttu-id="10f74-263">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="10f74-263">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="10f74-264">Modèles de relation d'entité</span><span class="sxs-lookup"><span data-stu-id="10f74-264">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="10f74-265">Collaborateur</span><span class="sxs-lookup"><span data-stu-id="10f74-265">Worker</span></span>

![Collaborateur](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="10f74-267">Emploi et poste</span><span class="sxs-lookup"><span data-stu-id="10f74-267">Job and Job Position</span></span>

![Emploi et poste](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="10f74-269">Avantages</span><span class="sxs-lookup"><span data-stu-id="10f74-269">Benefits</span></span>

![Avantages](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="10f74-271">Rémunération</span><span class="sxs-lookup"><span data-stu-id="10f74-271">Compensation</span></span>

![Rémunération](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="10f74-273">Quitter</span><span class="sxs-lookup"><span data-stu-id="10f74-273">Leave</span></span>

![Quitter](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="10f74-275">Calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="10f74-275">Work Calendar</span></span>

![Calendrier de travail](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="10f74-277">Voir également :</span><span class="sxs-lookup"><span data-stu-id="10f74-277">See also</span></span>

[<span data-ttu-id="10f74-278">Choisir une technologie d'intégration de données</span><span class="sxs-lookup"><span data-stu-id="10f74-278">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="10f74-279">Configuration de l'intégration Common Data Service</span><span class="sxs-lookup"><span data-stu-id="10f74-279">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)