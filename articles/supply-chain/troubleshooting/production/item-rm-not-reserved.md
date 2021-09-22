---
title: L'article RM ne peut pas être réservé lorsque l'ordre de fabrication est lancé
description: "Lors du lancement d'un ordre de fabrication, vous pouvez obtenir l'erreur : « L'article RM n'a pas pu être entièrement réservé. » Assurez-vous que la quantité totale est disponible ou réservez les articles manuellement."
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 528895252d661bb012f49190c15853989833064d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476363"
---
# <a name="item-rm-cant-be-fully-reserved-when-a-production-order-is-released"></a>L'article RM ne peut pas être entièrement réservé lorsqu'un ordre de fabrication est lancé

## <a name="symptoms"></a>Symptômes

Si tous les articles de ligne de nomenclature ne sont pas physiquement disponibles lorsqu’un ordre de fabrication est lancé vers un entrepôt, et que la stratégie **Lancement vers l'entrepôt** est définie sur *Exiger une réservation complète*, vous recevrez le message d’erreur suivant :

> L’article RM n’a pas pu être entièrement réservé. Assurez-vous que la quantité totale est disponible ou réservez les articles manuellement si le champ Réservation de la ligne de nomenclature est défini sur Manuel ou Démarré. Impossible de libérer la commande dans l'entrepôt, car certaines matières premières n'ont pas pu être réservées.

## <a name="resolution"></a>Résolution

Ce comportement est fait exprès et fonctionne comme prévu. Pour résoudre ce problème, suivez les instructions fournies dans le message d'erreur : « Assurez-vous que la quantité totale est disponible ou réservez les articles manuellement si le champ Réservation sur la ligne de nomenclature est défini sur Manuel ou Démarré. »
