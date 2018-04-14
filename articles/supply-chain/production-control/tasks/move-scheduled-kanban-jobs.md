--- 
title: "Déplacer les tâches de kanban planifiées"
description: "Cette procédure se concentre sur le déplacement des tâches de kanban d'un processus planifié dans une autre période."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a20765f29a3d8b3bff75229ebbb1996a4d601154
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="9f342-103">Déplacer les tâches de kanban planifiées</span><span class="sxs-lookup"><span data-stu-id="9f342-103">Move scheduled kanban jobs</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9f342-104">Cette procédure se concentre sur le déplacement des tâches de kanban d'un processus planifié dans une autre période.</span><span class="sxs-lookup"><span data-stu-id="9f342-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="9f342-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="9f342-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="9f342-106">Cette procédure est destinée au superviseur d'atelier ou au responsable de production qui utilisent des kanbans.</span><span class="sxs-lookup"><span data-stu-id="9f342-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>


## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="9f342-107">Sélectionner les tâches de kanban planifiées</span><span class="sxs-lookup"><span data-stu-id="9f342-107">Select scheduled kanban jobs</span></span>
1. <span data-ttu-id="9f342-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span><span class="sxs-lookup"><span data-stu-id="9f342-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span></span>
2. <span data-ttu-id="9f342-109">Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9f342-109">!MtCMR!In the Work cell field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="9f342-110">áçêìõý !</span><span class="sxs-lookup"><span data-stu-id="9f342-110">áçêìõý !</span></span>
3. <span data-ttu-id="9f342-111">Markér den valgte række på listen.</span><span class="sxs-lookup"><span data-stu-id="9f342-111">Markér den valgte række på listen.</span></span>
    * <span data-ttu-id="9f342-112">Sélectionnez la cellule de travail 1250.</span><span class="sxs-lookup"><span data-stu-id="9f342-112">Select work cell 1250.</span></span>  
4. <span data-ttu-id="9f342-113">Klik på Select.</span><span class="sxs-lookup"><span data-stu-id="9f342-113">Klik på Select.</span></span>
5. <span data-ttu-id="9f342-114">Vælg 'Planlagt' i feltet Display job status.</span><span class="sxs-lookup"><span data-stu-id="9f342-114">Vælg 'Planlagt' i feltet Display job status.</span></span>
    * <span data-ttu-id="9f342-115">Cette opération filtre la liste des tâches pour afficher uniquement les tâches de kanban planifiées.</span><span class="sxs-lookup"><span data-stu-id="9f342-115">This filters the job list to display only the scheduled kanban jobs.</span></span>  

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="9f342-116">Déplacer les tâches de kanban vers une autre période de planification.</span><span class="sxs-lookup"><span data-stu-id="9f342-116">Move kanban jobs to a different period</span></span>
1. <span data-ttu-id="9f342-117">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="9f342-117">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="9f342-118">Sélectionnez une tâche dont le statut est planifié, par exemple, une tâche prévue le 20 décembre 2012 dans le champ Période planifiée.</span><span class="sxs-lookup"><span data-stu-id="9f342-118">Select a job that has the Planned job status, for example, a job scheduled on December 20, 2012  in the Planned period field.</span></span> <span data-ttu-id="9f342-119">Déplacez ensuite la tâche vers la période précédente.</span><span class="sxs-lookup"><span data-stu-id="9f342-119">Then move the job to the previous period.</span></span>  
2. <span data-ttu-id="9f342-120">Klik på Previous period.</span><span class="sxs-lookup"><span data-stu-id="9f342-120">Klik på Previous period.</span></span>
3. <span data-ttu-id="9f342-121">Klik på End.</span><span class="sxs-lookup"><span data-stu-id="9f342-121">Klik på End.</span></span>
    * <span data-ttu-id="9f342-122">Cela déplacera la tâche à la fin de la liste des tâches comme la dernière tâche de la période précédente.</span><span class="sxs-lookup"><span data-stu-id="9f342-122">This will move the job to the end of the job list as the last job in the previous period.</span></span>  
4. <span data-ttu-id="9f342-123">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="9f342-123">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="9f342-124">Sélectionnez une tâche dont le statut est planifié, par exemple, une tâche prévue le 18 décembre 2012 dans le champ Période planifiée.</span><span class="sxs-lookup"><span data-stu-id="9f342-124">Select a job that has the Planned job status, for example, a job scheduled on December 18, 2012 in the Planned period field.</span></span> <span data-ttu-id="9f342-125">Déplacez ensuite la tâche vers la période suivante.</span><span class="sxs-lookup"><span data-stu-id="9f342-125">Then move the job to the next period.</span></span>  
5. <span data-ttu-id="9f342-126">Klik på Next period.</span><span class="sxs-lookup"><span data-stu-id="9f342-126">Klik på Next period.</span></span>
6. <span data-ttu-id="9f342-127">Klik på Start.</span><span class="sxs-lookup"><span data-stu-id="9f342-127">Klik på Start.</span></span>
    * <span data-ttu-id="9f342-128">Cela déplacera la tâche au début de la liste des tâches comme la première tâche de la période précédente.</span><span class="sxs-lookup"><span data-stu-id="9f342-128">This will move the job to the start of the job list as the first job in the previous period.</span></span>  

## <a name="task-move-a-job-within-a-period"></a><span data-ttu-id="9f342-129">Tâche : Déplacer une tâche dans une période.</span><span class="sxs-lookup"><span data-stu-id="9f342-129">Task: Move a job within a period</span></span>
1. <span data-ttu-id="9f342-130">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="9f342-130">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="9f342-131">Sélectionnez une tâche dont le statut est planifié, par exemple, la deuxième tâche prévue le 19 décembre 2012 dans le champ Période planifiée.</span><span class="sxs-lookup"><span data-stu-id="9f342-131">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the Planned period field.</span></span> <span data-ttu-id="9f342-132">Déplacez ensuite la tâche dans la période planifiée.</span><span class="sxs-lookup"><span data-stu-id="9f342-132">Then move the job within the planned period.</span></span>  
2. <span data-ttu-id="9f342-133">Klik på Forward.</span><span class="sxs-lookup"><span data-stu-id="9f342-133">Klik på Forward.</span></span>
    * <span data-ttu-id="9f342-134">Notez que la tâche est déplacée une ligne vers le bas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="9f342-134">Notice that the job is moved one line down on the list.</span></span>  
3. <span data-ttu-id="9f342-135">Klik på Backward.</span><span class="sxs-lookup"><span data-stu-id="9f342-135">Klik på Backward.</span></span>
    * <span data-ttu-id="9f342-136">Notez que la tâche est déplacée une ligne vers le haut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="9f342-136">Notice that the job is moved one line up on the list.</span></span>  


