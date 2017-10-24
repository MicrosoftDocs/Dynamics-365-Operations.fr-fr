--- 
title: "Programmer un ordre de fabrication avec la planification d'opérations et de travaux"
description: "Cette procédure se concentre sur la planification d’un ordre de fabrication avec la planification des opérations et la planification des tâches."
author: ChristianRytt
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d4aac437876862e9f776264fc81f246c820bdf45
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="46d64-103">Programmer un ordre de fabrication avec la planification d'opérations et de travaux</span><span class="sxs-lookup"><span data-stu-id="46d64-103">Schedule a production order with operations and job scheduling</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="46d64-104">Cette procédure se concentre sur la planification d’un ordre de fabrication avec la planification des opérations et la planification des tâches.</span><span class="sxs-lookup"><span data-stu-id="46d64-104">This procedure focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="46d64-105">Aucune tâche n'est créée avec la planification des opérations tandis que des travaux sont créés avec la planification des tâches.</span><span class="sxs-lookup"><span data-stu-id="46d64-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="46d64-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="46d64-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="46d64-107">Cette procédure est conçue pour le gestionnaire de production, le planificateur de production ou le superviseur d'atelier travaillant dans un environnement de fabrication discrète.</span><span class="sxs-lookup"><span data-stu-id="46d64-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="46d64-108">Créer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="46d64-108">Create a production order</span></span>
1. <span data-ttu-id="46d64-109">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="46d64-109">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="46d64-110">Cliquez sur Nouvel ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="46d64-110">Click New production order.</span></span>
3. <span data-ttu-id="46d64-111">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="46d64-111">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="46d64-112">Sélectionnez le numéro d'article D0001.</span><span class="sxs-lookup"><span data-stu-id="46d64-112">Select Item number D0001.</span></span>  
4. <span data-ttu-id="46d64-113">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="46d64-113">Click Create.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="46d64-114">Planifier les opérations pour l'ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="46d64-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="46d64-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="46d64-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="46d64-116">Sélectionnez l’ordre de fabrication que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="46d64-116">Select the production order that you have just created.</span></span> <span data-ttu-id="46d64-117">Il doit être en haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="46d64-117">It should be at the top of the list.</span></span>      
2. <span data-ttu-id="46d64-118">Dans le volet Actions, cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="46d64-118">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="46d64-119">Cliquez sur Planifier les opérations.</span><span class="sxs-lookup"><span data-stu-id="46d64-119">Click Schedule operations.</span></span>
4. <span data-ttu-id="46d64-120">Dans le champ Direction de la planification, sélectionnez « En avant à partir de la date de planification ».</span><span class="sxs-lookup"><span data-stu-id="46d64-120">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
5. <span data-ttu-id="46d64-121">Dans le champ Date de planification, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="46d64-121">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="46d64-122">Sélectionnez une date future, par exemple, aujourd'hui plus une semaine.</span><span class="sxs-lookup"><span data-stu-id="46d64-122">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="46d64-123">Avec la direction de planification sélectionée, l'ordre de fabrication est planifié en avant à partir de la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="46d64-123">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="46d64-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="46d64-124">Click OK.</span></span>
7. <span data-ttu-id="46d64-125">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="46d64-125">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="46d64-126">Notez que le statut devient Planifiée.</span><span class="sxs-lookup"><span data-stu-id="46d64-126">Note that the status is changed to Scheduled.</span></span>  
8. <span data-ttu-id="46d64-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="46d64-127">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="46d64-128">Cliquez sur Toutes les tâches.</span><span class="sxs-lookup"><span data-stu-id="46d64-128">Click All jobs.</span></span>
    * <span data-ttu-id="46d64-129">Notez qu’aucune tâche n’est créée avec la planification des opérations.</span><span class="sxs-lookup"><span data-stu-id="46d64-129">Note that no jobs are created with operations scheduling.</span></span>  
10. <span data-ttu-id="46d64-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="46d64-130">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="46d64-131">Planifier les tâches pour l'ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="46d64-131">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="46d64-132">Dans le volet Actions, cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="46d64-132">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="46d64-133">Cliquez sur Planifier les tâches.</span><span class="sxs-lookup"><span data-stu-id="46d64-133">Click Schedule jobs.</span></span>
3. <span data-ttu-id="46d64-134">Dans le champ Direction de la planification, sélectionnez « En avant à partir de la date de planification ».</span><span class="sxs-lookup"><span data-stu-id="46d64-134">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
4. <span data-ttu-id="46d64-135">Dans le champ Date de planification, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="46d64-135">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="46d64-136">Sélectionnez une date future, par exemple, aujourd'hui plus une semaine.</span><span class="sxs-lookup"><span data-stu-id="46d64-136">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="46d64-137">Avec la direction de planification sélectionée, l'ordre de fabrication est planifié en avant à partir de la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="46d64-137">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="46d64-138">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="46d64-138">Click OK.</span></span>
6. <span data-ttu-id="46d64-139">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="46d64-139">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="46d64-140">Cliquez sur Toutes les tâches.</span><span class="sxs-lookup"><span data-stu-id="46d64-140">Click All jobs.</span></span>
    * <span data-ttu-id="46d64-141">Notez qu’en fonction de la gamme active, 5 tâches sont créées avec la planification des tâches.</span><span class="sxs-lookup"><span data-stu-id="46d64-141">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  


