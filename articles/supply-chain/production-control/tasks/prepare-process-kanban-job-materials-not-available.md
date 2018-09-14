--- 
title: "Préparer une tâche de kanban de processus lorsque les matières ne sont pas disponibles pour la cellule de travail"
description: "Cette procédure se concentre sur la préparation d'une tâche de kanban de processus lorsque certaines matières sont disponibles pour la cellule de travail par conséquent, il est nécessaire de prélever des matières de l'entrepôt."
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardWorkCell
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
ms.openlocfilehash: f7e7eb46bda13ef7e72189f921686a9889a8773c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a><span data-ttu-id="d9116-103">Préparer une tâche de kanban de processus lorsque les matières ne sont pas disponibles pour la cellule de travail</span><span class="sxs-lookup"><span data-stu-id="d9116-103">Prepare a process kanban job when materials are not available for the work cell</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d9116-104">Cette procédure se concentre sur la préparation d'une tâche de kanban de processus lorsque certaines matières sont disponibles pour la cellule de travail par conséquent, il est nécessaire de prélever des matières de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d9116-104">This procedure focuses on preparing a process kanban job when some materials are not available for the work cell, therefore it's necessary to pick materials from the warehouse.</span></span> <span data-ttu-id="d9116-105">La procédure « Préparer une tâche de kanban de processus lorsque les matières sont disponibles » est une étape préliminaire à la création de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="d9116-105">The procedure "Prepare a process kanban job when materials are available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="d9116-106">Cette procédure est destinée à l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="d9116-106">This procedure is intended for the machine operator.</span></span> <span data-ttu-id="d9116-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="d9116-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="d9116-108">Accédez à Contrôle de la production > Kanban > Tableau kanban pour les opérations de traitement.</span><span class="sxs-lookup"><span data-stu-id="d9116-108">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="d9116-109">Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="d9116-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="d9116-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d9116-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d9116-111">Sélectionnez la cellule de travail 1250.</span><span class="sxs-lookup"><span data-stu-id="d9116-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="d9116-112">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d9116-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d9116-113">Sélectionnez Kanban 000356.</span><span class="sxs-lookup"><span data-stu-id="d9116-113">Select Kanban 000356.</span></span>  
5. <span data-ttu-id="d9116-114">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d9116-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d9116-115">Dans la liste, désélectionnez la ligne 4</span><span class="sxs-lookup"><span data-stu-id="d9116-115">In the list, deselect row 4.</span></span> <span data-ttu-id="d9116-116">ou sélectionnez-la si vous n'avez pas terminé la tâche « Préparer une tâche de kanban de processus lorsque les matières sont disponibles ».</span><span class="sxs-lookup"><span data-stu-id="d9116-116">or Select row 4 if you haven't completed the task "Prepare a process kanban job when materials are available."</span></span>  
6. <span data-ttu-id="d9116-117">Activez ou désactivez l'extension de la section Prélèvements.</span><span class="sxs-lookup"><span data-stu-id="d9116-117">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="d9116-118">L'icône Aucune entrée dans le statut d'approvisionnement indique qu'il manque 48 ea dans l'article P0002 pour la cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="d9116-118">The No entry icon in the supply status indicates that 48 ea of item P0002 are missing for the work cell.</span></span>  

## <a name="transfer-materials-to-work-cell"></a><span data-ttu-id="d9116-119">Transférer les matériaux à la cellule de travail</span><span class="sxs-lookup"><span data-stu-id="d9116-119">Transfer materials to work cell</span></span>
1. <span data-ttu-id="d9116-120">Activez ou désactivez l'extension de la section Tâches de transfert.</span><span class="sxs-lookup"><span data-stu-id="d9116-120">Toggle the expansion of the Transfer jobs section.</span></span>
2. <span data-ttu-id="d9116-121">Utilisez le filtre rapide pour filtrer sur le champ Numéro d'article avec une valeur de « P0002 ».</span><span class="sxs-lookup"><span data-stu-id="d9116-121">Use the Quick Filter to filter on the Item number field with a value of 'P0002'.</span></span>
3. <span data-ttu-id="d9116-122">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d9116-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="d9116-123">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="d9116-123">Click Start.</span></span>
    * <span data-ttu-id="d9116-124">Le transfert est en cours.</span><span class="sxs-lookup"><span data-stu-id="d9116-124">Transfer is in progress.</span></span>  
5. <span data-ttu-id="d9116-125">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="d9116-125">Click Complete.</span></span>
    * <span data-ttu-id="d9116-126">L'article P0002 est à présent disponible dans les prélèvements pour la tâche de kanban.</span><span class="sxs-lookup"><span data-stu-id="d9116-126">Item P0002 is now available in the picking list for the kanban job.</span></span> <span data-ttu-id="d9116-127">Cela signifie que nous pouvons préparer le kanban avec toutes les matériaux nécessaires.</span><span class="sxs-lookup"><span data-stu-id="d9116-127">This means that we can prepare the kanban with all the needed materials.</span></span>  
6. <span data-ttu-id="d9116-128">Cliquez sur Préparer.</span><span class="sxs-lookup"><span data-stu-id="d9116-128">Click Prepare.</span></span>
    * <span data-ttu-id="d9116-129">Notez qu'une icône dans le statut de la tâche indique que la tâche est désormais prête.</span><span class="sxs-lookup"><span data-stu-id="d9116-129">Notice that an icon in the Job status indicates that the job is now ready.</span></span>  


