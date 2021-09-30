---
title: Configurer la visibilité du stock
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
ms.openlocfilehash: 27dfc3f431fdfc1ec5c2cad2c3458b11c94189c3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474674"
---
# <a name="configure-inventory-visibility"></a>Configurer la visibilité du stock

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Cette rubrique décrit comment configurer la visibilité des stocks à l'aide de l'application Visibilité des stocks dans Power Apps.

## <a name="introduction"></a><a name="introduction"></a>Introduction

Avant de commencer à travailler avec la visibilité des stocks, vous devez effectuer la configuration suivante, comme décrit dans cette rubrique :

- [Configuration de la source de données](#data-source-configuration)
- [Configuration de la partition](#partition-configuration)
- [Configuration de la hiérarchie d’index des produits](#index-configuration)
- [Configuration de la réservation (facultatif)](#reservation-configuration)
- [Exemple de configuration par défaut](#default-configuration-sample)

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer, installez et configurez le complément de visibilité des stocks comme décrit dans [Installer et configurer la visibilité des stocks](inventory-visibility-setup.md).

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>Activer les fonctionnalités de visibilité des stocks dans la gestion des fonctionnalités de Power Apps

Le complément de visibilité des stocks ajoute plusieurs nouvelles fonctionnalités à votre installation Power Apps. Par défaut, ces fonctionnalités sont désactivées. Pour les utiliser, ouvrez la page **Configuration** dans Power Apps, puis, dans l’onglet **Gestion des fonctionnalités**, activez les fonctionnalités suivantes.

- *OnHandReservation*
- *OnHandMostSpecificBackgroundService*

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Rechercher le point de terminaison de service

Si vous ne connaissez pas le bon point de terminaison de service de visibilité des stocks, ouvrez la page **Configuration** dans Power Apps, puis sélectionnez **Afficher le point de terminaison de service** dans le coin supérieur droit. La page affichera le bon point de terminaison de service.

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>La page Configuration de l'application Visibilité des stocks

Dans Power Apps, la page **Configuration** de [l'application Visibilité des stocks](inventory-visibility-power-platform.md) vous permet de définir la configuration du stock disponible et la configuration des réservations provisoires. Une fois le complément installé, la configuration par défaut inclut la valeur de Microsoft Dynamics 365 Supply Chain Management (la source de données `fno`). Vous pouvez examiner les paramètres par défaut. De plus, en fonction des besoins de votre entreprise et des exigences de validation de stock de votre système externe, vous pouvez modifier la configuration pour standardiser la manière dont les modifications de stock peuvent être validées, organisées et interrogées sur les multiples systèmes. Les sections restantes de cette rubrique expliquent comment utiliser chaque partie de la page **Configuration**.

Une fois la configuration terminée, veillez à sélectionner **Mettre à jour la configuration** dans l’application.

## <a name="data-source-configuration"></a>Configuration de la source de données

Chaque source de données représente un système d’où proviennent vos données. Les exemples de noms de source de données incluent `fno` (qui signifie « Dynamics 365 Finance and Operations ») et `pos` (qui signifie « point de vente »). Par défaut, Supply Chain Management est configuré comme source de données par défaut (`fno`) dans la visibilité des stocks.

> [!NOTE]
> La source de données `fno` est réservée pour Dynamics 365 Supply Chain Management.

Pour ajouter une source de données, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Visibilité des stocks**.
1. Ouvrez la page **Configuration**.
1. Dans l’onglet **Source de données**, sélectionnez **Nouvelle source de données** pour ajouter une source de données.

> [!NOTE]
> Lorsque vous ajoutez une source de données, assurez-vous de valider le nom de votre source de données, les mesures physiques et les mappages de dimensions avant de mettre à jour la configuration pour le service de visibilité des stocks. Vous ne pourrez plus modifier ces paramètres après avoir sélectionné **Mettre à jour la configuration**.

La configuration de la source de données comprend les éléments suivants :

- Dimensions (mappage des dimensions)
- Mesures physiques
- Mesures calculées

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimensions (mappage des dimensions)

Le but de la configuration des dimensions est de standardiser l’intégration multi-système pour les événements et requêtes de publication, en fonction de combinaisons de dimensions. La visibilité des stocks fournit une liste de dimensions de base qui peuvent être mappées à partir des dimensions de votre source de données. Trente-trois dimensions sont disponibles pour le mappage.

- Par défaut, si vous utilisez Supply Chain Management comme l’une de vos sources de données, 13 dimensions sont mappées aux dimensions standard de Supply Chain Management. Douze autres dimensions (`inventDimension1` à `inventDimension12`) sont mappées à des dimensions personnalisées dans Supply Chain Management. Les huit dimensions restantes sont des dimensions étendues que vous pouvez mapper à des sources de données externes.
- Si vous n’utilisez pas Supply Chain Management comme l’une de vos sources de données, vous pouvez librement mapper les dimensions. Le tableau suivant présente la liste complète des dimensions disponibles.

> [!NOTE]
> Si votre dimension ne figure pas dans la liste des dimensions par défaut et que vous utilisez une source de données externe, nous vous recommandons d’utiliser `ExtendedDimension1` à `ExtendedDimension8` pour effectuer le mappage.

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
| Extension | `ExtendedDimension1` à `ExtendedDimension8` |
| Système | `Empty` |

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

Pour ajouter des mappages de dimensions, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Visibilité des stocks**.
1. Ouvrez la page **Configuration**.
1. Sur l’onglet **Source de données**, dans la section **Mappages de dimensions**, sélectionnez **Ajouter** pour ajouter des mappages de dimensions.
    ![Ajout des mappages de dimensions](media/inventory-visibility-dimension-mapping.png "Ajout des mappages de dimensions")

1. Dans le champ **Nom de la dimension**, spécifiez la dimension source.
1. Dans le champ **Vers dimension de base**, sélectionnez la dimension dans la visibilité des stocks que vous souhaitez mapper.
1. Sélectionnez **Enregistrer**.

Par exemple, si votre source de données inclut une dimension de couleur de produit, vous pouvez la mapper à la dimension de base `ColorId` pour ajouter une dimension personnalisée `ProductColor` dans la source de données `exterchannel`. Elle sera ensuite mappée à la dimension de base `ColorId`.

### <a name="physical-measures"></a>Mesures physiques

Lorsqu’une source de données valide une modification de stock dans la visibilité des stocks, cette modification est validée en utilisant les *mesures physiques*. Les mesures physiques modifient la quantité et reflètent le statut des stocks. Vous pouvez définir vos propres mesures physiques en fonction de vos besoins. Les requêtes peuvent être basées sur les mesures physiques.

La visibilité des stocks fournit une liste de mesures physiques par défaut qui sont liées à Supply Chain Management (la source de données `fno`). Ces mesures physiques par défaut sont extraites des statuts des transactions de stock sur la page **Liste stocks disponibles** dans Supply Chain Management (**Gestion des stocks \> Recherches et états \> Liste stocks disponibles**). Le tableau suivant fournit un exemple de mesures physiques.

| Nom de la mesure physique | Description |
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

Si la source de données est Supply Chain Management, vous n’avez pas besoin de recréer les mesures physiques par défaut. Cependant, pour les sources de données externes, vous pouvez créer de nouvelles mesures physiques en suivant ces étapes.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Visibilité des stocks**.
1. Ouvrez la page **Configuration**.
1. Sur l’onglet **Source de données**, dans la section **Mesures physiques**, sélectionnez **Ajouter**, spécifiez un nom de mesure source et enregistrez vos modifications.

### <a name="calculated-measures"></a>Mesures calculées

Vous pouvez utiliser la visibilité des stocks pour interroger à la fois les mesures physiques de stock et les *mesures calculées personnalisées*. Les mesures calculées fournissent une formule de calcul personnalisée qui consiste en une combinaison de mesures physiques. Cette fonctionnalité vous permet de définir un ensemble de mesures physiques qui seront ajoutées, et/ou un ensemble de mesures physiques qui seront soustraites, afin de former la mesure personnalisée.

La configuration vous permet de définir un ensemble de modificateurs qui sont ajoutés ou soustraits pour obtenir la quantité de sortie agrégée totale.

Pour configurer une mesure calculée personnalisée, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Visibilité des stocks**.
1. Ouvrez la page **Configuration**.
1. Dans l’onglet **Mesure calculée**, sélectionnez **Nouvelle mesure de calcul** pour ajouter une mesure calculée. Ensuite, définissez les champs comme décrit dans le tableau suivant.

    | Champ | Valeur |
    |---|---|
    | Nouveau nom de la mesure calculée | Entrez le nom de la mesure calculée. |
    | Source de données | Le système d’interrogation est une source de données. |
    | Source de données du modificateur | Entrez la source de données du modificateur. |
    | Modificateur | Entrez le nom du modificateur. |
    | Type de modificateur | Sélectionnez le type de modificateur (*Addition* ou *Soustraction*). |

Par exemple, vous pouvez obtenir le résultat de requête suivant.

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

Le résultat `MyCustomAvailableforReservation`, basé sur la configuration du calcul dans les mesures personnalisées, est 100 + 50 – 10 + 80 – 20 + 90 + 30 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Configuration de la partition

La configuration de la partition consiste en une combinaison de dimensions de base. Elle définit le modèle de distribution des données. Les opérations de données dans la même partition prennent en charge des performances élevées et ne coûtent pas trop cher. Par conséquent, de bons modèles de partition peuvent apporter des avantages significatifs.

La visibilité des stocks fournit la configuration de partition par défaut suivante.

| Dimension de base | Hiérarchie |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

> [!NOTE]
> La configuration de partition par défaut est à titre indicatif uniquement. Vous n’avez pas besoin de la définir dans la visibilité des stocks. Actuellement, la mise à niveau de la configuration de partition n’est pas prise en charge.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Configuration de la hiérarchie d’index des produits

La plupart du temps, la requête de stock disponible ne sera pas seulement au niveau « total » le plus élevé. Au lieu de cela, vous souhaiterez peut-être également voir les résultats agrégés en fonction des dimensions de stock.

La visibilité des stocks offre de la flexibilité en vous permettant de configurer les _index_. Ces index sont basés sur une dimension ou une combinaison de dimensions. Un index se compose d’un *numéro d’ensemble*, d’une *dimension* et d’une *hiérarchie*, tel que défini dans le tableau suivant.

| Nom | Description |
|---|---|
| Numéro d’ensemble | Les dimensions appartenant au même ensemble (index) seront regroupées et le même numéro d’ensemble leur sera attribué. |
| Dimension | Dimensions de base sur lesquelles le résultat de requête est agrégé. |
| Hiérarchie | La hiérarchie est utilisée pour définir les combinaisons de dimensions prises en charge qui peuvent être interrogées. Par exemple, vous configurez un ensemble de dimensions qui a une séquence hiérarchique de `(ColorId, SizeId, StyleId)`. Dans ce cas, le système prend en charge les requêtes sur quatre combinaisons de dimensions. La première combinaison est vide, la seconde est `(ColorId)`, la troisième est `(ColorId, SizeId)` et la quatrième est `(ColorId, SizeId, StyleId)`. Les autres combinaisons ne sont pas prises en charge. Pour plus d’informations, voir les exemples suivants. |

Pour paramétrer votre index de hiérarchie des produits, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Visibilité des stocks**.
1. Ouvrez la page **Configuration**.
1. Sur l’onglet **Index de hiérarchie des produits**, dans la section **Mappages des dimensions**, sélectionnez **Ajouter** pour ajouter des mappages de dimensions.
1. Par défaut, une liste d’index est fournie. Pour modifier un index existant, sélectionnez **Modifier** ou **Ajouter** dans la section de l’index approprié. Pour créer un ensemble d’index, sélectionnez **Nouvel ensemble d’index**. Pour chaque ligne de chaque ensemble d’index, dans le champ **Dimension**, faites votre sélection dans la liste des dimensions de base. Les valeurs des champs suivants sont générées automatiquement :

    - **Numéro d’ensemble** : les dimensions appartenant au même groupe (index) seront regroupées et le même numéro d’ensemble leur sera attribué.
    - **Hiérarchie** : la hiérarchie est utilisée pour définir les combinaisons de dimensions prises en charge qui peuvent être interrogées dans un groupe de dimensions (index). Par exemple, si vous configurez un groupe de dimensions ayant une séquence hiérarchique *Style*, *Couleur* et *Taille*, le système prend en charge le résultat de trois groupes de requêtes. Le premier groupe concerne uniquement le style. Le deuxième groupe est une combinaison de style et de couleur. Et le troisième groupe est une combinaison de style, couleur et taille. Les autres combinaisons ne sont pas prises en charge.

### <a name="example"></a>Exemple

Cette section fournit un exemple qui montre comment fonctionne la hiérarchie.

Le tableau suivant fournit une liste des stocks disponibles pour cet exemple.

| Article | ColorId | SizeId | StyleId | Quantité |
|---|---|---|---|---|
| T-shirt | Noir | Petite | Paysage | 1 |
| T-shirt | Noir | Petite | Régulier | 2 |
| T-shirt | Noir | Etendu | Paysage | 3 |
| T-shirt | Noir | Etendu | Régulier | 4 |
| T-shirt | Rouge | Petite | Paysage | 5 |
| T-shirt | Rouge | Petite | Régulier | 6 |
| T-shirt | Rouge | Etendu | Régulier | 7 |

Le tableau suivant montre comment la hiérarchie d’index est configurée.

| Numéro d’ensemble | Dimension | Hiérarchie |
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
> 
> Si vous devez interroger uniquement le stock qui est agrégé par toutes les combinaisons de dimensions, vous pouvez configurer un index unique qui contient la dimension de base `Empty`.

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Configuration de la réservation (facultatif)

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

La configuration de la réservation est requise si vous souhaitez utiliser la fonction de réservation provisoire. La configuration se compose de deux parties fondamentales :

- Mappage de réservation provisoire
- Hiérarchie de réservation provisoire

### <a name="soft-reservation-mapping"></a>Mappage de réservation provisoire

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Lorsque vous effectuerez une réservation, vous souhaiterez peut-être savoir si le stock disponible est actuellement disponible pour la réservation. La validation est liée à une mesure calculée qui représente une formule de calcul d’une combinaison de mesures physiques.

En configurant le mappage de la mesure physique à la mesure calculée, vous activez le service de visibilité des stocks pour valider automatiquement la disponibilité de la réservation, en fonction de la mesure physique.

Avant de configurer ce mappage, les mesures physiques, les mesures calculées et leurs sources de données doivent être définies dans les onglets **Source de données** et **Mesure calculée** de la page **Configuration** dans Power Apps (comme décrit plus haut dans cette rubrique).

Pour définir le mappage de réservation provisoire, procédez comme suit.

1. Définissez la mesure physique qui sert de mesure de réservation provisoire (par exemple, `SoftReservOrdered`).
1. Dans l’onglet **Mesure calculée** de la page **Configuration**, définissez la mesure calculée *disponible à la réservation* (AFR) qui contient la formule de calcul AFR que vous souhaitez mapper à la mesure physique. Par exemple, vous pouvez configurer `AvailableToReserve` (disponible à la réservation) afin qu’il soit mappé sur la mesure physique `SoftReservOrdered` précédemment définie. De cette façon, vous pouvez rechercher quelles quantités ayant le statut de stock `SoftReservOrdered` seront disponibles à la réservation. Le tableau suivant présente la formule de calcul AFR.

    | Type de calcul | Source de données | Mesure physique |
    |---|---|---|
    | Ajout | `fno` | `AvailPhysical` |
    | Ajout | `pos` | `Inbound` |
    | Soustraction | `pos` | `Outbound` |
    | Soustraction | `iv` | `SoftReservOrdered` |

    Nous vous recommandons de configurer la mesure calculée de sorte qu'elle contienne la mesure physique sur laquelle la mesure de la réservation est basée. De cette manière, la quantité de mesure calculée sera affectée par la quantité de mesure de la réservation. Par conséquent, dans cet exemple, la mesure calculée `AvailableToReserve` de la source de données `iv` doit contenir la mesure physique `SoftReservOrdered` issue de `iv` en tant que composant.

1. Ouvrez la page **Configuration**.
1. Dans l’onglet **Mappage de réservation provisoire**, configurez le mappage de la mesure physique à la mesure calculée. Pour l’exemple précédent, vous pouvez utiliser les paramètres suivants pour mapper `AvailableToReserve` à la mesure physique `SoftReservOrdered` précédemment définie.

    | Source de données Mesure physique | Mesure physique | Source de données Disponible à la réservation | Mesure calculée Disponible à la réservation |
    |---|---|---|---|
    | `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > Si vous ne pouvez pas modifier l'onglet **Mappage de réservation provisoire**, vous devez peut-être activer la fonctionnalité *OnHandReservation* sur l’onglet **Gestion des fonctionnalités**.

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

> [!NOTE]
> Lorsque vous appelez l'API de réservation, vous pouvez contrôler la validation de la réservation en spécifiant le paramètre booléen `ifCheckAvailForReserv` dans le corps de la requête. Une valeur `True` signifie que la validation est requise, alors qu'une valeur `False` signifie que la validation n'est pas requise. La valeur par défaut est `True`.

### <a name="soft-reservation-hierarchy"></a>Hiérarchie de réservation provisoire

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

La hiérarchie de réservation décrit la séquence de dimensions qui doit être spécifiée lors des réservations. EIle fonctionne de la même manière que la hiérarchie d’index des produits pour les requêtes de stock disponible.

La hiérarchie de réservation est indépendante de la hiérarchie d’index de produits. Cette indépendance vous permet de mettre en œuvre une gestion des catégories où les utilisateurs peuvent décomposer les dimensions en détails pour spécifier les exigences nécessaires pour effectuer des réservations plus précises. Votre hiérarchie de réservation provisoire doit contenir `SiteId` et `LocationId` en tant que composants, car ils construisent la configuration de la partition. Lorsque vous effectuez la réservation, vous devez spécifier une partition pour le produit.

Voici un exemple d’une hiérarchie de réservation provisoire.

| Dimension de base | Hiérarchie |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

Dans cet exemple, vous pouvez effectuer une réservation dans les séquences de dimensions suivantes. Vous devez spécifier une partition pour le produit lorsque vous effectuez la réservation. Par conséquent, la hiérarchie de base que vous pouvez utiliser est `(SiteId, LocationId)`.

- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

Une séquence de dimensions valide doit suivre strictement la hiérarchie de réservation, dimension par dimension. Par exemple, la séquence hiérarchique `(SiteId, LocationId, SizeId)` n’est pas valide, car `ColorId` est manquant.

## <a name="complete-and-update-the-configuration"></a>Terminer et mettre à jour la configuration

Une fois la configuration terminée, vous devez valider toutes les modifications apportées à la visibilité des stocks. Pour valider les modifications, sélectionnez **Mettre à jour la configuration** dans le coin supérieur droit de la page **Configuration** dans Power Apps.

La première fois que vous sélectionnez **Mettre à jour la configuration**, le système demande vos informations d’identification.

- **Identité du client** : ID d’application Azure que vous avez créé pour la visibilité des stocks.
- **ID de locataire** : ID de locataire Azure.
- **Clé secrète client** : clé secrète d’application Azure que vous avez créée pour la visibilité des stocks.

Une fois que vous êtes connecté, la configuration est mise à jour dans le service de visibilité des stocks.

> [!NOTE]
> Assurez-vous de valider le nom de votre source de données, les mesures physiques et les mappages de dimensions avant de mettre à jour la configuration pour le service de visibilité des stocks. Vous ne pourrez plus modifier ces paramètres après avoir sélectionné **Mettre à jour la configuration**.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Exemple de configuration par défaut

Lors de sa phase d’initialisation, la visibilité des stocks définit une configuration par défaut, qui est détaillée ici. Vous pouvez modifier cette configuration selon vos besoins.

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

| Dimension de base | Hiérarchie |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

### <a name="index-configuration"></a>Configuration de l’index

Le tableau suivant montre la configuration d’index par défaut.

| Numéro d’ensemble | Dimension | Hiérarchie |
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

| Dimension de base | Hiérarchie |
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