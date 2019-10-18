---
title: Amortissement paramétrable
description: Cet article donne une vue d'ensemble de la méthode d'amortissement paramétrable.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5c36441e926cd5a82c802a350adf6b2ed6d6387
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177705"
---
# <a name="factor-depreciation"></a><span data-ttu-id="d7b5a-103">Amortissement paramétrable</span><span class="sxs-lookup"><span data-stu-id="d7b5a-103">Factor depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d7b5a-104">Cet article donne une vue d'ensemble de la méthode d'amortissement paramétrable.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-104">This article gives an overview of the factor depreciation method.</span></span>

<span data-ttu-id="d7b5a-105">Les facteurs sont les pourcentages utilisés pour l'amortissement des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-105">Factors are the percentages that are used to depreciate assets.</span></span> <span data-ttu-id="d7b5a-106">Lorsque vous paramétrez un profil d'amortissement d'immobilisations et sélectionnez **Facteur** dans le champ **Méthode** de la page **Profils d'amortissement**, vous pouvez paramétrer un amortissement progressif, dégressif ou linéaire :</span><span class="sxs-lookup"><span data-stu-id="d7b5a-106">When you set up a fixed asset depreciation profile and select **Factor** in the **Method** field on the **Depreciation profiles** page, you can set up progressive, digressive, or straight line depreciation:</span></span>

-   <span data-ttu-id="d7b5a-107">Dans l'amortissement progressif, le montant d'amortissement augmente avec chaque période d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-107">In progressive depreciation, the amount of depreciation increases each depreciation period.</span></span>
-   <span data-ttu-id="d7b5a-108">Dans l'amortissement dégressif, le montant d'amortissement par période diminue dans le temps.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-108">In digressive depreciation, the amount of depreciation per period decreases over time.</span></span>
-   <span data-ttu-id="d7b5a-109">Dans l'amortissement linéaire, l'amortissement est identique pour chaque période.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-109">In straight line depreciation, the depreciation is the same in each period.</span></span>

<span data-ttu-id="d7b5a-110">Les règles et exemples suivants indiquent la procédure de paramétrage de facteurs pour chaque type d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-110">The rules and examples that follow indicate how you can set up factors for each type of depreciation.</span></span> 

> [!NOTE] 
> <span data-ttu-id="d7b5a-111">Lorsque vous sélectionnez **Facteur** dans le champ **Méthode**, le champ **Facteur** et le champ **Intervalle** s'affichent.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-111">When you select **Factor** in the **Method** field, the **Factor** field and the **Interval** field are displayed.</span></span>

## <a name="progressive-depreciation"></a><span data-ttu-id="d7b5a-112">Amortissement progressif</span><span class="sxs-lookup"><span data-stu-id="d7b5a-112">Progressive depreciation</span></span>
<span data-ttu-id="d7b5a-113">La valeur du champ **Facteur** est supérieure à **50**.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-113">The value in the **Factor** field is more than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="d7b5a-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="d7b5a-114">Example</span></span>

