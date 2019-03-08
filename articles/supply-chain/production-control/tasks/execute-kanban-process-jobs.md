---
title: Exécuter les opérations de traitement du kanban
description: Cette procédure se concentre sur l'exécution des tâches de traitement de kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 62be1f116dfecbc4c6ba11053b94efc874baa3e3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "357425"
---
# <a name="execute-kanban-process-jobs"></a><span data-ttu-id="ab31b-103">Exécuter les opérations de traitement du kanban</span><span class="sxs-lookup"><span data-stu-id="ab31b-103">Execute kanban process jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ab31b-104">Cette procédure se concentre sur l'exécution des tâches de traitement de kanban.</span><span class="sxs-lookup"><span data-stu-id="ab31b-104">This procedure focuses on executing kanban process jobs.</span></span> <span data-ttu-id="ab31b-105">La première tâche est terminée avec la quantité prévue et il n'y a pas d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="ab31b-105">The first job is completed with the expected quantity and has no errors.</span></span> <span data-ttu-id="ab31b-106">La deuxième tâche est exécutée avec des erreurs.</span><span class="sxs-lookup"><span data-stu-id="ab31b-106">The second job is completed with errors.</span></span> <span data-ttu-id="ab31b-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="ab31b-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ab31b-108">Cette procédure est destinée à l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="ab31b-108">This procedure is intended for the machine operator.</span></span>


## <a name="select-a-kanban-job"></a><span data-ttu-id="ab31b-109">Sélectionnez une tâche de kanban.</span><span class="sxs-lookup"><span data-stu-id="ab31b-109">Select a kanban job</span></span>
1. <span data-ttu-id="ab31b-110">Accédez à Contrôle de la production > Kanban > Tableau kanban pour les opérations de traitement.</span><span class="sxs-lookup"><span data-stu-id="ab31b-110">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="ab31b-111">Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ab31b-111">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="ab31b-112">Cliquez sur la ligne dont le groupe de ressources est 1250.</span><span class="sxs-lookup"><span data-stu-id="ab31b-112">Click the row with resource group 1250.</span></span> <span data-ttu-id="ab31b-113">Cela filtre la liste des tâches pour afficher uniquement les tâches de la cellule de travail 1250.</span><span class="sxs-lookup"><span data-stu-id="ab31b-113">This filters the Jobs list to display only the jobs for work cell 1250.</span></span>
    * <span data-ttu-id="ab31b-114">Marquez la ligne dont le statut est Planifié.</span><span class="sxs-lookup"><span data-stu-id="ab31b-114">Mark the row that has the Planned job status.</span></span>  

## <a name="complete-a-job-with-expected-quantity"></a><span data-ttu-id="ab31b-115">Effectuer une tâche avec la quantité prévue</span><span class="sxs-lookup"><span data-stu-id="ab31b-115">Complete a job with expected quantity</span></span>
1. <span data-ttu-id="ab31b-116">Développez ou réduisez la section Détails.</span><span class="sxs-lookup"><span data-stu-id="ab31b-116">Expand or collapse the Details section.</span></span>
    * <span data-ttu-id="ab31b-117">Cette section affiche des informations importantes sur le numéro de carte, le numéro d'article, la quantité commandée et le nom de l'activité.</span><span class="sxs-lookup"><span data-stu-id="ab31b-117">This section displays important information about card number, item number, quantity ordered, and activity name.</span></span>  
2. <span data-ttu-id="ab31b-118">Développez ou réduisez la section Instructions de production.</span><span class="sxs-lookup"><span data-stu-id="ab31b-118">Expand or collapse the Production instructions section.</span></span>
    * <span data-ttu-id="ab31b-119">Cette section affiche les instructions de production pour l'activité.</span><span class="sxs-lookup"><span data-stu-id="ab31b-119">This section displays production instructions for the activity.</span></span> <span data-ttu-id="ab31b-120">Il peut s'agir d'un texte, d'images, de dessins et d'autres documents.</span><span class="sxs-lookup"><span data-stu-id="ab31b-120">The instructions can be text, pictures, drawings, and other documents.</span></span>  
3. <span data-ttu-id="ab31b-121">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="ab31b-121">Click Start.</span></span>
    * <span data-ttu-id="ab31b-122">Sélectionnez une tâche qui n'est pas terminée.</span><span class="sxs-lookup"><span data-stu-id="ab31b-122">Select a job that is not completed.</span></span> <span data-ttu-id="ab31b-123">Utilisez les icônes de statut dans le champ Statut de tâche pour afficher le statut de la tâche.</span><span class="sxs-lookup"><span data-stu-id="ab31b-123">Use status icons in the Job status field to view job status.</span></span>      
4. <span data-ttu-id="ab31b-124">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="ab31b-124">Click Complete.</span></span>
    * <span data-ttu-id="ab31b-125">La tâche est exécutée avec la qualité prévue.</span><span class="sxs-lookup"><span data-stu-id="ab31b-125">The job is completed with the expected quality.</span></span>  

## <a name="complete-a-job-with-errors"></a><span data-ttu-id="ab31b-126">Effectuer une tâche avec des erreurs</span><span class="sxs-lookup"><span data-stu-id="ab31b-126">Complete a job with errors</span></span>
1. <span data-ttu-id="ab31b-127">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="ab31b-127">Click Start.</span></span>
    * <span data-ttu-id="ab31b-128">Lorsqu'une tâche est terminée, la tâche suivante dans la liste est activée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="ab31b-128">When a job is completed, the next job on the list is selected automatically.</span></span> <span data-ttu-id="ab31b-129">C'est pourquoi vous n'avez pas à sélectionner une tâche avant de cliquer sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="ab31b-129">This is why you don't need to select a job before you click Start.</span></span>  
2. <span data-ttu-id="ab31b-130">Dans le volet Actions, cliquez sur Fabrication.</span><span class="sxs-lookup"><span data-stu-id="ab31b-130">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="ab31b-131">Cliquez sur Terminer (détails).</span><span class="sxs-lookup"><span data-stu-id="ab31b-131">Click Complete (details).</span></span>
4. <span data-ttu-id="ab31b-132">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ab31b-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="ab31b-133">Entrez un nombre dans le champ Quantité erronée.</span><span class="sxs-lookup"><span data-stu-id="ab31b-133">In the Error quantity field, enter a number.</span></span>
6. <span data-ttu-id="ab31b-134">Entrez un nombre dans le champ Quantité correcte.</span><span class="sxs-lookup"><span data-stu-id="ab31b-134">In the Good quantity field, enter a number.</span></span>
7. <span data-ttu-id="ab31b-135">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ab31b-135">Click OK.</span></span>

