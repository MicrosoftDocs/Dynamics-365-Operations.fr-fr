--- 
title: "Planification des tâches de kanban"
description: "Cette procédure se concentre sur des tâches de kanban du processus de planification pour une cellule de travail spécifique."
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f36544993a9280ae10489a19252bc105abd40ac9
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="schedule-kanban-jobs"></a><span data-ttu-id="84eec-103">Planification des tâches de kanban</span><span class="sxs-lookup"><span data-stu-id="84eec-103">Schedule kanban jobs</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="84eec-104">Cette procédure se concentre sur des tâches de kanban du processus de planification pour une cellule de travail spécifique.</span><span class="sxs-lookup"><span data-stu-id="84eec-104">This procedure focuses on scheduling process kanban jobs for a specific work cell.</span></span> <span data-ttu-id="84eec-105">La procédure « Préparer une tâche de kanban de processus lorsque les matières ne sont pas disponibles » est une étape préliminaire à la création de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="84eec-105">The procedure "Prepare a process kanban job when materials are not available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="84eec-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="84eec-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="84eec-107">Cette tâche est destinée au superviseur d'atelier et au responsable de production qui utilisent des kanbans.</span><span class="sxs-lookup"><span data-stu-id="84eec-107">This task is intended for the shop floor supervisor and production planner working with kanbans.</span></span>


## <a name="select-kanban-jobs-for-a-work-cell"></a><span data-ttu-id="84eec-108">Sélectionner les tâches de kanban pour une cellule de travail</span><span class="sxs-lookup"><span data-stu-id="84eec-108">Select kanban jobs for a work cell</span></span>
1. <span data-ttu-id="84eec-109">Accédez à Contrôle de la production > Kanban > Planification de tâches de kanban.</span><span class="sxs-lookup"><span data-stu-id="84eec-109">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="84eec-110">Développez le récapitulatif Capacité de la période.</span><span class="sxs-lookup"><span data-stu-id="84eec-110">Expand the Period capacity fact box</span></span>
    * <span data-ttu-id="84eec-111">Développez le récapitulatif Kanban.</span><span class="sxs-lookup"><span data-stu-id="84eec-111">Expand the Kanban FactBox.</span></span>  
3. <span data-ttu-id="84eec-112">Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="84eec-112">In the Work cell field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="84eec-113">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="84eec-113">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="84eec-114">Sélectionnez la cellule de travail 1250.</span><span class="sxs-lookup"><span data-stu-id="84eec-114">Select work cell 1250.</span></span> <span data-ttu-id="84eec-115">Cela filtrera l'affichage pour afficher uniquement les tâches de la cellule de travail 1250.</span><span class="sxs-lookup"><span data-stu-id="84eec-115">This will filter the view to display only the jobs for work cell 1250.</span></span>  
5. <span data-ttu-id="84eec-116">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="84eec-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="84eec-117">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="84eec-117">Click Select.</span></span>

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a><span data-ttu-id="84eec-118">Planifier une tâche de kanban dans la première période disponible</span><span class="sxs-lookup"><span data-stu-id="84eec-118">Schedule a kanban job in the first available period</span></span>
1. <span data-ttu-id="84eec-119">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="84eec-119">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="84eec-120">Sélectionnez la première ligne de la liste ayant le statut Non prévu.</span><span class="sxs-lookup"><span data-stu-id="84eec-120">Select the first row in the list that has the Not planned status.</span></span> <span data-ttu-id="84eec-121">L'icône en pointillés du champ Statut de tâche signifie Non prévu.</span><span class="sxs-lookup"><span data-stu-id="84eec-121">The dotted icon in the Job status field indicates not planned.</span></span>  
2. <span data-ttu-id="84eec-122">Cliquez sur Programme.</span><span class="sxs-lookup"><span data-stu-id="84eec-122">Click Schedule.</span></span>
    * <span data-ttu-id="84eec-123">Cela planifie la tâche de kanban de la première période disponible.</span><span class="sxs-lookup"><span data-stu-id="84eec-123">This will schedule the kanban job in the first available period.</span></span>  
    * <span data-ttu-id="84eec-124">Notez que la tâche de kanban est déplacée à la fin de la liste car elle a été ajoutée à la période le jour-même.</span><span class="sxs-lookup"><span data-stu-id="84eec-124">Notice that the kanban job is moved to the end of the list because it has been added to the period starting from today.</span></span>  
    * <span data-ttu-id="84eec-125">Si la période commençant le jour-même est entièrement réservée, la tâche sera déplacée vers la première période disponible.</span><span class="sxs-lookup"><span data-stu-id="84eec-125">If the period starting from today is fully booked, the job will be moved to the first available period.</span></span>  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a><span data-ttu-id="84eec-126">Planifier deux tâches de kanban pour un jour spécifique</span><span class="sxs-lookup"><span data-stu-id="84eec-126">Schedule two kanban jobs for a specific day</span></span>
