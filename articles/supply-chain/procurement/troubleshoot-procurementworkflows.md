---
title: Résoudre les problèmes liés aux workflows d’approvisionnements
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lorsque vous utilisez des workflows d’approvisionnements.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 940a6c39ac83e7388d4e1a08b656b75df81ed801
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834354"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a><span data-ttu-id="3d37b-103">Résoudre les problèmes liés aux workflows d’approvisionnements</span><span class="sxs-lookup"><span data-stu-id="3d37b-103">Troubleshoot procurement and sourcing workflows</span></span>

<span data-ttu-id="3d37b-104">Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lorsque vous utilisez des workflows d’approvisionnements.</span><span class="sxs-lookup"><span data-stu-id="3d37b-104">This topic describes how to fix issues that you might encounter while you work with procurement and sourcing workflows.</span></span>

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a><span data-ttu-id="3d37b-105">Erreur lors de la nouvelle soumission d'une commande fournisseur au workflow après une modification : "Les modifications de la commande fournisseur X ne sont autorisées qu'à l'état Brouillon lorsque la gestion des modifications est activée"</span><span class="sxs-lookup"><span data-stu-id="3d37b-105">Error when re-submitting a purchase order to the workflow after a change: "Changes to purchase order X are allowed only in a Draft state when change management is activated"</span></span>

<span data-ttu-id="3d37b-106">Ce problème se produit uniquement si la commande fournisseur était dans un état *Confirmé* avant la demande des modifications.</span><span class="sxs-lookup"><span data-stu-id="3d37b-106">This issue occurs only if the purchase order was in a *Confirmed* state before you requested changes.</span></span> <span data-ttu-id="3d37b-107">Si vous demandez des modifications alors que la commande fournisseur est dans un état *Approuvé*, le flux de travail peut être traité avec succès.</span><span class="sxs-lookup"><span data-stu-id="3d37b-107">If you request changes while the purchase order is in an *Approved* state, the workflow can be processed successfully.</span></span>

### <a name="error-description"></a><span data-ttu-id="3d37b-108">Description de l'erreur</span><span class="sxs-lookup"><span data-stu-id="3d37b-108">Error description</span></span>

<span data-ttu-id="3d37b-109">L'erreur suivante se produit dans le workflow lorsqu'une commande fournisseur est soumise à nouveau après une modification :</span><span class="sxs-lookup"><span data-stu-id="3d37b-109">The following error occurs in the workflow when a purchase order is resubmitted after a change:</span></span>

> <span data-ttu-id="3d37b-110">Bloqué (erreur) : X ++ Exception : les modifications de la commande fournisseur PO0000569 ne sont autorisées que dans l'état Brouillon lorsque la gestion des modifications est activée sur</span><span class="sxs-lookup"><span data-stu-id="3d37b-110">Stopped (error): X++ Exception: Changes to purchase order PO0000569 are only allowed in state Draft when change management is activated at</span></span><br>
<span data-ttu-id="3d37b-111">SysWorkflowParticipantProvider-resolve</span><span class="sxs-lookup"><span data-stu-id="3d37b-111">SysWorkflowParticipantProvider-resolve</span></span><br>
<span data-ttu-id="3d37b-112">SysWorkflowParticipantProvider-resolveParticipants</span><span class="sxs-lookup"><span data-stu-id="3d37b-112">SysWorkflowParticipantProvider-resolveParticipants</span></span><br>
<span data-ttu-id="3d37b-113">SysWorkflowServiceProvider-resolveParticipant</span><span class="sxs-lookup"><span data-stu-id="3d37b-113">SysWorkflowServiceProvider-resolveParticipant</span></span><br>
<span data-ttu-id="3d37b-114">SysWorkflowQueue-resume</span><span class="sxs-lookup"><span data-stu-id="3d37b-114">SysWorkflowQueue-resume</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3d37b-115">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="3d37b-115">Issue resolution</span></span>

<span data-ttu-id="3d37b-116">Ce problème peut se produire en raison d'une incohérence dans les répartitions des commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3d37b-116">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="3d37b-117">Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l'état *Brouillon*, allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="3d37b-117">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="3d37b-118">Pour plus d'informations, consultez l'article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="3d37b-118">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

<span data-ttu-id="3d37b-119">Le problème sera résolu via [cet article de la Base de connaissances Microsoft (KB)](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).</span><span class="sxs-lookup"><span data-stu-id="3d37b-119">The issue will be fixed through [this Microsoft Knowledge Base (KB) article](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).</span></span>

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a><span data-ttu-id="3d37b-120">Une ou plusieurs répartitions comptables sont sur-réparties ou sous-réparties.</span><span class="sxs-lookup"><span data-stu-id="3d37b-120">One or more accounting distributions are either over-distributed or under-distributed.</span></span>

