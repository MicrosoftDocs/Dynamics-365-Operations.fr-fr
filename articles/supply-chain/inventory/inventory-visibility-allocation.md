---
title: Allocation de stocks Inventory Visibility
description: Cet article explique comment configurer et utiliser la fonctionnalité d’allocation de stock, qui vous permet de réserver un stock dédié pour vous assurer que vous pouvez satisfaire vos canaux ou clients les plus rentables.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: ccc3a8c4b3d0649397b1d1f9139f7feebf39b02f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852503"
---
# <a name="inventory-visibility-inventory-allocation"></a>Répartition de stock pour Visibilité des stocks

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Contexte et objectif de l’entreprise

Dans de nombreux cas, les fabricants, les détaillants et les autres acteurs de la chaîne d’approvisionnement doivent pré-allouer des stocks pour des canaux de vente, des emplacements ou des clients importants, ou pour des événements de vente spécifiques. L’allocation des stocks est une pratique typique dans le processus de planification opérationnelle des ventes et est effectuée avant que les activités de vente réelles ne se produisent et qu’une commande client ne soit créée.

Par exemple, une entreprise de vélos dispose d’un stock limité pour un vélo très populaire. Cette société vend à la fois en ligne et en magasin. Dans chaque canal de vente, l’entreprise compte quelques partenaires commerciaux importants (places de marché et grands détaillants) qui exigent qu’une partie spécifique du stock disponible du vélo leur soit réservée. Par conséquent, l’entreprise de vélos doit être en mesure d’équilibrer la répartition des stocks entre les canaux et également de gérer les attentes de ses partenaires VIP. La meilleure façon d’atteindre ces deux objectifs est d’utiliser l’allocation des stocks, afin que chaque canal et détaillant puisse recevoir des quantités allouées spécifiques qui peuvent être vendues ultérieurement aux consommateurs.

L’allocation de stock a deux objectifs commerciaux fondamentaux :

- **Protection des stocks (ringfencing)** – Les organisations souhaitent pré-allouer des stocks restreints ou limités aux canaux, régions, clients VIP et filiales prioritaires. La fonctionnalité d’allocation de Visibilité des stocks vise à protéger le stock alloué, afin que les autres allocations, réservations ou autres demandes de vente n’affectent pas le stock précédemment alloué.
- **Contrôle de la survente** – La fonctionnalité d’allocation de Visibilité des stocks vise à restreindre les quantités précédemment allouées, afin que la partie réceptrice (par exemple, un canal ou un groupe de clients) ne les surconsomme pas lorsque la transaction de vente réelle basée sur un soft la réservation entre en vigueur.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Définition de l’allocation dans le Service Visibilité des stocks

Bien que la fonctionnalité d’allocation dans le service de Visibilité des stocks ne réserve pas les quantités de stock physique, elle fait référence à la quantité de stock physique disponible pour définir sa quantité de pool virtuelle *disponible pour la répartition* initiale. L’allocation de stock dans Visibilité des stocks est une allocation temporaire. Elle est effectuée avant que les transactions de vente réelles ne se produisent et ne dépend pas des commandes client. Par exemple, vous pouvez allouer le stock à vos canaux de vente les plus importants ou aux grands détaillants avant que les clients finaux ne visitent le canal de vente ou le magasin de détail pour l’acheter.

