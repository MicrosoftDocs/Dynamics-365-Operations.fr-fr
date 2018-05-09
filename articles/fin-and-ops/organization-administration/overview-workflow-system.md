---
title: Vue d'ensemble du workflow
description: "Cette rubrique décrit le système de workflow dans Microsoft Dynamics 365 for Finance and Operations."
author: sericks007
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0febf2eaee91d0648ba6b5586abcf3be0f04dfa9
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="workflow-overview"></a><span data-ttu-id="71d8f-103">Vue d'ensemble du workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-103">Workflow overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71d8f-104">Cette rubrique décrit le système de workflow dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="71d8f-104">This topic describes the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<a name="what-is-workflow"></a><span data-ttu-id="71d8f-105">Qu'est-ce qu'un workflow ?</span><span class="sxs-lookup"><span data-stu-id="71d8f-105">What is workflow?</span></span>
-----------------

<span data-ttu-id="71d8f-106">Le terme *workflow* revêt deux concepts : workflow en tant que système et workflow en tant que processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="71d8f-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>
### <a name="workflow-is-a-system"></a><span data-ttu-id="71d8f-107">Un workflow est un système</span><span class="sxs-lookup"><span data-stu-id="71d8f-107">Workflow is a system</span></span>

<span data-ttu-id="71d8f-108">Un workflow est un système installé avec Finance and Operations, qui s'exécute sur le Serveur d'objets d'application (AOS).</span><span class="sxs-lookup"><span data-stu-id="71d8f-108">Workflow is a system that is installed with Finance and Operations and runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="71d8f-109">Les fonctionnalités du système de workflow permettent de créer des workflows ou des processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="71d8f-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="71d8f-110">Un workflow est un processus entreprise</span><span class="sxs-lookup"><span data-stu-id="71d8f-110">Workflow is a business process</span></span>

<span data-ttu-id="71d8f-111">Un workflow représente un processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="71d8f-111">A workflow represents a business process.</span></span> <span data-ttu-id="71d8f-112">Il définit la circulation, la progression, d'un document dans le système en indiquant qui doit traiter une tâche, prendre une décision ou approuver un document.</span><span class="sxs-lookup"><span data-stu-id="71d8f-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="71d8f-113">Par exemple, l'illustration suivante représente un workflow d'état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="71d8f-113">For example, the following illustration shows a workflow for expense reports.</span></span> 

![Workflow avec des éléments affectés à des utilisateurs](./media/workflow_user.gif) 

<span data-ttu-id="71d8f-115">Pour mieux comprendre ce workflow, supposons que Sam soumette un état de dépenses de USD 7 000.</span><span class="sxs-lookup"><span data-stu-id="71d8f-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="71d8f-116">Dans ce scénario, Ivan doit passer en revue les reçus envoyés par Sam.</span><span class="sxs-lookup"><span data-stu-id="71d8f-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="71d8f-117">Frank et Sue doivent ensuite approuver l'état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="71d8f-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="71d8f-118">Supposons maintenant que Sam soumette un état de dépenses de USD 11 000.</span><span class="sxs-lookup"><span data-stu-id="71d8f-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="71d8f-119">Dans ce scénario, Ivan doit passer en revue les reçus, et Frank, Sue et Ann doivent approuver l'état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="71d8f-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="71d8f-120">Avantages de l'utilisation du système de workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="71d8f-121">L'utilisation du système de workflow dans votre organisation présente plusieurs avantages :</span><span class="sxs-lookup"><span data-stu-id="71d8f-121">There are several benefits of using the workflow system in your organization:</span></span>
-   <span data-ttu-id="71d8f-122">**Processus cohérents** – Vous pouvez définir le traitement de documents spécifiques, tels que des demandes d'achat ou des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="71d8f-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="71d8f-123">Lorsque vous utilisez le système de workflow, vous pouvez vérifier que les documents sont traités et approuvés de manière cohérente et efficace.</span><span class="sxs-lookup"><span data-stu-id="71d8f-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
-   <span data-ttu-id="71d8f-124">**Visibilité du processus** – Vous pouvez suivre le statut, l'historique et les mesures de performance des instances de workflow.</span><span class="sxs-lookup"><span data-stu-id="71d8f-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="71d8f-125">Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d'en optimiser l'efficacité.</span><span class="sxs-lookup"><span data-stu-id="71d8f-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
-   <span data-ttu-id="71d8f-126">**Liste de travail centralisée** – Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées.</span><span class="sxs-lookup"><span data-stu-id="71d8f-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="71d8f-127">Contenu de workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-127">Workflow content</span></span>

+ [<span data-ttu-id="71d8f-128">Architecture de workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-128">Workflow architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="71d8f-129">Éléments du workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="71d8f-130">Actions de workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-130">Workflow actions</span></span>](workflow-actions.md)
+ [<span data-ttu-id="71d8f-131">Création d'un workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-131">Create a workflow</span></span>](create-workflow.md)
+ [<span data-ttu-id="71d8f-132">Configuration des propriétés de workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="71d8f-133">Configurer une tâche manuelle dans un workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-133">Configure a manual task in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="71d8f-134">Configurer une tâche automatique dans un workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-134">Configure an automated task in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="71d8f-135">Configurer un processus d'approbation dans un workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-135">Configure an approval process in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="71d8f-136">Configurer une étape d'approbation dans un workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-136">Configure an approval step in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="71d8f-137">Configurer une décision manuelle dans un workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-137">Configure a manual decision in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="71d8f-138">Configurer une décision conditionnelle dans un workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-138">Configure a conditional decision in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="71d8f-139">Configurer une activité parallèle dans un workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-139">Configure a parallel activity in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="71d8f-140">Configurer une branche parallèle dans un workflow</span><span class="sxs-lookup"><span data-stu-id="71d8f-140">Configure a parallel branch in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="71d8f-141">Configuration d'un workflow pour ligne</span><span class="sxs-lookup"><span data-stu-id="71d8f-141">Configure a line-item workflow</span></span>](configure-line-item-workflow.md)

