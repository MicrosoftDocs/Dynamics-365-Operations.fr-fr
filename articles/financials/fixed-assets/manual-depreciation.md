---
title: Amortissement manuel
description: "Cet article donne une vue d'ensemble de la méthode d'amortissement manuelle."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d7a672b80a0da7ab05acf5b5efe041f0f89c0042
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="manual-depreciation"></a><span data-ttu-id="478ce-103">Amortissement manuel</span><span class="sxs-lookup"><span data-stu-id="478ce-103">Manual depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="478ce-104">Cet article donne une vue d'ensemble de la méthode d'amortissement manuelle.</span><span class="sxs-lookup"><span data-stu-id="478ce-104">This article gives an overview of the manual depreciation method.</span></span>

<span data-ttu-id="478ce-105">Lorsque vous paramétrez un profil d'amortissement d'immobilisation et sélectionnez **Manuel** dans le champ **Méthode** de la page **Profils d'amortissement**, l'amortissement des immobilisations affectées au profil d'amortissement est déterminé par le pourcentage que vous spécifiez pour chaque intervalle dans l'année civile.</span><span class="sxs-lookup"><span data-stu-id="478ce-105">When you set up a fixed asset depreciation profile and select **Manual** in the **Method** field on the **Depreciation profiles** page, the depreciation of fixed assets that are assigned to the depreciation profile is determined by the percentage that you enter for each interval in the calendar year.</span></span> <span data-ttu-id="478ce-106">Les intervalles pour lesquels vous paramétrez des pourcentages sont validés en fonction de la valeur sélectionnée dans le champ **Période fréquence** de l'organisateur **Général** de la page **Profils d'amortissement**.</span><span class="sxs-lookup"><span data-stu-id="478ce-106">The intervals that you set up percentages for are posted according to the value that you select in the **Period frequency** field on the **General** FastTab of the **Depreciation profiles** page.</span></span> <span data-ttu-id="478ce-107">Les valeurs que vous pouvez sélectionner sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="478ce-107">Here are the values that you can select:</span></span>

-   <span data-ttu-id="478ce-108">Tous les ans</span><span class="sxs-lookup"><span data-stu-id="478ce-108">Yearly</span></span>
-   <span data-ttu-id="478ce-109">Mensuel</span><span class="sxs-lookup"><span data-stu-id="478ce-109">Monthly</span></span>
-   <span data-ttu-id="478ce-110">Trimestriel</span><span class="sxs-lookup"><span data-stu-id="478ce-110">Quarterly</span></span>
-   <span data-ttu-id="478ce-111">Semestriel</span><span class="sxs-lookup"><span data-stu-id="478ce-111">Half-Yearly</span></span>
-   <span data-ttu-id="478ce-112">Opérations diverses</span><span class="sxs-lookup"><span data-stu-id="478ce-112">Daily</span></span>

<span data-ttu-id="478ce-113">Après avoir sélectionné la fréquence de période, cliquez sur **Programmes manuels** et paramétrez les pourcentages pour chaque intervalle de validation.</span><span class="sxs-lookup"><span data-stu-id="478ce-113">After you select the period frequency, click **Manual schedules**, and set up percentages for each posting interval.</span></span> <span data-ttu-id="478ce-114">Ensemble, les programmes manuels et les intervalles de validation définissent le montant d'amortissement, comme l'illustrent les exemples de cet article.</span><span class="sxs-lookup"><span data-stu-id="478ce-114">Together, the manual schedules and the posting intervals define the depreciation amount, as shown in the examples later in this article.</span></span> <span data-ttu-id="478ce-115">L'amortissement manuel est toujours calculé comme pourcentage du prix d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="478ce-115">Manual depreciation is always calculated as a percentage of the acquisition price.</span></span> <span data-ttu-id="478ce-116">Dans le cas de l'amortissement manuel, les pourcentages que vous spécifiez dans les intervalles de l'amortissement ne doivent pas nécessairement totaliser 100 pour cent.</span><span class="sxs-lookup"><span data-stu-id="478ce-116">For manual depreciation, the percentages that you enter in the intervals of the depreciation don't have to add up to 100 percent.</span></span> <span data-ttu-id="478ce-117">L'amortissement manuel est une méthode d'amortissement flexible qui est souvent utilisée pour définir un profil d'amortissement exceptionnel sur la page **Registres**, tel qu'un amortissement non périodique à des fins particulières (par exemple, de taxe).</span><span class="sxs-lookup"><span data-stu-id="478ce-117">Manual depreciation is a flexible depreciation method that is often used to define an extraordinary depreciation profile on the **Books** page, such as a non-periodic depreciation for special purposes (for example, tax).</span></span>

