---
title: Rétablir le statut de l'opération kanban
description: Cette procédure traite du rétablissement d'un statut de tâche de kanban incorrect.
author: ShylaThompson
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
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 27874f89cede151b52b869fa0d58e320d548e6d3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562205"
---
# <a name="revert-kanban-job-status"></a><span data-ttu-id="0591b-103">Rétablir le statut de l'opération kanban</span><span class="sxs-lookup"><span data-stu-id="0591b-103">Revert kanban job status</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0591b-104">Cette procédure traite du rétablissement d'un statut de tâche de kanban incorrect.</span><span class="sxs-lookup"><span data-stu-id="0591b-104">This procedure focuses on reverting an incorrect kanban job status.</span></span> <span data-ttu-id="0591b-105">Cela est utile au cas où l'opérateur mettrait à jour la tâche incorrecte, ou définirait le statut incorrect par erreur.</span><span class="sxs-lookup"><span data-stu-id="0591b-105">This is useful in case the machine operator updates the wrong job, or sets the wrong status by mistake.</span></span> <span data-ttu-id="0591b-106">Dans cette procédure, une tâche de kanban est enregistrée comme préparée par erreur, et le statut est rétabli.</span><span class="sxs-lookup"><span data-stu-id="0591b-106">In this procedure, a kanban job is registered as prepared by mistake, and the status is reverted.</span></span> <span data-ttu-id="0591b-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="0591b-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0591b-108">Cette procédure est destinée au responsable de magasin ou à l'opérateur travaillant pour une société de lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="0591b-108">This procedure is intended for the shop supervisor or machine operator working in a lean manufacturing company.</span></span>


## <a name="open-process-board-for-the-work-cell"></a><span data-ttu-id="0591b-109">Ouvrir le tableau de traitement pour la cellule de travail</span><span class="sxs-lookup"><span data-stu-id="0591b-109">Open process board for the work cell</span></span>
1. <span data-ttu-id="0591b-110">Allez dans le tableau kanban pour les opérations de traitement.</span><span class="sxs-lookup"><span data-stu-id="0591b-110">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="0591b-111">Dans le champ Cellule de travail, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0591b-111">In the Work cell field, enter or select a value.</span></span>
    * <span data-ttu-id="0591b-112">Sélectionnez la cellule de travail 1260.</span><span class="sxs-lookup"><span data-stu-id="0591b-112">Select work cell 1260.</span></span>  

## <a name="prepare-kanban-job"></a><span data-ttu-id="0591b-113">Préparer une tâche de kanban</span><span class="sxs-lookup"><span data-stu-id="0591b-113">Prepare kanban job</span></span>
1. <span data-ttu-id="0591b-114">Cliquez sur Préparer.</span><span class="sxs-lookup"><span data-stu-id="0591b-114">Click Prepare.</span></span>
    * <span data-ttu-id="0591b-115">Si vous ne pouvez pas cliquer sur Préparer car l'option est grisée, assurez-vous que la tâche de kanban sélectionnée a le statut Planifiée, qui est indiqué par l'icône de kanban vide.</span><span class="sxs-lookup"><span data-stu-id="0591b-115">If you can't click Prepare because it is grayed out, make sure that the selected kanban job has status Planned, which is indicated by the empty kanban icon.</span></span> <span data-ttu-id="0591b-116">Si la préparation échoue, vérifiez que toutes les matières des prélèvements sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="0591b-116">If Prepare fails, make sure that all materials in the Picking list are available.</span></span>  
