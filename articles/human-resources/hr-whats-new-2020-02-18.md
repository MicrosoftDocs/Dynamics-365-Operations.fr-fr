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
ms.openlocfilehash: e087095807f587536f2dad7e65fbc8beaa88878e
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128063"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a><span data-ttu-id="497c8-103">Nouveautés ou modifications dans Dynamics 365 Human Resources (18 février 2020)</span><span class="sxs-lookup"><span data-stu-id="497c8-103">What's new or changed in Dynamics 365 Human Resources (February 18, 2020)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="497c8-104">Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="497c8-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="497c8-105">Les modifications s’appliquent au numéro de version 8.1.2903.</span><span class="sxs-lookup"><span data-stu-id="497c8-105">Changes apply to build number 8.1.2903.</span></span> <span data-ttu-id="497c8-106">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.</span><span class="sxs-lookup"><span data-stu-id="497c8-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="497c8-107">Platform update 32</span><span class="sxs-lookup"><span data-stu-id="497c8-107">Platform update 32</span></span> 

<span data-ttu-id="497c8-108">Platform update 32 est désormais disponible.</span><span class="sxs-lookup"><span data-stu-id="497c8-108">Platform update 32 is now available.</span></span> <span data-ttu-id="497c8-109">Pour plus d’informations, voir [Nouveautés ou modifications dans Platform update 32 pour Finance and Operations (février 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).</span><span class="sxs-lookup"><span data-stu-id="497c8-109">For more information, see [What's new or changed in Platform update 32 for Finance and Operations (February 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).</span></span>

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a><span data-ttu-id="497c8-110">Les valeurs de recherche sont mémorisées lors de la modification des options d’affichage dans le formulaire simplifié des employés (383833)</span><span class="sxs-lookup"><span data-stu-id="497c8-110">Search values are remembered when changing view options in streamlined employee form (383833)</span></span>

<span data-ttu-id="497c8-111">Le nouveau formulaire **Collaborateur** mémorise désormais les valeurs de recherche lorsque vous modifiez les options d’affichage et appliquez les modifications.</span><span class="sxs-lookup"><span data-stu-id="497c8-111">The new **Worker** form now remembers  search values when you change the view options and apply changes.</span></span>

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a><span data-ttu-id="497c8-112">Les vignettes récapitulatives de gestion de la rémunération dans la fonctionnalité en version préliminaire redirigent vers un formulaire incorrect (401861)</span><span class="sxs-lookup"><span data-stu-id="497c8-112">Compensation management summary tiles in preview feature redirect to wrong form (401861)</span></span>

<span data-ttu-id="497c8-113">Les vignettes de gestion de la rémunération fixe et variable affichent désormais les enregistrements corrects dans le nouveau formlaire **Collaborateur**.</span><span class="sxs-lookup"><span data-stu-id="497c8-113">Fixed and variable compensation management tiles now display the correct records in the new **Worker** form.</span></span> <span data-ttu-id="497c8-114">S’applique uniquement à la fonctionnalité en version préliminaire du formulaire simplifié des employés.</span><span class="sxs-lookup"><span data-stu-id="497c8-114">Applies only to the streamlined employee form preview feature.</span></span> <span data-ttu-id="497c8-115">Vous pouvez activer cette fonctionnalité en version préliminaire dans **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="497c8-115">You can enable this preview feature in **Feature management**.</span></span> <span data-ttu-id="497c8-116">Pour plus d’informations, voir [Gérer les fonctionnalités](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="497c8-116">For more information, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a><span data-ttu-id="497c8-117">Champ Statut vide pour certains enregistrements de demande de congé dans Dataverse (414915)</span><span class="sxs-lookup"><span data-stu-id="497c8-117">Empty Status field for some leave request records in Dataverse (414915)</span></span>

<span data-ttu-id="497c8-118">Cette modification corrige un problème dans Dataverse lorsque le champ **Statut** d’une demande de congé est défini sur **Révision**.</span><span class="sxs-lookup"><span data-stu-id="497c8-118">This change corrects an issue in Dataverse when the **Status** field in a leave request is set to **Review**.</span></span> <span data-ttu-id="497c8-119">Dataverse reflète maintenant le statut.</span><span class="sxs-lookup"><span data-stu-id="497c8-119">Dataverse now reflects the status.</span></span>

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a><span data-ttu-id="497c8-120">L’analyse des écarts de compétences n’est possible que pour les tâches affectées (411390)</span><span class="sxs-lookup"><span data-stu-id="497c8-120">Skill gap analysis only possible for assigned job (411390)</span></span>

<span data-ttu-id="497c8-121">Vous pouvez désormais effectuer une analyse des écarts de compétences sur n’importe quelle tâche définie dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="497c8-121">You can now do a skill gap analysis on any job defined in Human Resources.</span></span>

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a><span data-ttu-id="497c8-122">La devise du système ne se synchronise pas entre Dataverse et Human Resources dans les nouveaux environnements (418011)</span><span class="sxs-lookup"><span data-stu-id="497c8-122">System currency doesn't sync from Dataverse to Human Resources in new environments (418011)</span></span>

<span data-ttu-id="497c8-123">La devise du système dans Dataverse peut maintenant se synchroniser avec Human Resources.</span><span class="sxs-lookup"><span data-stu-id="497c8-123">The system currency in Dataverse can now sync to Human Resources.</span></span>

## <a name="in-preview"></a><span data-ttu-id="497c8-124">En mode aperçu</span><span class="sxs-lookup"><span data-stu-id="497c8-124">In preview</span></span>

- [<span data-ttu-id="497c8-125">Fonctionnalités d’aperçu des congés et absences</span><span class="sxs-lookup"><span data-stu-id="497c8-125">Leave and absence preview features</span></span>](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [<span data-ttu-id="497c8-126">Fonctionnalités en version préliminaire de gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="497c8-126">Benefits management preview features</span></span>](hr-benefits-management-overview.md)

## <a name="coming-soon"></a><span data-ttu-id="497c8-127">Prochainement</span><span class="sxs-lookup"><span data-stu-id="497c8-127">Coming soon</span></span>

### <a name="updated-dataverse-solution"></a><span data-ttu-id="497c8-128">Solution Dataverse mise à jour</span><span class="sxs-lookup"><span data-stu-id="497c8-128">Updated Dataverse solution</span></span>

<span data-ttu-id="497c8-129">Une nouvelle solution Dataverse sera bientôt disponible avec les modifications suivantes :</span><span class="sxs-lookup"><span data-stu-id="497c8-129">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="497c8-130">Description</span><span class="sxs-lookup"><span data-stu-id="497c8-130">Description</span></span> | <span data-ttu-id="497c8-131">Monnaie</span><span class="sxs-lookup"><span data-stu-id="497c8-131">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="497c8-132">Modifications de l’entité **Poste**</span><span class="sxs-lookup"><span data-stu-id="497c8-132">**Job/Position** entity changes</span></span> | <span data-ttu-id="497c8-133">**Région de rémunération** ajoutée</span><span class="sxs-lookup"><span data-stu-id="497c8-133">**Compensation region** added</span></span></br><span data-ttu-id="497c8-134">**Dimensions financières** ajoutées</span><span class="sxs-lookup"><span data-stu-id="497c8-134">**Financial dimensions** added</span></span> |
| <span data-ttu-id="497c8-135">Modifications de l’entité **Collaborateur**</span><span class="sxs-lookup"><span data-stu-id="497c8-135">**Worker** entity changes</span></span> | <span data-ttu-id="497c8-136">**Séquence de noms** ajoutée</span><span class="sxs-lookup"><span data-stu-id="497c8-136">**Name sequence** added</span></span></br><span data-ttu-id="497c8-137">**Télétravaille** ajouté</span><span class="sxs-lookup"><span data-stu-id="497c8-137">**Works from home** added</span></span></br><span data-ttu-id="497c8-138">**Langue** ajoutée</span><span class="sxs-lookup"><span data-stu-id="497c8-138">**Language** added</span></span></br><span data-ttu-id="497c8-139">**Date d’ancienneté** ajoutée</span><span class="sxs-lookup"><span data-stu-id="497c8-139">**Seniority date** added</span></span></br><span data-ttu-id="497c8-140">**Date anniversaire** ajoutée</span><span class="sxs-lookup"><span data-stu-id="497c8-140">**Anniversary date** added</span></span></br><span data-ttu-id="497c8-141">**Date d’embauche d’origine** ajoutée</span><span class="sxs-lookup"><span data-stu-id="497c8-141">**Original hire date** added</span></span> |
| <span data-ttu-id="497c8-142">Modifications de l’entité **Emploi**</span><span class="sxs-lookup"><span data-stu-id="497c8-142">**Employment** entity changes</span></span> | <span data-ttu-id="497c8-143">**Dimensions financières** ajoutées</span><span class="sxs-lookup"><span data-stu-id="497c8-143">**Financial dimensions** added</span></span></br><span data-ttu-id="497c8-144">**Motif de la fin du contrat** ajouté</span><span class="sxs-lookup"><span data-stu-id="497c8-144">**Termination reason** added</span></span></br><span data-ttu-id="497c8-145">**Date de résiliation** renommée à partir de **Date de transition**</span><span class="sxs-lookup"><span data-stu-id="497c8-145">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="497c8-146">**Période d’essai** ajoutée</span><span class="sxs-lookup"><span data-stu-id="497c8-146">**Probation date** added</span></span> |
| <span data-ttu-id="497c8-147">Modifications de l’entité **Adresse du collaborateur**</span><span class="sxs-lookup"><span data-stu-id="497c8-147">**Worker address** entity changes</span></span> | <span data-ttu-id="497c8-148">**Nom de la rue** ajouté</span><span class="sxs-lookup"><span data-stu-id="497c8-148">**Street address** added</span></span></br><span data-ttu-id="497c8-149">**Ligne d’adresse 1**, **Ligne d’adresse 2** et **Ligne d’adresse 3** marquées pour suppression</span><span class="sxs-lookup"><span data-stu-id="497c8-149">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="497c8-150">Nouvelles entités de configuration de la rémunération variable</span><span class="sxs-lookup"><span data-stu-id="497c8-150">New variable compensation setup entities</span></span> | <span data-ttu-id="497c8-151">**Type de régime variable de rémunération**</span><span class="sxs-lookup"><span data-stu-id="497c8-151">**Compensation variable plan type**</span></span></br><span data-ttu-id="497c8-152">**Régime variable de rémunération**</span><span class="sxs-lookup"><span data-stu-id="497c8-152">**Compensation variable plan**</span></span></br><span data-ttu-id="497c8-153">**Règles d’acquisition**</span><span class="sxs-lookup"><span data-stu-id="497c8-153">**Vesting rules**</span></span></br><span data-ttu-id="497c8-154">**Niveau de régime variable de rémunération**</span><span class="sxs-lookup"><span data-stu-id="497c8-154">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="497c8-155">Nouvelle entité **Emploi du calendrier du collaborateur**</span><span class="sxs-lookup"><span data-stu-id="497c8-155">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="497c8-156">**Entité de calendrier de travail** ajoutée</span><span class="sxs-lookup"><span data-stu-id="497c8-156">**Work calendar entity** added</span></span> |
| <span data-ttu-id="497c8-157">Nouvelle entité **Détails du poste de paie**</span><span class="sxs-lookup"><span data-stu-id="497c8-157">New **Payroll position detail** entity</span></span> | <span data-ttu-id="497c8-158">**Détails du poste de paie** ajoutés</span><span class="sxs-lookup"><span data-stu-id="497c8-158">**Payroll position detail** added</span></span> |
| <span data-ttu-id="497c8-159">Nouvelle entité **Titre**</span><span class="sxs-lookup"><span data-stu-id="497c8-159">New **Title** entity</span></span> | <span data-ttu-id="497c8-160">**Titre** ajouté.</span><span class="sxs-lookup"><span data-stu-id="497c8-160">**Title** added.</span></span> <span data-ttu-id="497c8-161">La nouvelle entité **Titre** sera incluse dans le processus de synchronisation entre Human Resources et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="497c8-161">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="497c8-162">Elle ne sera pas référencée initialement à partir des entités **Poste** ou **Tâche**.</span><span class="sxs-lookup"><span data-stu-id="497c8-162">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

## <a name="see-also"></a><span data-ttu-id="497c8-163">Voir également :</span><span class="sxs-lookup"><span data-stu-id="497c8-163">See also</span></span>

[<span data-ttu-id="497c8-164">Nouveautés ou modifications dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="497c8-164">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="497c8-165">Présentation de Dynamics 365 Human Resources 2019 vague de publication 2</span><span class="sxs-lookup"><span data-stu-id="497c8-165">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="497c8-166">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="497c8-166">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="497c8-167">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="497c8-167">Manage features</span></span>](hr-admin-manage-features.md)