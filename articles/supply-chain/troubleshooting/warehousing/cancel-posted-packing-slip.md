---
title: Impossible d'annuler un bon de livraison après qu'il a été validé à partir d’une commande
description: Lorsque les processus de prélèvement et d’expédition sont activés pour WMS, vous ne pouvez pas annuler un bon de livraison après l’avoir validé à partir d’une commande client. Cette page propose une solution de contournement.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d20e66e2721560b8409eb63c3546a79adc188c7c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476389"
---
# <a name="cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>Impossible d'annuler un bon de livraison après qu'il a été validé à partir d’une commande client

## <a name="symptoms"></a>Symptômes

Lorsque les processus de prélèvement et d’expédition sont activés pour la gestion avancée des entrepôts (WMS), vous ne pouvez pas annuler un bon de livraison après l’avoir validé à partir d’une commande client.

## <a name="resolution"></a>Résolution

Pour corriger les bons de livraison validés pour les articles qui sont activés pour WMS, l’enregistrement doit se faire à partir du chargement et non de la commande. Microsoft a évalué ce problème et a déterminé qu’il s’agissait d’une limitation de fonctionnalité.  

En général, une commande client qui a été prélevée et expédiée via des processus de gestion d’entrepôt peut être mise à jour selon le bon de livraison à partir du chargement ou de l’expédition et du document de commande client lui-même. Cependant, si vous mettez à jour la commande client selon le bon de livraison à partir du document de commande client, l’annulation du bon de livraison ne peut toujours pas être effectuée à partir du chargement ou de la commande client. Par conséquent, nous vous recommandons d’utiliser l’enregistrement du bon de livraison à partir du chargement. Dans ce cas, l’inversion qui doit être effectuée à partir de la charge sera activée.