## <a name="examples"></a><span data-ttu-id="478ce-118">Exemples</span><span class="sxs-lookup"><span data-stu-id="478ce-118">Examples</span></span>
<span data-ttu-id="478ce-119">Prix d'acquisition : 11 000,00 Valeur de mise au rebut prévue : 1 000,00 Le tableau suivant indique les intervalles et les pourcentages que vous paramétrez sur la page **Programmes de profil d'amortissement des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="478ce-119">Acquisition price: 11,000.00 Expected scrap value: 1,000.00 The following table shows the intervals and percentages that you set up on the **Fixed asset depreciation profile schedules** page.</span></span>

| <span data-ttu-id="478ce-120">Nombre d'intervalles</span><span class="sxs-lookup"><span data-stu-id="478ce-120">Interval number</span></span> | <span data-ttu-id="478ce-121">Pourcentage</span><span class="sxs-lookup"><span data-stu-id="478ce-121">Percentage</span></span> |
|-----------------|------------|
| <span data-ttu-id="478ce-122">1</span><span class="sxs-lookup"><span data-stu-id="478ce-122">1</span></span>               | <span data-ttu-id="478ce-123">10,00</span><span class="sxs-lookup"><span data-stu-id="478ce-123">10.00</span></span>      |
| <span data-ttu-id="478ce-124">2</span><span class="sxs-lookup"><span data-stu-id="478ce-124">2</span></span>               | <span data-ttu-id="478ce-125">50,00</span><span class="sxs-lookup"><span data-stu-id="478ce-125">50.00</span></span>      |
| <span data-ttu-id="478ce-126">3</span><span class="sxs-lookup"><span data-stu-id="478ce-126">3</span></span>               | <span data-ttu-id="478ce-127">8,00</span><span class="sxs-lookup"><span data-stu-id="478ce-127">8.00</span></span>       |

<span data-ttu-id="478ce-128">Le tableau suivant illustre la façon dont l'amortissement de chaque intervalle est calculé.</span><span class="sxs-lookup"><span data-stu-id="478ce-128">The following table shows how the depreciation for each interval is calculated.</span></span>

|  <span data-ttu-id="478ce-129">Nombre d'intervalles</span><span class="sxs-lookup"><span data-stu-id="478ce-129">Interval number</span></span> | <span data-ttu-id="478ce-130">Calcul du montant d'amortissement annuel</span><span class="sxs-lookup"><span data-stu-id="478ce-130">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="478ce-131">Valeur nette à la fin de l'intervalle</span><span class="sxs-lookup"><span data-stu-id="478ce-131">Net book value at the end of the interval</span></span> |
|------------------|-----------------------------------------------|-------------------------------------------|
| <span data-ttu-id="478ce-132">1</span><span class="sxs-lookup"><span data-stu-id="478ce-132">1</span></span>                | <span data-ttu-id="478ce-133">(11 000 – 1 000) × 10 % = 1 000</span><span class="sxs-lookup"><span data-stu-id="478ce-133">(11,000 – 1,000) × 10% = 1,000</span></span>                | <span data-ttu-id="478ce-134">10 000 (11 000 – 1 000)</span><span class="sxs-lookup"><span data-stu-id="478ce-134">10,000 (11,000 – 1,000)</span></span>                   |
| <span data-ttu-id="478ce-135">2</span><span class="sxs-lookup"><span data-stu-id="478ce-135">2</span></span>                | <span data-ttu-id="478ce-136">(11 000 – 1 000) × 50 % = 5 000</span><span class="sxs-lookup"><span data-stu-id="478ce-136">(11,000 – 1,000) × 50% = 5,000</span></span>                | <span data-ttu-id="478ce-137">5 000 (10 000 – 5 000)</span><span class="sxs-lookup"><span data-stu-id="478ce-137">5,000 (10,000 – 5,000)</span></span>                    |
| <span data-ttu-id="478ce-138">3</span><span class="sxs-lookup"><span data-stu-id="478ce-138">3</span></span>                | <span data-ttu-id="478ce-139">(11 000 – 1 000) × 8 % = 800</span><span class="sxs-lookup"><span data-stu-id="478ce-139">(11,000 – 1,000) × 8% = 800</span></span>                   | <span data-ttu-id="478ce-140">4 200 (5 000 – 800)</span><span class="sxs-lookup"><span data-stu-id="478ce-140">4,200 (5,000 – 800)</span></span>                       |

