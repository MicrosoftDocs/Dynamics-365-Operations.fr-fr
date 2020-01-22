---
title: Nouveautés et modifications dans Dynamics 365 Talent (16 avril 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-04-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a37436eb15ee4c561d5d0c15c90e37815cb80860
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897923"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-16-2019"></a><span data-ttu-id="4c135-103">Nouveautés et modifications dans Dynamics 365 Talent (16 avril 2019)</span><span class="sxs-lookup"><span data-stu-id="4c135-103">What's new or changed in Dynamics 365 Talent (April 16, 2019)</span></span>

<span data-ttu-id="4c135-104">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="4c135-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="4c135-105">Modifications apportées dans Attract</span><span class="sxs-lookup"><span data-stu-id="4c135-105">Changes in Attract</span></span>

### <a name="process-auditing"></a><span data-ttu-id="4c135-106">Audit de processus</span><span class="sxs-lookup"><span data-stu-id="4c135-106">Process auditing</span></span>

<span data-ttu-id="4c135-107">Vous pouvez désormais suivre les modifications apportées aux candidats, aux postes à pourvoir et aux candidatures à un poste.</span><span class="sxs-lookup"><span data-stu-id="4c135-107">You can now track the changes made to candidates, job openings, and job applications.</span></span> <span data-ttu-id="4c135-108">Pour plus d'informations, voir [Effectuer le suivi des données de recrutement](process-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="4c135-108">For more information, see [Track changes in recruiting data](process-auditing.md).</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="4c135-109">Modifications apportées à Onboard</span><span class="sxs-lookup"><span data-stu-id="4c135-109">Changes in Onboard</span></span>

<span data-ttu-id="4c135-110">Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="4c135-110">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="4c135-111">Modifications apportées à Core HR</span><span class="sxs-lookup"><span data-stu-id="4c135-111">Changes in Core HR</span></span>

<span data-ttu-id="4c135-112">Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2239.</span><span class="sxs-lookup"><span data-stu-id="4c135-112">Changes described in this section apply to build number 8.1.2239.</span></span> <span data-ttu-id="4c135-113">Les numéros entre parenthèses se rapportent aux numéros de support dans Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4c135-113">Numbers in parentheses refer to support numbers in Lifecycle Services (LCS).</span></span>

### <a name="compensation-region-compensation-level-benefit-option-and-skill-type-entities-in-common-data-service-updated-to-include-customer-field-support"></a><span data-ttu-id="4c135-114">Les entités Région de rémunération, Niveau de rémunération, Option d'avantage et Type de compétence dans Common Data Service ont été mis à jour pour inclure la prise en charge des champs client</span><span class="sxs-lookup"><span data-stu-id="4c135-114">Compensation region, Compensation level, Benefit option and Skill type entities in Common Data Service updated to include customer field support</span></span>

<span data-ttu-id="4c135-115">Avec cette version, ces entités Common Data Service ont été mises à jour pour comprendre la possibilité d'inclure un champ personnalisé ajouté via Talent : Core HR.</span><span class="sxs-lookup"><span data-stu-id="4c135-115">With this release, these Common Data Service entities have been updated to include the ability to include custom field added through Talent: Core HR.</span></span>

### <a name="new-common-data-service-entity-support-for-compensation-vesting-rules-compensation-variable-plan-variable-compensation"></a><span data-ttu-id="4c135-116">Nouvelle prise en charge d'entité Common Data Service pour : Règles d'acquisition de la rémunération, Régime variable de rémunération, Rémunération variable</span><span class="sxs-lookup"><span data-stu-id="4c135-116">New Common Data Service entity support for: Compensation vesting rules, Compensation variable plan, Variable compensation</span></span>

<span data-ttu-id="4c135-117">Avec cette version, les entités Règles d'acquisition de la rémunération, Régime variable de rémunération et Rémunération variable ont été ajoutées à Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="4c135-117">With this release, Compensation vesting rules, Compensation variable plan, and Variable compensation entities have been added to Common Data Service.</span></span> <span data-ttu-id="4c135-118">Ces entités sont également compatibles avec les champs personnalisés ajoutés via Talent : Core HR.</span><span class="sxs-lookup"><span data-stu-id="4c135-118">These entities also support custom fields added through Talent: Core HR.</span></span>

### <a name="powerbi-refresh-issues-314342"></a><span data-ttu-id="4c135-119">Problèmes d'actualisation de PowerBI (314342)</span><span class="sxs-lookup"><span data-stu-id="4c135-119">PowerBI refresh issues (314342)</span></span>

<span data-ttu-id="4c135-120">Cette modification corrige un problème avec les états de PowerBI s'actualisant correctement.</span><span class="sxs-lookup"><span data-stu-id="4c135-120">This change corrects an issue with PowerBI reports refreshing correctly.</span></span>

### <a name="unable-to-click-directly-through-on-transition-tasks-in-employee-self-service-303309"></a><span data-ttu-id="4c135-121">Impossible de cliquer directement sur des tâches de transition dans le libre service des employés (303309)</span><span class="sxs-lookup"><span data-stu-id="4c135-121">Unable to click directly through on transition tasks in employee self-service (303309)</span></span>

<span data-ttu-id="4c135-122">Cette modification permet aux utilisateurs avec le rôle d'employé de sélectionner et de mettre à jour des tâches de transition dans la liste de tâches de Talent.</span><span class="sxs-lookup"><span data-stu-id="4c135-122">This change enables users with the employee role to select and update transition tasks from the Talent to-do list.</span></span>

### <a name="performance-feedback-email-message-updated-309615"></a><span data-ttu-id="4c135-123">Message électronique en rétroaction sur les performances mis à jour (309615)</span><span class="sxs-lookup"><span data-stu-id="4c135-123">Performance feedback email message updated (309615)</span></span>

<span data-ttu-id="4c135-124">Avec cette modification, un message de confirmation s'affiche si le commentaire a bien été envoyé.</span><span class="sxs-lookup"><span data-stu-id="4c135-124">With this change, a confirmation message displays when feedback is successfully submitted.</span></span>

### <a name="missing-tables-in-word-template-308048"></a><span data-ttu-id="4c135-125">Tableaux manquants dans le modèle Word (308048)</span><span class="sxs-lookup"><span data-stu-id="4c135-125">Missing tables in Word template (308048)</span></span>

<span data-ttu-id="4c135-126">Avec cette modification, lors de la création d'un modèle Word avec des informations sur l'employé et ses compétences, seules les compétences de l'employé sélectionné apparaissent dans le document Word.</span><span class="sxs-lookup"><span data-stu-id="4c135-126">With this change, when creating a Word template with employee and skill information, only the skills for the selected employee appear in the Word document.</span></span>

### <a name="when-applying-an-offboarding-checklist-an-error-is-displayed-299877"></a><span data-ttu-id="4c135-127">Lors de l'application d'une liste de contrôle de départ, une erreur est affichée.</span><span class="sxs-lookup"><span data-stu-id="4c135-127">When applying an offboarding checklist an error is displayed.</span></span> <span data-ttu-id="4c135-128">(299877)</span><span class="sxs-lookup"><span data-stu-id="4c135-128">(299877)</span></span>

<span data-ttu-id="4c135-129">Cette modification corrige un problème lors de l'application d'une liste de contrôle de départ directement à partir de l'écran Collaborateur.</span><span class="sxs-lookup"><span data-stu-id="4c135-129">This change corrects an issue when applying an offboarding checklist directly from the worker form.</span></span>

## <a name="in-preview"></a><span data-ttu-id="4c135-130">En mode aperçu</span><span class="sxs-lookup"><span data-stu-id="4c135-130">In preview</span></span>

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a><span data-ttu-id="4c135-131">Autoriser les codes motif à être spécifiés sur les types de départ</span><span class="sxs-lookup"><span data-stu-id="4c135-131">Allow reason codes to be specified on leave types</span></span>

<span data-ttu-id="4c135-132">Les organisations peuvent avoir besoin d'informations supplémentaire sur les demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="4c135-132">Organizations might need additional information about time-off requests.</span></span> <span data-ttu-id="4c135-133">Vous pouvez désormais spécifier les codes motif des types de départ et permettre aux employés de sélectionner un code motif pour leurs demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="4c135-133">You can now specify reason codes for leave types and enable employees to select a reason code on their time-off requests.</span></span>

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a><span data-ttu-id="4c135-134">Codes motif requis pour certains types d'absence dans les demandes de congés</span><span class="sxs-lookup"><span data-stu-id="4c135-134">Require reason codes for certain leave types on time-off requests</span></span>

<span data-ttu-id="4c135-135">Les organisations peuvent exiger des codes motif pour certains types d'absence lorsque les employés envoient une demande de congé.</span><span class="sxs-lookup"><span data-stu-id="4c135-135">Organizations might require reason codes for specific leave types when employees submit time off.</span></span> <span data-ttu-id="4c135-136">Cela peut découler d'une stratégie de la société ou d'exigences réglementaires.</span><span class="sxs-lookup"><span data-stu-id="4c135-136">This might be due to company policy or regulatory requirements.</span></span> <span data-ttu-id="4c135-137">Vous pouvez désormais spécifier les types d'absence qui nécessitent un code motif, et vous pouvez exiger que les employés fournissent un code motif pour le type d'absence dans leurs demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="4c135-137">You can now specify which leave types require a reason code, and you can require employees to provide a reason code for the leave type on their time-off requests.</span></span>

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a><span data-ttu-id="4c135-138">Fournir une liste de transactions de départ et d'absence pour les RH</span><span class="sxs-lookup"><span data-stu-id="4c135-138">Provide leave and absence transaction list for HR</span></span>

<span data-ttu-id="4c135-139">Le suivi des congés des employés et la compréhension du calcul des congés aide non seulement les RH à répondre aux questions des employés, mais assure aussi l'attribution exacte des durées de congé aux employés.</span><span class="sxs-lookup"><span data-stu-id="4c135-139">Tracking employee time off and understanding how time off is calculated not only helps HR answer employee questions, but also ensures accurate time-off awards for employees.</span></span> <span data-ttu-id="4c135-140">Les RH disposent désormais d'une nouvelle vision des transactions (dotations, cumuls, ajustements et demandes) pour voir les causes des soldes.</span><span class="sxs-lookup"><span data-stu-id="4c135-140">HR now has a new view into the transactions (grants, accruals, adjustments, and requests) to see the reasons behind balances.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="4c135-141">Prochainement</span><span class="sxs-lookup"><span data-stu-id="4c135-141">Coming soon</span></span>

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a><span data-ttu-id="4c135-142">Améliorations apportées à l'interface utilisateur pour la vérification des doublons d'employé</span><span class="sxs-lookup"><span data-stu-id="4c135-142">Improvements to the user interface for duplicate employee check</span></span>

<span data-ttu-id="4c135-143">Avec cette modification, les doublons sont détectés au moment de renseigner les champs de nom. Un champ de statut affiche le nombre de doublons trouvés.</span><span class="sxs-lookup"><span data-stu-id="4c135-143">With this change, duplicates are detected as you enter name fields, and a status displays the number of duplicates found.</span></span> <span data-ttu-id="4c135-144">Vous pouvez sélectionner le lien fourni pour ouvrir une nouvelle page pour évaluer s'il convient d'utiliser la correspondance détectée.</span><span class="sxs-lookup"><span data-stu-id="4c135-144">You can select the provided link to open a new page to evaluate whether to use the detected match.</span></span> <span data-ttu-id="4c135-145">Pour éviter d'interrompre la saisie des données, l'écran des doublons ne s'ouvre pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="4c135-145">To avoid interrupting data entry, the duplicates form doesn't automatically open.</span></span>

### <a name="email-support-for-alerts"></a><span data-ttu-id="4c135-146">Prise en charge des alertes par e-mail</span><span class="sxs-lookup"><span data-stu-id="4c135-146">Email support for alerts</span></span>

<span data-ttu-id="4c135-147">Dans Platform Update 25 pour Finance and Operations, les utilisateurs peuvent créer des règles d'alerte qui envoient automatiquement des notifications par e-mail aux contacts lorsque des notifications sont déclenchées par un événement.</span><span class="sxs-lookup"><span data-stu-id="4c135-147">With Platform update 25 for Finance and Operations, users can create alert rules that automatically send email notifications to contacts when triggered by an event.</span></span>


