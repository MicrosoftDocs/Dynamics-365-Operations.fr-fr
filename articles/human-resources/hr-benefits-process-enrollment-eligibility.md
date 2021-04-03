---
title: Processus d’éligibilité à l’inscription
description: Cet article explique comment exécuter le processus d’éligibilité à l’inscription.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: 25699d643b3e74fe7118884457ab17314d1f9132
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466300"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="c05ff-103">Processus d’éligibilité à l’inscription</span><span class="sxs-lookup"><span data-stu-id="c05ff-103">Process enrollment eligibility</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="c05ff-104">Cet article explique comment exécuter le processus d’éligibilité à l’inscription.</span><span class="sxs-lookup"><span data-stu-id="c05ff-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="c05ff-105">Dans l’espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Processus d’éligibilité à l’inscription**.</span><span class="sxs-lookup"><span data-stu-id="c05ff-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="c05ff-106">Dans la boîte de dialogue **Exécuter le processus d’éligibilité à l’inscription aux avantages**, spécifiez des valeurs pour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="c05ff-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="c05ff-107">Champ</span><span class="sxs-lookup"><span data-stu-id="c05ff-107">Field</span></span> | <span data-ttu-id="c05ff-108">Description</span><span class="sxs-lookup"><span data-stu-id="c05ff-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="c05ff-109">**Période d’inscription**</span><span class="sxs-lookup"><span data-stu-id="c05ff-109">**Enrollment period**</span></span> | <span data-ttu-id="c05ff-110">La période d’inscription pour traiter l’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="c05ff-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="c05ff-111">**Entité juridique**</span><span class="sxs-lookup"><span data-stu-id="c05ff-111">**Legal entity**</span></span> | <span data-ttu-id="c05ff-112">L’entité juridique pour laquelle traiter l’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="c05ff-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="c05ff-113">**Collaborateur**</span><span class="sxs-lookup"><span data-stu-id="c05ff-113">**Worker**</span></span> | <span data-ttu-id="c05ff-114">Le collaborateur pour lequel traiter l’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="c05ff-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="c05ff-115">Si vous laissez ce champ vide, l’éligibilité à l’inscription sera traitée pour tous les collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="c05ff-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="c05ff-116">**Plan d’avantage**</span><span class="sxs-lookup"><span data-stu-id="c05ff-116">**Benefit plan**</span></span> | <span data-ttu-id="c05ff-117">Le régime de prestations pour lequel traiter l’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="c05ff-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="c05ff-118">Si vous souhaitez exécuter le processus en arrière-plan, sélectionnez **Exécuter à l’arrière-plan** et effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="c05ff-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="c05ff-119">Entrez les informations pour le processus.</span><span class="sxs-lookup"><span data-stu-id="c05ff-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="c05ff-120">Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c05ff-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="c05ff-121">Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c05ff-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="c05ff-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c05ff-122">Select **OK**.</span></span> <span data-ttu-id="c05ff-123">Le processus s’exécutera avec les paramètres que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="c05ff-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="c05ff-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c05ff-124">Select **OK**.</span></span>

## <a name="view-process-results"></a><span data-ttu-id="c05ff-125">Afficher les résultats du processus</span><span class="sxs-lookup"><span data-stu-id="c05ff-125">View Process Results</span></span>

<span data-ttu-id="c05ff-126">Cet article explique comment afficher les résultats du processus d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="c05ff-126">This article explains how to view eligibility process results.</span></span>

1.  <span data-ttu-id="c05ff-127">Dans l’espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Résultats du processus**.</span><span class="sxs-lookup"><span data-stu-id="c05ff-127">In the **Benefits management** workspace, under **Processing**, select **Process results**.</span></span>

