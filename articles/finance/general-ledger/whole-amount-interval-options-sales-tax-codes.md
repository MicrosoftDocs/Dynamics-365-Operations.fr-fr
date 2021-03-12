---
title: Options de calcul Montant entier et Intervalle pour les codes taxe
description: Cet article décrit les options du champ Mode de calcul sous codes taxe et comment la taxe est calculée pour les intervalles et les montants entiers.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec724030e12e504625b2b102cba25b7eddbf7e96
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978434"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a><span data-ttu-id="c52ff-103">Options de calcul Montant entier et Intervalle pour les codes taxe</span><span class="sxs-lookup"><span data-stu-id="c52ff-103">Whole amount and Interval calculation options for sales tax codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c52ff-104">Cet article décrit les options du champ Mode de calcul sous codes taxe et comment la taxe est calculée pour les intervalles et les montants entiers.</span><span class="sxs-lookup"><span data-stu-id="c52ff-104">This article explains the options for the Calculation method field on sales tax codes and how sales tax is calculated for intervals and whole amounts.</span></span>

<span data-ttu-id="c52ff-105">Vous pouvez paramétrer un code taxe à calculer en fonction d’un montant entier ou d’un intervalle.</span><span class="sxs-lookup"><span data-stu-id="c52ff-105">You can set up a sales tax code to be calculated based on a whole amount or an interval amount.</span></span> <span data-ttu-id="c52ff-106">Dans la page Codes taxe, utilisez le champ Mode de calcul de l’organisateur Calcul pour sélectionner le mode de calcul du code taxe.</span><span class="sxs-lookup"><span data-stu-id="c52ff-106">In the Sales tax codes page, use the Calculation method field on the Calculation FastTab to select how to calculate a sales tax code.</span></span>
- <span data-ttu-id="c52ff-107">Montant entier – Le taux de taxe est appliqué au montant imposable entier.</span><span class="sxs-lookup"><span data-stu-id="c52ff-107">Whole amount – The tax rate is applied to the whole taxable amount.</span></span>
- <span data-ttu-id="c52ff-108">Intervalle – Le montant imposable est divisé en plusieurs parts s’inscrivant chacune dans une plage associée à un taux de taxe spécifique.</span><span class="sxs-lookup"><span data-stu-id="c52ff-108">Interval – The taxable amount is divided into parts, each of which falls in a range that has a specific sales tax rate.</span></span> <span data-ttu-id="c52ff-109">La part du montant s’inscrivant dans un intervalle donné est taxée au taux correspondant.</span><span class="sxs-lookup"><span data-stu-id="c52ff-109">The part of the amount that falls in a given interval is taxed according to the tax rate for that interval.</span></span> <span data-ttu-id="c52ff-110">La taxe est égale à la somme des montants de taxe calculés pour chaque intervalle.</span><span class="sxs-lookup"><span data-stu-id="c52ff-110">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>
  > [!NOTE]                                                                                                                              
  > <span data-ttu-id="c52ff-111">L’option Intervalle est disponible uniquement si vous sélectionnez Ligne dans le champ Mode de calcul de la zone Taxe de la page Paramètres de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="c52ff-111">The Interval option is available only when you select Line in the Calculation method field in the Sales tax area of the General ledger parameters page.</span></span> 

<span data-ttu-id="c52ff-112">Les intervalles sont paramétrés dans la page Valeurs de code taxe en entrant les montants limites minimal et maximal par taux de taxe.</span><span class="sxs-lookup"><span data-stu-id="c52ff-112">Intervals are set up in the Sales tax code values page by entering Minimum and Maximum limit amounts per tax rate.</span></span> <span data-ttu-id="c52ff-113">Pour que les taxes soient calculées sur tous les montants imposables (quelle que soit la méthode de calcul sélectionnée), les intervalles doivent être conformes aux règles suivantes :</span><span class="sxs-lookup"><span data-stu-id="c52ff-113">For taxes to be calculated on all taxable amounts, regardless of which calculation method is selected, intervals must follow these rules:</span></span>
-   <span data-ttu-id="c52ff-114">La limite minimale du premier intervalle doit être de zéro.</span><span class="sxs-lookup"><span data-stu-id="c52ff-114">The first interval must have a Minimum limit of zero.</span></span>
-   <span data-ttu-id="c52ff-115">La limite maximale du dernier intervalle doit être de zéro, valeur correspondant à l’infini.</span><span class="sxs-lookup"><span data-stu-id="c52ff-115">The last interval must have a Maximum limit of zero, which indicates infinity.</span></span>
-   <span data-ttu-id="c52ff-116">La limite maximale d’un intervalle doit également être la limite minimale de l’intervalle suivant.</span><span class="sxs-lookup"><span data-stu-id="c52ff-116">The Maximum limit of an interval must be the Minimum limit of the next interval.</span></span>

