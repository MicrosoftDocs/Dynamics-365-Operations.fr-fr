---
title: Tables Dataverse
description: Microsoft Dynamics 365 Human Resources utilise Dataverse pour permettre des scénarios d’extensibilité et d’intégration.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8ddb74a2f0b6265c5be3c13a009211455ea862da
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893398"
---
# <a name="dataverse-tables"></a><span data-ttu-id="d45ed-103">Tables Dataverse</span><span class="sxs-lookup"><span data-stu-id="d45ed-103">Dataverse tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d45ed-104">Microsoft Dynamics 365 Human Resources utilise Dataverse pour permettre des scénarios d’extensibilité et d’intégration.</span><span class="sxs-lookup"><span data-stu-id="d45ed-104">Microsoft Dynamics 365 Human Resources uses Dataverse to enable extensibility and integration scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="d45ed-105">Les entités Human Resources correspondent aux tables Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d45ed-105">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="d45ed-106">Pour plus d’informations sur Dataverse (auparavant Common Data Service) et les mises à jour terminologiques, voir [Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="d45ed-106">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="d45ed-107">Les tables Dataverse suivantes sont disponibles dans les entités Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d45ed-107">The following Dataverse tables are available based on Human Resources entities.</span></span>

## <a name="benefit-tables"></a><span data-ttu-id="d45ed-108">Tables des avantages</span><span class="sxs-lookup"><span data-stu-id="d45ed-108">Benefit tables</span></span>

| <span data-ttu-id="d45ed-109">Nom</span><span class="sxs-lookup"><span data-stu-id="d45ed-109">Name</span></span> | <span data-ttu-id="d45ed-110">Table</span><span class="sxs-lookup"><span data-stu-id="d45ed-110">Table</span></span> |
| --- | --- |
| <span data-ttu-id="d45ed-111">Fréquence de calcul des avantages</span><span class="sxs-lookup"><span data-stu-id="d45ed-111">Benefit Calculation Frequency</span></span> | <span data-ttu-id="d45ed-112">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="d45ed-112">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="d45ed-113">Fréquence de calcul des avantages de la période de rémunération</span><span class="sxs-lookup"><span data-stu-id="d45ed-113">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="d45ed-114">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="d45ed-114">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="d45ed-115">Taux de calcul des avantages</span><span class="sxs-lookup"><span data-stu-id="d45ed-115">Benefit Calculation Rate</span></span> | <span data-ttu-id="d45ed-116">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="d45ed-116">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="d45ed-117">Détails du taux de calcul des avantages</span><span class="sxs-lookup"><span data-stu-id="d45ed-117">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="d45ed-118">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="d45ed-118">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="d45ed-119">Option d’avantage</span><span class="sxs-lookup"><span data-stu-id="d45ed-119">Benefit Option</span></span> | <span data-ttu-id="d45ed-120">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="d45ed-120">cdm_benefitoption</span></span> |
| <span data-ttu-id="d45ed-121">Plan d’avantages</span><span class="sxs-lookup"><span data-stu-id="d45ed-121">Benefit Plan</span></span> | <span data-ttu-id="d45ed-122">cdm_benefitplan (Non activé pour la prise en charge des champs personnalisés)</span><span class="sxs-lookup"><span data-stu-id="d45ed-122">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="d45ed-123">Type d’avantage</span><span class="sxs-lookup"><span data-stu-id="d45ed-123">Benefit Type</span></span> | <span data-ttu-id="d45ed-124">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="d45ed-124">cdm_benefittype</span></span> |

## <a name="business-process-tasks-tables"></a><span data-ttu-id="d45ed-125">Tables des tâches de processus d’entreprise</span><span class="sxs-lookup"><span data-stu-id="d45ed-125">Business process tasks tables</span></span>

