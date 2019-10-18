---
title: Commandes fournisseur pour un projet
description: Cet article décrit les différentes méthodes qui vous permettent de créer des commandes fournisseur pour un projet. La méthode que vous utilisez dépend de l'objectif de la commande fournisseur, la date à laquelle les articles achetés sont consommés et validés pour un projet.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4975b9f9e20906fb1259e36a07d8ef3db4f4fee
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174556"
---
# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="ef51e-104">Commandes fournisseur pour un projet</span><span class="sxs-lookup"><span data-stu-id="ef51e-104">Purchase orders for a project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef51e-105">Cet article décrit les différentes méthodes qui vous permettent de créer des commandes fournisseur pour un projet.</span><span class="sxs-lookup"><span data-stu-id="ef51e-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="ef51e-106">La méthode que vous utilisez dépend de l'objectif de la commande fournisseur, la date à laquelle les articles achetés sont consommés et validés pour un projet.</span><span class="sxs-lookup"><span data-stu-id="ef51e-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="ef51e-107">Méthodes de création d'une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="ef51e-107">Methods for creating a purchase order</span></span>

<span data-ttu-id="ef51e-108">Utilisez l'une des méthodes suivantes pour créer des commandes fournisseur dans Gestion et comptabilité des projets.</span><span class="sxs-lookup"><span data-stu-id="ef51e-108">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="ef51e-109">L'objectif de la commande fournisseur détermine quand celle-ci est consommée et donc le moment où les articles sont validés pour un projet.</span><span class="sxs-lookup"><span data-stu-id="ef51e-109">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef51e-110">Méthode</span><span class="sxs-lookup"><span data-stu-id="ef51e-110">Method</span></span></th>
<th><span data-ttu-id="ef51e-111">Objectif</span><span class="sxs-lookup"><span data-stu-id="ef51e-111">Purpose</span></span></th>
<th><span data-ttu-id="ef51e-112">Consommation d'articles</span><span class="sxs-lookup"><span data-stu-id="ef51e-112">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ef51e-113">Créer une commande fournisseur directement à partir d'un projet</span><span class="sxs-lookup"><span data-stu-id="ef51e-113">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="ef51e-114">Cette méthode permet d'acheter des articles à un fournisseur externe en vue d'une consommation sur un projet.</span><span class="sxs-lookup"><span data-stu-id="ef51e-114">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="ef51e-115">Vous pouvez créer une commande fournisseur de deux manières :</span><span class="sxs-lookup"><span data-stu-id="ef51e-115">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="ef51e-116">À partir du projet lui-même.</span><span class="sxs-lookup"><span data-stu-id="ef51e-116">From the project itself.</span></span> <span data-ttu-id="ef51e-117">Dans ce cas, le projet est déjà défini pour la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="ef51e-117">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="ef51e-118">En accédant à la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="ef51e-118">By navigating to the project purchase order.</span></span> <span data-ttu-id="ef51e-119">Vous devez sélectionner le fournisseur et le projet pour lequel créer la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="ef51e-119">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="ef51e-120">Les articles sont consommés lorsque la facture fournisseur est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="ef51e-120">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ef51e-121">Créez une commande fournisseur à partir d'une commande client.</span><span class="sxs-lookup"><span data-stu-id="ef51e-121">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="ef51e-122">Utilisez cette méthode pour des articles achetés lorsque vous créez une commande client à partir d'un projet.</span><span class="sxs-lookup"><span data-stu-id="ef51e-122">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="ef51e-123">Des articles sont consommés lorsque la commande client est facturée au client.</span><span class="sxs-lookup"><span data-stu-id="ef51e-123">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ef51e-124">Créez une commande fournisseur à partir d'une demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="ef51e-124">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="ef51e-125">Utilisez cette méthode pour des articles achetés lorsque vous créez une demande d'articles à partir d'un projet.</span><span class="sxs-lookup"><span data-stu-id="ef51e-125">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="ef51e-126">Des articles sont consommés lors de la mise à jour du bon de livraison de demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="ef51e-126">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="ef51e-127">Lorsque vous mettez à jour la facture fournisseur ou le bon de livraison, vous êtes invité à mettre à jour le bon de livraison sur la demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="ef51e-127">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="ef51e-128">Pour plus d'informations, voir [Recevoir des articles sur une commande fournisseur à partir d'une demande d'articles](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="ef51e-128">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>

