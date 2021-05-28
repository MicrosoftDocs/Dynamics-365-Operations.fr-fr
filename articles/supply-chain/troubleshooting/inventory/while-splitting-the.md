---
title: Lorsqu'une quantité de poids de capture est fractionnée, la quantité minimale est utilisée au lieu de la quantité nominale
description: Lorsqu'une quantité de poids variable est divisée en lots, le champ Choisir la quantité utilise la quantité minimale définie pour l'article, et non la quantité nominale.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 185365ced5c4516d8fcdbdca88794d0078615888
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026516"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a><span data-ttu-id="f56d8-103">Lorsqu'une quantité de poids de capture est fractionnée, la quantité minimale est utilisée au lieu de la quantité nominale</span><span class="sxs-lookup"><span data-stu-id="f56d8-103">When a catch-weight quantity is split, minimum quantity is used instead of nominal quantity</span></span>

<span data-ttu-id="f56d8-104">Numéro de la base de connaissances : 4612073</span><span class="sxs-lookup"><span data-stu-id="f56d8-104">KB number: 4612073</span></span>

## <a name="symptoms"></a><span data-ttu-id="f56d8-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="f56d8-105">Symptoms</span></span>

<span data-ttu-id="f56d8-106">Lorsqu'une quantité de poids variable est divisée en lots, le champ **Choisir la quantité** utilise la quantité minimale définie pour l'article, et non la quantité nominale.</span><span class="sxs-lookup"><span data-stu-id="f56d8-106">When a catch-weight quantity is being split into batches, the **Pick qty** field uses the minimum quantity that is set for the item, not the nominal quantity.</span></span>

## <a name="resolution"></a><span data-ttu-id="f56d8-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="f56d8-107">Resolution</span></span>

<span data-ttu-id="f56d8-108">Le système se comporte comme prévu.</span><span class="sxs-lookup"><span data-stu-id="f56d8-108">The system is behaving as designed.</span></span> <span data-ttu-id="f56d8-109">Le système utilise la configuration de quantité minimale de chaque article pour le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="f56d8-109">The system uses each item's minimum quantity setup for picking.</span></span>
