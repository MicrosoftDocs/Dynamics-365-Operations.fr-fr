---
title: Niveau de calcul des coûts
description: Cet article décrit le niveau de nomenclature nommé niveau de calcul des coûts. Ce niveau de nomenclature exclut les ordres de fabrication et les commandes par lots de ses calculs.
author: JennySong-SH
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 647ef4b13b864cfdbb7905fe7a0d340e85f6c1e6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850871"
---
# <a name="cost-calculation-level"></a>Niveau de calcul des coûts

[!include [banner](../includes/banner.md)]

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