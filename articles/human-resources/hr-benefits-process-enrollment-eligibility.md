---
title: Processus d'éligibilité à l'inscription
description: Cet article explique comment exécuter le processus d'éligibilité à l'inscription.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 0344c48460a7d1540481e09ba106526e119de72b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008961"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="54b7f-103">Processus d'éligibilité à l'inscription</span><span class="sxs-lookup"><span data-stu-id="54b7f-103">Process enrollment eligibility</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="54b7f-104">Cet article explique comment exécuter le processus d'éligibilité à l'inscription.</span><span class="sxs-lookup"><span data-stu-id="54b7f-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="54b7f-105">Dans l'espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Processus d'éligibilité à l'inscription**.</span><span class="sxs-lookup"><span data-stu-id="54b7f-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="54b7f-106">Dans la boîte de dialogue **Exécuter le processus d'éligibilité à l'inscription aux avantages**, spécifiez des valeurs pour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="54b7f-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="54b7f-107">Champ</span><span class="sxs-lookup"><span data-stu-id="54b7f-107">Field</span></span> | <span data-ttu-id="54b7f-108">Description</span><span class="sxs-lookup"><span data-stu-id="54b7f-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="54b7f-109">Période d'inscription</span><span class="sxs-lookup"><span data-stu-id="54b7f-109">Enrollment period</span></span> | <span data-ttu-id="54b7f-110">La période d'inscription pour traiter l'éligibilité.</span><span class="sxs-lookup"><span data-stu-id="54b7f-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="54b7f-111">Entité juridique</span><span class="sxs-lookup"><span data-stu-id="54b7f-111">Legal entity</span></span> | <span data-ttu-id="54b7f-112">L'entité juridique pour laquelle traiter l'éligibilité.</span><span class="sxs-lookup"><span data-stu-id="54b7f-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="54b7f-113">Collaborateur</span><span class="sxs-lookup"><span data-stu-id="54b7f-113">Worker</span></span> | <span data-ttu-id="54b7f-114">Le collaborateur pour lequel traiter l'éligibilité.</span><span class="sxs-lookup"><span data-stu-id="54b7f-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="54b7f-115">Si vous laissez ce champ vide, l'éligibilité à l'inscription sera traitée pour tous les collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="54b7f-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="54b7f-116">Plan d'avantages</span><span class="sxs-lookup"><span data-stu-id="54b7f-116">Benefit plan</span></span> | <span data-ttu-id="54b7f-117">Le plan d'avantages pour lequel traiter l'éligibilité.</span><span class="sxs-lookup"><span data-stu-id="54b7f-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="54b7f-118">Si vous souhaitez exécuter le processus en arrière-plan, sélectionnez **Exécuter à l'arrière-plan** et effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="54b7f-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="54b7f-119">Entrez les informations pour le processus.</span><span class="sxs-lookup"><span data-stu-id="54b7f-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="54b7f-120">Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="54b7f-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="54b7f-121">Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="54b7f-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="54b7f-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="54b7f-122">Select **OK**.</span></span> <span data-ttu-id="54b7f-123">Le processus s'exécutera avec les paramètres que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="54b7f-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="54b7f-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="54b7f-124">Select **OK**.</span></span>
