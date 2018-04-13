---
title: "Réservation de quantités en stock"
description: "La présente rubrique décrit les différentes options disponibles pour la réservation du stock."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 207264
ms.assetid: 47537e4f-cdf6-4813-96fd-c945b2dfe9d4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 67c7582665255e65995be688ef133e71938e7c28
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="reserve-inventory-quantities"></a>Réservation de quantités en stock

[!INCLUDE [banner](../includes/banner.md)]

La présente rubrique décrit les différentes options disponibles pour la réservation du stock.

Vous pouvez réserver automatiquement des quantités en stock pour une commande client spécifique. Cela signifie que le stock réservé ne peut pas être retiré de l'entrepôt pour les autres commandes, à moins que la réservation de stock ou une partie de celle-ci soit annulée.

Il existe plusieurs motifs pour réserver le stock :
-   Premier commandé, premier livré, ce qui signifie que les clients obtiennent les articles disponibles dans l'ordre dans lequel ils passent leurs commandes.
-   Il y a un risque de pénurie d'articles due à un délai de livraison long ou inconnu de la part du fournisseur. Vous souhaitez vous assurer que certains clients ou certaines commandes reçoivent la livraison des premiers articles disponibles.
-   Certains clients et certains types de commandes ont la priorité pour la livraison.
-   Des articles ont des numéros de lot ou de série. Vous pouvez marquer certains articles qui ont été ou seront livrés pour des commandes spécifiques.
-   Des articles spécialement commandés sont réservés pour certaines commandes.
-   Ordres de fabrication. Vous pouvez, par exemple, marquer des articles qui sont produits et ajustés pour des commandes spécifiques.

Le stock peut être réservé automatiquement lors de la création d'une ligne de commande, ou manuellement pour des commandes individuelles. Il est également possible de réserver le stock à différentes étapes d'un processus de production. Seuls les produits stockés peuvent être réservés. Les services ne peuvent pas être réservés car il n'y a pas de stock disponible. Il est possible de réserver le stock physique disponible et le stock commandé mais pas encore reçu. Si une quantité réservée est supérieure au stock disponible, un message s'affiche pour vous prévenir que la réservation d'une si grande quantité est impossible. Vous pouvez alors maintenir la réservation ou modifier la quantité commandée. La quantité peut être réservée ou modifiée. Si le nombre d'articles réservés est supérieur au nombre d'articles disponibles, la pénurie sera couverte dès que des articles seront disponibles pour la livraison.

## <a name="inventory-reservation-policies"></a>Stratégies de réservation de stock
Les stratégies de réservation de stock sont définies sur la page **Groupes de modèles d'article**, la page **Paramètres de gestion des stocks et des entrepôts**, et la page **Paramètres de production**.
### <a name="policies-on-the-item-model-groups-page"></a>Stratégies sur la page Groupes de modèles d'article

La section **Stratégies de stock** contient les stratégies suivantes pour réservation.

