---
title: Le statut de la commande demeure Lancé partiellement après sa facturation
description: Dans certains cas, le statut d’une commande client reste Lancé partiellement même après la facturation de la commande. Cette page explique pourquoi et donne une solution de contournement possible.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8bfe7ecfd4beb6e77e8dd1e23ccd896d067bdb51
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476346"
---
# <a name="order-status-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>Le statut d’une commande reste Lancé partiellement même après la facturation de la commande client

## <a name="symptoms"></a>Symptômes

Une commande client est un bon de livraison, mais un ou plusieurs articles y figurant ont un mode de livraison différent. Une fois la commande facturée, elle a toujours un statut de validation de *Lancé partiellement*.

Par exemple, une commande client comporte deux articles : un pour la livraison et un pour le retrait. La livraison et le retrait ont été effectués. Par conséquent, les deux lignes ont été facturées. Cependant, le statut du lancement est toujours affiché comme *Lancé partiellement*, ce qui est trompeur.

## <a name="workaround"></a>Solution de contournement

Le statut de lancement s’applique uniquement aux lignes de commande où les articles sont activés pour la gestion de l’entrepôt. Par conséquent, le statut du lancement *Lancé partiellement* dans ce scénario. Microsoft a évalué ce problème et a déterminé qu’il s’agissait d’une limitation de fonctionnalité. Une extension peut être ajoutée dans le cadre du bon de livraison et du processus de facturation pour mettre à jour le statut du lancement.