1. <span data-ttu-id="84eec-127">Sélectionnez la ligne 1 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="84eec-127">In the list, select row 1.</span></span>
    * <span data-ttu-id="84eec-128">Vous devez voir que la première ligne a le statut Non prévu dans le champ Statut de tâche.</span><span class="sxs-lookup"><span data-stu-id="84eec-128">You should see that the first row has the Not planned status in the Job status field.</span></span>  
2. <span data-ttu-id="84eec-129">Sélectionnez la ligne 2 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="84eec-129">In the list, select row 2.</span></span>
    * <span data-ttu-id="84eec-130">Vous devez voir que la deuxième ligne a le statut Non prévu dans le champ Statut de tâche.</span><span class="sxs-lookup"><span data-stu-id="84eec-130">You should see that the second row has the Not planned status in the Job status field.</span></span> <span data-ttu-id="84eec-131">Les deux premières tâches sont désormais sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="84eec-131">Now you have the first two jobs selected.</span></span>  
3. <span data-ttu-id="84eec-132">Cliquez sur Planifier à partir de la date pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="84eec-132">Click Schedule from date to open the drop dialog.</span></span>
4. <span data-ttu-id="84eec-133">Activez ou désactivez la case à cocher Remplacer la réaction de pénurie de capacité.</span><span class="sxs-lookup"><span data-stu-id="84eec-133">Check or uncheck the Override capacity shortage reaction box.</span></span>
    * <span data-ttu-id="84eec-134">Cette option permet d'ignorer la réaction de pénurie de capacité par défaut.</span><span class="sxs-lookup"><span data-stu-id="84eec-134">This option allows you to override the default capacity shortage reaction.</span></span>  
5. <span data-ttu-id="84eec-135">Dans le champ Réaction de pénurie de capacité, sélectionnez « Ajouter à la période demandée ».</span><span class="sxs-lookup"><span data-stu-id="84eec-135">In the Capacity shortage reaction field, select 'Add to the requested period'.</span></span>
    * <span data-ttu-id="84eec-136">Cette option garantit que la tâche est ajoutée à la période requise, sans tenir compte de la surcharge éventuelle de la cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="84eec-136">This option will ensure that the job is added to the requested period, regardless if the work cell might be overloaded.</span></span>  
6. <span data-ttu-id="84eec-137">Cliquez sur Programme.</span><span class="sxs-lookup"><span data-stu-id="84eec-137">Click Schedule.</span></span>
    * <span data-ttu-id="84eec-138">Notez que les deux tâches sont ajoutées à la période souhaitée.</span><span class="sxs-lookup"><span data-stu-id="84eec-138">Notice that both jobs are added to the desired period.</span></span>  
    * <span data-ttu-id="84eec-139">Dans la section Capacité de la période, vous pouvez afficher la charge pour chaque période.</span><span class="sxs-lookup"><span data-stu-id="84eec-139">In the Period capacity section, you can see the load for each period.</span></span> <span data-ttu-id="84eec-140">Le champ Consommation affiche la consommation prévue pendant cette période.</span><span class="sxs-lookup"><span data-stu-id="84eec-140">The Consumption field shows the scheduled consumption in this period.</span></span> <span data-ttu-id="84eec-141">Si la consommation prévue est supérieure à la capacité disponible pendant cette période, la consommation surchargée sera sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="84eec-141">If the scheduled consumption is higher than the available capacity in this period, the overloaded consumption will be selected.</span></span>  


