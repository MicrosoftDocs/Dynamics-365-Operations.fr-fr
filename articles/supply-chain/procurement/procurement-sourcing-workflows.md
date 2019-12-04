---
title: Workflows d'approvisionnement
description: Certaines organisations demandent que les demandes d'achat et les commandes fournisseur soient approuvées par un utilisateur autre que celui qui a saisi la transaction. Pour paramétrer un processus d'approbation, vous pouvez créer un workflow.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93ceab555bf278ced13d8360956f6db65ba275f8
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813452"
---
# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="fe378-104">Workflows d'approvisionnements</span><span class="sxs-lookup"><span data-stu-id="fe378-104">Procurement and sourcing workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fe378-105">Certaines organisations demandent que les demandes d'achat et les commandes fournisseur soient approuvées par un utilisateur autre que celui qui a saisi la transaction.</span><span class="sxs-lookup"><span data-stu-id="fe378-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="fe378-106">Pour paramétrer un processus d'approbation, vous pouvez créer un workflow.</span><span class="sxs-lookup"><span data-stu-id="fe378-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="fe378-107">Un workflow représente un processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="fe378-107">A workflow represents a business process.</span></span> <span data-ttu-id="fe378-108">Il définit le transfert d'un document dans le système et indique qui doit traiter une tâche ou approuver un document.</span><span class="sxs-lookup"><span data-stu-id="fe378-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="fe378-109">L'utilisation du système de workflow dans votre organisation présente plusieurs avantages :</span><span class="sxs-lookup"><span data-stu-id="fe378-109">There are several benefits of using the workflow system in your organization:</span></span>
-   <span data-ttu-id="fe378-110">**Processus cohérents** — Vous pouvez définir le processus d'approbation pour des documents spécifiques, tels que des demandes d'achat ou des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="fe378-110">**Consistent processes**— You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="fe378-111">Le système de workflow permet de s'assurer que les documents sont traités et approuvés de manière cohérente et efficace.</span><span class="sxs-lookup"><span data-stu-id="fe378-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
-   <span data-ttu-id="fe378-112">**Visibilité de processus** — Vous pouvez suivre le statut, l'historique et les mesures de performance d'une instance de workflow spécifique.</span><span class="sxs-lookup"><span data-stu-id="fe378-112">**Process visibility** — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="fe378-113">Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d'en optimiser l'efficacité.</span><span class="sxs-lookup"><span data-stu-id="fe378-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
-   <span data-ttu-id="fe378-114">**Liste de travail centralisée** — Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées dans l'ensemble des workflows auxquels ils participent.</span><span class="sxs-lookup"><span data-stu-id="fe378-114">**Centralized work list** — Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="fe378-115">Cette option est disponible dans la page Éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="fe378-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="fe378-116"> Types de workflows qu'il est possible de créer</span><span class="sxs-lookup"><span data-stu-id="fe378-116">The types of workflows that you can create</span></span>
<span data-ttu-id="fe378-117">Les types de workflows suivants sont disponibles pour le module Approvisionnements.</span><span class="sxs-lookup"><span data-stu-id="fe378-117">The following workflow types are available for Procurement and sourcing.</span></span>

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| <span data-ttu-id="fe378-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="fe378-118">**Type**</span></span>                         | <span data-ttu-id="fe378-119">**Utilisation**</span><span class="sxs-lookup"><span data-stu-id="fe378-119">**Use this type to**</span></span>                                          |
| <span data-ttu-id="fe378-120">Révision de la demande d'achat</span><span class="sxs-lookup"><span data-stu-id="fe378-120">Purchase requisition review</span></span>      | <span data-ttu-id="fe378-121">Permet de créer des workflows de révision et d'approbation pour les demandes d'achat.</span><span class="sxs-lookup"><span data-stu-id="fe378-121">Create review and approval workflows for purchase requisitions.</span></span>            |
| <span data-ttu-id="fe378-122">Analyse de la ligne de demande d'achat</span><span class="sxs-lookup"><span data-stu-id="fe378-122">Purchase requisition line review</span></span> | <span data-ttu-id="fe378-123">Permet de créer des workflows de révision et d'approbation pour les lignes de demande d'achat.</span><span class="sxs-lookup"><span data-stu-id="fe378-123">Create review and approval workflows for purchase requisition lines.</span></span>       |
| <span data-ttu-id="fe378-124">Workflow de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="fe378-124">Purchase order workflow</span></span>          | <span data-ttu-id="fe378-125">Permet de créer des workflows de révision et d'approbation pour les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="fe378-125">Create review and approval workflows for purchase orders.</span></span>     |
| <span data-ttu-id="fe378-126">Workflow de ligne de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="fe378-126">Purchase order line workflow</span></span>     | <span data-ttu-id="fe378-127">Permet de créer des workflows de révision et d'approbation pour les lignes de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="fe378-127">Create review and approve workflows for purchase order lines.</span></span> |
| <span data-ttu-id="fe378-128">Workflow d'application d'ajout de fournisseur</span><span class="sxs-lookup"><span data-stu-id="fe378-128">Vendor add application workflow</span></span>  | <span data-ttu-id="fe378-129">Permet de créer des workflows de révision et d'approbation pour ajouter de nouveaux fournisseurs via les demandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="fe378-129">Create review and approval workflows for adding new vendors via vendor requests.</span></span> |

