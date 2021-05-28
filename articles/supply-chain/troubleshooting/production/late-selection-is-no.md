---
title: La sélection tardive n'est pas respectée lorsque les ordres de fabrication sont réinitialisés via un travail par lots
description: Lorsque vous utilisez un travail par lots récurrent pour réinitialiser le statut d'un ordre de fabrication, les sélections tardives ne sont pas respectées.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e53198f427f4060421a4f0078277682c43db1320
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026501"
---
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a><span data-ttu-id="93d95-103">La sélection tardive n'est pas respectée lorsque les ordres de fabrication sont réinitialisés via un travail par lots</span><span class="sxs-lookup"><span data-stu-id="93d95-103">Late selection isn't respected when production orders are reset via a batch job</span></span>

<span data-ttu-id="93d95-104">Numéro de la base de connaissances : 4614634</span><span class="sxs-lookup"><span data-stu-id="93d95-104">KB number: 4614634</span></span>

## <a name="symptoms"></a><span data-ttu-id="93d95-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="93d95-105">Symptoms</span></span>

<span data-ttu-id="93d95-106">Lorsque vous utilisez un travail par lots récurrent pour réinitialiser le statut d'un ordre de fabrication, les sélections tardives ne sont pas respectées.</span><span class="sxs-lookup"><span data-stu-id="93d95-106">When you use a recurring batch job to reset the status of a production order, late selections aren't respected.</span></span>

## <a name="resolution"></a><span data-ttu-id="93d95-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="93d95-107">Resolution</span></span>

<span data-ttu-id="93d95-108">La conception actuelle ne prend pas en charge l'utilisation de sélections tardives pour le processus *Statut de réinitialisation*.</span><span class="sxs-lookup"><span data-stu-id="93d95-108">The current design doesn't support the use of late selections for the *Reset status* process.</span></span>
