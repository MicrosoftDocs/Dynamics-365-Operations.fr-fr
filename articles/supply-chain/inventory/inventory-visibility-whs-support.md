---
title: Prise en charge d’Inventory Visibility pour les articles WMS
description: Cet article décrit la prise en charge de la Inventory Visibility pour les articles activés pour les processus de gestion des entrepôts (articles WMS).
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: bed402ecf20c19e81b2687efd90dba600460971a
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762737"
---
# <a name="inventory-visibility-support-for-wms-items"></a>Prise en charge d’Inventory Visibility pour les articles WMS

[!include [banner](../includes/banner.md)]

Cet article décrit la prise en charge de la Inventory Visibility pour les articles activés pour les processus de gestion des entrepôts (articles WMS). La fonctionnalité qui ajoute cette fonctionnalité à la visibilité de l’inventaire est nommée *WMS avancé*.

## <a name="wms-items"></a>Articles WMS

Un article WMS est un article activé pour les processus de gestion des entrepôts et traité dans un entrepôt également activé WMS.

Pour plus d’informations sur WMS et le module **Warehouse management** dans Microsoft Dynamics 365 Supply Chain Management, voir [Aperçu de Warehouse management](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>Étendue de la fonctionnalité

La fonctionnalité WMS avancée pour la visibilité des stocks se concentre sur les calculs de quantité en stock basés sur des requêtes en stock. La fonctionnalité n’est pas destinée à vous permettre d’utiliser la visibilité des stocks pour gérer les activités de traitement de l’entrepôt en général. La Inventory Visibility n’expose pas les concepts spécifiques à l’entrepôt à ses utilisateurs. Voici quelques exemples de ces concepts :

- Hiérarchie de réservation
- Si un article ou un entrepôt est compatible WMS
- ID groupe de séquences d’unités
- Processus spécifiques à l’entrepôt, tels que les expéditions, les chargements, les vagues et le travail

Inventory Visibility déduit ces informations en fonction des données envoyées par Supply Chain Management. Les données spécifiques au WMS (c’est-à-dire les données de la table `WHSInventReserve`) n’est pas visible pour les utilisateurs.

Quand vous utilisez la fonctionnalité WMS avancée pour la visibilité des stocks, tous les résultats de la requête seront identiques aux résultats des requêtes effectuées directement dans Supply Chain Management. Cependant, ils ne seront pas identiques aux résultats des requêtes effectuées à l’aide de l’application mobile Warehouse Management, car l’application mobile utilise une logique de calcul légèrement différente.

## <a name="when-to-use-the-feature"></a>Quand utiliser la fonctionnalité

Nous vous recommandons d’utiliser la fonctionnalité WMS pour Inventory Visibility dans les scénarios où toutes les conditions suivantes sont remplies :

- Vous synchronisez les données de Supply Chain Management avec la Inventory Visibility.
- Vous utilisez WMS dans Supply Chain Management.
- Les utilisateurs effectuent des réservations pour les articles WMS à des niveaux inférieurs au niveau de l’entrepôt (par exemple, au niveau du contenant parce que vous traitez le travail d’entrepôt).

Dans d’autres scénarios, les résultats des requêtes disponibles seront les mêmes, que la fonctionnalité WMS avancée pour la visibilité des stocks soit activée ou non. De plus, les performances seront meilleures si vous n’activez pas la fonctionnalité dans ces scénarios, car il y a moins de calculs et moins de surcharge.

## <a name="enable-the-wms-feature-for-inventory-visibility"></a>Activer la fonctionnalité WMS pour Inventory Visibility

Pour activer la fonctionnalité WMS pour Inventory Visibility, procédez comme suit.

1. Connectez-vous à Supply Chain Management en tant qu’administrateur.
1. Ouvrez l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), puis activez les fonctionnalités suivantes dans cet ordre :

    1. *Intégration de la visibilité du stock*
    1. *Activer les articles d’entrepôt dans Inventory Visibility*