<span data-ttu-id="d7b5a-115">Le prix d'acquisition s'élève à 10 000, le facteur est de 70, la durée de vie est de 10 ans et l'amortissement débute le 1er janvier.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-115">The acquisition price is 100,000, the factor is 70, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="d7b5a-116">Les montants d'amortissement et de valeur comptable nette sont uniquement affichés pour les six premières années de la durée de vie.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-116">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="d7b5a-117">Année</span><span class="sxs-lookup"><span data-stu-id="d7b5a-117">Year</span></span> | <span data-ttu-id="d7b5a-118">Période</span><span class="sxs-lookup"><span data-stu-id="d7b5a-118">Period</span></span>      | <span data-ttu-id="d7b5a-119">Montant d'amortissement</span><span class="sxs-lookup"><span data-stu-id="d7b5a-119">Depreciation amount</span></span> | <span data-ttu-id="d7b5a-120">Valeur comptable nette</span><span class="sxs-lookup"><span data-stu-id="d7b5a-120">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="d7b5a-121">1</span><span class="sxs-lookup"><span data-stu-id="d7b5a-121">1</span></span>    | <span data-ttu-id="d7b5a-122">31 décembre</span><span class="sxs-lookup"><span data-stu-id="d7b5a-122">December 31</span></span> | <span data-ttu-id="d7b5a-123">307,69</span><span class="sxs-lookup"><span data-stu-id="d7b5a-123">307.69</span></span>              | <span data-ttu-id="d7b5a-124">99 692,31</span><span class="sxs-lookup"><span data-stu-id="d7b5a-124">99,692.31</span></span>             |
| <span data-ttu-id="d7b5a-125">2</span><span class="sxs-lookup"><span data-stu-id="d7b5a-125">2</span></span>    | <span data-ttu-id="d7b5a-126">31 décembre</span><span class="sxs-lookup"><span data-stu-id="d7b5a-126">December 31</span></span> | <span data-ttu-id="d7b5a-127">1 447,21</span><span class="sxs-lookup"><span data-stu-id="d7b5a-127">1,447.21</span></span>            | <span data-ttu-id="d7b5a-128">98 245,10</span><span class="sxs-lookup"><span data-stu-id="d7b5a-128">98,245.10</span></span>             |
| <span data-ttu-id="d7b5a-129">3</span><span class="sxs-lookup"><span data-stu-id="d7b5a-129">3</span></span>    | <span data-ttu-id="d7b5a-130">31 décembre</span><span class="sxs-lookup"><span data-stu-id="d7b5a-130">December 31</span></span> | <span data-ttu-id="d7b5a-131">3 104,50</span><span class="sxs-lookup"><span data-stu-id="d7b5a-131">3,104.50</span></span>            | <span data-ttu-id="d7b5a-132">95 140,60</span><span class="sxs-lookup"><span data-stu-id="d7b5a-132">95,140.60</span></span>             |
| <span data-ttu-id="d7b5a-133">4</span><span class="sxs-lookup"><span data-stu-id="d7b5a-133">4</span></span>    | <span data-ttu-id="d7b5a-134">31 décembre</span><span class="sxs-lookup"><span data-stu-id="d7b5a-134">December 31</span></span> | <span data-ttu-id="d7b5a-135">5 150,21</span><span class="sxs-lookup"><span data-stu-id="d7b5a-135">5,150.21</span></span>            | <span data-ttu-id="d7b5a-136">89 990,39</span><span class="sxs-lookup"><span data-stu-id="d7b5a-136">89,990.39</span></span>             |
| <span data-ttu-id="d7b5a-137">5</span><span class="sxs-lookup"><span data-stu-id="d7b5a-137">5</span></span>    | <span data-ttu-id="d7b5a-138">31 décembre</span><span class="sxs-lookup"><span data-stu-id="d7b5a-138">December 31</span></span> | <span data-ttu-id="d7b5a-139">7 522,95</span><span class="sxs-lookup"><span data-stu-id="d7b5a-139">7,522.95</span></span>            | <span data-ttu-id="d7b5a-140">82 467,44</span><span class="sxs-lookup"><span data-stu-id="d7b5a-140">82,467.44</span></span>             |
| <span data-ttu-id="d7b5a-141">6</span><span class="sxs-lookup"><span data-stu-id="d7b5a-141">6</span></span>    | <span data-ttu-id="d7b5a-142">31 décembre</span><span class="sxs-lookup"><span data-stu-id="d7b5a-142">December 31</span></span> | <span data-ttu-id="d7b5a-143">10 184,06</span><span class="sxs-lookup"><span data-stu-id="d7b5a-143">10,184.06</span></span>           | <span data-ttu-id="d7b5a-144">72 283,38</span><span class="sxs-lookup"><span data-stu-id="d7b5a-144">72,283.38</span></span>             |

## <a name="digressive-depreciation"></a><span data-ttu-id="d7b5a-145">Amortissement dégressif</span><span class="sxs-lookup"><span data-stu-id="d7b5a-145">Digressive depreciation</span></span>
<span data-ttu-id="d7b5a-146">La valeur du champ **Facteur** est inférieure à **50**.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-146">The value in the **Factor** field is less than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="d7b5a-147">Exemple</span><span class="sxs-lookup"><span data-stu-id="d7b5a-147">Example</span></span>

