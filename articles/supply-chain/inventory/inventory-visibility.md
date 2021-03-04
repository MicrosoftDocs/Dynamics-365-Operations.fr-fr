---
title: Complément de visibilité de stock
description: Cette rubrique décrit comment installer et configurer le complément de visibilité de stock pour Dynamics 365 Supply Chain Management.
author: chuzheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 2976153a6a7e4b4130e8f7673ed128945aeabf65
ms.sourcegitcommit: 03c2e1717b31e4c17ee7bb9004d2ba8cf379a036
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/24/2020
ms.locfileid: "4625063"
---
# <a name="inventory-visibility-add-in"></a>Complément de visibilité de stock

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Le complément de visibilité de stock est un microservice indépendant et hautement évolutif qui permet un suivi des stocks en temps réel, offrant ainsi une vue globale de la visibilité du stock.

Toutes les informations relatives à l'inventaire disponible sont exportées vers le service en temps quasi réel via une intégration SQL de bas niveau. Les systèmes externes accèdent au service via des API RESTful pour interroger les informations disponibles sur des ensembles de dimensions donnés, récupérant ainsi une liste des positions disponibles.

La visibilité du stock est un microservice basé sur Common Data Service, ce qui signifie que vous pouvez l'étendre en créant Power Apps et en appliquant Power BI pour fournir des fonctionnalités personnalisées pour répondre aux besoins de votre entreprise. Il est également possible de mettre à niveau l'index pour effectuer des requêtes d'inventaire.

La visibilité du stock fournit des options de configuration qui lui permettent de s'intégrer à plusieurs systèmes tiers. Il prend en charge la dimension de stock normalisée, l'extensibilité personnalisée et les quantités calculées normalisées et configurables.

Cette rubrique décrit comment installer et configurer le complément de visibilité de stock pour Dynamics 365 Supply Chain Management, et comment utiliser son interface de programmation d'application (API).

## <a name="install-the-inventory-visibility-add-in"></a>Installer le complément de visibilité de stock

Vous devez installer le complément de visibilité de stock à l'aide de Microsoft Dynamics Lifecycle Services (LCS). LCS est un portail de collaboration qui fournit un environnement et un ensemble de services régulièrement mis à jour qui vous aident à gérer le cycle de vie des applications de vos applications Dynamics 365 Finance and Operations.

Pour plus d'informations, voir [Ressources Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).

### <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir installer le complément Visibilité du stock, vous devez procéder comme suit :

- Obtenez un projet d'implémentation LCS avec au moins un environnement déployé.
- Générez les clés bêta de votre offre dans LCS.
- Activez les clés bêta de votre offre pour votre utilisateur dans LCS.
- Contactez l'équipe produit de la visibilité du stock Microsoft et fournissez un ID d'environnement dans lequel vous souhaitez déployer le complément de visibilité de stock.

Si vous avez des questions sur ces conditions préalables, contactez l'équipe produit de visibilité du stock.

### <a name="install-the-add-in"></a><a name="install-add-in"></a>Installer le complément

Pour pouvoir installer le complément Visibilité du stock, procédez comme suit :

