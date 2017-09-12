---
title: "Éléments du workflow"
description: "Cet article décrit les divers éléments qui constituent un workflow."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 5620a91ff9f300bed782170307a295ab79fc5b2e
ms.contentlocale: fr-fr
ms.lasthandoff: 07/18/2017

---

# <a name="workflow-elements"></a><span data-ttu-id="02ac6-103">Éléments du workflow</span><span class="sxs-lookup"><span data-stu-id="02ac6-103">Workflow elements</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="02ac6-104">Cet article décrit les divers éléments qui constituent un workflow.</span><span class="sxs-lookup"><span data-stu-id="02ac6-104">This article describes the various elements that make up a workflow.</span></span>

<span data-ttu-id="02ac6-105">Un workflow consiste en des éléments.</span><span class="sxs-lookup"><span data-stu-id="02ac6-105">A workflow consists of elements.</span></span> <span data-ttu-id="02ac6-106">Les sections suivantes décrivent chaque type d'élément.</span><span class="sxs-lookup"><span data-stu-id="02ac6-106">The sections that follow describe each type of element.</span></span>

## <a name="tasks"></a><span data-ttu-id="02ac6-107">Tâches</span><span class="sxs-lookup"><span data-stu-id="02ac6-107">Tasks</span></span>
<span data-ttu-id="02ac6-108">Une *tâche* est une unité de travail qui doit être réalisée.</span><span class="sxs-lookup"><span data-stu-id="02ac6-108">A *task* is a unit of work that must be performed.</span></span> <span data-ttu-id="02ac6-109">Deux types de tâche peuvent être ajoutés à un workflow : des tâches manuelles et des tâches automatiques.</span><span class="sxs-lookup"><span data-stu-id="02ac6-109">Two types of tasks can be added to a workflow: manual tasks and automated tasks.</span></span>

### <a name="manual-task"></a><span data-ttu-id="02ac6-110">Tâche manuelle</span><span class="sxs-lookup"><span data-stu-id="02ac6-110">Manual task</span></span>

<span data-ttu-id="02ac6-111">Une *tâche manuelle* est une unité de travail qui doit être réalisée par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="02ac6-111">A *manual task* is a unit of work that must be performed by a user.</span></span> <span data-ttu-id="02ac6-112">Par exemple, un workflow d'état de dépenses peut comporter des tâches manuelles qui nécessitent les actions suivantes des utilisateurs affectés :</span><span class="sxs-lookup"><span data-stu-id="02ac6-112">For example, an expense report workflow can have manual tasks that require the assigned users to complete the following actions:</span></span>

-   <span data-ttu-id="02ac6-113">révision des reçus soumis avec un état de dépenses ;</span><span class="sxs-lookup"><span data-stu-id="02ac6-113">Review the receipts that are submitted together with an expense report.</span></span>
-   <span data-ttu-id="02ac6-114">appel du responsable d'un employé.</span><span class="sxs-lookup"><span data-stu-id="02ac6-114">Call an employee's manager.</span></span>

### <a name="automated-task"></a><span data-ttu-id="02ac6-115">Tâche automatique</span><span class="sxs-lookup"><span data-stu-id="02ac6-115">Automated task</span></span>

<span data-ttu-id="02ac6-116">Une *tâche automatique* est une unité de travail qui doit être réalisée par le système.</span><span class="sxs-lookup"><span data-stu-id="02ac6-116">An *automated task* is a unit of work that must be performed by the system.</span></span> <span data-ttu-id="02ac6-117">Aucune intervention n'est requise.</span><span class="sxs-lookup"><span data-stu-id="02ac6-117">No human interaction is required.</span></span> <span data-ttu-id="02ac6-118">Par exemple, un workflow de commande client peut comporter des tâches automatiques qui nécessitent les actions suivantes du système :</span><span class="sxs-lookup"><span data-stu-id="02ac6-118">For example, a sales order workflow can have automated tasks that require the system to complete the following actions:</span></span>

