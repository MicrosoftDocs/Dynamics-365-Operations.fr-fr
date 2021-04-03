---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (18 février 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 18 février 2020.
author: andreabichsel
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 66ffd9d0ffcf0e8466be785274ef5fb0fceda7a9
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463788"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a><span data-ttu-id="a5195-103">Nouveautés ou modifications dans Dynamics 365 Human Resources (18 février 2020)</span><span class="sxs-lookup"><span data-stu-id="a5195-103">What's new or changed in Dynamics 365 Human Resources (February 18, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a5195-104">Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a5195-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="a5195-105">Les modifications s’appliquent au numéro de version 8.1.2903.</span><span class="sxs-lookup"><span data-stu-id="a5195-105">Changes apply to build number 8.1.2903.</span></span> <span data-ttu-id="a5195-106">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.</span><span class="sxs-lookup"><span data-stu-id="a5195-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="a5195-107">Platform update 32</span><span class="sxs-lookup"><span data-stu-id="a5195-107">Platform update 32</span></span> 

<span data-ttu-id="a5195-108">Platform update 32 est désormais disponible.</span><span class="sxs-lookup"><span data-stu-id="a5195-108">Platform update 32 is now available.</span></span> <span data-ttu-id="a5195-109">Pour plus d’informations, voir [Nouveautés ou modifications dans Platform update 32 pour Finance and Operations (février 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).</span><span class="sxs-lookup"><span data-stu-id="a5195-109">For more information, see [What's new or changed in Platform update 32 for Finance and Operations (February 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).</span></span>

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a><span data-ttu-id="a5195-110">Les valeurs de recherche sont mémorisées lors de la modification des options d’affichage dans le formulaire simplifié des employés (383833)</span><span class="sxs-lookup"><span data-stu-id="a5195-110">Search values are remembered when changing view options in streamlined employee form (383833)</span></span>

<span data-ttu-id="a5195-111">Le nouveau formulaire **Collaborateur** mémorise désormais les valeurs de recherche lorsque vous modifiez les options d’affichage et appliquez les modifications.</span><span class="sxs-lookup"><span data-stu-id="a5195-111">The new **Worker** form now remembers  search values when you change the view options and apply changes.</span></span>

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a><span data-ttu-id="a5195-112">Les vignettes récapitulatives de gestion de la rémunération dans la fonctionnalité en version préliminaire redirigent vers un formulaire incorrect (401861)</span><span class="sxs-lookup"><span data-stu-id="a5195-112">Compensation management summary tiles in preview feature redirect to wrong form (401861)</span></span>

<span data-ttu-id="a5195-113">Les vignettes de gestion de la rémunération fixe et variable affichent désormais les enregistrements corrects dans le nouveau formlaire **Collaborateur**.</span><span class="sxs-lookup"><span data-stu-id="a5195-113">Fixed and variable compensation management tiles now display the correct records in the new **Worker** form.</span></span> <span data-ttu-id="a5195-114">S’applique uniquement à la fonctionnalité en version préliminaire du formulaire simplifié des employés.</span><span class="sxs-lookup"><span data-stu-id="a5195-114">Applies only to the streamlined employee form preview feature.</span></span> <span data-ttu-id="a5195-115">Vous pouvez activer cette fonctionnalité en version préliminaire dans **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="a5195-115">You can enable this preview feature in **Feature management**.</span></span> <span data-ttu-id="a5195-116">Pour plus d’informations, voir [Gérer les fonctionnalités](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="a5195-116">For more information, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a><span data-ttu-id="a5195-117">Champ Statut vide pour certains enregistrements de demande de congé dans Dataverse (414915)</span><span class="sxs-lookup"><span data-stu-id="a5195-117">Empty Status field for some leave request records in Dataverse (414915)</span></span>

<span data-ttu-id="a5195-118">Cette modification corrige un problème dans Dataverse lorsque le champ **Statut** d’une demande de congé est défini sur **Révision**.</span><span class="sxs-lookup"><span data-stu-id="a5195-118">This change corrects an issue in Dataverse when the **Status** field in a leave request is set to **Review**.</span></span> <span data-ttu-id="a5195-119">Dataverse reflète maintenant le statut.</span><span class="sxs-lookup"><span data-stu-id="a5195-119">Dataverse now reflects the status.</span></span>

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a><span data-ttu-id="a5195-120">L’analyse des écarts de compétences n’est possible que pour les tâches affectées (411390)</span><span class="sxs-lookup"><span data-stu-id="a5195-120">Skill gap analysis only possible for assigned job (411390)</span></span>

<span data-ttu-id="a5195-121">Vous pouvez désormais effectuer une analyse des écarts de compétences sur n’importe quelle tâche définie dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a5195-121">You can now do a skill gap analysis on any job defined in Human Resources.</span></span>

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a><span data-ttu-id="a5195-122">La devise du système ne se synchronise pas entre Dataverse et Human Resources dans les nouveaux environnements (418011)</span><span class="sxs-lookup"><span data-stu-id="a5195-122">System currency doesn't sync from Dataverse to Human Resources in new environments (418011)</span></span>

<span data-ttu-id="a5195-123">La devise du système dans Dataverse peut maintenant se synchroniser avec Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a5195-123">The system currency in Dataverse can now sync to Human Resources.</span></span>

## <a name="in-preview"></a><span data-ttu-id="a5195-124">En mode aperçu</span><span class="sxs-lookup"><span data-stu-id="a5195-124">In preview</span></span>

- [<span data-ttu-id="a5195-125">Fonctionnalités d’aperçu des congés et absences</span><span class="sxs-lookup"><span data-stu-id="a5195-125">Leave and absence preview features</span></span>](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [<span data-ttu-id="a5195-126">Fonctionnalités en version préliminaire de gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="a5195-126">Benefits management preview features</span></span>](hr-benefits-management-overview.md)

## <a name="coming-soon"></a><span data-ttu-id="a5195-127">Prochainement</span><span class="sxs-lookup"><span data-stu-id="a5195-127">Coming soon</span></span>

### <a name="updated-dataverse-solution"></a><span data-ttu-id="a5195-128">Solution Dataverse mise à jour</span><span class="sxs-lookup"><span data-stu-id="a5195-128">Updated Dataverse solution</span></span>

<span data-ttu-id="a5195-129">Une nouvelle solution Dataverse sera bientôt disponible avec les modifications suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5195-129">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="a5195-130">Description</span><span class="sxs-lookup"><span data-stu-id="a5195-130">Description</span></span> | <span data-ttu-id="a5195-131">Monnaie</span><span class="sxs-lookup"><span data-stu-id="a5195-131">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="a5195-132">Modifications de l’entité **Poste**</span><span class="sxs-lookup"><span data-stu-id="a5195-132">**Job/Position** entity changes</span></span> | <span data-ttu-id="a5195-133">**Région de rémunération** ajoutée</span><span class="sxs-lookup"><span data-stu-id="a5195-133">**Compensation region** added</span></span></br><span data-ttu-id="a5195-134">**Dimensions financières** ajoutées</span><span class="sxs-lookup"><span data-stu-id="a5195-134">**Financial dimensions** added</span></span> |
| <span data-ttu-id="a5195-135">Modifications de l’entité **Collaborateur**</span><span class="sxs-lookup"><span data-stu-id="a5195-135">**Worker** entity changes</span></span> | <span data-ttu-id="a5195-136">**Séquence de noms** ajoutée</span><span class="sxs-lookup"><span data-stu-id="a5195-136">**Name sequence** added</span></span></br><span data-ttu-id="a5195-137">**Télétravaille** ajouté</span><span class="sxs-lookup"><span data-stu-id="a5195-137">**Works from home** added</span></span></br><span data-ttu-id="a5195-138">**Langue** ajoutée</span><span class="sxs-lookup"><span data-stu-id="a5195-138">**Language** added</span></span></br><span data-ttu-id="a5195-139">**Date d’ancienneté** ajoutée</span><span class="sxs-lookup"><span data-stu-id="a5195-139">**Seniority date** added</span></span></br><span data-ttu-id="a5195-140">**Date anniversaire** ajoutée</span><span class="sxs-lookup"><span data-stu-id="a5195-140">**Anniversary date** added</span></span></br><span data-ttu-id="a5195-141">**Date d’embauche d’origine** ajoutée</span><span class="sxs-lookup"><span data-stu-id="a5195-141">**Original hire date** added</span></span> |
| <span data-ttu-id="a5195-142">Modifications de l’entité **Emploi**</span><span class="sxs-lookup"><span data-stu-id="a5195-142">**Employment** entity changes</span></span> | <span data-ttu-id="a5195-143">**Dimensions financières** ajoutées</span><span class="sxs-lookup"><span data-stu-id="a5195-143">**Financial dimensions** added</span></span></br><span data-ttu-id="a5195-144">**Motif de la fin du contrat** ajouté</span><span class="sxs-lookup"><span data-stu-id="a5195-144">**Termination reason** added</span></span></br><span data-ttu-id="a5195-145">**Date de résiliation** renommée à partir de **Date de transition**</span><span class="sxs-lookup"><span data-stu-id="a5195-145">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="a5195-146">**Période d’essai** ajoutée</span><span class="sxs-lookup"><span data-stu-id="a5195-146">**Probation date** added</span></span> |
| <span data-ttu-id="a5195-147">Modifications de l’entité **Adresse du collaborateur**</span><span class="sxs-lookup"><span data-stu-id="a5195-147">**Worker address** entity changes</span></span> | <span data-ttu-id="a5195-148">**Nom de la rue** ajouté</span><span class="sxs-lookup"><span data-stu-id="a5195-148">**Street address** added</span></span></br><span data-ttu-id="a5195-149">**Ligne d’adresse 1**, **Ligne d’adresse 2** et **Ligne d’adresse 3** marquées pour suppression</span><span class="sxs-lookup"><span data-stu-id="a5195-149">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="a5195-150">Nouvelles entités de configuration de la rémunération variable</span><span class="sxs-lookup"><span data-stu-id="a5195-150">New variable compensation setup entities</span></span> | <span data-ttu-id="a5195-151">**Type de régime variable de rémunération**</span><span class="sxs-lookup"><span data-stu-id="a5195-151">**Compensation variable plan type**</span></span></br><span data-ttu-id="a5195-152">**Régime variable de rémunération**</span><span class="sxs-lookup"><span data-stu-id="a5195-152">**Compensation variable plan**</span></span></br><span data-ttu-id="a5195-153">**Règles d’acquisition**</span><span class="sxs-lookup"><span data-stu-id="a5195-153">**Vesting rules**</span></span></br><span data-ttu-id="a5195-154">**Niveau de régime variable de rémunération**</span><span class="sxs-lookup"><span data-stu-id="a5195-154">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="a5195-155">Nouvelle entité **Emploi du calendrier du collaborateur**</span><span class="sxs-lookup"><span data-stu-id="a5195-155">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="a5195-156">**Entité de calendrier de travail** ajoutée</span><span class="sxs-lookup"><span data-stu-id="a5195-156">**Work calendar entity** added</span></span> |
| <span data-ttu-id="a5195-157">Nouvelle entité **Détails du poste de paie**</span><span class="sxs-lookup"><span data-stu-id="a5195-157">New **Payroll position detail** entity</span></span> | <span data-ttu-id="a5195-158">**Détails du poste de paie** ajoutés</span><span class="sxs-lookup"><span data-stu-id="a5195-158">**Payroll position detail** added</span></span> |
| <span data-ttu-id="a5195-159">Nouvelle entité **Titre**</span><span class="sxs-lookup"><span data-stu-id="a5195-159">New **Title** entity</span></span> | <span data-ttu-id="a5195-160">**Titre** ajouté.</span><span class="sxs-lookup"><span data-stu-id="a5195-160">**Title** added.</span></span> <span data-ttu-id="a5195-161">La nouvelle entité **Titre** sera incluse dans le processus de synchronisation entre Human Resources et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a5195-161">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="a5195-162">Elle ne sera pas référencée initialement à partir des entités **Poste** ou **Tâche**.</span><span class="sxs-lookup"><span data-stu-id="a5195-162">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a5195-163">Voir également :</span><span class="sxs-lookup"><span data-stu-id="a5195-163">See also</span></span>

[<span data-ttu-id="a5195-164">Nouveautés ou modifications dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="a5195-164">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="a5195-165">Présentation de Dynamics 365 Human Resources 2019 vague de publication 2</span><span class="sxs-lookup"><span data-stu-id="a5195-165">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="a5195-166">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="a5195-166">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="a5195-167">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="a5195-167">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]