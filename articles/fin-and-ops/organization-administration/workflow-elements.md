---
title: "Éléments du workflow"
description: "Cette rubrique décrit les divers éléments qui constituent un workflow."
author: sericks007
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: 15cac09a97305c1b467cbb97da2d4b8a864ccbc7
ms.contentlocale: fr-fr
ms.lasthandoff: 11/14/2017

---

# <a name="workflow-elements"></a><span data-ttu-id="f36da-103">Éléments du workflow</span><span class="sxs-lookup"><span data-stu-id="f36da-103">Workflow elements</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f36da-104">Cette rubrique décrit les divers éléments qui constituent un workflow.</span><span class="sxs-lookup"><span data-stu-id="f36da-104">This topic describes the various elements that make up a workflow.</span></span>

<span data-ttu-id="f36da-105">Un workflow est constitué d'éléments.</span><span class="sxs-lookup"><span data-stu-id="f36da-105">A workflow consists of elements.</span></span> <span data-ttu-id="f36da-106">Les sections suivantes décrivent chaque type d'élément.</span><span class="sxs-lookup"><span data-stu-id="f36da-106">The sections that follow describe each type of element.</span></span>

## <a name="tasks"></a><span data-ttu-id="f36da-107">Tâches</span><span class="sxs-lookup"><span data-stu-id="f36da-107">Tasks</span></span>
<span data-ttu-id="f36da-108">Une *tâche* est une unité de travail qui doit être réalisée.</span><span class="sxs-lookup"><span data-stu-id="f36da-108">A *task* is a unit of work that must be performed.</span></span> <span data-ttu-id="f36da-109">Deux types de tâche peuvent être ajoutés à un workflow : des tâches manuelles et des tâches automatiques.</span><span class="sxs-lookup"><span data-stu-id="f36da-109">Two types of tasks can be added to a workflow: manual tasks and automated tasks.</span></span>

### <a name="manual-task"></a><span data-ttu-id="f36da-110">Tâche manuelle</span><span class="sxs-lookup"><span data-stu-id="f36da-110">Manual task</span></span>

<span data-ttu-id="f36da-111">Une *tâche manuelle* est une unité de travail qui doit être réalisée par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f36da-111">A *manual task* is a unit of work that must be performed by a user.</span></span> <span data-ttu-id="f36da-112">Par exemple, un workflow d'état de dépenses peut comporter des tâches manuelles qui nécessitent les actions suivantes des utilisateurs affectés :</span><span class="sxs-lookup"><span data-stu-id="f36da-112">For example, an expense report workflow can have manual tasks that require the assigned users to complete the following actions:</span></span>

-   <span data-ttu-id="f36da-113">révision des reçus soumis avec un état de dépenses ;</span><span class="sxs-lookup"><span data-stu-id="f36da-113">Review the receipts that are submitted together with an expense report.</span></span>
-   <span data-ttu-id="f36da-114">appel du responsable d'un employé.</span><span class="sxs-lookup"><span data-stu-id="f36da-114">Call an employee's manager.</span></span>

### <a name="automated-task"></a><span data-ttu-id="f36da-115">Tâche automatique</span><span class="sxs-lookup"><span data-stu-id="f36da-115">Automated task</span></span>

<span data-ttu-id="f36da-116">Une *tâche automatique* est une unité de travail qui doit être réalisée par le système.</span><span class="sxs-lookup"><span data-stu-id="f36da-116">An *automated task* is a unit of work that must be performed by the system.</span></span> <span data-ttu-id="f36da-117">Aucune intervention n'est requise.</span><span class="sxs-lookup"><span data-stu-id="f36da-117">No human interaction is required.</span></span> <span data-ttu-id="f36da-118">Par exemple, un workflow de commande client peut comporter des tâches automatiques qui nécessitent les actions suivantes du système :</span><span class="sxs-lookup"><span data-stu-id="f36da-118">For example, a sales order workflow can have automated tasks that require the system to complete the following actions:</span></span>

