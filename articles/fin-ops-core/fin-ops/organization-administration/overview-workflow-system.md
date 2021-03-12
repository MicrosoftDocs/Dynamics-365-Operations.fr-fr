---
title: Vue d’ensemble du système de workflow
description: Cette rubrique décrit le système de workflow.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 660e01618eea66bc611dd51818694d36993ba9ea
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796994"
---
# <a name="workflow-system-overview"></a><span data-ttu-id="0ad18-103">Vue d’ensemble du système de workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-103">Workflow system overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ad18-104">Cette rubrique décrit le système de workflow.</span><span class="sxs-lookup"><span data-stu-id="0ad18-104">This topic describes the workflow system.</span></span>

## <a name="what-is-workflow"></a><span data-ttu-id="0ad18-105">Qu’est-ce qu’un workflow ?</span><span class="sxs-lookup"><span data-stu-id="0ad18-105">What is workflow?</span></span>

<span data-ttu-id="0ad18-106">Le terme *workflow* revêt deux concepts : workflow en tant que système et workflow en tant que processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ad18-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>

### <a name="workflow-is-a-system"></a><span data-ttu-id="0ad18-107">Un workflow est un système</span><span class="sxs-lookup"><span data-stu-id="0ad18-107">Workflow is a system</span></span>

<span data-ttu-id="0ad18-108">Un workflow est un système qui s’exécute sur le serveur d’objets d’application (AOS).</span><span class="sxs-lookup"><span data-stu-id="0ad18-108">Workflow is a system that runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="0ad18-109">Les fonctionnalités du système de workflow permettent de créer des workflows ou des processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ad18-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="0ad18-110">Un workflow est un processus entreprise</span><span class="sxs-lookup"><span data-stu-id="0ad18-110">Workflow is a business process</span></span>

<span data-ttu-id="0ad18-111">Un workflow représente un processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ad18-111">A workflow represents a business process.</span></span> <span data-ttu-id="0ad18-112">Il définit la circulation, la progression, d’un document dans le système en indiquant qui doit traiter une tâche, prendre une décision ou approuver un document.</span><span class="sxs-lookup"><span data-stu-id="0ad18-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="0ad18-113">Par exemple, l’illustration suivante représente un workflow d’état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="0ad18-113">For example, the following illustration shows a workflow for expense reports.</span></span>

![Workflow avec des éléments affectés à des utilisateurs](./media/workflow_user.gif)

<span data-ttu-id="0ad18-115">Pour mieux comprendre ce workflow, supposons que Sam soumette un état de dépenses de USD 7 000.</span><span class="sxs-lookup"><span data-stu-id="0ad18-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="0ad18-116">Dans ce scénario, Ivan doit passer en revue les reçus envoyés par Sam.</span><span class="sxs-lookup"><span data-stu-id="0ad18-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="0ad18-117">Frank et Sue doivent ensuite approuver l’état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="0ad18-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="0ad18-118">Supposons maintenant que Sam soumette un état de dépenses de USD 11 000.</span><span class="sxs-lookup"><span data-stu-id="0ad18-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="0ad18-119">Dans ce scénario, Ivan doit passer en revue les reçus, et Frank, Sue et Ann doivent approuver l’état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="0ad18-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="0ad18-120">Avantages de l’utilisation du système de workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="0ad18-121">L’utilisation du système de workflow dans votre organisation présente plusieurs avantages :</span><span class="sxs-lookup"><span data-stu-id="0ad18-121">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="0ad18-122">**Processus cohérents** – Vous pouvez définir le traitement de documents spécifiques, tels que des demandes d’achat ou des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="0ad18-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="0ad18-123">Lorsque vous utilisez le système de workflow, vous pouvez vérifier que les documents sont traités et approuvés de manière cohérente et efficace.</span><span class="sxs-lookup"><span data-stu-id="0ad18-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="0ad18-124">**Visibilité du processus** – Vous pouvez suivre le statut, l’historique et les mesures de performance des instances de workflow.</span><span class="sxs-lookup"><span data-stu-id="0ad18-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="0ad18-125">Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d’en optimiser l’efficacité.</span><span class="sxs-lookup"><span data-stu-id="0ad18-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="0ad18-126">**Liste de travail centralisée** – Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées.</span><span class="sxs-lookup"><span data-stu-id="0ad18-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="0ad18-127">Contenu de workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-127">Workflow content</span></span>

+ [<span data-ttu-id="0ad18-128">Architecture de système de workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-128">Workflow system architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="0ad18-129">Éléments du flux de travail</span><span class="sxs-lookup"><span data-stu-id="0ad18-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="0ad18-130">Actions dans les processus d’approbation d’un workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-130">Actions in workflow approval processes</span></span>](workflow-actions.md)
+ [<span data-ttu-id="0ad18-131">Vue d’ensemble de création des workflows</span><span class="sxs-lookup"><span data-stu-id="0ad18-131">Create workflows overview</span></span>](create-workflow.md)
+ [<span data-ttu-id="0ad18-132">Configuration des propriétés de workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="0ad18-133">Configurer des tâches manuelles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-133">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="0ad18-134">Configurer des tâches automatiques dans un workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-134">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="0ad18-135">Configurer des processus d’approbation dans un workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-135">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="0ad18-136">Configurer des étapes d’approbation dans un workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-136">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="0ad18-137">Configurer des décisions manuelles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-137">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="0ad18-138">Configurer des décisions conditionnelles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-138">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="0ad18-139">Configurer des activités parallèles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-139">Configure parallel activities in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="0ad18-140">Configurer des branches parallèles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="0ad18-140">Configure parallel branches in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="0ad18-141">Configuration de workflows pour ligne</span><span class="sxs-lookup"><span data-stu-id="0ad18-141">Configure line-item workflows</span></span>](configure-line-item-workflow.md)
+ [<span data-ttu-id="0ad18-142">FAQ sur les workflows</span><span class="sxs-lookup"><span data-stu-id="0ad18-142">Workflow FAQ</span></span>](workflow-FAQ.md)
