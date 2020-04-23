---
title: Rétablir le statut de l'opération kanban
description: Cette procédure traite du rétablissement d'un statut de tâche de kanban incorrect.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: adf65175669d4cd5ec4cb431a7e1436ea3da83ed
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210502"
---
# <a name="revert-kanban-job-status"></a><span data-ttu-id="eaafb-103">Rétablir le statut de l'opération kanban</span><span class="sxs-lookup"><span data-stu-id="eaafb-103">Revert kanban job status</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eaafb-104">Cette procédure traite du rétablissement d'un statut de tâche de kanban incorrect.</span><span class="sxs-lookup"><span data-stu-id="eaafb-104">This procedure focuses on reverting an incorrect kanban job status.</span></span> <span data-ttu-id="eaafb-105">Cela est utile au cas où l'opérateur mettrait à jour la tâche incorrecte, ou définirait le statut incorrect par erreur.</span><span class="sxs-lookup"><span data-stu-id="eaafb-105">This is useful in case the machine operator updates the wrong job, or sets the wrong status by mistake.</span></span> <span data-ttu-id="eaafb-106">Dans cette procédure, une tâche de kanban est enregistrée comme préparée par erreur, et le statut est rétabli.</span><span class="sxs-lookup"><span data-stu-id="eaafb-106">In this procedure, a kanban job is registered as prepared by mistake, and the status is reverted.</span></span> <span data-ttu-id="eaafb-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="eaafb-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="eaafb-108">Cette procédure est destinée au responsable de magasin ou à l'opérateur travaillant pour une société de lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="eaafb-108">This procedure is intended for the shop supervisor or machine operator working in a lean manufacturing company.</span></span>


## <a name="open-process-board-for-the-work-cell"></a><span data-ttu-id="eaafb-109">Ouvrir le tableau de traitement pour la cellule de travail</span><span class="sxs-lookup"><span data-stu-id="eaafb-109">Open process board for the work cell</span></span>
1. <span data-ttu-id="eaafb-110">Allez dans le tableau kanban pour les opérations de traitement.</span><span class="sxs-lookup"><span data-stu-id="eaafb-110">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="eaafb-111">Dans le champ Cellule de travail, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="eaafb-111">In the Work cell field, enter or select a value.</span></span>
    * <span data-ttu-id="eaafb-112">Sélectionnez la cellule de travail 1260.</span><span class="sxs-lookup"><span data-stu-id="eaafb-112">Select work cell 1260.</span></span>  

## <a name="prepare-kanban-job"></a><span data-ttu-id="eaafb-113">Préparer une tâche de kanban</span><span class="sxs-lookup"><span data-stu-id="eaafb-113">Prepare kanban job</span></span>
1. <span data-ttu-id="eaafb-114">Cliquez sur Préparer.</span><span class="sxs-lookup"><span data-stu-id="eaafb-114">Click Prepare.</span></span>
    * <span data-ttu-id="eaafb-115">Si vous ne pouvez pas cliquer sur Préparer car l'option est grisée, assurez-vous que la tâche de kanban sélectionnée a le statut Planifiée, qui est indiqué par l'icône de kanban vide.</span><span class="sxs-lookup"><span data-stu-id="eaafb-115">If you can't click Prepare because it is grayed out, make sure that the selected kanban job has status Planned, which is indicated by the empty kanban icon.</span></span> <span data-ttu-id="eaafb-116">Si la préparation échoue, vérifiez que toutes les matières des prélèvements sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="eaafb-116">If Prepare fails, make sure that all materials in the Picking list are available.</span></span>  
