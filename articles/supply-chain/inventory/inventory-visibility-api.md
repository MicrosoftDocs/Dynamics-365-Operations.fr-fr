---
title: API publiques de visibilité des stocks
description: Cette rubrique décrit les API publiques fournies par la visibilité des stocks.
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 92c427d3063c34f263d5bc449be6fac695b5912d
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/10/2022
ms.locfileid: "7952625"
---
# <a name="inventory-visibility-public-apis"></a>API publiques de visibilité des stocks

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Cette rubrique décrit les API publiques fournies par la visibilité des stocks.

L’API REST publique du complément de visibilité des stocks présente plusieurs points de terminaison d’intégration spécifiques. Elle prend en charge quatre types d’interactions :

- Publication des modifications de stock disponibles du complément à partir d’un système externe
- Définition ou remplacement des quantités de stock disponible dans le complément à partir d’un système externe
- Publication des événements de réservation dans le complément à partir d’un système externe
- Interrogation des quantités en stock actuelles à partir d’un système externe

Le tableau suivant répertorie les API actuellement disponibles :

| Chemin d’accès | méthode | Description |
|---|---|---|
| /api/environment/{environmentId}/onhand | Valider | [Créer un événement de modification de stock disponible](#create-one-onhand-change-event) |
| /api/environment/{environmentId}/onhand/bulk | Valider | [Créer plusieurs événements de modification](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | Valider | [Définir/remplacer les quantités de stock disponible](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | Valider | [Créer un événement de réservation](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | Valider | [Créer plusieurs événements de réservation](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/indexquery | Valider | [Interroger en utilisant la méthode post](#query-with-post-method) |
| /api/environment/{environmentId}/onhand | Obtenir | [Interroger en utilisant la méthode get](#query-with-get-method) |

Microsoft a fourni une collection de requêtes *Postman* prêtes à l’emploi. Vous pouvez importer cette collection dans votre logiciel *Postman* en utilisant le lien partagé suivant : <https://www.getpostman.com/collections/90bd57f36a789e1f8d4c>.

> [!NOTE]
> La partie {environmentId} du chemin d’accès est l’ID d’environnement dans Microsoft Dynamics Lifecycle Services (LCS).
> 
> L’API en masse peut renvoyer un maximum de 512 enregistrements pour chaque requête.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a>Rechercher le point de terminaison en fonction de votre environnement Lifecycle Services

Le microservice de visibilité des stocks est déployé sur Microsoft Azure Service Fabric, dans plusieurs zones géographiques et plusieurs régions. Il n’existe actuellement aucun point de terminaison central qui puisse rediriger automatiquement votre requête vers la zone géographique et la région correspondantes. Par conséquent, vous devez composer les informations dans une URL en utilisant le modèle suivant :

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

Le nom abrégé de la région se trouve dans l’environnement Microsoft Dynamics Lifecycle Services (LCS). Le tableau suivant répertorie les régions actuellement disponibles.

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
| Brésil Sud        | sbr               |
| Centre-sud des États-Unis    | scus              |

Le numéro d’île est l’endroit où votre environnement LCS est déployé sur Service Fabric. Il n’y a actuellement aucun moyen d’obtenir ces informations du côté de l’utilisateur.

Microsoft a construit une interface utilisateur (IU) dans Power Apps afin que vous puissiez obtenir le point de terminaison complet du microservice. Pour plus d’informations, voir [Rechercher le point de terminaison de service](inventory-visibility-configuration.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Authentification

Le jeton de sécurité de la plateforme est utilisé pour appeler l’API publique de visibilité des stocks. Par conséquent, vous devez générer un jeton _Azure Active Directory (Azure AD)_ en utilisant votre application Azure AD. Vous devez ensuite utiliser le jeton Azure AD pour obtenir le _jeton d’accès_ du service de sécurité.

Microsoft fournit une collection de jetons d’obtention *Postman* prête à l’emploi. Vous pouvez importer cette collection dans votre logiciel *Postman* en utilisant le lien partagé suivant : <https://www.getpostman.com/collections/496645018f96b3f0455e>.

Pour obtenir un jeton de service de sécurité, procédez comme suit.

1. Connectez-vous au portail Azure et utilisez-le pour trouver les valeurs `clientId` et `clientSecret` pour votre application Dynamics 365 Supply Chain Management.
1. Récupérez un jeton Azure AD (`aadToken`) en envoyant une requête HTTP avec les propriétés suivantes :

   - **URL :** `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
   - **Méthode :** `GET`
   - **Contenu du corps (données du formulaire) :**

     | Clé           | Valeur                                |
     | ------------- | ------------------------------------ |
     | client_id     | ${aadAppId}                          |
     | client_secret | ${aadAppSecret}                      |
     | grant_type    | client_credentials                   |
     | resource      | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |

   Vous devriez recevoir un jeton Azure AD (`aadToken`) en réponse. Elle doit ressembler à l’exemple ci-dessous.

   ```json
   {
       "token_type": "Bearer",
       "expires_in": "3599",
       "ext_expires_in": "3599",
       "expires_on": "1610466645",
       "not_before": "1610462745",
       "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
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
       "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
       "context_type": "finops-env"
   }
   ```

   Notez les points suivants :

   - La valeur `client_assertion` doit être le jeton Azure AD (`aadToken`) que vous avez reçu à l’étape précédente.
   - La valeur `context` doit être l’ID d’environnement LCS dans lequel vous souhaitez déployer le complément.
   - Définissez toutes les autres valeurs comme indiqué dans l’exemple.

1. Récupérez un jeton d’accès (`access_token`) en envoyant une requête HTTP avec les propriétés suivantes :

   - **URL :** `https://securityservice.operations365.dynamics.com/token`
   - **Méthode :** `POST`
   - **En-tête HTTP :** incluez la version de l’API. (La clé est `Api-Version` et la valeur est `1.0` .)
   - **Contenu du corps :** incluez la requête JSON que vous avez créée à l’étape précédente.

   Vous devriez recevoir un jeton (`access_token`) en réponse. Vous devez utiliser ce jeton comme jeton du porteur pour appeler l’API de visibilité des stocks. Voici un exemple :

   ```json
   {
       "access_token": "{Returned_Token}",
       "token_type": "bearer",
       "expires_in": 3600
   }
   ```

> [!IMPORTANT]
> Lorsque vous utilisez la demande de collecte *Postman* pour appeler les API publiques Inventory Visibility, vous devez ajouter un jeton de support pour chaque demande. Pour trouver votre jeton au porteur, sélectionnez l’onglet **Autorisation** sous l’URL de la demande, sélectionnez le type **Jeton du porteur**, tapez et copiez le jeton d’accès qui a été récupéré à la dernière étape. Dans les sections suivantes de cette rubrique, `$access_token` sera utilisé pour représenter le jeton qui a été récupéré à la dernière étape.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>Créer des événements de modification de stock disponible

Il existe deux API pour créer des événements de modification de stock disponible :

- Créer un enregistrement : `/api/environment/{environmentId}/onhand`
- Créer plusieurs enregistrements : `/api/environment/{environmentId}/onhand/bulk`

Le tableau suivant récapitule la signification de chaque champ dans le corps JSON.

| ID champ | Description |
|---|---|
| `id` | Un ID unique pour l’événement de modification spécifique. Cet ID est utilisé pour garantir qu’en cas d’échec de la communication avec le service pendant la publication, le même événement ne sera pas compté deux fois dans le système s’il est soumis de nouveau. |
| `organizationId` | L’identificateur de l’organisation liée à l’événement. Cette valeur est mappée à un ID d’organisation ou de zone de données dans Supply Chain Management. |
| `productId` | Identificateur du produit. |
| `quantities` | Quantité selon laquelle la quantité disponible doit être modifiée. Par exemple, si 10 nouveaux livres sont ajoutés dans un rayon, cette valeur sera `quantities:{ shelf:{ received: 10 }}`. Si trois livres sont retirés du rayon ou vendus, cette valeur sera `quantities:{ shelf:{ sold: 3 }}`. |
| `dimensionDataSource` | Source de données des dimensions utilisées dans l’événement et la requête de modification de publication. Si vous spécifiez la source de données, vous pouvez utiliser les dimensions personnalisées de la source de données spécifiée. La visibilité des stocks peut utiliser la configuration des dimensions pour mapper les dimensions personnalisées aux dimensions générales par défaut. Si aucune valeur `dimensionDataSource` n’est spécifiée, vous ne pouvez n’utiliser que les [dimensions de base](inventory-visibility-configuration.md#data-source-configuration-dimension) générales dans vos requêtes. |
| `dimensions` | Paire clé-valeur dynamique. Les valeurs sont mappées à certaines des dimensions dans Supply Chain Management. Cependant, vous pouvez également ajouter des dimensions personnalisées (par exemple, _Source_) pour indiquer si l’événement provient de Supply Chain Management ou d’un système externe. |

> [!NOTE]
> Les paramètres `SiteId` et `LocationId` construisent la [configuration de la partition](inventory-visibility-configuration.md#partition-configuration). Par conséquent, vous devez les spécifier dans les dimensions lorsque vous créez des événements de modification de stock disponible, définissez ou remplacez des quantités en stock ou créez des événements de réservation.

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

L’exemple suivant montre un exemple de contenu du corps. Dans cet exemple, vous publiez un événement de modification pour le produit *T-shirt*. Cet événement provient du système de point de vente (PDV) et le client a renvoyé un t-shirt rouge dans votre magasin. Cet événement augmentera la quantité du produit *T-shirt* de 1.

```json
{
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "PosMachineId": "0001",
        "ColorId": "Red"
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
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Créer plusieurs événements de modification

Cette API peut créer plusieurs enregistrements en même temps. Les seules différences entre cette API et l’[API d’événement unique](#create-one-onhand-change-event) sont les valeurs `Path` et `Body`. Pour cette API, `Body` fournit un tableau d’enregistrements. Le nombre maximal d’enregistrements est de 512, ce qui signifie que l’API en bloc de modification disponible peut prendre en charge jusqu’à 512 événements de modification à la fois.

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
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "654321",
        "organizationId": "usmf",
        "productId": "Pants",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>Définir/remplacer les quantités de stock disponible

L’API _Set on-hand_ remplace les données actuelles pour le produit spécifié.

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

L’exemple suivant montre un exemple de contenu du corps. Le comportement de cette API diffère du comportement des API décrites dans la section [Créer des événements de modification de stock disponible](#create-onhand-change-event) plus haut dans cette rubrique. Dans cet exemple, la quantité du produit *T-shirt* sera définie sur 1.

```json
[
    {
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
             "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId": "0001"
        },
        "quantities": {
            "pos": {
                "inbound": 1
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>Créer des événements de réservation

Pour utiliser l’API *Reserve*, vous devez ouvrir la fonctionnalité de réservation et compléter la configuration de la réservation. Pour plus d’informations, voir [Configuration de la réservation (facultatif)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Créer un événement de réservation

Une réservation peut être effectuée pour différents paramètres de source de données. Pour configurer ce type de réservation, indiquez d’abord la source de données dans le paramètre `dimensionDataSource`. Ensuite, dans le paramètre `dimensions`, spécifiez les dimensions en fonction des paramètres de dimension dans la source de données cible.

Lorsque vous appelez l’API de réservation, vous pouvez contrôler la validation de la réservation en spécifiant le paramètre booléen `ifCheckAvailForReserv` dans le corps de la requête. Une valeur `True` signifie que la validation est requise, alors qu’une valeur `False` signifie que la validation n’est pas requise. La valeur par défaut est `True`.

Si vous souhaitez annuler une réservation ou annuler la réservation de quantités de stock spécifiées, définissez la quantité sur une valeur négative et définissez le paramètre `ifCheckAvailForReserv` sur `False` pour ignorer la validation.

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
    "organizationId": "usmf",
    "productId": "T-shirt",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softreservordered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    }
}
```

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Créer plusieurs événements de réservation

Cette API est une version en bloc de l’[API d’événement unique](#create-one-reservation-event).

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

## <a name="query-on-hand"></a>Interroger le stock disponible

Utilisez l’API _Query on-hand_ pour récupérer les données de stock disponible actuelles pour vos produits. L’API prend actuellement en charge l’interrogation de jusqu’à 100 éléments individuels par valeur `ProductID`. Plusieurs valeurs `SiteID` et `LocationID` peuvent également être spécifiées dans chaque requête. La limite maximale est définie comme `NumOf(SiteID) * NumOf(LocationID) <= 100`.

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

Le paramètre `groupByValues` doit suivre votre configuration pour l’indexation. Pour plus d’informations, voir [Configuration de la hiérarchie d’index des produits](./inventory-visibility-configuration.md#index-configuration).

Le paramètre `returnNegative` contrôle si les résultats contiennent des entrées négatives.

L’exemple suivant montre un exemple de contenu du corps.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "LocationId": ["11"],
        "ColorId": ["Red"]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true
}
```

Les exemples suivants montrent comment interroger tous les produits d’un site et d’un emplacement spécifiques.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": [],
        "siteId": ["1"],
        "LocationId": ["11"],
    },
    "groupByValues": ["ColorId", "SizeId"],
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
/api/environment/{environmentId}/onhand?organizationId=usmf&productId=T-shirt&SiteId=1&LocationId=11&ColorId=Red&groupBy=ColorId,SizeId&returnNegative=true
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
