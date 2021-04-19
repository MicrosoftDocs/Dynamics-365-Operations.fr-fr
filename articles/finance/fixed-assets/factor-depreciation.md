---
title: Amortissement paramétrable
description: Cet article donne une vue d’ensemble de la méthode d’amortissement paramétrable.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8adfc91251ba1707c688fac6da04adaa9af1a47f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815690"
---
# <a name="factor-depreciation"></a><span data-ttu-id="7c2fd-103">Amortissement paramétrable</span><span class="sxs-lookup"><span data-stu-id="7c2fd-103">Factor depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7c2fd-104">Cet article donne une vue d’ensemble de la méthode d’amortissement paramétrable.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-104">This article gives an overview of the factor depreciation method.</span></span>

<span data-ttu-id="7c2fd-105">Les facteurs sont les pourcentages utilisés pour l’amortissement des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-105">Factors are the percentages that are used to depreciate assets.</span></span> <span data-ttu-id="7c2fd-106">Lorsque vous paramétrez un profil d’amortissement d’immobilisations et sélectionnez **Facteur** dans le champ **Méthode** de la page **Profils d’amortissement**, vous pouvez paramétrer un amortissement progressif, dégressif ou linéaire :</span><span class="sxs-lookup"><span data-stu-id="7c2fd-106">When you set up a fixed asset depreciation profile and select **Factor** in the **Method** field on the **Depreciation profiles** page, you can set up progressive, digressive, or straight line depreciation:</span></span>

-   <span data-ttu-id="7c2fd-107">Dans l’amortissement progressif, le montant d’amortissement augmente avec chaque période d’amortissement.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-107">In progressive depreciation, the amount of depreciation increases each depreciation period.</span></span>
-   <span data-ttu-id="7c2fd-108">Dans l’amortissement dégressif, le montant d’amortissement par période diminue dans le temps.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-108">In digressive depreciation, the amount of depreciation per period decreases over time.</span></span>
-   <span data-ttu-id="7c2fd-109">Dans l’amortissement linéaire, l’amortissement est identique pour chaque période.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-109">In straight line depreciation, the depreciation is the same in each period.</span></span>

<span data-ttu-id="7c2fd-110">Les règles et exemples suivants indiquent la procédure de paramétrage de facteurs pour chaque type d’amortissement.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-110">The rules and examples that follow indicate how you can set up factors for each type of depreciation.</span></span> 

> [!NOTE] 
> <span data-ttu-id="7c2fd-111">Lorsque vous sélectionnez **Facteur** dans le champ **Méthode**, le champ **Facteur** et le champ **Intervalle** s’affichent.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-111">When you select **Factor** in the **Method** field, the **Factor** field and the **Interval** field are displayed.</span></span>

## <a name="progressive-depreciation"></a><span data-ttu-id="7c2fd-112">Amortissement progressif</span><span class="sxs-lookup"><span data-stu-id="7c2fd-112">Progressive depreciation</span></span>
<span data-ttu-id="7c2fd-113">La valeur du champ **Facteur** est supérieure à **50**.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-113">The value in the **Factor** field is more than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="7c2fd-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="7c2fd-114">Example</span></span>

