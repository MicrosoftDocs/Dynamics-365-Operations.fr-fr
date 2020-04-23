---
title: Exemple de jours de réduction
description: Exemple de jours de réduction.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9d2407fde9dc586d296b0ddd61478aa84a71132
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204445"
---
# <a name="reduction-days-example"></a><span data-ttu-id="bf9b2-103">Exemple de jours de réduction</span><span class="sxs-lookup"><span data-stu-id="bf9b2-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="bf9b2-104">Vous avez créé une transaction d'abonnement pour un abonnement de maintenance d'un client, comme décrit dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="bf9b2-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bf9b2-105">Du</span><span class="sxs-lookup"><span data-stu-id="bf9b2-105">From date</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-106">Au</span><span class="sxs-lookup"><span data-stu-id="bf9b2-106">To date</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-107">Abonnement</span><span class="sxs-lookup"><span data-stu-id="bf9b2-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-108">Type d'abonnement</span><span class="sxs-lookup"><span data-stu-id="bf9b2-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-109">Projet</span><span class="sxs-lookup"><span data-stu-id="bf9b2-109">Project</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-110">Catégorie</span><span class="sxs-lookup"><span data-stu-id="bf9b2-110">Category</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-111">Devise de vente</span><span class="sxs-lookup"><span data-stu-id="bf9b2-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-112">Prix de vente</span><span class="sxs-lookup"><span data-stu-id="bf9b2-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf9b2-113">01 mars 2011</span><span class="sxs-lookup"><span data-stu-id="bf9b2-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="bf9b2-114">31 mars 2011</span><span class="sxs-lookup"><span data-stu-id="bf9b2-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="bf9b2-115">NR-2</span><span class="sxs-lookup"><span data-stu-id="bf9b2-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="bf9b2-116"><strong>Normal</strong></span><span class="sxs-lookup"><span data-stu-id="bf9b2-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="bf9b2-117">9013</span><span class="sxs-lookup"><span data-stu-id="bf9b2-117">9013</span></span></p></td>
<td><p><span data-ttu-id="bf9b2-118">SousCat2</span><span class="sxs-lookup"><span data-stu-id="bf9b2-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="bf9b2-119">EUR</span><span class="sxs-lookup"><span data-stu-id="bf9b2-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="bf9b2-120">200,00</span><span class="sxs-lookup"><span data-stu-id="bf9b2-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bf9b2-121">Le client signale qu'il n'a pas besoin d'une couverture de service pendant deux jours (10 et 11 mars).</span><span class="sxs-lookup"><span data-stu-id="bf9b2-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="bf9b2-122">Vous acceptez de réduire l'abonnement pour ces deux jours.</span><span class="sxs-lookup"><span data-stu-id="bf9b2-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="bf9b2-123">Vous créez une nouvelle transaction de type **Jours de réduction**, telle que décrite dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="bf9b2-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bf9b2-124">Date de début</span><span class="sxs-lookup"><span data-stu-id="bf9b2-124">From date</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-125">Au</span><span class="sxs-lookup"><span data-stu-id="bf9b2-125">To date</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-126">Abonnement</span><span class="sxs-lookup"><span data-stu-id="bf9b2-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-127">Type d'abonnement</span><span class="sxs-lookup"><span data-stu-id="bf9b2-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-128">Projet</span><span class="sxs-lookup"><span data-stu-id="bf9b2-128">Project</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-129">Catégorie</span><span class="sxs-lookup"><span data-stu-id="bf9b2-129">Category</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-130">Devise de vente</span><span class="sxs-lookup"><span data-stu-id="bf9b2-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="bf9b2-131">Prix de vente</span><span class="sxs-lookup"><span data-stu-id="bf9b2-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf9b2-132">10 mars 2011</span><span class="sxs-lookup"><span data-stu-id="bf9b2-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="bf9b2-133">11 mars 2011</span><span class="sxs-lookup"><span data-stu-id="bf9b2-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="bf9b2-134">NR-2</span><span class="sxs-lookup"><span data-stu-id="bf9b2-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="bf9b2-135"><strong>Jours de réduction</strong></span><span class="sxs-lookup"><span data-stu-id="bf9b2-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="bf9b2-136">9013</span><span class="sxs-lookup"><span data-stu-id="bf9b2-136">9013</span></span></p></td>
<td><p><span data-ttu-id="bf9b2-137">SousCat2</span><span class="sxs-lookup"><span data-stu-id="bf9b2-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="bf9b2-138">EUR</span><span class="sxs-lookup"><span data-stu-id="bf9b2-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="bf9b2-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="bf9b2-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bf9b2-140">Lorsque les transactions pour mars 2011 sont facturées, le prix de vente de 200 EUR est réduit de 12,90 EUR.</span><span class="sxs-lookup"><span data-stu-id="bf9b2-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="bf9b2-141">Le montant facturable pour la transaction d'abonnement est donc de 187,10 EUR et deux transactions sont facturées pour un total de 187,10 EUR.</span><span class="sxs-lookup"><span data-stu-id="bf9b2-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf9b2-142">Voir également :</span><span class="sxs-lookup"><span data-stu-id="bf9b2-142">See also</span></span>

[<span data-ttu-id="bf9b2-143">Réduction des jours sur les frais d'abonnement</span><span class="sxs-lookup"><span data-stu-id="bf9b2-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  