|                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Stratégie de réservation**  | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Date FIFO contrôlée    | Si vous cochez l'option **Date FIFO contrôlée**, la réservation de stock est contrôlée par une date de tri selon le principe du premier entré, premier sorti (First In First Out, FIFO). Les lots sont réservés sur la base de la date de réception des articles la plus proche, en fonction du principe du premier entré, premier sorti (First In, First Out, FIFO),                                                                                                                                                                                                                                                                       |
| En arrière à partir de la date d'expédition | Cette option devient disponible si vous avez sélectionné l'option **Date FIFO contrôlée**. Si vous sélectionnez **En arrière à partir de la date d'expédition**, le stock est réservé en arrière à partir de la date d'expédition souhaitée selon le principe du dernier entré, premier sorti (Last In, First Out, LIFO). Si aucune réception n'est disponible avant la date d'expédition, une réservation de type FIFO est utilisée.                                                                                                                                                                                                           |
| Réservation de ligne de vente d'articles  | Détermine si la réservation d'article est manuelle ou automatique. Si une réservation est automatiquement, le stock est réservé lors de la création de lignes de commande. Il est possible de créer des réservations au niveau du nombre d'articles pour les nomenclatures (option **Automatique**), ou pour les éléments individuels d'une nomenclature (option **Éclatement**). La valeur par défaut pour **Réservation de ligne de vente d'articles** peut être héritée des **Paramètres de la comptabilité client**. Sur cette page, la valeur est définie dans le champ Réservation de la **section** **Valeurs par défaut des ventes** sous l'onglet **Général**. |
| Même sélection de lot    | Une réservation de lots identiques vous permet de réserver du stock pour une ligne de commande client par rapport à un lot de stock unique. Si vous souhaitez utiliser cette option, vous devez également définir l'option **Consolider le besoin** sur **Oui**. Certains paramètres supplémentaires sont requis pour le groupe de dimensions de suivi et le groupe de dimensions de stockage. Pour plus d'informations, voir [Réservation du même lot pour une commande client](../sales-marketing/reserve-same-batch-sales-order.md).                                                          |
| Consolider le besoin | Cette option est similaire à l'option **Même sélection de lot**, qui consolide le stock réservé pour les lignes de commande client en un seul besoin.                                                                                                                                                                                                                                                                                                                                                                                      |
| Contrôlé par date FEFO    | Cette option permet de réserver des lots qui sont proches de leur date d'expiration ou période de consommation recommandée. Vous devez également définir le champ **Critères de prélèvement** pour sélectionner **Date d'expiration** ou **Période de consommation recommandée**.                                                                                                                                                                                                                                                                                                                              |

#### <a name="example-for-fifo-date-controlled-and-backward-from-ship-date"></a>Exemples de Date FIFO contrôlée et de En arrière à partir de la date d'expédition

Dans cet exemple, le stock disponible pour le numéro d'article A existe pour trois numéros de lot différents.

| numéro d'article | Numéro du lot | Quantité | date ;             |
|-------------|--------------|----------|------------------|
| A           | 1 000         | 5        | 2 février 2016 |
| A           | 1 001         | 3        | 1 janvier 2016  |
| A           | 1 002         | 7        | 3 mars 2016    |

Une commande client qui doit être automatiquement réservée et livrée le 4 avril 2016 réserve le lot suivant :
-   Si les deux cases à cocher **Date FIFO contrôlée** et **En arrière à partir de la date d'expédition** sont désactivées, le lot 1 000 est réservé le numéro de celui-ci est le plus petit.
-   Si la case à cocher **Date FIFO contrôlée** est activée et que la case à cocher **En arrière à partir de la date d'expédition** est désactivée, le lot 1 001 est réservé car il s'agit du lot avec la première date de réception (FIFO).
-   Si les deux cases à cocher **Date FIFO contrôlée** et **En arrière à partir de la date d'expédition** sont activées, le lot 1 002 est réservé car la date de réception de celui-ci est la plus proche de la date d'expédition de la commande client.

### <a name="policies-on-the-inventory-and-warehouse-management-parameter-page"></a>Stratégies sur la page du paramètre Gestion des stocks et des entrepôts

Il existe deux options liées aux réservations sur la page **Paramètres de gestion des stocks et des entrepôts** :
-   L'option **Réserver les articles commandés** sous l'onglet **Général** vous permet de réserver les réceptions d'articles qui sont commandées par rapport aux sorties d'articles dans les modules Comptabilité client, Gestion de projets et comptabilité et Contrôle de la production. Si vous désactivez cette option, vous pouvez uniquement réserver les articles physiquement reçus. Si un article a été paramétré pour accepter un stock négatif, ce champ est sans importance.
-   L'option **Réserver automatiquement les articles** sous l'onglet **Transport** détermine le paramètre par défaut si les articles sont automatiquement réservés pour les ordres de transfert. Le paramètre par défaut peut être remplacé sur les ordres de transfert individuels.

### <a name="inventory-reservation-policies-on-the-production-parameters-page"></a>Stratégies de réservation de stock sur la page Paramètres de production

La valeur du champ **Réservation** sous l'onglet **Général** sur la page **Paramètres de production** détermine le moment par défaut du processus de production auquel le stock doit être réservé. Par exemple, le stock peut être réservé lorsque le travail est planifiée, ou lorsque le travail est lancé.

