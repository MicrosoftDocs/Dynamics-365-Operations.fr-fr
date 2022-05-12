---
title: Prise en charge d’Inventory Visibility pour les articles WHS
description: Cette rubrique décrit la prise en charge de la Visibilité des stocks pour les articles activés pour les processus d’entrepôt avancés (articles WHS).
author: yufeihuang
ms.date: 03/10/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: cfbff05697f4159cb74d110887b8029f28fbf96b
ms.sourcegitcommit: 1050e58e621d9a0454895ed07c286936f8c03320
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2022
ms.locfileid: "8625400"
---
# <a name="inventory-visibility-support-for-whs-items"></a>Prise en charge d’Inventory Visibility pour les articles WHS

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la prise en charge de la Visibilité des stocks pour les articles activés pour les processus d’entrepôt avancés (articles WHS). La fonctionnalité qui ajoute cette fonctionnalité à la visibilité de l’inventaire est nommée *WHS avancé*.

## <a name="whs-items"></a>Articles WHS

Un article WHS est un article activé pour les processus d’entrepôt avancés (WHS) et traité dans un entrepôt également activé WHS.

Pour plus d’informations sur WHS et le module **Warehouse management** dans Microsoft Dynamics 365 Supply Chain Management, voir [Aperçu de Warehouse management](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>Étendue de la fonctionnalité

La fonctionnalité WHS avancée pour la visibilité des stocks se concentre sur les calculs de quantité en stock basés sur des requêtes en stock. La fonctionnalité n’est pas destinée à vous permettre d’utiliser la visibilité des stocks pour gérer les activités de traitement de l’entrepôt en général. La Visibilité des stocks n’expose pas les concepts spécifiques à l’entrepôt à ses utilisateurs. Voici quelques exemples de ces concepts :

- Hiérarchie de réservation
- Si un article ou un entrepôt est compatible WHS
- ID groupe de séquences d’unités
- Processus spécifiques à l’entrepôt, tels que les expéditions, les chargements, les vagues et le travail

Visibilité des stocks déduit ces informations en fonction des données envoyées par Supply Chain Management. Les données spécifiques au WHS (c’est-à-dire les données de la table `WHSInventReserve`) n’est pas visible pour les utilisateurs.

Quand vous utilisez la fonctionnalité WHS avancée pour la visibilité des stocks, tous les résultats de la requête seront identiques aux résultats des requêtes effectuées directement dans Supply Chain Management. Cependant, ils ne seront pas identiques aux résultats des requêtes effectuées à l’aide de l’application mobile Warehouse Management, car l’application mobile utilise une logique de calcul légèrement différente.

## <a name="when-to-use-the-feature"></a>Quand utiliser la fonctionnalité

Nous vous recommandons d’utiliser la fonctionnalité WHS avancée pour la visibilité des stocks dans les scénarios où toutes les conditions suivantes sont remplies :

- Vous synchronisez les données de Supply Chain Management avec la Visibilité des stocks.
- Vous utilisez WHS dans Supply Chain Management.
- Les utilisateurs effectuent des réservations pour les articles WHS à des niveaux autres que le niveau de l’entrepôt (par exemple, parce que vous utilisez le travail d’entrepôt).

Dans d’autres scénarios, les résultats des requêtes disponibles seront les mêmes, que la fonctionnalité WHS avancée pour la visibilité des stocks soit activée ou non. De plus, les performances seront meilleures si vous n’activez pas la fonctionnalité dans ces scénarios, car il y a moins de calculs et moins de surcharge.

## <a name="enable-the-advanced-whs-feature-for-inventory-visibility"></a>Activer la fonctionnalité WHS avancée pour la visibilité des stocks

Pour activer la fonctionnalité WHS avancée pour la visibilité des stocks, procédez comme suit.

1. Connectez-vous à Supply Chain Management en tant qu’administrateur.
1. Ouvrez l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), puis activez les fonctionnalités suivantes dans cet ordre :

    1. *Intégration de la visibilité du stock*
    1. *Activer les articles d’entrepôt dans Visibilité des stocks*

