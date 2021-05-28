---
title: Le rapport Coûts indirects en cours comprend les ordres de fabrication supprimés
description: Le rapport Coûts indirects en cours présente des informations sur les ordres de fabrication qui ont été partiellement traités puis supprimés.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 707fa9bb30129c3656e10c6756dee770a7712e65
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026508"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a><span data-ttu-id="e8f48-103">Le rapport Coûts indirects en cours comprend les ordres de fabrication supprimés</span><span class="sxs-lookup"><span data-stu-id="e8f48-103">The Indirect costs in process report includes deleted production orders</span></span>

<span data-ttu-id="e8f48-104">Numéro de la base de connaissances : 4612748</span><span class="sxs-lookup"><span data-stu-id="e8f48-104">KB number: 4612748</span></span>

## <a name="symptoms"></a><span data-ttu-id="e8f48-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="e8f48-105">Symptoms</span></span>

<span data-ttu-id="e8f48-106">Le rapport **Coûts indirects en cours** présente des informations sur les ordres de fabrication qui ont été partiellement traités puis supprimés.</span><span class="sxs-lookup"><span data-stu-id="e8f48-106">The **Indirect costs in process** report presents information about production orders that were partially processed and later deleted.</span></span>

## <a name="resolution"></a><span data-ttu-id="e8f48-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="e8f48-107">Resolution</span></span>

<span data-ttu-id="e8f48-108">Lorsque vous annulez un ordre de fabrication, vous annulez également toutes les transactions de cet ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="e8f48-108">When you reverse a production order, you also reverse all the transactions of that production order.</span></span> <span data-ttu-id="e8f48-109">Lorsque vous supprimez l'ordre de fabrication, les tables de livres auxiliaires et le compte général conservent toutes les transactions qui y sont liées.</span><span class="sxs-lookup"><span data-stu-id="e8f48-109">When you delete the production order, the subledger tables and general ledger persist all transactions that are related to it.</span></span> <span data-ttu-id="e8f48-110">Les rapports afficheront les transactions dans les tables de livres auxiliaires.</span><span class="sxs-lookup"><span data-stu-id="e8f48-110">The reports will show the transactions in the subledger tables.</span></span> <span data-ttu-id="e8f48-111">Pour l'ordre de fabrication spécifique, la valeur nette doit être de 0,00.</span><span class="sxs-lookup"><span data-stu-id="e8f48-111">For the specific production order, the net value should be 0.00.</span></span>
