---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (14 mai 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 14 mai 2020.
author: andreabichsel
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2c5ae1078e3490fef3383fc6d637df70128683e7
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051015"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a><span data-ttu-id="6ac47-103">Nouveautés ou modifications dans Dynamics 365 Human Resources (14 mai 2020)</span><span class="sxs-lookup"><span data-stu-id="6ac47-103">What's new or changed in Dynamics 365 Human Resources (May 14, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="6ac47-104">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6ac47-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="6ac47-105">Les modifications s’appliquent au numéro de version 8.1.3244.</span><span class="sxs-lookup"><span data-stu-id="6ac47-105">Changes apply to build number 8.1.3244.</span></span> <span data-ttu-id="6ac47-106">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support Lifecycle Services (LCS) pour référence.</span><span class="sxs-lookup"><span data-stu-id="6ac47-106">The numbers in parentheses in some headings refer to Lifecycle Services (LCS) support numbers for reference.</span></span>

## <a name="platform-changes"></a><span data-ttu-id="6ac47-107">Modifications de plateforme</span><span class="sxs-lookup"><span data-stu-id="6ac47-107">Platform changes</span></span>

<span data-ttu-id="6ac47-108">Des modifications de plateforme sont incluses dans la version de cette semaine.</span><span class="sxs-lookup"><span data-stu-id="6ac47-108">Platform changes are included in this week's release.</span></span> <span data-ttu-id="6ac47-109">Pour en savoir plus, consultez [Mises à jour de la plateforme pour la version 10.0.10 des applications Finance and Operations (mai 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34.md).</span><span class="sxs-lookup"><span data-stu-id="6ac47-109">For more information, see [Platform updates for version 10.0.10 of Finance and Operations apps (May 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34.md).</span></span> <span data-ttu-id="6ac47-110">Cette version inclut des corrections de bugs et des modifications des vues enregistrées.</span><span class="sxs-lookup"><span data-stu-id="6ac47-110">This release includes bug fixes and changes to saved views.</span></span>
 
## <a name="ensure-dataverse-picklists-are-consistent-with-leave-enums-436343"></a><span data-ttu-id="6ac47-111">Garantir que les listes de sélection Dataverse sont compatibles avec les énumérations relatives aux congés (436343)</span><span class="sxs-lookup"><span data-stu-id="6ac47-111">Ensure Dataverse picklists are consistent with Leave enums (436343)</span></span>

<span data-ttu-id="6ac47-112">Les listes de sélection Dataverse sont désormais compatibles avec les énumérations relatives aux congés.</span><span class="sxs-lookup"><span data-stu-id="6ac47-112">Dataverse picklists are now consistent with Leave enums.</span></span>

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a><span data-ttu-id="6ac47-113">Autoriser les utilisateurs à configurer le workflow de demande de congé en fonction du montant de la demande (300044)</span><span class="sxs-lookup"><span data-stu-id="6ac47-113">Allow users to configure leave request workflow based on the request amount (300044)</span></span>

<span data-ttu-id="6ac47-114">Les utilisateurs peuvent configurer les workflows de demande de congé en fonction des montants de la demande.</span><span class="sxs-lookup"><span data-stu-id="6ac47-114">Users can configure leave requests workflows based on request amounts.</span></span>
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a><span data-ttu-id="6ac47-115">Un nouveau formulaire de travail expose les données via le menu Afficher lorsque la sécurité avancée est activée (403185)</span><span class="sxs-lookup"><span data-stu-id="6ac47-115">New worker form exposes data through the View menu when advanced security is enabled (403185)</span></span>

<span data-ttu-id="6ac47-116">Cette version corrige le fonctionnement de l’affichage des employés dans les entités juridiques lorsque l’accès avancé est activé et que les employés d’autres entreprises sont accessibles.</span><span class="sxs-lookup"><span data-stu-id="6ac47-116">This release corrects how viewing workers across legal entities functions when advanced access is enabled and workers in other companies are accessible.</span></span>

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a><span data-ttu-id="6ac47-117">Autoriser les cumuls de congés pour un seul régime ou une seule entreprise (318844)</span><span class="sxs-lookup"><span data-stu-id="6ac47-117">Allow running leave accruals for a single plan or a single company (318844)</span></span>

<span data-ttu-id="6ac47-118">Avec cette modification, vous pouvez exécuter des régularisations pour une entreprise ou un plan.</span><span class="sxs-lookup"><span data-stu-id="6ac47-118">With this change, you can run accruals for a company or a plan.</span></span>
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a><span data-ttu-id="6ac47-119">Afficher l’équivalent temps plein (ETP) du poste dans le formulaire Collaborateurs inscrits (414658)</span><span class="sxs-lookup"><span data-stu-id="6ac47-119">Show the position's full-time equivalent (FTE) in the Enrolled workers form (414658)</span></span>

<span data-ttu-id="6ac47-120">La valeur ETP du poste d’un travailleur détermine le taux d’accumulation d’un travailleur lorsque l’option ETP est activée sur le type de congé.</span><span class="sxs-lookup"><span data-stu-id="6ac47-120">The FTE value from a worker's position determines a worker's accrual rate when the FTE option is enabled on the leave type.</span></span> <span data-ttu-id="6ac47-121">Ce champ est désormais inclus dans le formulaire **Collaborateurs inscrits** et la boîte de dialogue **Inscription en masse**.</span><span class="sxs-lookup"><span data-stu-id="6ac47-121">This field is now included in **Enrolled workers** form and the **Mass enrollment** dialog.</span></span>

## <a name="add-leave-balance-expiration-batch-job-431266"></a><span data-ttu-id="6ac47-122">Ajouter un traitement par lots d’expiration du solde de congés (431266)</span><span class="sxs-lookup"><span data-stu-id="6ac47-122">Add leave balance expiration batch job (431266)</span></span>

<span data-ttu-id="6ac47-123">Un nouveau traitement par lots est désormais disponible et s’exécute quotidiennement.</span><span class="sxs-lookup"><span data-stu-id="6ac47-123">A new batch job is now available that runs daily.</span></span> <span data-ttu-id="6ac47-124">Il diminue le solde de congés restant lorsque les dates d’expiration sont atteintes.</span><span class="sxs-lookup"><span data-stu-id="6ac47-124">It decreases the remaining leave balance when expiration dates become current.</span></span>

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a><span data-ttu-id="6ac47-125">L’exportation des contacts personnels d’un employé à l’aide de l’entité Personne à contacter personnelle du collaborateur n’exporte pas les contacts personnels avec le type de relation Parent (345893)</span><span class="sxs-lookup"><span data-stu-id="6ac47-125">Exporting personal contacts for an employee using the Worker personal contact person entity doesn't export personal contacts with the Parent relationship type (345893)</span></span>

<span data-ttu-id="6ac47-126">L’entité de données **Personne à contacter personnelle du collaborateur** (**HcmPersonalContactPersonEntity** dans DMF et **PersonalContactPerson** dans OData) n’a pas pu exporter les contacts personnels qui ont un type de relation **Parent**.</span><span class="sxs-lookup"><span data-stu-id="6ac47-126">The **Worker personal contact person** data entity (**HcmPersonalContactPersonEntity** in DMF and **PersonalContactPerson** in OData) couldn't export personal contacts that have a relationship type of **Parent**.</span></span> <span data-ttu-id="6ac47-127">Ce problème est résolu pour les contacts personnels créés après cette modification.</span><span class="sxs-lookup"><span data-stu-id="6ac47-127">This issue is fixed for personal contacts that are created after this change.</span></span> <span data-ttu-id="6ac47-128">Les contacts personnels existants de type **Parent** seront corrigés dans une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="6ac47-128">Existing personal contacts of type **Parent** will be fixed in a later release.</span></span>

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a><span data-ttu-id="6ac47-129">Les codes de motif s’affichent dans différents scénarios lorsqu’ils sont marqués comme Congé et absence et que le formulaire d’employé rationalisé est activé (434163)</span><span class="sxs-lookup"><span data-stu-id="6ac47-129">Reason codes display across different scenarios when they're marked as Leave and absence and the streamlined employee form is enabled (434163)</span></span>

<span data-ttu-id="6ac47-130">Cette modification limite les codes de motif aux codes de congé et d’absence uniquement lorsque vous activez la saisie simplifiée des employés.</span><span class="sxs-lookup"><span data-stu-id="6ac47-130">This change restricts the reason codes to only Leave and absence codes when you enable streamlined employee entry.</span></span>

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a><span data-ttu-id="6ac47-131">La fonction d’aperçu Attribuer un plan de congés aux employés dans le future affiche une erreur (433555)</span><span class="sxs-lookup"><span data-stu-id="6ac47-131">The preview feature Assign a leave plan to employees in the future displays error (433555)</span></span>

<span data-ttu-id="6ac47-132">Cette modification corrige une erreur lorsqu’un plan de congé a deux types de congé affectés et que vous essayez d’affecter un employé.</span><span class="sxs-lookup"><span data-stu-id="6ac47-132">This change corrects an error when a leave plan has two leave types assigned and you attempt to assign an employee.</span></span>

## <a name="getting-started-banner-appears-for-all-users-441731"></a><span data-ttu-id="6ac47-133">La bannière de mise en route apparaît pour tous les utilisateurs (441731)</span><span class="sxs-lookup"><span data-stu-id="6ac47-133">Getting started banner appears for all users (441731)</span></span>

<span data-ttu-id="6ac47-134">Avec cette modification, la bannière de mise en route est masquée pour les utilisateurs qui ne sont pas administrateurs système ou administrateurs de gestion des données.</span><span class="sxs-lookup"><span data-stu-id="6ac47-134">With this change, the Getting started banner is hidden for users that aren't System administrators or Data management administrators.</span></span> 

## <a name="the-dataverse-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a><span data-ttu-id="6ac47-135">L’entité Adresse du collaborateur Dataverse fonctionne différemment en termes de dates d’effet date-heure dans Human Resources (425071)</span><span class="sxs-lookup"><span data-stu-id="6ac47-135">The Dataverse Worker Address entity works differently in terms of date time effective dates in Human Resources (425071)</span></span>

<span data-ttu-id="6ac47-136">Cette modification maintient les informations d’adresse alignées dans certains scénarios, en fonction des dates de l’adresse.</span><span class="sxs-lookup"><span data-stu-id="6ac47-136">This change keeps address information aligned in certain scenarios, based on the dates of the address.</span></span>

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a><span data-ttu-id="6ac47-137">Impossible d’ajouter une pièce jointe à une demande de congé approuvée (425407)</span><span class="sxs-lookup"><span data-stu-id="6ac47-137">Unable to add an attachment to an approved leave request (425407)</span></span>

<span data-ttu-id="6ac47-138">Avec la version de cette semaine, vous pouvez ajouter des pièces jointes aux demandes de congé approuvées sans modifier la demande de congé.</span><span class="sxs-lookup"><span data-stu-id="6ac47-138">With this week's release, you can add attachments to approved leave requests without changing the leave request.</span></span>

## <a name="in-preview"></a><span data-ttu-id="6ac47-139">En mode aperçu</span><span class="sxs-lookup"><span data-stu-id="6ac47-139">In preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="6ac47-140">Suspension des congés</span><span class="sxs-lookup"><span data-stu-id="6ac47-140">Leave suspension</span></span>

<span data-ttu-id="6ac47-141">Vous pouvez suspendre les congés et les absences d’un employé dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6ac47-141">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="6ac47-142">La suspension des congés arrête les régularisations de congés pour les types de congé sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="6ac47-142">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="6ac47-143">Si la suspension survient après le traitement d’une régularisation, la suspension du congé crée un ajustement au prorata du solde des congés de l’employé.</span><span class="sxs-lookup"><span data-stu-id="6ac47-143">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="6ac47-144">Pour plus d’informations, voir la rubrique [Suspension des congés](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="6ac47-144">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="6ac47-145">Mettre à jour l’expérience utilisateur pour indiquer que la comptabilité d’exercice est suspendue (429550)</span><span class="sxs-lookup"><span data-stu-id="6ac47-145">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="6ac47-146">L’expérience utilisateur indique désormais que la comptabilité d’exercice a été suspendue pour un plan.</span><span class="sxs-lookup"><span data-stu-id="6ac47-146">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a><span data-ttu-id="6ac47-147">Suspendre l’accumulation de congés pour certains types de congés (272447)</span><span class="sxs-lookup"><span data-stu-id="6ac47-147">Suspend leave accrual for specified leave types (272447)</span></span>

<span data-ttu-id="6ac47-148">Dans cette version, les RH peuvent créer une règle pour suspendre les cumuls de congés pour les employés dont les demandes de congés ont été saisies pour des congés non payés.</span><span class="sxs-lookup"><span data-stu-id="6ac47-148">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="6ac47-149">Le congé sans solde peut être un type, mais ce n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="6ac47-149">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="6ac47-150">Vous pouvez suspendre tout congé basé sur un autre type de congé.</span><span class="sxs-lookup"><span data-stu-id="6ac47-150">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a><span data-ttu-id="6ac47-151">Entité DMF disponible pour les suspensions de régularisation (429549)</span><span class="sxs-lookup"><span data-stu-id="6ac47-151">DMF entity available for accrual suspensions (429549)</span></span>

<span data-ttu-id="6ac47-152">Une entité DMF est désormais disponible pour les suspensions de régularisation.</span><span class="sxs-lookup"><span data-stu-id="6ac47-152">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-429547"></a><span data-ttu-id="6ac47-153">Ajouter un code de motif aux suspensions de cumul (429547)</span><span class="sxs-lookup"><span data-stu-id="6ac47-153">Add reason code to accrual suspensions (429547)</span></span>

<span data-ttu-id="6ac47-154">Des codes de motif ont été ajoutés à la suspension de la comptabilité d’exercice.</span><span class="sxs-lookup"><span data-stu-id="6ac47-154">Reason codes have been added to the accrual suspension.</span></span>

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a><span data-ttu-id="6ac47-155">Commencer la transition des paramètres des Ressources humaines vers les paramètres de congés et d’absence</span><span class="sxs-lookup"><span data-stu-id="6ac47-155">Begin transitioning from Human Resources parameters to leave and absence parameters</span></span>

<span data-ttu-id="6ac47-156">Cette version commence à combiner les paramètres des Ressources humaines avec les paramètres de Congé et d’absence.</span><span class="sxs-lookup"><span data-stu-id="6ac47-156">This release starts to combine Human Resources parameters with Leave and absence parameters.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="6ac47-157">Règles de report</span><span class="sxs-lookup"><span data-stu-id="6ac47-157">Carry forward rules</span></span>

<span data-ttu-id="6ac47-158">Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés.</span><span class="sxs-lookup"><span data-stu-id="6ac47-158">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="6ac47-159">Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours.</span><span class="sxs-lookup"><span data-stu-id="6ac47-159">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="6ac47-160">Pour plus d’informations, voir [Configurer les types de congé et d’absence](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="6ac47-160">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ac47-161">Voir également :</span><span class="sxs-lookup"><span data-stu-id="6ac47-161">See also</span></span>

[<span data-ttu-id="6ac47-162">Nouveautés ou modifications dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="6ac47-162">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="6ac47-163">Présentation de Dynamics 365 Human Resources 2019 vague de publication 2</span><span class="sxs-lookup"><span data-stu-id="6ac47-163">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="6ac47-164">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="6ac47-164">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="6ac47-165">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="6ac47-165">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]