1. Allez dans **Gestion des stocks \> Configuration \> Paramètres d’intégration de la visibilité des stocks**.
1. Dans l’onglet **Activer les articles WHS**, définissez l’option **Activer les articles WHS** sur *Oui*.
1. Connectez-vous à Power Apps.
1. Ouvrez la page **Configuration**, puis, dans l’onglet **Gestion des fonctionnalités**, activez la fonctionnalité *AdvancedWHS*.
1. Dans Supply Chain Management, accédez à **Gestion de l’inventaire \> Tâches périodiques \> Intégration de la visibilité des stocks**.
1. Dans le volet Actions, sélectionnez **Désactiver** pour désactiver temporairement la visibilité de l’inventaire.
1. Dans le volet Actions, sélectionnez **Activer** pour réactiver la visibilité du stock. Le complément est rechargé et la nouvelle fonctionnalité est maintenant activée. Vos données liées au WHS commencent à être synchronisées avec la Visibilité des stocks.

## <a name="query-on-hand-quantities-of-whs-items"></a>Interroger les quantités en stock des articles WHS

Pour rechercher des articles WHS, utilisez les mêmes [interface de programmation d’application (API) et syntaxe des messages](inventory-visibility-api.md) que pour les articles non WHS. Vous n’avez pas à spécifier si un article est un article WHS ou un article non WHS. La Visibilité de stocks distingue automatiquement les articles en fonction des données stockées.

Les résultats des requêtes pour les articles WHS sont essentiellement les mêmes que les résultats pour les articles non WHS. La seule différence est que les mesures physiques suivantes de la source de données `fno` sont calculées en fonction de la logique WHS dans Supply Chain Management :

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Toutes les autres mesures physiques sont calculées comme elles le sont quand la fonction WHS avancée pour la visibilité du stock est désactivée.

Pour des informations détaillées sur le fonctionnement des calculs de disponibilité pour les articles WHS, voir le livre blanc [Réservations dans Warehouse Management](https://www.microsoft.com/download/details.aspx?id=43284).

Les entités de données qui sont exportées vers Dataverse ne peut pas encore mettre à jour les quantités pour les articles WHS. Les quantités affichées dans les entités de données sont correctes à la fois pour les articles non WHS et pour les quantités qui ne sont pas affectées par la logique WHS (c’est-à-dire les mesures sauf `AvailPhysical`, `AvailOrdered`, `ReservPhysical` et `ReservOrdered` dans la source de données `fno`).

Les modifications apportées aux quantités d’articles WHS stockées dans la source de données Supply Chain Management sont interdites. Comme pour les autres fonctionnalités de la Visibilité des stock, cette restriction est appliquée pour aider à prévenir les conflits.

## <a name="soft-reservations-on-whs-items-in-inventory-visibility"></a>Réservation provisoire des articles WHS dans la visibilité des stocks

En général, [les réservations provisoires](inventory-visibility-reservations.md) sur les articles WHS sont pris en charge. Vous pouvez inclure des mesures physiques liées au WHS dans les calculs de réservation provisoire. 

Dans une limitation connue, le calcul *disponible à la réservation* n’est actuellement pas pris en charge pour les articles WHS. Par conséquent, s’il y a une réservation au-dessus des dimensions actuelles où une réservation provisoire se produit, le calcul *disponible à la réservation* est incorrect. Les réservations provisoires ne seront pas affectées quand l’option **ifCheckAvailForReserv** est désactivée dans [l’API de réservation provisoire](inventory-visibility-api.md#create-one-reservation-event).

Cette contrainte s’applique également aux fonctionnalités et aux personnalisations basées sur des réservations provisoires (telles que l’allocation).

## <a name="calculate-available-to-promise-quantities"></a>Calcul des quantités disponibles à la vente

La solution prend entièrement en charge [disponible à la vente (DAV)](inventory-visibility-available-to-promise.md) pour les articles WHS. Vous pouvez définir des calculs DAV sans vous soucier des détails spécifiques à WHS.
