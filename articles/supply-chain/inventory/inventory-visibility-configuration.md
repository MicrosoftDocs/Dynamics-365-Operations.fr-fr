---
title: Configuration de la visibilité des stocks
description: Cette rubrique décrit comment configurer la visibilité des stocks.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 92e42b22d424ab80303d771f760cfcf0599b9f4c
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345031"
---
# <a name="inventory-visibility-configuration"></a>Configuration de la visibilité des stocks

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Cette rubrique décrit comment configurer la visibilité des stocks.

## <a name="introduction"></a><a name="introduction"></a>Introduction

Avant de commencer à travailler avec la visibilité des stocks, vous devez effectuer la configuration suivante, comme décrit dans cette rubrique :

- [Configuration de la source de données](#data-source-configuration)
- [Configuration de la partition](#partition-configuration)
- [Configuration de la hiérarchie d’index des produits](#index-configuration)
- [Configuration de la réservation (facultatif)](#reservation-configuration)
- [Exemple de configuration par défaut](#default-configuration-sample)

> [!NOTE]
> Vous pouvez afficher et modifier les configurations de visibilité des stocks dans [Microsoft Power Apps](./inventory-visibility-power-platform.md#configuration). Une fois la configuration terminée, sélectionnez **Mettre à jour la configuration** dans l’application.

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Configuration de la source de données

La source de données représente le système d’où proviennent vos données. Les exemples incluent `fno` (qui signifie « Dynamics 365 Finance and Operations ») et `pos` (qui signifie « point de vente »).

La configuration de la source de données comprend les éléments suivants :

- Dimension (mappage des dimensions)
- Mesure physique
- Mesure calculée

> [!NOTE]
> La source de données `fno` est réservée pour Dynamics 365 Supply Chain Management.

### <a name="dimension-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimension (mappage des dimensions)

Le but de la configuration des dimensions est de standardiser l’intégration multi-système pour les événements et requêtes de publication, en fonction de combinaisons de dimensions.

La visibilité des stocks prend en charge les dimensions de base générales suivantes.

| Type de dimension | Dimension de base |
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
| Spécifique à l’entrepôt | `WMSLocationId` |
| Spécifique à l’entrepôt | `WMSPalletId` |
| Spécifique à l’entrepôt | `LicensePlateId` |
| Autres | `VersionId` |
| Stock (personnalisé) | `InventDimension1` à `InventDimension12` |
| Poste | `ExtendedDimension1` à `ExtendedDimension8` |

> [!NOTE]
> Les types de dimensions répertoriés dans le tableau précédent sont à titre indicatif uniquement. Vous n’avez pas besoin de les définir dans la visibilité des stocks.
>
> Les dimensions de stock (personnalisées) peuvent être réservées pour Supply Chain Management. Dans ce cas, vous pouvez utiliser les dimensions étendues à la place.

Les systèmes externes peuvent accéder à la visibilité des stocks via ses API RESTful. Pour l’intégration, la visibilité des stocks vous permet de configurer la _source de données externe_ et le mappage des _dimensions externes_ aux _dimensions de base_. Voici un exemple d’une table de mappage des dimensions.

| Dimension externe | Dimension de base |
|---|---|
| `MyColorId` | `ColorId` |
| `MySizeId` | `SizeId` |
| `MyStyleId` | `StyleId` |
| `MyDimension1` | `ExtendedDimension1` |
| `MyDimension2` | `ExtendedDimension2` |

En configurant un mappage de dimensions, vous pouvez envoyer les dimensions externes directement à la visibilité des stocks. La visibilité des stocks convertira alors automatiquement les dimensions externes en dimensions de base.

### <a name="physical-measures"></a>Mesures physiques

Les mesures physiques modifient la quantité et reflètent le statut des stocks. Vous pouvez définir vos propres mesures physiques en fonction de vos besoins.

La visibilité des stocks fournit une liste de mesures physiques par défaut qui sont liées à Supply Chain Management (la source de données `fno`). Le tableau suivant fournit un exemple de mesures physiques.

| Nom de la mesure physique | Description  |
|---|---|
| `NotSpecified` | Non spécifié(e) |
| `Arrived` | Arrivé |
| `AvailOrdered` | Disponible commandé |
| `AvailPhysical` | Physique disponible |
| `Deducted` | Déduit |
| `OnOrder` | Sur commande |
| `Ordered` | Commandée |
| `PhysicalInvent` | Stock physique |
| `Picked` | Prélevée |
| `PostedQty` | Quantité validée |
| `QuotationIssue` | Sortie de devis |
| `QuotationReceipt` | Réception de devis |
| `Received` | Réceptions |
| `Registered` | Enregistré |
| `ReservOrdered` | Commandé réservé |
| `ReservPhysical` | Physique réservé |

### <a name="calculated-measures"></a><a name="data-source-configuration-calculated-measure"></a>Mesures calculées

Les mesures calculées fournissent une formule de calcul personnalisée qui consiste en une combinaison de mesures physiques. Cette fonctionnalité vous permet de définir un ensemble de mesures physiques qui seront ajoutées, et/ou un ensemble de mesures physiques qui seront soustraites, afin de former la mesure personnalisée.

Par exemple, vous avez le résultat de requête suivant.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]
```

Vous configurez ensuite une mesure calculée nommée `MyCustomAvailableforReservation`, comme indiqué dans le tableau suivant. Cette mesure calculée sera utilisée par le système de consommation.

| Système de consommation | Mesure calculée | Source de données | Mesure physique | Type de calcul |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `scheduled` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `reserved` | `Subtraction` |

Lorsque cette formule de calcul sera utilisée, le nouveau résultat de requête inclura la mesure personnalisée.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
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

La sortie `MyCustomAvailableforReservation`, basée sur le paramètre de calcul dans les mesures personnalisées, est 100 + 50 + 80 + 90 + 30 – 10 – 20 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Configuration de la partition

La configuration de la partition consiste en une combinaison de dimensions de base. Elle définit le modèle de distribution des données. Les opérations de données dans la même partition prennent en charge des performances élevées et ne coûtent pas trop cher. Par conséquent, de bons modèles de partition peuvent apporter des avantages significatifs.

La visibilité des stocks fournit la configuration de partition par défaut suivante.

| Dimension de base | Hiérarchie  |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

> [!NOTE]
> La configuration de partition par défaut est à titre indicatif uniquement. Vous n’avez pas besoin de la définir dans la visibilité des stocks. Actuellement, la mise à niveau de la configuration de partition n’est pas prise en charge.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Configuration de la hiérarchie d’index des produits

La plupart du temps, la requête de stock disponible ne sera pas seulement au niveau « total » le plus élevé. Au lieu de cela, vous souhaiterez peut-être également voir les résultats agrégés en fonction des dimensions de stock.

La visibilité des stocks offre de la flexibilité en vous permettant de configurer les _index_. Ces index sont basés sur une dimension ou une combinaison de dimensions. Un index se compose d’un *numéro d’ensemble*, d’une *dimension* et d’une *hiérarchie*, tel que défini dans le tableau suivant.

| Nom | Description  |
|---|---|
| Numéro d’ensemble | Les dimensions appartenant au même ensemble (index) seront regroupées et le même numéro d’ensemble leur sera attribué. |
| Dimension | Dimensions de base sur lesquelles le résultat de requête est agrégé. |
| Hiérarchie  | La hiérarchie est utilisée pour définir les combinaisons de dimensions prises en charge qui peuvent être interrogées. Par exemple, vous configurez un ensemble de dimensions qui a une séquence hiérarchique de `(ColorId, SizeId, StyleId)`. Dans ce cas, le système prend en charge les requêtes sur quatre combinaisons de dimensions. La première combinaison est vide, la seconde est `(ColorId)`, la troisième est `(ColorId, SizeId)` et la quatrième est `(ColorId, SizeId, StyleId)`. Les autres combinaisons ne sont pas prises en charge. Pour plus d’informations, voir les exemples suivants. |

### <a name="example"></a>Exemple

Cette section fournit un exemple qui montre comment fonctionne la hiérarchie.

Les articles suivants se trouvent dans votre stock.

| Article | ColorId | SizeId | StyleId | Quantité |
|---|---|---|---|---|
| T-shirt | Noir | Petite | Paysage | 1 |
| T-shirt | Noir | Petite | Régulier | 2 |
| T-shirt | Noir | Etendu | Paysage | 3 |
| T-shirt | Noir | Etendu | Régulier | 4 |
| T-shirt | Rouge | Petite | Paysage | 5 |
| T-shirt | Rouge | Petite | Régulier | 6 |
| T-shirt | Rouge | Etendu | Régulier | 7 |

Voici l’index.

| Numéro d’ensemble | Dimension | Hiérarchie  |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

L’index vous permet d’interroger le stock disponible des manières suivantes :

- `()` – Groupé par tous

    - T-shirt, 28

- `(ColorId)` – Groupé par `ColorId`

    - T-shirt, Noir, 10
    - T-shirt, Rouge, 18

- `(ColorId, SizeId)` – Groupé par la combinaison de `ColorId` et `SizeId`

    - T-shirt, Noir, Petit, 3
    - T-shirt, Noir, Grand, 7
    - T-shirt, Rouge, Petit, 11
    - T-shirt, Rouge, Grand, 7

- `(ColorId, SizeId, StyleId)` – Groupé par combinaison de `ColorId`, `SizeId` et `StyleId`

    - T-shirt, Noir, Petit, Ample, 1
    - T-shirt, Noir, Petit, Normal, 2
    - T-shirt, Noir, Grand, Ample, 3
    - T-shirt, Noir, Grand, Normal, 4
    - T-shirt, Rouge, Petit, Ample, 5
    - T-shirt, Rouge, Petit, Normal, 6
    - T-shirt, Rouge, Grand, Normal, 7

> [!NOTE]
> Les dimensions de base définies dans la configuration de la partition ne doivent pas être définies dans les configurations d’index.

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Configuration de la réservation (facultatif)

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

La configuration de la réservation est requise si vous souhaitez utiliser la fonction de réservation provisoire. La configuration se compose de deux parties fondamentales :

- Mappage de réservation provisoire
- Hiérarchie de réservation provisoire

### <a name="soft-reservation-mapping"></a>Mappage de réservation provisoire

Lorsque vous effectuerez une réservation, vous souhaiterez peut-être savoir si le stock disponible est actuellement disponible pour la réservation. La validation est liée à une mesure calculée qui représente une formule de calcul d’une combinaison de mesures physiques.

Par exemple, une mesure de réservation est basée sur la mesure physique `SoftReservOrdered` de la source de données `iv` (visibilité des stocks). Dans ce cas, vous pouvez configurer la mesure calculée `AvailableToReserve` de la source de données `iv` comme indiqué ici.

| Type de calcul | Source de données | Mesure physique |
|---|---|---|
| Ajout | `fno` | `AvailPhysical` |
| Ajout | `pos` | `Inbound` |
| Soustraction | `pos` | `Outbound` |
| Soustraction | `iv` | `SoftReservOrdered` |

Configurez ensuite un mappage de réservation provisoire pour fournir un mappage de la mesure de réservation `SoftReservOrdered` à la mesure calculée `AvailableToReserve`.

| Source de données Mesure physique | Mesure physique | Source de données Disponible à la réservation | Mesure calculée Disponible à la réservation |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

Maintenant, lorsque vous réserverez sur `SoftReservOrdered`, la visibilité des stocks trouvera automatiquement `AvailableToReserve` et sa formule de calcul associée pour effectuer la validation de la réservation.

Par exemple, vous disposez du stock disponible suivant dans la visibilité des stocks.

```json
{
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservOrdered": 90
        },
        "fno": {
            "availphysical": 70.0,
        },
        "pos": {
            "inbound": 50.0,
            "outbound": 20.0
        }
    }
}
```

Dans ce cas, le calcul suivant s’applique :

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` – `pos.outbound` – `iv.SoftReservOrdered`  
= 70 + 50 – 20 – 90  
= 10

Par conséquent, si vous essayez de faire des réservations sur `iv.SoftReservOrdered` et que la quantité est inférieure ou égale à `AvailableToReserve` (10), vous pouvez faire la réservation.

### <a name="soft-reservation-hierarchy"></a>Hiérarchie de réservation provisoire

La hiérarchie de réservation décrit la séquence de dimensions qui doit être spécifiée lors des réservations. EIle fonctionne de la même manière que la hiérarchie d’index des produits pour les requêtes de stock disponible.

La hiérarchie de réservation est indépendante de la hiérarchie d’index de produits. Cette indépendance vous permet de mettre en œuvre une gestion des catégories où les utilisateurs peuvent décomposer les dimensions en détails pour spécifier les exigences nécessaires pour effectuer des réservations plus précises.

Voici un exemple d’une hiérarchie de réservation provisoire.

| Dimension de base | Hiérarchie  |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

Dans cet exemple, vous pouvez effectuer une réservation dans les séquences de dimensions suivantes :

- `()` – Aucune dimension n’est spécifiée.
- `(SiteId)`
- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

Une séquence de dimensions valide doit suivre strictement la hiérarchie de réservation, dimension par dimension. Par exemple, la séquence hiérarchique `(SiteId, LocationId, SizeId)` n’est pas valide, car `ColorId` est manquant.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Exemple de configuration par défaut

Lors de sa phase d’initialisation, la visibilité des stocks définit une configuration par défaut. Vous pouvez modifier la configuration selon vos besoins.

### <a name="data-source-configuration"></a>Configuration de la source de données

#### <a name="configuration-of-the-iv-data-source"></a>Configuration de la source de données iv

Cette section décrit comment la source de données `iv` est configurée.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>Mesures physiques configurées pour la source de données iv

Les mesures physiques suivantes sont configurées pour la source de données `iv` :

- `Ordered`
- `SoftReservPhysical`
- `SoftReservOrdered`
- `ReservOrdered`
- `ReservPhysical`

##### <a name="orderedtotal-calculated-measure"></a>Mesure calculée OrderedTotal

La mesure calculée `OrderedTotal` est configurée pour la source de données `iv` comme illustré dans le tableau suivant.

| Type de calcul | Source de données | Mesure physique |
|---|---|---|
| Ajout | `fno` | `Ordered` |
| Ajout | `fno` | `Arrived` |
| Ajout | `iv` | `Ordered` |

##### <a name="onhand-calculated-measure"></a>Mesure calculée OnHand

La mesure calculée `OnHand` est configurée pour la source de données `iv` comme illustré dans le tableau suivant.

| Type de calcul | Source de données | Mesure physique |
|---|---|---|
| Ajout | `fno` | `PhysicalInvent` |
| Ajout | `iom` | `OnHand` |
| Ajout | `erp` | `Unrestricted` |
| Ajout | `erp` | `QualityInspection` |
| Ajout | `pos` | `PosInbound` |
| Soustraction | `pos` | `PosOutbound` |

##### <a name="reservedtotal-calculated-measure"></a>Mesure calculée ReservedTotal

La mesure calculée `ReservedTotal` est configurée pour la source de données `iv` comme illustré dans le tableau suivant.

| Type de calcul | Source de données | Mesure physique |
|---|---|---|
| Ajout | `fno` | `ReservPhysical` |
| Ajout | `fno` | `ReservOrdered` |
| Ajout | `iv` | `SoftReservPhysical` |
| Ajout | `iv` | `SoftReservOrdered` |
| Ajout | `iv` | `ReservPhysical` |
| Ajout | `iv` | `ReservOrdered` |

##### <a name="softreserved-calculated-measure"></a>Mesure calculée SoftReserved

La mesure calculée `SoftReserved` est configurée pour la source de données `iv` comme illustré dans le tableau suivant.

| Type de calcul | Source de données | Mesure physique |
|---|---|---|
| Ajout | `iv` | `SoftReservPhysical` |
| Ajout | `iv` | `SoftReservOrdered` |

##### <a name="hardreserved-calculated-measure"></a>Mesure calculée HardReserved

La mesure calculée `HardReserved` est configurée pour la source de données `iv` comme illustré dans le tableau suivant.

| Type de calcul | Source de données | Mesure physique |
|---|---|---|
| Ajout | `fno` | `ReservPhysical` |
| Ajout | `fno` | `ReservOrdered` |
| Ajout | `iv` | `ReservPhysical` |
| Ajout | `iv` | `ReservOrdered` |

##### <a name="openorder-calculated-measure"></a>Mesure calculée OpenOrder

La mesure calculée `OpenOrder` est configurée pour la source de données `iv` comme illustré dans le tableau suivant.

| Type de calcul | Source de données | Mesure physique |
|---|---|---|
| Ajout | `fno` | `OnOrder` |
| Ajout | `iom` | `OnOrder` |

##### <a name="onhandavailable-calculated-measure"></a>Mesure calculée OnHandAvailable

La mesure calculée `OnHandAvailable` est configurée pour la source de données `iv` comme illustré dans le tableau suivant.

| Type de calcul | Source de données | Mesure physique |
|---|---|---|
| Ajout | `fno` | `PhysicalInvent` |
| Ajout | `iom` | `OnHand` |
| Ajout | `erp` | `Unrestricted` |
| Ajout | `erp` | `QualityInspection` |
| Ajout | `pos` | `PosInbound` |
| Soustraction | `fno` | `ReservPhysical` |
| Soustraction | `iv` | `SoftReservPhysical` |
| Soustraction | `pos` | `PosOutbound` |

##### <a name="availabletoreserve-calculated-measure"></a>Mesure calculée AvailableToReserve

La mesure calculée `AvailableToReserve` est configurée pour la source de données `iv` comme illustré dans le tableau suivant.

| Type de calcul | Source de données | Mesure physique |
|---|---|---|
| Ajout | `fno` | `PhysicalInvent` |
| Ajout | `iom` | `OnHand` |
| Ajout | `erp` | `Unrestricted` |
| Ajout | `erp` | `QualityInspection` |
| Ajout | `pos` | `PosInbound` |
| Ajout | `fno` | `Ordered` |
| Ajout | `fno` | `Arrived` |
| Ajout | `iv` | `Ordered` |
| Soustraction | `fno` | `ReservPhysical` |
| Soustraction | `fno` | `ReservOrdered` |
| Soustraction | `iv` | `SoftReservPhysical` |
| Soustraction | `iv` | `SoftReservOrdered` |
| Soustraction | `iv` | `ReservPhysical` |
| Soustraction | `iv` | `ReservOrdered` |
| Soustraction | `pos` | `PosOutbound` |

##### <a name="inventorysupply-calculated-measure"></a>Mesure calculée InventorySupply

La mesure calculée `InventorySupply` est configurée pour la source de données `iv` comme illustré dans le tableau suivant.

| Type de calcul | Source de données | Mesure physique |
|---|---|---|
| Ajout | `fno` | `Ordered` |
| Ajout | `fno` | `Arrived` |
| Ajout | `iv` | `Ordered` |
| Ajout | `fno` | `PhysicalInvent` |
| Ajout | `iom` | `OnHand` |
| Ajout | `erp` | `Unrestricted` |
| Ajout | `erp` | `QualityInspection` |
| Ajout | `pos` | `PosInbound` |
| Soustraction | `pos` | `PosOutbound` |

##### <a name="inventorydemand-calculated-measure"></a>Mesure calculée InventoryDemand

La mesure calculée `InventoryDemand` est configurée pour la source de données `iv` comme illustré dans le tableau suivant.

| Type de calcul | Source de données | Mesure physique |
|---|---|---|
| Ajout | `fno` | `OnOrder` |
| Ajout | `iom` | `OnOrder` |
| Ajout | `iv` | `SoftReservPhysical` |
| Ajout | `iv` | `SoftReservOrdered` |
| Ajout | `fno` | `ReservPhysical` |
| Ajout | `fno` | `ReservOrdered` |
| Ajout | `iv` | `ReservPhysical` |
| Ajout | `iv` | `ReservOrdered` |

#### <a name="configuration-of-the-fno-data-source"></a>Configuration de la source de données fno

Cette section décrit comment la source de données `fno` est configurée.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>Mappages de dimensions pour la source de données fno

Les mappages de dimensions répertoriés dans le tableau suivant sont configurés pour la source de données `fno`.

| Dimension externe | Dimension de base |
|---|---|
| `InventBatchId` | `BatchId` |
| `InventColorId` | `ColorId` |
| `InventLocationId` | `LocationId` |
| `InventSerialId` | `SerialId` |
| `InventSiteId` | `SiteId` |
| `InventSizeId` | `SizeId` |
| `InventStatusId` | `StatusId` |
| `InventStyleId` | `StyleId` |
| `LicensePlateId` | `LicensePlateId` |
| `WMSLocationId` | `WMSLocationId` |
| `WMSPalletId` | `WMSPalletId` |
| `ConfigId` | `ConfigId` |
| `InventVersionId` | `VersionId` |
| `InventDimension1` | `CustomDimension1` |
| `InventDimension2` | `CustomDimension2` |
| `InventDimension3` | `CustomDimension3` |
| `InventDimension4` | `CustomDimension4` |
| `InventDimension5` | `CustomDimension5` |
| `InventDimension6` | `CustomDimension6` |
| `InventDimension7` | `CustomDimension7` |
| `InventDimension8` | `CustomDimension8` |
| `InventDimension9` | `CustomDimension9` |
| `InventDimension10` | `CustomDimension10` |
| `InventDimension11` | `CustomDimension11` |
| `InventDimension12` | `CustomDimension12` |

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>Mesures physiques configurées pour la source de données fno

Les mesures physiques suivantes sont configurées pour la source de données `fno` :

- `Ordered`
- `Arrived`
- `AvailPhysical`
- `PhysicalInvent`
- `ReservPhysical`
- `ReservOrdered`
- `OnOrder`

#### <a name="configuration-of-the-pos-data-source"></a>Configuration de la source de données pos

Cette section décrit comment la source de données `pos` est configurée.

##### <a name="physical-measures-for-the-pos-data-source"></a>Mesures physiques pour la source de données pos

Les mesures physiques suivantes sont configurées pour la source de données `pos` :

- `PosInbound`
- `PosOutbound`

##### <a name="availquantity-calculated-measure"></a>Mesure calculée AvailQuantity

La mesure calculée `AvailQuantity` est configurée pour la source de données `pos` comme illustré dans le tableau suivant.

| Type de calcul | Source de données | Mesure physique |
|---|---|---|
| Ajout | `fno` | `AvailPhysical` |
| Ajout | `pos` | `PosInbound` |
| Soustraction | `pos` | `PosOutbound` |

#### <a name="configuration-of-the-iom-data-source"></a>Configuration de la source de données iom

Les mesures physiques suivantes sont configurées pour la source de données `iom` (intelligent order management) :

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>Configuration de la source de données erp

Les mesures physiques suivantes sont configurées pour la source de données `erp` (enterprise resource planning) :

- `Unrestricted`
- `QualityInspection`

### <a name="partition-configuration"></a>Configuration de la partition

Le tableau suivant montre la configuration de partition par défaut.

| Dimension de base | Hiérarchie  |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

### <a name="index-configuration"></a>Configuration de l’index

Le tableau suivant montre la configuration d’index par défaut.

| Numéro d’ensemble | Dimension | Hiérarchie  |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

### <a name="reservation-configuration"></a>Configuration de la réservation

Cette section décrit la configuration de réservation par défaut.

#### <a name="reservation-mapping"></a>Mappage de réservations

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Le tableau suivant montre le mappage de réservations par défaut.

| Source de données Mesure physique | Mesure physique | Source de données Disponible à la réservation | Mesure calculée Disponible à la réservation |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>Hiérarchie de réservation

Le tableau suivant montre la hiérarchie de réservation par défaut.

| Dimension de base | Hiérarchie  |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |
| `BatchId` | 6 |
| `SerialId` | 7 |
| `StatusId` | 8 |
| `LicensePlateId` | 9 |
| `WMSLocationId` | 10 |
| `WMSPalletId` | 11 |
| `ConfigId` | 12 |
| `VersionId` | 13 |
| `CustomDimension1` | 14 |
| `CustomDimension2` | 15 |
| `CustomDimension3` | 16 |
| `CustomDimension4` | 17 |
| `CustomDimension5` | 18 |
| `CustomDimension6` | 19 |
| `CustomDimension7` | 20 |
| `CustomDimension8` | 21 |
| `CustomDimension9` | 22 |
| `CustomDimension10` | 23 |
| `CustomDimension11` | 24 |
| `CustomDimension12` | 25 |
| `ExtendedDimension1` | 26 |
| `ExtendedDimension2` | 27 |
| `ExtendedDimension3` | 28 |
| `ExtendedDimension4` | 29 |
| `ExtendedDimension5` | 30 |
| `ExtendedDimension6` | 31 |
| `ExtendedDimension7` | 32 |
| `ExtendedDimension8` | 33 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
