---
title: Réduire l’amortissement après un fractionnement
description: Cet article décrit la méthode utilisée dans Immobilisations pour calculer l’amortissement après le fractionnement d’une immobilisation à l’aide de la méthode de réduction du solde.
author: moaamer
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 539967a9a73da91f6b49c1bb89f404267ae0a804
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883298"
---
# <a name="reduce-balance-depreciation-after-a-split"></a>Réduire l’amortissement après un fractionnement

[!include [banner](../includes/banner.md)]

Cet article décrit la méthode utilisée dans Immobilisations pour calculer l’amortissement après le fractionnement d’un actif en un autre à l’aide de la méthode de réduction du solde. L’année d’amortissement configurée dans le registre d’immobilisations est l’exercice comptable. Pour plus d’informations, consultez [Réduire l’amortissement du solde](reduce-balance-depreciation.md) et [Fractionner une immobilisation](tasks/split-fixed-asset.md).

Si vous scindez une immobilisation au cours d’une période fiscale postérieure à la période d’acquisition de l’immobilisation, l’amortissement réduit du solde tiendra compte de la valeur nette (VN) de l’actif pour l’année précédente. Il tiendra également compte des transactions d’acquisition et de correction d’amortissement générées à partir de la transaction qui a fractionné l’actif. Ce comportement suppose que l’actif a été acquis au cours d’un exercice et fractionné au cours d’un exercice ultérieur. Le montant qui doit être amorti pour l’actif d’origine après le fractionnement reflète la VN de l’actif avant le fractionnement de l’actif et la transaction d’acquisition et d’ajustement de l’amortissement qui a été comptabilisée pour le fractionnement.

Par exemple, les conditions suivantes sont en vigueur :

- L’exercice financier va du 30 juin au 1er juillet.
- Le pourcentage de solde réducteur est de 18 % et un actif est acquis en juin 2019 à un prix d’acquisition de 10 000 $.
- L’amortissement du premier exercice est égal à 18 000 $, l’amortissement mensuel est égal à 150 $, et l’actif est ensuite amorti jusqu’en novembre 2019, à hauteur de 738,75 $.
- En novembre 2019, 80 % de l’actif est divisé en une autre immobilisation.

[![Réduire l’amortissement après un fractionnement.](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)

Le montant à amortir pour l’actif d’origine est 1 822,25 $. Ce montant correspond à la VN avant la validation de la transaction de fractionnement (9 111,25 USD), plus l’ajustement d’acquisition généré lors de la validation de la transaction de fractionnement (-8 000 USD), plus l’ajustement de dépréciation généré lors de la transaction de fractionnement (711 USD). Par conséquent, la dépréciation pour la deuxième année est (1 822,25 × 18 pour cent) ÷ 12 = 27,33 $.

Le montant à amortir pour la nouvelle immobilisation la première année est (8 000 × 18 pour cent) ÷ 12 = 120 $.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