| <span data-ttu-id="d45ed-126">Nom</span><span class="sxs-lookup"><span data-stu-id="d45ed-126">Name</span></span> | <span data-ttu-id="d45ed-127">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="d45ed-127">Table</span></span> |
| --- | --- |
| <span data-ttu-id="d45ed-128">Calendrier pour le processus d’entreprise</span><span class="sxs-lookup"><span data-stu-id="d45ed-128">Business Process Calendar</span></span> | <span data-ttu-id="d45ed-129">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="d45ed-129">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="d45ed-130">Affectation du groupe de processus d’entreprise</span><span class="sxs-lookup"><span data-stu-id="d45ed-130">Business Process Group Assignment</span></span> | <span data-ttu-id="d45ed-131">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="d45ed-131">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="d45ed-132">Groupe de tâches de la bibliothèque de processus d’entreprise</span><span class="sxs-lookup"><span data-stu-id="d45ed-132">Business Process Library Task Group</span></span> | <span data-ttu-id="d45ed-133">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="d45ed-133">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="d45ed-134">Phase du processus d’entreprise</span><span class="sxs-lookup"><span data-stu-id="d45ed-134">Business Process Stage</span></span> | <span data-ttu-id="d45ed-135">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="d45ed-135">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="d45ed-136">En-tête de modèle de liste de contrôle</span><span class="sxs-lookup"><span data-stu-id="d45ed-136">Checklist Template Header</span></span> | <span data-ttu-id="d45ed-137">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="d45ed-137">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="d45ed-138">Tâche du modèle de liste de contrôle</span><span class="sxs-lookup"><span data-stu-id="d45ed-138">Checklist Template Task</span></span> | <span data-ttu-id="d45ed-139">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="d45ed-139">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-tables"></a><span data-ttu-id="d45ed-140">Tables de rémunération</span><span class="sxs-lookup"><span data-stu-id="d45ed-140">Compensation tables</span></span>

| <span data-ttu-id="d45ed-141">Nom</span><span class="sxs-lookup"><span data-stu-id="d45ed-141">Name</span></span> | <span data-ttu-id="d45ed-142">Table</span><span class="sxs-lookup"><span data-stu-id="d45ed-142">Table</span></span> |
| --- | --- |
| <span data-ttu-id="d45ed-143">Régime fixe de rémunération</span><span class="sxs-lookup"><span data-stu-id="d45ed-143">Compensation Fixed Plan</span></span> | <span data-ttu-id="d45ed-144">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="d45ed-144">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="d45ed-145">Grille de rémunération</span><span class="sxs-lookup"><span data-stu-id="d45ed-145">Compensation Grid</span></span> | <span data-ttu-id="d45ed-146">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="d45ed-146">cdm_compensationgrid</span></span> |
| <span data-ttu-id="d45ed-147">Niveau de rémunération</span><span class="sxs-lookup"><span data-stu-id="d45ed-147">Compensation Level</span></span> | <span data-ttu-id="d45ed-148">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="d45ed-148">cdm_compensationlevel</span></span> |
| <span data-ttu-id="d45ed-149">Fréquence de paiement de la rémunération</span><span class="sxs-lookup"><span data-stu-id="d45ed-149">Compensation Pay Frequency</span></span> | <span data-ttu-id="d45ed-150">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="d45ed-150">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="d45ed-151">Paramétrage des points de référence de rémunération</span><span class="sxs-lookup"><span data-stu-id="d45ed-151">Compensation Reference Point Setup</span></span> | <span data-ttu-id="d45ed-152">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="d45ed-152">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="d45ed-153">Ligne de paramétrage des points de référence de rémunération</span><span class="sxs-lookup"><span data-stu-id="d45ed-153">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="d45ed-154">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="d45ed-154">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="d45ed-155">Région de rémunération</span><span class="sxs-lookup"><span data-stu-id="d45ed-155">Compensation Region</span></span> | <span data-ttu-id="d45ed-156">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="d45ed-156">cdm_compensationregion</span></span> |
| <span data-ttu-id="d45ed-157">Structure des rémunérations</span><span class="sxs-lookup"><span data-stu-id="d45ed-157">Compensation Structure</span></span> | <span data-ttu-id="d45ed-158">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="d45ed-158">cdm_compensationstructure</span></span> |
| <span data-ttu-id="d45ed-159">Régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="d45ed-159">Compensation Variable Plan</span></span> | <span data-ttu-id="d45ed-160">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="d45ed-160">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="d45ed-161">Niveau du régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="d45ed-161">Compensation Variable Plan Level</span></span> | <span data-ttu-id="d45ed-162">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="d45ed-162">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="d45ed-163">Type du régime rémunération variable</span><span class="sxs-lookup"><span data-stu-id="d45ed-163">Compensation Variable Plan Type</span></span> | <span data-ttu-id="d45ed-164">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="d45ed-164">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="d45ed-165">Événement de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="d45ed-165">Fixed Compensation Event</span></span> | <span data-ttu-id="d45ed-166">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="d45ed-166">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="d45ed-167">Règle d’acquisition</span><span class="sxs-lookup"><span data-stu-id="d45ed-167">Vesting Rule</span></span> | <span data-ttu-id="d45ed-168">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="d45ed-168">cdm_vestingrule</span></span> |
| <span data-ttu-id="d45ed-169">Rémunération fixe du collaborateur</span><span class="sxs-lookup"><span data-stu-id="d45ed-169">Worker Fixed Compensation</span></span> | <span data-ttu-id="d45ed-170">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="d45ed-170">cdm_workerfixedcompensation</span></span> |

