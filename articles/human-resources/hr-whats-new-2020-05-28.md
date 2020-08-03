---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (28 mai 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7664afbd0b1fd4e2c9686053fa102d85809c0411
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555313"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a><span data-ttu-id="df872-103">Nouveautés ou modifications dans Dynamics 365 Human Resources (28 mai 2020)</span><span class="sxs-lookup"><span data-stu-id="df872-103">What's new or changed in Dynamics 365 Human Resources (May 28, 2020)</span></span>

<span data-ttu-id="df872-104">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="df872-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="df872-105">Les modifications s'appliquent au numéro de version 8.1.3287.</span><span class="sxs-lookup"><span data-stu-id="df872-105">Changes apply to build number 8.1.3287.</span></span> <span data-ttu-id="df872-106">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.</span><span class="sxs-lookup"><span data-stu-id="df872-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a><span data-ttu-id="df872-107">L'entité LeaveRequest ne fonctionne pas lorsque vous activez plusieurs types par plan de congé (447498)</span><span class="sxs-lookup"><span data-stu-id="df872-107">LeaveRequest entity doesn't work when you enable multiple types per leave plan (447498)</span></span>

<span data-ttu-id="df872-108">Avec cette modification, l'entité **LeaveEnrollmentV2Entity** est désormais disponible pour corriger l'erreur qui se produit lorsque vous activez plusieurs types de congé.</span><span class="sxs-lookup"><span data-stu-id="df872-108">With this change, the **LeaveEnrollmentV2Entity** is now available to correct the error that occurs when you enable multiple leave types.</span></span>

## <a name="batch-contention-reduction-feature-preview-446619"></a><span data-ttu-id="df872-109">Fonction de réduction des conflits de lots (préversion) (446619)</span><span class="sxs-lookup"><span data-stu-id="df872-109">Batch contention reduction feature (preview) (446619)</span></span>

<span data-ttu-id="df872-110">Lorsque vous activez cette fonctionnalité, vous pouvez vous attendre à une réduction des blocages dans les tables de cadre par lots lors de la sélection des tâches et l'achèvement des tâches.</span><span class="sxs-lookup"><span data-stu-id="df872-110">When you enable this feature, you can expect a reduction in blocking on batch framework tables while selecting tasks and finishing jobs.</span></span>

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a><span data-ttu-id="df872-111">UpdateConflict pendant l'enregistrement d'un collaborateur empêche de modifier un enregistrement dans Personnes (427915)</span><span class="sxs-lookup"><span data-stu-id="df872-111">UpdateConflict while saving worker prevents editing a record in People (427915)</span></span>

<span data-ttu-id="df872-112">Cette modification corrige une erreur lors de l'ajout d'un nouveau collaborateur, de la mise à jour des informations d'adresse et de la modification des préférences linguistiques.</span><span class="sxs-lookup"><span data-stu-id="df872-112">This change corrects an error when adding a new worker, updating address information, and changing language preference.</span></span> <span data-ttu-id="df872-113">Dans ce scénario unique, une erreur s'affiche indiquant que l'enregistrement n'a pas pu être mis à jour.</span><span class="sxs-lookup"><span data-stu-id="df872-113">In this unique scenario, an error displayed indicating the record couldn't be updated.</span></span> 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a><span data-ttu-id="df872-114">Impossible d'ajouter une pièce jointe à une demande de congé approuvée à soumettre à nouveau (425407)</span><span class="sxs-lookup"><span data-stu-id="df872-114">Unable to add an attachment to an approved leave request to resubmit (425407)</span></span>

<span data-ttu-id="df872-115">Cette modification autorise désormais de joindre des documents aux demandes de congé approuvées.</span><span class="sxs-lookup"><span data-stu-id="df872-115">This change now allows attachments to approved leave requests.</span></span>

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a><span data-ttu-id="df872-116">L'utilisateur peut saisir la rémunération d'un collaborateur dans un formulaire d'entité juridique différent (409529)</span><span class="sxs-lookup"><span data-stu-id="df872-116">User can enter compensation for an employee in a different legal entity form (409529)</span></span>

<span data-ttu-id="df872-117">Cette modification désactive les options de rémunération pour empêcher la saisie par inadvertance d'enregistrements de rémunération pour la mauvaise entité juridique.</span><span class="sxs-lookup"><span data-stu-id="df872-117">This change disables compensation options to prevent inadvertent entry of compensation records for the wrong legal entity.</span></span>

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a><span data-ttu-id="df872-118">Erreur lorsque vous transférez un collaborateur et que la date d'affectation de poste du collaborateur est antérieure à la durée du poste (429402)</span><span class="sxs-lookup"><span data-stu-id="df872-118">Error when you transfer an employee and the Worker position assignment date is before the position duration (429402)</span></span>

<span data-ttu-id="df872-119">Les messages d'erreur lors du transfert d'un collaborateur dans ce scénario ont été mis à jour pour mieux décrire les modifications nécessaires pour corriger le problème.</span><span class="sxs-lookup"><span data-stu-id="df872-119">Error messages when transferring an employee in this scenario have been updated to better describe the changes needed to correct the problem.</span></span>

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a><span data-ttu-id="df872-120">Fonctionnalités de pièces jointes dans l'adhésion aux avantages en libre service des employés</span><span class="sxs-lookup"><span data-stu-id="df872-120">Attachments capabilities in Employee self service benefits enrollment</span></span>
 
<span data-ttu-id="df872-121">Vous pouvez maintenant ajouter des pièces jointes pendant le processus d'adhésion aux avantages pour chaque plan auquel le collaborateur souscrit.</span><span class="sxs-lookup"><span data-stu-id="df872-121">Now you can add attachments during the benefits enrollment process for each plan that the employee's enrolling in.</span></span> <span data-ttu-id="df872-122">Vous pouvez ensuite afficher les pièces jointes dans le formulaire **Avantages inscrits du collaborateur**.</span><span class="sxs-lookup"><span data-stu-id="df872-122">You can then view the attachments within the **Worker enrolled benefit** form.</span></span>

## <a name="in-preview"></a><span data-ttu-id="df872-123">En mode aperçu</span><span class="sxs-lookup"><span data-stu-id="df872-123">In preview</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="df872-124">Application Human Resources de Teams</span><span class="sxs-lookup"><span data-stu-id="df872-124">Human Resources application in Teams</span></span>

<span data-ttu-id="df872-125">Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="df872-125">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="df872-126">Ils peuvent interagir avec un bot pour créer des demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="df872-126">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="df872-127">Pour plus d'informations, voir [Application Human Resources dans Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="df872-127">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="leave-suspension"></a><span data-ttu-id="df872-128">Suspension des congés</span><span class="sxs-lookup"><span data-stu-id="df872-128">Leave suspension</span></span>

<span data-ttu-id="df872-129">Vous pouvez suspendre les congés et les absences d'un employé dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="df872-129">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="df872-130">La suspension des congés arrête les régularisations de congés pour les types de congé sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="df872-130">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="df872-131">Si la suspension survient après le traitement d'une régularisation, la suspension du congé crée un ajustement au prorata du solde des congés de l'employé.</span><span class="sxs-lookup"><span data-stu-id="df872-131">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="df872-132">Pour plus d'informations, voir la rubrique [Suspension des congés](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="df872-132">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="df872-133">Mettre à jour l'expérience utilisateur pour indiquer que la comptabilité d'exercice est suspendue (429550)</span><span class="sxs-lookup"><span data-stu-id="df872-133">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="df872-134">L'expérience utilisateur indique désormais que la comptabilité d'exercice a été suspendue pour un plan.</span><span class="sxs-lookup"><span data-stu-id="df872-134">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="df872-135">Prochainement</span><span class="sxs-lookup"><span data-stu-id="df872-135">Coming soon</span></span>

## <a name="database-logging-in-preview-in-june"></a><span data-ttu-id="df872-136">Journalisation de la base de données (en préversion en juin)</span><span class="sxs-lookup"><span data-stu-id="df872-136">Database logging (in preview in June)</span></span>

<span data-ttu-id="df872-137">La fonctionnalité de journalisation de la base de données vous permet de déterminer quelles tables et quels champs doivent être surveillés.</span><span class="sxs-lookup"><span data-stu-id="df872-137">The database logging feature allows you to determine which table and fields should be monitored.</span></span> <span data-ttu-id="df872-138">Elle vous permet également de déterminer les événements qui doivent déclencher le suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="df872-138">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="df872-139">Des capacités de recherche sont disponibles pour observer ces changements au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="df872-139">Inquiry capabilities are available to see these changes over time.</span></span>

## <a name="buy-and-sell-leave-in-preview-june-1"></a><span data-ttu-id="df872-140">Achat et vente de congés (en préversion le 1er juin)</span><span class="sxs-lookup"><span data-stu-id="df872-140">Buy and sell leave (in preview June 1)</span></span>

<span data-ttu-id="df872-141">Certaines organisations offrent un avantage qui permet aux employés d'acheter ou de vendre des congés.</span><span class="sxs-lookup"><span data-stu-id="df872-141">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="df872-142">Ce processus est souvent géré manuellement.</span><span class="sxs-lookup"><span data-stu-id="df872-142">This process is often managed manually.</span></span> <span data-ttu-id="df872-143">Cette fonctionnalité offre un moyen plus automatisé de gérer les politiques et les demandes au service des ressources humaines. Elle aide également à éliminer les erreurs tout en rationalisant le processus de gestion des congés.</span><span class="sxs-lookup"><span data-stu-id="df872-143">This feature provides a more automated way to manage policies and requests for the HR department, and it helps eliminate mistakes while streamlining the leave management process.</span></span> <span data-ttu-id="df872-144">Pour plus d'informations, voir :</span><span class="sxs-lookup"><span data-stu-id="df872-144">For more information, see:</span></span>

- [<span data-ttu-id="df872-145">Gérer les stratégies d'achat et de vente de congés</span><span class="sxs-lookup"><span data-stu-id="df872-145">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="df872-146">Achat et vente de congés</span><span class="sxs-lookup"><span data-stu-id="df872-146">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="df872-147">Entités DMF (Data Management Framework) pour la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="df872-147">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="df872-148">Les entités de gestion des avantages publient.</span><span class="sxs-lookup"><span data-stu-id="df872-148">Benefits management entities are releasing.</span></span> <span data-ttu-id="df872-149">Les entités DMF permettent d'importer et d'exporter des données pour configurer facilement la gestion des avantages.</span><span class="sxs-lookup"><span data-stu-id="df872-149">DMF entities allow importing and exporting data to easily configure benefits management.</span></span> <span data-ttu-id="df872-150">Un modèle de gestion des avantages sera également disponible pour déplacer les données.</span><span class="sxs-lookup"><span data-stu-id="df872-150">A Benefits management template will also be available to move data.</span></span> <span data-ttu-id="df872-151">Le modèle exporte et importe les données de manière séquentielle pour respecter les dépendances des données.</span><span class="sxs-lookup"><span data-stu-id="df872-151">The template exports and imports the data in a sequential manner to respect data dependencies.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a><span data-ttu-id="df872-152">Ajouter un code motif aux suspensions de cumul (1er juin)</span><span class="sxs-lookup"><span data-stu-id="df872-152">Add reason code to accrual suspensions (June 1)</span></span>

<span data-ttu-id="df872-153">Des codes de motif ont été ajoutés à la suspension de la comptabilité d'exercice.</span><span class="sxs-lookup"><span data-stu-id="df872-153">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules-june-1"></a><span data-ttu-id="df872-154">Règles de report (1er juin)</span><span class="sxs-lookup"><span data-stu-id="df872-154">Carry forward rules (June 1)</span></span>

<span data-ttu-id="df872-155">Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés.</span><span class="sxs-lookup"><span data-stu-id="df872-155">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="df872-156">Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours.</span><span class="sxs-lookup"><span data-stu-id="df872-156">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="df872-157">Pour plus d'informations, voir [Configurer les types de congé et d'absence](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="df872-157">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a><span data-ttu-id="df872-158">Suspendre l'accumulation de congés pour certains types de congés (1er juin)</span><span class="sxs-lookup"><span data-stu-id="df872-158">Suspend leave accrual for specified leave types (June 1)</span></span>

<span data-ttu-id="df872-159">Dans cette version, les RH peuvent créer une règle pour suspendre les cumuls de congés pour les employés dont les demandes de congés ont été saisies pour des congés non payés.</span><span class="sxs-lookup"><span data-stu-id="df872-159">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="df872-160">Le congé sans solde peut être un type, mais ce n'est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="df872-160">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="df872-161">Vous pouvez suspendre tout congé basé sur un autre type de congé.</span><span class="sxs-lookup"><span data-stu-id="df872-161">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a><span data-ttu-id="df872-162">Entité DMF disponible pour les suspensions de régularisation (1er juin)</span><span class="sxs-lookup"><span data-stu-id="df872-162">DMF entity available for accrual suspensions (June 1)</span></span>

<span data-ttu-id="df872-163">Une entité DMF est désormais disponible pour les suspensions de régularisation.</span><span class="sxs-lookup"><span data-stu-id="df872-163">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="see-also"></a><span data-ttu-id="df872-164">Voir également :</span><span class="sxs-lookup"><span data-stu-id="df872-164">See also</span></span>

[<span data-ttu-id="df872-165">Nouveautés ou modifications dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="df872-165">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="df872-166">Présentation de Dynamics 365 Human Resources 2019 vague de publication 2</span><span class="sxs-lookup"><span data-stu-id="df872-166">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="df872-167">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="df872-167">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="df872-168">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="df872-168">Manage features</span></span>](hr-admin-manage-features.md)