---
title: Réduire l’amortissement après un fractionnement
description: Cette rubrique décrit la méthode utilisée dans Immobilisations pour calculer l’amortissement après le fractionnement d’une immobilisation à l’aide de la méthode de réduction du solde.
author: moaamer
manager: Ann Beebe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f276f49e5b1bc2814dc851f1ad4204a151d86c43
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222381"
---
# <a name="reduce-balance-depreciation-after-a-split"></a><span data-ttu-id="b828d-103">Réduire l’amortissement après un fractionnement</span><span class="sxs-lookup"><span data-stu-id="b828d-103">Reduce balance depreciation after a split</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b828d-104">Cette rubrique décrit la méthode utilisée dans Immobilisations pour calculer l’amortissement après le fractionnement d’un actif en un autre à l’aide de la méthode de réduction du solde.</span><span class="sxs-lookup"><span data-stu-id="b828d-104">This topic describes the method that is used in Fixed assets to calculate depreciation after an asset is split to another asset by using the reduce balance method.</span></span> <span data-ttu-id="b828d-105">L’année d’amortissement configurée dans le registre d’immobilisations est l’exercice comptable.</span><span class="sxs-lookup"><span data-stu-id="b828d-105">The depreciation year that is configured in the asset book is the fiscal year.</span></span> <span data-ttu-id="b828d-106">Pour plus d’informations, consultez [Réduire l’amortissement du solde](reduce-balance-depreciation.md) et [Fractionner une immobilisation](tasks/split-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="b828d-106">For more information, see [Reduce balance depreciation](reduce-balance-depreciation.md) and [Split a fixed asset](tasks/split-fixed-asset.md).</span></span>

<span data-ttu-id="b828d-107">Si vous scindez une immobilisation au cours d’une période fiscale postérieure à la période d’acquisition de l’immobilisation, l’amortissement réduit du solde tiendra compte de la valeur nette (VN) de l’actif pour l’année précédente.</span><span class="sxs-lookup"><span data-stu-id="b828d-107">If you split a fixed asset during a fiscal period that is later than the period when the asset was acquired, the reduced balance depreciation will account for the asset's net book value (NBV) for the previous year.</span></span> <span data-ttu-id="b828d-108">Il tiendra également compte des transactions d’acquisition et de correction d’amortissement générées à partir de la transaction qui a fractionné l’actif.</span><span class="sxs-lookup"><span data-stu-id="b828d-108">It will also account for the acquisition and depreciation adjustment transactions that were generated from the transaction that split the asset.</span></span> <span data-ttu-id="b828d-109">Ce comportement suppose que l’actif a été acquis au cours d’un exercice et fractionné au cours d’un exercice ultérieur.</span><span class="sxs-lookup"><span data-stu-id="b828d-109">This behavior assumes that the asset was acquired in one fiscal year and split in a later fiscal year.</span></span> <span data-ttu-id="b828d-110">Le montant qui doit être amorti pour l’actif d’origine après le fractionnement reflète la VN de l’actif avant le fractionnement de l’actif et la transaction d’acquisition et d’ajustement de l’amortissement qui a été comptabilisée pour le fractionnement.</span><span class="sxs-lookup"><span data-stu-id="b828d-110">The amount that must be depreciated for the original asset after the split reflects the asset's NBV before the asset was split, and the acquisition and depreciation adjustment transaction that was posted for the split.</span></span>

<span data-ttu-id="b828d-111">Par exemple, les conditions suivantes sont en vigueur :</span><span class="sxs-lookup"><span data-stu-id="b828d-111">For example, the following conditions are in effect:</span></span>

- <span data-ttu-id="b828d-112">L’exercice financier va du 30 juin au 1er juillet.</span><span class="sxs-lookup"><span data-stu-id="b828d-112">The fiscal period is from June 30 to July 1.</span></span>
- <span data-ttu-id="b828d-113">Le pourcentage de solde réducteur est de 18 % et un actif est acquis en juin 2019 à un prix d’acquisition de 10 000 $.</span><span class="sxs-lookup"><span data-stu-id="b828d-113">The reducing balance percentage is 18 percent, and an asset is acquired in June 2019 at an acquisition price of $10,000.</span></span>
- <span data-ttu-id="b828d-114">L’amortissement du premier exercice est égal à 18 000 $, l’amortissement mensuel est égal à 150 $, et l’actif est ensuite amorti jusqu’en novembre 2019, à hauteur de 738,75 $.</span><span class="sxs-lookup"><span data-stu-id="b828d-114">The depreciation of the first fiscal year equals $18,000, the monthly depreciation equals $150, and the asset is then depreciated until November 2019, in the amount of $738.75.</span></span>
- <span data-ttu-id="b828d-115">En novembre 2019, 80 % de l’actif est divisé en une autre immobilisation.</span><span class="sxs-lookup"><span data-stu-id="b828d-115">In November 2019, 80 percent of the asset is split to another fixed asset.</span></span>

<span data-ttu-id="b828d-116">[![Réduire l’amortissement après un fractionnement](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span><span class="sxs-lookup"><span data-stu-id="b828d-116">[![Reduce balance depreciation after a split](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span></span>

<span data-ttu-id="b828d-117">Le montant à amortir pour l’actif d’origine est 1 822,25 $.</span><span class="sxs-lookup"><span data-stu-id="b828d-117">The amount to depreciate for the original asset is $1,822.25.</span></span> <span data-ttu-id="b828d-118">Ce montant correspond à la VN avant la validation de la transaction de fractionnement (9 111,25 USD), plus l’ajustement d’acquisition généré lors de la validation de la transaction de fractionnement (-8 000 USD), plus l’ajustement de dépréciation généré lors de la transaction de fractionnement (711 USD).</span><span class="sxs-lookup"><span data-stu-id="b828d-118">This amount equals the NBV before the split transaction is posted ($9,111.25), plus the acquisition adjustment that is generated during posting of the split transaction (-$8,000), plus the depreciation adjustment that is generated during the split transaction ($711).</span></span> <span data-ttu-id="b828d-119">Par conséquent, la dépréciation pour la deuxième année est (1 822,25 × 18 pour cent) ÷ 12 = 27,33 $.</span><span class="sxs-lookup"><span data-stu-id="b828d-119">Therefore, the depreciation for the second year is (1,822.25 × 18 percent) ÷ 12 = $27.33.</span></span>

<span data-ttu-id="b828d-120">Le montant à amortir pour la nouvelle immobilisation la première année est (8 000 × 18 pour cent) ÷ 12 = 120 $.</span><span class="sxs-lookup"><span data-stu-id="b828d-120">The amount to depreciate for the new fixed asset in the first year is (8,000 × 18 percent) ÷ 12 = $120.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]