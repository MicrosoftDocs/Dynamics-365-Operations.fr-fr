---
title: Allocation de stocks Inventory Visibility
description: Cet article explique comment configurer et utiliser la fonctionnalité d’allocation de stock, qui vous permet de réserver un stock dédié pour vous assurer que vous pouvez satisfaire vos canaux ou clients les plus rentables.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 449ca0616405ba589b92fba1ef078a4350d1e3b1
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762670"
---
# <a name="inventory-visibility-inventory-allocation"></a>Allocation de stocks Inventory Visibility

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Contexte et objectif de l’entreprise

Les organisations doivent souvent préallouer leur stock disponible aux canaux de vente, groupes de clients, régions et événements promotionnels les plus importants pour s’assurer que le stock préalloué est protégé contre toute autre utilisation et ne peut être consommé que par des transactions de vente pertinentes pour la répartition. La répartition des stocks dans Inventory Visibility est un composant du processus de planification opérationnelle des ventes qui s’effectue avant toute activité de vente réelle ou la création d’une commande client.

Par exemple, une entreprise nommée Contoso produit un vélo populaire. Malheureusement, suite à une récente perturbation de la chaîne d’approvisionnement qui a touché tout le stock en transit du vélo, Contoso ne dispose que d’un stock disponible limité et doit en faire le meilleur usage. Contoso vend ses produits à la fois en ligne et en magasin. Dans chaque canal de vente, l’entreprise compte quelques partenaires commerciaux importants (places de marché et grands détaillants) qui exigent qu’une partie spécifique du stock disponible du vélo leur soit réservée. Par conséquent, l’entreprise de vélos doit être en mesure d’équilibrer la répartition des stocks entre les canaux et également de gérer les attentes de ses partenaires VIP. La meilleure façon d’atteindre ces deux objectifs est d’utiliser l’allocation des stocks, afin que chaque canal et détaillant puisse recevoir des quantités allouées spécifiques qui peuvent être vendues ultérieurement aux consommateurs.

L’allocation de stock a deux objectifs commerciaux fondamentaux :

- **Protection des stocks (réservation)**  : les organisations souhaitent pré-allouer des stocks restreints ou limités aux canaux, régions, clients VIP et filiales prioritaires. La fonctionnalité d’allocation de Inventory Visibility vise à protéger le stock alloué, afin que les autres allocations, réservations ou autres demandes de vente n’affectent pas le stock précédemment alloué.
- **Contrôle de la survente** – La fonctionnalité d’allocation de Inventory Visibility vise à restreindre les quantités précédemment allouées, afin que la partie réceptrice (par exemple, un canal ou un groupe de clients) ne les surconsomme pas lorsque la transaction de vente réelle basée sur un soft la réservation entre en vigueur.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Définition de l’allocation dans le Service Inventory Visibility

### <a name="allocation-virtual-pool"></a>Pool virtuel de répartition

Bien que la fonctionnalité de répartition dans Inventory Visibility ne mette pas de côté des quantités de stocks physiques, elle fait référence à la quantité de stocks physiques disponible pour définir sa quantité de pool virtuel *disponible pour répartition* initiale. L’allocation de stock dans Inventory Visibility est une allocation temporaire. Elle est effectuée avant que les transactions de vente réelles ne se produisent et ne dépend pas des commandes client. Par exemple, vous pouvez allouer le stock à vos canaux de vente les plus importants ou aux grands détaillants avant que les clients finaux ne visitent le canal de vente ou le magasin de détail pour l’acheter.

### <a name="difference-between-inventory-allocation-and-soft-reservation"></a>Différence entre la répartition de stocks et la réservation provisoire