## <a name="organization-tables"></a><span data-ttu-id="d45ed-171">Tables d’organisation</span><span class="sxs-lookup"><span data-stu-id="d45ed-171">Organization tables</span></span>

| <span data-ttu-id="d45ed-172">Nom</span><span class="sxs-lookup"><span data-stu-id="d45ed-172">Name</span></span> | <span data-ttu-id="d45ed-173">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="d45ed-173">Table</span></span> |
| --- | --- |
| <span data-ttu-id="d45ed-174">Département</span><span class="sxs-lookup"><span data-stu-id="d45ed-174">Department</span></span> | <span data-ttu-id="d45ed-175">cdm_department</span><span class="sxs-lookup"><span data-stu-id="d45ed-175">cdm_department</span></span> |
| <span data-ttu-id="d45ed-176">Emploi</span><span class="sxs-lookup"><span data-stu-id="d45ed-176">Employment</span></span> | <span data-ttu-id="d45ed-177">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="d45ed-177">cdm_employment</span></span> |
| <span data-ttu-id="d45ed-178">Société</span><span class="sxs-lookup"><span data-stu-id="d45ed-178">Company</span></span> | <span data-ttu-id="d45ed-179">cdm_company</span><span class="sxs-lookup"><span data-stu-id="d45ed-179">cdm_company</span></span> |
| <span data-ttu-id="d45ed-180">Mission</span><span class="sxs-lookup"><span data-stu-id="d45ed-180">Job</span></span> | <span data-ttu-id="d45ed-181">cdm_job</span><span class="sxs-lookup"><span data-stu-id="d45ed-181">cdm_job</span></span> |
| <span data-ttu-id="d45ed-182">Fonction de tâche</span><span class="sxs-lookup"><span data-stu-id="d45ed-182">Job Function</span></span> | <span data-ttu-id="d45ed-183">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="d45ed-183">cdm_jobfunction</span></span> |
| <span data-ttu-id="d45ed-184">Poste</span><span class="sxs-lookup"><span data-stu-id="d45ed-184">Job Position</span></span> | <span data-ttu-id="d45ed-185">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="d45ed-185">cdm_jobposition</span></span> |
| <span data-ttu-id="d45ed-186">Type de poste</span><span class="sxs-lookup"><span data-stu-id="d45ed-186">Position Type</span></span> | <span data-ttu-id="d45ed-187">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="d45ed-187">cdm_positiontype</span></span> |
| <span data-ttu-id="d45ed-188">Affectation du collaborateur au poste</span><span class="sxs-lookup"><span data-stu-id="d45ed-188">Position Worker Assignment</span></span> | <span data-ttu-id="d45ed-189">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="d45ed-189">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="d45ed-190">Dimension du poste</span><span class="sxs-lookup"><span data-stu-id="d45ed-190">Job Position Dimension</span></span> | <span data-ttu-id="d45ed-191">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="d45ed-191">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="d45ed-192">Type de poste</span><span class="sxs-lookup"><span data-stu-id="d45ed-192">Job Type</span></span> | <span data-ttu-id="d45ed-193">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="d45ed-193">cdm_jobtype</span></span> |
| <span data-ttu-id="d45ed-194">Langue</span><span class="sxs-lookup"><span data-stu-id="d45ed-194">Language</span></span> | <span data-ttu-id="d45ed-195">cdm_language</span><span class="sxs-lookup"><span data-stu-id="d45ed-195">cdm_language</span></span> |
| <span data-ttu-id="d45ed-196">Titre</span><span class="sxs-lookup"><span data-stu-id="d45ed-196">Title</span></span> | <span data-ttu-id="d45ed-197">cdm_title</span><span class="sxs-lookup"><span data-stu-id="d45ed-197">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="d45ed-198">Les dimensions financières pour **Type de poste**, **Affectation du collaborateur au poste** et **Emploi** fournissent une intégration unidirectionnelle vers Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d45ed-198">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Dataverse.</span></span> <span data-ttu-id="d45ed-199">Les mises à jour des dimensions financières ne peuvent actuellement pas se synchroniser de Dataverse vers Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d45ed-199">Financial dimensions updates currently can't synchronize from Dataverse to Human Resources.</span></span> 

