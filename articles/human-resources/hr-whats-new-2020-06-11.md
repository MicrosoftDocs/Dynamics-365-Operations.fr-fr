---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (11 juin 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 06/16/2020
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
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8ec15c33cdb1abc32c28fd78822b06188dd0feac
ms.sourcegitcommit: 81296c49be9953aa01e15527c34d0ef13b4622a9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2020
ms.locfileid: "3614284"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a><span data-ttu-id="6108c-103">Nouveautés ou modifications dans Dynamics 365 Human Resources (11 juin 2020)</span><span class="sxs-lookup"><span data-stu-id="6108c-103">What's new or changed in Dynamics 365 Human Resources (June 11, 2020)</span></span>

<span data-ttu-id="6108c-104">Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6108c-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="6108c-105">Les modifications s’appliquent au numéro de version 8.1.3316.</span><span class="sxs-lookup"><span data-stu-id="6108c-105">Changes apply to build number 8.1.3316.</span></span> <span data-ttu-id="6108c-106">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.</span><span class="sxs-lookup"><span data-stu-id="6108c-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a><span data-ttu-id="6108c-107">Le formulaire simplifié des employés provoque parfois l’arrêt des boutons de fermeture du formulaire enfant (X) (442369)</span><span class="sxs-lookup"><span data-stu-id="6108c-107">Streamlined employee form sometimes causes child form close (X) buttons to stop working (442369)</span></span>

<span data-ttu-id="6108c-108">Lorsque le nouveau formulaire **Collaborateur** était activé, le bouton de fermeture (**X**) ne fonctionnait parfois pas sur les formulaires enfants.</span><span class="sxs-lookup"><span data-stu-id="6108c-108">When the new **Worker** form was enabled, the close (**X**) button occasionally didn't work on child forms.</span></span> <span data-ttu-id="6108c-109">Ce problème était intermittent.</span><span class="sxs-lookup"><span data-stu-id="6108c-109">This problem was intermittent.</span></span> <span data-ttu-id="6108c-110">Vous pouvez fermer le formulaire après l’avoir quitté et y revenir.</span><span class="sxs-lookup"><span data-stu-id="6108c-110">You could close the form after leaving and coming back to it.</span></span> <span data-ttu-id="6108c-111">Par exemple, vous pouvez sélectionner un élément de menu sur la gauche et revenir au formulaire **Collaborateur**, puis le fermer.</span><span class="sxs-lookup"><span data-stu-id="6108c-111">For example, you could select a menu item on the left, and navigate back to the **Worker** form, and then close it.</span></span> <span data-ttu-id="6108c-112">La version de cette semaine résout ce problème.</span><span class="sxs-lookup"><span data-stu-id="6108c-112">This week's release fixes this problem.</span></span> 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a><span data-ttu-id="6108c-113">L’entité Personne de contact personnelle du collaborateur n’exporte pas les contacts personnels avec un type de relation parent</span><span class="sxs-lookup"><span data-stu-id="6108c-113">The Worker personal contact person entity doesn't export personal contacts with a parent relationship type</span></span>

<span data-ttu-id="6108c-114">Avec cette version, l’entité **Personne de contact personnelle du collaborateur** exporte tous les types de relations.</span><span class="sxs-lookup"><span data-stu-id="6108c-114">With this release, the **Worker personal contact person** entity exports all relationship types.</span></span>

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a><span data-ttu-id="6108c-115">Par défaut, l’entité HcmPositionWorkerAssignmentV2Entity devrait faire partie du package d’intégration de paie Ceridian (448506)</span><span class="sxs-lookup"><span data-stu-id="6108c-115">The HcmPositionWorkerAssignmentV2Entity should be part of the Ceridian payroll integration package by default (448506)</span></span>

<span data-ttu-id="6108c-116">Avec ce changement, l’entité **HcmPositionWorkerAssignmentV2Entity** est incluse dans le package d’intégration de la paie Ceridian.</span><span class="sxs-lookup"><span data-stu-id="6108c-116">With this change, the **HcmPositionWorkerAssignmentV2Entity** is included in the Ceridian payroll integration package.</span></span>

## <a name="in-preview"></a><span data-ttu-id="6108c-117">En mode aperçu</span><span class="sxs-lookup"><span data-stu-id="6108c-117">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="6108c-118">Connexion à la base de données</span><span class="sxs-lookup"><span data-stu-id="6108c-118">Database logging</span></span>

<span data-ttu-id="6108c-119">La fonctionnalité de journalisation de la base de données vous permet de déterminer quelles tables et quels champs doivent être surveillés.</span><span class="sxs-lookup"><span data-stu-id="6108c-119">The database logging feature allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="6108c-120">Elle vous permet également de déterminer les événements qui doivent déclencher le suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="6108c-120">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="6108c-121">Vous utilisez les capacités de journalisation de la base de données pour voir ces changements au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="6108c-121">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="6108c-122">Pour plus d’informations, voir [Configurer et gérer la journalisation de la base de données](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="6108c-122">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="6108c-123">Application Human Resources de Teams</span><span class="sxs-lookup"><span data-stu-id="6108c-123">Human Resources application in Teams</span></span>

<span data-ttu-id="6108c-124">Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6108c-124">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="6108c-125">Ils peuvent interagir avec un bot pour créer des demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="6108c-125">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="6108c-126">Pour plus d’informations, voir [Application Human Resources dans Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="6108c-126">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="6108c-127">Entités DMF (Data Management Framework) pour la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="6108c-127">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="6108c-128">Les entités de gestion des avantages publient.</span><span class="sxs-lookup"><span data-stu-id="6108c-128">Benefits management entities are releasing.</span></span> <span data-ttu-id="6108c-129">Les entités DMF permettent d’importer et d’exporter des données pour configurer facilement la gestion des avantages.</span><span class="sxs-lookup"><span data-stu-id="6108c-129">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="6108c-130">Un modèle de gestion des avantages sera disponible pour déplacer les données.</span><span class="sxs-lookup"><span data-stu-id="6108c-130">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="6108c-131">Le modèle exporte et importe les données de manière séquentielle pour respecter les dépendances des données.</span><span class="sxs-lookup"><span data-stu-id="6108c-131">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="6108c-132">Achat et vente de congés</span><span class="sxs-lookup"><span data-stu-id="6108c-132">Buy and sell leave</span></span> 

<span data-ttu-id="6108c-133">Certaines organisations offrent un avantage qui permet aux employés d’acheter ou de vendre des congés.</span><span class="sxs-lookup"><span data-stu-id="6108c-133">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="6108c-134">Ce processus est souvent géré manuellement.</span><span class="sxs-lookup"><span data-stu-id="6108c-134">This process is often managed manually.</span></span> <span data-ttu-id="6108c-135">Cette fonctionnalité automatise la gestion des stratégies et des demandes pour le service RH.</span><span class="sxs-lookup"><span data-stu-id="6108c-135">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="6108c-136">Il rationalise le processus de gestion des congés et aide à éliminer les erreurs.</span><span class="sxs-lookup"><span data-stu-id="6108c-136">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="6108c-137">Pour plus d’informations, voir :</span><span class="sxs-lookup"><span data-stu-id="6108c-137">For more information, see:</span></span>

- [<span data-ttu-id="6108c-138">Gérer les stratégies d’achat et de vente de congés</span><span class="sxs-lookup"><span data-stu-id="6108c-138">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="6108c-139">Achat et vente de congés</span><span class="sxs-lookup"><span data-stu-id="6108c-139">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="6108c-140">Provisions de congés pour une seule entreprise ou un seul plan</span><span class="sxs-lookup"><span data-stu-id="6108c-140">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="6108c-141">Les clients peuvent traiter les charges à payer pour une seule entreprise ou un seul plan de congé et d’absence.</span><span class="sxs-lookup"><span data-stu-id="6108c-141">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="6108c-142">Cette capacité permet de clarifier le processus d’accumulation pour les clients avec différentes années de congé ou politiques d’accumulation de congé.</span><span class="sxs-lookup"><span data-stu-id="6108c-142">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="6108c-143">Pour plus d’informations, voir [Accumulation de congés par entreprise ou par plan de congés](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span><span class="sxs-lookup"><span data-stu-id="6108c-143">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="6108c-144">Ajouter des pièces jointes aux demandes de congé</span><span class="sxs-lookup"><span data-stu-id="6108c-144">Add attachments to time off requests</span></span>

<span data-ttu-id="6108c-145">La possibilité d’ajouter des pièces jointes aux demandes de congé approuvées est essentielle dans l’environnement COVID-19 actuel.</span><span class="sxs-lookup"><span data-stu-id="6108c-145">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="6108c-146">Les employés peuvent désormais ajouter ces pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="6108c-146">Employees can now add these attachments.</span></span> <span data-ttu-id="6108c-147">Ils ont également plus d’informations sur la façon dont les mises à jour sont effectuées pour les demandes de congés.</span><span class="sxs-lookup"><span data-stu-id="6108c-147">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="6108c-148">Pour plus d’informations, voir [Ajouter une pièce jointe à une demande existante](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="6108c-148">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="6108c-149">Ajouter un code de motif aux suspensions de cumul</span><span class="sxs-lookup"><span data-stu-id="6108c-149">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="6108c-150">Des codes de motif ont été ajoutés à la suspension de la comptabilité d’exercice.</span><span class="sxs-lookup"><span data-stu-id="6108c-150">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="6108c-151">Règles de report</span><span class="sxs-lookup"><span data-stu-id="6108c-151">Carry forward rules</span></span> 

<span data-ttu-id="6108c-152">Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés.</span><span class="sxs-lookup"><span data-stu-id="6108c-152">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="6108c-153">Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours.</span><span class="sxs-lookup"><span data-stu-id="6108c-153">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="6108c-154">Pour plus d’informations, voir [Configurer les types de congé et d’absence](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="6108c-154">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="6108c-155">Suspendre l’accumulation de congés pour certains types de congés</span><span class="sxs-lookup"><span data-stu-id="6108c-155">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="6108c-156">Vous pouvez créer une règle pour suspendre les cumuls de congés pour les employés dont les demandes de congés ont été saisies pour des congés non payés.</span><span class="sxs-lookup"><span data-stu-id="6108c-156">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="6108c-157">Le congé sans solde peut être un type, mais ce n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="6108c-157">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="6108c-158">Vous pouvez suspendre tout congé basé sur un autre type de congé.</span><span class="sxs-lookup"><span data-stu-id="6108c-158">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="6108c-159">Entité DMF disponible pour les suspensions de régularisation</span><span class="sxs-lookup"><span data-stu-id="6108c-159">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="6108c-160">Une entité DMF est désormais disponible pour les suspensions de régularisation.</span><span class="sxs-lookup"><span data-stu-id="6108c-160">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="6108c-161">Prochainement</span><span class="sxs-lookup"><span data-stu-id="6108c-161">Coming soon</span></span>

## <a name="new-platform-capabilities"></a><span data-ttu-id="6108c-162">Nouvelles capacités de plateforme</span><span class="sxs-lookup"><span data-stu-id="6108c-162">New platform capabilities</span></span> 

<span data-ttu-id="6108c-163">Vous pourrez rendre les champs obligatoires en utilisant la personnalisation.</span><span class="sxs-lookup"><span data-stu-id="6108c-163">You'll be able to make fields mandatory by using personalization.</span></span> <span data-ttu-id="6108c-164">Cette fonctionnalité vous obligera à activer les **Vues enregistrées**.</span><span class="sxs-lookup"><span data-stu-id="6108c-164">This feature will require you to enable **Saved views**.</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="6108c-165">Configurer le nom du libre service employé</span><span class="sxs-lookup"><span data-stu-id="6108c-165">Configure the name of Employee self-service</span></span>

<span data-ttu-id="6108c-166">Une nouvelle option sera disponible dans les paramètres des Ressources humaines pour mettre à jour le nom de l’espace de travail Libre-service Employé en Libre-service.</span><span class="sxs-lookup"><span data-stu-id="6108c-166">A new option will be available in Human Resources parameters to update the name of the Employee self service workspace to Self service.</span></span> 

## <a name="see-also"></a><span data-ttu-id="6108c-167">Voir également :</span><span class="sxs-lookup"><span data-stu-id="6108c-167">See also</span></span>

[<span data-ttu-id="6108c-168">Nouveautés ou modifications dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="6108c-168">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="6108c-169">Présentation de Dynamics 365 Human Resources 2019 vague de publication 2</span><span class="sxs-lookup"><span data-stu-id="6108c-169">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="6108c-170">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="6108c-170">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="6108c-171">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="6108c-171">Manage features</span></span>](hr-admin-manage-features.md)