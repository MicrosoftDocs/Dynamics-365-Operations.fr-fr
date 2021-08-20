---
title: Planification avec des quantités disponibles négatives
description: Cette rubrique explique comment une quantité disponible négative est gérée lorsque vous utilisez la fonctionnalité d’optimisation de la planification.
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 97688e09aae9706dd85e7965aa08c7ea873a44d81391c39406e2e6367660e0d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758542"
---
# <a name="planning-with-negative-on-hand-quantities"></a>Planification avec des quantités disponibles négatives

[!include [banner](../../includes/banner.md)]

Si le système affiche une quantité globale disponible négative, le moteur de planification traite la quantité comme étant égale à 0 (zéro) pour éviter tout approvisionnement excessif. Voici comment fonctionne cette fonctionnalité :

1. La fonctionnalité d’optimisation de la planification regroupe les quantités disponibles au niveau le plus bas des dimensions de couverture. (Par exemple, si *emplacement* n’est pas une dimension de couverture, la fonctionnalité d’optimisation de la planification regroupe les quantités disponibles au niveau *entrepôt*.)
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

## <a name="planning-when-there-is-a-reservation-against-negative-on-hand-inventory"></a>Planification lorsqu’il y a une réservation par rapport au stock disponible négatif

Si vous ajustez le stock alors que des réservations physiques existent, vous pouvez provoquer une situation où une commande est physiquement réservée par rapport à un stock négatif. Dans ce cas, étant donné qu’une réservation physique existe, l’optimisation de la planification suppose qu’elle est prise en charge par le stock disponible, même si la réception du stock disponible n’est pas encore enregistrée dans le système. Par conséquent, il suppose que le réapprovisionnement n’est pas requis et ne crée pas d’ordre planifié pour réapprovisionner la quantité de la commande.

L’exemple suivant illustre ce scénario.

### <a name="example"></a>Exemple

Le système est configuré de la manière suivante :

- Le produit *FG* existe avec *10* unités. de stock disponible.
- La configuration du produit permet un stock physique négatif.
- Une commande client existe pour une quantité de *10* unités. de produit *FG*.
- La quantité de la commande client est physiquement réservée par rapport au stock disponible existant.

Vous ajustez ensuite la quantité de produit *FG* de sorte que le stock disponible devienne 0 (zéro). Étant donné que le stock de produits en stock est nul, la quantité de la commande client est désormais réservée par rapport au stock négatif. Cependant, si vous exécutez la planification principale maintenant, aucun ordre planifié ne sera créé pour fournir la commande client, car l’optimisation de la planification supposera que le stock disponible requis existe pour fournir la réservation physique.

## <a name="related-resources"></a>Ressources associées

- [Vue d’ensemble de l’optimisation de la planification](planning-optimization-overview.md)
- [Mise en route de l’optimisation de la planification](get-started.md)
- [Analyse de concordance d’optimisation de la planification](planning-optimization-fit-analysis.md)
- [Afficher l’historique du plan et les journaux de planification](plan-history-logs.md)
- [Annuler une tâche de planification](cancel-planning-job.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