<span data-ttu-id="c52ff-117">Si un montant est égal à la limite maximale de l’intervalle précédent et à la limite minimale de l’intervalle suivant, le taux de taxe du premier intervalle s’applique.</span><span class="sxs-lookup"><span data-stu-id="c52ff-117">If an amount is the Maximum limit of the previous interval and the Minimum limit of the next interval, the sales tax rate of the first interval will be applied to the amount.</span></span> <span data-ttu-id="c52ff-118">Si un montant ne s’inscrit dans aucun des intervalles définis par les limites supérieure et inférieure, un taux de taxe nul est appliqué.</span><span class="sxs-lookup"><span data-stu-id="c52ff-118">If an amount falls outside the intervals that are defined by upper and lower limits, a sales tax rate of zero will be applied.</span></span>

## <a name="example-whole-amount-method-of-calculation"></a><span data-ttu-id="c52ff-119">Exemple : mode de calcul Montant entier</span><span class="sxs-lookup"><span data-stu-id="c52ff-119">Example: Whole amount method of calculation</span></span>
<span data-ttu-id="c52ff-120">Dans la page Valeurs de code taxe, les taux de taxe sont paramétrés dans les intervalles suivants :</span><span class="sxs-lookup"><span data-stu-id="c52ff-120">In the Sales tax code values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="c52ff-121">**Limite inférieure**</span><span class="sxs-lookup"><span data-stu-id="c52ff-121">**Minimum limit**</span></span> | <span data-ttu-id="c52ff-122">**Limite maximale**</span><span class="sxs-lookup"><span data-stu-id="c52ff-122">**Maximum limit**</span></span> | <span data-ttu-id="c52ff-123">**Taux de taxe**</span><span class="sxs-lookup"><span data-stu-id="c52ff-123">**Tax rate**</span></span> |
| <span data-ttu-id="c52ff-124">0,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-124">0.00</span></span>              | <span data-ttu-id="c52ff-125">50,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-125">50.00</span></span>             | <span data-ttu-id="c52ff-126">30 %</span><span class="sxs-lookup"><span data-stu-id="c52ff-126">30%</span></span>          |
| <span data-ttu-id="c52ff-127">50,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-127">50.00</span></span>             | <span data-ttu-id="c52ff-128">100,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-128">100.00</span></span>            | <span data-ttu-id="c52ff-129">20 %</span><span class="sxs-lookup"><span data-stu-id="c52ff-129">20%</span></span>          |
| <span data-ttu-id="c52ff-130">100,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-130">100.00</span></span>            | <span data-ttu-id="c52ff-131">0,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-131">0.00</span></span>              | <span data-ttu-id="c52ff-132">10 %</span><span class="sxs-lookup"><span data-stu-id="c52ff-132">10%</span></span>          |

<span data-ttu-id="c52ff-133">La taxe est calculée sur le montant imposable entier.</span><span class="sxs-lookup"><span data-stu-id="c52ff-133">The sales tax is calculated on the whole taxable amount.</span></span>

| <span data-ttu-id="c52ff-134">Montant imposable (prix)</span><span class="sxs-lookup"><span data-stu-id="c52ff-134">Taxable amount (price)</span></span> | <span data-ttu-id="c52ff-135">Calcul</span><span class="sxs-lookup"><span data-stu-id="c52ff-135">Calculation</span></span>    | <span data-ttu-id="c52ff-136">Taxe</span><span class="sxs-lookup"><span data-stu-id="c52ff-136">Sales tax</span></span> |
|------------------------|----------------|-----------|
| <span data-ttu-id="c52ff-137">35,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-137">35.00</span></span>                  | <span data-ttu-id="c52ff-138">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="c52ff-138">35.00 \* 0.30</span></span>  | <span data-ttu-id="c52ff-139">10,50</span><span class="sxs-lookup"><span data-stu-id="c52ff-139">10.50</span></span>     |
| <span data-ttu-id="c52ff-140">50,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-140">50.00</span></span>                  | <span data-ttu-id="c52ff-141">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="c52ff-141">50.00 \* 0.30</span></span>  | <span data-ttu-id="c52ff-142">15,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-142">15.00</span></span>     |
| <span data-ttu-id="c52ff-143">85,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-143">85.00</span></span>                  | <span data-ttu-id="c52ff-144">85,00 \* 0,20</span><span class="sxs-lookup"><span data-stu-id="c52ff-144">85.00 \* 0.20</span></span>  | <span data-ttu-id="c52ff-145">17,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-145">17.00</span></span>     |
| <span data-ttu-id="c52ff-146">305,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-146">305.00</span></span>                 | <span data-ttu-id="c52ff-147">305,00 \* 0,10</span><span class="sxs-lookup"><span data-stu-id="c52ff-147">305.00 \* 0.10</span></span> | <span data-ttu-id="c52ff-148">30,50</span><span class="sxs-lookup"><span data-stu-id="c52ff-148">30.50</span></span>     |

