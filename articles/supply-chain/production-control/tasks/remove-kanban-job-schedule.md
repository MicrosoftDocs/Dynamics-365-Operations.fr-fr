---
title: Supprimer une tâche de kanban du programme
description: Cette procédure consiste à supprimer une tâche de kanban d'un processus planifié du programme en basculant le statut de la tâche sur Non planifié.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4d994be5c6bb1edc6f0fc64494a19a5babf72ae
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571970"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="83416-103">Supprimer une tâche de kanban du programme</span><span class="sxs-lookup"><span data-stu-id="83416-103">Remove a kanban job from the schedule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="83416-104">Cette procédure consiste à supprimer une tâche de kanban d'un processus planifié du programme en basculant le statut de la tâche sur Non planifié.</span><span class="sxs-lookup"><span data-stu-id="83416-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="83416-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="83416-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="83416-106">Cette procédure est destinée au superviseur d'atelier ou au responsable de production.</span><span class="sxs-lookup"><span data-stu-id="83416-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="83416-107">Rechercher une tâche de kanban planifiée</span><span class="sxs-lookup"><span data-stu-id="83416-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="83416-108">Accédez à Contrôle de la production > Kanban > Planification de tâches de kanban.</span><span class="sxs-lookup"><span data-stu-id="83416-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="83416-109">Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="83416-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="83416-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="83416-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="83416-111">Sélectionnez la cellule de travail 1250.</span><span class="sxs-lookup"><span data-stu-id="83416-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="83416-112">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="83416-112">Click Select.</span></span>
5. <span data-ttu-id="83416-113">Sélectionnez « Planifié » dans le champ Afficher le statut de la tâche.</span><span class="sxs-lookup"><span data-stu-id="83416-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="83416-114">Supprimer la tâche de kanban planifiée du programme</span><span class="sxs-lookup"><span data-stu-id="83416-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="83416-115">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="83416-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="83416-116">Sélectionnez une tâche dont le statut est Planifié, par exemple, une tâche du 19 décembre 2012.</span><span class="sxs-lookup"><span data-stu-id="83416-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="83416-117">Cliquez sur Planifier dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="83416-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="83416-118">Cliquez sur Rétablir le statut de la tâche.</span><span class="sxs-lookup"><span data-stu-id="83416-118">Click Revert job status.</span></span>
4. <span data-ttu-id="83416-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="83416-119">Click OK.</span></span>
    * <span data-ttu-id="83416-120">Cela va basculer le statut de la tâche actuel de « Planifié » à « Non planifié » et l'enlèvera du tableau de traitement.</span><span class="sxs-lookup"><span data-stu-id="83416-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   

