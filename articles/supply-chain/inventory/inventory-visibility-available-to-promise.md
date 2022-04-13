---
title: Plannings de changement du stock disponible et disponibilité à la vente de la Visibilité des stocks
description: Cette rubrique décrit comment planifier les futurs changements de stock disponible et calculer les quantités disponibles à la vente (DAV).
author: yufeihuang
ms.date: 03/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-04
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 7ce868871f093fd734a466bb8a06c5782bf83302
ms.sourcegitcommit: a3b121a8c8daa601021fee275d41a95325d12e7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8525882"
---
# <a name="inventory-visibility-on-hand-change-schedules-and-available-to-promise"></a>Plannings de changement du stock disponible et disponibilité à la vente de la Visibilité des stocks

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer la fonction *Planning de changement de stock disponible* pour planifier les futurs changements du stock disponible et calculer les quantités disponibles à la vente (DAV). Le DAV correspond à la quantité d’un article qui est disponible et peut être promise à un client dans le courant d’une période à venir. L’utilisation de ce calcul peut augmenter considérablement votre capacité de traitement des commandes.

Pour de nombreux fabricants, détaillants ou vendeurs, il ne suffit pas de savoir ce qui est actuellement disponible. Ils doivent avoir une visibilité totale de la disponibilité future. Cette disponibilité future doit tenir compte de l’offre future, de la demande future et de la DAV.

## <a name="enable-and-set-up-the-features"></a><a name="setup"></a>Activer et configurer les fonctionnalités

Avant de pouvoir utiliser la DAV, vous devez paramétrer une ou plusieurs mesures calculées pour calculer les quantités DAV. Vous devez également activer la fonction et configurer les paramètres DAV dans Microsoft Power Apps.

### <a name="set-up-calculated-measures-for-atp-quantities"></a>Configurer les mesures calculées pour les quantités DAV

La *Mesure DAV calculée* est une mesure calculée prédéfinie qui est généralement utilisée pour trouver la quantité actuellement disponible. La somme des quantités de ses modificateurs d’addition est la quantité d’offre et la somme des quantités de ses modificateurs de soustraction est la quantité de demande.

Vous pouvez ajouter plusieurs mesures calculées pour calculer les quantités DAV. Cependant, le nombre total des modificateurs pour toutes les mesures calculées de la DAV doit être inférieur à neuf.

Par exemple, vous pouvez définir la mesure calculée suivante :

**Disponible immédiatement** = (*StockPhysique* + *Disponible* + *Illimité* + *InspectionQualité* + *Entrant*) – (*RéservPhysique* + *RéservPhysiqueProv* + *Sortant*)

La somme (*StockPhysique* + *Disponible* + *Illimité* + *InspectionQualité* + *Entrant*) représente l’offre, et la somme (*RéservPhysique* + *RéservPhysiqueProv* + *Sortant*) représente la demande. Par conséquent, la mesure calculée peut être comprise de la manière suivante :

**Disponible immédiatement** = *Offre* – *Demande*

