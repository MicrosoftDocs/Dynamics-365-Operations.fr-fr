---
title: Valeurs d'un objet de stock
description: Cet article fournit des informations sur la manière dont les valeurs d'un objet de stock sont calculées.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e92c7889b11208c4d2b48eb279a104a7c226f904
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "319130"
---
# <a name="inventory-object-values"></a><span data-ttu-id="1edb7-103">Valeurs d'un objet de stock</span><span class="sxs-lookup"><span data-stu-id="1edb7-103">Inventory object values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1edb7-104">Cet article fournit des informations sur la manière dont les valeurs d'un objet de stock sont calculées.</span><span class="sxs-lookup"><span data-stu-id="1edb7-104">This article provides information about how the values of an inventory object are calculated.</span></span> 

<span data-ttu-id="1edb7-105">Une nouvelle fonctionnalité nommée **quantité physique** vous permet de consulter les valeurs d'un objet de stock spécifique.</span><span class="sxs-lookup"><span data-stu-id="1edb7-105">A new functionality that is named **physical quantity** lets you see the values of a specific inventory object.</span></span> 

<span data-ttu-id="1edb7-106">Un objet de coût représente le niveau d'entité où est effectué le comptage d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="1edb7-106">A cost object represents the entity level where inventory accounting is performed.</span></span> <span data-ttu-id="1edb7-107">Pour plus d'informations sur les objets de coût, consultez [Objets de coût](cost-object.md).</span><span class="sxs-lookup"><span data-stu-id="1edb7-107">For more information about cost objects, see [Cost objects](cost-object.md).</span></span> 

<span data-ttu-id="1edb7-108">Pour afficher les valeurs d'un objet de stock spécifique, cliquez sur **Quantité physique** dans la page **Objet de coût**.</span><span class="sxs-lookup"><span data-stu-id="1edb7-108">To see the values of a specific inventory object, click **Physical quantity** on the **Cost object** page.</span></span> <span data-ttu-id="1edb7-109">Spécifiez comment la valeur d'un objet de stock est calculée :</span><span class="sxs-lookup"><span data-stu-id="1edb7-109">Here is how the value of an inventory object is calculated:</span></span> 

<span data-ttu-id="1edb7-110">Objet de stock. Valeur = Objet de coût.Coût unitaire moyen × Objet de stock.Quantité</span><span class="sxs-lookup"><span data-stu-id="1edb7-110">Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity</span></span> 

<span data-ttu-id="1edb7-111">L'exemple suivant montre comment les valeurs d'un objet de stock et d'un objet de coût sont calculées.</span><span class="sxs-lookup"><span data-stu-id="1edb7-111">The following example shows how the values of an inventory object and a cost object are calculated.</span></span> <span data-ttu-id="1edb7-112">Deux événements d'accusé de réception de marchandises sont enregistrés pour l'article A :</span><span class="sxs-lookup"><span data-stu-id="1edb7-112">Two product receipt events are registered on item A:</span></span>

-   <span data-ttu-id="1edb7-113">Accusé de réception de marchandises 1 : Quantité = 100., pcs, Montant = 1 000.00 USD, Site = 1, Entrepôt =11, N° de lot.</span><span class="sxs-lookup"><span data-stu-id="1edb7-113">Product receipt 1: Quantity = 100 pcs., Amount = $1,000.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="1edb7-114">= B1</span><span class="sxs-lookup"><span data-stu-id="1edb7-114">= B1</span></span>
-   <span data-ttu-id="1edb7-115">Accusé de réception de marchandises 2 : Quantité = 50., pcs, Montant = 800.00 USD, Site = 1, Entrepôt =11, N° de lot.</span><span class="sxs-lookup"><span data-stu-id="1edb7-115">Product receipt 2: Quantity = 50 pcs., Amount = $800.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="1edb7-116">= B2</span><span class="sxs-lookup"><span data-stu-id="1edb7-116">= B2</span></span>

