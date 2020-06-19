---
title: Processus d'éligibilité à l'inscription
description: Cet article explique comment exécuter le processus d'éligibilité à l'inscription.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dfb7f13dce48f33c111af491918702763f7e3b8a
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429287"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="0bee6-103">Processus d'éligibilité à l'inscription</span><span class="sxs-lookup"><span data-stu-id="0bee6-103">Process enrollment eligibility</span></span>

<span data-ttu-id="0bee6-104">Cet article explique comment exécuter le processus d'éligibilité à l'inscription.</span><span class="sxs-lookup"><span data-stu-id="0bee6-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="0bee6-105">Dans l'espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Processus d'éligibilité à l'inscription**.</span><span class="sxs-lookup"><span data-stu-id="0bee6-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="0bee6-106">Dans la boîte de dialogue **Exécuter le processus d'éligibilité à l'inscription aux avantages**, spécifiez des valeurs pour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="0bee6-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="0bee6-107">Champ</span><span class="sxs-lookup"><span data-stu-id="0bee6-107">Field</span></span> | <span data-ttu-id="0bee6-108">Description</span><span class="sxs-lookup"><span data-stu-id="0bee6-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="0bee6-109">**Période d'inscription**</span><span class="sxs-lookup"><span data-stu-id="0bee6-109">**Enrollment period**</span></span> | <span data-ttu-id="0bee6-110">La période d'inscription pour traiter l'éligibilité.</span><span class="sxs-lookup"><span data-stu-id="0bee6-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="0bee6-111">**Entité juridique**</span><span class="sxs-lookup"><span data-stu-id="0bee6-111">**Legal entity**</span></span> | <span data-ttu-id="0bee6-112">L'entité juridique pour laquelle traiter l'éligibilité.</span><span class="sxs-lookup"><span data-stu-id="0bee6-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="0bee6-113">**Collaborateur**</span><span class="sxs-lookup"><span data-stu-id="0bee6-113">**Worker**</span></span> | <span data-ttu-id="0bee6-114">Le collaborateur pour lequel traiter l'éligibilité.</span><span class="sxs-lookup"><span data-stu-id="0bee6-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="0bee6-115">Si vous laissez ce champ vide, l'éligibilité à l'inscription sera traitée pour tous les collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="0bee6-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="0bee6-116">**Plan d'avantage**</span><span class="sxs-lookup"><span data-stu-id="0bee6-116">**Benefit plan**</span></span> | <span data-ttu-id="0bee6-117">Le plan d'avantages pour lequel traiter l'éligibilité.</span><span class="sxs-lookup"><span data-stu-id="0bee6-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="0bee6-118">Si vous souhaitez exécuter le processus en arrière-plan, sélectionnez **Exécuter à l'arrière-plan** et effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="0bee6-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="0bee6-119">Entrez les informations pour le processus.</span><span class="sxs-lookup"><span data-stu-id="0bee6-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="0bee6-120">Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bee6-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="0bee6-121">Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bee6-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="0bee6-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bee6-122">Select **OK**.</span></span> <span data-ttu-id="0bee6-123">Le processus s'exécutera avec les paramètres que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="0bee6-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="0bee6-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bee6-124">Select **OK**.</span></span>

## <a name="view-process-results"></a><span data-ttu-id="0bee6-125">Afficher les résultats du processus</span><span class="sxs-lookup"><span data-stu-id="0bee6-125">View Process Results</span></span>

<span data-ttu-id="0bee6-126">Cet article explique comment afficher les résultats du processus d'éligibilité.</span><span class="sxs-lookup"><span data-stu-id="0bee6-126">This article explains how to view eligibility process results.</span></span>

1.  <span data-ttu-id="0bee6-127">Dans l'espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Résultats du processus**.</span><span class="sxs-lookup"><span data-stu-id="0bee6-127">In the **Benefits management** workspace, under **Processing**, select **Process results**.</span></span>