<span data-ttu-id="d7b5a-148">Le prix d'acquisition s'élève à 10 000, le facteur est de 20, la durée de vie est de 10 ans et l'amortissement débute le 1er janvier.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-148">The acquisition price is 100,000, the factor is 20, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="d7b5a-149">Les montants d'amortissement et de valeur comptable nette sont uniquement affichés pour les six premières années de la durée de vie.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-149">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="d7b5a-150">Année</span><span class="sxs-lookup"><span data-stu-id="d7b5a-150">Year</span></span> | <span data-ttu-id="d7b5a-151">Période</span><span class="sxs-lookup"><span data-stu-id="d7b5a-151">Period</span></span>      | <span data-ttu-id="d7b5a-152">Montant d'amortissement</span><span class="sxs-lookup"><span data-stu-id="d7b5a-152">Depreciation amount</span></span> | <span data-ttu-id="d7b5a-153">Valeur comptable nette</span><span class="sxs-lookup"><span data-stu-id="d7b5a-153">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="d7b5a-154">1</span><span class="sxs-lookup"><span data-stu-id="d7b5a-154">1</span></span>    | <span data-ttu-id="d7b5a-155">31 décembre</span><span class="sxs-lookup"><span data-stu-id="d7b5a-155">December 31</span></span> | <span data-ttu-id="d7b5a-156">56 080,43</span><span class="sxs-lookup"><span data-stu-id="d7b5a-156">56,080.43</span></span>           | <span data-ttu-id="d7b5a-157">43 919,57</span><span class="sxs-lookup"><span data-stu-id="d7b5a-157">43,919.57</span></span>             |
| <span data-ttu-id="d7b5a-158">2</span><span class="sxs-lookup"><span data-stu-id="d7b5a-158">2</span></span>    | <span data-ttu-id="d7b5a-159">31 décembre</span><span class="sxs-lookup"><span data-stu-id="d7b5a-159">December 31</span></span> | <span data-ttu-id="d7b5a-160">10 665,70</span><span class="sxs-lookup"><span data-stu-id="d7b5a-160">10,665.70</span></span>           | <span data-ttu-id="d7b5a-161">33 253,87</span><span class="sxs-lookup"><span data-stu-id="d7b5a-161">33,253.87</span></span>             |
| <span data-ttu-id="d7b5a-162">3</span><span class="sxs-lookup"><span data-stu-id="d7b5a-162">3</span></span>    | <span data-ttu-id="d7b5a-163">31 décembre</span><span class="sxs-lookup"><span data-stu-id="d7b5a-163">December 31</span></span> | <span data-ttu-id="d7b5a-164">7 156,22</span><span class="sxs-lookup"><span data-stu-id="d7b5a-164">7,156.22</span></span>            | <span data-ttu-id="d7b5a-165">26 097,65</span><span class="sxs-lookup"><span data-stu-id="d7b5a-165">26,097.65</span></span>             |
| <span data-ttu-id="d7b5a-166">4</span><span class="sxs-lookup"><span data-stu-id="d7b5a-166">4</span></span>    | <span data-ttu-id="d7b5a-167">31 décembre</span><span class="sxs-lookup"><span data-stu-id="d7b5a-167">December 31</span></span> | <span data-ttu-id="d7b5a-168">5 538,06</span><span class="sxs-lookup"><span data-stu-id="d7b5a-168">5,538.06</span></span>            | <span data-ttu-id="d7b5a-169">20 559,59</span><span class="sxs-lookup"><span data-stu-id="d7b5a-169">20,559.59</span></span>             |
| <span data-ttu-id="d7b5a-170">5</span><span class="sxs-lookup"><span data-stu-id="d7b5a-170">5</span></span>    | <span data-ttu-id="d7b5a-171">31 décembre</span><span class="sxs-lookup"><span data-stu-id="d7b5a-171">December 31</span></span> | <span data-ttu-id="d7b5a-172">4 579,89</span><span class="sxs-lookup"><span data-stu-id="d7b5a-172">4,579.89</span></span>            | <span data-ttu-id="d7b5a-173">15 979,70</span><span class="sxs-lookup"><span data-stu-id="d7b5a-173">15,979.70</span></span>             |
| <span data-ttu-id="d7b5a-174">6</span><span class="sxs-lookup"><span data-stu-id="d7b5a-174">6</span></span>    | <span data-ttu-id="d7b5a-175">31 décembre</span><span class="sxs-lookup"><span data-stu-id="d7b5a-175">December 31</span></span> | <span data-ttu-id="d7b5a-176">3 937,36</span><span class="sxs-lookup"><span data-stu-id="d7b5a-176">3,937.36</span></span>            | <span data-ttu-id="d7b5a-177">12 042,34</span><span class="sxs-lookup"><span data-stu-id="d7b5a-177">12,042.34</span></span>             |

## <a name="straight-line-depreciation"></a><span data-ttu-id="d7b5a-178">Amortissement linéaire</span><span class="sxs-lookup"><span data-stu-id="d7b5a-178">Straight line depreciation</span></span>
<span data-ttu-id="d7b5a-179">La valeur du champ **Facteur** est égale à **50**.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-179">The value in the **Factor** field is equal to **50**.</span></span> <span data-ttu-id="d7b5a-180">Dans ce cas, l'amortissement est identique pour chaque période, et vous devez prendre en compte les implications des valeurs que vous avez spécifiées dans d'autres champs, comme décrit dans [Amortissement linéaire sur la durée de vie](straight-line-service-life-depreciation.md).</span><span class="sxs-lookup"><span data-stu-id="d7b5a-180">In this case, the depreciation is the same in each period, and you should consider the implications of the values that you have specified in other fields, as described in [Straight line service life depreciation](straight-line-service-life-depreciation.md).</span></span>



