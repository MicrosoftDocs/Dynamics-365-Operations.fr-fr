---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (08 juillet 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 8 juillet 2020.
author: andreabichsel
manager: tfehr
ms.date: 07/08/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9715f332088b7b5340f4252af5f789d226d90ff2
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463596"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a><span data-ttu-id="09b33-103">Nouveautés ou modifications dans Dynamics 365 Human Resources (8 juillet 2020)</span><span class="sxs-lookup"><span data-stu-id="09b33-103">What's new or changed in Dynamics 365 Human Resources (July 8, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="09b33-104">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="09b33-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="09b33-105">Les modifications s’appliquent au numéro de version 8.1.3382.</span><span class="sxs-lookup"><span data-stu-id="09b33-105">Changes apply to build number 8.1.3382.</span></span> <span data-ttu-id="09b33-106">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.</span><span class="sxs-lookup"><span data-stu-id="09b33-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="database-logging"></a><span data-ttu-id="09b33-107">Connexion à la base de données</span><span class="sxs-lookup"><span data-stu-id="09b33-107">Database logging</span></span>

<span data-ttu-id="09b33-108">La journalisation de la base de données vous permet de déterminer quelles tables et quels champs doivent être surveillés.</span><span class="sxs-lookup"><span data-stu-id="09b33-108">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="09b33-109">Elle vous permet également de déterminer les événements qui doivent déclencher le suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="09b33-109">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="09b33-110">Vous utilisez les capacités de journalisation de la base de données pour voir ces changements au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="09b33-110">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="09b33-111">Pour plus d’informations, voir [Configurer et gérer la journalisation de la base de données](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="09b33-111">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="09b33-112">Configurer le nom du libre service employé</span><span class="sxs-lookup"><span data-stu-id="09b33-112">Configure the name of Employee self service</span></span>

<span data-ttu-id="09b33-113">Dans les **Paramètres Human Resources**, vous pouvez maintenant changer le nom de l’espace de travail **Libre service des employés** en **Libre service**.</span><span class="sxs-lookup"><span data-stu-id="09b33-113">In **Human Resources parameters**, you can now change the name of the **Employee self service** workspace to **Self service**.</span></span> <span data-ttu-id="09b33-114">Pour plus d’informations, voir [Modifier le nom de l’espace de travail en libre service des employés](hr-employee-self-service-workspace-name.md).</span><span class="sxs-lookup"><span data-stu-id="09b33-114">For more information, see [Change Employee self service workspace name](hr-employee-self-service-workspace-name.md)</span></span>

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a><span data-ttu-id="09b33-115">Accès à l’inscription à la gestion des avantages ouvert en dehors de la période</span><span class="sxs-lookup"><span data-stu-id="09b33-115">Benefits management open enrollment access outside of period</span></span>

<span data-ttu-id="09b33-116">Cette version corrige un bogue où les employés pouvaient accéder à l’inscription ouverte aux avantages en dehors de la période d’inscription ou sans événement dans leur vie.</span><span class="sxs-lookup"><span data-stu-id="09b33-116">This release fixes a bug where employees could access benefits open enrollment outside of the enrollment period or without a life event.</span></span> <span data-ttu-id="09b33-117">Par conséquent, si vous devez faire une démonstration de l’inscription ouverte dans le libre service des employés, vous devez ajuster les dates de l’inscription ouverte à la date du jour (ou à une date antérieure) pour la rendre accessible.</span><span class="sxs-lookup"><span data-stu-id="09b33-117">As a result, if you need to demo open enrollment in Employee self service, you must adjust the open enrollment dates to today (or earlier) to make it accessible.</span></span> <span data-ttu-id="09b33-118">Vous pouvez modifier ce paramètre sous **Gestion des avantages > Règles et périodes des options**.</span><span class="sxs-lookup"><span data-stu-id="09b33-118">You can change this setting under **Benefits management > Rules and options periods**.</span></span>

## <a name="email-employee-enrollment-confirmation"></a><span data-ttu-id="09b33-119">Email de confirmation de l’inscription des employés</span><span class="sxs-lookup"><span data-stu-id="09b33-119">Email employee enrollment confirmation</span></span>

<span data-ttu-id="09b33-120">Vous pouvez désormais envoyer des courriels aux employés une fois qu’ils ont terminé leur sélection d’avantages.</span><span class="sxs-lookup"><span data-stu-id="09b33-120">You can now send emails to employees after they complete their benefits selection.</span></span> <span data-ttu-id="09b33-121">Vous pouvez envoyer un message par défaut ou utiliser un modèle d’e-mail de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="09b33-121">You can either send a default message or use an organization email template.</span></span> <span data-ttu-id="09b33-122">Ces paramètres se trouvent sous **Paramètres Human Resources > Gestion des avantages**.</span><span class="sxs-lookup"><span data-stu-id="09b33-122">These settings are under **Human resource parameters > Benefits management**.</span></span>

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a><span data-ttu-id="09b33-123">Le congé annulé apparaît toujours dans le temps de congé à venir sur l’espace de travail Contacts (441358)</span><span class="sxs-lookup"><span data-stu-id="09b33-123">Canceled leave still appears in upcoming time off on People workspace (441358)</span></span>

<span data-ttu-id="09b33-124">Le congé annulé ne s’affiche plus comme un congé à venir sur les cartes de congé dans l’espace de travail **Personnes**.</span><span class="sxs-lookup"><span data-stu-id="09b33-124">Canceled leave no longer displays as upcoming time off on the leave cards in the **People** workspace.</span></span>

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a><span data-ttu-id="09b33-125">Impossible d’utiliser la propriété d’entité Service dans l’entité PositionV2 (456486)</span><span class="sxs-lookup"><span data-stu-id="09b33-125">Unable to use the department entity property in the PositionV2 entity (456486)</span></span>

<span data-ttu-id="09b33-126">Vous pouvez désormais ajouter un service sans créer de relation en double.</span><span class="sxs-lookup"><span data-stu-id="09b33-126">You can now add a department without creating a duplicate relation.</span></span>

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a><span data-ttu-id="09b33-127">PayrollWorkerEnrolledBenefitDetailEntity ne doit utiliser le champ calculé que pour les régimes de retraite (459779)</span><span class="sxs-lookup"><span data-stu-id="09b33-127">PayrollWorkerEnrolledBenefitDetailEntity should only use calculated field for retirement plans (459779)</span></span>

<span data-ttu-id="09b33-128">Lors de l’exportation de l’entité **PayrollWorkerEnrolledBenefitDetailEntity**, l’exportation détermine s’il convient d’utiliser un champ calculé basé sur une table de taux ou utiliser le champ **ContributionAmountCur** de la table de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="09b33-128">When exporting the **PayrollWorkerEnrolledBenefitDetailEntity** entity, the export determines whether it should use a calculated field based on a rate table or use the **ContributionAmountCur** field on the backing table.</span></span> <span data-ttu-id="09b33-129">La logique utilisée par l’entité de données utilise la table des taux dans des situations où l’application ne le fait normalement pas.</span><span class="sxs-lookup"><span data-stu-id="09b33-129">The logic used by the data entity uses the rate table in situations where the application normally doesn't.</span></span> <span data-ttu-id="09b33-130">Cette logique fait que les exportations d’entité renvoient une valeur nulle pour cette colonne, car il n’y a pas de table de taux de calcul et le produit ne permet pas au client d’en spécifier une.</span><span class="sxs-lookup"><span data-stu-id="09b33-130">This logic causes the entity exports to return a zero value for this column, because there's no calculation rate table and the product doesn't allow the customer to specify one.</span></span>
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a><span data-ttu-id="09b33-131">Traductions confuses en langue tchèque dans la Gestion du personnel et le libre service des employés (400276)</span><span class="sxs-lookup"><span data-stu-id="09b33-131">Confusing translations in Czech language in Personnel management and Employee self service (400276)</span></span>

<span data-ttu-id="09b33-132">Cette version corrige les traductions pour **Annuaire de l’entreprise**, **Prochain cours enregistré**, **Emploi**, et **Poste**.</span><span class="sxs-lookup"><span data-stu-id="09b33-132">This release corrects the translations for **Company directory**, **Next registered course**, **Job**, and **Position**.</span></span>
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a><span data-ttu-id="09b33-133">La table WorkCalendarEmployment n’a pas les champs système créés et modifiés activés (460171)</span><span class="sxs-lookup"><span data-stu-id="09b33-133">The WorkCalendarEmployment table doesn't have the created and modified system fields enabled (460171)</span></span>

<span data-ttu-id="09b33-134">Les champs système créés et modifiés sont désormais activés sur la table **WorkCalendarEmployment** dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="09b33-134">Created and modified system fields are now enabled on the **WorkCalendarEmployment** table in Human Resources.</span></span>
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a><span data-ttu-id="09b33-135">Exception de référence Null pour Embaucher et ajouter des détails pour le futur employé (455475)</span><span class="sxs-lookup"><span data-stu-id="09b33-135">Null reference exception for Hire and add details for future employee (455475)</span></span>

<span data-ttu-id="09b33-136">Cette version corrige une erreur (une référence Null) dans l’entrée simplifiée de l’employé lors de l’embauche d’un employé en utilisant l’option **Embaucher et ajouter des détails**.</span><span class="sxs-lookup"><span data-stu-id="09b33-136">This release corrects an error (null reference) in streamlined employee entry when you hire an employee using the option to **Hire and add details**.</span></span>

## <a name="changes-made-in-the-dataverse-worker-entity-dont-reflect-in-human-resources-455652"></a><span data-ttu-id="09b33-137">Les modifications apportées à l’entité Employé de Dataverse ne sont pas répercutées dans Human Resources (455652)</span><span class="sxs-lookup"><span data-stu-id="09b33-137">Changes made in the Dataverse Worker entity don't reflect in Human Resources (455652)</span></span>

<span data-ttu-id="09b33-138">Les modifications apportées aux champs suivants de l’entité **Employé** dans Dataverse apparaissent désormais dans Human Resources :</span><span class="sxs-lookup"><span data-stu-id="09b33-138">Changes made to the following fields in the **Worker** entity in Dataverse will now show up in Human Resources:</span></span>

- <span data-ttu-id="09b33-139">**Travaille à domicile**</span><span class="sxs-lookup"><span data-stu-id="09b33-139">**Works from home**</span></span>
- <span data-ttu-id="09b33-140">**Date d’ancienneté**</span><span class="sxs-lookup"><span data-stu-id="09b33-140">**Seniority date**</span></span>
- <span data-ttu-id="09b33-141">**Date anniversaire**</span><span class="sxs-lookup"><span data-stu-id="09b33-141">**Anniversary date**</span></span>
- <span data-ttu-id="09b33-142">**Date d’embauche d’origine**</span><span class="sxs-lookup"><span data-stu-id="09b33-142">**Original hire date**</span></span>

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a><span data-ttu-id="09b33-143">Le niveau de rémunération correct n’est pas défini par défaut en fonction de l’emploi affecté au poste (394136)</span><span class="sxs-lookup"><span data-stu-id="09b33-143">Correct compensation level doesn't default based on the job assigned to the position (394136)</span></span>

<span data-ttu-id="09b33-144">Avec ce changement, le niveau de compensation correct est par défaut basé sur les enregistrements **Date d’entrée en vigueur** pour le champ **Détails du poste** et **Date de début** pour l’**Affectation du plan de rémunération**.</span><span class="sxs-lookup"><span data-stu-id="09b33-144">With this change, the correct compensation level defaults based on the **Date effective** records for the **Position details** and the **Start date** of the **Compensation plan assignment**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="09b33-145">En mode aperçu</span><span class="sxs-lookup"><span data-stu-id="09b33-145">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="09b33-146">Champs obligatoires</span><span class="sxs-lookup"><span data-stu-id="09b33-146">Mandatory fields</span></span> 

<span data-ttu-id="09b33-147">Vous pouvez maintenant rendre les champs obligatoires en utilisant les fonctionnalités de personnalisation de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="09b33-147">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="09b33-148">Cette fonctionnalité nécessite des **Vues enregistrées**.</span><span class="sxs-lookup"><span data-stu-id="09b33-148">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="09b33-149">Application Human Resources de Teams</span><span class="sxs-lookup"><span data-stu-id="09b33-149">Human Resources application in Teams</span></span>

<span data-ttu-id="09b33-150">Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="09b33-150">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="09b33-151">Ils peuvent interagir avec un bot pour créer des demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="09b33-151">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="09b33-152">Pour plus d’informations, voir [Application Human Resources dans Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="09b33-152">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="09b33-153">Entités DMF (Data Management Framework) pour la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="09b33-153">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="09b33-154">Les entités de gestion des avantages publient.</span><span class="sxs-lookup"><span data-stu-id="09b33-154">Benefits management entities are releasing.</span></span> <span data-ttu-id="09b33-155">Les entités DMF permettent d’importer et d’exporter des données pour configurer facilement la gestion des avantages.</span><span class="sxs-lookup"><span data-stu-id="09b33-155">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="09b33-156">Un modèle de gestion des avantages sera disponible pour déplacer les données.</span><span class="sxs-lookup"><span data-stu-id="09b33-156">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="09b33-157">Le modèle exporte et importe les données de manière séquentielle pour respecter les dépendances des données.</span><span class="sxs-lookup"><span data-stu-id="09b33-157">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="09b33-158">Achat et vente de congés</span><span class="sxs-lookup"><span data-stu-id="09b33-158">Buy and sell leave</span></span> 

<span data-ttu-id="09b33-159">Certaines organisations offrent un avantage qui permet aux employés d’acheter ou de vendre des congés.</span><span class="sxs-lookup"><span data-stu-id="09b33-159">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="09b33-160">Ce processus est souvent géré manuellement.</span><span class="sxs-lookup"><span data-stu-id="09b33-160">This process is often managed manually.</span></span> <span data-ttu-id="09b33-161">Cette fonctionnalité automatise la gestion des stratégies et des demandes pour le service RH.</span><span class="sxs-lookup"><span data-stu-id="09b33-161">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="09b33-162">Il rationalise le processus de gestion des congés et aide à éliminer les erreurs.</span><span class="sxs-lookup"><span data-stu-id="09b33-162">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="09b33-163">Pour plus d’informations, voir :</span><span class="sxs-lookup"><span data-stu-id="09b33-163">For more information, see:</span></span>

- [<span data-ttu-id="09b33-164">Gérer les stratégies d’achat et de vente de congés</span><span class="sxs-lookup"><span data-stu-id="09b33-164">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="09b33-165">Achat et vente de congés</span><span class="sxs-lookup"><span data-stu-id="09b33-165">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="09b33-166">Provisions de congés pour une seule entreprise ou un seul plan</span><span class="sxs-lookup"><span data-stu-id="09b33-166">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="09b33-167">Les clients peuvent traiter les charges à payer pour une seule entreprise ou un seul plan de congé et d’absence.</span><span class="sxs-lookup"><span data-stu-id="09b33-167">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="09b33-168">Cette capacité permet de clarifier le processus d’accumulation pour les clients avec différentes années de congé ou politiques d’accumulation de congé.</span><span class="sxs-lookup"><span data-stu-id="09b33-168">This ability provides clarity for the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="09b33-169">Pour plus d’informations, voir [Accumulation de congés par entreprise ou par plan de congés](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="09b33-169">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="09b33-170">Ajouter des pièces jointes aux demandes de congé</span><span class="sxs-lookup"><span data-stu-id="09b33-170">Add attachments to time-off requests</span></span>

<span data-ttu-id="09b33-171">La possibilité d’ajouter des pièces jointes aux demandes de congé approuvées est essentielle dans l’environnement COVID-19 actuel.</span><span class="sxs-lookup"><span data-stu-id="09b33-171">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="09b33-172">Les employés peuvent désormais ajouter ces pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="09b33-172">Employees can now add these attachments.</span></span> <span data-ttu-id="09b33-173">Ils ont également plus d’informations sur la façon dont les mises à jour sont effectuées pour les demandes de congés.</span><span class="sxs-lookup"><span data-stu-id="09b33-173">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="09b33-174">Pour plus d’informations, voir [Ajouter une pièce jointe à une demande existante](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="09b33-174">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="09b33-175">Ajouter un code de motif aux suspensions de cumul</span><span class="sxs-lookup"><span data-stu-id="09b33-175">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="09b33-176">Des codes de motif ont été ajoutés à la suspension de la comptabilité d’exercice.</span><span class="sxs-lookup"><span data-stu-id="09b33-176">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="09b33-177">Règles de report</span><span class="sxs-lookup"><span data-stu-id="09b33-177">Carry forward rules</span></span> 

<span data-ttu-id="09b33-178">Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés.</span><span class="sxs-lookup"><span data-stu-id="09b33-178">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="09b33-179">Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours.</span><span class="sxs-lookup"><span data-stu-id="09b33-179">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="09b33-180">Pour plus d’informations, voir [Configurer les types de congé et d’absence](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="09b33-180">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="09b33-181">Suspendre l’accumulation de congés pour certains types de congés</span><span class="sxs-lookup"><span data-stu-id="09b33-181">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="09b33-182">Vous pouvez créer une règle pour suspendre les cumuls de congés pour les employés dont les demandes de congés ont été saisies pour des congés non payés.</span><span class="sxs-lookup"><span data-stu-id="09b33-182">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="09b33-183">Le congé sans solde peut être un type, mais ce n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="09b33-183">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="09b33-184">Vous pouvez suspendre tout congé basé sur un autre type de congé.</span><span class="sxs-lookup"><span data-stu-id="09b33-184">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="09b33-185">Entité DMF disponible pour les suspensions de régularisation</span><span class="sxs-lookup"><span data-stu-id="09b33-185">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="09b33-186">Une entité DMF est désormais disponible pour les suspensions de régularisation.</span><span class="sxs-lookup"><span data-stu-id="09b33-186">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="09b33-187">Prochainement</span><span class="sxs-lookup"><span data-stu-id="09b33-187">Coming soon</span></span>

## <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="09b33-188">Entités de liste de contrôle incluses dans Dataverse</span><span class="sxs-lookup"><span data-stu-id="09b33-188">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="09b33-189">Les entités de liste de contrôle pour les processus d’intégration, de départ, de transfert et d’entreprise seront bientôt disponibles dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="09b33-189">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="09b33-190">Voir également :</span><span class="sxs-lookup"><span data-stu-id="09b33-190">See also</span></span>

[<span data-ttu-id="09b33-191">Nouveautés ou modifications dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="09b33-191">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="09b33-192">Présentation de Dynamics 365 Human Resources 2019 vague de publication 2</span><span class="sxs-lookup"><span data-stu-id="09b33-192">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="09b33-193">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="09b33-193">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="09b33-194">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="09b33-194">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]