## <a name="leave-and-absence-tables"></a><span data-ttu-id="d45ed-200">Tables de congés et d’absences</span><span class="sxs-lookup"><span data-stu-id="d45ed-200">Leave and absence tables</span></span>

| <span data-ttu-id="d45ed-201">Nom</span><span class="sxs-lookup"><span data-stu-id="d45ed-201">Name</span></span> | <span data-ttu-id="d45ed-202">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="d45ed-202">Table</span></span> |
| --- | --- |
| <span data-ttu-id="d45ed-203">Transaction bancaire de congé</span><span class="sxs-lookup"><span data-stu-id="d45ed-203">Leave Bank Transaction</span></span> | <span data-ttu-id="d45ed-204">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="d45ed-204">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="d45ed-205">Inscription à un congé</span><span class="sxs-lookup"><span data-stu-id="d45ed-205">Leave Enrollment</span></span> | <span data-ttu-id="d45ed-206">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="d45ed-206">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="d45ed-207">Plan de congé</span><span class="sxs-lookup"><span data-stu-id="d45ed-207">Leave Plan</span></span> | <span data-ttu-id="d45ed-208">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="d45ed-208">cdm_leaveplan</span></span> |
| <span data-ttu-id="d45ed-209">Demande de congé</span><span class="sxs-lookup"><span data-stu-id="d45ed-209">Leave Request</span></span> | <span data-ttu-id="d45ed-210">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="d45ed-210">cdm_leaverequest</span></span> |
| <span data-ttu-id="d45ed-211">Détails de la demande de congés</span><span class="sxs-lookup"><span data-stu-id="d45ed-211">Leave Request Detail</span></span> | <span data-ttu-id="d45ed-212">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="d45ed-212">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="d45ed-213">Type de congé</span><span class="sxs-lookup"><span data-stu-id="d45ed-213">Leave Type</span></span> | <span data-ttu-id="d45ed-214">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="d45ed-214">cdm_leavetype</span></span> |
| <span data-ttu-id="d45ed-215">Code motif du type de congé</span><span class="sxs-lookup"><span data-stu-id="d45ed-215">Leave Type Reason Code</span></span> | <span data-ttu-id="d45ed-216">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="d45ed-216">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-tables"></a><span data-ttu-id="d45ed-217">Tables des salaires</span><span class="sxs-lookup"><span data-stu-id="d45ed-217">Payroll tables</span></span>

