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
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a>La commande d'achat planifiée est créée lorsqu'un achat existe dans les jours négatifs

Numéro de la base de connaissances : 4614298

## <a name="symptoms"></a>Symptômes

Si le code de couverture est *Min/max*, l'optimisation de la planification crée une commande d'achat planifiée lorsqu'un achat existe dans les jours négatifs.

## <a name="resolution"></a>Résolution

L'optimisation de la planification ne prend pas en charge les jours négatifs. Cependant, cela garantit toujours que les commandes planifiées ne seront pas planifiées dans le délai par rapport à la date actuelle. Par exemple, le délai d'achat est de 10 jours et un bon de commande devrait arriver dans huit jours à compter d'aujourd'hui. Dans ce cas, le bon de commande sera utilisé comme offre pour la demande dans cinq jours à compter d'aujourd'hui.

Par conséquent, nous vous recommandons d'ajuster vos délais pour couvrir tous (ou presque tous) vos scénarios.