<span data-ttu-id="478ce-141">Si vous sélectionnez **Mensuel** dans le champ**Période fréquence**, vous paramétrez 12 intervalles de planification manuels.</span><span class="sxs-lookup"><span data-stu-id="478ce-141">If you select **Monthly** in the **Period frequency** field, you set up 12 manual schedule intervals.</span></span> <span data-ttu-id="478ce-142">Le tableau suivant illustre les montants d'amortissement pour les deux premiers intervalles.</span><span class="sxs-lookup"><span data-stu-id="478ce-142">The following table shows the depreciation amounts for the first two intervals.</span></span>

| <span data-ttu-id="478ce-143">Intervalle</span><span class="sxs-lookup"><span data-stu-id="478ce-143">Interval</span></span> | <span data-ttu-id="478ce-144">Montant d'amortissement</span><span class="sxs-lookup"><span data-stu-id="478ce-144">Depreciation amount</span></span>            |
|----------|--------------------------------|
| <span data-ttu-id="478ce-145">Janvier</span><span class="sxs-lookup"><span data-stu-id="478ce-145">January</span></span>  | <span data-ttu-id="478ce-146">(11 000 – 1 000) × 10 % = 1 000</span><span class="sxs-lookup"><span data-stu-id="478ce-146">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="478ce-147">Février</span><span class="sxs-lookup"><span data-stu-id="478ce-147">February</span></span> | <span data-ttu-id="478ce-148">(11 000 – 1 000) × 50 % = 5 000</span><span class="sxs-lookup"><span data-stu-id="478ce-148">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="478ce-149">Si vous sélectionnez **Semestriel** dans le champ **Période fréquence**, vous paramétrez deux intervalles de planification manuels.</span><span class="sxs-lookup"><span data-stu-id="478ce-149">If you select **Half-Yearly** in the ****Period frequency** field**, you set up two manual schedule intervals.</span></span> <span data-ttu-id="478ce-150">Le tableau suivant illustre les montants d'amortissement pour ces deux intervalles.</span><span class="sxs-lookup"><span data-stu-id="478ce-150">The following table shows the depreciation amounts for those two intervals.</span></span>

| <span data-ttu-id="478ce-151">Intervalle</span><span class="sxs-lookup"><span data-stu-id="478ce-151">Interval</span></span>    | <span data-ttu-id="478ce-152">Montant d'amortissement</span><span class="sxs-lookup"><span data-stu-id="478ce-152">Depreciation amount</span></span>            |
|-------------|--------------------------------|
| <span data-ttu-id="478ce-153">30 juin</span><span class="sxs-lookup"><span data-stu-id="478ce-153">June 30</span></span>     | <span data-ttu-id="478ce-154">(11 000 – 1 000) × 10 % = 1 000</span><span class="sxs-lookup"><span data-stu-id="478ce-154">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="478ce-155">31 décembre</span><span class="sxs-lookup"><span data-stu-id="478ce-155">December 31</span></span> | <span data-ttu-id="478ce-156">(11 000 – 1 000) × 50 % = 5 000</span><span class="sxs-lookup"><span data-stu-id="478ce-156">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="478ce-157">Le total des pourcentages de tous les intervalles ne doit pas être 100.</span><span class="sxs-lookup"><span data-stu-id="478ce-157">The total of percentages for all intervals doesn't have to be 100.</span></span> <span data-ttu-id="478ce-158">Toutefois, vous recevez un message si la valeur du champ **Pourcentage cumulé** de la page **Programmes de profil d'amortissement des immobilisations** n'est pas **100**.</span><span class="sxs-lookup"><span data-stu-id="478ce-158">However, you receive a message if the value in the **Cumulative percentage** field on the **Fixed asset depreciation profile schedules** page isn't **100**.</span></span>