2.  <span data-ttu-id="0bee6-128">Dans le formulaire **Résultats du processus**, les champs suivants sont spécifiés :</span><span class="sxs-lookup"><span data-stu-id="0bee6-128">In the **Process results** form, the following fields are specified:</span></span>

   | <span data-ttu-id="0bee6-129">Champ</span><span class="sxs-lookup"><span data-stu-id="0bee6-129">Field</span></span> | <span data-ttu-id="0bee6-130">Description</span><span class="sxs-lookup"><span data-stu-id="0bee6-130">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="0bee6-131">**ID processus**</span><span class="sxs-lookup"><span data-stu-id="0bee6-131">**Process ID**</span></span> | <span data-ttu-id="0bee6-132">ID unique pour la combinaison de Collaborateur, Entité juridique et exécution de processus.</span><span class="sxs-lookup"><span data-stu-id="0bee6-132">The unique ID for the combination of Worker, Legal entity, and process run.</span></span> |
   | <span data-ttu-id="0bee6-133">**Type de processus**</span><span class="sxs-lookup"><span data-stu-id="0bee6-133">**Process type**</span></span> | <span data-ttu-id="0bee6-134">Cela identifie le processus qui a été exécuté.</span><span class="sxs-lookup"><span data-stu-id="0bee6-134">This identifies the process that was run.</span></span> <span data-ttu-id="0bee6-135">Par exemple : Inscription.</span><span class="sxs-lookup"><span data-stu-id="0bee6-135">For example:  Enrollment.</span></span> |
   | <span data-ttu-id="0bee6-136">**Horodatage**</span><span class="sxs-lookup"><span data-stu-id="0bee6-136">**Time stamp**</span></span> | <span data-ttu-id="0bee6-137">Heure à laquelle le processus d'éligibilité a été exécuté.</span><span class="sxs-lookup"><span data-stu-id="0bee6-137">The time that the eligibility process was run.</span></span> |
   | <span data-ttu-id="0bee6-138">**Entité juridique**</span><span class="sxs-lookup"><span data-stu-id="0bee6-138">**Legal entity**</span></span> | <span data-ttu-id="0bee6-139">L'entité juridique spécifiée lors du processus d'inscription.</span><span class="sxs-lookup"><span data-stu-id="0bee6-139">The legal entity specified during the enrollment process.</span></span> |
   | <span data-ttu-id="0bee6-140">**Collaborateur**</span><span class="sxs-lookup"><span data-stu-id="0bee6-140">**Worker**</span></span> | <span data-ttu-id="0bee6-141">Collaborateur ayant été traité.</span><span class="sxs-lookup"><span data-stu-id="0bee6-141">The worker who was processed.</span></span> |
   | <span data-ttu-id="0bee6-142">\*\*Plan</span><span class="sxs-lookup"><span data-stu-id="0bee6-142">\*\*Plan</span></span> | <span data-ttu-id="0bee6-143">Le plan d'avantages pour lequel l'inscription a été tentée.</span><span class="sxs-lookup"><span data-stu-id="0bee6-143">The Benefit plan that enrollment was attempted for.</span></span> |
   | <span data-ttu-id="0bee6-144">**Règle d'éligibilité**</span><span class="sxs-lookup"><span data-stu-id="0bee6-144">**Eligibility rule**</span></span> | <span data-ttu-id="0bee6-145">La règle d'éligibilité qui a été traitée.</span><span class="sxs-lookup"><span data-stu-id="0bee6-145">The eligibility rule that was processed.</span></span> <span data-ttu-id="0bee6-146">Si une erreur s'est produite avant l'exécution de l'éligibilité, elle sera vide.</span><span class="sxs-lookup"><span data-stu-id="0bee6-146">If an error was encountered before eligibility was run, this will be blank.</span></span> <span data-ttu-id="0bee6-147">Par exemple : si la rémunération n'a pas été définie pour un collaborateur, le processus d'éligibilité ne s'exécutera pas et ce champ sera laissé vide.</span><span class="sxs-lookup"><span data-stu-id="0bee6-147">For example: If compensation hasn't been defined for a worker, the eligibility process won't run, and this field will be left blank.</span></span> |
   | <span data-ttu-id="0bee6-148">**Statut du résultat**</span><span class="sxs-lookup"><span data-stu-id="0bee6-148">**Result status**</span></span> | <span data-ttu-id="0bee6-149">Il s'agit du statut Éligible ou Inéligible.</span><span class="sxs-lookup"><span data-stu-id="0bee6-149">This will be Eligible or Ineligible.</span></span> <span data-ttu-id="0bee6-150">Le statut du résultat est défini sur Ineligible si le collaborateur n'a pas répondu aux critères de règle d'éligibilité, si le collaborateur n'a pas les informations requises comme la fréquence de paiement ou la rémunération fixe, ou si des informations manquent sur le plan d'avantages qui empêche l'inscription des collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="0bee6-150">The result status will be Ineligible if the worker didn’t meet the eligibility rule criteria, if the worker is missing required information such as a pay frequency or fixed compensation, or if there is information missing on the benefit plan that prevents workers from being enrolled.</span></span> |
   | <span data-ttu-id="0bee6-151">**Message de résultat**</span><span class="sxs-lookup"><span data-stu-id="0bee6-151">**Result message**</span></span> | <span data-ttu-id="0bee6-152">Indique pourquoi un collaborateur n'est pas admissible à un régime d'avantages sociaux ou si la règle d'admissibilité a été adoptée.</span><span class="sxs-lookup"><span data-stu-id="0bee6-152">Indicates why a worker is ineligible for a benefit plan or if the eligibility rule passed.</span></span> |