1. Allez dans **Gestion des stocks \> Configuration \> Paramètres d’intégration de la visibilité des stocks**.
1. Dans l’onglet **Activer les articles WMS**, définissez l’option **Activer les articles WMS** sur *Oui*.
1. Connectez-vous à votre environnement Power Apps et ouvrez **Inventory Visibility**.
1. Ouvrez la page **Configuration**, puis, dans l’onglet **Gestion des fonctionnalités**, activez la fonctionnalité *AdvancedWHS*.
1. Dans Supply Chain Management, accédez à **Gestion de l’inventaire \> Tâches périodiques \> Intégration de la visibilité des stocks**.
1. Dans le volet Actions, sélectionnez **Désactiver** pour désactiver temporairement la visibilité de l’inventaire.
1. Dans le volet Actions, sélectionnez **Activer** pour réactiver la visibilité du stock. Le complément est rechargé et la nouvelle fonctionnalité est maintenant activée. Vos données liées au WMS commencent à être synchronisées avec la Inventory Visibility.

## <a name="query-on-hand-quantities-of-wms-items"></a>Interroger les quantités en stock des articles WMS

Pour rechercher des articles WMS, utilisez les mêmes [interface de programmation d’application (API) et syntaxe des messages](inventory-visibility-api.md) que pour les articles non WMS. Vous n’avez pas à spécifier si un article est un article WMS ou un article non WMS. La Visibilité de stocks distingue automatiquement les articles en fonction des données stockées.

Les résultats des requêtes pour les articles WMS sont essentiellement les mêmes que les résultats pour les articles non WMS. La seule différence est que les mesures physiques suivantes de la source de données `fno` sont calculées en fonction de la logique WMS dans Supply Chain Management :

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Toutes les autres mesures physiques sont calculées comme elles sont quand la fonction WMS pour Inventory Visibility est désactivée.

Pour des informations détaillées sur le fonctionnement des calculs de disponibilité pour les articles WMS, voir le livre blanc [Réservations dans Warehouse Management](https://www.microsoft.com/download/details.aspx?id=43284).

## <a name="on-hand-list-view-and-data-entity-for-wms-items"></a>Affichage de la liste des stocks disponibles et entité de données pour les articles WMS

La page **Précharger le récapitulatif de visibilité des stocks** fournit une vue pour l’entité *Résultats de préchargement de requête d’index disponibles*. Contrairement à l’entité *Récapitulatif des stocks*, l’entité *Résultats de préchargement de requête d’index disponibles* fournit une liste des stocks disponibles pour les produits avec les dimensions sélectionnées. La Inventory Visibility synchronise les données récapitulatives préchargées toutes les 15 minutes.

Si vous utilisez Inventory Visibility avec les articles WMS et que vous souhaitez afficher la liste disponible pour les articles WMS, nous vous recommandons d’activer la fonctionnalité *Précharger la synthèse Inventory Visibility* (voir aussi [Précharger une requête des stocks disponibles simplifiée](inventory-visibility-power-platform.md#preload-streamlined-onhand-query)). Une entité de données correspondante dans Dataverse stocke le résultat de préchargement de la requête, qui est mis à jour toutes les 15 minutes. Le nom de l’entité de données est `Onhand Index Query Preload Result`.

> [!IMPORTANT]
> L’entité Dataverse est en lecture seule. Vous pouvez afficher et exporter les données dans les entités Inventory Visibility, mais **ne les modifiez pas**.

Les modifications apportées aux quantités d’articles WMS stockées dans la source de données Supply Chain Management (`fno`) sont interdites. Ce comportement correspond au comportement des autres fonctionnalités d‘Inventory Visibility. Cette restriction est appliquée pour aider à prévenir les conflits.

## <a name="wms-item-compatibility-for-other-functions-in-inventory-visibility"></a>Compatibilité des articles WMS pour les autres fonctions dans Inventory Visibility

Les [réservations souples](inventory-visibility-reservations.md) et la [répartition des stocks](inventory-visibility-allocation.md) des articles WMS sont pris en charge. Vous pouvez inclure des mesures physiques liées au WMS dans les calculs de réservation et de répartition.

## <a name="calculate-available-to-promise-quantities"></a>Calcul des quantités disponibles à la vente

La solution prend entièrement en charge [disponible à la vente (DAV)](inventory-visibility-available-to-promise.md) pour les articles WMS. Vous pouvez définir des calculs DAV sans vous soucier des détails spécifiques à WMS.
