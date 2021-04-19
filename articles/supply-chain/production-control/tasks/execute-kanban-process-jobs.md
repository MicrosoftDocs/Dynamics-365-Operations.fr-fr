---
title: Exécuter les opérations de traitement du kanban
description: Cette procédure se concentre sur l’exécution des tâches de traitement de kanban.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0bccee458ee48c51bdeeb64cee1f62aac9bdf4f9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828536"
---
# <a name="execute-kanban-process-jobs"></a><span data-ttu-id="48e01-103">Exécuter les opérations de traitement du kanban</span><span class="sxs-lookup"><span data-stu-id="48e01-103">Execute kanban process jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="48e01-104">Cette procédure se concentre sur l’exécution des tâches de traitement de kanban.</span><span class="sxs-lookup"><span data-stu-id="48e01-104">This procedure focuses on executing kanban process jobs.</span></span> <span data-ttu-id="48e01-105">La première tâche est terminée avec la quantité prévue et il n’y a pas d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="48e01-105">The first job is completed with the expected quantity and has no errors.</span></span> <span data-ttu-id="48e01-106">La deuxième tâche est exécutée avec des erreurs.</span><span class="sxs-lookup"><span data-stu-id="48e01-106">The second job is completed with errors.</span></span> <span data-ttu-id="48e01-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="48e01-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="48e01-108">Cette procédure est destinée à l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="48e01-108">This procedure is intended for the machine operator.</span></span>


## <a name="select-a-kanban-job"></a><span data-ttu-id="48e01-109">Sélectionnez une tâche de kanban.</span><span class="sxs-lookup"><span data-stu-id="48e01-109">Select a kanban job</span></span>
1. <span data-ttu-id="48e01-110">Accédez à Contrôle de la production > Kanban > Tableau kanban pour les opérations de traitement.</span><span class="sxs-lookup"><span data-stu-id="48e01-110">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="48e01-111">Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="48e01-111">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="48e01-112">Cliquez sur la ligne dont le groupe de ressources est 1250.</span><span class="sxs-lookup"><span data-stu-id="48e01-112">Click the row with resource group 1250.</span></span> <span data-ttu-id="48e01-113">Cela filtre la liste des tâches pour afficher uniquement les tâches de la cellule de travail 1250.</span><span class="sxs-lookup"><span data-stu-id="48e01-113">This filters the Jobs list to display only the jobs for work cell 1250.</span></span>
    * <span data-ttu-id="48e01-114">Marquez la ligne dont le statut est Planifié.</span><span class="sxs-lookup"><span data-stu-id="48e01-114">Mark the row that has the Planned job status.</span></span>  

## <a name="complete-a-job-with-expected-quantity"></a><span data-ttu-id="48e01-115">Effectuer une tâche avec la quantité prévue</span><span class="sxs-lookup"><span data-stu-id="48e01-115">Complete a job with expected quantity</span></span>
1. <span data-ttu-id="48e01-116">Développez ou réduisez la section Détails.</span><span class="sxs-lookup"><span data-stu-id="48e01-116">Expand or collapse the Details section.</span></span>
    * <span data-ttu-id="48e01-117">Cette section affiche des informations importantes sur le numéro de carte, le numéro d’article, la quantité commandée et le nom de l’activité.</span><span class="sxs-lookup"><span data-stu-id="48e01-117">This section displays important information about card number, item number, quantity ordered, and activity name.</span></span>  
2. <span data-ttu-id="48e01-118">Développez ou réduisez la section Instructions de production.</span><span class="sxs-lookup"><span data-stu-id="48e01-118">Expand or collapse the Production instructions section.</span></span>
    * <span data-ttu-id="48e01-119">Cette section affiche les instructions de production pour l’activité.</span><span class="sxs-lookup"><span data-stu-id="48e01-119">This section displays production instructions for the activity.</span></span> <span data-ttu-id="48e01-120">Il peut s’agir d’un texte, d’images, de dessins et d’autres documents.</span><span class="sxs-lookup"><span data-stu-id="48e01-120">The instructions can be text, pictures, drawings, and other documents.</span></span>  
3. <span data-ttu-id="48e01-121">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="48e01-121">Click Start.</span></span>
    * <span data-ttu-id="48e01-122">Sélectionnez une tâche qui n’est pas terminée.</span><span class="sxs-lookup"><span data-stu-id="48e01-122">Select a job that is not completed.</span></span> <span data-ttu-id="48e01-123">Utilisez les icônes de statut dans le champ Statut de tâche pour afficher le statut de la tâche.</span><span class="sxs-lookup"><span data-stu-id="48e01-123">Use status icons in the Job status field to view job status.</span></span>      
4. <span data-ttu-id="48e01-124">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="48e01-124">Click Complete.</span></span>
    * <span data-ttu-id="48e01-125">La tâche est exécutée avec la qualité prévue.</span><span class="sxs-lookup"><span data-stu-id="48e01-125">The job is completed with the expected quality.</span></span>  

## <a name="complete-a-job-with-errors"></a><span data-ttu-id="48e01-126">Effectuer une tâche avec des erreurs</span><span class="sxs-lookup"><span data-stu-id="48e01-126">Complete a job with errors</span></span>
1. <span data-ttu-id="48e01-127">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="48e01-127">Click Start.</span></span>
    * <span data-ttu-id="48e01-128">Lorsqu’une tâche est terminée, la tâche suivante dans la liste est activée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="48e01-128">When a job is completed, the next job on the list is selected automatically.</span></span> <span data-ttu-id="48e01-129">C’est pourquoi vous n’avez pas à sélectionner une tâche avant de cliquer sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="48e01-129">This is why you don't need to select a job before you click Start.</span></span>  
2. <span data-ttu-id="48e01-130">Dans le volet Actions, cliquez sur Fabrication.</span><span class="sxs-lookup"><span data-stu-id="48e01-130">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="48e01-131">Cliquez sur Terminer (détails).</span><span class="sxs-lookup"><span data-stu-id="48e01-131">Click Complete (details).</span></span>
4. <span data-ttu-id="48e01-132">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="48e01-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="48e01-133">Entrez un nombre dans le champ Quantité erronée.</span><span class="sxs-lookup"><span data-stu-id="48e01-133">In the Error quantity field, enter a number.</span></span>
6. <span data-ttu-id="48e01-134">Entrez un nombre dans le champ Quantité correcte.</span><span class="sxs-lookup"><span data-stu-id="48e01-134">In the Good quantity field, enter a number.</span></span>
7. <span data-ttu-id="48e01-135">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="48e01-135">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]