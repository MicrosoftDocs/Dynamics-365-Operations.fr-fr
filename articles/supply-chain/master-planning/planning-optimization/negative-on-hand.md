---
title: Planification avec des quantités disponibles négatives
description: Cet article explique comment les quantités disponibles négatives sont gérées.
author: t-benebo
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: b4fc8b37fd800e3b4652513f150f9806bf1d5d67
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741120"
---
# <a name="planning-with-negative-on-hand-quantities"></a>Planification avec des quantités disponibles négatives

[!include [banner](../../includes/banner.md)]

Si le système affiche une quantité globale disponible négative, le moteur de planification traite la quantité comme étant égale à 0 (zéro) pour éviter tout approvisionnement excessif. Voici comment fonctionne cette fonctionnalité :

1. La planification générale regroupe les quantités disponibles au niveau le plus bas des dimensions de couverture. (Par exemple, si *emplacement* n’est pas une dimension de couverture, la planification générale regroupe les quantités disponibles au niveau *entrepôt*.)
1. Si la quantité globale disponible au niveau le plus bas des dimensions de couverture est négative, le système suppose que la quantité disponible est vraiment égale à 0 (zéro).

> [!IMPORTANT]
> Le système de planification peut seulement être aussi précis que les données d’entrée. Si les données d’entrée sont inexactes, les enregistrements de la quantité disponible négative indiqueront que les informations de stock dans Microsoft Dynamics 365 Supply Chain Management ne sont pas synchronisées avec le monde réel. Par conséquent, le résultat de la planification sera erroné. Pour obtenir un résultat de planification précis, vous devez réduire le nombre d’enregistrements affichant une quantité disponible négative.

## <a name="example-1"></a>Exemple 1

L’entrepôt 13 est configuré de la manière suivante :

- **Code couverture** : Min./Max.
- **Minimum** : 15 pièces (pcs)
- **Maximum** : 25 pcs

Le niveau le plus bas des dimensions de couverture est *entrepôt*, et les quantités disponibles suivantes sont enregistrées au niveau *emplacement* :

- **Site 1, entrepôt 13, emplacement 1** : 20 pcs
- **Site 1, entrepôt 13, emplacement 2** : &minus;8 pcs

Par conséquent, la quantité globale disponible pour l’entrepôt 13 est 12 pcs (= 20 pcs &minus; 8 pcs).

Dans ce cas, le moteur de planification utilise une quantité globale disponible de 12 pcs pour l’entrepôt 13.

Le résultat est une commande planifiée de 13 pcs (= 25 pcs &minus; 12 pcs) pour remplir l’entrepôt 13 de 12 pcs à 25 pcs

## <a name="example-2"></a>Exemple 2

L’entrepôt 13 est configuré de la manière suivante :

- **Code couverture** : Min./Max.
- **Minimum** : 15 pcs
- **Maximum** : 25 pcs

Le niveau le plus bas des dimensions de couverture est *entrepôt*, et les quantités disponibles suivantes sont enregistrées au niveau *emplacement* :

- **Site 1, entrepôt 13, emplacement 1** : 4 pcs
- **Site 1, entrepôt 13, emplacement 2** : &minus;8 pcs

Par conséquent, la quantité globale disponible pour l’entrepôt 13 est &minus;4 pcs (= 4 pcs &minus; 8 pcs). Autrement dit, elle est inférieure à 0 (zéro).

Dans ce cas, le moteur de planification suppose que la quantité disponible pour l’entrepôt 13 est 0 pcs au lieu de &minus;4 pcs.

Le résultat est une commande planifiée de 25 pcs (= 25 pcs &minus; 0 pcs) pour remplir l’entrepôt 13 de 0 pcs à 25 pcs

## <a name="planning-when-there-is-a-reservation-against-negative-on-hand-inventory"></a>Planification quand  il y a une réservation par rapport au stock disponible négatif

Si vous ajustez le stock alors que des réservations physiques existent, vous pouvez provoquer une situation où une commande est physiquement réservée par rapport à un stock négatif. Dans ce cas, étant donné qu’une réservation physique existe, vous devez disposer d’un approvisionnement pour couvrir la quantité réservée. Par conséquent, un réapprovisionnement est nécessaire, de sorte que le système crée soit une commande planifiée pour réapprovisionner la quantité qui ne peut pas être couverte par le stock disponible existant, soit la couvre avec une commande existante pour l’article.

L’exemple suivant illustre ce scénario.

### <a name="example"></a>Exemple

Le système est configuré de la manière suivante :

- Le produit *FG* existe avec *10* unités. de stock disponible.
- La configuration du produit permet un stock physique négatif.
- Une commande client existe pour une quantité de *10* unités. de produit *FG*.
- La quantité de la commande client est physiquement réservée par rapport au stock disponible existant.

Vous ajustez ensuite la quantité de produit *FG* de sorte que le stock disponible devienne 5. Étant donné que le stock de produits en stock est de 5, la quantité de la commande client est désormais réservée par rapport à la quantité qui n’est pas disponible en stock (ce serait similaire si le stock était de 0, auquel cas la commande client serait réservée par rapport au stock négatif ). Si vous exécutez la planification générale maintenant, un ordre planifié d’une quantité de 5 pour *FG* sera créé pour fournir la commande client, car la planification générale utilisera toujours l’approvisionnement existant ou créera une commande planifiée pour fournir la réservation physique.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