| <span data-ttu-id="d45ed-218">Nom</span><span class="sxs-lookup"><span data-stu-id="d45ed-218">Name</span></span> | <span data-ttu-id="d45ed-219">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="d45ed-219">Table</span></span> |
| --- | --- |
| <span data-ttu-id="d45ed-220">Cycle de paie</span><span class="sxs-lookup"><span data-stu-id="d45ed-220">Pay Cycle</span></span> | <span data-ttu-id="d45ed-221">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="d45ed-221">cdm_paycycle</span></span> |
| <span data-ttu-id="d45ed-222">Période de rémunération</span><span class="sxs-lookup"><span data-stu-id="d45ed-222">Pay Period</span></span> | <span data-ttu-id="d45ed-223">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="d45ed-223">cdm_payperiod</span></span> |
| <span data-ttu-id="d45ed-224">Code de rémunération des salaires</span><span class="sxs-lookup"><span data-stu-id="d45ed-224">Payroll Earning Code</span></span> | <span data-ttu-id="d45ed-225">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="d45ed-225">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="d45ed-226">Décaissements du compte en banque</span><span class="sxs-lookup"><span data-stu-id="d45ed-226">Bank Account Disbursement</span></span> | <span data-ttu-id="d45ed-227">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="d45ed-227">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="d45ed-228">Zone fiscale</span><span class="sxs-lookup"><span data-stu-id="d45ed-228">Tax Region</span></span> | <span data-ttu-id="d45ed-229">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="d45ed-229">cdm_taxregion</span></span> |

## <a name="worker-tables"></a><span data-ttu-id="d45ed-230">Tables des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="d45ed-230">Worker tables</span></span>

| <span data-ttu-id="d45ed-231">Nom</span><span class="sxs-lookup"><span data-stu-id="d45ed-231">Name</span></span> | <span data-ttu-id="d45ed-232">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="d45ed-232">Table</span></span> |
| --- | --- |
| <span data-ttu-id="d45ed-233">Collaborateur</span><span class="sxs-lookup"><span data-stu-id="d45ed-233">Worker</span></span> | <span data-ttu-id="d45ed-234">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="d45ed-234">cdm_worker</span></span> |
| <span data-ttu-id="d45ed-235">Adresse du collaborateur</span><span class="sxs-lookup"><span data-stu-id="d45ed-235">Worker Address</span></span> | <span data-ttu-id="d45ed-236">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="d45ed-236">cdm_workeraddress</span></span> |
| <span data-ttu-id="d45ed-237">Détails personnels du collaborateur</span><span class="sxs-lookup"><span data-stu-id="d45ed-237">Worker Personal Detail</span></span> | <span data-ttu-id="d45ed-238">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="d45ed-238">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="d45ed-239">Numéro d’identification personnel du collaborateur</span><span class="sxs-lookup"><span data-stu-id="d45ed-239">Worker Person Identification Number</span></span> | <span data-ttu-id="d45ed-240">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="d45ed-240">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="d45ed-241">Type d’identification personnel du collaborateur</span><span class="sxs-lookup"><span data-stu-id="d45ed-241">Worker Person Identification Type</span></span> | <span data-ttu-id="d45ed-242">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="d45ed-242">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="d45ed-243">Calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="d45ed-243">Work Calendar</span></span> | <span data-ttu-id="d45ed-244">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="d45ed-244">cdm_workcalendar</span></span> |
| <span data-ttu-id="d45ed-245">Jours de calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="d45ed-245">Work Calendar Day</span></span> | <span data-ttu-id="d45ed-246">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="d45ed-246">cdm_workcalendarday</span></span> |
| <span data-ttu-id="d45ed-247">Congé du calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="d45ed-247">Work Calendar Holiday</span></span> |<span data-ttu-id="d45ed-248">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="d45ed-248">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="d45ed-249">Ligne de congé du calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="d45ed-249">Work Calendar Holiday Line</span></span> | <span data-ttu-id="d45ed-250">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="d45ed-250">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="d45ed-251">Intervalle de temps du calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="d45ed-251">Work Calendar Time Interval</span></span> | <span data-ttu-id="d45ed-252">cdm_workcalendartimeinterval (Non activé pour la prise en charge des champs personnalisés)</span><span class="sxs-lookup"><span data-stu-id="d45ed-252">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="d45ed-253">Compte bancaire du collaborateur</span><span class="sxs-lookup"><span data-stu-id="d45ed-253">Worker Bank Account</span></span> | <span data-ttu-id="d45ed-254">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="d45ed-254">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-tables"></a><span data-ttu-id="d45ed-255">Tables de configuration des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="d45ed-255">Worker setup tables</span></span>

