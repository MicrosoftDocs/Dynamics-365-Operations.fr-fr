---
title: Workflows d'approvisionnement
description: "Certaines organisations demandent que les demandes d'achat et les commandes fournisseur soient approuvées par un utilisateur autre que celui qui a saisi la transaction. Pour paramétrer un processus d'approbation, vous pouvez créer un workflow."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3bf244786e308ebcaee27a16fae378f41086f963
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="3c6a3-104">Workflows d'approvisionnements</span><span class="sxs-lookup"><span data-stu-id="3c6a3-104">Procurement and sourcing workflows</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3c6a3-105">Certaines organisations demandent que les demandes d'achat et les commandes fournisseur soient approuvées par un utilisateur autre que celui qui a saisi la transaction.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="3c6a3-106">Pour paramétrer un processus d'approbation, vous pouvez créer un workflow.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="3c6a3-107">Un workflow représente un processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-107">A workflow represents a business process.</span></span> <span data-ttu-id="3c6a3-108">Il définit le transfert d'un document dans le système et indique qui doit traiter une tâche ou approuver un document.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="3c6a3-109">L'utilisation du système de workflow dans votre organisation présente plusieurs avantages :</span><span class="sxs-lookup"><span data-stu-id="3c6a3-109">There are several benefits of using the workflow system in your organization:</span></span>
-   <span data-ttu-id="3c6a3-110">**Processus cohérents** — Vous pouvez définir le processus d'approbation pour des documents spécifiques, tels que des demandes d'achat ou des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-110">**Consistent processes**— You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="3c6a3-111">Le système de workflow permet de s'assurer que les documents sont traités et approuvés de manière cohérente et efficace.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
-   <span data-ttu-id="3c6a3-112">**Visibilité de processus** — Vous pouvez suivre le statut, l'historique et les mesures de performance d'une instance de workflow spécifique.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-112">**Process visibility**— You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="3c6a3-113">Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d'en optimiser l'efficacité.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
-   <span data-ttu-id="3c6a3-114">**Liste de travail centralisée** — Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées dans l'ensemble des workflows auxquels ils participent.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-114">**Centralized work list**— Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="3c6a3-115">Cette option est disponible dans la page Éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="3c6a3-116"> Types de workflows qu'il est possible de créer</span><span class="sxs-lookup"><span data-stu-id="3c6a3-116">The types of workflows that you can create</span></span>
<span data-ttu-id="3c6a3-117">Les types de workflows suivants sont disponibles pour le module Approvisionnements.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-117">The following workflow types are available for Procurement and sourcing.</span></span>

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| <span data-ttu-id="3c6a3-118">**Tapez**</span><span class="sxs-lookup"><span data-stu-id="3c6a3-118">**Type**</span></span>                         | <span data-ttu-id="3c6a3-119">**Utilisation**</span><span class="sxs-lookup"><span data-stu-id="3c6a3-119">**Use this type to**</span></span>                                          |
| <span data-ttu-id="3c6a3-120">Révision de la demande d'achat</span><span class="sxs-lookup"><span data-stu-id="3c6a3-120">Purchase requisition review</span></span>      | <span data-ttu-id="3c6a3-121">Permet de créer des workflows de révision pour les demandes d'achat.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-121">Create review workflows for purchase requisitions.</span></span>            |
| <span data-ttu-id="3c6a3-122">Analyse de la ligne de demande d'achat</span><span class="sxs-lookup"><span data-stu-id="3c6a3-122">Purchase requisition line review</span></span> | <span data-ttu-id="3c6a3-123">Permet de créer des workflows de révision pour les lignes de demandes d'achat.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-123">Create review workflows for purchase requisition lines.</span></span>       |
| <span data-ttu-id="3c6a3-124">Workflow de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="3c6a3-124">Purchase order workflow</span></span>          | <span data-ttu-id="3c6a3-125">Permet de créer des workflows de révision et d'approbation pour les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-125">Create review and approval workflows for purchase orders.</span></span>     |
| <span data-ttu-id="3c6a3-126">Workflow de ligne de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="3c6a3-126">Purchase order line workflow</span></span>     | <span data-ttu-id="3c6a3-127">Permet de créer des workflows de révision et d'approbation pour les lignes de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-127">Create review and approve workflows for purchase order lines.</span></span> |

