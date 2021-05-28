---
title: Le cumul des remises client échoue lorsque des groupes de remises d'articles sont utilisés
description: Lorsque vous utilisez des accords de remise client en combinaison avec des groupes de remise d'article, les remises sont calculées, mais le cumul échoue.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5222d5a52a34ecfa4a1eac96a2cb561f257f17ea
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026497"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a><span data-ttu-id="5135c-103">Le cumul des remises client échoue lorsque des groupes de remises d'articles sont utilisés</span><span class="sxs-lookup"><span data-stu-id="5135c-103">Cumulation of customer rebates fails when item rebate groups are used</span></span>

<span data-ttu-id="5135c-104">Numéro de la base de connaissances : 4611372</span><span class="sxs-lookup"><span data-stu-id="5135c-104">KB number: 4611372</span></span>

## <a name="symptoms"></a><span data-ttu-id="5135c-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="5135c-105">Symptoms</span></span>

<span data-ttu-id="5135c-106">Lorsque vous utilisez des accords de remise client en combinaison (du type *montant*) avec des groupes de remise d'article, les remises sont calculées, mais le cumul échoue.</span><span class="sxs-lookup"><span data-stu-id="5135c-106">When you use customer rebate agreements (of the *amount* type) in combination with item rebate groups, rebates are calculated, but cumulation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="5135c-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="5135c-107">Resolution</span></span>

<span data-ttu-id="5135c-108">Le système se comporte comme prévu.</span><span class="sxs-lookup"><span data-stu-id="5135c-108">The system is behaving as designed.</span></span> <span data-ttu-id="5135c-109">Les groupes d'articles regroupent uniquement les articles qui ont la même condition de seuil.</span><span class="sxs-lookup"><span data-stu-id="5135c-109">Item groups group only items that have the same threshold condition.</span></span> <span data-ttu-id="5135c-110">La condition de remise (seuil) est définie par rapport au montant de chaque article, et non par rapport au montant cumulé pour tout article du groupe d'articles.</span><span class="sxs-lookup"><span data-stu-id="5135c-110">The rebate condition (threshold) is set against the amount for each item, not against the cumulated amount for any item in the item group.</span></span>
