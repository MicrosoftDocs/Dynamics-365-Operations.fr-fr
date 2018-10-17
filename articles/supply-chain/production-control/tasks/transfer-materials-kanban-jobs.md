--- 
title: "Transférer des matériaux avec des tâches de kanban"
description: "Cette procédure traite de l'exécution d'une tâche de kanban de prélèvement pour transférer des matériaux."
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: a2db7b9fb960beb5b4a851aabb9f28a0f9e3d3da
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="transfer-materials-with-kanban-jobs"></a><span data-ttu-id="d8d06-103">Transférer des matériaux avec des tâches de kanban</span><span class="sxs-lookup"><span data-stu-id="d8d06-103">Transfer materials with kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d8d06-104">Cette procédure traite de l'exécution d'une tâche de kanban de prélèvement pour transférer des matériaux.</span><span class="sxs-lookup"><span data-stu-id="d8d06-104">This procedure focuses on executing a withdrawal kanban job to transfer materials.</span></span> <span data-ttu-id="d8d06-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="d8d06-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d8d06-106">Cette procédure est destinée au magasinier.</span><span class="sxs-lookup"><span data-stu-id="d8d06-106">This procedure is intended for the warehouse worker.</span></span>


## <a name="display-transfer-jobs"></a><span data-ttu-id="d8d06-107">Afficher les opérations de transfert</span><span class="sxs-lookup"><span data-stu-id="d8d06-107">Display transfer jobs</span></span>
1. <span data-ttu-id="d8d06-108">Allez dans Contrôle de la production > Kanban > Tableau kanban pour les opérations de transfert.</span><span class="sxs-lookup"><span data-stu-id="d8d06-108">Go to Production control > Kanban > Kanban board for transfer jobs.</span></span>
2. <span data-ttu-id="d8d06-109">Développez ou réduisez la section Filtres.</span><span class="sxs-lookup"><span data-stu-id="d8d06-109">Expand or collapse the Filters section.</span></span>
    * <span data-ttu-id="d8d06-110">Dans la section Filtres, vous pouvez spécifier les tâches que vous souhaitez afficher en filtrant sur Flux de production, Nom de l'activité, Entrepôt d'origine et Emplacement, et Entrepôt de destination et emplacement.</span><span class="sxs-lookup"><span data-stu-id="d8d06-110">In the Filters section, you can specify what jobs you want to see by filtering on Production flow, Activity name, From warehouse and location, and To warehouse and location.</span></span>  
3. <span data-ttu-id="d8d06-111">Tapez « 11 » dans le champ Entrepôt d'origine.</span><span class="sxs-lookup"><span data-stu-id="d8d06-111">In the From warehouse field, type '11'.</span></span>
4. <span data-ttu-id="d8d06-112">Tapez « 12 » dans le champ Lieu de destination.</span><span class="sxs-lookup"><span data-stu-id="d8d06-112">In the To location field, type '12'.</span></span>

## <a name="start-a-transfer-job"></a><span data-ttu-id="d8d06-113">Commencer une tâche de transfert</span><span class="sxs-lookup"><span data-stu-id="d8d06-113">Start a transfer job</span></span>
1. <span data-ttu-id="d8d06-114">Dans la liste, désélectionnez la ligne sélectionnée, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="d8d06-114">In the list, deselect the selected row - if any.</span></span>
2. <span data-ttu-id="d8d06-115">Sélectionnez la ligne 4 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="d8d06-115">In the list, select row 4.</span></span>
    * <span data-ttu-id="d8d06-116">Sélectionnez la première tâche ayant le statut Non planifié.</span><span class="sxs-lookup"><span data-stu-id="d8d06-116">Select the first job with status Not planned.</span></span> <span data-ttu-id="d8d06-117">Assurez-vous que c'est la seule tâche sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d8d06-117">Make sure this is the only job selected.</span></span>  
3. <span data-ttu-id="d8d06-118">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="d8d06-118">Click Start.</span></span>
    * <span data-ttu-id="d8d06-119">Notez qu'une icône indique que la tâche a commencé.</span><span class="sxs-lookup"><span data-stu-id="d8d06-119">Notice that an icon indicates that the job is started.</span></span>  