La différence entre la répartition des stocks et [réservation logicielle de stock](inventory-visibility-reservations.md) est que la pré-réservation est généralement liée aux transactions de vente réelles (lignes de commande client). Par conséquent, si vous souhaitez utiliser ensemble les fonctionnalités d’allocation et de réservation provisoire, nous vous recommandons d’effectuer d’abord l’allocation de stock, puis la réservation provisoire par rapport aux quantités allouées. Pour plus d’informations, voir [Consommer en réservation temporaire](#consume-to-soft-reserved).

La fonction d’allocation des stocks permet aux planificateurs des ventes ou aux gestionnaires de grands comptes de gérer et de pré-allouer les stocks importants entre les groupes d’allocation (tels que les canaux, les régions et les groupes de clients). Il prend également en charge le suivi, l’ajustement et l’analyse en temps réel de la consommation par rapport aux quantités allouées, de sorte que le réapprovisionnement ou la réallocation puisse être effectué à temps. Cette possibilité d’avoir une visibilité en temps réel sur l’allocation, la consommation et l’équilibre de l’allocation est particulièrement importante lors d’événements de vente rapide ou de promotion.

## <a name="terminology"></a>Terminologie

Les termes et concepts suivants sont utiles dans les discussions sur la répartition des stocks :

- **Groupe d’attribution** – Le groupe propriétaire de l’allocation, tel qu’un canal de vente, un groupe de clients ou un type de commande.
- **Valeur du groupe d’allocation** – La valeur de chaque groupe d’allocation. Par exemple, *web* ou *boutique* peut être la valeur du groupe d’allocation des canaux de vente, alors que *VIP* ou *normal* peut être la valeur du groupe d’allocation client.
- **Hiérarchie des allocations** – Un moyen de combiner des groupes d’attribution de manière hiérarchique. Par exemple, vous pouvez définir *canal* en tant que niveau hiérarchique 1, *région* comme niveau 2 et *groupe de clients* comme niveau 3. Lors de l’allocation de stock, vous devez suivre la séquence de la hiérarchie d’allocation lorsque vous spécifiez la valeur du groupe d’allocation. Par exemple, vous pouvez allouer 200 vélos rouges au canal *Web*, à la région *Londres* et au groupe de clients *VIP*.
- **Disponible à allouer** - Le *pool commun virtuel* qui indique la quantité disponible pour une allocation ultérieure. Il s’agit d’une mesure calculée que vous pouvez librement définir en utilisant votre propre formule. Si vous utilisez également la fonction de réservation temporaire, nous vous recommandons d’utiliser la même formule pour calculer le disponible à allouer et le disponible à réserver.
- **Alloué** – Une mesure physique indiquant le quota alloué pouvant être consommé par les groupes d’allocation.
- **Consommé** – Une mesure physique qui indique les quantités qui ont été consommées par rapport à la quantité initialement allouée. Au fur et à mesure que des nombres sont ajoutés à cette mesure physique, la mesure physique allouée est automatiquement réduite.

L’illustration suivante montre le flux de travail d’entreprise pour l’allocation de stock.

![Workflow métier d’allocation de visibilité de stock.](media/inventory-visibility-allocation-flow.png "Workflow métier d’allocation de visibilité de stock.")

## <a name="set-up-inventory-allocation"></a>Paramétrage de la répartition des stocks

La fonctionnalité d’allocation de stock comprend les composants suivants :

- La source de données prédéfinie liée à l’allocation, les mesures physiques et les mesures calculées.
- Groupes d’allocation personnalisables comportant un maximum de huit niveaux.
- Un ensemble d’interfaces de programmation d’application (API) d’allocation :

    - allouer
    - réallouer
    - ne pas allouer
    - consommer
    - interroger

Le processus de configuration de la fonctionnalité d’allocation comporte deux étapes :

- Configurez la [source de données](inventory-visibility-configuration.md#data-source-configuration) et ses [mesures](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- Configurez le nom et la hiérarchie du groupe d’allocation.

### <a name="predefined-data-source"></a>Source de données prédéfinies

Lorsque vous activez la fonctionnalité d’allocation et appelez l’API de mise à jour de configuration, Visibilité des stocks crée une source de données prédéfinie et plusieurs mesures initiales.

La source de données est nommée `@iv`.

Voici les premières mesures physiques :

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Voici les premières mesures calculées :

- `@iv`

    - `@iv.@available_to_allocate` = `??` – `??` – `@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>Ajouter d’autres mesures physiques à la mesure calculée disponible pour allocation

Pour utiliser l’allocation, vous devez configurer la mesure calculée disponible pour allocation (`@iv.@available_to_allocate`). Par exemple, vous avez la source de données `fno` et la mesure `onordered`, la source de données `pos` et la mesure `inbound`, et vous voulez faire une allocation sur place pour la somme de `fno.onordered` et `pos.inbound`. Dans ce cas, `@iv.@available_to_allocate` doit contenir `pos.inbound` et `fno.onordered` dans la formule. Voici un exemple :

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

### <a name="change-the-allocation-group-name"></a>Modifier le nom du groupe d’allocation

Un maximum de huit noms de groupe d’allocation peut être défini. Les groupes ont une hiérarchie.

Vous définissez les noms de groupe sur la page **Configuration Power App Visibilité des stocks**. Pour ouvrir cette page, dans votre environnement Microsoft Dataverse, ouvrez l’application Visibilité des stocks, puis sélectionnez **Configuration \> Affectation**.

Par exemple, si vous utilisez quatre noms de groupe et que vous les définissez sur \[`channel`, `customerGroup`, `region`, `orderType`\], ces noms seront valides pour les demandes liées à l’allocation lorsque vous appelez l’API de mise à jour de la configuration.

### <a name="allocation-using-tips"></a>Allocation à l’aide de pointes

- Pour chaque produit, la fonction de répartition doit utiliser le même *niveau de dimension* en fonction de la hiérarchie d’index de produits que vous avez définie dans la [configuration de la hiérarchie de l’index des produits](inventory-visibility-configuration.md#index-configuration). Par exemple, supposons que votre hiérarchie d'index est \[`Site`, `Location`, `Color`, `Size`\]. Si vous allouez une certaine quantité pour un produit au niveau de la dimension \[`Site`, `Location`, `Color`\], la prochaine fois que vous souhaitez allouer ce produit, vous devez également allouer au même niveau, \[`Site`, `Location`, `Color`\]. Si vous utilisez le niveau \[`Site`, `Location`, `Color`, `Size`\] ou \[`Site`, `Location`\], les données seront incohérentes.
- La modification du nom du groupe d’allocation n’aura aucune incidence sur les données enregistrées dans le service.
- L’attribution doit avoir lieu une fois que le produit a la quantité positive en stock.
- Pour allouer des produits d'un groupe de *niveau d'attribution* élevé à un sous-groupe, utilisez les API `Reallocate`. Par exemple, vous avez une hiérarchie de groupe d'allocation \[`channel`, `customerGroup`, `region`, `orderType`\], et vous souhaitez allouer un produit du groupe d'allocation \[En ligne, VIP\] au sous-groupe d'affectation \[En ligne, VIP, UE\], utilisez l'API `Reallocate` pour déplacer la quantité. Si vous utilisez l'API `Allocate`, elle allouera la quantité du pool commun virtuel.

### <a name="using-the-allocation-api"></a><a name="using-allocation-api"></a>Utilisation de l’API d’allocation

Actuellement, cinq API d’allocation sont ouvertes :

- POST /api/environment/{environmentId}/allocation/allocate
- POST /api/environment/{environmentId}/allocation/unallocate
- POST /api/environment/{environmentId}/allocation/reallocate
- POST /api/environment/{environmentId}/allocation/consume
- POST /api/environment/{environmentId}/allocation/query

#### <a name="allocate"></a>Allouer

Appelez l’API `Allocate` pour allouer un produit qui a des dimensions spécifiques. Voici le schéma du corps de la requête.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Par exemple, vous souhaitez allouer une quantité de 10 pour le produit *Vélo*, le site *1*, l’emplacement *11*, la couleur *rouge*, le canal *En ligne*, le groupe de clients *VIP* et la région *US*. Pour effectuer cette allocation, vous pouvez effectuer un appel dont le contenu de corps est le suivant.

```json
{
    "id": "???",
    "productId": "Bike",
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 10,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

La quantité doit toujours être supérieure à 0 (zéro).

#### <a name="unallocate"></a>Ne pas allouer

Utilisez l’API `Unallocate` pour inverser l’opération `Allocate`. La quantité négative n’est pas autorisée dans une opération `Allocate`. Le corps de `Unallocate` est identique au corps de `Allocate`.

#### <a name="reallocate"></a>Réallouer

Utilisez l’API `Reallocate` pour déplacer une quantité allouée vers une autre combinaison de groupe. Voici le schéma du corps de la requête.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "sourceGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "targetGroups": {
        "groupD": "string",
        "groupE": "string",
        "groupF": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Par exemple, vous pouvez déplacer deux vélos qui ont les dimensions \[1site=1, location=11, color=red\] du groupe d’attribution \[Online, VIP, US\] au groupe d’attribution \[Online, VIP, EU\] en appelant l’API `Reallocate` et en fournissant le corps de texte suivant.

```json
{
    "id": "???",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "EU"
    },
    "quantity": 2,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

#### <a name="consume"></a>Consommer

Utilisez l’API `Consume` pour valider la quantité consommée par rapport à l’allocation. Par exemple, vous pouvez utiliser cette API pour déplacer la quantité allouée vers certaines mesures réelles. Voici le schéma du corps de la requête.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "physicalMeasures": {
        "datasource1": {
            "measure": "string" // Addition or Subtraction
        }
    }
}
```

Par exemple, il y a huit vélos attribués qui ont les dimensions \[site=1, location=11, color=red\] pour le groupe d’allocation \[Online, VIP, US\]. La formule de disponibilité à allouer suivante est utilisée :

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

Les huit vélos sont attribués à partir de la mesure `pos.inbound`.

Maintenant, trois vélos sont vendus et ils sont prélevés sur le pool d’allocation. Pour enregistrer ce déplacement, vous pouvez passer un appel dont le corps de requête est le suivant.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "pos": {
            "inbound": "Subtraction"
        }
    }
}
```

Après cet appel, la quantité allouée pour le produit sera réduite de 3. De plus, la Visibilité des stocks générera un événement de modification disponible où `pos.inbound` = *-3*. Alternativement, vous pouvez conserver la valeur `pos.inbound` telle quelle et consommez simplement la quantité allouée. Cependant, dans ce cas, vous devez soit créer une autre mesure physique pour conserver les quantités consommées, soit utiliser la mesure prédéfinie `@iv.@consumed`.

Dans cette requête, notez que la mesure physique que vous utilisez dans le corps de la demande de calcul doit utiliser le type de modificateur opposé (addition ou soustraction), par rapport au type de modificateur utilisé dans la mesure calculée. Alors dans ce corps de consommation, `iv.inbound` a la valeur `Subtraction` et non pas `Addition`.

La source de données `fno` ne peut pas être utilisée dans le corps de consommation car nous avons toujours affirmé que la Visibilité des stocks ne peut modifier aucune donnée pour la source de données `fno`. Le flux de données est unidirectionnel, ce qui signifie que toutes les quantités changent pour la source de données `fno` doit provenir de votre environnement Supply Chain Management.

#### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a>Consommer en tant que réservation temporaire

L’API `Consume` peut également consommer la quantité allouée en tant que réservation temporaire. Dans ce cas, l’opération `Consume` réduira la quantité allouée, puis effectuera une réservation provisoire pour cette quantité. Pour utiliser cette approche, vous devez également utiliser la fonctionnalité [réservation temporaire](inventory-visibility-reservations.md) sous Visibilité des stocks.

Par exemple, vous avez défini un modificateur de réservation temporaire (mesure) comme `iv.softreserved`. La formule suivante est utilisée pour la mesure calculée disponible à la réservation :

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound` – `iv.softreserved`

Pour utiliser cette configuration avec la fonction d’allocation, ajoutez `@iv.@allocated` à `iv.available_to_reserve` pour produire la formule suivante :

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound` | `iv.softreserved` | `@iv.@allocated`

Puis mettez à jour `@iv.@available_to_allocate` avec la même valeur.

Lorsque vous souhaitez consommer une quantité de 3 et réserver directement cette quantité, vous pouvez passer un appel dont le corps de requête est le suivant.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "iv": {
            "softreserved": "Addition"
        }
    }
}
```

Dans cette requête, notez que `iv.softreserved` a la valeur `Addition` et non pas `Subtraction`.

#### <a name="query"></a>Requête

Utilisez l’API `Query` permettant de récupérer des informations relatives à l’allocation pour certains produits. Vous pouvez utiliser des filtres de dimension et des filtres de groupe d’allocation pour affiner les résultats. Les dimensions doivent correspondre exactement à celle que vous souhaitez récupérer, par exemple, \[site=1, location=11\] aura des résultats non liés par rapport à \[site=1, location=11, color=red\].

```json
{
    "productId": "string",
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "groups": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
    },
}
```

Par exemple, utilisez \[site=1, location=11, color=red\] et videz le champ des groupes pour obtenir tous les enregistrements d’allocation :

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

Utilisez \[site=1, location=11, color=red\] et les groupes \[channel=Online, customerGroup=VIP, region=US\] pour obtenir les enregistrements d’allocation pour ce groupe :

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```
