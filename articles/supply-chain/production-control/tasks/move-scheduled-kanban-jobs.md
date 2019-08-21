---
title: Déplacer les tâches de kanban planifiées
description: Cette procédure se concentre sur le déplacement des tâches de kanban d'un processus planifié dans une autre période.
author: ChristianRytt
manager: AnnBe
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2526c2bd106e35c736e930b5b5114d019718dc5a
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836238"
---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="92060-103">Déplacer les tâches de kanban planifiées</span><span class="sxs-lookup"><span data-stu-id="92060-103">Move scheduled kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="92060-104">Cette procédure se concentre sur le déplacement des tâches de kanban d'un processus planifié dans une autre période.</span><span class="sxs-lookup"><span data-stu-id="92060-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="92060-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="92060-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="92060-106">Cette procédure est destinée au superviseur d'atelier ou au responsable de production qui utilisent des kanbans.</span><span class="sxs-lookup"><span data-stu-id="92060-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>

## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="92060-107">Sélectionner les tâches de kanban planifiées.</span><span class="sxs-lookup"><span data-stu-id="92060-107">Select scheduled kanban jobs.</span></span> 

1. <span data-ttu-id="92060-108">Accédez à **Contrôle de la production > Kanban > Planification de tâches de kanban**.</span><span class="sxs-lookup"><span data-stu-id="92060-108">Go to **Production control > Kanban > Kanban job scheduling**.</span></span> 

2. <span data-ttu-id="92060-109">Dans le champ **Cellule de travail**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="92060-109">In the **Work cell** field, click the drop-down button to open the lookup.</span></span> 

3. <span data-ttu-id="92060-110">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="92060-110">In the list, mark the selected row.</span></span> 
   - <span data-ttu-id="92060-111">Sélectionnez la cellule de travail 1250.</span><span class="sxs-lookup"><span data-stu-id="92060-111">Select work cell 1250.</span></span> 
4. <span data-ttu-id="92060-112">Cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="92060-112">Click **Select**.</span></span> 

5. <span data-ttu-id="92060-113">Sélectionnez **Planifié** dans le champ **Afficher le statut de la tâche**.</span><span class="sxs-lookup"><span data-stu-id="92060-113">In the **Display job status** field, select **Scheduled**.</span></span> <span data-ttu-id="92060-114">Cette opération filtre la liste des tâches pour afficher uniquement les tâches de kanban planifiées.</span><span class="sxs-lookup"><span data-stu-id="92060-114">This filters the job list to display only the scheduled kanban jobs.</span></span> 

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="92060-115">Déplacer les tâches de kanban vers une autre période de planification.</span><span class="sxs-lookup"><span data-stu-id="92060-115">Move kanban jobs to a different period.</span></span> 

1. <span data-ttu-id="92060-116">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="92060-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="92060-117">Sélectionnez une tâche dont le statut est **Planifié**, par exemple, une tâche prévue le 20 décembre 2012 dans le champ **Période planifiée**.</span><span class="sxs-lookup"><span data-stu-id="92060-117">Select a job that has the **Planned job** status, for example, a job scheduled on December 20, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="92060-118">Déplacez ensuite la tâche vers la période précédente.</span><span class="sxs-lookup"><span data-stu-id="92060-118">Then move the job to the previous period.</span></span> 

2. <span data-ttu-id="92060-119">Cliquez sur **Période précédente**.</span><span class="sxs-lookup"><span data-stu-id="92060-119">Click **Previous period**.</span></span> 

3. <span data-ttu-id="92060-120">Cliquez sur **Fin** pour déplacer la tâche à la fin de la liste des tâches comme la dernière tâche de la période précédente.</span><span class="sxs-lookup"><span data-stu-id="92060-120">Click **End** to move the job to the end of the job list as the last job in the previous period.</span></span> 

4. <span data-ttu-id="92060-121">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="92060-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="92060-122">Sélectionnez une tâche dont le statut est **Planifié**, par exemple, une tâche prévue le 18 décembre 2012 dans le champ **Période planifiée**.</span><span class="sxs-lookup"><span data-stu-id="92060-122">Select a job that has the **Planned job** status, for example, a job scheduled on December 18, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="92060-123">Déplacez ensuite la tâche vers la période suivante.</span><span class="sxs-lookup"><span data-stu-id="92060-123">Then move the job to the next period.</span></span> 

5. <span data-ttu-id="92060-124">Cliquez sur **Période suivante**.</span><span class="sxs-lookup"><span data-stu-id="92060-124">Click **Next period**.</span></span> 

6. <span data-ttu-id="92060-125">Cliquez sur **Début** pour déplacer la tâche au début de la liste des tâches comme la première tâche de la période précédente.</span><span class="sxs-lookup"><span data-stu-id="92060-125">Click **Start** to move the job to the start of the job list as the first job in the previous period.</span></span> 

## <a name="move-a-job-within-a-period"></a><span data-ttu-id="92060-126">Déplacer une tâche dans une période.</span><span class="sxs-lookup"><span data-stu-id="92060-126">Move a job within a period.</span></span> 

1. <span data-ttu-id="92060-127">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="92060-127">In the list, find and select the desired record.</span></span> <span data-ttu-id="92060-128">Sélectionnez une tâche dont le statut est planifié, par exemple, la deuxième tâche prévue le 19 décembre 2012 dans le champ **Période planifiée**.</span><span class="sxs-lookup"><span data-stu-id="92060-128">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="92060-129">Déplacez ensuite la tâche dans la période planifiée.</span><span class="sxs-lookup"><span data-stu-id="92060-129">Then move the job within the planned period.</span></span> 

2. <span data-ttu-id="92060-130">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="92060-130">Click **Forward**.</span></span> <span data-ttu-id="92060-131">Notez que la tâche est déplacée une ligne vers le bas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="92060-131">Notice that the job is moved one line down on the list.</span></span> 

3. <span data-ttu-id="92060-132">Cliquez sur **Précédent**.</span><span class="sxs-lookup"><span data-stu-id="92060-132">Click **Backward**.</span></span> <span data-ttu-id="92060-133">Notez que la tâche est déplacée une ligne vers le haut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="92060-133">Notice that the job is moved one line up on the list.</span></span>
