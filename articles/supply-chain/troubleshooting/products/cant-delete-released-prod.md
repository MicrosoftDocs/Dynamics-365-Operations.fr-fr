---
title: Vous ne pouvez pas supprimer un produit lancé
description: Vous pouvez supprimer un produit lancé et toutes ses variantes uniquement si le produit lancé ne comporte aucune transaction associée.
author: SmithaNataraj
ms.date: 06/11/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f03d45a36401314a4b02ff354fabb474568c48b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476368"
---
# <a name="you-cant-delete-a-released-product"></a>Vous ne pouvez pas supprimer un produit lancé

## <a name="symptoms"></a>Symptômes

Vous pouvez supprimer un produit lancé et toutes ses variantes uniquement si le produit lancé ne comporte aucune transaction associée.

## <a name="resolution"></a>Résolution

Suivez ces étapes pour supprimer un produit lancé ou un produit générique.

1. Fermez toutes les transactions ouvertes pour les articles.
1. Réduisez le stock à 0 (zéro).
1. Effectuer la clôture des stocks.
1. Supprimez toutes les variantes de produit pour le produit générique que vous souhaitez supprimer.
