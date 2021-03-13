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
ms.openlocfilehash: 4faecb83518f3ef8af825872abc2a6ffb94162fc
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128020"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a><span data-ttu-id="c2c42-103">Nouveautés ou modifications dans Dynamics 365 Human Resources (25 février 2020)</span><span class="sxs-lookup"><span data-stu-id="c2c42-103">What's new or changed in Dynamics 365 Human Resources (February 25, 2020)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="c2c42-104">Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c2c42-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="c2c42-105">Les modifications s’appliquent au numéro de version 8.1.2927.</span><span class="sxs-lookup"><span data-stu-id="c2c42-105">Changes apply to build number 8.1.2927.</span></span> <span data-ttu-id="c2c42-106">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.</span><span class="sxs-lookup"><span data-stu-id="c2c42-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a><span data-ttu-id="c2c42-107">Activer l’entité Infrastructure de gestion des données (DMF) et navigation de la gestion des dossiers (414754)</span><span class="sxs-lookup"><span data-stu-id="c2c42-107">Enable Case Management navigation and data management framework (DMF) entity (414754)</span></span>

<span data-ttu-id="c2c42-108">Cette fonction d’aperçu permet une navigation supplémentaire vers les cas de gestion des dossiers.</span><span class="sxs-lookup"><span data-stu-id="c2c42-108">This preview feature enables additional navigation to case management cases.</span></span> <span data-ttu-id="c2c42-109">Vous pouvez activer cette fonctionnalité en version préliminaire dans l’espace de travail **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="c2c42-109">You can enable this preview feature in the **Feature Management** workspace.</span></span> <span data-ttu-id="c2c42-110">Ces éléments de menu apparaissent dans l’espace de travail **Conformité** de Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c2c42-110">These menu items appear in the **Compliance** workspace of Dynamics 365 Human Resources.</span></span> <span data-ttu-id="c2c42-111">Avec cette modification, les ressources humaines peuvent accéder à :</span><span class="sxs-lookup"><span data-stu-id="c2c42-111">With this change, Human Resources can access:</span></span>

- <span data-ttu-id="c2c42-112">Tous les dossiers</span><span class="sxs-lookup"><span data-stu-id="c2c42-112">All cases</span></span>
- <span data-ttu-id="c2c42-113">Mes dossiers</span><span class="sxs-lookup"><span data-stu-id="c2c42-113">My cases</span></span>
- <span data-ttu-id="c2c42-114">Mes dossiers ouverts</span><span class="sxs-lookup"><span data-stu-id="c2c42-114">My open cases</span></span>
- <span data-ttu-id="c2c42-115">Mes dossiers en retard</span><span class="sxs-lookup"><span data-stu-id="c2c42-115">My overdue cases</span></span>
- <span data-ttu-id="c2c42-116">Dossiers affectés à moi-même via le flux de travail</span><span class="sxs-lookup"><span data-stu-id="c2c42-116">Cases assigned to me through workflow</span></span>

<span data-ttu-id="c2c42-117">Parallèlement à ces nouvelles vues des dossiers, l’entité DMF **Détail du dossier** est également disponible.</span><span class="sxs-lookup"><span data-stu-id="c2c42-117">Along with these new views into cases, the **Case detail** DMF entity is also available.</span></span>

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a><span data-ttu-id="c2c42-118">Activer les définitions de relations dans l’adresse bBook globale (414762)</span><span class="sxs-lookup"><span data-stu-id="c2c42-118">Enable Relationship definitions in global address bBook (414762)</span></span>

<span data-ttu-id="c2c42-119">Les relations sont désormais activées dans le carnet d’adresses global.</span><span class="sxs-lookup"><span data-stu-id="c2c42-119">Relationships are now enabled in the global address book.</span></span> <span data-ttu-id="c2c42-120">Avant la sortie de cette semaine, le récapitulatif **Relation** affichait toutes les relations définies par le système.</span><span class="sxs-lookup"><span data-stu-id="c2c42-120">Prior to this week's release, the **Relationship** fact box displayed any system-defined relationships.</span></span> <span data-ttu-id="c2c42-121">Vous pouvez maintenant définir ces relations dans la page du carnet d’adresses global.</span><span class="sxs-lookup"><span data-stu-id="c2c42-121">Now you can define those relationships within the global address book page.</span></span>

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a><span data-ttu-id="c2c42-122">Un poste peut être supprimé lorsqu’il existe des enregistrements de rémunération actifs pour le poste (414568)</span><span class="sxs-lookup"><span data-stu-id="c2c42-122">A position can be removed when active compensation records exist for the position (414568)</span></span>