2.  <span data-ttu-id="c05ff-128">Dans le formulaire **Résultats du processus**, les champs suivants sont spécifiés :</span><span class="sxs-lookup"><span data-stu-id="c05ff-128">In the **Process results** form, the following fields are specified:</span></span>

   | <span data-ttu-id="c05ff-129">Champ</span><span class="sxs-lookup"><span data-stu-id="c05ff-129">Field</span></span> | <span data-ttu-id="c05ff-130">Description</span><span class="sxs-lookup"><span data-stu-id="c05ff-130">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="c05ff-131">**ID processus**</span><span class="sxs-lookup"><span data-stu-id="c05ff-131">**Process ID**</span></span> | <span data-ttu-id="c05ff-132">ID unique pour la combinaison de Collaborateur, Entité juridique et exécution de processus.</span><span class="sxs-lookup"><span data-stu-id="c05ff-132">The unique ID for the combination of Worker, Legal entity, and process run.</span></span> |
   | <span data-ttu-id="c05ff-133">**Type de processus**</span><span class="sxs-lookup"><span data-stu-id="c05ff-133">**Process type**</span></span> | <span data-ttu-id="c05ff-134">Cela identifie le processus qui a été exécuté.</span><span class="sxs-lookup"><span data-stu-id="c05ff-134">This identifies the process that was run.</span></span> <span data-ttu-id="c05ff-135">Par exemple : Inscription.</span><span class="sxs-lookup"><span data-stu-id="c05ff-135">For example:  Enrollment.</span></span> |
   | <span data-ttu-id="c05ff-136">**Horodatage**</span><span class="sxs-lookup"><span data-stu-id="c05ff-136">**Time stamp**</span></span> | <span data-ttu-id="c05ff-137">Heure à laquelle le processus d’éligibilité a été exécuté.</span><span class="sxs-lookup"><span data-stu-id="c05ff-137">The time that the eligibility process was run.</span></span> |
   | <span data-ttu-id="c05ff-138">**Entité juridique**</span><span class="sxs-lookup"><span data-stu-id="c05ff-138">**Legal entity**</span></span> | <span data-ttu-id="c05ff-139">L’entité juridique spécifiée lors du processus d’inscription.</span><span class="sxs-lookup"><span data-stu-id="c05ff-139">The legal entity specified during the enrollment process.</span></span> |
   | <span data-ttu-id="c05ff-140">**Collaborateur**</span><span class="sxs-lookup"><span data-stu-id="c05ff-140">**Worker**</span></span> | <span data-ttu-id="c05ff-141">Collaborateur ayant été traité.</span><span class="sxs-lookup"><span data-stu-id="c05ff-141">The worker who was processed.</span></span> |
   | <span data-ttu-id="c05ff-142">\*\*Plan</span><span class="sxs-lookup"><span data-stu-id="c05ff-142">\*\*Plan</span></span> | <span data-ttu-id="c05ff-143">Le régime de prestations pour lequel l’inscription a été tentée.</span><span class="sxs-lookup"><span data-stu-id="c05ff-143">The Benefit plan that enrollment was attempted for.</span></span> |
   | <span data-ttu-id="c05ff-144">**Règle d’éligibilité**</span><span class="sxs-lookup"><span data-stu-id="c05ff-144">**Eligibility rule**</span></span> | <span data-ttu-id="c05ff-145">La règle d’éligibilité qui a été traitée.</span><span class="sxs-lookup"><span data-stu-id="c05ff-145">The eligibility rule that was processed.</span></span> <span data-ttu-id="c05ff-146">Si une erreur s’est produite avant l’exécution de l’éligibilité, elle sera vide.</span><span class="sxs-lookup"><span data-stu-id="c05ff-146">If an error was encountered before eligibility was run, this will be blank.</span></span> <span data-ttu-id="c05ff-147">Par exemple : si la rémunération n’a pas été définie pour un collaborateur, le processus d’éligibilité ne s’exécutera pas et ce champ sera laissé vide.</span><span class="sxs-lookup"><span data-stu-id="c05ff-147">For example: If compensation hasn't been defined for a worker, the eligibility process won't run, and this field will be left blank.</span></span> |
   | <span data-ttu-id="c05ff-148">**Statut du résultat**</span><span class="sxs-lookup"><span data-stu-id="c05ff-148">**Result status**</span></span> | <span data-ttu-id="c05ff-149">Il s’agit du statut Éligible ou Inéligible.</span><span class="sxs-lookup"><span data-stu-id="c05ff-149">This will be Eligible or Ineligible.</span></span> <span data-ttu-id="c05ff-150">Le statut du résultat est défini sur Ineligible si le collaborateur n’a pas répondu aux critères de règle d’éligibilité, si le collaborateur n’a pas les informations requises comme la fréquence de paiement ou la rémunération fixe, ou si des informations manquent sur le régime de prestations qui empêche l’inscription des collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="c05ff-150">The result status will be Ineligible if the worker didn’t meet the eligibility rule criteria, if the worker is missing required information such as a pay frequency or fixed compensation, or if there is information missing on the benefit plan that prevents workers from being enrolled.</span></span> |
   | <span data-ttu-id="c05ff-151">**Message de résultat**</span><span class="sxs-lookup"><span data-stu-id="c05ff-151">**Result message**</span></span> | <span data-ttu-id="c05ff-152">Indique pourquoi un collaborateur n’est pas admissible à un régime de prestations sociales ou si la règle d’admissibilité a été adoptée.</span><span class="sxs-lookup"><span data-stu-id="c05ff-152">Indicates why a worker is ineligible for a benefit plan or if the eligibility rule passed.</span></span> |



[!INCLUDE[footer-include](../includes/footer-banner.md)]