---
title: "Préparation de la mise à jour des coûts standard pour les articles fabriqués"
description: "Cette rubrique décrit les étapes de préparation de la mise à jour des coûts pour les articles fabriqués."
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 605f4c6391e9c40b1b80fab93d61b88553369069
ms.openlocfilehash: 6f52d2d90d655d1ab465e1808ca55ef3d5ea9e56
ms.contentlocale: fr-fr
ms.lasthandoff: 01/19/2018

---


# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a>Préparation de la mise à jour des coûts standard pour les articles fabriqués

Cette rubrique décrit les étapes de préparation de la mise à jour des coûts pour les articles fabriqués. Les étapes pour les articles fabriqués diffèrent légèrement des étapes pour les articles achetés.

Les stratégies appliquées aux articles fabriqués peuvent affecter les calculs de coûts pour les articles fabriqués parents. Pour préparer la mise à jour des coûts pour les articles fabriqués, procédez comme suit :

1. Affectez un groupe de modèles d'article à l'article fabriqué. 

   Le groupe de modèles d'article identifie que les coûts standard sont utilisés.

2. Affectez un groupe d'articles à l'objet fabriqué. 

   Le groupe d'articles contient des comptes généraux qui s'appliquent à l'article fabriqué. Les comptes généraux pour un article fabriqué avec un modèle de stock de coût standard comprennent plusieurs écarts de production, l'écart de modification des coûts et la réévaluation des coûts de stock.

3. Affectez l'unité de mesure de stock à l'article. 

   Les coûts de l'article sont toujours exprimés dans l'unité de mesure de stock de l'article.

4. N'affectez pas un groupe de coûts à l'article fabriqué, à moins qu'il ne soit traité comme un article acheté.

5. Affectez un groupe de calcul de nomenclature à l'article fabriqué. 

   Le groupe de calcul de nomenclature de l'article définit les conditions d'avertissement applicables. Ainsi, lorsqu'un calcul de nomenclature est effectué, des messages d'avertissement peuvent être générés concernant les sources possibles des erreurs de calcul. Par exemple, un message d'avertissement peut identifier si une nomenclature ou une gamme active n'existe pas. Le groupe de calcul de nomenclature contient une stratégie d'arrêt d'éclatement qui indique quand un article fabriqué doit être traité comme un article acheté.

6. Si l'article fabriqué a des coûts constants, affectez-lui une quantité de commande standard. 

   La quantité de commande standard fait office de taille de lot comptable pour l'amortissement des coûts constants. Les coûts standard sont, par exemple, les temps de réglage des opérations de gamme et une quantité de composant constante dans la nomenclature.

7. Définissez la nomenclature pour l'article fabriqué. 

   Une ou plusieurs versions de nomenclature peuvent être définies pour l'article fabriqué. Vérifiez que les versions que vous souhaitez sont marquées comme approuvées et actives et qu'elles ont les dates effectives que vous souhaitez. La version de nomenclature peut s'appliquer à toute la société ou être spécifique aux sites.

8. Définissez la gamme pour l'article fabriqué. 

   Une ou plusieurs versions de gamme peuvent être définies pour l'article fabriqué. Vérifiez que les versions que vous souhaitez sont marquées comme approuvées et actives et qu'elles ont les dates effectives que vous souhaitez. La version de gamme doit être spécifique aux sites.

Si vous souhaitez utiliser les informations de gamme à des fins d'évaluation des coûts, des étapes de préparation supplémentaires sont nécessaires. Par exemple, les catégories de coûts qui sont affectées aux opérations de gamme doivent être correctes et complétées.

<a name="related-topics"></a>Rubriques connexes
--------

[Amortissement des coûts constants pour un article fabriqué](amortize-constant-costs-manufactured-item.md)

[Paramétrer les produits pouvant être produits ou approvisionnés](manufactured-items-treated-as-purchased-items.md)