| <span data-ttu-id="d45ed-256">Nom</span><span class="sxs-lookup"><span data-stu-id="d45ed-256">Name</span></span> | <span data-ttu-id="d45ed-257">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="d45ed-257">Table</span></span> |
| --- | --- |
| <span data-ttu-id="d45ed-258">Statut de vétéran</span><span class="sxs-lookup"><span data-stu-id="d45ed-258">Veteran Status</span></span> | <span data-ttu-id="d45ed-259">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="d45ed-259">cdm_veteranstatus</span></span> |
| <span data-ttu-id="d45ed-260">Origine ethnique</span><span class="sxs-lookup"><span data-stu-id="d45ed-260">Ethnic Origin</span></span> | <span data-ttu-id="d45ed-261">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="d45ed-261">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="d45ed-262">Code motif</span><span class="sxs-lookup"><span data-stu-id="d45ed-262">Reason Code</span></span> | <span data-ttu-id="d45ed-263">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="d45ed-263">cdm_reasoncode</span></span> |
| <span data-ttu-id="d45ed-264">Agence émettrice de l’identification de la personne</span><span class="sxs-lookup"><span data-stu-id="d45ed-264">Person Identification Issuing Agency</span></span> | <span data-ttu-id="d45ed-265">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="d45ed-265">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-tables"></a><span data-ttu-id="d45ed-266">Tables des compétences</span><span class="sxs-lookup"><span data-stu-id="d45ed-266">Competency tables</span></span>

| <span data-ttu-id="d45ed-267">Nom</span><span class="sxs-lookup"><span data-stu-id="d45ed-267">Name</span></span> | <span data-ttu-id="d45ed-268">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="d45ed-268">Table</span></span> |
| --- | --- |
| <span data-ttu-id="d45ed-269">Type de qualification</span><span class="sxs-lookup"><span data-stu-id="d45ed-269">Skill Type</span></span> | <span data-ttu-id="d45ed-270">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="d45ed-270">cdm_skilltype</span></span> |

## <a name="table-relationship-models"></a><span data-ttu-id="d45ed-271">Modèles de relations de table</span><span class="sxs-lookup"><span data-stu-id="d45ed-271">Table relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="d45ed-272">Collaborateur</span><span class="sxs-lookup"><span data-stu-id="d45ed-272">Worker</span></span>

![Collaborateur](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="d45ed-274">Emploi et poste</span><span class="sxs-lookup"><span data-stu-id="d45ed-274">Job and Job Position</span></span>

![Emploi et poste](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="d45ed-276">Avantages</span><span class="sxs-lookup"><span data-stu-id="d45ed-276">Benefits</span></span>

![Avantages](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="d45ed-278">Rémunération</span><span class="sxs-lookup"><span data-stu-id="d45ed-278">Compensation</span></span>

![Rémunération](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="d45ed-280">Quitter</span><span class="sxs-lookup"><span data-stu-id="d45ed-280">Leave</span></span>

![Quitter](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="d45ed-282">Calendrier de travail</span><span class="sxs-lookup"><span data-stu-id="d45ed-282">Work Calendar</span></span>

![Calendrier de travail](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="d45ed-284">Voir également :</span><span class="sxs-lookup"><span data-stu-id="d45ed-284">See also</span></span>

[<span data-ttu-id="d45ed-285">Choisir une technologie d’intégration de données</span><span class="sxs-lookup"><span data-stu-id="d45ed-285">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)<br>
[<span data-ttu-id="d45ed-286">Configuration de l’intégration Dataverse</span><span class="sxs-lookup"><span data-stu-id="d45ed-286">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)<br>
[<span data-ttu-id="d45ed-287">Configurer des tables virtuelles Dataverse</span><span class="sxs-lookup"><span data-stu-id="d45ed-287">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="d45ed-288">FAQ sur les tables virtuelles Human Resources</span><span class="sxs-lookup"><span data-stu-id="d45ed-288">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="d45ed-289">Qu’est-ce que Microsoft Dataverse ?</span><span class="sxs-lookup"><span data-stu-id="d45ed-289">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="d45ed-290">Mises à jour de la terminologie</span><span class="sxs-lookup"><span data-stu-id="d45ed-290">Terminology updates</span></span>](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]