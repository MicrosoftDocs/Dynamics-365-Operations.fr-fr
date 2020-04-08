---
title: Programmer un ordre de fabrication avec la planification d'opérations et de travaux
description: Cette rubrique se concentre sur la planification d’un ordre de fabrication avec la planification des opérations et la planification des tâches.
author: ChristianRytt
manager: AnnBe
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2181a84aea08aac0ddb202f7211dbda6330a3d49
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148835"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="0993d-103">Programmer un ordre de fabrication avec la planification d'opérations et de travaux</span><span class="sxs-lookup"><span data-stu-id="0993d-103">Schedule a production order with operations and job scheduling</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0993d-104">Cette rubrique se concentre sur la planification d’un ordre de fabrication avec la planification des opérations et la planification des tâches.</span><span class="sxs-lookup"><span data-stu-id="0993d-104">This topic focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="0993d-105">Aucune tâche n'est créée avec la planification des opérations tandis que des travaux sont créés avec la planification des tâches.</span><span class="sxs-lookup"><span data-stu-id="0993d-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="0993d-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="0993d-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="0993d-107">Cette procédure est conçue pour le gestionnaire de production, le planificateur de production ou le superviseur d'atelier travaillant dans un environnement de fabrication discrète.</span><span class="sxs-lookup"><span data-stu-id="0993d-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="0993d-108">Créer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="0993d-108">Create a production order</span></span>
1. <span data-ttu-id="0993d-109">Dans le volet de navigation, accédez à **Modules > Contrôle de la production > Commun > Ordres de fabrication > Tous les ordres de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="0993d-109">In the navigation pane, go to **Modules > Production control > Production orders > All production orders**.</span></span>
2. <span data-ttu-id="0993d-110">Sélectionnez **Nouvel ordre de production**.</span><span class="sxs-lookup"><span data-stu-id="0993d-110">Select **New production order**.</span></span>
3. <span data-ttu-id="0993d-111">Entrez ou sélectionnez une valeur dans le champ **Numéro d'article**.</span><span class="sxs-lookup"><span data-stu-id="0993d-111">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="0993d-112">Sélectionnez le numéro d'article **D0001**.</span><span class="sxs-lookup"><span data-stu-id="0993d-112">Select Item number **D0001**.</span></span>  
4. <span data-ttu-id="0993d-113">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="0993d-113">Select **Create**.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="0993d-114">Planifier les opérations pour l'ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="0993d-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="0993d-115">Marquez la ligne récemment créée.</span><span class="sxs-lookup"><span data-stu-id="0993d-115">Mark the newly created row.</span></span>      
2. <span data-ttu-id="0993d-116">Dans le volet Actions, sélectionnez **Planifier**.</span><span class="sxs-lookup"><span data-stu-id="0993d-116">On the Action Pane, select **Schedule**.</span></span>
3. <span data-ttu-id="0993d-117">Sélectionnez **Planifier les opérations**.</span><span class="sxs-lookup"><span data-stu-id="0993d-117">Select **Schedule operations**.</span></span>
4. <span data-ttu-id="0993d-118">Dans le champ **Direction de la planification**, sélectionnez **En avant à partir de la date de planification**.</span><span class="sxs-lookup"><span data-stu-id="0993d-118">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
5. <span data-ttu-id="0993d-119">Dans le champ **Date de planification**, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="0993d-119">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="0993d-120">Sélectionnez une date future, par exemple, aujourd'hui plus une semaine.</span><span class="sxs-lookup"><span data-stu-id="0993d-120">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="0993d-121">Avec la direction de planification sélectionée, l'ordre de fabrication est planifié en avant à partir de la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="0993d-121">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="0993d-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0993d-122">Select **OK**.</span></span>
7. <span data-ttu-id="0993d-123">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0993d-123">In the list, mark the selected row.</span></span> <span data-ttu-id="0993d-124">Notez que le statut devient **Planifiée**.</span><span class="sxs-lookup"><span data-stu-id="0993d-124">Note that the status is changed to **Scheduled**.</span></span> 
8. <span data-ttu-id="0993d-125">Sélectionnez **Toutes les tâches**.</span><span class="sxs-lookup"><span data-stu-id="0993d-125">Select **All jobs**.</span></span> <span data-ttu-id="0993d-126">Notez qu’aucune tâche n’est créée avec la planification des opérations.</span><span class="sxs-lookup"><span data-stu-id="0993d-126">Note that no jobs are created with operations scheduling.</span></span>  
9. <span data-ttu-id="0993d-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0993d-127">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="0993d-128">Planifier les tâches pour l'ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="0993d-128">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="0993d-129">Dans le volet Actions, sélectionnez **Planifier**.</span><span class="sxs-lookup"><span data-stu-id="0993d-129">On the Action Pane, select **Schedule**.</span></span>
2. <span data-ttu-id="0993d-130">Sélectionnez **Planifier les tâches**.</span><span class="sxs-lookup"><span data-stu-id="0993d-130">Select **Schedule jobs**.</span></span>
3. <span data-ttu-id="0993d-131">Dans le champ **Direction de la planification**, sélectionnez **En avant à partir de la date de planification**.</span><span class="sxs-lookup"><span data-stu-id="0993d-131">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
4. <span data-ttu-id="0993d-132">Dans le champ **Date de planification**, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="0993d-132">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="0993d-133">Sélectionnez une date future, par exemple, aujourd'hui plus une semaine.</span><span class="sxs-lookup"><span data-stu-id="0993d-133">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="0993d-134">Avec la direction de planification sélectionée, l'ordre de fabrication est planifié en avant à partir de la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="0993d-134">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="0993d-135">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0993d-135">Select **OK**.</span></span>
6. <span data-ttu-id="0993d-136">Dans le volet Actions, sélectionnez **Ordre de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="0993d-136">On the Action Pane, select **Production order**.</span></span>
7. <span data-ttu-id="0993d-137">Sélectionnez **Toutes les tâches**.</span><span class="sxs-lookup"><span data-stu-id="0993d-137">Select **All jobs**.</span></span> <span data-ttu-id="0993d-138">Notez qu’en fonction de la gamme active, 5 tâches sont créées avec la planification des tâches.</span><span class="sxs-lookup"><span data-stu-id="0993d-138">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  