## <a name="select-a-second-transfer-job-and-change-quantity"></a><span data-ttu-id="d8d06-120">Sélectionner une deuxième opération de transfert et modifier la quantité</span><span class="sxs-lookup"><span data-stu-id="d8d06-120">Select a second transfer job and change quantity</span></span>
1. <span data-ttu-id="d8d06-121">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d8d06-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d8d06-122">Vous pouvez avoir plusieurs tâches sélectionnées, mais pour l'instant, sélectionnez la ligne 5.</span><span class="sxs-lookup"><span data-stu-id="d8d06-122">You can have multiple jobs selected, but for now select row 5.</span></span>  
2. <span data-ttu-id="d8d06-123">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d8d06-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d8d06-124">Vérifiez que la tâche de l'étape précédente est la seule sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d8d06-124">Make sure the job in the previous step is the only one selected.</span></span> <span data-ttu-id="d8d06-125">Désélectionnez toutes les autres tâches.</span><span class="sxs-lookup"><span data-stu-id="d8d06-125">Deselect all other jobs.</span></span>  
3. <span data-ttu-id="d8d06-126">Notez la valeur du champ Quantité de tâches pour la consulter plus tard</span><span class="sxs-lookup"><span data-stu-id="d8d06-126">Note the value in the Job quantity field to reference later</span></span>
4. <span data-ttu-id="d8d06-127">Définissez la quantité de tâches sur 30.</span><span class="sxs-lookup"><span data-stu-id="d8d06-127">Set Job quantity to '30'.</span></span>
    * <span data-ttu-id="d8d06-128">Notez l'avertissement !</span><span class="sxs-lookup"><span data-stu-id="d8d06-128">Notice the warning!</span></span> <span data-ttu-id="d8d06-129">Vous n'êtes pas autorisé à transférer 30.</span><span class="sxs-lookup"><span data-stu-id="d8d06-129">You are not allowed to transfer 30.</span></span> <span data-ttu-id="d8d06-130">En fonction du paramétrage de la règle de kanban, vous pouvez uniquement transférer la quantité originale.</span><span class="sxs-lookup"><span data-stu-id="d8d06-130">According to the setup of the kanban rule, you can only transfer the original quantity.</span></span>  
5. <span data-ttu-id="d8d06-131">Utiliser la valeur notée précédemment dans le champ Quantité de tâches</span><span class="sxs-lookup"><span data-stu-id="d8d06-131">Use the value noted previously in the Job quantity field</span></span>
    * <span data-ttu-id="d8d06-132">Définissez la quantité de tâches sur la valeur précédente.</span><span class="sxs-lookup"><span data-stu-id="d8d06-132">Set the Job quantity to the previous value.</span></span>  

## <a name="start-the-second-transfer-job"></a><span data-ttu-id="d8d06-133">Démarrer la deuxième opération de transfert</span><span class="sxs-lookup"><span data-stu-id="d8d06-133">Start the second transfer job</span></span>
1. <span data-ttu-id="d8d06-134">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="d8d06-134">Click Start.</span></span>
    * <span data-ttu-id="d8d06-135">Cela débute le transfert de la tâche dans la ligne 5.</span><span class="sxs-lookup"><span data-stu-id="d8d06-135">This will start the transfer of the job in row 5.</span></span>  

## <a name="complete-both-transfer-jobs"></a><span data-ttu-id="d8d06-136">Terminer les deux tâches de transfert</span><span class="sxs-lookup"><span data-stu-id="d8d06-136">Complete both transfer jobs</span></span>
1. <span data-ttu-id="d8d06-137">Sélectionnez la ligne 4 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="d8d06-137">In the list, select row 4.</span></span>
    * <span data-ttu-id="d8d06-138">Désormais deux tâches de transfert sont sélectionnées sur la ligne 4 et la ligne 5.</span><span class="sxs-lookup"><span data-stu-id="d8d06-138">Now two transfer jobs are selected on row 4 and row 5.</span></span>  
2. <span data-ttu-id="d8d06-139">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="d8d06-139">Click Complete.</span></span>
    * <span data-ttu-id="d8d06-140">Le transfert des deux tâches est alors terminé.</span><span class="sxs-lookup"><span data-stu-id="d8d06-140">This will complete the transfer of both jobs.</span></span>  


