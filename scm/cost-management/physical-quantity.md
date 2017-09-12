---
title: Valeurs d'un objet de stock
description: "Cet article fournit des informations sur la manière dont les valeurs d'un objet de stock sont calculées."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 4aec6e70325c7e4d00e6070293a1ab0c719e420b
ms.contentlocale: fr-fr
ms.lasthandoff: 07/18/2017

---

# <a name="inventory-object-values"></a><span data-ttu-id="897ab-103">Valeurs d'un objet de stock</span><span class="sxs-lookup"><span data-stu-id="897ab-103">Inventory object values</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="897ab-104">Cet article fournit des informations sur la manière dont les valeurs d'un objet de stock sont calculées.</span><span class="sxs-lookup"><span data-stu-id="897ab-104">This article provides information about how the values of an inventory object are calculated.</span></span> 

<span data-ttu-id="897ab-105">Une nouvelle fonctionnalité nommée **quantité physique** vous permet de consulter les valeurs d'un objet de stock spécifique.</span><span class="sxs-lookup"><span data-stu-id="897ab-105">A new functionality that is named **physical quantity** lets you see the values of a specific inventory object.</span></span> 

<span data-ttu-id="897ab-106">Un objet de coût représente le niveau d'entité où est effectué le comptage d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="897ab-106">A cost object represents the entity level where inventory accounting is performed.</span></span> <span data-ttu-id="897ab-107">Pour plus d'informations sur les objets de coût, consultez [Objets de coût](cost-object.md).</span><span class="sxs-lookup"><span data-stu-id="897ab-107">For more information about cost objects, see [Cost objects](cost-object.md).</span></span> 

<span data-ttu-id="897ab-108">Pour afficher les valeurs d'un objet de stock spécifique, cliquez sur **Quantité physique** dans la page **Objet de coût**.</span><span class="sxs-lookup"><span data-stu-id="897ab-108">To see the values of a specific inventory object, click **Physical quantity** on the **Cost object** page.</span></span> <span data-ttu-id="897ab-109">Spécifiez comment la valeur d'un objet de stock est calculée :</span><span class="sxs-lookup"><span data-stu-id="897ab-109">Here is how the value of an inventory object is calculated:</span></span> 

<span data-ttu-id="897ab-110">Objet de stock. Valeur = Objet de coût.Coût unitaire moyen × Objet de stock.Quantité</span><span class="sxs-lookup"><span data-stu-id="897ab-110">Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity</span></span> 

<span data-ttu-id="897ab-111">L'exemple suivant montre comment les valeurs d'un objet de stock et d'un objet de coût sont calculées.</span><span class="sxs-lookup"><span data-stu-id="897ab-111">The following example shows how the values of an inventory object and a cost object are calculated.</span></span> <span data-ttu-id="897ab-112">Deux événements d'accusé de réception de marchandises sont enregistrés pour l'article A :</span><span class="sxs-lookup"><span data-stu-id="897ab-112">Two product receipt events are registered on item A:</span></span>

-   <span data-ttu-id="897ab-113">Accusé de réception de marchandises 1 : Quantité = 100., pcs, Montant = 1 000.00 USD, Site = 1, Entrepôt =11, N° de lot.</span><span class="sxs-lookup"><span data-stu-id="897ab-113">Product receipt 1: Quantity = 100 pcs., Amount = $1,000.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="897ab-114">= B1</span><span class="sxs-lookup"><span data-stu-id="897ab-114">= B1</span></span>
-   <span data-ttu-id="897ab-115">Accusé de réception de marchandises 2 : Quantité = 50., pcs, Montant = 800.00 USD, Site = 1, Entrepôt =11, N° de lot.</span><span class="sxs-lookup"><span data-stu-id="897ab-115">Product receipt 2: Quantity = 50 pcs., Amount = $800.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="897ab-116">= B2</span><span class="sxs-lookup"><span data-stu-id="897ab-116">= B2</span></span>

