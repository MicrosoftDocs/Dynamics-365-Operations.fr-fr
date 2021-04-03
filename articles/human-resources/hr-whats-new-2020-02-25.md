---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (25 février 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 25 février 2020.
author: andreabichsel
manager: tfehr
ms.date: 02/25/2020
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
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5048c94543d0ee35bbc0f210a86a5d58ae901510
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463764"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a><span data-ttu-id="d75a5-103">Nouveautés ou modifications dans Dynamics 365 Human Resources (25 février 2020)</span><span class="sxs-lookup"><span data-stu-id="d75a5-103">What's new or changed in Dynamics 365 Human Resources (February 25, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d75a5-104">Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d75a5-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="d75a5-105">Les modifications s’appliquent au numéro de version 8.1.2927.</span><span class="sxs-lookup"><span data-stu-id="d75a5-105">Changes apply to build number 8.1.2927.</span></span> <span data-ttu-id="d75a5-106">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.</span><span class="sxs-lookup"><span data-stu-id="d75a5-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a><span data-ttu-id="d75a5-107">Activer l’entité Infrastructure de gestion des données (DMF) et navigation de la gestion des dossiers (414754)</span><span class="sxs-lookup"><span data-stu-id="d75a5-107">Enable Case Management navigation and data management framework (DMF) entity (414754)</span></span>

<span data-ttu-id="d75a5-108">Cette fonction d’aperçu permet une navigation supplémentaire vers les cas de gestion des dossiers.</span><span class="sxs-lookup"><span data-stu-id="d75a5-108">This preview feature enables additional navigation to case management cases.</span></span> <span data-ttu-id="d75a5-109">Vous pouvez activer cette fonctionnalité en version préliminaire dans l’espace de travail **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="d75a5-109">You can enable this preview feature in the **Feature Management** workspace.</span></span> <span data-ttu-id="d75a5-110">Ces éléments de menu apparaissent dans l’espace de travail **Conformité** de Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d75a5-110">These menu items appear in the **Compliance** workspace of Dynamics 365 Human Resources.</span></span> <span data-ttu-id="d75a5-111">Avec cette modification, les ressources humaines peuvent accéder à :</span><span class="sxs-lookup"><span data-stu-id="d75a5-111">With this change, Human Resources can access:</span></span>

- <span data-ttu-id="d75a5-112">Tous les dossiers</span><span class="sxs-lookup"><span data-stu-id="d75a5-112">All cases</span></span>
- <span data-ttu-id="d75a5-113">Mes dossiers</span><span class="sxs-lookup"><span data-stu-id="d75a5-113">My cases</span></span>
- <span data-ttu-id="d75a5-114">Mes dossiers ouverts</span><span class="sxs-lookup"><span data-stu-id="d75a5-114">My open cases</span></span>
- <span data-ttu-id="d75a5-115">Mes dossiers en retard</span><span class="sxs-lookup"><span data-stu-id="d75a5-115">My overdue cases</span></span>
- <span data-ttu-id="d75a5-116">Dossiers affectés à moi-même via le flux de travail</span><span class="sxs-lookup"><span data-stu-id="d75a5-116">Cases assigned to me through workflow</span></span>

<span data-ttu-id="d75a5-117">Parallèlement à ces nouvelles vues des dossiers, l’entité DMF **Détail du dossier** est également disponible.</span><span class="sxs-lookup"><span data-stu-id="d75a5-117">Along with these new views into cases, the **Case detail** DMF entity is also available.</span></span>

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a><span data-ttu-id="d75a5-118">Activer les définitions de relations dans l’adresse bBook globale (414762)</span><span class="sxs-lookup"><span data-stu-id="d75a5-118">Enable Relationship definitions in global address bBook (414762)</span></span>

<span data-ttu-id="d75a5-119">Les relations sont désormais activées dans le carnet d’adresses global.</span><span class="sxs-lookup"><span data-stu-id="d75a5-119">Relationships are now enabled in the global address book.</span></span> <span data-ttu-id="d75a5-120">Avant la sortie de cette semaine, le récapitulatif **Relation** affichait toutes les relations définies par le système.</span><span class="sxs-lookup"><span data-stu-id="d75a5-120">Prior to this week's release, the **Relationship** fact box displayed any system-defined relationships.</span></span> <span data-ttu-id="d75a5-121">Vous pouvez maintenant définir ces relations dans la page du carnet d’adresses global.</span><span class="sxs-lookup"><span data-stu-id="d75a5-121">Now you can define those relationships within the global address book page.</span></span>

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a><span data-ttu-id="d75a5-122">Un poste peut être supprimé lorsqu’il existe des enregistrements de rémunération actifs pour le poste (414568)</span><span class="sxs-lookup"><span data-stu-id="d75a5-122">A position can be removed when active compensation records exist for the position (414568)</span></span>

<span data-ttu-id="d75a5-123">Avec cette modification, un avertissement s’affiche lorsque vous tentez de supprimer un poste et un collaborateur a un enregistrement de rémunération actif pour ce même poste.</span><span class="sxs-lookup"><span data-stu-id="d75a5-123">With this change, a warning appears when you attempt to delete a position and a worker has an active compensation record for that same position.</span></span> <span data-ttu-id="d75a5-124">Dans ce cas, vous devez mettre à jour l’enregistrement de rémunération fixe des employés avant de supprimer le poste.</span><span class="sxs-lookup"><span data-stu-id="d75a5-124">When this happens, you must update the employee fixed compensation record before removing the position.</span></span>

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a><span data-ttu-id="d75a5-125">Le flux de travail d’examen des performances ajoute occasionnellement des approbations de personnes qui ne font pas partie du processus (414171)</span><span class="sxs-lookup"><span data-stu-id="d75a5-125">Performance review workflow occasionally adds sign-offs from people who are not part of the process (414171)</span></span>

<span data-ttu-id="d75a5-126">Cette modification corrige un problème dans lequel des participants d’approbation supplémentaires sont ajoutés à l’évaluation des performances.</span><span class="sxs-lookup"><span data-stu-id="d75a5-126">This change corrects an issue where additional sign-off participants are added to the performance review.</span></span>

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a><span data-ttu-id="d75a5-127">Affectation de poste de travail non créée dans Dataverse lorsque sélectionné dans la boîte de dialogue Nouveau collaborateur (413479)</span><span class="sxs-lookup"><span data-stu-id="d75a5-127">Worker position assignment not created in Dataverse when selected on the New Worker dialog (413479)</span></span>

<span data-ttu-id="d75a5-128">Cette modification corrige un problème lors du recrutement d’un nouveau collaborateur et de l’affectation de la nouvelle recrue à un poste via la boîte de dialogue **Nouveau collaborateur**.</span><span class="sxs-lookup"><span data-stu-id="d75a5-128">This change corrects an issue when hiring a new worker and assigning the new hire to a position through the **New worker** dialog.</span></span> <span data-ttu-id="d75a5-129">Maintenant, l’affectation de poste se reflète dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d75a5-129">Now the position assignment is reflected in Dataverse.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="d75a5-130">Prochainement</span><span class="sxs-lookup"><span data-stu-id="d75a5-130">Coming soon</span></span>

### <a name="updated-dataverse-solution"></a><span data-ttu-id="d75a5-131">Solution Dataverse mise à jour</span><span class="sxs-lookup"><span data-stu-id="d75a5-131">Updated Dataverse solution</span></span>

<span data-ttu-id="d75a5-132">Une nouvelle solution Dataverse sera bientôt disponible avec les modifications suivantes :</span><span class="sxs-lookup"><span data-stu-id="d75a5-132">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="d75a5-133">Description</span><span class="sxs-lookup"><span data-stu-id="d75a5-133">Description</span></span> | <span data-ttu-id="d75a5-134">Monnaie</span><span class="sxs-lookup"><span data-stu-id="d75a5-134">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="d75a5-135">Modifications de l’entité **Poste**</span><span class="sxs-lookup"><span data-stu-id="d75a5-135">**Job/Position** entity changes</span></span> | <span data-ttu-id="d75a5-136">**Région de rémunération** ajoutée</span><span class="sxs-lookup"><span data-stu-id="d75a5-136">**Compensation region** added</span></span></br><span data-ttu-id="d75a5-137">**Dimensions financières** ajoutées</span><span class="sxs-lookup"><span data-stu-id="d75a5-137">**Financial dimensions** added</span></span> |
| <span data-ttu-id="d75a5-138">Modifications de l’entité **Collaborateur**</span><span class="sxs-lookup"><span data-stu-id="d75a5-138">**Worker** entity changes</span></span> | <span data-ttu-id="d75a5-139">**Séquence de noms** ajoutée</span><span class="sxs-lookup"><span data-stu-id="d75a5-139">**Name sequence** added</span></span></br><span data-ttu-id="d75a5-140">**Télétravaille** ajouté</span><span class="sxs-lookup"><span data-stu-id="d75a5-140">**Works from home** added</span></span></br><span data-ttu-id="d75a5-141">**Langue** ajoutée</span><span class="sxs-lookup"><span data-stu-id="d75a5-141">**Language** added</span></span></br><span data-ttu-id="d75a5-142">**Date d’ancienneté** ajoutée</span><span class="sxs-lookup"><span data-stu-id="d75a5-142">**Seniority date** added</span></span></br><span data-ttu-id="d75a5-143">**Date anniversaire** ajoutée</span><span class="sxs-lookup"><span data-stu-id="d75a5-143">**Anniversary date** added</span></span></br><span data-ttu-id="d75a5-144">**Date d’embauche d’origine** ajoutée</span><span class="sxs-lookup"><span data-stu-id="d75a5-144">**Original hire date** added</span></span> |
| <span data-ttu-id="d75a5-145">Modifications de l’entité **Emploi**</span><span class="sxs-lookup"><span data-stu-id="d75a5-145">**Employment** entity changes</span></span> | <span data-ttu-id="d75a5-146">**Dimensions financières** ajoutées</span><span class="sxs-lookup"><span data-stu-id="d75a5-146">**Financial dimensions** added</span></span></br><span data-ttu-id="d75a5-147">**Motif de la fin du contrat** ajouté</span><span class="sxs-lookup"><span data-stu-id="d75a5-147">**Termination reason** added</span></span></br><span data-ttu-id="d75a5-148">**Date de résiliation** renommée à partir de **Date de transition**</span><span class="sxs-lookup"><span data-stu-id="d75a5-148">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="d75a5-149">**Période d’essai** ajoutée</span><span class="sxs-lookup"><span data-stu-id="d75a5-149">**Probation date** added</span></span> |
| <span data-ttu-id="d75a5-150">Modifications de l’entité **Adresse du collaborateur**</span><span class="sxs-lookup"><span data-stu-id="d75a5-150">**Worker address** entity changes</span></span> | <span data-ttu-id="d75a5-151">**Nom de la rue** ajouté</span><span class="sxs-lookup"><span data-stu-id="d75a5-151">**Street address** added</span></span></br><span data-ttu-id="d75a5-152">**Ligne d’adresse 1**, **Ligne d’adresse 2** et **Ligne d’adresse 3** marquées pour suppression</span><span class="sxs-lookup"><span data-stu-id="d75a5-152">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="d75a5-153">Nouvelles entités de configuration de la rémunération variable</span><span class="sxs-lookup"><span data-stu-id="d75a5-153">New variable compensation setup entities</span></span> | <span data-ttu-id="d75a5-154">**Type de régime variable de rémunération**</span><span class="sxs-lookup"><span data-stu-id="d75a5-154">**Compensation variable plan type**</span></span></br><span data-ttu-id="d75a5-155">**Régime variable de rémunération**</span><span class="sxs-lookup"><span data-stu-id="d75a5-155">**Compensation variable plan**</span></span></br><span data-ttu-id="d75a5-156">**Règles d’acquisition**</span><span class="sxs-lookup"><span data-stu-id="d75a5-156">**Vesting rules**</span></span></br><span data-ttu-id="d75a5-157">**Niveau de régime variable de rémunération**</span><span class="sxs-lookup"><span data-stu-id="d75a5-157">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="d75a5-158">Nouvelle entité **Emploi du calendrier du collaborateur**</span><span class="sxs-lookup"><span data-stu-id="d75a5-158">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="d75a5-159">**Entité de calendrier de travail** ajoutée</span><span class="sxs-lookup"><span data-stu-id="d75a5-159">**Work calendar entity** added</span></span> |
| <span data-ttu-id="d75a5-160">Nouvelle entité **Détails du poste de paie**</span><span class="sxs-lookup"><span data-stu-id="d75a5-160">New **Payroll position detail** entity</span></span> | <span data-ttu-id="d75a5-161">**Détails du poste de paie** ajoutés</span><span class="sxs-lookup"><span data-stu-id="d75a5-161">**Payroll position detail** added</span></span> |
| <span data-ttu-id="d75a5-162">Nouvelle entité **Titre**</span><span class="sxs-lookup"><span data-stu-id="d75a5-162">New **Title** entity</span></span> | <span data-ttu-id="d75a5-163">**Titre** ajouté.</span><span class="sxs-lookup"><span data-stu-id="d75a5-163">**Title** added.</span></span> <span data-ttu-id="d75a5-164">La nouvelle entité **Titre** sera incluse dans le processus de synchronisation entre Human Resources et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d75a5-164">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="d75a5-165">Elle ne sera pas référencée initialement à partir des entités **Poste** ou **Tâche**.</span><span class="sxs-lookup"><span data-stu-id="d75a5-165">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

<span data-ttu-id="d75a5-166">Au cours des prochaines semaines, ces modifications d’entités seront disponibles dans tous les environnements.</span><span class="sxs-lookup"><span data-stu-id="d75a5-166">Over the next few weeks, these entity changes will be available in all environments.</span></span> <span data-ttu-id="d75a5-167">Pour installer manuellement la dernière solution Dataverse pour les ressources humaines :</span><span class="sxs-lookup"><span data-stu-id="d75a5-167">To manually install the latest Dataverse solution for Human Resources:</span></span>

1.  <span data-ttu-id="d75a5-168">Accédez au [Centre d’administration Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d75a5-168">Go to the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com).</span></span>

2.  <span data-ttu-id="d75a5-169">Sélectionner **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="d75a5-169">Select **Environments**.</span></span>

3.  <span data-ttu-id="d75a5-170">Recherchez l’environnement que vous souhaitez mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="d75a5-170">Find the environment you want to upgrade.</span></span> <span data-ttu-id="d75a5-171">Celui-ci doit correspondre à **Nom de l’environnement** dans la section **Informations relatives à Common Data Service** dans le formulaire **À propos de** dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d75a5-171">This should correspond to **Environment name** in the **Common Data Service information** section in the **About** form in Human Resources.</span></span>

4.  <span data-ttu-id="d75a5-172">Sélectionnez l’environnement pour afficher les détails de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="d75a5-172">Select the environment to view the environment details.</span></span>

5.  <span data-ttu-id="d75a5-173">Dans la barre d’action située en haut, sélectionnez **Gérer les solutions**.</span><span class="sxs-lookup"><span data-stu-id="d75a5-173">In the action bar at the top, select **Manage Solutions**.</span></span> <span data-ttu-id="d75a5-174">Une nouvelle fenêtre de navigateur s’ouvrira et accédera au **Centre d’administration Dynamics 365** dans le contexte de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d75a5-174">A new browser window will open and navigate to **Dynamics 365 Administration Center** in the context of your environment.</span></span>

6.  <span data-ttu-id="d75a5-175">Dans la liste **Solution**, sélectionnez **Ancre Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="d75a5-175">In the **Solution** list, select **Dynamics 365 Human Resources Anchor**.</span></span>

7.  <span data-ttu-id="d75a5-176">Sélectionnez **Mettre à niveau** pour appliquer la dernière solution.</span><span class="sxs-lookup"><span data-stu-id="d75a5-176">Select **Upgrade** to apply the latest solution.</span></span>

## <a name="in-preview"></a><span data-ttu-id="d75a5-177">En mode aperçu</span><span class="sxs-lookup"><span data-stu-id="d75a5-177">In preview</span></span>

<span data-ttu-id="d75a5-178">Les fonctionnalités d’aperçu suivantes sont disponibles depuis le 3 février 2020 :</span><span class="sxs-lookup"><span data-stu-id="d75a5-178">The following preview features became available on February 3, 2020:</span></span>

- <span data-ttu-id="d75a5-179">**Fonctionnalités d’aperçu de congé et d’absence** - Pour plus d’informations, voir [Fonctionnalités d’aperçu de congé et absence](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span><span class="sxs-lookup"><span data-stu-id="d75a5-179">**Leave and absence preview features** - For more information, see [Leave and absence preview features](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span></span>

- <span data-ttu-id="d75a5-180">**Fonction d’aperçu de la gestion des avantages** - Pour plus d’informations, y compris les problèmes connus, voir [Aperçu de la gestion des avantages](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d75a5-180">**Benefits management preview feature** - For more information, including known issues, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d75a5-181">Voir également :</span><span class="sxs-lookup"><span data-stu-id="d75a5-181">See also</span></span>

[<span data-ttu-id="d75a5-182">Nouveautés ou modifications dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="d75a5-182">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="d75a5-183">Présentation de Dynamics 365 Human Resources 2019 vague de publication 2</span><span class="sxs-lookup"><span data-stu-id="d75a5-183">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="d75a5-184">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="d75a5-184">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="d75a5-185">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="d75a5-185">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]