2. <span data-ttu-id="eaafb-117">Dans la liste, sélectionnez la tâche préparée.</span><span class="sxs-lookup"><span data-stu-id="eaafb-117">In the list, select the prepared job.</span></span>
    * <span data-ttu-id="eaafb-118">Sélectionnez la première tâche que vous venez de préparer.</span><span class="sxs-lookup"><span data-stu-id="eaafb-118">Select the first job that you have just prepared.</span></span>  
    * <span data-ttu-id="eaafb-119">Remarquez que le statut des tâches est Préparée, ce qui est signalé par un triangle à l'intérieur de l'icône de kanban.</span><span class="sxs-lookup"><span data-stu-id="eaafb-119">Notice that the jobs status is prepared, which is indicated with a triangle inside the kanban icon.</span></span>  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a><span data-ttu-id="eaafb-120">Rétablir le statut de la tâche de kanban préparée</span><span class="sxs-lookup"><span data-stu-id="eaafb-120">Revert the status of the prepared kanban job</span></span>
1. <span data-ttu-id="eaafb-121">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="eaafb-121">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="eaafb-122">Sélectionnez la première tâche ayant été préparée.</span><span class="sxs-lookup"><span data-stu-id="eaafb-122">Select the first job that was prepared.</span></span>  
2. <span data-ttu-id="eaafb-123">Dans le volet Actions, cliquez sur Fabrication.</span><span class="sxs-lookup"><span data-stu-id="eaafb-123">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="eaafb-124">Cliquez sur Rétablir le statut.</span><span class="sxs-lookup"><span data-stu-id="eaafb-124">Click Revert status.</span></span>
    * <span data-ttu-id="eaafb-125">Vous pouvez utiliser une autre règle de kanban lorsque les conditions suivantes sont remplies : - La stratégie de réapprovisionnement est la même pour les deux règles.</span><span class="sxs-lookup"><span data-stu-id="eaafb-125">You can use an alternative kanban rule when the following conditions are true:  - The replenishment strategy is the same for both rules.</span></span>  <span data-ttu-id="eaafb-126">- La version du flux de production est la même pour les deux règles.</span><span class="sxs-lookup"><span data-stu-id="eaafb-126">- The version of the production flow is the same for both rules.</span></span>  <span data-ttu-id="eaafb-127">- Le produit qui est fourni est identique pour les deux règles.</span><span class="sxs-lookup"><span data-stu-id="eaafb-127">- The product that is supplied is the same for both rules.</span></span>  <span data-ttu-id="eaafb-128">- Toutes les activités en aval qui sont configurées pour la dernière activité des règles de kanban doivent être identiques pour les deux règles.</span><span class="sxs-lookup"><span data-stu-id="eaafb-128">- Any downstream activities that are configured for the last activity of the kanban rules must be the same for both rules.</span></span>  <span data-ttu-id="eaafb-129">- Les mêmes dimensions de stock fournies doivent être configurées pour les deux règles.</span><span class="sxs-lookup"><span data-stu-id="eaafb-129">- The same supplied inventory dimensions must be configured for both rules.</span></span>  <span data-ttu-id="eaafb-130">- Le statut de l'unité de manutention doit être Non affecté.</span><span class="sxs-lookup"><span data-stu-id="eaafb-130">- The status of the handling unit must be Not assigned.</span></span>  <span data-ttu-id="eaafb-131">- Les configurations des kanbans d'événement doivent être identique.</span><span class="sxs-lookup"><span data-stu-id="eaafb-131">- The configuration for event kanbans must be the same.</span></span>  
    * <span data-ttu-id="eaafb-132">Vérifiez que le nouveau statut est Planifié.</span><span class="sxs-lookup"><span data-stu-id="eaafb-132">Ensure that the new status is Planned.</span></span>  
4. <span data-ttu-id="eaafb-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="eaafb-133">Click OK.</span></span>
5. <span data-ttu-id="eaafb-134">Dans la liste, désactiver la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="eaafb-134">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="eaafb-135">Sélectionnez la même tâche.</span><span class="sxs-lookup"><span data-stu-id="eaafb-135">Select the same job.</span></span>  
    * <span data-ttu-id="eaafb-136">Remarquez que le statut de la tâche de kanban est revenu à Planifiée, ce qui est signalé par une icône de kanban vide.</span><span class="sxs-lookup"><span data-stu-id="eaafb-136">Notice that the job status for the kanban job is reverted to Planned, which is indicated by an empty kanban icon.</span></span>  

