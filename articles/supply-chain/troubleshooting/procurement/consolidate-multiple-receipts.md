---
title: Impossible de regrouper plusieurs accusés de réception de marchandises en une seule commande fournisseur
description: Vous ne pouvez pas consolider plusieurs accusés de réception de marchandises en une seule commande fournisseur si les différentes lignes d’accusé de réception de marchandises ont des dates comptables différentes.
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
ms.openlocfilehash: 485306279281ceb55a140526f4216af35574af42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476305"
---
# <a name="you-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>Impossible de regrouper plusieurs accusés de réception de marchandises en une seule commande fournisseur

## <a name="symptoms"></a>Symptômes

Vous ne pouvez pas consolider plusieurs accusés de réception de marchandises en une seule commande fournisseur si les différentes lignes d’accusé de réception de marchandises ont des dates comptables différentes.

## <a name="resolution"></a>Résolution

Dans les versions antérieures de Dynamics 365 Supply Chain Management, le regroupement était autorisé dans cette situation. Cependant, la pratique pouvait causer des erreurs. La date comptable sur les lignes de commande fournisseur qui sont créées ne doit pas différer de la date comptable sur les lignes d’accusé de réception de marchandises à partir desquelles ces lignes de commande fournisseur ont été créées. (La date comptable sur les lignes de commande fournisseur correspond à la date comptable sur l’en-tête de commande fournisseur.) Par conséquent, le regroupement de plusieurs accusés de réception de marchandises en une seule commande fournisseur n’est plus autorisée.

La date comptable est utilisée, par exemple, pour les réservations budgétaires et les engagements. Par conséquent, elle doit être conservée pendant la transition de l’accusé de réception de marchandises à la commande fournisseur.