## <a name="creating-a-workflow"></a><span data-ttu-id="3c6a3-128">Création d'un workflow</span><span class="sxs-lookup"><span data-stu-id="3c6a3-128">Creating a workflow</span></span>
<span data-ttu-id="3c6a3-129">Pour créer un workflow, accédez à Approvisionnements &gt; Paramétrage &gt; Workflows d'approvisionnement, puis créez un workflow en sélectionnant le type de workflow à créer.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-129">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span>  

<span data-ttu-id="3c6a3-130">Dans le canevas de workflow, vous pouvez faire glisser des éléments de workflow dans le concepteur et lier les éléments dans un flux.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-130">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="3c6a3-131">Les éléments de workflow doivent être configurés.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-131">The workflow elements should be configured.</span></span> <span data-ttu-id="3c6a3-132">Pour les éléments de workflow d'approbation et de tâche, vous pouvez configurer le participant qui doit effectuer l'action.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-132">For approval and task workflow elements you can configure which participant should take action.</span></span>
<span data-ttu-id="3c6a3-133">Types de participants</span><span class="sxs-lookup"><span data-stu-id="3c6a3-133">Types of participants</span></span>
----------------------

<span data-ttu-id="3c6a3-134">Vous pouvez affecter une étape d'approbation aux groupes suivants de participants.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-134">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="3c6a3-135">Groupe d'utilisateurs</span><span class="sxs-lookup"><span data-stu-id="3c6a3-135">User group</span></span>    | <span data-ttu-id="3c6a3-136">Description</span><span class="sxs-lookup"><span data-stu-id="3c6a3-136">Description</span></span>                                                               |
|---------------|---------------------------------------------------------------------------|
| <span data-ttu-id="3c6a3-137">Participant</span><span class="sxs-lookup"><span data-stu-id="3c6a3-137">Participant</span></span>   | <span data-ttu-id="3c6a3-138">Permet d'affecter l'étape d'approbation aux membres d'un groupe ou rôle.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-138">Assign the approval step to members of a group or role.</span></span>                   |
| <span data-ttu-id="3c6a3-139">Hiérarchie</span><span class="sxs-lookup"><span data-stu-id="3c6a3-139">Hierarchy</span></span>     | <span data-ttu-id="3c6a3-140">Permet d'affecter l'étape d'approbation aux utilisateurs d'une hiérarchie d'organisation spécifique.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-140">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="3c6a3-141">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="3c6a3-141">Workflow user</span></span> | <span data-ttu-id="3c6a3-142">Permet d'affecter l'étape d'approbation aux utilisateurs de ce workflow.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-142">Assign the approval step to users of this workflow.</span></span>                       |
| <span data-ttu-id="3c6a3-143">File d'attente</span><span class="sxs-lookup"><span data-stu-id="3c6a3-143">Queue</span></span>         | <span data-ttu-id="3c6a3-144">Permet d'affecter l'étape d'approbation à une file d'attente des éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-144">Assign the approval step to a work item queue.</span></span>                            |
| <span data-ttu-id="3c6a3-145">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="3c6a3-145">User</span></span>          | <span data-ttu-id="3c6a3-146">Permet d'affecter l'étape d'approbation à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3c6a3-146">Assign the approval step to specific users.</span></span>                               |



<a name="see-also"></a><span data-ttu-id="3c6a3-147">Voir également :</span><span class="sxs-lookup"><span data-stu-id="3c6a3-147">See also</span></span>
--------

<span data-ttu-id="3c6a3-148">[Defining business process workflows for purchase requisitions](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions) (livre blanc)</span><span class="sxs-lookup"><span data-stu-id="3c6a3-148">[Defining business process workflows for purchase requisitions](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)</span></span>

[<span data-ttu-id="3c6a3-149">workflow de demande d'achat</span><span class="sxs-lookup"><span data-stu-id="3c6a3-149">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)