-   <span data-ttu-id="f36da-119">vérification d'un crédit ;</span><span class="sxs-lookup"><span data-stu-id="f36da-119">Perform a credit check.</span></span>
-   <span data-ttu-id="f36da-120">création d'un enregistrement client pour le client, s'il n'en existe pas déjà un.</span><span class="sxs-lookup"><span data-stu-id="f36da-120">Create a customer record for the customer, if a record doesn't already exist.</span></span>

## <a name="approval-processes"></a><span data-ttu-id="f36da-121">Processus d'approbation</span><span class="sxs-lookup"><span data-stu-id="f36da-121">Approval processes</span></span>
<span data-ttu-id="f36da-122">Un *processus d'approbation* est un processus qui consiste en différentes étapes.</span><span class="sxs-lookup"><span data-stu-id="f36da-122">An *approval process* is a process that consists of separate steps.</span></span> <span data-ttu-id="f36da-123">À chaque étape d'approbation, l'utilisateur peut effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="f36da-123">At each approval step, the user can perform the following actions:</span></span>

-   <span data-ttu-id="f36da-124">approuver le document ;</span><span class="sxs-lookup"><span data-stu-id="f36da-124">Approve the document.</span></span>
-   <span data-ttu-id="f36da-125">rejeter le document ;</span><span class="sxs-lookup"><span data-stu-id="f36da-125">Reject the document.</span></span>
-   <span data-ttu-id="f36da-126">demander une modification du document ;</span><span class="sxs-lookup"><span data-stu-id="f36da-126">Request a change to the document.</span></span>
-   <span data-ttu-id="f36da-127">affecter le document à un autre utilisateur pour approbation.</span><span class="sxs-lookup"><span data-stu-id="f36da-127">Assign the document to another user for approval.</span></span>

## <a name="line-item-workflow-elements"></a><span data-ttu-id="f36da-128">Éléments de workflow pour ligne</span><span class="sxs-lookup"><span data-stu-id="f36da-128">Line-item workflow elements</span></span>
<span data-ttu-id="f36da-129">Vous pouvez créer un workflow pour traiter des documents ou les lignes d'un document.</span><span class="sxs-lookup"><span data-stu-id="f36da-129">A workflow can be created to process either documents or the line items on a document.</span></span> <span data-ttu-id="f36da-130">Par exemple, vous avez créé un workflow d'approbation pour des feuilles de temps.</span><span class="sxs-lookup"><span data-stu-id="f36da-130">For example, you've created an approval workflow for timesheets.</span></span> <span data-ttu-id="f36da-131">(Nous appellerons ce workflow le *workflow de document*.) Il est possible d'y ajouter un élément de *workflow pour ligne*.</span><span class="sxs-lookup"><span data-stu-id="f36da-131">(We will refer to this workflow as the *document workflow*.) You can add a *line-item workflow* element to that document workflow.</span></span> <span data-ttu-id="f36da-132">Lorsque l'élément de ligne est exécuté, chaque ligne du document est soumise pour traitement.</span><span class="sxs-lookup"><span data-stu-id="f36da-132">When the line-item element is run, each line item on the document is submitted for processing.</span></span> <span data-ttu-id="f36da-133">Vous pouvez décider de faire traiter toutes les lignes par le même workflow pour ligne ou chaque ligne par un workflow pour ligne différent.</span><span class="sxs-lookup"><span data-stu-id="f36da-133">You might want all the line items to be processed by the same line-item workflow, or you might want each line item to be processed by a different line-item workflow.</span></span> <span data-ttu-id="f36da-134">Imaginons qu'un employé ait soumis une feuille de temps semblable à celle de la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="f36da-134">Imagine that an employee has submitted a timesheet that resembles the following figure.</span></span>

![Workflow avec lignes](./media/workflow_lineitemworkflow.gif) 

<span data-ttu-id="f36da-136">Dans ce cas, il pourrait s'avérer utile de créer les workflows pour ligne suivants :</span><span class="sxs-lookup"><span data-stu-id="f36da-136">In this scenario, you might want to create the following line-item workflows:</span></span>

