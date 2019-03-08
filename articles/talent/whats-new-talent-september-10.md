---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (10 septembre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.openlocfilehash: b41ce93c8ae93054d2b0d71340b99e0910d4510f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304420"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-september-10-2018"></a><span data-ttu-id="35856-103">Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (10 septembre 2018)</span><span class="sxs-lookup"><span data-stu-id="35856-103">What's new or changed in Dynamics 365 for Talent Core HR (September 10, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="35856-104">**Version 8.1.138.0**</span><span class="sxs-lookup"><span data-stu-id="35856-104">**Build 8.1.138.0**</span></span>

<span data-ttu-id="35856-105">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.</span><span class="sxs-lookup"><span data-stu-id="35856-105">This topic describes features that are either new or changed in Microsoft Dynamics 365 for Talent Core HR.</span></span>

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a><span data-ttu-id="35856-106">Indiquer un moment spécifique de la journée dans les demandes de congés (demi-journées)</span><span class="sxs-lookup"><span data-stu-id="35856-106">Allow specific time of day on time-off requests (half days)</span></span>

<span data-ttu-id="35856-107">Si le plan de congé et d'absence est paramétré pour que les congés soient soumis en jours, vous pouvez maintenant activer une définition d'une demi-journée.</span><span class="sxs-lookup"><span data-stu-id="35856-107">If leave and absence is set up so that time off is submitted in days, you can now also enable a half-day definition.</span></span> <span data-ttu-id="35856-108">Ensuite, lorsque les utilisateurs soumettent des demandes de congés, ils peuvent spécifier s'ils souhaitent prendre la matinée ou l'après-midi.</span><span class="sxs-lookup"><span data-stu-id="35856-108">Then, when users submit time-off requests, they can specify whether they are requesting the first half or the second half of the day off.</span></span>

<span data-ttu-id="35856-109">Par défaut, cette option est désactivée.</span><span class="sxs-lookup"><span data-stu-id="35856-109">By default, this option is turned off.</span></span> <span data-ttu-id="35856-110">Pour permettre aux employés de demander une matinée ou une après-midi de congé, vous devez activer cette option dans la zone **Congé et absence** des paramètres des ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="35856-110">For employees to request the first half or second half of the day off, you must turn on this option in the **Leave and absence** area of Human resources parameters.</span></span>

<span data-ttu-id="35856-111">Le privilège de sécurité pour cette fonction est Tenir à jour les paramètres de ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="35856-111">The security privilege for this feature is Maintain Human Resources Parameters.</span></span>

## <a name="validation-of-leave-and-absence-entries"></a><span data-ttu-id="35856-112">Validation des entrées de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="35856-112">Validation of leave and absence entries</span></span>

<span data-ttu-id="35856-113">Selon la manière dont les congés sont configurés, les employés qui essaient de soumettre une demande de congés d'une durée plus longue que leur journée de travail reçoivent un message d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="35856-113">Depending on how leave is configured, employees who try to submit a time-off request that is longer than their work day receive a warning message.</span></span> <span data-ttu-id="35856-114">Autrement dit, un avertissement leur est envoyé s'ils essaient de prendre plus qu'une journée entière à une date donnée.</span><span class="sxs-lookup"><span data-stu-id="35856-114">In other words, they are warned if they try to take more than a full day off on any given date.</span></span>

<span data-ttu-id="35856-115">Cette validaton est toujours activée.</span><span class="sxs-lookup"><span data-stu-id="35856-115">This validation is always turned on.</span></span> <span data-ttu-id="35856-116">Chaque fois que les employés dépassent le seuil de jours défini, ils reçoivent un avertissement dans leur demande de congés.</span><span class="sxs-lookup"><span data-stu-id="35856-116">Any time that employees exceed the day threshold that is defined, they receive a warning in their time-off request.</span></span>

## <a name="additional-fields-for-conditional-statements-in-workflows"></a><span data-ttu-id="35856-117">Champs supplémentaires des instructions conditionnelles des workflows</span><span class="sxs-lookup"><span data-stu-id="35856-117">Additional fields for conditional statements in workflows</span></span>

<span data-ttu-id="35856-118">Des champs supplémentaires ont été ajoutés aux instructions conditionnelles et aux espaces réservés pour plusieurs workflows dans Core HR.</span><span class="sxs-lookup"><span data-stu-id="35856-118">Additional fields have been added to conditional statements and placeholders for several workflows in Core HR.</span></span>

<span data-ttu-id="35856-119">Les champs suivants ont été ajoutés aux workflows de rémunération, de résiliation et de transfert :</span><span class="sxs-lookup"><span data-stu-id="35856-119">The following fields have been added to the compensation, termination, and transfer workflows:</span></span>

- <span data-ttu-id="35856-120">EmploymentType</span><span class="sxs-lookup"><span data-stu-id="35856-120">EmploymentType</span></span>
- <span data-ttu-id="35856-121">LegalEntity</span><span class="sxs-lookup"><span data-stu-id="35856-121">LegalEntity</span></span>
- <span data-ttu-id="35856-122">AdjustedWorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="35856-122">AdjustedWorkerStartDate</span></span>
- <span data-ttu-id="35856-123">EmployerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="35856-123">EmployerNoticeAmount</span></span>
- <span data-ttu-id="35856-124">EmployerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="35856-124">EmployerUnitOfNotice</span></span>
- <span data-ttu-id="35856-125">TransitionDate</span><span class="sxs-lookup"><span data-stu-id="35856-125">TransitionDate</span></span>
- <span data-ttu-id="35856-126">WorkerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="35856-126">WorkerNoticeAmount</span></span>
- <span data-ttu-id="35856-127">WorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="35856-127">WorkerStartDate</span></span>
- <span data-ttu-id="35856-128">WorkerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="35856-128">WorkerUnitOfNotice</span></span>
- <span data-ttu-id="35856-129">ProbationEndDate</span><span class="sxs-lookup"><span data-stu-id="35856-129">ProbationEndDate</span></span>
- <span data-ttu-id="35856-130">Poste</span><span class="sxs-lookup"><span data-stu-id="35856-130">Position</span></span>
- <span data-ttu-id="35856-131">Union</span><span class="sxs-lookup"><span data-stu-id="35856-131">Union</span></span>
- <span data-ttu-id="35856-132">Département</span><span class="sxs-lookup"><span data-stu-id="35856-132">Department</span></span>
- <span data-ttu-id="35856-133">PositionType</span><span class="sxs-lookup"><span data-stu-id="35856-133">PositionType</span></span>
- <span data-ttu-id="35856-134">CompLocation</span><span class="sxs-lookup"><span data-stu-id="35856-134">CompLocation</span></span>
- <span data-ttu-id="35856-135">Fonction</span><span class="sxs-lookup"><span data-stu-id="35856-135">Title</span></span>
- <span data-ttu-id="35856-136">Poste</span><span class="sxs-lookup"><span data-stu-id="35856-136">Job</span></span>
- <span data-ttu-id="35856-137">JobType</span><span class="sxs-lookup"><span data-stu-id="35856-137">JobType</span></span>
- <span data-ttu-id="35856-138">JobFamily</span><span class="sxs-lookup"><span data-stu-id="35856-138">JobFamily</span></span>
- <span data-ttu-id="35856-139">JobFunction</span><span class="sxs-lookup"><span data-stu-id="35856-139">JobFunction</span></span>

<span data-ttu-id="35856-140">Les champs suivants ont été ajoutés au workflow de position :</span><span class="sxs-lookup"><span data-stu-id="35856-140">The following fields have been added to the position workflow:</span></span>

- <span data-ttu-id="35856-141">Poste</span><span class="sxs-lookup"><span data-stu-id="35856-141">Position</span></span>
- <span data-ttu-id="35856-142">Union</span><span class="sxs-lookup"><span data-stu-id="35856-142">Union</span></span>
- <span data-ttu-id="35856-143">Département</span><span class="sxs-lookup"><span data-stu-id="35856-143">Department</span></span>
- <span data-ttu-id="35856-144">PositionType</span><span class="sxs-lookup"><span data-stu-id="35856-144">PositionType</span></span>
- <span data-ttu-id="35856-145">CompLocation</span><span class="sxs-lookup"><span data-stu-id="35856-145">CompLocation</span></span>
- <span data-ttu-id="35856-146">Fonction</span><span class="sxs-lookup"><span data-stu-id="35856-146">Title</span></span>
- <span data-ttu-id="35856-147">Poste</span><span class="sxs-lookup"><span data-stu-id="35856-147">Job</span></span>
- <span data-ttu-id="35856-148">JobType</span><span class="sxs-lookup"><span data-stu-id="35856-148">JobType</span></span>
- <span data-ttu-id="35856-149">JobFamily</span><span class="sxs-lookup"><span data-stu-id="35856-149">JobFamily</span></span>
- <span data-ttu-id="35856-150">JobFunction</span><span class="sxs-lookup"><span data-stu-id="35856-150">JobFunction</span></span>

<span data-ttu-id="35856-151">Les champs des instructions conditionnelles et des espaces réservés sont disponibles pour tous les utilisateurs qui disposent d'un accès pour configurer les workflows précédemment mentionnés.</span><span class="sxs-lookup"><span data-stu-id="35856-151">Fields in conditional statements and placeholders are available to all users who have access to configure the previously mentioned workflows.</span></span>

## <a name="navigation-to-attract-from-personnel-management"></a><span data-ttu-id="35856-152">Accès à Attract à partir du module Gestion du personnel</span><span class="sxs-lookup"><span data-stu-id="35856-152">Navigation to Attract from personnel management</span></span>

<span data-ttu-id="35856-153">Dans le module Gestion du personnel, si Attract n'a pas été paramétré, la section **Candidats à l'embauche** redirige les utilisateurs vers la page de mise en route d'Attract au lieu d'afficher le message « Nous n'avons rien trouvé à afficher ici ».</span><span class="sxs-lookup"><span data-stu-id="35856-153">In personnel management, if Attract hasn't been set up, the **Candidates to hire** section directs users to get started with Attract instead of showing the message, "We didn't find anything to show here."</span></span>

## <a name="other-changes"></a><span data-ttu-id="35856-154">Autres modifications</span><span class="sxs-lookup"><span data-stu-id="35856-154">Other changes</span></span>

<span data-ttu-id="35856-155">Cette version contient plusieurs correctifs de bogue supplémentaires :</span><span class="sxs-lookup"><span data-stu-id="35856-155">This release includes several additional bug fixes:</span></span>

- <span data-ttu-id="35856-156">Lorsqu'un fournisseur est embauché, l'onglet **Rémunération** ne doit pas être disponible dans la page de demande/d'action.</span><span class="sxs-lookup"><span data-stu-id="35856-156">When a contractor is hired, the **Compensation** tab should not be available on the request/action page.</span></span>
- <span data-ttu-id="35856-157">Au cours du processus de résiliation de la demande, vous ne pouvez pas continuer tant que tous les champs obligatoires ne contiennent pas des données.</span><span class="sxs-lookup"><span data-stu-id="35856-157">During the request termination process, you can't continue until all required fields contain data.</span></span>
- <span data-ttu-id="35856-158">Les problèmes d'ordre de tri et d'affichage de la date dans le module Analyse de la gestion du personnel ont été résolus.</span><span class="sxs-lookup"><span data-stu-id="35856-158">Sort order and date display issues on the Personnel management analytics have been addressed.</span></span>
