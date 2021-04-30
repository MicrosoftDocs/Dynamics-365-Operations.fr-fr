---
title: Nouveautés et modifications dans Dynamics 365 Human Resources (13 avril 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 13 avril 2020.
author: andreabichsel
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 93873707703ce7148c353735ce1abce795796a5e
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892007"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a><span data-ttu-id="e1e21-103">Nouveautés et modifications dans Dynamics 365 Human Resources (13 avril 2020)</span><span class="sxs-lookup"><span data-stu-id="e1e21-103">What's new or changed in Dynamics 365 Human Resources (April 13, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="e1e21-104">Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e1e21-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="e1e21-105">Les modifications s’appliquent au numéro de version 8.1.3136.</span><span class="sxs-lookup"><span data-stu-id="e1e21-105">Changes apply to build number 8.1.3136.</span></span> <span data-ttu-id="e1e21-106">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.</span><span class="sxs-lookup"><span data-stu-id="e1e21-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="new-production-release-cadence"></a><span data-ttu-id="e1e21-107">Nouvelle cadence de sortie de production</span><span class="sxs-lookup"><span data-stu-id="e1e21-107">New production release cadence</span></span>

<span data-ttu-id="e1e21-108">Avec cette publication hebdomadaire, le rythme de publication des versions pour Human Resources passe d’une mise à jour hebdomadaire à une mise à jour toutes les deux semaines.</span><span class="sxs-lookup"><span data-stu-id="e1e21-108">With this week's release, the release cadence for Human Resources shifts from a weekly update to a biweekly update.</span></span> <span data-ttu-id="e1e21-109">Pour garantir l’alignement avec les pratiques de déploiement sécurisées et maintenir des normes élevées de stabilité et de fiabilité du service, le processus de déploiement des mises à jour de service dans toutes les régions se déroulera sur deux semaines.</span><span class="sxs-lookup"><span data-stu-id="e1e21-109">To ensure alignment with safe deployment practices, and maintain high standards of stability and reliability in the service, the process of deploying service updates to all regions is now a two-week rollout.</span></span> <span data-ttu-id="e1e21-110">Des tests et des moniteurs supplémentaires seront en place pour vérifier le succès du déploiement à chaque étape du processus.</span><span class="sxs-lookup"><span data-stu-id="e1e21-110">Additional testing and monitors are in place to verify successful deployment at each stage of the process.</span></span> <span data-ttu-id="e1e21-111">Pour plus d’informations sur la cadence de publication, voir [Processus de mise à jour](hr-admin-setup-update-process.md).</span><span class="sxs-lookup"><span data-stu-id="e1e21-111">For more information on the release cadence, see [Update process](hr-admin-setup-update-process.md).</span></span>

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a><span data-ttu-id="e1e21-112">Le champ de précision d’arrondi n’est pas modifiable après avoir spécifié un type d’arrondi (435616)</span><span class="sxs-lookup"><span data-stu-id="e1e21-112">Rounding precision field isn't editable after specifying a Rounding type (435616)</span></span>

<span data-ttu-id="e1e21-113">Avec ce changement, le champ **Précision d’arrondi** est désormais disponible après la mise à jour du champ **Type d’arrondi**.</span><span class="sxs-lookup"><span data-stu-id="e1e21-113">With this change, the **Rounding precision** field is now available after you update the **Rounding type** field.</span></span>

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a><span data-ttu-id="e1e21-114">Impossible de modifier la date de fin d’inscription au congé lorsque le plan de congé ne comporte pas de périodes de régularisation (413628)</span><span class="sxs-lookup"><span data-stu-id="e1e21-114">Can't edit leave enrollment end date when the leave plan doesn't have accrual periods (413628)</span></span>

<span data-ttu-id="e1e21-115">Vous pouvez maintenant modifier la date de fin d’inscription sans obtenir l’erreur « La base de la date de régularisation du champ doit être renseignée ».</span><span class="sxs-lookup"><span data-stu-id="e1e21-115">You can now edit the enrollment end date without getting the error "Field Accrual date basis must be filled in."</span></span>

## <a name="employment-entity-doesnt-sync-to-dataverse-430834"></a><span data-ttu-id="e1e21-116">L’entité Emploi ne se synchronise pas avec Dataverse (430834)</span><span class="sxs-lookup"><span data-stu-id="e1e21-116">Employment entity doesn't sync to Dataverse (430834)</span></span>

<span data-ttu-id="e1e21-117">Cette modification corrige un problème impliquant que les données relatives à l’emploi n’étaient pas synchronisées avec Dataverse après l’ajout de dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="e1e21-117">This change corrects an issue where the employment data wasn't syncing to Dataverse after adding financial dimensions.</span></span> 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a><span data-ttu-id="e1e21-118">Supprimer la multi-parentalité pour l’entité Intervalle de temps du calendrier de travail (431775)</span><span class="sxs-lookup"><span data-stu-id="e1e21-118">Remove multi-parenting for Work Calendar Time Interval entity (431775)</span></span>

<span data-ttu-id="e1e21-119">Cette modification supprime la multi-parentalité pour l’entité **Intervalle de temps du calendrier de travail**.</span><span class="sxs-lookup"><span data-stu-id="e1e21-119">This change removes multi-parenting for the **Work Calendar Time Interval** entity.</span></span>

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a><span data-ttu-id="e1e21-120">Le filtre avec la fonction CAST ne fonctionne pas sur l’entité Affectation du collaborateur au poste de l’appel OData (431699)</span><span class="sxs-lookup"><span data-stu-id="e1e21-120">Filter with CAST function doesn't work on OData call Position Worker Assignment entity (431699)</span></span>

<span data-ttu-id="e1e21-121">Cette mise à jour inclut une modification pour autoriser le filtre avec la fonction CAST dans OData pour l’entité **Affectation du collaborateur au poste**.</span><span class="sxs-lookup"><span data-stu-id="e1e21-121">This update includes a change to allow  filter with CAST function within OData for the **Position Worker Assignment** entity.</span></span>

## <a name="in-preview"></a><span data-ttu-id="e1e21-122">En version préliminaire</span><span class="sxs-lookup"><span data-stu-id="e1e21-122">In Preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="e1e21-123">Suspension des congés</span><span class="sxs-lookup"><span data-stu-id="e1e21-123">Leave suspension</span></span>

<span data-ttu-id="e1e21-124">Vous pouvez suspendre les congés et les absences d’un employé dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e1e21-124">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="e1e21-125">La suspension des congés arrête les régularisations de congés pour les types de congé sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="e1e21-125">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="e1e21-126">Si la suspension survient après le traitement d’une régularisation, la suspension du congé crée un ajustement au prorata du solde des congés de l’employé.</span><span class="sxs-lookup"><span data-stu-id="e1e21-126">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="e1e21-127">Pour plus d’informations, voir la rubrique [Suspension des congés](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="e1e21-127">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="e1e21-128">Règles de report</span><span class="sxs-lookup"><span data-stu-id="e1e21-128">Carry forward rules</span></span>

<span data-ttu-id="e1e21-129">Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés.</span><span class="sxs-lookup"><span data-stu-id="e1e21-129">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="e1e21-130">Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours.</span><span class="sxs-lookup"><span data-stu-id="e1e21-130">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="e1e21-131">Pour plus d’informations, voir [Configurer les types de congé et d’absence](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="e1e21-131">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="e1e21-132">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="e1e21-132">Known issues</span></span>

## <a name="employment-details-entity"></a><span data-ttu-id="e1e21-133">Entité Détails de l’emploi</span><span class="sxs-lookup"><span data-stu-id="e1e21-133">Employment Details entity</span></span>

<span data-ttu-id="e1e21-134">L’entité **Détails de l’emploi** a été mise à jour avec les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="e1e21-134">The **Employment Detail** entity has been updated with the following fields:</span></span>

- <span data-ttu-id="e1e21-135">**PayFrequency**</span><span class="sxs-lookup"><span data-stu-id="e1e21-135">**PayFrequency**</span></span>
- <span data-ttu-id="e1e21-136">**ID catégorie d’emploi**</span><span class="sxs-lookup"><span data-stu-id="e1e21-136">**Employment Category ID**</span></span>
- <span data-ttu-id="e1e21-137">**Type d’emploi**</span><span class="sxs-lookup"><span data-stu-id="e1e21-137">**Employment Type**</span></span>
- <span data-ttu-id="e1e21-138">**ID EmploymentType**</span><span class="sxs-lookup"><span data-stu-id="e1e21-138">**EmploymentType ID**</span></span>
- <span data-ttu-id="e1e21-139">**Statut d’emploi à avantages**</span><span class="sxs-lookup"><span data-stu-id="e1e21-139">**Benefit Employment Status**</span></span>

<span data-ttu-id="e1e21-140">Les données de configuration de ces champs reposent sur l’activation de la gestion des avantages dans l’espace de travail **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="e1e21-140">The setup data for these fields rely on benefits management being enabled in the **Feature management** workspace.</span></span> <span data-ttu-id="e1e21-141">Ne complétez pas ces champs ou ne les mettez pas à jour dans l’entité **Détails de l’emploi**, car cela entraînera des erreurs lors de l’importation.</span><span class="sxs-lookup"><span data-stu-id="e1e21-141">Don't populate or update these fields in the **Employment Detail** entity, because it will result in errors during import.</span></span>

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a><span data-ttu-id="e1e21-142">L’aperçu SharePoint ne fonctionne pas dans certains environnements</span><span class="sxs-lookup"><span data-stu-id="e1e21-142">SharePoint preview doesn't work in some environments</span></span>

<span data-ttu-id="e1e21-143">Si l’aperçu du document pour les documents stockés dans SharePoint ne fonctionne pas, essayez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="e1e21-143">If document preview for documents stored in SharePoint doesn't work, try the following procedure:</span></span>

1. <span data-ttu-id="e1e21-144">Vérifiez que le compte utilisateur Admin possède un e-mail associé à l’enregistrement utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e1e21-144">Verify the Admin user account has an email associated with the user record.</span></span> <span data-ttu-id="e1e21-145">Vous pouvez afficher ces informations sur la page **Utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="e1e21-145">You can view this information in the **User** page.</span></span> <span data-ttu-id="e1e21-146">Si le courrier électronique n’est pas configuré, vous devez ajouter le courrier électronique et le fournisseur avec le complément OData Excel.</span><span class="sxs-lookup"><span data-stu-id="e1e21-146">If email isn't set up, you need to add the email and provider with the OData Excel add-in.</span></span> <span data-ttu-id="e1e21-147">Par défaut, l’adresse e-mail n’est pas présente dans la conception Excel.</span><span class="sxs-lookup"><span data-stu-id="e1e21-147">By default, the email address isn't present in the Excel design.</span></span> <span data-ttu-id="e1e21-148">Vous devrez modifier la conception d’Excel, ajouter tous les champs, appliquer et actualiser.</span><span class="sxs-lookup"><span data-stu-id="e1e21-148">You'll need to edit the Excel design, add all fields, apply, and refresh.</span></span> <span data-ttu-id="e1e21-149">Une fois ces étapes exécutées, vous pouvez mettre à jour le compte administrateur.</span><span class="sxs-lookup"><span data-stu-id="e1e21-149">Once you've completed those steps, you can update the admin account.</span></span>

2. <span data-ttu-id="e1e21-150">Une fois que le compte administrateur a un compte de messagerie associé, connectez-vous à Human Resources avec les informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="e1e21-150">After the Admin account has an associated email account, sign in to Human Resources with Admin credentials.</span></span>

3. <span data-ttu-id="e1e21-151">Accédez à une pièce jointe dans SharePoint pour lancer l’aperçu du document.</span><span class="sxs-lookup"><span data-stu-id="e1e21-151">Access an attachment in SharePoint to start the document preview.</span></span>

4. <span data-ttu-id="e1e21-152">Connectez-vous avec un autre compte d’utilisateur qui a accès aux pièces jointes et vérifiez que l’aperçu fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="e1e21-152">Sign in with another user account that has access to attachments and verify that the preview works as expected.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1e21-153">Voir également :</span><span class="sxs-lookup"><span data-stu-id="e1e21-153">See also</span></span>

[<span data-ttu-id="e1e21-154">Nouveautés ou modifications dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="e1e21-154">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="e1e21-155">Présentation de Dynamics 365 Human Resources 2019 vague de publication 2</span><span class="sxs-lookup"><span data-stu-id="e1e21-155">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="e1e21-156">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="e1e21-156">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="e1e21-157">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="e1e21-157">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]