-   <span data-ttu-id="02ac6-119">vérification d'un crédit ;</span><span class="sxs-lookup"><span data-stu-id="02ac6-119">Perform a credit check.</span></span>
-   <span data-ttu-id="02ac6-120">création d'un enregistrement client pour le client, s'il n'en existe pas déjà un.</span><span class="sxs-lookup"><span data-stu-id="02ac6-120">Create a customer record for the customer, if a record doesn't already exist.</span></span>

## <a name="approval-processes"></a><span data-ttu-id="02ac6-121">Processus d'approbation</span><span class="sxs-lookup"><span data-stu-id="02ac6-121">Approval processes</span></span>
<span data-ttu-id="02ac6-122">Un *processus d'approbation* est un processus qui consiste en différentes étapes.</span><span class="sxs-lookup"><span data-stu-id="02ac6-122">An *approval process* is a process that consists of separate steps.</span></span> <span data-ttu-id="02ac6-123">À chaque étape d'approbation, l'utilisateur peut effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="02ac6-123">At each approval step, the user can perform the following actions:</span></span>

-   <span data-ttu-id="02ac6-124">approuver le document ;</span><span class="sxs-lookup"><span data-stu-id="02ac6-124">Approve the document.</span></span>
-   <span data-ttu-id="02ac6-125">rejeter le document ;</span><span class="sxs-lookup"><span data-stu-id="02ac6-125">Reject the document.</span></span>
-   <span data-ttu-id="02ac6-126">demander une modification du document ;</span><span class="sxs-lookup"><span data-stu-id="02ac6-126">Request a change to the document.</span></span>
-   <span data-ttu-id="02ac6-127">affecter le document à un autre utilisateur pour approbation.</span><span class="sxs-lookup"><span data-stu-id="02ac6-127">Assign the document to another user for approval.</span></span>

## <a name="lineitem-workflow-elements"></a><span data-ttu-id="02ac6-128">Éléments de workflow pour ligne</span><span class="sxs-lookup"><span data-stu-id="02ac6-128">Lineitem workflow elements</span></span>
<span data-ttu-id="02ac6-129">Vous pouvez créer un workflow pour traiter des documents ou les lignes d'un document.</span><span class="sxs-lookup"><span data-stu-id="02ac6-129">A workflow can be created to process either documents or the line items on a document.</span></span> <span data-ttu-id="02ac6-130">Par exemple, vous avez créé un workflow d'approbation pour des feuilles de temps.</span><span class="sxs-lookup"><span data-stu-id="02ac6-130">For example, you've created an approval workflow for timesheets.</span></span> <span data-ttu-id="02ac6-131">(Nous appellerons ce workflow le *workflow de document*.) Il est possible d'y ajouter un élément de *workflow pour ligne*.</span><span class="sxs-lookup"><span data-stu-id="02ac6-131">(We will refer to this workflow as the *document workflow*.) You can add a *line-item workflow* element to that document workflow.</span></span> <span data-ttu-id="02ac6-132">Lorsque l'élément de ligne est exécuté, chaque ligne du document est soumise pour traitement.</span><span class="sxs-lookup"><span data-stu-id="02ac6-132">When the line-item element is run, each line item on the document is submitted for processing.</span></span> <span data-ttu-id="02ac6-133">Vous pouvez décider de faire traiter toutes les lignes par le même workflow pour ligne ou chaque ligne par un workflow pour ligne différent.</span><span class="sxs-lookup"><span data-stu-id="02ac6-133">You might want all the line items to be processed by the same line-item workflow, or you might want each line item to be processed by a different line-item workflow.</span></span> <span data-ttu-id="02ac6-134">Imaginons qu'un employé ait soumis une feuille de temps semblable à celle de la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="02ac6-134">Imagine that an employee has submitted a timesheet that resembles the following figure.</span></span> <span data-ttu-id="02ac6-135">![Workflow avec lignes](./media/workflow_lineitemworkflow.gif) Dans ce scénario, vous pouvez créer les workflows pour ligne suivants :</span><span class="sxs-lookup"><span data-stu-id="02ac6-135">![Workflow with line items](./media/workflow_lineitemworkflow.gif) In this scenario, you might want to create the following line-item workflows:</span></span>