<span data-ttu-id="c2c42-123">Avec cette modification, un avertissement s’affiche lorsque vous tentez de supprimer un poste et un collaborateur a un enregistrement de rémunération actif pour ce même poste.</span><span class="sxs-lookup"><span data-stu-id="c2c42-123">With this change, a warning appears when you attempt to delete a position and a worker has an active compensation record for that same position.</span></span> <span data-ttu-id="c2c42-124">Dans ce cas, vous devez mettre à jour l’enregistrement de rémunération fixe des employés avant de supprimer le poste.</span><span class="sxs-lookup"><span data-stu-id="c2c42-124">When this happens, you must update the employee fixed compensation record before removing the position.</span></span>

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a><span data-ttu-id="c2c42-125">Le flux de travail d’examen des performances ajoute occasionnellement des approbations de personnes qui ne font pas partie du processus (414171)</span><span class="sxs-lookup"><span data-stu-id="c2c42-125">Performance review workflow occasionally adds sign-offs from people who are not part of the process (414171)</span></span>

<span data-ttu-id="c2c42-126">Cette modification corrige un problème dans lequel des participants d’approbation supplémentaires sont ajoutés à l’évaluation des performances.</span><span class="sxs-lookup"><span data-stu-id="c2c42-126">This change corrects an issue where additional sign-off participants are added to the performance review.</span></span>

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a><span data-ttu-id="c2c42-127">Affectation de poste de travail non créée dans Dataverse lorsque sélectionné dans la boîte de dialogue Nouveau collaborateur (413479)</span><span class="sxs-lookup"><span data-stu-id="c2c42-127">Worker position assignment not created in Dataverse when selected on the New Worker dialog (413479)</span></span>

<span data-ttu-id="c2c42-128">Cette modification corrige un problème lors du recrutement d’un nouveau collaborateur et de l’affectation de la nouvelle recrue à un poste via la boîte de dialogue **Nouveau collaborateur**.</span><span class="sxs-lookup"><span data-stu-id="c2c42-128">This change corrects an issue when hiring a new worker and assigning the new hire to a position through the **New worker** dialog.</span></span> <span data-ttu-id="c2c42-129">Maintenant, l’affectation de poste se reflète dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c2c42-129">Now the position assignment is reflected in Dataverse.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="c2c42-130">Prochainement</span><span class="sxs-lookup"><span data-stu-id="c2c42-130">Coming soon</span></span>

### <a name="updated-dataverse-solution"></a><span data-ttu-id="c2c42-131">Solution Dataverse mise à jour</span><span class="sxs-lookup"><span data-stu-id="c2c42-131">Updated Dataverse solution</span></span>