## <a name="example-interval-method-of-calculation"></a><span data-ttu-id="c52ff-149">Exemple de méthode de calcul Intervalle</span><span class="sxs-lookup"><span data-stu-id="c52ff-149">Example: Interval method of calculation</span></span>
<span data-ttu-id="c52ff-150">Dans la page Valeurs, les taux de taxe sont paramétrés dans les intervalles suivants :</span><span class="sxs-lookup"><span data-stu-id="c52ff-150">In the Values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="c52ff-151">**Limite inférieure**</span><span class="sxs-lookup"><span data-stu-id="c52ff-151">**Minimum limit**</span></span> | <span data-ttu-id="c52ff-152">**Limite maximale**</span><span class="sxs-lookup"><span data-stu-id="c52ff-152">**Maximum limit**</span></span> | <span data-ttu-id="c52ff-153">**Taux de taxe**</span><span class="sxs-lookup"><span data-stu-id="c52ff-153">**Tax rate**</span></span> |
| <span data-ttu-id="c52ff-154">0,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-154">0.00</span></span>              | <span data-ttu-id="c52ff-155">50,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-155">50.00</span></span>             | <span data-ttu-id="c52ff-156">30 %</span><span class="sxs-lookup"><span data-stu-id="c52ff-156">30%</span></span>          |
| <span data-ttu-id="c52ff-157">50,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-157">50.00</span></span>             | <span data-ttu-id="c52ff-158">100,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-158">100.00</span></span>            | <span data-ttu-id="c52ff-159">20 %</span><span class="sxs-lookup"><span data-stu-id="c52ff-159">20%</span></span>          |
| <span data-ttu-id="c52ff-160">100,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-160">100.00</span></span>            | <span data-ttu-id="c52ff-161">0,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-161">0.00</span></span>              | <span data-ttu-id="c52ff-162">10 %</span><span class="sxs-lookup"><span data-stu-id="c52ff-162">10%</span></span>          |

<span data-ttu-id="c52ff-163">La taxe est égale à la somme des montants de taxe calculés pour chaque intervalle.</span><span class="sxs-lookup"><span data-stu-id="c52ff-163">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>

| <span data-ttu-id="c52ff-164">Montant imposable (prix)</span><span class="sxs-lookup"><span data-stu-id="c52ff-164">Taxable amount (price)</span></span> | <span data-ttu-id="c52ff-165">Calcul</span><span class="sxs-lookup"><span data-stu-id="c52ff-165">Calculation</span></span>                                                               | <span data-ttu-id="c52ff-166">Taxe</span><span class="sxs-lookup"><span data-stu-id="c52ff-166">Sales tax</span></span> |
|------------------------|---------------------------------------------------------------------------|-----------|
| <span data-ttu-id="c52ff-167">35,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-167">35.00</span></span>                  | <span data-ttu-id="c52ff-168">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="c52ff-168">35.00 \* 0.30</span></span>                                                             | <span data-ttu-id="c52ff-169">10,50</span><span class="sxs-lookup"><span data-stu-id="c52ff-169">10.50</span></span>     |
| <span data-ttu-id="c52ff-170">50,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-170">50.00</span></span>                  | <span data-ttu-id="c52ff-171">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="c52ff-171">50.00 \* 0.30</span></span>                                                             | <span data-ttu-id="c52ff-172">15,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-172">15.00</span></span>     |
| <span data-ttu-id="c52ff-173">85,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-173">85.00</span></span>                  | <span data-ttu-id="c52ff-174">(50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)</span><span class="sxs-lookup"><span data-stu-id="c52ff-174">(50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)</span></span>                          | <span data-ttu-id="c52ff-175">22,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-175">22.00</span></span>     |
| <span data-ttu-id="c52ff-176">305,00</span><span class="sxs-lookup"><span data-stu-id="c52ff-176">305.00</span></span>                 | <span data-ttu-id="c52ff-177">(50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50)</span><span class="sxs-lookup"><span data-stu-id="c52ff-177">(50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50)</span></span> | <span data-ttu-id="c52ff-178">45.50</span><span class="sxs-lookup"><span data-stu-id="c52ff-178">45.50</span></span>     |



<span data-ttu-id="c52ff-179">Pour plus d’informations, voir [Taux de taxe en fonction des champs Base marginale et Modes de calcul](marginal-base-field.md).</span><span class="sxs-lookup"><span data-stu-id="c52ff-179">For more information, see [Sales tax rates based on the Marginal base and Calculation methods](marginal-base-field.md).</span></span>