1. Connectez-vous au portail [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. Sur la page d'accueil, sélectionnez le projet dans lequel votre environnement est déployé.
1. Sur la page du projet, sélectionnez l'environnement dans lequel vous souhaitez installer le complément.
1. Sur la page d'environnement, faites défiler vers le bas jusqu'à ce que vous voyiez la section **Compléments d'environnement**. Si la section n'est pas visible, assurez-vous que les clés bêta prérequises ont été entièrement traitées.
1. Dans la section **Compléments de l'environnement**, sélectionnez **Installer un nouveau complément**.
    ![Page de l'environnement dans LCS](media/inventory-visibility-environment.png "Page de l'environnement dans LCS")
1. Sélectionnez le lien **Installer un nouveau complément**. Une liste des compléments disponibles s'ouvre.
1. Sélectionnez **Service d'inventaire** dans la liste. (Notez que cela peut maintenant être répertorié comme **Complément de visibilité de stock pour Dynamics 365 Supply Chain Management**.)
1. Saisissez des valeurs pour les champs suivants pour votre environnement :

    - **ID application AAD**
    - **ID locataire AAD**

    ![Ajouter dans la page de configuration](media/inventory-visibility-setup.png "Page de configuration de complément")

1. Acceptez les termes et conditions en cochant la case **Termes et conditions**.
1. Sélectionnez **Installer**. Le statut du complément s'affichera comme **Installation en cours**. Une fois terminé, actualisez la page pour voir le statut changer en **Installé**.

### <a name="get-a-security-service-token"></a>Obtenir un jeton de service de sécurité

Pour obtenir un jeton de service de sécurité, procédez comme suit :

1. Obtenir votre `aadToken` et appelez le point de terminaison : https://securityservice.operations365.dynamics.com/token.
1. Remplacez le `client_assertion` dans le corps avec votre `aadToken`.
1. Remplacez le contexte dans le corps par l'environnement dans lequel vous souhaitez déployer le complément.
1. Remplacez la portée dans le corps par ce qui suit :

    - Portée pour MCK – « https://inventoryservice.operations365.dynamics.cn/.default »  
    (Vous pouvez trouver ID d'application et ID de locataire Azure Active Directory pour MCK dans `appsettings.mck.json`.)
    - Portée pour PROD – « https://inventoryservice.operations365.dynamics.com/.default »  
    (Vous pouvez trouver ID d'application et ID de locataire Azure Active Directory pour PROD dans `appsettings.prod.json`.)

    Le résultat doit ressembler à l’exemple ci-dessous.

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{**Your_AADToken**}",
        "scope":"**https://inventoryservice.operations365.dynamics.com/.default**",
        "context": "**5dbf6cc8-255e-4de2-8a25-2101cd5649b4**",
        "context_type": "finops-env"
    }
    ```

1. Vous obtiendrez un `access_token` en réponse. C'est ce dont vous avez besoin en tant que jeton de support pour appeler l'API de visibilité de stock. Voici un exemple :

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a>Désinstaller le complément

Pour désinstaller le complément, sélectionnez **Désinstaller**. Actualiser LCS et le complément de visibilité de stock seront supprimés. Le processus de désinstallation supprimera l'inscription du complément et lancera également une tâche pour nettoyer toutes les données d'entreprise stockées dans le service.

## <a name="inventory-visibility-add-in-public-api"></a>API publique du complément de visibilité de stock

L'API REST publique du complément de visibilité de stock présente plusieurs points de terminaison d'intégration spécifiques. Elle prend en charge trois types d'interactions principaux :

- Publication des modifications disponibles du complément à partir d'un système externe.
- Interrogation des quantités en stock actuelles à partir d'un système externe.
- Synchronisation automatique avec Supply Chain Management à portée de main.

La synchronisation automatique ne fait pas partie de l'API publique, mais est plutôt gérée en arrière-plan pour les environnements qui ont activé le complément de visibilité d'inventaire.

### <a name="authentication"></a>Authentification

Le jeton de sécurité de la plateforme est utilisé pour appeler le complément de visibilité d'inventaire, vous devez donc générer un jeton Azure Active Directory en utilisant votre application Azure Active Directory.

Pour plus d'informations sur la façon d'obtenir le jeton de sécurité, consultez [Installer le complément de visibilité de stock](#install-add-in).

### <a name="configure-the-inventory-visibility-api"></a>Configurer l'API de visibilité de stock

Avant d'utiliser le service, vous devez effectuer les configurations décrites dans les sous-sections suivantes. La configuration peut varier en fonction des détails de votre environnement. Il comprend principalement quatre parties :

- [Partitionnement](#partitioning)
- [Configurations des dimensions](#dimension-configurations)
- [Indexation](#indexing)
- [Mesure personnalisée](#custom-measurement)

#### <a name="partitioning"></a>Partitionnement

Le partitionnement peut influencer considérablement les performances de l'API de visibilité d'inventaire. C'est une bonne idée de définir un schéma qui permet de petits regroupements de données tout en permettant des requêtes de données significatives.

L'`organizationId` (`dataAreaId` dans Supply Chain Management) fera toujours partie du partitionnement et, par défaut, la visibilité du stock est définie pour partitionner par dimensions comme *Site + Localisation*. Cela signifie que le service doit toujours être interrogé avec ces dimensions définies sur les filtres.

> [!NOTE]
> *Site* et *Emplacement* sont deux dimensions générales par défaut dans la visibilité du stock. Dans Supply Chain Management, ces dimensions sont appelées *Site* (`InventSiteId`) et *Entrepôt* (`InventLocationId`)

### <a name="dimension-configurations"></a>Configurations des dimensions

La visibilité du stock fournira une liste de dimensions générales par défaut pour permettre l'intégration du système source multiple.

Le tableau suivant répertorie les dimensions d'inventaire qui seront les noms de dimension par défaut dans la visibilité du stock.

| Type de dimension | Nom de dimension |
|---|---|
| Produit | `ColorId` |
| Produit | `SizeId` |
| Produit | `StyleId` |
| Produit | `ConfigId` |
| Suivi | `BatchId` |
| Suivi | `SerialId` |
| Entrepôt | `LocationId` |
| Entrepôt | `SiteId` |
| Statut du stock | `StatusId` |
| Spécifique à l'entrepôt | `WMSLocationId` |
| Spécifique à l'entrepôt | `WMSPalletId` |
| Spécifique à l'entrepôt | `LicensePlateId` |

> [!NOTE]
> Le type de dimension répertorié dans le tableau précédent est à titre indicatif uniquement. Vous n'avez pas besoin de définir le type de dimension dans la visibilité du stock.

Si une dimension personnalisée existe et doit passer à une valeur par défaut lorsqu'elle est utilisée par la visibilité du stock, vous pouvez configurer le nom **Dimension personnalisée** dans la visibilité du stock.

Les systèmes externes accèdent à la visibilité du stock via des API RESTful qui permettent d'interroger des informations disponibles sur des ensembles de dimensions donnés. Pour l'intégration, la visibilité du stock vous permet de configurer la *source de données de canal externe* et la dimension source des *dimensions cibles* dans la visibilité du stock.

Les dimensions cibles doivent être l'une des suivantes :

- Dimensions par défaut dans la visibilité du stock
- Dimensions personnalisées

Le but de la configuration des dimensions est de standardiser l'intégration multi-système pour la requête sur les dimensions et l'événement de publication avec les dimensions.

#### <a name="indexing"></a>Indexation

La plupart du temps, la requête de stock disponible sera non seulement au niveau "total" le plus élevé, mais vous souhaiterez peut-être voir les résultats agrégés en fonction des dimensions de stock.

La visibilité du stock offre une certaine flexibilité en vous permettant de configurer les index, qui sont basés sur la dimension ou la combinaison des dimensions.

> [!NOTE]
> Actuellement, vous ne pouvez configurer les index que jusqu'à un maximum de cinq. Vous devez examiner attentivement la dimension ou la combinaison de dimensions que vous utiliserez avant la mise en œuvre pour vous assurer qu'elle répondra aux besoins de votre entreprise. Par exemple, si vous souhaitez interroger les produits comme suit :

- Recherchez le produit agrégé disponible par les dimensions *Couleur* et *Taille*.
- Dans certains cas, vous souhaitez simplement interroger le produit au total.

Vous auriez deux index définis comme suit :

- `["ColorId", "SizeId"]`
- `[]`

Le crochet vide sera agrégé en fonction de l'ID de produit dans la partition.

L'indexation définit comment vous pouvez regrouper vos résultats en fonction du paramètre de requête `groupBy`. Dans ce cas, si vous ne définissez aucune valeur `groupBy`, vous obtiendrez les totaux par `productid`. Sinon si vous définissez `groupBy` comme `groupBy=ColorId&groupBy=SizeId`, vous obtiendrez plusieurs lignes renvoyées, en fonction des différentes combinaisons de couleurs et de tailles du système.

Vous pouvez mettre vos critères de requête dans le corps de la requête.

Voici un exemple de requête sur le produit avec une combinaison de couleur et de taille.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a>Mesure personnalisée

Les quantités de mesure par défaut sont liées à Supply Chain Management, mais vous souhaiterez peut-être avoir une quantité composée d'une combinaison des mesures par défaut. Pour ce faire, vous pouvez avoir une configuration de quantités personnalisées, qui seront ajoutées à la sortie des requêtes en main.

La fonctionnalité vous permet simplement de définir un ensemble de mesures qui seront ajoutées, et/ou un ensemble de mesures qui seront soustraites, afin de la mesure personnalisée.

Par exemple, avec la condition de requête suivante, vous configurerez la quantité de mesure personnalisée comme `MyCustomAvailableforReservation` à consommer par le système de consommation.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| Système de consommation | Mesures calculées | Source de données | Modificateur | Type de calcul du modificateur |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | Addition |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | Addition |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | Soustraction |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | Addition |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | Soustraction |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | Addition |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | Addition |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | Soustraction |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | Soustraction |

Avec cela, la requête sur la quantité de mesure personnalisée renverra la sortie suivante.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

La sortie `MyCustomAvailableforReservation` est basée sur le paramètre de calcul dans les mesures personnalisées comme :  
 *100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*

### <a name="posting-on-hand-changes"></a>Publication des modifications en stock

L'URL exacte sur laquelle l'événement sera publié dépendra de votre région géographique. Il prendra la forme :

`https://{serviceURL}/api/environment/{environmentId}/onhand`

Une fois authentifiée, cette URL peut être utilisée avec la méthode HTTP `POST` pour envoyer des événements de modification en main au service.

Un en-tête spécial est utilisé pour communiquer avec les services Dynamics 365 via des requêtes HTTP, indiquant l'ID d'environnement de l'instance Supply Chain Management à laquelle les données sont liées. Par exemple :

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a>Exemple de requête de publication de modifications en main 1

Cet exemple montre un scénario dans lequel vous allez configurer la configuration de dimension dans Power Apps.

Utilisez la requête suivante pour configurer le mappage de dimension dans Power Apps :

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Vous pouvez maintenant spécifier la `dimensionDataSource` et utilisez des dimensions personnalisées dans vos requêtes. Le système convertira automatiquement les dimensions personnalisées en dimensions de base.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a>Exemple de requête de publication de modifications en main 2

Cet exemple montre un scénario dans lequel aucun mappage n'est configuré pour la configuration de dimension dans Power Apps, donc la publication doit également utiliser les dimensions de base. Toutes les dimensions doivent être des dimensions de base lorsque le champ `dimensionDataSource` est nul, vide ou espace.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a>Propriétés du champs de documents JSON

Les champs des exemples de requête JSON fournis précédemment ont les propriétés répertoriées dans le tableau suivant.

| ID champ | Description |
|---|---|
| `id` | Un ID unique pour l'événement de modification spécifique. Cet ID est utilisé pour garantir qu'en cas d'échec de la communication avec le service pendant la comptabilisation, la soumission à nouveau de l'événement n'entraînerait pas le comptage du même événement deux fois dans le système. |
| `organizationId` | L'identificateur de l'organisation liée à l'événement. Cela correspond aux organisations de gestion de Supply Chain Management ou aux ID de zone de données. |
| `productId` | Identificateur du produit en question. |
| `quantity` | La quantité dont le stock doit être changé. Si, par exemple, 10 nouveaux bagels étaient ajoutés à une étagère, cette valeur serait de 10. Si 3 bagels étaient ensuite retirés de l'étagère ou vendus, cette valeur serait de -3. |
| `dimensionDataSource` | Source de données des dimensions utilisées dans l'événement et la requête de modification de publication. Si vous spécifiez la source de données, vous pouvez utiliser les dimensions personnalisées de la source de données spécifiée. Avec la configuration des dimensions, la visibilité du stock peut mapper les dimensions personnalisées aux dimensions générales par défaut. Si la `dimensionDataSource` n'est pas spécifié, vous ne pouvez utiliser que les dimensions générales par défaut dans vos requêtes.   |
| `dimensions` | Un sac dynamique de paires clé/valeur. Celles-ci correspondront à certaines des dimensions de Supply Chain Management, mais vous pouvez également ajouter des dimensions personnalisées (comme *Source*) qui peut indiquer si l'événement provenait de Supply Chain Management ou d'un système externe. |

### <a name="querying-current-on-hand"></a>Interrogation actuellement disponible

Le point de terminaison pour interroger le stock actuel aura une URL similaire :

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

Il sera interrogé avec la méthode HTTP `POST`.

#### <a name="current-on-hand-query-example-1"></a>Exemple de requête en main actuel 1

Cet exemple montre un scénario dans lequel vous disposez déjà d'une configuration de dimension terminée dans Power Apps.

Utilisez la requête suivante pour configurer le mappage de dimension dans Power Apps :

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Vous pouvez maintenant spécifier la `dimensionDataSource` et utilisez des dimensions personnalisées dans vos requêtes. Le système convertira automatiquement les dimensions personnalisées en dimensions de base. Vous pouvez spécifier la `DimensionDataSource` dans `filters` et spécifiez des dimensions personnalisées dans `filters` et `groupByValues`. Le système convertira automatiquement les dimensions personnalisées en dimensions de base.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a>Exemple de requête en main actuel 2

Cet exemple montre un scénario dans lequel aucun mappage n'est configuré pour la configuration de dimension dans Power Apps, donc la publication doit également utiliser les dimensions de base. Toutes les dimensions doivent être des dimensions de base lorsque le champ `dimensionDataSource`, sous `filters`, est nul, vide ou espace.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a>Exemple de résultat de retour

Les requêtes présentées dans les exemples précédents peuvent renvoyer un résultat comme celui-ci.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

Notez que les champs de quantités sont structurés comme un dictionnaire de mesures et de leurs valeurs associées.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]