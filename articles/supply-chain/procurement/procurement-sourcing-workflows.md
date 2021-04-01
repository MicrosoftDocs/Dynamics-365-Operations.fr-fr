---
title: Workflows d’approvisionnement
description: Certaines organisations demandent que les demandes d’achat et les commandes fournisseur soient approuvées par un utilisateur autre que celui qui a saisi la transaction. Pour paramétrer un processus d’approbation, vous pouvez créer un workflow.
author: RichardLuan
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e591007a1330fe11b3f586185f9daca845798908
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218463"
---
# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="6afb7-104">Workflows d’approvisionnements</span><span class="sxs-lookup"><span data-stu-id="6afb7-104">Procurement and sourcing workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6afb7-105">Certaines organisations demandent que les demandes d’achat et les commandes fournisseur soient approuvées par un utilisateur autre que celui qui a saisi la transaction.</span><span class="sxs-lookup"><span data-stu-id="6afb7-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="6afb7-106">Pour paramétrer un processus d’approbation, vous pouvez créer un workflow.</span><span class="sxs-lookup"><span data-stu-id="6afb7-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="6afb7-107">Un workflow représente un processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="6afb7-107">A workflow represents a business process.</span></span> <span data-ttu-id="6afb7-108">Il définit le transfert d’un document dans le système et indique qui doit traiter une tâche ou approuver un document.</span><span class="sxs-lookup"><span data-stu-id="6afb7-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="6afb7-109">L’utilisation du système de workflow dans votre organisation présente plusieurs avantages :</span><span class="sxs-lookup"><span data-stu-id="6afb7-109">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="6afb7-110">**Processus cohérents** — Vous pouvez définir le processus d’approbation pour des documents spécifiques, tels que des demandes d’achat ou des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="6afb7-110">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="6afb7-111">Le système de workflow permet de s’assurer que les documents sont traités et approuvés de manière cohérente et efficace.</span><span class="sxs-lookup"><span data-stu-id="6afb7-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="6afb7-112">**Visibilité de processus** — Vous pouvez suivre le statut, l’historique et les mesures de performance d’une instance de workflow spécifique.</span><span class="sxs-lookup"><span data-stu-id="6afb7-112">**Process visibility** — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="6afb7-113">Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d’en optimiser l’efficacité.</span><span class="sxs-lookup"><span data-stu-id="6afb7-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="6afb7-114">**Liste de travail centralisée** — Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées dans l’ensemble des workflows auxquels ils participent.</span><span class="sxs-lookup"><span data-stu-id="6afb7-114">**Centralized work list** — Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="6afb7-115">Cette option est disponible dans la page Éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="6afb7-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="6afb7-116">Types de workflows qu’il est possible de créer</span><span class="sxs-lookup"><span data-stu-id="6afb7-116">The types of workflows that you can create</span></span>

<span data-ttu-id="6afb7-117">Les types de workflows suivants sont disponibles pour le module Approvisionnements.</span><span class="sxs-lookup"><span data-stu-id="6afb7-117">The following workflow types are available for Procurement and sourcing.</span></span>

| <span data-ttu-id="6afb7-118">Type</span><span class="sxs-lookup"><span data-stu-id="6afb7-118">Type</span></span> | <span data-ttu-id="6afb7-119">Utilisation</span><span class="sxs-lookup"><span data-stu-id="6afb7-119">Use this type to</span></span> |
|---|---|
| <span data-ttu-id="6afb7-120">Révision de la demande d’achat</span><span class="sxs-lookup"><span data-stu-id="6afb7-120">Purchase requisition review</span></span> | <span data-ttu-id="6afb7-121">Permet de créer des workflows de révision et d’approbation pour les demandes d’achat.</span><span class="sxs-lookup"><span data-stu-id="6afb7-121">Create review and approval workflows for purchase requisitions.</span></span> |
| <span data-ttu-id="6afb7-122">Analyse de la ligne de demande d’achat</span><span class="sxs-lookup"><span data-stu-id="6afb7-122">Purchase requisition line review</span></span> | <span data-ttu-id="6afb7-123">Permet de créer des workflows de révision et d’approbation pour les lignes de demande d’achat.</span><span class="sxs-lookup"><span data-stu-id="6afb7-123">Create review and approval workflows for purchase requisition lines.</span></span> |
| <span data-ttu-id="6afb7-124">Workflow de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="6afb7-124">Purchase order workflow</span></span> | <span data-ttu-id="6afb7-125">Permet de créer des workflows de révision et d’approbation pour les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6afb7-125">Create review and approval workflows for purchase orders.</span></span> |
| <span data-ttu-id="6afb7-126">Workflow de ligne de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="6afb7-126">Purchase order line workflow</span></span> | <span data-ttu-id="6afb7-127">Permet de créer des workflows de révision et d’approbation pour les lignes de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6afb7-127">Create review and approve workflows for purchase order lines.</span></span> |
| <span data-ttu-id="6afb7-128">Workflow d’application d’ajout de fournisseur</span><span class="sxs-lookup"><span data-stu-id="6afb7-128">Vendor add application workflow</span></span> | <span data-ttu-id="6afb7-129">Permet de créer des workflows de révision et d’approbation pour ajouter de nouveaux fournisseurs via les demandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6afb7-129">Create review and approval workflows for adding new vendors via vendor requests.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="6afb7-130">Lorsque vous ajoutez un nouveau workflow, vous pouvez également voir les workflows obsolètes suivants répertoriés dans la boite de dialogue **Créer un workflow**.</span><span class="sxs-lookup"><span data-stu-id="6afb7-130">When you are adding a new workflow, you might also see the following obsolete workflows listed in the **Create workflow** dialog box.</span></span> <span data-ttu-id="6afb7-131">Ceux-ci sont liés à la fonctionnalité *confirmation de réception* disponible dans [Dynamique AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), mais qui est désormais obsolète.</span><span class="sxs-lookup"><span data-stu-id="6afb7-131">These are related to the *confirmation of receipt* functionality that was available in [Dynamics AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), but which has now been deprecated.</span></span> <span data-ttu-id="6afb7-132">Ces workflows ne sont actuellement pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6afb7-132">These workflows are currently unsupported.</span></span>
> 
> - <span data-ttu-id="6afb7-133">Flux de travail de notification de date d’échéance de livraison</span><span class="sxs-lookup"><span data-stu-id="6afb7-133">Delivery due date notification workflow</span></span>
> - <span data-ttu-id="6afb7-134">Flux de travail de notification de réception de facture</span><span class="sxs-lookup"><span data-stu-id="6afb7-134">Invoice received notification workflow</span></span>
> - <span data-ttu-id="6afb7-135">Accusé de réception de marchandises - Flux de travail de notification d’échec</span><span class="sxs-lookup"><span data-stu-id="6afb7-135">Product receipt failed notification workflow</span></span>
> - <span data-ttu-id="6afb7-136">Flux de travail de notification de rejet de l’accusé de réception de marchandises non confirmé</span><span class="sxs-lookup"><span data-stu-id="6afb7-136">Unconfirmed product receipt rejection notification workflow</span></span>

