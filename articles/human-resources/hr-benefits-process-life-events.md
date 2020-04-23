---
title: Traitement des événements de vie
description: Pendant le cycle de vie des employés dans Microsoft Dynamics 365 Human Resources, chaque employé peut rencontrer divers changements d'événement de vie.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ba8d21482a18c6baa93437fc65c165907bdb515d
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229925"
---
# <a name="process-life-events"></a><span data-ttu-id="d8a24-103">Traitement des événements de vie</span><span class="sxs-lookup"><span data-stu-id="d8a24-103">Process life events</span></span>

<span data-ttu-id="d8a24-104">Pendant le cycle de vie des employés dans Microsoft Dynamics 365 Human Resources, chaque employé peut rencontrer divers changements d'événement de vie.</span><span class="sxs-lookup"><span data-stu-id="d8a24-104">During the employee lifecycle in Microsoft Dynamics 365 Human Resources, each employee may encounter various life event changes.</span></span> <span data-ttu-id="d8a24-105">Par exemple, mariage, changement d'emploi ou changement de personne à charge / bénéficiaire.</span><span class="sxs-lookup"><span data-stu-id="d8a24-105">For example, marriage, change in employment, or dependent/beneficiary change.</span></span> <span data-ttu-id="d8a24-106">Pour utiliser des événements de vie, vous devez activer les événements de vie dans l'écran des paramètres d'avantages, configurer les types d'événements de vie et configurer les options d'événements de vie pour les types de plan.</span><span class="sxs-lookup"><span data-stu-id="d8a24-106">To use life events, you must enable life events in the benefits parameters form, set up life event types, and set up life event options for plan types.</span></span>

<span data-ttu-id="d8a24-107">Avant de pouvoir traiter des événements de vie, vous devez avoir déjà exécuté l'inscription ouverte au moins une fois au cours d'une période d'embauche.</span><span class="sxs-lookup"><span data-stu-id="d8a24-107">Before you can process life events, you must have already run open enrollment at least once during a hiring time frame.</span></span> <span data-ttu-id="d8a24-108">Aux États-Unis, l'inscription ouverte est généralement une fois par an.</span><span class="sxs-lookup"><span data-stu-id="d8a24-108">In the United States, open enrollment is typically once per year.</span></span> <span data-ttu-id="d8a24-109">En dehors des États-Unis, l'inscription ouverte peut être exécutée au moment de l'embauche.</span><span class="sxs-lookup"><span data-stu-id="d8a24-109">Outside the United States, open enrollment may be run at the time of hire.</span></span> <span data-ttu-id="d8a24-110">Un collaborateur n'a pas besoin de sélectionner un régime d'avantages pour que les événements de vie soient traités, mais ils doivent avoir été inclus dans le processus d'inscription ouverte.</span><span class="sxs-lookup"><span data-stu-id="d8a24-110">A worker does not need to select a benefit plan in order for life events to be processed, but they need to have been included in open enrollment processing.</span></span> 

<span data-ttu-id="d8a24-111">Utilisez le traitement des événements de vie lorsque vous avez des collaborateurs dont les événements de vie ont lieu à une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d8a24-111">Use life event processing when you have workers who have life events that take place on a future date.</span></span> <span data-ttu-id="d8a24-112">Cet événement traitera tous les événements de vie qui n'ont pas été traités (comme les événements de vie futurs ou les événements de vie ajoutés qui ne sont pas spécifiques à un collaborateur - un exemple est un nouvel avantage).</span><span class="sxs-lookup"><span data-stu-id="d8a24-112">This event will process all life events that have not been processed (like future life events, or life events that have been added that are not specific to any one worker – one example is a new benefit).</span></span> <span data-ttu-id="d8a24-113">Les événements de vie en temps réel sont cachés.</span><span class="sxs-lookup"><span data-stu-id="d8a24-113">Real-time life events are hidden.</span></span>

<span data-ttu-id="d8a24-114">Par exemple, si aujourd'hui est le 1er février et que le 14 février, le collaborateur Joe Smith doit changer d'entité juridique, si vous exécutez le traitement des événements de vie pour le 15 février, le système traite tous les événements jusqu'au 15 février.</span><span class="sxs-lookup"><span data-stu-id="d8a24-114">For example, if today is February 1, and on February 14 worker Joe Smith is scheduled to change legal entities, if you run life event processing for February 15, the system processes all events up until February 15.</span></span> 

1. <span data-ttu-id="d8a24-115">Dans l'espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Traitement des événements de vie**.</span><span class="sxs-lookup"><span data-stu-id="d8a24-115">In the **Benefits management** workspace, under **Processing**, select **Life event processing**.</span></span>

2. <span data-ttu-id="d8a24-116">Dans la boîte de dialogue **Exécuter le processus d'événement de vie**, spécifiez des valeurs pour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="d8a24-116">In the **Run life event process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="d8a24-117">Champ</span><span class="sxs-lookup"><span data-stu-id="d8a24-117">Field</span></span> | <span data-ttu-id="d8a24-118">Description</span><span class="sxs-lookup"><span data-stu-id="d8a24-118">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d8a24-119">**Période d'inscription**</span><span class="sxs-lookup"><span data-stu-id="d8a24-119">**Enrollment period**</span></span> | <span data-ttu-id="d8a24-120">Période d'inscription pour laquelle traiter les événements de vie.</span><span class="sxs-lookup"><span data-stu-id="d8a24-120">The enrollment period to process life events for.</span></span> |
   | <span data-ttu-id="d8a24-121">**Entité juridique**</span><span class="sxs-lookup"><span data-stu-id="d8a24-121">**Legal entity**</span></span> | <span data-ttu-id="d8a24-122">Entité juridique pour laquelle traiter les événements de vie.</span><span class="sxs-lookup"><span data-stu-id="d8a24-122">The legal entity to process life events for.</span></span> |
   | <span data-ttu-id="d8a24-123">**Date de l'événement de vie**</span><span class="sxs-lookup"><span data-stu-id="d8a24-123">**Life event date**</span></span> | <span data-ttu-id="d8a24-124">Le système traite tous les événements de la période d'inscription qui se produisent jusqu'à cette date.</span><span class="sxs-lookup"><span data-stu-id="d8a24-124">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="d8a24-125">**Collaborateur**</span><span class="sxs-lookup"><span data-stu-id="d8a24-125">**Worker**</span></span> | <span data-ttu-id="d8a24-126">Collaborateur pour lequel traiter les événements de vie.</span><span class="sxs-lookup"><span data-stu-id="d8a24-126">The worker to process life events for.</span></span> <span data-ttu-id="d8a24-127">Si vous laissez ce champ vide, les événements de vie seront traités pour tous les collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="d8a24-127">If you leave this field blank, life events will be processed for all workers.</span></span> |

3. <span data-ttu-id="d8a24-128">Si vous souhaitez exécuter le processus en arrière-plan, sélectionnez **Exécuter à l'arrière-plan** et effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="d8a24-128">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="d8a24-129">Entrez les informations pour le processus.</span><span class="sxs-lookup"><span data-stu-id="d8a24-129">Enter information for the process.</span></span>

   2. <span data-ttu-id="d8a24-130">Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8a24-130">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="d8a24-131">Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8a24-131">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="d8a24-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8a24-132">Select **OK**.</span></span> <span data-ttu-id="d8a24-133">Le processus s'exécutera avec les paramètres que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="d8a24-133">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="d8a24-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8a24-134">Select **OK**.</span></span>
