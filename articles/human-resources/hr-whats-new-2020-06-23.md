---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (25 juin 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 6/25/2020
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
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8d83268292ac65d62cbe8fa9a4c146bf4af36b50
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555025"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a><span data-ttu-id="2b143-103">Nouveautés ou modifications dans Dynamics 365 Human Resources (23 juin 2020)</span><span class="sxs-lookup"><span data-stu-id="2b143-103">What's new or changed in Dynamics 365 Human Resources (June 23, 2020)</span></span>

<span data-ttu-id="2b143-104">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2b143-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="2b143-105">Les modifications s'appliquent au numéro de version 8.1.3347.</span><span class="sxs-lookup"><span data-stu-id="2b143-105">Changes apply to build number 8.1.3347.</span></span> <span data-ttu-id="2b143-106">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.</span><span class="sxs-lookup"><span data-stu-id="2b143-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a><span data-ttu-id="2b143-107">Lorsqu'une inscription a expiré pour un employé dont le contrat est terminé, le type de départ, le solde et le montant sont tous effacés dans le formulaire Inscription au départ (444867)</span><span class="sxs-lookup"><span data-stu-id="2b143-107">When an enrollment is expired for a terminated employee, the leave type, balance, and amount are all cleared in the Leave enrollment form (444867)</span></span>

<span data-ttu-id="2b143-108">Les valeurs des champs **Type de départ**, **Solde** et **Montant** sont maintenant conservées au lieu d'être effacées lors de cette sélection.</span><span class="sxs-lookup"><span data-stu-id="2b143-108">Values in the **Leave type**, **Balance**, and **Amount** are now maintained instead of cleared upon making this selection.</span></span>

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a><span data-ttu-id="2b143-109">Solde prévisionnel incorrect lorsque la nouvelle fonctionnalité (Provisions de congés pour une seule entreprise ou un seul plan) est activée (456553)</span><span class="sxs-lookup"><span data-stu-id="2b143-109">Incorrect forecasted balance when new feature (Leave accrual for a single company or a single plan) is enabled (456553)</span></span>

<span data-ttu-id="2b143-110">Le solde prévisionnel correct s'affiche maintenant lorsque les provisions de congés pour une seule entreprise ou un seul plan ont été activées.</span><span class="sxs-lookup"><span data-stu-id="2b143-110">The correct forecasted balance now displays when the leave accrual for a single company or single plan has been enabled.</span></span>

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a><span data-ttu-id="2b143-111">Les entités avec des relations génèrent des propriétés de navigation en double (456486)</span><span class="sxs-lookup"><span data-stu-id="2b143-111">Entities with relations that result in duplicate navigation properties (456486)</span></span>

<span data-ttu-id="2b143-112">Cette version corrige un problème avec les propriétés de navigation (relation) de plusieurs entités.</span><span class="sxs-lookup"><span data-stu-id="2b143-112">This release corrects an issue with the navigation properties (relation) of multiple entities.</span></span> <span data-ttu-id="2b143-113">Des relations en double sont détectées.</span><span class="sxs-lookup"><span data-stu-id="2b143-113">Duplicate relations are detected.</span></span> <span data-ttu-id="2b143-114">Ces scénarios ont tous été corrigés.</span><span class="sxs-lookup"><span data-stu-id="2b143-114">These scenarios have all been corrected.</span></span>
 
## <a name="cross-company-comments-on-performance-review-455536"></a><span data-ttu-id="2b143-115">Commentaires intersociétés sur l'évaluation des performances (455536)</span><span class="sxs-lookup"><span data-stu-id="2b143-115">Cross-company comments on Performance review (455536)</span></span>

<span data-ttu-id="2b143-116">Les commentaires intersociétés sont désormais visibles sur les évaluations des performances avec ce correctif.</span><span class="sxs-lookup"><span data-stu-id="2b143-116">Cross-company comments are now visible on performance reviews with this fix.</span></span> <span data-ttu-id="2b143-117">Cette modification corrige la vue des commentaires des réviseurs qui ont été entrés dans différentes sociétés pour la même évaluation des performances.</span><span class="sxs-lookup"><span data-stu-id="2b143-117">This change corrects the view of reviewer comments that were entered in different companies for the same performance review.</span></span>
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a><span data-ttu-id="2b143-118">Incohérence dans l'affichage des données de gestion des rémunérations (432562)</span><span class="sxs-lookup"><span data-stu-id="2b143-118">Inconsistency in showing compensation management data (432562)</span></span>

<span data-ttu-id="2b143-119">Une vue cohérente des données de rémunération est désormais gérée dans Libre-service pour responsables.</span><span class="sxs-lookup"><span data-stu-id="2b143-119">A consistent view of compensation data is now maintained in Manager self service.</span></span> <span data-ttu-id="2b143-120">Selon la façon dont vous accédez aux **Détails de rémunération** d'un employé, les données de rémunération s'affichent maintenant de manière cohérente pour les responsables.</span><span class="sxs-lookup"><span data-stu-id="2b143-120">Depending on how you navigate to a worker's **Compensation details**, compensation data now consistently displays to managers.</span></span>
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a><span data-ttu-id="2b143-121">La date d'effet du régime de rémunération fixe affiche par défaut la date du jour (411994)</span><span class="sxs-lookup"><span data-stu-id="2b143-121">Fixed compensation plan's effective date defaults to today's date (411994)</span></span>

<span data-ttu-id="2b143-122">La date de début de rémunération est maintenant basée sur la date de début du poste attribué à l'employé.</span><span class="sxs-lookup"><span data-stu-id="2b143-122">The compensation start date is now based on the start date of the position being assigned to the employee.</span></span>

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a><span data-ttu-id="2b143-123">L'option Activer la définition d'une demi-journée dans le formulaire de congé et d'absence est désactivée à l'ouverture du formulaire (452607)</span><span class="sxs-lookup"><span data-stu-id="2b143-123">Leave and absence form Enable half day definition is disabled when form opens (452607)</span></span>

<span data-ttu-id="2b143-124">Avec cette modification, l'option **Activer la définition d'une demi-journée** sera activée jusqu'à ce que de nouvelles transactions de congé s'affichent.</span><span class="sxs-lookup"><span data-stu-id="2b143-124">With this change, the **Enable half day definition** will be enabled until new leave transactions exist.</span></span> 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a><span data-ttu-id="2b143-125">Impossible de publier sur HcmDiscussionEntity via Excel ; erreur de champ TotalRatingScore (453899)</span><span class="sxs-lookup"><span data-stu-id="2b143-125">Unable to publish to HcmDiscussionEntity via Excel; TotalRatingScore field error (453899)</span></span>

<span data-ttu-id="2b143-126">Vous pouvez maintenant mettre à jour le champ **TotalRatingScore** en utilisant **HCMDiscussionEntity** dans le concepteur de classeurs Excel.</span><span class="sxs-lookup"><span data-stu-id="2b143-126">You can now update the **TotalRatingScore** field using **HCMDiscussionEntity** in the Excel workbook designer.</span></span>

## <a name="in-preview"></a><span data-ttu-id="2b143-127">En mode aperçu</span><span class="sxs-lookup"><span data-stu-id="2b143-127">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="2b143-128">Connexion à la base de données</span><span class="sxs-lookup"><span data-stu-id="2b143-128">Database logging</span></span>

<span data-ttu-id="2b143-129">La journalisation de la base de données vous permet de déterminer quelles tables et quels champs doivent être surveillés.</span><span class="sxs-lookup"><span data-stu-id="2b143-129">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="2b143-130">Elle vous permet également de déterminer les événements qui doivent déclencher le suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="2b143-130">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="2b143-131">Vous utilisez les capacités de journalisation de la base de données pour voir ces changements au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="2b143-131">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="2b143-132">Pour plus d'informations, voir [Configurer et gérer la journalisation de la base de données](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="2b143-132">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="2b143-133">Champs obligatoires</span><span class="sxs-lookup"><span data-stu-id="2b143-133">Mandatory fields</span></span> 

<span data-ttu-id="2b143-134">Vous pouvez maintenant rendre les champs obligatoires en utilisant les fonctionnalités de personnalisation de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2b143-134">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="2b143-135">Cette fonctionnalité nécessite des **Vues enregistrées**.</span><span class="sxs-lookup"><span data-stu-id="2b143-135">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="2b143-136">Application Human Resources de Teams</span><span class="sxs-lookup"><span data-stu-id="2b143-136">Human Resources application in Teams</span></span>

<span data-ttu-id="2b143-137">Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2b143-137">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="2b143-138">Ils peuvent interagir avec un bot pour créer des demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="2b143-138">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="2b143-139">Pour plus d'informations, voir [Application Human Resources dans Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="2b143-139">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="2b143-140">Entités DMF (Data Management Framework) pour la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="2b143-140">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="2b143-141">Les entités de gestion des avantages publient.</span><span class="sxs-lookup"><span data-stu-id="2b143-141">Benefits management entities are releasing.</span></span> <span data-ttu-id="2b143-142">Les entités DMF permettent d'importer et d'exporter des données pour configurer facilement la gestion des avantages.</span><span class="sxs-lookup"><span data-stu-id="2b143-142">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="2b143-143">Un modèle de gestion des avantages sera disponible pour déplacer les données.</span><span class="sxs-lookup"><span data-stu-id="2b143-143">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="2b143-144">Le modèle exporte et importe les données de manière séquentielle pour respecter les dépendances des données.</span><span class="sxs-lookup"><span data-stu-id="2b143-144">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="2b143-145">Achat et vente de congés</span><span class="sxs-lookup"><span data-stu-id="2b143-145">Buy and sell leave</span></span> 

<span data-ttu-id="2b143-146">Certaines organisations offrent un avantage qui permet aux employés d'acheter ou de vendre des congés.</span><span class="sxs-lookup"><span data-stu-id="2b143-146">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="2b143-147">Ce processus est souvent géré manuellement.</span><span class="sxs-lookup"><span data-stu-id="2b143-147">This process is often managed manually.</span></span> <span data-ttu-id="2b143-148">Cette fonctionnalité automatise la gestion des stratégies et des demandes pour le service RH.</span><span class="sxs-lookup"><span data-stu-id="2b143-148">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="2b143-149">Il rationalise le processus de gestion des congés et aide à éliminer les erreurs.</span><span class="sxs-lookup"><span data-stu-id="2b143-149">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="2b143-150">Pour plus d'informations, voir :</span><span class="sxs-lookup"><span data-stu-id="2b143-150">For more information, see:</span></span>

- [<span data-ttu-id="2b143-151">Gérer les stratégies d'achat et de vente de congés</span><span class="sxs-lookup"><span data-stu-id="2b143-151">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="2b143-152">Achat et vente de congés</span><span class="sxs-lookup"><span data-stu-id="2b143-152">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="2b143-153">Provisions de congés pour une seule entreprise ou un seul plan</span><span class="sxs-lookup"><span data-stu-id="2b143-153">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="2b143-154">Les clients peuvent traiter les charges à payer pour une seule entreprise ou un seul plan de congé et d'absence.</span><span class="sxs-lookup"><span data-stu-id="2b143-154">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="2b143-155">Cette capacité permet de clarifier le processus d'accumulation pour les clients avec différentes années de congé ou politiques d'accumulation de congé.</span><span class="sxs-lookup"><span data-stu-id="2b143-155">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="2b143-156">Pour plus d'informations, voir [Accumulation de congés par entreprise ou par plan de congés](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span><span class="sxs-lookup"><span data-stu-id="2b143-156">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="2b143-157">Ajouter des pièces jointes aux demandes de congé</span><span class="sxs-lookup"><span data-stu-id="2b143-157">Add attachments to time off requests</span></span>

<span data-ttu-id="2b143-158">La possibilité d'ajouter des pièces jointes aux demandes de congé approuvées est essentielle dans l'environnement COVID-19 actuel.</span><span class="sxs-lookup"><span data-stu-id="2b143-158">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="2b143-159">Les employés peuvent désormais ajouter ces pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="2b143-159">Employees can now add these attachments.</span></span> <span data-ttu-id="2b143-160">Ils ont également plus d'informations sur la façon dont les mises à jour sont effectuées pour les demandes de congés.</span><span class="sxs-lookup"><span data-stu-id="2b143-160">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="2b143-161">Pour plus d'informations, voir [Ajouter une pièce jointe à une demande existante](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="2b143-161">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="2b143-162">Ajouter un code de motif aux suspensions de cumul</span><span class="sxs-lookup"><span data-stu-id="2b143-162">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="2b143-163">Des codes de motif ont été ajoutés à la suspension de la comptabilité d'exercice.</span><span class="sxs-lookup"><span data-stu-id="2b143-163">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="2b143-164">Règles de report</span><span class="sxs-lookup"><span data-stu-id="2b143-164">Carry forward rules</span></span> 

<span data-ttu-id="2b143-165">Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés.</span><span class="sxs-lookup"><span data-stu-id="2b143-165">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="2b143-166">Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours.</span><span class="sxs-lookup"><span data-stu-id="2b143-166">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="2b143-167">Pour plus d'informations, voir [Configurer les types de congé et d'absence](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="2b143-167">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="2b143-168">Suspendre l'accumulation de congés pour certains types de congés</span><span class="sxs-lookup"><span data-stu-id="2b143-168">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="2b143-169">Vous pouvez créer une règle pour suspendre les cumuls de congés pour les employés dont les demandes de congés ont été saisies pour des congés non payés.</span><span class="sxs-lookup"><span data-stu-id="2b143-169">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="2b143-170">Le congé sans solde peut être un type, mais ce n'est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="2b143-170">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="2b143-171">Vous pouvez suspendre tout congé basé sur un autre type de congé.</span><span class="sxs-lookup"><span data-stu-id="2b143-171">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="2b143-172">Entité DMF disponible pour les suspensions de régularisation</span><span class="sxs-lookup"><span data-stu-id="2b143-172">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="2b143-173">Une entité DMF est désormais disponible pour les suspensions de régularisation.</span><span class="sxs-lookup"><span data-stu-id="2b143-173">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="2b143-174">Prochainement</span><span class="sxs-lookup"><span data-stu-id="2b143-174">Coming soon</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="2b143-175">Configurer le nom du libre service employé</span><span class="sxs-lookup"><span data-stu-id="2b143-175">Configure the name of Employee self-service</span></span>

<span data-ttu-id="2b143-176">Une nouvelle option sera disponible dans les **paramètres des Ressources humaines** pour mettre à jour le nom de l'espace de travail Libre-service Employé en Libre-service.</span><span class="sxs-lookup"><span data-stu-id="2b143-176">A new option will be available in **Human Resources parameters** to update the name of the Employee self service workspace to Self service.</span></span>

## <a name="checklist-entities-included-in-common-data-service"></a><span data-ttu-id="2b143-177">Entités de liste de contrôle incluses dans Common Data Service</span><span class="sxs-lookup"><span data-stu-id="2b143-177">Checklist entities included in Common Data Service</span></span>

<span data-ttu-id="2b143-178">Les entités de liste de contrôle pour les processus d'intégration, de départ, de transfert et d'entreprise seront bientôt disponibles dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2b143-178">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon within Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b143-179">Voir également :</span><span class="sxs-lookup"><span data-stu-id="2b143-179">See also</span></span>

[<span data-ttu-id="2b143-180">Nouveautés ou modifications dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="2b143-180">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="2b143-181">Présentation de Dynamics 365 Human Resources 2019 vague de publication 2</span><span class="sxs-lookup"><span data-stu-id="2b143-181">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="2b143-182">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="2b143-182">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="2b143-183">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="2b143-183">Manage features</span></span>](hr-admin-manage-features.md)