Pour plus d’informations sur les mesures calculées, voir [Mesures calculées](inventory-visibility-configuration.md#calculated-measures).

### <a name="turn-on-the-on-hand-change-schedule-feature-and-configure-atp-settings"></a>Activer la fonction de planification de changement de stock disponible et configurer les paramètres DAV

Suivez ces étapes pour activer la fonctionnalité *Planning de changement de stock disponible* dans Power Apps et configurer les paramètres DAV.

1. Connectez-vous à Power Apps et ouvrez Visibilité du stock.
1. Ouvrez la page **Configuration**.
1. Sur l’onglet **Gestion des fonctionnalités**, activez la fonctionnalité *OnhandChangeSchedule*.
1. Sélectionnez l’onglet **Paramètres DAV**.
1. Lorsque vous interrogez la visibilité du stock, elle renvoie un résultat qui inclut chaque mesure DAV calculée que vous ajoutez ici. Sélectionnez **Ajouter** pour ajouter une nouvelle mesure calculée pour la DAV.
1. Définissez les champs suivants :

    - **Source de données** – Sélectionnez la source de données associée à la mesure calculée.
    - **Mesure calculée** – Sélectionnez la mesure calculée qui est associée à la source de données sélectionnée et que vous souhaitez utiliser pour trouver la quantité en stock actuellement disponible.
    - **Période de planification** – Entrez le nombre de jours pendant lesquels les utilisateurs peuvent afficher et soumettre des changements planifiés de stock disponible lorsque la mesure calculée sélectionnée est utilisée. Les utilisateurs qui demandent des informations sur les stocks obtiendront le stock disponible, les changements planifiés du stock disponible et la DAV pour chaque jour de cette période, en commençant par la date actuelle. Sélectionnez un nombre entier entre 1 et 7.

    > [!IMPORTANT]
    > La période de planification inclut la date actuelle. Par conséquent, les utilisateurs peuvent programmer des changements de stock disponible pour qu’ils se produisent à tout moment entre la date du jour (le jour où le changement est soumis) et (période de planification - 1) jours dans le futur.

1. Cliquez sur **Enregistrer**.
1. Répétez les étapes 5 à 7 jusqu’à ce que vous ayez ajouté toutes les mesures calculées dont vous avez besoin pour la DAV.
1. Lorsque vous avez terminé de configurer tous les paramètres requis, sélectionnez **Mettre à jour la configuration**.

Pour plus d’informations, voir [Terminer et mettre à jour la configuration](inventory-visibility-configuration.md).

## <a name="how-the-on-hand-change-schedule-and-atp-calculations-work"></a>Fonctionnement des calculs du planning de changement du stock disponible et de la DAV

Un *Planning de changement du stock disponible* établit les dates et les quantités de changements de stock disponible prévues. Vous pouvez soumettre un planning de changement du stock disponible à la Visibilité du stock, à condition que les dates soient comprises dans la période définie par le paramètre **Période de planification** (voir la section [Activer et configurer les fonctionnalités](#setup)). Les utilisateurs qui demandent des informations sur les stocks obtiendront le stock disponible, les changements planifiés du stock disponible et la DAV pour chaque jour de cette période.

Les changements planifiés ne sont initialement pas validés et n’affectent donc pas les quantités réellement disponibles dans le système. Pour valider les changements, vous devez envoyer un *événement de changement du stock disponible*, qui met à jour la quantité réelle du stock disponible. Vous devez ensuite annuler le changement planifié en soumettant un planning de changement du stock disponible pour une quantité négative correspondante.

Par exemple, vous passez une commande de 10 vélos et vous vous attendez à ce qu’elle arrive demain. Par conséquent, vous soumettez un planning de changement du stock disponible qui a une quantité entrante de 10 et est daté de demain. Lorsque la commande arrive le lendemain, vous ajoutez les vélos à votre stock physique disponible. Vous devez ensuite valider la modification dans votre système pour mettre à jour la quantité en stock réelle. Pour valider la modification, vous soumettez un événement de changement du stock disponible dont la quantité entrante est de 10. Vous annulez ensuite le changement planifié en soumettant un programme de changement du stock disponible ayant une quantité entrante de -10.

Lorsque vous interrogez la Visibilité du stock pour connaître les quantités en stock et DAV, les informations suivantes sont renvoyées pour chaque jour de la période de planification :

- **Date** – La date à laquelle le résultat s’applique.
- **Quantité disponible immédiatement** – La quantité disponible réelle en stock pour la date spécifiée. Ce calcul est effectué en fonction de la mesure DAV calculée qui est configurée pour la Visibilité du stock.
- **Offre planifiée** – La somme de toutes les quantités entrantes planifiées qui ne sont pas devenues physiquement disponibles pour une consommation ou une expédition immédiate à la date spécifiée.
- **Demande planifiée** – La somme de toutes les quantités sortantes planifiées qui n’ont pas été consommées ou expédiées à la date spécifiée.
- **Quantité DAV** – La quantité minimale projetée de stock disponible qui est disponible à partir de la date spécifiée jusqu’à la fin de la période de planification. Cette quantité comprend tous les ajustements de quantité planifiés. C’est la quantité maximale qui peut être promise à la date du jour pour livraison ou consommation ce jour-là.

Par exemple, si la date actuelle est le 1er février 2022 et que la période de planification est 7, les utilisateurs peuvent soumettre des changements planifiés de stock disponible attendus entre le 1er février et le 7 février 2022. Dans ce cas, la quantité DAV pour le 3 février, par exemple, est calculée en fonction de la quantité en stock pour ce jour et des quantités planifiées du 3 février au 7 février.

## <a name="example"></a>Exemple

L’exemple suivant montre comment une série de changements planifiés de quantité affecte les quantités de stock disponible et DAV rapportées par la Visibilité du stock. Il montre également comment valider un changement planifié, comment un changement planifié validé affecte les résultats, et ce qui peut se produire si vous ne validez pas un changement planifié.

Les résultats de cet exemple montrent une valeur *stock disponible projeté*. Cette valeur intègre toutes les mises à jour planifiées à des fins d’illustration, mais n’est pas réellement rapportée lorsque vous interrogez la Visibilité du stock.

1. Les paramètres suivants sont configurés pour votre système sur la page **Paramètre DAV** dans Power Apps :

    - **Mesure DAV calculée** – Vous disposez d’une mesure calculée nommée *Stock disponible*. Il est calculé comme *Disponible = Offre – Demande*. Vous sélectionnez cette mesure ici.
    - **Période de planification** – Vous sélectionnez *7*.

1. Les conditions suivantes s’appliquent également :

    - La date actuelle est le 1er février 2022.
    - La quantité disponible actuelle est de 20.

1. Pour la date actuelle (1er février 2022), vous soumettez une quantité de demande planifiée de 3 à la Visibilité du stock. Par conséquent, la quantité disponible projetée est 17. Le tableau suivant présente le résultat.

    | Date | Disponible | Offre planifiée | Demande planifiée | Stock disponible projeté | DAV |
    | --- | --- | --- | --- | --- | --- |
    | 01/02/2022 | 20 | | 3 | 17 | 17 |
    | 02/02/2022 | 20 | | | 17 | 17 |
    | 03/02/2022 | 20 | | | 17 | 17 |
    | 04/02/2022 | 20 | | | 17 | 17 |
    | 05/02/2022 | 20 | | | 17 | 17 |
    | 06/02/2022 | 20 | | | 17 | 17 |
    | 07/02/2022 | 20 | | | 17 | 17 |

1. À la date actuelle (1er février 2022), vous soumettez une quantité d’approvisionnement planifié de 10 pour le 3 février 2022. Le tableau suivant présente le résultat.

    | Date | Disponible | Offre planifiée | Demande planifiée | Stock disponible projeté | DAV |
    | --- | --- | --- | --- | --- | --- |
    | 01/02/2022 | 20 | | 3 | 17 | 17 |
    | 02/02/2022 | 20 | | | 17 | 17 |
    | 03/02/2022 | 20 | 10 | | 27 | 27 |
    | 04/02/2022 | 20 | | | 27 | 27 |
    | 05/02/2022 | 20 | | | 27 | 27 |
    | 06/02/2022 | 20 | | | 27 | 27 |
    | 07/02/2022 | 20 | | | 27 | 27 |

1. À la date actuelle (1er février 2022), vous soumettez les changements de quantité planifiés suivants :

    - Quantité demandée de 15 pour le 4 février 2022
    - Quantité fournie de 1 pour le 5 février 2022
    - Quantité demandée de 3 pour le 6 février 2022

    Le tableau suivant présente le résultat.

    | Date | Disponible | Offre planifiée | Demande planifiée | Stock disponible projeté | DAV |
    | --- | --- | --- | --- | --- | --- |
    | 01/02/2022 | 20 | | 3 | 17 | 12 |
    | 02/02/2022 | 20 | | | 17 | 12 |
    | 03/02/2022 | 20 | 10 | | 27 | 12 |
    | 04/02/2022 | 20 | | 15 | 12 | 12 |
    | 05/02/2022 | 20 | 1 | | 13 | 13 |
    | 06/02/2022 | 20 | 3 | | 16 | 16 |
    | 07/02/2022 | 20 | | | 16 | 16 |

1. À la date actuelle (1er février 2022), vous expédiez la quantité demandée planifiée de 3. Par conséquent, vous devez valider ce changement afin qu’il se reflète dans votre quantité en stock réelle. Pour valider le changement, vous soumettez un événement de changement du stock disponible dont la quantité sortante est de 3. Vous annulez ensuite le changement planifié en soumettant un programme de changement du stock disponible ayant une quantité sortante de -3. Le tableau suivant présente le résultat.

    | Date | Disponible | Offre planifiée | Demande planifiée | Stock disponible projeté | DAV |
    | --- | --- | --- | --- | --- | --- |
    | 01/02/2022 | 17 | | 0 | 17 | 12 |
    | 02/02/2022 | 17 | | | 17 | 12 |
    | 03/02/2022 | 17 | 10 | | 27 | 12 |
    | 04/02/2022 | 17 | | 15 | 12 | 12 |
    | 05/02/2022 | 17 | 1 | | 13 | 13 |
    | 06/02/2022 | 17 | 3 | | 16 | 16 |
    | 07/02/2022 | 17 | | | 16 | 16 |

1. Le jour suivant (2 février 2022), la période de planification avance d’un jour. Le tableau suivant présente le résultat.

    | Date | Disponible | Offre planifiée | Demande planifiée | Stock disponible projeté | DAV |
    | --- | --- | --- | --- | --- | --- |
    | 02/02/2022 | 17 | | | 17 | 12 |
    | 03/02/2022 | 17 | 10 | | 27 | 12 |
    | 04/02/2022 | 17 | | 15 | 12 | 12 |
    | 05/02/2022 | 17 | 1 | | 13 | 13 |
    | 06/02/2022 | 17 | 3 | | 16 | 16 |
    | 07/02/2022 | 17 | | | 16 | 16 |
    | 08/02/2022 | 17 | | | 16 | 16 |

1. Cependant, deux jours plus tard (le 4 février 2022), la quantité d’approvisionnement de 10 qui était prévue pour le 3 février n’est toujours pas arrivée. Le tableau suivant présente le résultat.

    | Date | Disponible | Offre planifiée | Demande planifiée | Stock disponible projeté | DAV |
    | --- | --- | --- | --- | --- | --- |
    | 04/02/2022 | 17 | | 15 | 2 | 2 |
    | 05/02/2022 | 17 | 1 | | 3 | 3 |
    | 06/02/2022 | 17 | 3 | | 6 | 6 |
    | 07/02/2022 | 17 | | | 6 | 6 |
    | 08/02/2022 | 17 | | | 6 | 6 |
    | 09/02/2022 | 17 | | | 6 | 6 |
    | 10/02/2022 | 17 | | | 6 | 6 |

    Comme vous le voyez, les changements planifiés (mais non validés) du stock disponible n’affectent pas la quantité de stock disponible réelle.

## <a name="submit-change-schedules-change-events-and-atp-queries-through-the-api"></a><a name="api-urls"></a>Soumettre des plannings de changement, des événements de changement et des requêtes DAV via l’API

Vous pouvez utiliser les URL d’interface de programmation d’application (API) suivantes pour soumettre des plannings de changement du stock disponible, des événements de changement et des requêtes.

| Chemin d’accès | méthode | Description |
| --- | --- | --- |
| `/api/environment/{environmentId}/on-hand/changeschedule` | `POST` | Créer un changement planifié du stock disponible. |
| `/api/environment/{environmentId}/on-hand/changeschedule/bulk` | `POST` | Créer plusieurs changements planifiés du stock disponible. |
| `/api/environment/{environmentId}/onhand` | `POST` | Créer un événement de changement de stock disponible. |
| `/api/environment/{environmentId}/onhand/bulk` | `POST` | Créer plusieurs événements de changement. |
| `/api/environment/{environmentId}/onhand/indexquery` | `POST` | Requête à l’aide de la méthode `POST`. |
| `/api/environment/{environmentId}/onhand` | `GET` | Requête à l’aide de la méthode `GET`. |

Pour plus d’informations, voir [API publiques de la Visibilité des stocks](inventory-visibility-api.md).

### <a name="submit-on-hand-change-schedules"></a>Soumettre les plannings de changement du stock disponible

Les plannings de changement du stock disponible sont effectués en soumettant une requête `POST` à l’URL du service Visibilité du stock concerné (voir la section [Soumettre des plannings de changement, des événements de changement et des requêtes DAV via l’API](#api-urls)). Vous pouvez également soumettre des requêtes en masse.

Pour soumettre un planning de changement de stock disponible, le corps de la requête doit contenir un ID d’organisation, un ID de produit, une date planifiée et des quantités par date. La date planifiée doit être comprise entre la date actuelle et la fin de la période de planification actuelle.

#### <a name="example-request-body-that-contains-a-single-update"></a>Exemple de corps de requête contenant une seule mise à jour

L’exemple suivant présente un corps de requête contenant une seule mise à jour.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/on-hand/changeschedule

# Method
Post

# Header
# Replace {access_token} with the one from your security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId": "Small"
    },
    "quantitiesByDate":
    {
        "2022/02/01": // today
        {
            "pos":{
                "inbound": 10,
            },
        },
    },
}
```

#### <a name="example-request-body-that-contains-multiple-bulk-updates"></a>Exemple de corps de requête contenant plusieurs mises à jour (en masse)

L’exemple suivant présente un corps de requête contenant plusieurs mises à jour (en masse).

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/on-hand/changeschedule/bulk

# Method
Post

# Header
# replace {access_token} with the one from your security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

[
    {
        "id": "id-bike-0001",
        "organizationId": "usmf",
        "productId": "Bike",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId": "Small"
        },
        "quantitiesByDate":
        {
            "2022/02/01": // today
            {
                "pos":{
                    "inbound": 10,
                },
            },
        },
    },
    {
        "id": "id-bike-0002",
        "organizationId": "usmf",
        "productId": "Car",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId": "Small"
        },
        "quantitiesByDate":
        {
            "2022/02/05":
            {
                "pos":{
                    "outbound": 10,
                },
            },
        },
    }
]
```

### <a name="submit-on-hand-change-events"></a>Soumettre des événements de changement de stock disponible

Les événements de changement du stock disponible sont effectués en soumettant une requête `POST` à l’URL du service Visibilité du stock concerné (voir la section [Soumettre des plannings de changement, des événements de changement et des requêtes DAV via l’API](#api-urls)). Vous pouvez également soumettre des requêtes en masse.

> [!NOTE]
> Les événements de changement du stock disponibles ne sont pas propres à la fonctionnalité DAV, mais font partie de l’API Visibilité du stock standard. Cet exemple a été inclus car les événements sont pertinents lorsque vous travaillez avec la DAV. Les événements de changement du stock disponible ressemblent aux réservations de changement du stock disponible, mais les messages d’événement doivent être envoyés à une URL d’API différente, et les événements utilisent `quantities` au lieu de `quantityByDate` dans le corps du message. Pour plus d’informations sur les événements de changement du stock disponible et d’autres fonctionnalités de l’API Visibilité du stock, consultez [API publiques de visibilité du stock](inventory-visibility-api.md).

Pour soumettre un événement de changement de stock disponible, le corps de la requête doit contenir un ID d’organisation, un ID de produit, une date planifiée et des quantités par date. La date planifiée doit être comprise entre la date actuelle et la fin de la période de planification actuelle.

L’exemple suivant présente un corps de requête contenant un seul événement de changement du stock disponible.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# Replace {access_token} with the one from your security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "SizeId": "Big",
        "ColorId": "Red",
    },
    "quantities": {
        "pos": {
            "inbound": 10.0
        }
    }
}
```

## <a name="query-the-scheduled-on-hand-changes-and-atp-results"></a>Interroger les changements planifiés du stock disponible et les résultats de la DAV

Vous pouvez interroger les changements planifiés du stock disponible et les résultats de la DAV en soumettant soit une requête `POST` ou une requête `GET` à l’URL de l’API appropriée (voir la section [oumettre des plannings de changement, des événements de changement et des requêtes DAV via l’API](#api-urls)).

Dans votre requête, définissez `QueryATP` sur *true* si vous souhaitez interroger les changements planifiés du stock disponible et les résultats de la DAV.

- Si vous soumettez la requête en utilisant la méthode `GET`, définissez ce paramètre dans l’URL.
- Si vous soumettez la requête en utilisant la méthode `POST`, définissez ce paramètre dans le corps de la requête.

> [!NOTE]
> Indépendamment du fait que le paramètre `returnNegative` est défini sur *true* ou *false* dans le corps de la requête, le résultat inclura des valeurs négatives lorsque vous interrogerez les changements planifiés du stock disponible et les résultats de la DAV. Ces valeurs négatives seront incluses car, si seules les commandes de demande sont planifiées, ou si les quantités d’approvisionnement sont inférieures aux quantités demandées, les quantités du changement planifié du stock disponible seront négatives. Si les valeurs négatives n’étaient pas incluses, les résultats seraient déroutants. Pour plus d’informations sur cette option et son fonctionnement pour d’autres types de requêtes, voir [API publiques de visibilité du stock](inventory-visibility-api.md).

### <a name="post-method-example"></a>Exemple de méthode POST

L’exemple suivant montre comment créer un corps de requête pouvant être soumis à la Visibilité du stock à l’aide de la méthode `POST`.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/on-hand/indexquery

# Method
Post

# Header
# replace {access_token} with the one from your security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["Bike"],
        "siteId": ["1"],
        "LocationId": ["11"],
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true,
    "QueryATP":true,
}
```

### <a name="get-method-example"></a>Exemple de méthode GET

L’exemple suivant montre comment créer une URL de requête sous forme de requête `GET`.

```txt
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand?organizationId=usmf&productId=Bike&SiteId=1&groupBy=ColorId,SizeId&returnNegative=true&QueryATP=true
```

Le résultat de cette requête `GET` est exactement le même que le résultat de la requête `POST` dans l’exemple précédent.

### <a name="query-result-example"></a>Exemple de résultat de requête

Les deux exemples de requête précédents peuvent produire la réponse suivante. Pour cet exemple, le système est configuré avec les paramètres suivants :

- **Mesure DAV calculée :** *iv.onhand = pos.inbound – pos.outbound*
- **Période planifiée :** *7*

Voici un exemple du corps de la réponse.

```json
[
    {
        "quantitiesByDate": {
            "2022-02-02T00:00:00": {
                "pos": {
                    "outbound": 5,
                    "inbound": 0,
                },
                "iv": {
                    "onhand": -5,
                },
            },
            "2022-02-06T00:00:00": {
                "pos": {
                    "inbound": 7,
                    "outbound": 0,
                },
                "iv": {
                    "onhand": 7,
                },
            }
        },
        "atpQuantities": {
            "2022-02-01T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-02T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-03T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-04T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-05T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-06T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            },
            "2022-02-07T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            }
        },
        "productId": "Bike ",
        "dimensions": {
            "ColorId": "Red",
            "SizeId": "Big",
            "siteid": "1",
            "locationid": "11"
        },
        "quantities": {
            "pos": {
                "inbound": 10.0,
                "outbound": 0,
            },
            "iv": {
                "onhand": 10.0,
            }
        }
    }
]
```