-   <span data-ttu-id="f36da-137">**Workflow pour ligne 1** – Ce workflow permet de traiter les lignes dont l'ID projet est 1111.</span><span class="sxs-lookup"><span data-stu-id="f36da-137">**Line-item workflow 1** – This workflow is used to process line items where the project ID is 1111.</span></span>
-   <span data-ttu-id="f36da-138">**Workflow pour ligne 2** – Ce workflow permet de traiter les lignes dont l'ID projet est 2222.</span><span class="sxs-lookup"><span data-stu-id="f36da-138">**Line-item workflow 2** – This workflow is used to process line items where the project ID is 2222.</span></span>
-   <span data-ttu-id="f36da-139">**Workflow pour ligne 3** – Ce workflow permet de traiter les lignes dont l'ID projet est 3333.</span><span class="sxs-lookup"><span data-stu-id="f36da-139">**Line-item workflow 3** – This workflow is used to process line items where the project ID is 3333.</span></span>

## <a name="flow-control-elements"></a><span data-ttu-id="f36da-140">Éléments de contrôle des flux</span><span class="sxs-lookup"><span data-stu-id="f36da-140">Flow-control elements</span></span>
<span data-ttu-id="f36da-141">Les éléments suivants permettent de concevoir des workflows avec des branches secondaires ou avec des branches qui s'exécutent simultanément.</span><span class="sxs-lookup"><span data-stu-id="f36da-141">The following elements let you design workflows that have alternate branches or branches that run at the same time.</span></span>

### <a name="manual-decision"></a><span data-ttu-id="f36da-142">Décision manuelle</span><span class="sxs-lookup"><span data-stu-id="f36da-142">Manual decision</span></span>

<span data-ttu-id="f36da-143">Une *décision manuelle* est un point où un workflow se divise en deux branches.</span><span class="sxs-lookup"><span data-stu-id="f36da-143">A *manual decision* is a point where a workflow divides into two branches.</span></span> <span data-ttu-id="f36da-144">Un utilisateur doit prendre une décision qui détermine la branche utilisée pour traiter le document soumis.</span><span class="sxs-lookup"><span data-stu-id="f36da-144">A user must make a decision, and this decision determines which branch is used to process the document that was submitted.</span></span>

### <a name="conditional-decision"></a><span data-ttu-id="f36da-145">Décision conditionnelle</span><span class="sxs-lookup"><span data-stu-id="f36da-145">Conditional decision</span></span>

<span data-ttu-id="f36da-146">Une *décision conditionnelle* est également un point où un workflow se divise en deux branches.</span><span class="sxs-lookup"><span data-stu-id="f36da-146">A *conditional decision* is also a point where a workflow divides into two branches.</span></span> <span data-ttu-id="f36da-147">Toutefois, le système détermine la branche utilisée pour traiter le document soumis.</span><span class="sxs-lookup"><span data-stu-id="f36da-147">However, the system decides which branch is used to process the document that was submitted.</span></span> <span data-ttu-id="f36da-148">Pour prendre cette décision, le système évalue le document pour déterminer s'il répond aux conditions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="f36da-148">To make this decision, the system evaluates the document to determine whether it meets specified conditions.</span></span>

### <a name="parallel-activity"></a><span data-ttu-id="f36da-149">Activité parallèle</span><span class="sxs-lookup"><span data-stu-id="f36da-149">Parallel activity</span></span>

<span data-ttu-id="f36da-150">Une *activité parallèle* est un élément de workflow qui inclut deux branches de workflow ou plus s'exécutant simultanément.</span><span class="sxs-lookup"><span data-stu-id="f36da-150">A *parallel activity* is a workflow element that includes two or more workflow branches that run at the same time.</span></span>

### <a name="subworkflow"></a><span data-ttu-id="f36da-151">Sous-workflow</span><span class="sxs-lookup"><span data-stu-id="f36da-151">Subworkflow</span></span>

<span data-ttu-id="f36da-152">Un *sous-workflow* est un workflow qui s'exécute dans le contexte d'un autre workflow.</span><span class="sxs-lookup"><span data-stu-id="f36da-152">A *subworkflow* is a workflow that runs in the context of another workflow.</span></span>