<span data-ttu-id="7c2fd-115">Le prix d’acquisition s’élève à 10 000, le facteur est de 70, la durée de vie est de 10 ans et l’amortissement débute le 1er janvier.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-115">The acquisition price is 100,000, the factor is 70, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="7c2fd-116">Les montants d’amortissement et de valeur comptable nette sont uniquement affichés pour les six premières années de la durée de vie.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-116">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="7c2fd-117">Année</span><span class="sxs-lookup"><span data-stu-id="7c2fd-117">Year</span></span> | <span data-ttu-id="7c2fd-118">Période</span><span class="sxs-lookup"><span data-stu-id="7c2fd-118">Period</span></span>      | <span data-ttu-id="7c2fd-119">Montant d’amortissement</span><span class="sxs-lookup"><span data-stu-id="7c2fd-119">Depreciation amount</span></span> | <span data-ttu-id="7c2fd-120">Valeur comptable nette</span><span class="sxs-lookup"><span data-stu-id="7c2fd-120">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="7c2fd-121">1</span><span class="sxs-lookup"><span data-stu-id="7c2fd-121">1</span></span>    | <span data-ttu-id="7c2fd-122">31 décembre</span><span class="sxs-lookup"><span data-stu-id="7c2fd-122">December 31</span></span> | <span data-ttu-id="7c2fd-123">307,69</span><span class="sxs-lookup"><span data-stu-id="7c2fd-123">307.69</span></span>              | <span data-ttu-id="7c2fd-124">99 692,31</span><span class="sxs-lookup"><span data-stu-id="7c2fd-124">99,692.31</span></span>             |
| <span data-ttu-id="7c2fd-125">2</span><span class="sxs-lookup"><span data-stu-id="7c2fd-125">2</span></span>    | <span data-ttu-id="7c2fd-126">31 décembre</span><span class="sxs-lookup"><span data-stu-id="7c2fd-126">December 31</span></span> | <span data-ttu-id="7c2fd-127">1 447,21</span><span class="sxs-lookup"><span data-stu-id="7c2fd-127">1,447.21</span></span>            | <span data-ttu-id="7c2fd-128">98 245,10</span><span class="sxs-lookup"><span data-stu-id="7c2fd-128">98,245.10</span></span>             |
| <span data-ttu-id="7c2fd-129">3</span><span class="sxs-lookup"><span data-stu-id="7c2fd-129">3</span></span>    | <span data-ttu-id="7c2fd-130">31 décembre</span><span class="sxs-lookup"><span data-stu-id="7c2fd-130">December 31</span></span> | <span data-ttu-id="7c2fd-131">3 104,50</span><span class="sxs-lookup"><span data-stu-id="7c2fd-131">3,104.50</span></span>            | <span data-ttu-id="7c2fd-132">95 140,60</span><span class="sxs-lookup"><span data-stu-id="7c2fd-132">95,140.60</span></span>             |
| <span data-ttu-id="7c2fd-133">4</span><span class="sxs-lookup"><span data-stu-id="7c2fd-133">4</span></span>    | <span data-ttu-id="7c2fd-134">31 décembre</span><span class="sxs-lookup"><span data-stu-id="7c2fd-134">December 31</span></span> | <span data-ttu-id="7c2fd-135">5 150,21</span><span class="sxs-lookup"><span data-stu-id="7c2fd-135">5,150.21</span></span>            | <span data-ttu-id="7c2fd-136">89 990,39</span><span class="sxs-lookup"><span data-stu-id="7c2fd-136">89,990.39</span></span>             |
| <span data-ttu-id="7c2fd-137">5</span><span class="sxs-lookup"><span data-stu-id="7c2fd-137">5</span></span>    | <span data-ttu-id="7c2fd-138">31 décembre</span><span class="sxs-lookup"><span data-stu-id="7c2fd-138">December 31</span></span> | <span data-ttu-id="7c2fd-139">7 522,95</span><span class="sxs-lookup"><span data-stu-id="7c2fd-139">7,522.95</span></span>            | <span data-ttu-id="7c2fd-140">82 467,44</span><span class="sxs-lookup"><span data-stu-id="7c2fd-140">82,467.44</span></span>             |
| <span data-ttu-id="7c2fd-141">6</span><span class="sxs-lookup"><span data-stu-id="7c2fd-141">6</span></span>    | <span data-ttu-id="7c2fd-142">31 décembre</span><span class="sxs-lookup"><span data-stu-id="7c2fd-142">December 31</span></span> | <span data-ttu-id="7c2fd-143">10 184,06</span><span class="sxs-lookup"><span data-stu-id="7c2fd-143">10,184.06</span></span>           | <span data-ttu-id="7c2fd-144">72 283,38</span><span class="sxs-lookup"><span data-stu-id="7c2fd-144">72,283.38</span></span>             |

## <a name="digressive-depreciation"></a><span data-ttu-id="7c2fd-145">Amortissement dégressif</span><span class="sxs-lookup"><span data-stu-id="7c2fd-145">Digressive depreciation</span></span>
<span data-ttu-id="7c2fd-146">La valeur du champ **Facteur** est inférieure à **50**.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-146">The value in the **Factor** field is less than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="7c2fd-147">Exemple</span><span class="sxs-lookup"><span data-stu-id="7c2fd-147">Example</span></span>

