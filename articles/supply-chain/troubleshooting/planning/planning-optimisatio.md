---
title: La commande d'achat planifiée est créée lorsqu'un achat existe dans les jours négatifs
description: Si le code de couverture est Min/Max, l'optimisation de la planification crée une commande d'achat planifiée lorsqu'un achat existe dans les jours négatifs.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026513"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a><span data-ttu-id="cfdd3-103">La commande d'achat planifiée est créée lorsqu'un achat existe dans les jours négatifs</span><span class="sxs-lookup"><span data-stu-id="cfdd3-103">Planned purchase order is created when a purchase exists within negative days</span></span>

<span data-ttu-id="cfdd3-104">Numéro de la base de connaissances : 4614298</span><span class="sxs-lookup"><span data-stu-id="cfdd3-104">KB number: 4614298</span></span>

## <a name="symptoms"></a><span data-ttu-id="cfdd3-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="cfdd3-105">Symptoms</span></span>

<span data-ttu-id="cfdd3-106">Si le code de couverture est *Min/max*, l'optimisation de la planification crée une commande d'achat planifiée lorsqu'un achat existe dans les jours négatifs.</span><span class="sxs-lookup"><span data-stu-id="cfdd3-106">If the coverage code is *Min/max*, Planning Optimization creates a planned purchase order when a purchase exists within negative days.</span></span>

## <a name="resolution"></a><span data-ttu-id="cfdd3-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="cfdd3-107">Resolution</span></span>

<span data-ttu-id="cfdd3-108">L'optimisation de la planification ne prend pas en charge les jours négatifs.</span><span class="sxs-lookup"><span data-stu-id="cfdd3-108">Planning Optimization doesn't support negative days.</span></span> <span data-ttu-id="cfdd3-109">Cependant, cela garantit toujours que les commandes planifiées ne seront pas planifiées dans le délai par rapport à la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="cfdd3-109">However, it always ensures that planned orders won't be scheduled within the lead time relative to the current date.</span></span> <span data-ttu-id="cfdd3-110">Par exemple, le délai d'achat est de 10 jours et un bon de commande devrait arriver dans huit jours à compter d'aujourd'hui.</span><span class="sxs-lookup"><span data-stu-id="cfdd3-110">For example, the purchase lead time is 10 days, and a purchase order is expected to arrive eight days from today.</span></span> <span data-ttu-id="cfdd3-111">Dans ce cas, le bon de commande sera utilisé comme offre pour la demande dans cinq jours à compter d'aujourd'hui.</span><span class="sxs-lookup"><span data-stu-id="cfdd3-111">In this case, the purchase order will be used as supply for demand that is five days from today.</span></span>

<span data-ttu-id="cfdd3-112">Par conséquent, nous vous recommandons d'ajuster vos délais pour couvrir tous (ou presque tous) vos scénarios.</span><span class="sxs-lookup"><span data-stu-id="cfdd3-112">Therefore, we recommend that you adjust your lead times to cover all (or almost all) of your scenarios.</span></span>
