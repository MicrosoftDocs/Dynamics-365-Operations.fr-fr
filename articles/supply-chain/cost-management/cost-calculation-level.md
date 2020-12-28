---
title: Niveau de calcul des coûts
description: Cette rubrique décrit le niveau de nomenclature nommé niveau de calcul des coûts. Ce niveau de nomenclature exclut les ordres de fabrication et les commandes par lots de ses calculs.
author: AndersGirke
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 52b77e794ee38add556ac01d62c973b38c48a548
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427799"
---
# <a name="cost-calculation-level"></a>Niveau de calcul des coûts

Le niveau de nomenclature nommé **Niveau de calcul des coûts** exclut les ordres de fabrication et les commandes par lots de ses calculs. Le système utilise ce niveau lorsqu'il exécute des calculs de coût dans les versions d'évaluation des coûts. Dans les processus tels que le recalcul et la clôture de stock, le système utilise le niveau de nomenclature **Niveau d'évaluation des coûts** à la place.

Le scénario simple suivant montre les différences entre le niveau de nomenclature **Niveau de calcul des coûts** et le niveau de nomenclature **Niveau d'évaluation des coûts**.

Vous avez trois produits : A, B et C. Le produit C est un composant du produit B et le produit B est un composant du produit A.

- Le **Niveau d'évaluation des coûts** attribue les niveaux de nomenclature suivants :

    - **Produit A :** 0
    - **Produit B :** 1
    - **Produit C :** 2

- Le **Niveau de calcul des coûts** attribue les niveaux de nomenclature suivants :

    - **Produit A :** 0
    - **Produit B :** 1
    - **Produit C :** 2

Un ordre de fabrication pour le produit C est ensuite créé et le produit A est ajouté à la nomenclature de l'ordre de fabrication. Une fois la commande estimée, les niveaux de nomenclature sont mis à jour de la manière suivante :

- Le **Niveau d'évaluation des coûts** attribue les niveaux de nomenclature suivants :

    - **Produit B :** 1
    - **Produit C :** 2
    - **Produit A :** 3

- Le **Niveau de calcul des coûts** attribue les niveaux de nomenclature suivants :

    - **Produit A :** 0
    - **Produit B :** 1
    - **Produit C :** 2

Ce comportement garantit que les modifications apportées aux nomenclatures des ordres de fabrication n'affectent pas les calculs de coûts ultérieurs.