<span data-ttu-id="1edb7-117">Le tableau suivant donne le résultat du calcul pour un objet de coût.</span><span class="sxs-lookup"><span data-stu-id="1edb7-117">The following table shows the calculation result for a cost object.</span></span> <span data-ttu-id="1edb7-118">Vous pouvez afficher le résultat dans la page **Objet de coût**.</span><span class="sxs-lookup"><span data-stu-id="1edb7-118">You can view the result on the **Cost object** page.</span></span>

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
<th><span data-ttu-id="1edb7-119">Type d'objet</span><span class="sxs-lookup"><span data-stu-id="1edb7-119">Object type</span></span></th>
<th><span data-ttu-id="1edb7-120">Numéro d'article</span><span class="sxs-lookup"><span data-stu-id="1edb7-120">Item number</span></span></th>
<th><span data-ttu-id="1edb7-121">site ;</span><span class="sxs-lookup"><span data-stu-id="1edb7-121">Site</span></span></th>
<th><span data-ttu-id="1edb7-122">Quantité</span><span class="sxs-lookup"><span data-stu-id="1edb7-122">Quantity</span></span></th>
<th><span data-ttu-id="1edb7-123">Unité de stock</span><span class="sxs-lookup"><span data-stu-id="1edb7-123">Inventory unit</span></span></th>
<th><span data-ttu-id="1edb7-124">Valeur</span><span class="sxs-lookup"><span data-stu-id="1edb7-124">Value</span></span></th>
<th><span data-ttu-id="1edb7-125">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="1edb7-125">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1edb7-126">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="1edb7-126">Cost object</span></span></td>
<td><span data-ttu-id="1edb7-127">A</span><span class="sxs-lookup"><span data-stu-id="1edb7-127">A</span></span></td>
<td><span data-ttu-id="1edb7-128">1</span><span class="sxs-lookup"><span data-stu-id="1edb7-128">1</span></span></td>
<td><span data-ttu-id="1edb7-129">150</span><span class="sxs-lookup"><span data-stu-id="1edb7-129">150</span></span></td>
<td><span data-ttu-id="1edb7-130">Pcs.</span><span class="sxs-lookup"><span data-stu-id="1edb7-130">Pcs.</span></span></td>
<td><p><span data-ttu-id="1edb7-131">1800,00 USD</span><span class="sxs-lookup"><span data-stu-id="1edb7-131">$1800.00</span></span></p></td>
<td><p><span data-ttu-id="1edb7-132">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="1edb7-132">$12.00</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1edb7-133">Le tableau suivant donne le résultat du calcul pour un objet de stock.</span><span class="sxs-lookup"><span data-stu-id="1edb7-133">The following table shows the calculation result for an inventory object.</span></span> <span data-ttu-id="1edb7-134">Vous pouvez afficher le résultat en cliquant sur **Quantité physique** dans la page **Objet de coût**.</span><span class="sxs-lookup"><span data-stu-id="1edb7-134">You can view the result by clicking **Physical quantity** on the **Cost object** page.</span></span>

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
<th><span data-ttu-id="1edb7-135">Type d'objet</span><span class="sxs-lookup"><span data-stu-id="1edb7-135">Object type</span></span></th>
<th><span data-ttu-id="1edb7-136">Numéro d'article</span><span class="sxs-lookup"><span data-stu-id="1edb7-136">Item number</span></span></th>
<th><span data-ttu-id="1edb7-137">site ;</span><span class="sxs-lookup"><span data-stu-id="1edb7-137">Site</span></span></th>
<th><span data-ttu-id="1edb7-138">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="1edb7-138">Warehouse</span></span></th>
<th><span data-ttu-id="1edb7-139">N° de lot</span><span class="sxs-lookup"><span data-stu-id="1edb7-139">Batch No.</span></span></th>
<th><span data-ttu-id="1edb7-140">Quantité</span><span class="sxs-lookup"><span data-stu-id="1edb7-140">Quantity</span></span></th>
<th><span data-ttu-id="1edb7-141">Unité de stock</span><span class="sxs-lookup"><span data-stu-id="1edb7-141">Inventory unit</span></span></th>
<th><span data-ttu-id="1edb7-142">Valeur</span><span class="sxs-lookup"><span data-stu-id="1edb7-142">Value</span></span></th>
<th><span data-ttu-id="1edb7-143">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="1edb7-143">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1edb7-144">Objet de stock</span><span class="sxs-lookup"><span data-stu-id="1edb7-144">Inventory object</span></span></td>
<td><span data-ttu-id="1edb7-145">A</span><span class="sxs-lookup"><span data-stu-id="1edb7-145">A</span></span></td>
<td><span data-ttu-id="1edb7-146">1</span><span class="sxs-lookup"><span data-stu-id="1edb7-146">1</span></span></td>
<td><span data-ttu-id="1edb7-147">11</span><span class="sxs-lookup"><span data-stu-id="1edb7-147">11</span></span></td>
<td><span data-ttu-id="1edb7-148">B1</span><span class="sxs-lookup"><span data-stu-id="1edb7-148">B1</span></span></td>
<td><span data-ttu-id="1edb7-149">100</span><span class="sxs-lookup"><span data-stu-id="1edb7-149">100</span></span></td>
<td><span data-ttu-id="1edb7-150">Pcs.</span><span class="sxs-lookup"><span data-stu-id="1edb7-150">Pcs.</span></span></td>
<td><p><span data-ttu-id="1edb7-151">1200,00 USD</span><span class="sxs-lookup"><span data-stu-id="1edb7-151">$1200.00</span></span></p></td>
<td><p><span data-ttu-id="1edb7-152">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="1edb7-152">$12.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1edb7-153">Objet de stock</span><span class="sxs-lookup"><span data-stu-id="1edb7-153">Inventory object</span></span></td>
<td><span data-ttu-id="1edb7-154">A</span><span class="sxs-lookup"><span data-stu-id="1edb7-154">A</span></span></td>
<td><span data-ttu-id="1edb7-155">1</span><span class="sxs-lookup"><span data-stu-id="1edb7-155">1</span></span></td>
<td><span data-ttu-id="1edb7-156">11</span><span class="sxs-lookup"><span data-stu-id="1edb7-156">11</span></span></td>
<td><span data-ttu-id="1edb7-157">B2</span><span class="sxs-lookup"><span data-stu-id="1edb7-157">B2</span></span></td>
<td><span data-ttu-id="1edb7-158">50</span><span class="sxs-lookup"><span data-stu-id="1edb7-158">50</span></span></td>
<td><span data-ttu-id="1edb7-159">Pcs.</span><span class="sxs-lookup"><span data-stu-id="1edb7-159">Pcs.</span></span></td>
<td><p><span data-ttu-id="1edb7-160">600,00 USD</span><span class="sxs-lookup"><span data-stu-id="1edb7-160">$600.00</span></span></p></td>
<td><p><span data-ttu-id="1edb7-161">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="1edb7-161">$12.00</span></span></p></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="1edb7-162">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1edb7-162">Additional resources</span></span>
--------

[<span data-ttu-id="1edb7-163">Objets de coût</span><span class="sxs-lookup"><span data-stu-id="1edb7-163">Cost objects</span></span>](cost-object.md)

[<span data-ttu-id="1edb7-164">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="1edb7-164">Cost entries</span></span>](cost-entries.md)

[<span data-ttu-id="1edb7-165">Nouveautés et changements</span><span class="sxs-lookup"><span data-stu-id="1edb7-165">What's new and changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)



