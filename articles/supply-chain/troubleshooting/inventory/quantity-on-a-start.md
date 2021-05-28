---
title: La quantité d'une commande de quarantaine lancée n'est pas mise à jour lorsque la commande est fractionnée
description: Lorsque vous créez une commande de quarantaine et que vous essayez de la fractionner, la quantité de commande n'est pas mise à jour avec la quantité restante fractionnée.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a8af535257ce217629d5ba92e624623c3ea39345
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026520"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a><span data-ttu-id="d4b67-103">La quantité d'une commande de quarantaine lancée n'est pas mise à jour lorsque la commande est fractionnée</span><span class="sxs-lookup"><span data-stu-id="d4b67-103">Quantity on a started quarantine order isn't updated when the order is split</span></span>

<span data-ttu-id="d4b67-104">Numéro de la base de connaissances : 4613113</span><span class="sxs-lookup"><span data-stu-id="d4b67-104">KB number: 4613113</span></span>

## <a name="symptoms"></a><span data-ttu-id="d4b67-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="d4b67-105">Symptoms</span></span>

<span data-ttu-id="d4b67-106">Lorsque vous créez une commande de quarantaine et que vous essayez de la fractionner, la quantité de commande n'est pas mise à jour avec la quantité restante après le fractionnement.</span><span class="sxs-lookup"><span data-stu-id="d4b67-106">When you create a quarantine order and try to split it, the order quantity isn't updated to the remaining quantity after the split.</span></span>

## <a name="resolution"></a><span data-ttu-id="d4b67-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="d4b67-107">Resolution</span></span>

<span data-ttu-id="d4b67-108">Le système ne modifie pas la quantité d'origine d'une commande de quarantaine pour garantir que vous pouvez suivre la quantité d'origine qui a été créée pour cette commande de quarantaine.</span><span class="sxs-lookup"><span data-stu-id="d4b67-108">The system doesn't change the original quantity from a quarantine order to ensure that you can track the original quantity that was created for that quarantine order.</span></span> <span data-ttu-id="d4b67-109">Cependant, le système effectue le suivi de la quantité fractionnée à partir d'une commande de quarantaine.</span><span class="sxs-lookup"><span data-stu-id="d4b67-109">However, the system does track the quantity that is split from a quarantine order.</span></span> <span data-ttu-id="d4b67-110">Pour effectuer ce suivi, il utilise un champ de base de données nommé `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span><span class="sxs-lookup"><span data-stu-id="d4b67-110">To do this tracking, it uses a database field that is named `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span></span> <span data-ttu-id="d4b67-111">Cependant, ce champ n'est pas visible dans l'interface utilisateur (UI).</span><span class="sxs-lookup"><span data-stu-id="d4b67-111">However, this field isn't visible in the user interface (UI).</span></span>