<span data-ttu-id="c2c42-132">Une nouvelle solution Dataverse sera bientôt disponible avec les modifications suivantes :</span><span class="sxs-lookup"><span data-stu-id="c2c42-132">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="c2c42-133">Description</span><span class="sxs-lookup"><span data-stu-id="c2c42-133">Description</span></span> | <span data-ttu-id="c2c42-134">Monnaie</span><span class="sxs-lookup"><span data-stu-id="c2c42-134">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="c2c42-135">Modifications de l’entité **Poste**</span><span class="sxs-lookup"><span data-stu-id="c2c42-135">**Job/Position** entity changes</span></span> | <span data-ttu-id="c2c42-136">**Région de rémunération** ajoutée</span><span class="sxs-lookup"><span data-stu-id="c2c42-136">**Compensation region** added</span></span></br><span data-ttu-id="c2c42-137">**Dimensions financières** ajoutées</span><span class="sxs-lookup"><span data-stu-id="c2c42-137">**Financial dimensions** added</span></span> |
| <span data-ttu-id="c2c42-138">Modifications de l’entité **Collaborateur**</span><span class="sxs-lookup"><span data-stu-id="c2c42-138">**Worker** entity changes</span></span> | <span data-ttu-id="c2c42-139">**Séquence de noms** ajoutée</span><span class="sxs-lookup"><span data-stu-id="c2c42-139">**Name sequence** added</span></span></br><span data-ttu-id="c2c42-140">**Télétravaille** ajouté</span><span class="sxs-lookup"><span data-stu-id="c2c42-140">**Works from home** added</span></span></br><span data-ttu-id="c2c42-141">**Langue** ajoutée</span><span class="sxs-lookup"><span data-stu-id="c2c42-141">**Language** added</span></span></br><span data-ttu-id="c2c42-142">**Date d’ancienneté** ajoutée</span><span class="sxs-lookup"><span data-stu-id="c2c42-142">**Seniority date** added</span></span></br><span data-ttu-id="c2c42-143">**Date anniversaire** ajoutée</span><span class="sxs-lookup"><span data-stu-id="c2c42-143">**Anniversary date** added</span></span></br><span data-ttu-id="c2c42-144">**Date d’embauche d’origine** ajoutée</span><span class="sxs-lookup"><span data-stu-id="c2c42-144">**Original hire date** added</span></span> |
| <span data-ttu-id="c2c42-145">Modifications de l’entité **Emploi**</span><span class="sxs-lookup"><span data-stu-id="c2c42-145">**Employment** entity changes</span></span> | <span data-ttu-id="c2c42-146">**Dimensions financières** ajoutées</span><span class="sxs-lookup"><span data-stu-id="c2c42-146">**Financial dimensions** added</span></span></br><span data-ttu-id="c2c42-147">**Motif de la fin du contrat** ajouté</span><span class="sxs-lookup"><span data-stu-id="c2c42-147">**Termination reason** added</span></span></br><span data-ttu-id="c2c42-148">**Date de résiliation** renommée à partir de **Date de transition**</span><span class="sxs-lookup"><span data-stu-id="c2c42-148">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="c2c42-149">**Période d’essai** ajoutée</span><span class="sxs-lookup"><span data-stu-id="c2c42-149">**Probation date** added</span></span> |
| <span data-ttu-id="c2c42-150">Modifications de l’entité **Adresse du collaborateur**</span><span class="sxs-lookup"><span data-stu-id="c2c42-150">**Worker address** entity changes</span></span> | <span data-ttu-id="c2c42-151">**Nom de la rue** ajouté</span><span class="sxs-lookup"><span data-stu-id="c2c42-151">**Street address** added</span></span></br><span data-ttu-id="c2c42-152">**Ligne d’adresse 1**, **Ligne d’adresse 2** et **Ligne d’adresse 3** marquées pour suppression</span><span class="sxs-lookup"><span data-stu-id="c2c42-152">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="c2c42-153">Nouvelles entités de configuration de la rémunération variable</span><span class="sxs-lookup"><span data-stu-id="c2c42-153">New variable compensation setup entities</span></span> | <span data-ttu-id="c2c42-154">**Type de régime variable de rémunération**</span><span class="sxs-lookup"><span data-stu-id="c2c42-154">**Compensation variable plan type**</span></span></br><span data-ttu-id="c2c42-155">**Régime variable de rémunération**</span><span class="sxs-lookup"><span data-stu-id="c2c42-155">**Compensation variable plan**</span></span></br><span data-ttu-id="c2c42-156">**Règles d’acquisition**</span><span class="sxs-lookup"><span data-stu-id="c2c42-156">**Vesting rules**</span></span></br><span data-ttu-id="c2c42-157">**Niveau de régime variable de rémunération**</span><span class="sxs-lookup"><span data-stu-id="c2c42-157">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="c2c42-158">Nouvelle entité **Emploi du calendrier du collaborateur**</span><span class="sxs-lookup"><span data-stu-id="c2c42-158">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="c2c42-159">**Entité de calendrier de travail** ajoutée</span><span class="sxs-lookup"><span data-stu-id="c2c42-159">**Work calendar entity** added</span></span> |
| <span data-ttu-id="c2c42-160">Nouvelle entité **Détails du poste de paie**</span><span class="sxs-lookup"><span data-stu-id="c2c42-160">New **Payroll position detail** entity</span></span> | <span data-ttu-id="c2c42-161">**Détails du poste de paie** ajoutés</span><span class="sxs-lookup"><span data-stu-id="c2c42-161">**Payroll position detail** added</span></span> |
| <span data-ttu-id="c2c42-162">Nouvelle entité **Titre**</span><span class="sxs-lookup"><span data-stu-id="c2c42-162">New **Title** entity</span></span> | <span data-ttu-id="c2c42-163">**Titre** ajouté.</span><span class="sxs-lookup"><span data-stu-id="c2c42-163">**Title** added.</span></span> <span data-ttu-id="c2c42-164">La nouvelle entité **Titre** sera incluse dans le processus de synchronisation entre Human Resources et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c2c42-164">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="c2c42-165">Elle ne sera pas référencée initialement à partir des entités **Poste** ou **Tâche**.</span><span class="sxs-lookup"><span data-stu-id="c2c42-165">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

