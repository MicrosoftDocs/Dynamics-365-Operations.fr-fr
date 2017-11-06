---
title: Commandes fournisseur pour un projet
description: "Cet article décrit les différentes méthodes qui vous permettent de créer des commandes fournisseur pour un projet. La méthode que vous utilisez dépend de l'objectif de la commande fournisseur, la date à laquelle les articles achetés sont consommés et validés pour un projet."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0cf1effee6fd9e08b85d30f90c5e83aa77bc22cc
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="4bef2-104">Commandes fournisseur pour un projet</span><span class="sxs-lookup"><span data-stu-id="4bef2-104">Purchase orders for a project</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4bef2-105">Cet article décrit les différentes méthodes qui vous permettent de créer des commandes fournisseur pour un projet.</span><span class="sxs-lookup"><span data-stu-id="4bef2-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="4bef2-106">La méthode que vous utilisez dépend de l'objectif de la commande fournisseur, la date à laquelle les articles achetés sont consommés et validés pour un projet.</span><span class="sxs-lookup"><span data-stu-id="4bef2-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

<span data-ttu-id="4bef2-107">Dans Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, vous pouvez utiliser plusieurs méthodes pour créer des commandes fournisseur pour un projet.</span><span class="sxs-lookup"><span data-stu-id="4bef2-107">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, you can use multiple methods to create purchase orders for a project.</span></span> <span data-ttu-id="4bef2-108">La méthode que vous utilisez dépend de l'objectif de la commande fournisseur, la date à laquelle les articles achetés sont consommés, et celle à laquelle ils sont validés pour un projet.</span><span class="sxs-lookup"><span data-stu-id="4bef2-108">The method that you use depends on the purpose of the purchase order, when the purchased items are consumed, and when the purchased items are charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="4bef2-109">Méthodes de création d'une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="4bef2-109">Methods for creating a purchase order</span></span>

<span data-ttu-id="4bef2-110">Utilisez l'une des méthodes suivantes pour créer des commandes fournisseur dans Gestion et comptabilité des projets.</span><span class="sxs-lookup"><span data-stu-id="4bef2-110">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="4bef2-111">L'objectif de la commande fournisseur détermine quand celle-ci est consommée et donc le moment où les articles sont validés pour un projet.</span><span class="sxs-lookup"><span data-stu-id="4bef2-111">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bef2-112">Méthode</span><span class="sxs-lookup"><span data-stu-id="4bef2-112">Method</span></span></th>
<th><span data-ttu-id="4bef2-113">Objectif</span><span class="sxs-lookup"><span data-stu-id="4bef2-113">Purpose</span></span></th>
<th><span data-ttu-id="4bef2-114">Consommation d'articles</span><span class="sxs-lookup"><span data-stu-id="4bef2-114">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4bef2-115">Créer une commande fournisseur directement à partir d'un projet</span><span class="sxs-lookup"><span data-stu-id="4bef2-115">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="4bef2-116">Cette méthode permet d'acheter des articles à un fournisseur externe en vue d'une consommation sur un projet.</span><span class="sxs-lookup"><span data-stu-id="4bef2-116">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="4bef2-117">Vous pouvez créer une commande fournisseur de deux manières :</span><span class="sxs-lookup"><span data-stu-id="4bef2-117">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="4bef2-118">À partir du projet lui-même.</span><span class="sxs-lookup"><span data-stu-id="4bef2-118">From the project itself.</span></span> <span data-ttu-id="4bef2-119">Dans ce cas, le projet est déjà défini pour la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4bef2-119">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="4bef2-120">En accédant à la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4bef2-120">By navigating to the project purchase order.</span></span> <span data-ttu-id="4bef2-121">Vous devez sélectionner le fournisseur et le projet pour lequel créer la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4bef2-121">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="4bef2-122">Les articles sont consommés lorsque la facture fournisseur est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="4bef2-122">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4bef2-123">Créez une commande fournisseur à partir d'une commande client.</span><span class="sxs-lookup"><span data-stu-id="4bef2-123">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="4bef2-124">Utilisez cette méthode pour des articles achetés lorsque vous créez une commande client à partir d'un projet.</span><span class="sxs-lookup"><span data-stu-id="4bef2-124">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="4bef2-125">Des articles sont consommés lorsque la commande client est facturée au client.</span><span class="sxs-lookup"><span data-stu-id="4bef2-125">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4bef2-126">Créez une commande fournisseur à partir d'une demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="4bef2-126">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="4bef2-127">Utilisez cette méthode pour des articles achetés lorsque vous créez une demande d'articles à partir d'un projet.</span><span class="sxs-lookup"><span data-stu-id="4bef2-127">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="4bef2-128">Des articles sont consommés lors de la mise à jour du bon de livraison de demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="4bef2-128">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="4bef2-129">Lorsque vous mettez à jour la facture fournisseur ou le bon de livraison, vous êtes invité à mettre à jour le bon de livraison sur la demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="4bef2-129">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="4bef2-130">Pour plus d'informations, voir [Recevoir des articles sur une commande fournisseur à partir d'une demande d'articles](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="4bef2-130">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>


