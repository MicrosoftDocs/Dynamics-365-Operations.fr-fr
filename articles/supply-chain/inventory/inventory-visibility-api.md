---
title: API publiques Inventory Visibility
description: Cet article décrit les API publiques fournies par la visibilité des stocks.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 8b0b8ca261237fbb2190f2a94cc11b816ae05af5
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762832"
---
# <a name="inventory-visibility-public-apis"></a>API publiques Inventory Visibility

[!include [banner](../includes/banner.md)]

Cet article décrit les API publiques fournies par la visibilité des stocks.

L’API REST publique du complément de visibilité des stocks présente plusieurs points de terminaison d’intégration spécifiques. Elle prend en charge quatre types d’interactions :

- Publication des modifications de stock disponibles du complément à partir d’un système externe
- Définition ou remplacement des quantités de stock disponible dans le complément à partir d’un système externe
- Publication des événements de réservation dans le complément à partir d’un système externe
- Interrogation des quantités en stock actuelles à partir d’un système externe

Le tableau suivant répertorie les API actuellement disponibles :

| Chemin d’accès | méthode | Description |
|---|---|---|
| /api/environment/{environmentId}/onhand | Valider | [Créer un événement de modification de stock disponible](#create-one-onhand-change-event)|
| /api/environment/{environmentId}/onhand/bulk | Valider | [Créer plusieurs événements de modification](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | Valider | [Définir/remplacer les quantités de stock disponible](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | Valider | [Créer un événement de réservation provisoire](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | Valider | [Créer plusieurs événements de réservation provisoire](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/unreserve | Valider | [Rétablir un événement de réservation provisoire](#reverse-one-reservation-event) |
| /api/environment/{environmentId}/onhand/unreserve/bulk | Valider | [Rétablir plusieurs événements de réservation provisoire](#reverse-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/changeschedule | Valider | [Créer un changement planifié du stock disponible](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/changeschedule/bulk | Valider | [Créer plusieurs changements disponibles avec dates](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/indexquery | Valider | [Interroger en utilisant la méthode de validation](#query-with-post-method) (recommandé) |
| /api/environment/{environmentId}/onhand | Obtenir | [Interroger en utilisant la méthode get](#query-with-get-method) |
| /api/environment/{environmentId}/onhand/exactquery | Valider | [Interroger avec exactitude en utilisant la méthode post](#exact-query-with-post-method) |
| /api/environment/{environmentId}/allocation<wbr>/allocate | Valider | [Créer un événement d’affectation](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/unallocate | Valider | [Créer un événement de non affectation](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/reallocate | Valider | [Créer un événement de réaffectation](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/consume | Valider | [Créer un événement de consommation](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/query | Valider | [Résultat d’allocation de requête](inventory-visibility-allocation.md#using-allocation-api) |

> [!NOTE]
> La partie {environmentId} du chemin d’accès est l’ID d’environnement dans Microsoft Dynamics Lifecycle Services.
> 
> L’API en masse peut renvoyer un maximum de 512 enregistrements pour chaque requête.

Microsoft a fourni une collection de requêtes *Postman* prêtes à l’emploi. Vous pouvez importer cette collection dans votre logiciel *Postman* en utilisant le lien partagé suivant : <https://www.getpostman.com/collections/95a57891aff1c5f2a7c2>.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a><a name = "endpoint-lcs"></a>Rechercher le point de terminaison en fonction de votre environnement Lifecycle Services

Le microservice de visibilité des stocks est déployé sur Microsoft Azure Service Fabric, dans plusieurs zones géographiques et plusieurs régions. Il n’existe actuellement aucun point de terminaison central qui puisse rediriger automatiquement votre requête vers la zone géographique et la région correspondantes. Par conséquent, vous devez composer les informations dans une URL en utilisant le modèle suivant :

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

Le nom abrégé de la région se trouve dans l’environnement Lifecycle Services. Le tableau suivant répertorie les régions actuellement disponibles.

| Région Azure        | Nom abrégé de la région |
| ------------------- | ----------------- |
| Est de l’Australie      | eau               |
| Sud-est de l’Australie | seau              |
| Centre du Canada      | cca               |
| Canada Est         | eca               |
| Nord de l’Europe        | neu               |
| Ouest de l’Europe         | weu               |
| Est des États-Unis             | eus               |
| Ouest des États-Unis             | wus               |
| Royaume-Uni Sud            | suk               |
| Royaume-Uni Ouest             | wuk               |
| Japon Est          | ejp               |
| Japon Ouest          | wjp               |
| Centre de l’Inde       | cin               |
| Sud de l’Inde         | sin               |
| Suisse Nord   | nch               |
| Suisse Ouest    | wch               |
| France Sud        | sfr               |
| Est de l’Asie           | eas               |
| Asie Sud-Est     | seas              |
| Émirats arabes unis Nord           | nae               |
| Norvège Est         | eno               |
| Norvège Ouest         | wno               |
| Afrique du Sud Ouest   | wza               |
| Afrique du Sud Nord  | nza               |

Le numéro d’île est l’endroit où votre environnement Lifecycle Services est déployé sur Service Fabric. Il n’y a actuellement aucun moyen d’obtenir ces informations du côté de l’utilisateur.

Microsoft a construit une interface utilisateur (IU) dans Power Apps afin que vous puissiez obtenir le point de terminaison complet du microservice. Pour plus d’informations, voir [Rechercher le point de terminaison de service](inventory-visibility-configuration.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Authentification

Le jeton de sécurité de la plateforme est utilisé pour appeler l’API publique de visibilité des stocks. Par conséquent, vous devez générer un jeton *Azure Active Directory (Azure AD)* en utilisant votre application Azure AD. Vous devez ensuite utiliser le jeton Azure AD pour obtenir le *jeton d’accès* du service de sécurité.

Microsoft fournit une collection de jetons d’obtention *Postman* prête à l’emploi. Vous pouvez importer cette collection dans votre logiciel *Postman* en utilisant le lien partagé suivant : <https://www.getpostman.com/collections/496645018f96b3f0455e>.

Pour obtenir un jeton de service de sécurité, procédez comme suit.

1. Connectez-vous au portail Azure et utilisez-le pour trouver les valeurs `clientId` et `clientSecret` pour votre application Dynamics 365 Supply Chain Management.
1. Récupérez un jeton Azure AD (`aadToken`) en envoyant une requête HTTP avec les propriétés suivantes :

    - **URL :** `https://login.microsoftonline.com/${aadTenantId}/oauth2/v2.0/token`
    - **Méthode :** `GET`
    - **Contenu du corps (données du formulaire) :**

        | Clé           | Valeur                                            |
        | ------------- | -------------------------------------------------|
        | client_id     | ${aadAppId}                                      |
        | client_secret | ${aadAppSecret}                                  |
        | grant_type    | client_credentials                               |
        | étendue         | 0cdb527f-a8d1-4bf8-9436-b352c68682b2/ par défaut    |

    Vous devriez recevoir un jeton Azure AD (`aadToken`) en réponse. Elle doit ressembler à l’exemple ci-dessous.

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "access_token": "eyJ0eX...8WQ"
    }
    ```

1. Formulez une requête JavaScript Object Notation (JSON) qui ressemble à l’exemple suivant.

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type": "aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope": "https://inventoryservice.operations365.dynamics.com/.default",
        "context": "{$LCS_environment_id}",
        "context_type": "finops-env"
    }
    ```

    Notez les points suivants :

    - La valeur `client_assertion` doit être le jeton Azure AD (`aadToken`) que vous avez reçu à l’étape précédente.
    - La valeur `context` doit être l’ID d’environnement Lifecycle Services dans lequel vous souhaitez déployer le complément.
    - Définissez toutes les autres valeurs comme indiqué dans l’exemple.

1. Récupérez un jeton d’accès (`access_token`) en envoyant une requête HTTP avec les propriétés suivantes :

    - **URL :** `https://securityservice.operations365.dynamics.com/token`
    - **Méthode :** `POST`
    - **En-tête HTTP :** incluez la version de l’API. (La clé est `Api-Version` et la valeur est `1.0` .)
    - **Contenu du corps :** incluez la requête JSON que vous avez créée à l’étape précédente.

    Vous devriez recevoir un jeton (`access_token`) en réponse. Vous devez utiliser ce jeton comme jeton du porteur pour appeler l’API de visibilité des stocks. Voici un exemple.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 3600
    }
    ```

> [!IMPORTANT]
> Lorsque vous utilisez la demande de collecte *Postman* pour appeler les API publiques Inventory Visibility, vous devez ajouter un jeton de support pour chaque demande. Pour trouver votre jeton au porteur, sélectionnez l’onglet **Autorisation** sous l’URL de la demande, sélectionnez le type **Jeton du porteur**, tapez et copiez le jeton d’accès qui a été récupéré à la dernière étape. Dans les sections suivantes de cet article, `$access_token` sera utilisé pour représenter le jeton qui a été récupéré à la dernière étape.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>Créer des événements de modification de stock disponible

Il existe deux API pour créer des événements de modification de stock disponible :

- Créer un enregistrement : `/api/environment/{environmentId}/onhand`
- Créer plusieurs enregistrements : `/api/environment/{environmentId}/onhand/bulk`

Le tableau suivant récapitule la signification de chaque champ dans le corps JSON.

| ID champ | Description |
|---|---|
| `id` | Un ID unique pour l’événement de modification spécifique. En cas de nouvelle soumission suite à ce dysfonctionnement de service, cet ID est utilisé pour garantir que le même événement ne sera pas compté deux fois dans le système. |
| `organizationId` | L’identificateur de l’organisation liée à l’événement. Cette valeur est mappée à un ID d’organisation ou de zone de données dans Supply Chain Management. |
| `productId` | Identificateur du produit. |
| `quantities` | Quantité selon laquelle la quantité disponible doit être modifiée. Par exemple, si 10 nouveaux livres sont ajoutés dans un rayon, cette valeur sera `quantities:{ shelf:{ received: 10 }}`. Si trois livres sont retirés du rayon ou vendus, cette valeur sera `quantities:{ shelf:{ sold: 3 }}`. |
| `dimensionDataSource` | Source de données des dimensions utilisées dans l’événement et la requête de modification de publication. Si vous spécifiez la source de données, vous pouvez utiliser les dimensions personnalisées de la source de données spécifiée. La visibilité des stocks peut utiliser la configuration des dimensions pour mapper les dimensions personnalisées aux dimensions générales par défaut. Si aucune valeur `dimensionDataSource` n’est spécifiée, vous ne pouvez n’utiliser que les [dimensions de base](inventory-visibility-configuration.md#data-source-configuration-dimension) générales dans vos requêtes. |
| `dimensions` | Paire clé-valeur dynamique. Les valeurs sont mappées à certaines des dimensions dans Supply Chain Management. Cependant, vous pouvez également ajouter des dimensions personnalisées (par exemple, *Source*) pour indiquer si l’événement provient de Supply Chain Management ou d’un système externe. |

> [!NOTE]
> Les paramètres `siteId` et `locationId` construisent la [configuration de la partition](inventory-visibility-configuration.md#partition-configuration). Par conséquent, vous devez les spécifier dans les dimensions lorsque vous créez des événements de modification de stock disponible, définissez ou remplacez des quantités en stock ou créez des événements de réservation.

Les sous-sections suivantes fournissent des exemples qui montrent comment utiliser ces API.

### <a name="create-one-on-hand-change-event"></a><a name="create-one-onhand-change-event"></a>Créer un événement de modification de stock disponible

Cette API crée un seul événement de modification de stock disponible.

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string, # Optional
        dimensions: {
            [key:string]: string,
        },
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
    }
```

L’exemple suivant montre un exemple de contenu du corps. Dans cet exemple, l’entreprise dispose d’un système de point de vente (PDV) qui traite les transactions en magasin et donc les changements de stock. Le client a retourné un t-shirt rouge dans votre magasin. Pour refléter ce changement, vous valisez un seul événement de modification pour le produit *T-shirt*. Cet événement augmentera la quantité du produit *T-shirt* de 1.

```json
{
    "id": "Test201",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "posMachineId": "0001",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

L’exemple suivant montre un exemple de contenu du corps sans `dimensionDataSource`. Dans ce cas, `dimensions` correspondra aux [dimensions de base](inventory-visibility-configuration.md#data-source-configuration-dimension). Si `dimensionDataSource` est défini, `dimensions` peut être soit les dimensions de la source de données, soit les dimensions de base.

```json
{
    "id": "Test202",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Créer plusieurs événements de modification

Cette API peut créer des événements de modification comme l’[API d’événement unique](#create-one-onhand-change-event) le peut. La seule différence est que cette API peut créer plusieurs enregistrements en même temps. Par conséquent, les valeurs `Path` et `Body` diffèrent. Pour cette API, `Body` fournit un tableau d’enregistrements. Le nombre maximal d’enregistrements est de 512. Ainsi, l’API en bloc des modifications disponibles peut prendre en charge jusqu’à 512 événements de modification à la fois. 

Par exemple, un terminal de point de vente d’un magasin de détail a traité les deux transactions suivantes :

- Une commande de retour d’un t-shirt rouge
- Une transaction de vente de trois t-shirts noirs

Dans ce cas, vous pouvez inclure les deux mises à jour de stock dans un seul appel d’API.

```txt
Path:
    /api/environment/{environmentId}/onhand/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
        },
        ...
    ]
```

L’exemple suivant montre un exemple de contenu du corps.

```json
[
    {
        "id": "Test203",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "SiteId": "Site1",
            "LocationId": "11",
            "posMachineId&quot;: &quot;0001"
            "colorId&quot;: &quot;red"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "Test204",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensions": {
            "siteId": "1",
            "locationId": "11",
            "colorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>Définir/remplacer les quantités de stock disponible

L’API *Set on-hand* remplace les données actuelles pour le produit spécifié. Cette fonctionnalité est généralement utilisée pour mettre à jour les comptages de stock. Par exemple, lors de son comptage quotidien de stock, un magasin peut constater que le stock réel disponible pour un t-shirt rouge est de 100. Ainsi, la quantité entrante du PDV doit être mise à jour sur 100, quelle que soit la quantité précédente. Vous pouvez utiliser cette API pour remplacer la valeur existante.

```txt
Path:
    /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifiedDateTimeUTC: datetime,
        },
        ...
    ]
```

L’exemple suivant montre un exemple de contenu du corps. Le comportement de cette API diffère du comportement des API décrites dans la section [Créer des événements de modification de stock disponible](#create-onhand-change-event) plus haut dans cet article. Dans cet exemple, la quantité du produit *T-shirt* sera définie sur 1.

```json
[
    {
        "id": "Test204",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "posMachineId": "0001"
            "colorId": "red"
        },
        "quantities": {
            "pos": {
                "inbound": 100
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>Créer des événements de réservation

Pour utiliser l’API *Reserve*, vous devez activer la fonctionnalité de réservation et compléter la configuration de la réservation. Pour plus d’informations (dont un exemple de flux de données et un exemple de scénario), voir [Configuration de la réservation (facultatif)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Créer un événement de réservation

Une réservation peut être effectuée pour différents paramètres de source de données. Pour configurer ce type de réservation, indiquez d’abord la source de données dans le paramètre `dimensionDataSource`. Ensuite, dans le paramètre `dimensions`, spécifiez les dimensions en fonction des paramètres de dimension dans la source de données cible.

Lorsque vous appelez l’API de réservation, vous pouvez contrôler la validation de la réservation en spécifiant le paramètre booléen `ifCheckAvailForReserv` dans le corps de la requête. Une valeur `True` signifie que la validation est requise, alors qu’une valeur `False` signifie que la validation n’est pas requise. La valeur par défaut est `True`.

Si vous souhaitez créer une réservation ou annuler la réservation de quantités de stock spécifiées, définissez la quantité sur une valeur négative et définissez le paramètre `ifCheckAvailForReserv` sur `False` pour ignorer la validation. Il existe également une API d’annulation dédiée pour faire de même. La différence réside uniquement dans la manière dont les deux API sont appelées. Il est plus facile d’annuler un événement de réservation spécifique en utilisant `reservationId` avec l’API *annuler la réservation*. Pour plus d’informations, voir la section [Annuler un événement de réservation](#reverse-reservation-events).

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string,
        dimensions: {
            [key:string]: string,
        },
        quantityDataSource: string, # optional
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
        modifier: string,
        quantity: number,
        ifCheckAvailForReserv: boolean,
    }
```

L’exemple suivant montre un exemple de contenu du corps.

```json
{
    "id": "reserve-0",
    "organizationId": "SCM_IV",
    "productId": "iv_postman_product",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softReservOrdered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "siteId": "iv_postman_site",
        "locationId": "iv_postman_location",
        "colorId": "red",
        "sizeId&quot;: &quot;small"
    }
}
```

L’exemple suivant montre une réponse réussie.

```json
{
    "reservationId": "RESERVATION_ID",
    "id": "ohre~id-822-232959-524",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
``` 

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Créer plusieurs événements de réservation

Cette API est une version en bloc de l’[API d’événement unique](#create-reservation-events).

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string,
            dimensions: {
                [key:string]: string,
            },
            quantityDataSource: string, # optional
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifier: string,
            quantity: number,
            ifCheckAvailForReserv: boolean,
        },
        ...
    ]
```

## <a name="reverse-reservation-events"></a>Annuler des événements de réservation

L’API *Annuler la réservation* sert d’opération d’annulation pour les événements de [*réservation*](#create-reservation-events). Elle fournit un moyen d’annuler un événement de réservation spécifié par `reservationId` ou pour diminuer la quantité de réservation.

### <a name="reverse-one-reservation-event"></a><a name="reverse-one-reservation-event"></a>Annuler un événement de réservation

Lorsqu’une réservation est créée, un `reservationId` est inclus dans le corps de la réponse. Vous devez fournir le même `reservationId` pour annuler la réservation, et inclure le même `organizationId` et les `dimensions` utilisés pour l’appel de l’API de réservation. Enfin, spécifiez une valeur `OffsetQty` qui représente le nombre d’éléments à libérer de la réservation précédente. Une réservation peut être entièrement ou partiellement annulée en fonction de la condition `OffsetQty` spécifiée. Par exemple, si *100* unités d’éléments ont été réservées, vous pouvez spécifier `OffsetQty: 10` pour annuler la réservation *10* du montant initialement réservé.

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        reservationId: string,
        dimensions: {
            [key:string]: string,
        },
        OffsetQty: number
    }
```

Le code suivant montre un exemple de contenu du corps.

```json
{
    "id": "unreserve-0",
    "organizationId": "SCM_IV",
    "reservationId": "RESERVATION_ID",
    "dimensions": {
        "siteid":"iv_postman_site",
        "locationid":"iv_postman_location",
        "ColorId": "red",
        "SizeId&quot;: &quot;small"
    },
    "OffsetQty": 1
}
```

Le code suivant montre un exemple de corps de réponse réussie.

```json
{
    "reservationId": "RESERVATION_ID",
    "totalInvalidOffsetQtyByReservId": 0,
    "id": "ohoe~id-823-11744-883",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
```

> [!NOTE]
> Dans le corps de la réponse, lorsque `OffsetQty` est inférieur ou égal à la quantité réservée, `processingStatus` est « *Succès* » et `totalInvalidOffsetQtyByReservId` est *0*.
>
> Si la condition `OffsetQty` est supérieure au montant réservé, `processingStatus` est « *partialSuccess* » et `totalInvalidOffsetQtyByReservId` est la différence entre `OffsetQty` et le montant réservé.
>
>Par exemple, si la réservation a une quantité de *10*, et `OffsetQty` a une valeur de *12*, `totalInvalidOffsetQtyByReservId` est *2*.

### <a name="reverse-multiple-reservation-events"></a><a name="reverse-multiple-reservation-events"></a>Annuler plusieurs événements de réservation

Cette API est une version en bloc de l’[API d’événement unique](#reverse-one-reservation-event).

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [      
        {
            id: string,
            organizationId: string,
            reservationId: string,
            dimensions: {
                [key:string]: string,
            },
            OffsetQty: number
        }
        ...
    ]
```

## <a name="query-on-hand"></a>Interroger le stock disponible

Utilisez l’API *Query on-hand* pour récupérer les données de stock disponible actuelles pour vos produits. Vous pouvez utiliser cette API chaque fois que vous devez connaître le stock, par exemple pour consulter les niveaux de stock des produits sur votre site Web d’e-commerce ou pour vérifier la disponibilité des produits dans les régions ou dans les magasins et entrepôts à proximité. L’API prend actuellement en charge l’interrogation de jusqu’à 5000 éléments individuels par valeur `productID`. Plusieurs valeurs `siteID` et `locationID` peuvent également être spécifiées dans chaque requête. La limite maximale est définie par l’équation suivante :

*NumOf(SiteID) \* NumOf(LocationID) <= 100*.

### <a name="query-by-using-the-post-method"></a><a name="query-with-post-method"></a>Interroger en utilisant la méthode post

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            siteId: string[],
            locationId: string[],
            [dimensionKey:string]: string[],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

Dans le corps de cette requête, `dimensionDataSource` est toujours un paramètre facultatif. S’il n’est pas défini, `filters` sera traité comme *dimensions de base*. Il y a quatre champs obligatoires pour `filters` : `organizationId`, `productId`, `siteId` et `locationId`.

- `organizationId` ne doit contenir qu’une seule valeur, mais c’est tout de même un tableau.
- `productId` peut contenir une ou plusieurs valeurs. Si c’est un tableau vide, tous les produits seront renvoyés.
- `siteId` et `locationId` sont utilisés pour le partitionnement pour la visibilité du stock. Vous pouvez spécifier plusieurs valeurs `siteId` et `locationId` dans une requête *Requête en main*. Dans la version actuelle, vous devez spécifier à la fois les valeurs `siteId` et `locationId`.

Nous vous suggérons d’utiliser le paramètre `groupByValues` pour suivre votre configuration pour l’indexation. Pour plus d’informations, voir [Configuration de la hiérarchie d’index des produits](./inventory-visibility-configuration.md#index-configuration).

Le paramètre `returnNegative` contrôle si les résultats contiennent des entrées négatives.

> [!NOTE]
> Si vous avez activé les fonctionnalités de planification des changements de stock disponible et de disponibilité à la vente (DAV), votre requête peut également inclure le paramètre booléen `QueryATP`, qui contrôle si les résultats de la requête incluent des informations DAV. Pour plus d’informations et des exemples, voir [Plannings de changement du stock disponible et disponibilité à la vente de la Inventory Visibility](inventory-visibility-available-to-promise.md).

L’exemple suivant montre un exemple de contenu du corps. Il montre que vous pouvez interroger le stock disponible à partir de plusieurs emplacements (entrepôts).

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "locationId": ["11","12","13"],
        "colorId": ["red"]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

L’exemple suivant montre comment interroger tous les produits d’un site et d’un emplacement spécifiques.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": [],
        "siteId": ["1"],
        "locationId": ["11"],
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

### <a name="query-by-using-the-get-method"></a><a name="query-with-get-method"></a>Interroger en utilisant la méthode get

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Get
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Query(Url Parameters):
    groupBy
    returnNegative
    [Filters]
```

Voici un exemple d’URL pour get. Cette requête get est exactement la même que l’exemple post fourni précédemment.

```txt
/api/environment/{environmentId}/onhand?organizationId=SCM_IV&productId=iv_postman_product&siteId=iv_postman_site&locationId=iv_postman_location&colorId=red&groupBy=colorId,sizeId&returnNegative=true
```

## <a name="on-hand-exact-query"></a><a name="exact-query-with-post-method"></a>Requête exacte disponible

Les requêtes exactes disponibles ressemblent aux requêtes disponibles classiques à la différence qu’elle vous permettent de spécifier une hiérarchie de mappage entre un site et un emplacement. Par exemple, vous avez les deux sites suivants :

- Site 1, qui est mappé à l’emplacement A
- Site 2, qui est mappé à l’emplacement B

Pour une requête de stock disponible classique, si vous spécifiez `"siteId": ["1","2"]` et `"locationId": ["A","B"]`, Inventory Visibility interroge automatiquement le résultat des sites et emplacements suivants :

- Site 1, emplacement A
- Site 1, emplacement B
- Site 2, emplacement A
- Site 2, emplacement B

Comme vous le constatez, la requête de stock disponible standard ne voit pas que l’emplacement A n’existe que sur le site 1 et que l’emplacement B n’existe que sur le site 2. Par conséquent, il effectue des requêtes redondantes. Pour prendre en charge ce mappage hiérarchique, vous pouvez utiliser une requête exacte disponible et spécifier les mappages d’emplacement dans le corps de la requête. Dans ce cas, vous interrogez et recevez des résultats uniquement pour site 1, emplacement A et site 2, emplacement B.

### <a name="exact-query-by-using-the-post-method"></a><a name="exact-query-with-post-method"></a>Interroger avec exactitude en utilisant la méthode post

```txt
Path:
    /api/environment/{environmentId}/onhand/exactquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            dimensions: string[],
            values: string[][],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

Dans le corps de cette requête, `dimensionDataSource` est un paramètre facultatif. S’il n’est pas défini, `dimensions` dans `filters` sera traité comme *dimensions de base*. Il y a quatre champs obligatoires pour `filters` : `organizationId`, `productId`, `dimensions` et `values`.

- `organizationId` ne doit contenir qu’une seule valeur, mais c’est tout de même un tableau.
- `productId` peut contenir une ou plusieurs valeurs. Si c’est un tableau vide, tous les produits seront renvoyés.
- Dans le tableau `dimensions`, `siteId` et `locationId` sont obligatoires mais peuvent apparaître avec d’autres éléments dans n’importe quel ordre.
- `values` peut contenir un ou plusieurs tuples distincts de valeurs correspondant à `dimensions`.

`dimensions` dans `filters` sera ajouté automatiquement à `groupByValues`.

Le paramètre `returnNegative` contrôle si les résultats contiennent des entrées négatives.

L’exemple suivant montre un exemple de contenu du corps.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": ["iv_postman_product"],
        "dimensions": ["siteId", "locationId", "colorId"],
        "values" : [
            ["iv_postman_site", "iv_postman_location", "red"],
            ["iv_postman_site", "iv_postman_location", "blue"],
        ]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

L’exemple suivant montre comment interroger tous les produits de plusieurs sites et emplacements.

```json
{
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": [],
        "dimensions": ["siteId", "locationId"],
        "values" : [
            ["iv_postman_site_1", "iv_postman_location_1"],
            ["iv_postman_site_2", "iv_postman_location_2"],
        ]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

## <a name="available-to-promise"></a>Disponible à la vente

Vous pouvez configurer la Inventory Visibility pour vous permettre de planifier les futurs changements de stock et de calculer les quantités DAV. Le DAV correspond à la quantité d’un article qui est disponible et peut être promise à un client dans le courant d’une période à venir. L’utilisation du calcul de la DAV peut augmenter considérablement votre capacité de traitement des commandes. Pour plus d’informations sur l’activation de cette fonctionnalité et sur l’interaction avec la Inventory Visibility via son API une fois la fonctionnalité activée, consultez [Plannings de changement du stock disponible et disponibilité à la vente de la Inventory Visibility](inventory-visibility-available-to-promise.md#api-urls).

## <a name="allocation"></a>Allocation

Les API liées à l’allocation sont situées dans [Allocation de la visibilité des stocks](inventory-visibility-allocation.md#using-allocation-api).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
