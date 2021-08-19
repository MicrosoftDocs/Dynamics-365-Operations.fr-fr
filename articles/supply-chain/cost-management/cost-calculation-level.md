---
title: Niveau de calcul des coûts
description: Cette rubrique décrit le niveau de nomenclature nommé niveau de calcul des coûts. Ce niveau de nomenclature exclut les ordres de fabrication et les commandes par lots de ses calculs.
author: AndersGirke
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 41f2550ff22b838aa5d85022582fd9715917fe462aa34dbfc833941f5ada3325
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717388"
---
# <a name="cost-calculation-level"></a>Niveau de calcul des coûts

Le niveau de nomenclature nommé **Niveau de calcul des coûts** exclut les ordres de fabrication et les commandes par lots de ses calculs. Le système utilise ce niveau lorsqu’il exécute des calculs de coût dans les versions d’évaluation des coûts. Dans les processus tels que le recalcul et la clôture de stock, le système utilise le niveau de nomenclature **Niveau d’évaluation des coûts** à la place.

Le scénario simple suivant montre les différences entre le niveau de nomenclature **Niveau de calcul des coûts** et le niveau de nomenclature **Niveau d’évaluation des coûts**.

Vous avez trois produits : A, B et C. Le produit C est un composant du produit B et le produit B est un composant du produit A.

- Le **Niveau d’évaluation des coûts** attribue les niveaux de nomenclature suivants :

    - **Produit A :** 0
    - **Produit B :** 1
    - **Produit C :** 2

- Le **Niveau de calcul des coûts** attribue les niveaux de nomenclature suivants :

    - **Produit A :** 0
    - **Produit B :** 1
    - **Produit C :** 2

Un ordre de fabrication pour le produit C est ensuite créé et le produit A est ajouté à la nomenclature de l’ordre de fabrication. Une fois la commande estimée, les niveaux de nomenclature sont mis à jour de la manière suivante :

- Le **Niveau d’évaluation des coûts** attribue les niveaux de nomenclature suivants :

    - **Produit B :** 1
    - **Produit C :** 2
    - **Produit A :** 3

- Le **Niveau de calcul des coûts** attribue les niveaux de nomenclature suivants :

    - **Produit A :** 0
    - **Produit B :** 1
    - **Produit C :** 2

Ce comportement garantit que les modifications apportées aux nomenclatures des ordres de fabrication n’affectent pas les calculs de coûts ultérieurs.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]