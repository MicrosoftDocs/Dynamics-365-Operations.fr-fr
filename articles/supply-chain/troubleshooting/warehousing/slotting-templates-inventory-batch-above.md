---
title: Inventaire disponible non pris en compte pour les articles « batch-above » (lot au-dessus)
description: Certains modèles de positionnement ne tiennent pas compte de l’inventaire disponible actuel pour les articles « batch-above » (lot au-dessus). Le numéro de lot ou de série doit être spécifié sur la commande à la demande.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: df5642b32f5e053144230eab3dbcf633f526279a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476336"
---
# <a name="slotting-templates-dont-consider-on-hand-inventory-for-batch-above-items"></a>Les modèles de positionnement ne tiennent pas compte de l’inventaire disponible actuel pour les articles « batch-above » (lot au-dessus)

## <a name="symptoms"></a>Symptômes

Les modèles de positionnement qui ont le critère d’emplacement *Considérer comme disponible* ne prennent pas en compte le stock disponible actuel pour les articles *batch-above*. Ils ne le prennent en compte que si le numéro de lot est indiqué sur la ligne de commande client.

Cependant, lorsque vous utilisez des articles *batch-below*, l’inventaire disponible actuel est considéré comme attendu.

Pour plus d’informations, voir [Créneaux de l’entrepôt](/dynamics365/supply-chain/warehousing/warehouse-slotting).

## <a name="resolution"></a>Résolution

L’en-tête du modèle de positionnement peut être défini pour les stratégies de demande *Commandé*, *Réservé*, ou *Libéré*. Pour la stratégie de demande *Commandé*, les mêmes exigences de hiérarchie de réservation s’appliquent que celles qui s’appliquent aux processus de réservation ou de lancement vers l’entrepôt. Par conséquent, pour les articles qui ont des hiérarchies de réservation *batch-above* et *serial-below*, le numéro de lot ou de série doit être indiqué sur l’ordre de demande (vente ou transfert).

Alternativement, la stratégie de demande *Réservé* peut être utilisée pour sélectionner le numéro de lot ou de série avant que la demande de positionnement d’entrepôt ne soit générée.