-   <span data-ttu-id="02ac6-136">**Workflow pour ligne 1** – Ce workflow permet de traiter les lignes dont l'ID projet est 1111.</span><span class="sxs-lookup"><span data-stu-id="02ac6-136">**Line-item workflow 1** – This workflow is used to process line items where the project ID is 1111.</span></span>
-   <span data-ttu-id="02ac6-137">**Workflow pour ligne 2** – Ce workflow permet de traiter les lignes dont l'ID projet est 2222.</span><span class="sxs-lookup"><span data-stu-id="02ac6-137">**Line-item workflow 2** – This workflow is used to process line items where the project ID is 2222.</span></span>
-   <span data-ttu-id="02ac6-138">**Workflow pour ligne 3** – Ce workflow permet de traiter les lignes dont l'ID projet est 3333.</span><span class="sxs-lookup"><span data-stu-id="02ac6-138">**Line-item workflow 3** – This workflow is used to process line items where the project ID is 3333.</span></span>

## <a name="flowcontrol-elements"></a><span data-ttu-id="02ac6-139">Éléments de contrôle des flux</span><span class="sxs-lookup"><span data-stu-id="02ac6-139">Flowcontrol elements</span></span>
<span data-ttu-id="02ac6-140">Les éléments suivants permettent de concevoir des workflows avec des branches secondaires ou avec des branches qui s'exécutent simultanément.</span><span class="sxs-lookup"><span data-stu-id="02ac6-140">The following elements let you design workflows that have alternate branches or branches that run at the same time.</span></span>

### <a name="manual-decision"></a><span data-ttu-id="02ac6-141">Décision manuelle</span><span class="sxs-lookup"><span data-stu-id="02ac6-141">Manual decision</span></span>

<span data-ttu-id="02ac6-142">Une *décision manuelle* est un point où un workflow se divise en deux branches.</span><span class="sxs-lookup"><span data-stu-id="02ac6-142">A *manual decision* is a point where a workflow divides into two branches.</span></span> <span data-ttu-id="02ac6-143">Un utilisateur doit prendre une décision qui détermine la branche utilisée pour traiter le document soumis.</span><span class="sxs-lookup"><span data-stu-id="02ac6-143">A user must make a decision, and this decision determines which branch is used to process the document that was submitted.</span></span>

### <a name="conditional-decision"></a><span data-ttu-id="02ac6-144">Décision conditionnelle</span><span class="sxs-lookup"><span data-stu-id="02ac6-144">Conditional decision</span></span>

<span data-ttu-id="02ac6-145">Une *décision conditionnelle* est également un point où un workflow se divise en deux branches.</span><span class="sxs-lookup"><span data-stu-id="02ac6-145">A *conditional decision* is also a point where a workflow divides into two branches.</span></span> <span data-ttu-id="02ac6-146">Toutefois, le système détermine la branche utilisée pour traiter le document soumis.</span><span class="sxs-lookup"><span data-stu-id="02ac6-146">However, the system decides which branch is used to process the document that was submitted.</span></span> <span data-ttu-id="02ac6-147">Pour prendre cette décision, le système évalue le document pour déterminer s'il répond aux conditions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="02ac6-147">To make this decision, the system evaluates the document to determine whether it meets specified conditions.</span></span>

### <a name="parallel-activity"></a><span data-ttu-id="02ac6-148">Activité parallèle</span><span class="sxs-lookup"><span data-stu-id="02ac6-148">Parallel activity</span></span>

<span data-ttu-id="02ac6-149">Une *activité parallèle* est un élément de workflow qui inclut deux branches de workflow ou plus s'exécutant simultanément.</span><span class="sxs-lookup"><span data-stu-id="02ac6-149">A *parallel activity* is a workflow element that includes two or more workflow branches that run at the same time.</span></span>

### <a name="subworkflow"></a><span data-ttu-id="02ac6-150">Sous-workflow</span><span class="sxs-lookup"><span data-stu-id="02ac6-150">Subworkflow</span></span>

<span data-ttu-id="02ac6-151">Un *sous-workflow* est un workflow qui s'exécute dans le contexte d'un autre workflow.</span><span class="sxs-lookup"><span data-stu-id="02ac6-151">A *subworkflow* is a workflow that runs in the context of another workflow.</span></span>