<span data-ttu-id="c2c42-166">Au cours des prochaines semaines, ces modifications d’entités seront disponibles dans tous les environnements.</span><span class="sxs-lookup"><span data-stu-id="c2c42-166">Over the next few weeks, these entity changes will be available in all environments.</span></span> <span data-ttu-id="c2c42-167">Pour installer manuellement la dernière solution Dataverse pour les ressources humaines :</span><span class="sxs-lookup"><span data-stu-id="c2c42-167">To manually install the latest Dataverse solution for Human Resources:</span></span>

1.  <span data-ttu-id="c2c42-168">Accédez au [Centre d’administration Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c2c42-168">Go to the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com).</span></span>

2.  <span data-ttu-id="c2c42-169">Sélectionner **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="c2c42-169">Select **Environments**.</span></span>

3.  <span data-ttu-id="c2c42-170">Recherchez l’environnement que vous souhaitez mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="c2c42-170">Find the environment you want to upgrade.</span></span> <span data-ttu-id="c2c42-171">Celui-ci doit correspondre à **Nom de l’environnement** dans la section **Informations relatives à Common Data Service** dans le formulaire **À propos de** dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c2c42-171">This should correspond to **Environment name** in the **Common Data Service information** section in the **About** form in Human Resources.</span></span>

4.  <span data-ttu-id="c2c42-172">Sélectionnez l’environnement pour afficher les détails de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="c2c42-172">Select the environment to view the environment details.</span></span>

5.  <span data-ttu-id="c2c42-173">Dans la barre d’action située en haut, sélectionnez **Gérer les solutions**.</span><span class="sxs-lookup"><span data-stu-id="c2c42-173">In the action bar at the top, select **Manage Solutions**.</span></span> <span data-ttu-id="c2c42-174">Une nouvelle fenêtre de navigateur s’ouvrira et accédera au **Centre d’administration Dynamics 365** dans le contexte de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="c2c42-174">A new browser window will open and navigate to **Dynamics 365 Administration Center** in the context of your environment.</span></span>

6.  <span data-ttu-id="c2c42-175">Dans la liste **Solution**, sélectionnez **Ancre Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="c2c42-175">In the **Solution** list, select **Dynamics 365 Human Resources Anchor**.</span></span>

7.  <span data-ttu-id="c2c42-176">Sélectionnez **Mettre à niveau** pour appliquer la dernière solution.</span><span class="sxs-lookup"><span data-stu-id="c2c42-176">Select **Upgrade** to apply the latest solution.</span></span>

## <a name="in-preview"></a><span data-ttu-id="c2c42-177">En mode aperçu</span><span class="sxs-lookup"><span data-stu-id="c2c42-177">In preview</span></span>

<span data-ttu-id="c2c42-178">Les fonctionnalités d’aperçu suivantes sont disponibles depuis le 3 février 2020 :</span><span class="sxs-lookup"><span data-stu-id="c2c42-178">The following preview features became available on February 3, 2020:</span></span>

- <span data-ttu-id="c2c42-179">**Fonctionnalités d’aperçu de congé et d’absence** - Pour plus d’informations, voir [Fonctionnalités d’aperçu de congé et absence](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span><span class="sxs-lookup"><span data-stu-id="c2c42-179">**Leave and absence preview features** - For more information, see [Leave and absence preview features](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span></span>

- <span data-ttu-id="c2c42-180">**Fonction d’aperçu de la gestion des avantages** - Pour plus d’informations, y compris les problèmes connus, voir [Aperçu de la gestion des avantages](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c2c42-180">**Benefits management preview feature** - For more information, including known issues, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c2c42-181">Voir également :</span><span class="sxs-lookup"><span data-stu-id="c2c42-181">See also</span></span>

[<span data-ttu-id="c2c42-182">Nouveautés ou modifications dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="c2c42-182">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="c2c42-183">Présentation de Dynamics 365 Human Resources 2019 vague de publication 2</span><span class="sxs-lookup"><span data-stu-id="c2c42-183">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="c2c42-184">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="c2c42-184">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="c2c42-185">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="c2c42-185">Manage features</span></span>](hr-admin-manage-features.md)