Les [réservations provisoires](inventory-visibility-reservations.md) sont généralement liées aux transactions de vente réelles (lignes de commande client). La répartition et la réservation provisoire peuvent être utilisées indépendamment, mais pour les utiliser ensemble, la réservation provisoire doit être effectuée après la répartition. Nous vous recommandons de commencer par allouer les stocks, puis d’effectuer la réservation provisoire par rapport aux quantités allouées afin d’atteindre une consommation en temps quasi réel par rapport à la répartition. Pour plus d’informations, voir [Consommer en réservation provisoire](#consume-to-soft-reserved).

La fonction de répartition permet aux planificateurs des ventes ou aux gestionnaires de grands comptes de gérer et de pré-allouer les stocks importants entre les groupes d’allocation (tels que les canaux, les régions et les groupes de clients). Elle prend également en charge le suivi, l’ajustement et l’analyse en temps réel de la consommation par rapport aux quantités allouées afin de garantir que le réapprovisionnement ou la réallocation puisse être effectué(e) à temps. Cette possibilité d’avoir une visibilité en temps réel sur l’allocation, la consommation et l’équilibre de l’allocation est particulièrement importante lors d’événements de vente rapide ou de promotion.

## <a name="terminology"></a>Terminologie

Les termes et concepts suivants sont utiles dans les discussions sur la répartition des stocks :

- **Groupe d’attribution** – Le groupe propriétaire de l’allocation, tel qu’un canal de vente, un groupe de clients ou un type de commande.
- **Valeur du groupe d’allocation** – La valeur de chaque groupe d’allocation. Par exemple, *web* ou *boutique* peut être la valeur du groupe d’allocation des canaux de vente, alors que *VIP* ou *normal* peut être la valeur du groupe d’allocation client.
- **Hiérarchie des allocations** – Un moyen de combiner des groupes d’attribution de manière hiérarchique. Par exemple, vous pouvez définir *canal* en tant que niveau hiérarchique 1, *région* comme niveau 2 et *groupe de clients* comme niveau 3. Lors de l’allocation de stock, vous devez suivre la séquence de la hiérarchie d’allocation lorsque vous spécifiez la valeur du groupe d’allocation. Par exemple, vous pouvez allouer 200 vélos rouges au canal *Web*, à la région *Londres* et au groupe de clients *VIP*.
- **Disponible à allouer** - Le *pool commun virtuel* qui indique la quantité disponible pour une allocation ultérieure. Il s’agit d’une mesure calculée que vous pouvez librement définir en utilisant votre propre formule. Si vous utilisez également la fonction de réservation provisoire, nous vous recommandons d’utiliser la même formule pour calculer le disponible à allouer et le disponible à réserver.
- **Alloué** – Une mesure physique indiquant le quota alloué pouvant être consommé par les groupes d’allocation. Elle est déduite en même temps que la quantité consommée est ajoutée.
- **Consommé** – Une mesure physique qui indique les quantités qui ont été consommées par rapport à la quantité initialement allouée. Au fur et à mesure que des nombres sont ajoutés à cette mesure physique, la mesure physique allouée est automatiquement réduite.

L’illustration suivante montre le flux de travail d’entreprise pour l’allocation de stock.

![Workflow métier d’allocation de visibilité de stock.](media/inventory-visibility-allocation-flow.png "Workflow métier d’allocation de visibilité de stock.")

L’illustration suivante montre la hiérarchie de répartition et les groupes de répartition. Le *pool commun virtuel* indiqué ici est la quantité disponible pour répartition.

[<img src="media/inventory-visibility-allocation-hierarchy.png" alt="Inventory Visibility allocation hierarchy." title="Hiérarchie de répartition Inventory Visibility" width="720" />](media/inventory-visibility-allocation-hierarchy.png)

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

La configuration de la fonctionnalité de répartition comporte trois étapes :

- Activez la fonctionnalité dans l’application Inventory Visibility en accédant à **Configuration \> Gestion des fonctionnalités et paramètres \>Répartition**.
- Configurez la [source de données](inventory-visibility-configuration.md#data-source-configuration) et ses [mesures](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- Configurez le nom et la hiérarchie du groupe d’allocation.

### <a name="predefined-data-source"></a>Source de données prédéfinies

Lorsque vous activez la fonctionnalité d’allocation et appelez l’API de mise à jour de configuration, Inventory Visibility crée une source de données prédéfinie et plusieurs mesures initiales.

La source de données est nommée `@iv`. Elle comprend un ensemble de mesures physiques par défaut. Vous pouvez les afficher à partir de l’application Inventory Visibility en accédant à **Configuration \> Source de données**. Vous devriez afficher **Datasource - @IV**. Développez la source de données `@iv` pour afficher la liste des mesures physiques initiales :

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Sélectionnez l’onglet **Mesures calculées** pour afficher la mesure calculée initiale nommée `@iv.@available_to_allocate` :

- `@iv`

    - `@iv.@available_to_allocate` = `??` – `??` – `@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>Ajouter d’autres mesures physiques à la mesure calculée disponible pour allocation

Pour utiliser la répartition, configurez correctement la formule de la mesure calculée disponible pour répartition (`@iv.@available_to_allocate`). Par exemple, vous avez la source de données `fno` et la mesure `onordered`, la source de données `pos` et la mesure `inbound`, et vous voulez faire une répartition sur le stock disponible pour la somme de `fno.onordered` et `pos.inbound`. Dans ce cas, `@iv.@available_to_allocate` doit contenir `pos.inbound` et `fno.onordered` dans la formule. Voici un exemple :

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

> [!NOTE]
> La source de données `@iv` est une source de données prédéfinie et les mesures physiques définies dans `@iv` avec préfixe `@` sont des mesures prédéfinies. Ces mesures sont une configuration prédéfinie pour la fonctionnalité de répartition, donc ne les modifiez pas ou ne les supprimez pas ou vous risquez de rencontrer des erreurs inattendues lors de l’utilisation de la fonctionnalité de répartition.
>
> Vous pouvez ajouter de nouvelles mesures physiques à la mesure calculée prédéfinie `@iv.@available_to_allocate`, mais vous ne devez pas modifier son nom.

### <a name="manage-allocation-groups"></a>Gérer les groupes de répartition

Un maximum de huit noms de groupe d’allocation peut être défini. Les groupes ont une hiérarchie. Pour afficher et mettre à jour les groupes de répartition, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Inventory Visibility**.
1. Ouvrez la page **Configuration**, puis, dans l’onglet **Répartition**, sélectionnez **Modifier la configuration**. Par défaut, il existe une hiérarchie de répartition à quatre couches : `Channel` (couche supérieure), `customerGroup` (deuxième couche), `Region` (troisième couche) et `OrderType` (quatrième couche).
1. Vous pouvez supprimer un groupe de répartition existant en sélectionnant le **X** en regard. Vous pouvez également ajouter de nouveaux groupes de répartition à la hiérarchie en saisissant le nom de chaque nouveau groupe directement dans le champ.

    > [!IMPORTANT]
    > Soyez prudent lorsque vous supprimez ou modifiez la mise en correspondance de la hiérarchie de répartition. Pour obtenir de l’aide, voir [Conseils d’utilisation de la répartition](#allocation-tips).

1. Lorsque vous avez terminé de configurer les paramètres de la hiérarchie et des groupes de répartition, enregistrez vos modifications, puis sélectionnez **Mettre à jour la configuration** en haut à droite. Les valeurs des groupes de répartition configurés sont mises à jour lorsque vous créez une allocation en utilisant soit l’interface utilisateur, soit l’API POST (/api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/allocate). Des détails sur les deux approches sont fournis plus loin dans cet article.

Si vous utilisez quatre noms de groupe et que vous les définissez sur \[`channel`, `customerGroup`, `region`, `orderType`\], ces noms sont valides pour les demandes liées à la répartition lorsque vous appelez l’API de mise à jour de la configuration.

### <a name="tips-for-using-allocation"></a><a name="allocation-tips"></a>Conseils d’utilisation de la répartition

- Pour chaque produit, la fonction de répartition doit utiliser le même *niveau de dimension* en fonction de la hiérarchie d’index de produits que vous avez définie dans la [configuration de la hiérarchie de l’index des produits](inventory-visibility-configuration.md#index-configuration). Par exemple, supposons que votre hiérarchie d’index est \[`Site`, `Location`, `Color`, `Size`\]. Si vous allouez une certaine quantité pour un produit au niveau de la dimension \[`Site`, `Location`, `Color`\], la prochaine fois que vous souhaitez allouer ce produit, vous devez également allouer au même niveau, \[`Site`, `Location`, `Color`\]. Si vous utilisez le niveau \[`Site`, `Location`, `Color`, `Size`\] ou \[`Site`, `Location`\], les données seront incohérentes.
- **Modification des groupes d’allocation et de la hiérarchie :** si les données de répartition existent déjà dans le système, la suppression des groupes de répartition existants ou un changement dans la hiérarchie des groupes de répartition endommage la mise en correspondance existante entre les groupes de répartition. Par conséquent, veillez à nettoyer manuellement toutes les anciennes données avant de mettre à jour la nouvelle configuration. Cependant, l’ajout de nouveaux groupes de répartition à la hiérarchie la plus basse n’affectant pas les mises en correspondance existantes, vous n’aurez pas besoin de nettoyer les données.
- La répartition ne réussit que si le produit a une quantité `available_to_allocate` positive.
- Pour allouer des produits d’un groupe de *niveau d’attribution* élevé à un sous-groupe, utilisez les API `Reallocate`. Par exemple, vous avez une hiérarchie de groupe d’allocation \[`channel`, `customerGroup`, `region`, `orderType`\], et vous souhaitez allouer un produit du groupe d’allocation \[En ligne, VIP\] au sous-groupe d’affectation \[En ligne, VIP, UE\], utilisez l’API `Reallocate` pour déplacer la quantité. Si vous utilisez l’API `Allocate`, elle allouera la quantité du pool commun virtuel.
- Pour afficher la disponibilité globale des produits (le pool commun), utilisez l’API [requête disponible](inventory-visibility-api.md#query-on-hand) pour demander le montant de l’inventaire *disponible pour répartition*. Vous pouvez ensuite prendre des décisions de répartition en fonction de ces informations.

## <a name="use-the-allocation-api"></a><a name="using-allocation-api"></a>Utiliser l’API de répartition

Actuellement, cinq API d’allocation sont ouvertes :

- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/allocate** – Cette API sert à créer la répartition initiale.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/unallocate** – Cette API sert à rétablir ou supprimer les quantités allouées.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/reallocate** – Cette API sert à déplacer la quantité allouée d’un emplacement existant vers les autres groupes de répartition.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/consume** – Cette API sert à déduire (utiliser) la quantité allouée.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/query** – Cette API sert à vérifier les enregistrements de répartition existants par rapport aux groupes de répartition et à la hiérarchie.

### <a name="allocate"></a>Allouer

Appelez l’API `Allocate` pour allouer un produit qui a des dimensions spécifiques. Voici le schéma du corps de la requête.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
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
    "id": "test101",
    "productId": "Bike",
    "groups": {
        "channel": "Web",
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

### <a name="unallocate"></a>Ne pas allouer

Utilisez l’API `Unallocate` pour inverser l’opération `Allocate`. La quantité négative n’est pas autorisée dans une opération `Allocate`. Le corps de `Unallocate` est identique au corps de `Allocate`.

### <a name="reallocate"></a>Réallouer

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
    "groups": {
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
    "id": "test102",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
    "groups": {
        "channel": "Web",
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

### <a name="consume"></a>Consommer

Utilisez l’API `Consume` pour valider la quantité consommée par rapport à l’allocation. Par exemple, vous pouvez utiliser cette API pour déplacer la quantité allouée vers certaines mesures réelles. Voici le schéma du corps de la requête.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
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
    "id": "test103",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Web",
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

Après cet appel, la quantité allouée pour le produit sera réduite de 3. De plus, la Inventory Visibility générera un événement de modification disponible où `pos.inbound` = *-3*. Alternativement, vous pouvez conserver la valeur `pos.inbound` telle quelle et consommez simplement la quantité allouée. Cependant, dans ce cas, vous devez soit créer une autre mesure physique pour conserver les quantités consommées, soit utiliser la mesure prédéfinie `@iv.@consumed`.

Dans cette requête, notez que la mesure physique que vous utilisez dans le corps de la demande de calcul doit utiliser le type de modificateur opposé (addition ou soustraction), par rapport au type de modificateur utilisé dans la mesure calculée. Ainsi, dans ce corps de consommation, `iv.inbound` a la valeur `Subtraction` et non pas `Addition`.

La source de données `fno` ne peut pas être utilisée dans le corps de consommation car nous avons toujours affirmé que la Inventory Visibility ne peut modifier aucune donnée pour la source de données `fno`. Le flux de données est unidirectionnel, ce qui signifie que toutes les quantités changent pour la source de données `fno` doit provenir de votre environnement Supply Chain Management.

### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a>Consommer en tant que réservation provisoire

L’API `Consume` peut également consommer la quantité allouée en tant que réservation provisoire. Dans ce cas, l’opération `Consume` réduira la quantité allouée, puis effectuera une réservation provisoire pour cette quantité. Pour utiliser cette approche, vous devez également utiliser la fonctionnalité [réservation provisoire](inventory-visibility-reservations.md) sous Inventory Visibility.

Par exemple, vous avez défini une mesure physique de réservation provisoire comme `iv.softreserved`. La formule suivante est utilisée pour la mesure calculée disponible à la réservation :

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
    "groups": {
        "channel": "Web",
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

### <a name="query"></a>Requête

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
        "channel": "Web",
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
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

## <a name="use-the-allocation-user-interface"></a>Utiliser l’interface utilisateur de répartition

Vous pouvez gérer manuellement les répartitions par l’interface utilisateur en ouvrant l’application Inventory Visibility et en accédant à **Visibilité opérationnelle \> Répartition**. À partir de là, vous pouvez effectuer toutes les actions décrites dans les sous-sections suivantes.

### <a name="create-an-allocation"></a>Créer une répartition

Suivez ces étapes pour créer une répartition à partir de la page **Répartition** de l’application Inventory Visibility.

1. Sélectionnez **Allouer**.
1. Définissez les champs de base, les dimensions et les valeurs des groupes de répartition cible. (Lorsque vous sélectionnez la source de données de collecte dans la section **Dimensions**, utilisez d’abord la liste déroulante pour spécifier les dimensions (par exemple, `siteId`). Entrez ensuite les valeurs de dimension dans les champs qui s’affichent.)
1. Sélectionnez **Envoyer**.

### <a name="consume-an-allocation"></a>Consommer une répartition

Sélectionnez **Consommer** pour consommer une répartition. Pour vous assurer que vous consommez dans le groupe de répartition et la hiérarchie appropriés, entrez les mêmes ensembles de détails d’organisation et de dimension que lors de la création de la répartition.

### <a name="reallocate-an-allocation"></a>Réallouer une répartition

Sélectionnez **Réallouer** pour déplacer la quantité allouée existante d’un ensemble de groupes de répartition vers un autre.

### <a name="query-existing-allocations"></a>Interroger les répartitions existantes

Sélectionnez **Interroger**, puis entrez les valeurs de produit, d’organisation, de dimension et de groupe de répartition pour obtenir les résultats de la requête des répartitions existantes.