2. <span data-ttu-id="0591b-117">Dans la liste, sélectionnez la tâche préparée.</span><span class="sxs-lookup"><span data-stu-id="0591b-117">In the list, select the prepared job.</span></span>
    * <span data-ttu-id="0591b-118">Sélectionnez la première tâche que vous venez de préparer.</span><span class="sxs-lookup"><span data-stu-id="0591b-118">Select the first job that you have just prepared.</span></span>  
    * <span data-ttu-id="0591b-119">Remarquez que le statut des tâches est Préparée, ce qui est signalé par un triangle à l'intérieur de l'icône de kanban.</span><span class="sxs-lookup"><span data-stu-id="0591b-119">Notice that the jobs status is prepared, which is indicated with a triangle inside the kanban icon.</span></span>  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a><span data-ttu-id="0591b-120">Rétablir le statut de la tâche de kanban préparée</span><span class="sxs-lookup"><span data-stu-id="0591b-120">Revert the status of the prepared kanban job</span></span>
1. <span data-ttu-id="0591b-121">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0591b-121">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0591b-122">Sélectionnez la première tâche ayant été préparée.</span><span class="sxs-lookup"><span data-stu-id="0591b-122">Select the first job that was prepared.</span></span>  
2. <span data-ttu-id="0591b-123">Dans le volet Actions, cliquez sur Fabrication.</span><span class="sxs-lookup"><span data-stu-id="0591b-123">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="0591b-124">Cliquez sur Rétablir le statut.</span><span class="sxs-lookup"><span data-stu-id="0591b-124">Click Revert status.</span></span>
    * <span data-ttu-id="0591b-125">Vous pouvez utiliser une autre règle de kanban lorsque les conditions suivantes sont remplies : - La stratégie de réapprovisionnement est la même pour les deux règles.</span><span class="sxs-lookup"><span data-stu-id="0591b-125">You can use an alternative kanban rule when the following conditions are true:  - The replenishment strategy is the same for both rules.</span></span>  <span data-ttu-id="0591b-126">- La version du flux de production est la même pour les deux règles.</span><span class="sxs-lookup"><span data-stu-id="0591b-126">- The version of the production flow is the same for both rules.</span></span>  <span data-ttu-id="0591b-127">- Le produit qui est fourni est identique pour les deux règles.</span><span class="sxs-lookup"><span data-stu-id="0591b-127">- The product that is supplied is the same for both rules.</span></span>  <span data-ttu-id="0591b-128">- Toutes les activités en aval qui sont configurées pour la dernière activité des règles de kanban doivent être identiques pour les deux règles.</span><span class="sxs-lookup"><span data-stu-id="0591b-128">- Any downstream activities that are configured for the last activity of the kanban rules must be the same for both rules.</span></span>  <span data-ttu-id="0591b-129">- Les mêmes dimensions de stock fournies doivent être configurées pour les deux règles.</span><span class="sxs-lookup"><span data-stu-id="0591b-129">- The same supplied inventory dimensions must be configured for both rules.</span></span>  <span data-ttu-id="0591b-130">- Le statut de l'unité de manutention doit être Non affecté.</span><span class="sxs-lookup"><span data-stu-id="0591b-130">- The status of the handling unit must be Not assigned.</span></span>  <span data-ttu-id="0591b-131">- Les configurations des kanbans d'événement doivent être identique.</span><span class="sxs-lookup"><span data-stu-id="0591b-131">- The configuration for event kanbans must be the same.</span></span>  
    * <span data-ttu-id="0591b-132">Vérifiez que le nouveau statut est Planifié.</span><span class="sxs-lookup"><span data-stu-id="0591b-132">Ensure that the new status is Planned.</span></span>  
4. <span data-ttu-id="0591b-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0591b-133">Click OK.</span></span>
5. <span data-ttu-id="0591b-134">Dans la liste, désactiver la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0591b-134">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="0591b-135">Sélectionnez la même tâche.</span><span class="sxs-lookup"><span data-stu-id="0591b-135">Select the same job.</span></span>  
    * <span data-ttu-id="0591b-136">Remarquez que le statut de la tâche de kanban est revenu à Planifiée, ce qui est signalé par une icône de kanban vide.</span><span class="sxs-lookup"><span data-stu-id="0591b-136">Notice that the job status for the kanban job is reverted to Planned, which is indicated by an empty kanban icon.</span></span>  