<span data-ttu-id="3d37b-121">Ce problème peut se produire en raison d'une incohérence dans les répartitions des commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3d37b-121">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="3d37b-122">Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l'état *Brouillon*, allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="3d37b-122">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="3d37b-123">Pour plus d'informations, consultez l'article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="3d37b-123">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a><span data-ttu-id="3d37b-124">Si un solde de livraison est annulé sur une commande fournisseur où la gestion des modifications est activée, la commande fournisseur passe à l'état Confirmé.</span><span class="sxs-lookup"><span data-stu-id="3d37b-124">If a delivery remainder is canceled on a purchase order where change management is turned on, the purchase order goes to a Confirmed state.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3d37b-125">Description du problème</span><span class="sxs-lookup"><span data-stu-id="3d37b-125">Issue description</span></span>

<span data-ttu-id="3d37b-126">Pour une commande fournisseur faisant l'objet d'une gestion des modifications, si la seule modification demandée est l'annulation d'un solde de livraison sur une ou plusieurs des lignes, la commande fournisseur passera directement à l'état *Confirmé* quand elle sera approuvée, et aucun journal ne sera créé.</span><span class="sxs-lookup"><span data-stu-id="3d37b-126">For a purchase order that is subject to change management, if the only change that is requested is the cancellation of a delivery remainder on one or more of the lines, the purchase order will go directly to a *Confirmed* state when it's approved, and no journal will be created.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3d37b-127">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="3d37b-127">Issue resolution</span></span>

<span data-ttu-id="3d37b-128">L'annulation d'un solde de livraison n'affecte pas le contenu du journal de confirmation.</span><span class="sxs-lookup"><span data-stu-id="3d37b-128">Cancellation of a delivery remainder doesn't affect the contents of the confirmation journal.</span></span> <span data-ttu-id="3d37b-129">Cette fonctionnalité doit être utilisée lorsque la ligne a été partiellement reçue, et la qualité du solde doit être annulée à l'étape du processus après que la commande fournisseur a été confirmée avec le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3d37b-129">This functionality should be used when the line has been partially received, and the remainder quality should be canceled in the process step after the purchase order has been confirmed with the vendor.</span></span>

<span data-ttu-id="3d37b-130">Si cela doit être reflété sur la confirmation de la commande fournisseur, la quantité doit être ajustée sur la ligne de commande afin que la confirmation soit requise.</span><span class="sxs-lookup"><span data-stu-id="3d37b-130">If this should be reflected on the purchase order confirmation, the quantity should be adjusted on the purchase order line so that the confirmation will be required.</span></span> <span data-ttu-id="3d37b-131">Sinon, si rien n'a été reçu sur la ligne, la quantité peut être supprimée.</span><span class="sxs-lookup"><span data-stu-id="3d37b-131">Alternatively, if nothing has been received on the line, the quantity can be removed.</span></span> <span data-ttu-id="3d37b-132">Dans ce cas, une reconfirmation sera nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3d37b-132">In this case, reconfirmation will be required.</span></span>

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a><span data-ttu-id="3d37b-133">Les commandes fournisseur annulées apparaissent dans la liste des brouillons de l'espace de travail Préparation de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3d37b-133">Canceled purchase orders appear in the draft list in the Purchase order preparation workspace.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3d37b-134">Description du problème</span><span class="sxs-lookup"><span data-stu-id="3d37b-134">Issue description</span></span>

<span data-ttu-id="3d37b-135">Une que vous avez annulé les commandes fournisseur qui étaient dans un état *Confirmé*, les commandes fournisseur annulées apparaissent toujours dans la liste des brouillons de commande fournisseur dans l'espace de travail **Préparation de la commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="3d37b-135">After you cancel purchase orders that were in a *Confirmed* state, the canceled purchase orders still appear in the list of draft purchase orders in the **Purchase order preparation** workspace.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3d37b-136">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="3d37b-136">Issue resolution</span></span>

<span data-ttu-id="3d37b-137">Ce problème se produit uniquement pour les commandes fournisseur faisant l'objet d'une gestion des modifications.</span><span class="sxs-lookup"><span data-stu-id="3d37b-137">This issue occurs only for purchase orders that are subject to change management.</span></span> <span data-ttu-id="3d37b-138">Cela se produit parce que l'annulation est considérée comme un changement qui doit être approuvé.</span><span class="sxs-lookup"><span data-stu-id="3d37b-138">It occurs because the cancellation is considered a change that must be approved.</span></span> <span data-ttu-id="3d37b-139">L'approbation peut être effectuée automatiquement par le système.</span><span class="sxs-lookup"><span data-stu-id="3d37b-139">The approval can be done automatically by the system.</span></span> <span data-ttu-id="3d37b-140">Par conséquent, le processus consiste à soumettre la commande fournisseur annulée au workflow d'approbation afin qu'elle puisse passer à l'état *Approuvé*.</span><span class="sxs-lookup"><span data-stu-id="3d37b-140">Therefore, the process is to submit the canceled purchase order to the approval workflow so that it can go to an *Approved* state.</span></span> <span data-ttu-id="3d37b-141">À ce stade, la commande fournisseur n'apparaîtra plus dans la liste des brouillons de commande fournisseur dans l'espace de travail **Préparation de la commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="3d37b-141">At that point, the purchase order will no longer appear in the list of draft purchase orders in the **Purchase order preparation** workspace.</span></span>