<span data-ttu-id="7c2fd-148">Le prix d’acquisition s’élève à 10 000, le facteur est de 20, la durée de vie est de 10 ans et l’amortissement débute le 1er janvier.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-148">The acquisition price is 100,000, the factor is 20, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="7c2fd-149">Les montants d’amortissement et de valeur comptable nette sont uniquement affichés pour les six premières années de la durée de vie.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-149">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="7c2fd-150">Année</span><span class="sxs-lookup"><span data-stu-id="7c2fd-150">Year</span></span> | <span data-ttu-id="7c2fd-151">Période</span><span class="sxs-lookup"><span data-stu-id="7c2fd-151">Period</span></span>      | <span data-ttu-id="7c2fd-152">Montant d’amortissement</span><span class="sxs-lookup"><span data-stu-id="7c2fd-152">Depreciation amount</span></span> | <span data-ttu-id="7c2fd-153">Valeur comptable nette</span><span class="sxs-lookup"><span data-stu-id="7c2fd-153">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="7c2fd-154">1</span><span class="sxs-lookup"><span data-stu-id="7c2fd-154">1</span></span>    | <span data-ttu-id="7c2fd-155">31 décembre</span><span class="sxs-lookup"><span data-stu-id="7c2fd-155">December 31</span></span> | <span data-ttu-id="7c2fd-156">56 080,43</span><span class="sxs-lookup"><span data-stu-id="7c2fd-156">56,080.43</span></span>           | <span data-ttu-id="7c2fd-157">43 919,57</span><span class="sxs-lookup"><span data-stu-id="7c2fd-157">43,919.57</span></span>             |
| <span data-ttu-id="7c2fd-158">2</span><span class="sxs-lookup"><span data-stu-id="7c2fd-158">2</span></span>    | <span data-ttu-id="7c2fd-159">31 décembre</span><span class="sxs-lookup"><span data-stu-id="7c2fd-159">December 31</span></span> | <span data-ttu-id="7c2fd-160">10 665,70</span><span class="sxs-lookup"><span data-stu-id="7c2fd-160">10,665.70</span></span>           | <span data-ttu-id="7c2fd-161">33 253,87</span><span class="sxs-lookup"><span data-stu-id="7c2fd-161">33,253.87</span></span>             |
| <span data-ttu-id="7c2fd-162">3</span><span class="sxs-lookup"><span data-stu-id="7c2fd-162">3</span></span>    | <span data-ttu-id="7c2fd-163">31 décembre</span><span class="sxs-lookup"><span data-stu-id="7c2fd-163">December 31</span></span> | <span data-ttu-id="7c2fd-164">7 156,22</span><span class="sxs-lookup"><span data-stu-id="7c2fd-164">7,156.22</span></span>            | <span data-ttu-id="7c2fd-165">26 097,65</span><span class="sxs-lookup"><span data-stu-id="7c2fd-165">26,097.65</span></span>             |
| <span data-ttu-id="7c2fd-166">4</span><span class="sxs-lookup"><span data-stu-id="7c2fd-166">4</span></span>    | <span data-ttu-id="7c2fd-167">31 décembre</span><span class="sxs-lookup"><span data-stu-id="7c2fd-167">December 31</span></span> | <span data-ttu-id="7c2fd-168">5 538,06</span><span class="sxs-lookup"><span data-stu-id="7c2fd-168">5,538.06</span></span>            | <span data-ttu-id="7c2fd-169">20 559,59</span><span class="sxs-lookup"><span data-stu-id="7c2fd-169">20,559.59</span></span>             |
| <span data-ttu-id="7c2fd-170">5</span><span class="sxs-lookup"><span data-stu-id="7c2fd-170">5</span></span>    | <span data-ttu-id="7c2fd-171">31 décembre</span><span class="sxs-lookup"><span data-stu-id="7c2fd-171">December 31</span></span> | <span data-ttu-id="7c2fd-172">4 579,89</span><span class="sxs-lookup"><span data-stu-id="7c2fd-172">4,579.89</span></span>            | <span data-ttu-id="7c2fd-173">15 979,70</span><span class="sxs-lookup"><span data-stu-id="7c2fd-173">15,979.70</span></span>             |
| <span data-ttu-id="7c2fd-174">6</span><span class="sxs-lookup"><span data-stu-id="7c2fd-174">6</span></span>    | <span data-ttu-id="7c2fd-175">31 décembre</span><span class="sxs-lookup"><span data-stu-id="7c2fd-175">December 31</span></span> | <span data-ttu-id="7c2fd-176">3 937,36</span><span class="sxs-lookup"><span data-stu-id="7c2fd-176">3,937.36</span></span>            | <span data-ttu-id="7c2fd-177">12 042,34</span><span class="sxs-lookup"><span data-stu-id="7c2fd-177">12,042.34</span></span>             |

## <a name="straight-line-depreciation"></a><span data-ttu-id="7c2fd-178">Amortissement linéaire</span><span class="sxs-lookup"><span data-stu-id="7c2fd-178">Straight line depreciation</span></span>
<span data-ttu-id="7c2fd-179">La valeur du champ **Facteur** est égale à **50**.</span><span class="sxs-lookup"><span data-stu-id="7c2fd-179">The value in the **Factor** field is equal to **50**.</span></span> <span data-ttu-id="7c2fd-180">Dans ce cas, l’amortissement est identique pour chaque période, et vous devez prendre en compte les implications des valeurs que vous avez spécifiées dans d’autres champs, comme décrit dans [Amortissement linéaire sur la durée de vie](straight-line-service-life-depreciation.md).</span><span class="sxs-lookup"><span data-stu-id="7c2fd-180">In this case, the depreciation is the same in each period, and you should consider the implications of the values that you have specified in other fields, as described in [Straight line service life depreciation](straight-line-service-life-depreciation.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]