<span data-ttu-id="897ab-117">Le tableau suivant donne le résultat du calcul pour un objet de coût.</span><span class="sxs-lookup"><span data-stu-id="897ab-117">The following table shows the calculation result for a cost object.</span></span> <span data-ttu-id="897ab-118">Vous pouvez afficher le résultat dans la page **Objet de coût**.</span><span class="sxs-lookup"><span data-stu-id="897ab-118">You can view the result on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="897ab-119">Type d'objet</span><span class="sxs-lookup"><span data-stu-id="897ab-119">Object type</span></span></th>
<th><span data-ttu-id="897ab-120">Numéro d'article</span><span class="sxs-lookup"><span data-stu-id="897ab-120">Item number</span></span></th>
<th><span data-ttu-id="897ab-121">site ;</span><span class="sxs-lookup"><span data-stu-id="897ab-121">Site</span></span></th>
<th><span data-ttu-id="897ab-122">Quantité</span><span class="sxs-lookup"><span data-stu-id="897ab-122">Quantity</span></span></th>
<th><span data-ttu-id="897ab-123">Unité de stock</span><span class="sxs-lookup"><span data-stu-id="897ab-123">Inventory unit</span></span></th>
<th><span data-ttu-id="897ab-124">Valeur</span><span class="sxs-lookup"><span data-stu-id="897ab-124">Value</span></span></th>
<th><span data-ttu-id="897ab-125">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="897ab-125">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="897ab-126">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="897ab-126">Cost object</span></span></td>
<td><span data-ttu-id="897ab-127">A</span><span class="sxs-lookup"><span data-stu-id="897ab-127">A</span></span></td>
<td><span data-ttu-id="897ab-128">1</span><span class="sxs-lookup"><span data-stu-id="897ab-128">1</span></span></td>
<td><span data-ttu-id="897ab-129">150</span><span class="sxs-lookup"><span data-stu-id="897ab-129">150</span></span></td>
<td><span data-ttu-id="897ab-130">Pcs.</span><span class="sxs-lookup"><span data-stu-id="897ab-130">Pcs.</span></span></td>
<td><p><span data-ttu-id="897ab-131">1800,00 USD</span><span class="sxs-lookup"><span data-stu-id="897ab-131">$1800.00</span></span></p></td>
<td><p><span data-ttu-id="897ab-132">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="897ab-132">$12.00</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="897ab-133">Le tableau suivant donne le résultat du calcul pour un objet de stock.</span><span class="sxs-lookup"><span data-stu-id="897ab-133">The following table shows the calculation result for an inventory object.</span></span> <span data-ttu-id="897ab-134">Vous pouvez afficher le résultat en cliquant sur **Quantité physique** dans la page **Objet de coût**.</span><span class="sxs-lookup"><span data-stu-id="897ab-134">You can view the result by clicking **Physical quantity** on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="897ab-135">Type d'objet</span><span class="sxs-lookup"><span data-stu-id="897ab-135">Object type</span></span></th>
<th><span data-ttu-id="897ab-136">Numéro d'article</span><span class="sxs-lookup"><span data-stu-id="897ab-136">Item number</span></span></th>
<th><span data-ttu-id="897ab-137">site ;</span><span class="sxs-lookup"><span data-stu-id="897ab-137">Site</span></span></th>
<th><span data-ttu-id="897ab-138">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="897ab-138">Warehouse</span></span></th>
<th><span data-ttu-id="897ab-139">N° de lot</span><span class="sxs-lookup"><span data-stu-id="897ab-139">Batch No.</span></span></th>
<th><span data-ttu-id="897ab-140">Quantité</span><span class="sxs-lookup"><span data-stu-id="897ab-140">Quantity</span></span></th>
<th><span data-ttu-id="897ab-141">Unité de stock</span><span class="sxs-lookup"><span data-stu-id="897ab-141">Inventory unit</span></span></th>
<th><span data-ttu-id="897ab-142">Valeur</span><span class="sxs-lookup"><span data-stu-id="897ab-142">Value</span></span></th>
<th><span data-ttu-id="897ab-143">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="897ab-143">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="897ab-144">Objet de stock</span><span class="sxs-lookup"><span data-stu-id="897ab-144">Inventory object</span></span></td>
<td><span data-ttu-id="897ab-145">A</span><span class="sxs-lookup"><span data-stu-id="897ab-145">A</span></span></td>
<td><span data-ttu-id="897ab-146">1</span><span class="sxs-lookup"><span data-stu-id="897ab-146">1</span></span></td>
<td><span data-ttu-id="897ab-147">11</span><span class="sxs-lookup"><span data-stu-id="897ab-147">11</span></span></td>
<td><span data-ttu-id="897ab-148">B1</span><span class="sxs-lookup"><span data-stu-id="897ab-148">B1</span></span></td>
<td><span data-ttu-id="897ab-149">100</span><span class="sxs-lookup"><span data-stu-id="897ab-149">100</span></span></td>
<td><span data-ttu-id="897ab-150">Pcs.</span><span class="sxs-lookup"><span data-stu-id="897ab-150">Pcs.</span></span></td>
<td><p><span data-ttu-id="897ab-151">1200,00 USD</span><span class="sxs-lookup"><span data-stu-id="897ab-151">$1200.00</span></span></p></td>
<td><p><span data-ttu-id="897ab-152">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="897ab-152">$12.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="897ab-153">Objet de stock</span><span class="sxs-lookup"><span data-stu-id="897ab-153">Inventory object</span></span></td>
<td><span data-ttu-id="897ab-154">A</span><span class="sxs-lookup"><span data-stu-id="897ab-154">A</span></span></td>
<td><span data-ttu-id="897ab-155">1</span><span class="sxs-lookup"><span data-stu-id="897ab-155">1</span></span></td>
<td><span data-ttu-id="897ab-156">11</span><span class="sxs-lookup"><span data-stu-id="897ab-156">11</span></span></td>
<td><span data-ttu-id="897ab-157">B2</span><span class="sxs-lookup"><span data-stu-id="897ab-157">B2</span></span></td>
<td><span data-ttu-id="897ab-158">50</span><span class="sxs-lookup"><span data-stu-id="897ab-158">50</span></span></td>
<td><span data-ttu-id="897ab-159">Pcs.</span><span class="sxs-lookup"><span data-stu-id="897ab-159">Pcs.</span></span></td>
<td><p><span data-ttu-id="897ab-160">600,00 USD</span><span class="sxs-lookup"><span data-stu-id="897ab-160">$600.00</span></span></p></td>
<td><p><span data-ttu-id="897ab-161">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="897ab-161">$12.00</span></span></p></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="897ab-162">Voir également :</span><span class="sxs-lookup"><span data-stu-id="897ab-162">See also</span></span>
--------

[<span data-ttu-id="897ab-163">Objets de coût</span><span class="sxs-lookup"><span data-stu-id="897ab-163">Cost objects</span></span>](cost-object.md)

[<span data-ttu-id="897ab-164">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="897ab-164">Cost entries</span></span>](cost-entries.md)

[<span data-ttu-id="897ab-165">Nouveautés et changements</span><span class="sxs-lookup"><span data-stu-id="897ab-165">What's new and changed</span></span>](/dynamics365/unified-operations/dev-itpro/get-started/whats-new-changed)