## <a name="creating-a-workflow"></a><span data-ttu-id="fe378-130">Création d'un workflow</span><span class="sxs-lookup"><span data-stu-id="fe378-130">Creating a workflow</span></span>

<span data-ttu-id="fe378-131">Pour créer un workflow, accédez à Approvisionnements &gt; Paramétrage &gt; Workflows d'approvisionnement, puis créez un workflow en sélectionnant le type de workflow à créer.</span><span class="sxs-lookup"><span data-stu-id="fe378-131">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span>  

<span data-ttu-id="fe378-132">Dans le canevas de workflow, vous pouvez faire glisser des éléments de workflow dans le concepteur et lier les éléments dans un flux.</span><span class="sxs-lookup"><span data-stu-id="fe378-132">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="fe378-133">Les éléments de workflow doivent être configurés.</span><span class="sxs-lookup"><span data-stu-id="fe378-133">The workflow elements should be configured.</span></span> <span data-ttu-id="fe378-134">Pour les éléments de workflow d'approbation et de tâche, vous pouvez configurer le participant qui doit effectuer l'action.</span><span class="sxs-lookup"><span data-stu-id="fe378-134">For approval and task workflow elements you can configure which participant should take action.</span></span>

## <a name="types-of-participants"></a><span data-ttu-id="fe378-135">Types de participants</span><span class="sxs-lookup"><span data-stu-id="fe378-135">Types of participants</span></span>

<span data-ttu-id="fe378-136">Vous pouvez affecter une étape d'approbation aux groupes suivants de participants.</span><span class="sxs-lookup"><span data-stu-id="fe378-136">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="fe378-137">Groupe d'utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fe378-137">User group</span></span>    | <span data-ttu-id="fe378-138">Description</span><span class="sxs-lookup"><span data-stu-id="fe378-138">Description</span></span>                                                               |
|---------------|---------------------------------------------------------------------------|
| <span data-ttu-id="fe378-139">Participant</span><span class="sxs-lookup"><span data-stu-id="fe378-139">Participant</span></span>   | <span data-ttu-id="fe378-140">Permet d'affecter l'étape d'approbation aux membres d'un groupe ou rôle.</span><span class="sxs-lookup"><span data-stu-id="fe378-140">Assign the approval step to members of a group or role.</span></span>                   |
| <span data-ttu-id="fe378-141">Hiérarchie</span><span class="sxs-lookup"><span data-stu-id="fe378-141">Hierarchy</span></span>     | <span data-ttu-id="fe378-142">Permet d'affecter l'étape d'approbation aux utilisateurs d'une hiérarchie d'organisation spécifique.</span><span class="sxs-lookup"><span data-stu-id="fe378-142">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="fe378-143">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="fe378-143">Workflow user</span></span> | <span data-ttu-id="fe378-144">Permet d'affecter l'étape d'approbation aux utilisateurs de ce workflow.</span><span class="sxs-lookup"><span data-stu-id="fe378-144">Assign the approval step to users of this workflow.</span></span>                       |
| <span data-ttu-id="fe378-145">File d'attente</span><span class="sxs-lookup"><span data-stu-id="fe378-145">Queue</span></span>         | <span data-ttu-id="fe378-146">Permet d'affecter l'étape d'approbation à une file d'attente des éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="fe378-146">Assign the approval step to a work item queue.</span></span>                            |
| <span data-ttu-id="fe378-147">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="fe378-147">User</span></span>          | <span data-ttu-id="fe378-148">Permet d'affecter l'étape d'approbation à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="fe378-148">Assign the approval step to specific users.</span></span>                               |



## <a name="additional-resources"></a><span data-ttu-id="fe378-149">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fe378-149">Additional resources</span></span>

- <span data-ttu-id="fe378-150">[Définition des flux de travail de processus entreprise pour les demandes d'achat](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions) (livre blanc)</span><span class="sxs-lookup"><span data-stu-id="fe378-150">[Defining business process workflows for purchase requisitions](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)</span></span>

- [<span data-ttu-id="fe378-151">Workflow de demande d'achat</span><span class="sxs-lookup"><span data-stu-id="fe378-151">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)

- [<span data-ttu-id="fe378-152">Intégrer des fournisseurs</span><span class="sxs-lookup"><span data-stu-id="fe378-152">Onboard vendors</span></span>](vendor-onboarding.md)

