---
title: L'annulation du reste de la livraison fait passer la commande fournisseur à l'état Confirmé
description: Si un solde de livraison est annulé sur une commande fournisseur où la gestion des modifications est activée, la commande fournisseur passe à l’état Confirmé
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 1d8b331bc5699487dff3491d65daa36293f3212f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476348"
---
# <a name="cancelling-delivery-remainder-moves-purchase-order-to-a-confirmed-state"></a>L'annulation du reste de la livraison fait passer la commande fournisseur à l'état Confirmé

## <a name="symptoms"></a>Symptômes

Pour une commande fournisseur faisant l’objet d’une gestion des modifications, si la seule modification demandée est l’annulation d’un solde de livraison sur une ou plusieurs des lignes, la commande fournisseur passera directement à l’état *Confirmé* quand elle sera approuvée, et aucun journal ne sera créé.

## <a name="resolution"></a>Résolution

L’annulation d’un solde de livraison n’affecte pas le contenu du journal de confirmation. Cette fonctionnalité doit être utilisée lorsque la ligne a été partiellement reçue, et la qualité du solde doit être annulée à l’étape du processus après que la commande fournisseur a été confirmée avec le fournisseur.

Si cela doit être reflété sur la confirmation de la commande fournisseur, la quantité doit être ajustée sur la ligne de commande afin que la confirmation soit requise. Sinon, si rien n’a été reçu sur la ligne, la quantité peut être supprimée. Dans ce cas, une reconfirmation sera nécessaire.