## <a name="creating-a-workflow"></a><span data-ttu-id="6afb7-137">Création d’un workflow</span><span class="sxs-lookup"><span data-stu-id="6afb7-137">Creating a workflow</span></span>

<span data-ttu-id="6afb7-138">Pour créer un workflow, accédez à Approvisionnements &gt; Paramétrage &gt; Workflows d’approvisionnement, puis créez un workflow en sélectionnant le type de workflow à créer.</span><span class="sxs-lookup"><span data-stu-id="6afb7-138">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span> 

<span data-ttu-id="6afb7-139">Dans le canevas de workflow, vous pouvez faire glisser des éléments de workflow dans le concepteur et lier les éléments dans un flux.</span><span class="sxs-lookup"><span data-stu-id="6afb7-139">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="6afb7-140">Les éléments de workflow doivent être configurés.</span><span class="sxs-lookup"><span data-stu-id="6afb7-140">The workflow elements should be configured.</span></span> <span data-ttu-id="6afb7-141">Pour les éléments de workflow d’approbation et de tâche, vous pouvez configurer le participant qui doit effectuer l’action.</span><span class="sxs-lookup"><span data-stu-id="6afb7-141">For approval and task workflow elements you can configure which participant should take action.</span></span>

## <a name="types-of-participants"></a><span data-ttu-id="6afb7-142">Types de participants</span><span class="sxs-lookup"><span data-stu-id="6afb7-142">Types of participants</span></span>

<span data-ttu-id="6afb7-143">Vous pouvez affecter une étape d’approbation aux groupes suivants de participants.</span><span class="sxs-lookup"><span data-stu-id="6afb7-143">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="6afb7-144">Groupe d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6afb7-144">User group</span></span> | <span data-ttu-id="6afb7-145">Description</span><span class="sxs-lookup"><span data-stu-id="6afb7-145">Description</span></span> |
|---|---|
| <span data-ttu-id="6afb7-146">Participant</span><span class="sxs-lookup"><span data-stu-id="6afb7-146">Participant</span></span> | <span data-ttu-id="6afb7-147">Permet d’affecter l’étape d’approbation aux membres d’un groupe ou rôle.</span><span class="sxs-lookup"><span data-stu-id="6afb7-147">Assign the approval step to members of a group or role.</span></span> |
| <span data-ttu-id="6afb7-148">Hiérarchie</span><span class="sxs-lookup"><span data-stu-id="6afb7-148">Hierarchy</span></span> | <span data-ttu-id="6afb7-149">Permet d’affecter l’étape d’approbation aux utilisateurs d’une hiérarchie d’organisation spécifique.</span><span class="sxs-lookup"><span data-stu-id="6afb7-149">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="6afb7-150">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="6afb7-150">Workflow user</span></span> | <span data-ttu-id="6afb7-151">Permet d’affecter l’étape d’approbation aux utilisateurs de ce workflow.</span><span class="sxs-lookup"><span data-stu-id="6afb7-151">Assign the approval step to users of this workflow.</span></span> |
| <span data-ttu-id="6afb7-152">File d’attente</span><span class="sxs-lookup"><span data-stu-id="6afb7-152">Queue</span></span> | <span data-ttu-id="6afb7-153">Permet d’affecter l’étape d’approbation à une file d’attente des éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="6afb7-153">Assign the approval step to a work item queue.</span></span> |
| <span data-ttu-id="6afb7-154">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="6afb7-154">User</span></span> | <span data-ttu-id="6afb7-155">Permet d’affecter l’étape d’approbation à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6afb7-155">Assign the approval step to specific users.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="6afb7-156">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6afb7-156">Additional resources</span></span>

- [<span data-ttu-id="6afb7-157">Définition des flux de travail de processus entreprise pour les demandes d’achat (livre blanc)</span><span class="sxs-lookup"><span data-stu-id="6afb7-157">Defining business process workflows for purchase requisitions</span></span>](https://www.microsoft.com/download/details.aspx?id=101821)
- [<span data-ttu-id="6afb7-158">Workflow de demande d’achat</span><span class="sxs-lookup"><span data-stu-id="6afb7-158">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)
- [<span data-ttu-id="6afb7-159">Intégrer des fournisseurs</span><span class="sxs-lookup"><span data-stu-id="6afb7-159">Onboard vendors</span></span>](vendor-onboarding.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]