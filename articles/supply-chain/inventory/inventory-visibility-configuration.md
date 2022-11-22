---
title: Configurer Inventory Visibility
description: Cet article décrit comment configurer la visibilité des stocks.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 915382c14cc9ba89b9d543cfd668a94cecbc0a55
ms.sourcegitcommit: 4f987aad3ff65fe021057ac9d7d6922fb74f980e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9765707"
---
# <a name="configure-inventory-visibility"></a>Configurer Inventory Visibility

[!include [banner](../includes/banner.md)]

Cet article décrit comment configurer la visibilité des stocks à l’aide de l’application Inventory Visibility dans Power Apps.

## <a name="introduction"></a><a name="introduction"></a>Introduction

Avant de commencer à travailler avec la visibilité des stocks, vous devez effectuer la configuration suivante, comme décrit dans cet article :

- [Configuration de la source de données](#data-source-configuration)
- [Configuration de la partition](#partition-configuration)
- [Configuration de la hiérarchie d’index des produits](#index-configuration)
- [Configuration de la réservation (facultatif)](#reservation-configuration)
- [Exemple de configuration par défaut](#default-configuration-sample)

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer, installez et configurez le complément de visibilité des stocks comme décrit dans [Installer et configurer la visibilité des stocks](inventory-visibility-setup.md).

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>La page Configuration de l’application Inventory Visibility

Dans Power Apps, la page **Configuration** de [l’application Inventory Visibility](inventory-visibility-power-platform.md) vous permet de définir la configuration du stock disponible et la configuration des réservations provisoires. Une fois le complément installé, la configuration par défaut inclut la valeur de Microsoft Dynamics 365 Supply Chain Management (la source de données `fno`). Vous pouvez examiner les paramètres par défaut. De plus, en fonction des besoins de votre entreprise et des exigences de validation de stock de votre système externe, vous pouvez modifier la configuration pour standardiser la manière dont les modifications de stock peuvent être validées, organisées et interrogées sur les multiples systèmes. Les sections restantes de cet article expliquent comment utiliser chaque partie de la page **Configuration**.

Une fois la configuration terminée, veillez à sélectionner **Mettre à jour la configuration** dans l’application.

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>Activer les fonctionnalités de visibilité des stocks dans la gestion des fonctionnalités de Power Apps

Le complément de visibilité des stocks ajoute plusieurs nouvelles fonctionnalités à votre installation Power Apps. Par défaut, ces fonctionnalités sont désactivées. Pour les utiliser, ouvrez la page **Configuration** et, sur l’onglet **Gestion des fonctionnalités**, activez les fonctionnalités suivantes selon vos besoins.

| Nom dans la Gestion des fonctionnalités | Description |
|---|---|
| *OnHandReservation* | Cette fonction vous permet de créer des réservations, consommer des réservations et/ou annuler la réservation de quantités en stock spécifiées à l’aide de la Inventory Visibility. Pour plus d’informations, voir [Réservation dans la visibilité des stocks](inventory-visibility-reservations.md). |
| *OnHandMostSpecificBackgroundService* | Cette fonctionnalité fournit un récapitulatif du stock pour les produits, avec toutes les dimensions. Les données récapitulatives du stock seront périodiquement synchronisées à partir de la visibilité des stocks. La fréquence de synchronisation par défaut est d’une fois toutes les 15 minutes et peut être réglée jusqu’à une fois toutes les 5 minutes. Pour plus d’informations, voir [Récapitulatif du stock](inventory-visibility-power-platform.md#inventory-summary). |
| *onHandIndexQueryPreloadBackgroundService* | Cette fonctionnalité permet de précharger les requêtes disponibles pour la visibilité des stocks pour assembler des listes de disponibilité avec des dimensions présélectionnées. La fréquence de synchronisation par défaut est une fois toutes les 15 minutes. Pour plus d’informations, voir [Précharger une requête de stock disponible simplifiée](inventory-visibility-power-platform.md#preload-streamlined-onhand-query). |
| *OnhandChangeSchedule* | Cette fonctionnalité facultative active les fonctionnalités de planning de changement du stock disponible et de quantité disponible à la vente (DAV). Pour plus d’informations, voir [Planning de changement du stock disponible et disponibilité à la vente de la Inventory Visibility](inventory-visibility-available-to-promise.md). |
| *Allocation* | Cette fonctionnalité facultative permet à Inventory Visibility d’avoir la possibilité de protéger les stocks (réservation) et de contrôler la survente. Pour plus d’informations, voir [Répartition de stock pour Inventory Visibility](inventory-visibility-allocation.md). |
| *Activer les articles d’entrepôt dans Inventory Visibility* | Cette fonctionnalité facultative permet à la Inventory Visibility de prendre en charge les articles activés pour les processus de gestion des entrepôts (articles WMS). Pour plus d’informations, voir [Prise en charge de la Inventory Visibility pour les articles WMS](inventory-visibility-whs-support.md). |

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Rechercher le point de terminaison de service

Si vous ignorez le point de terminaison correct du service Inventory Visibility, ouvrez la page **Configuration** dans Power Apps, puis sélectionnez **Afficher les détails du service** dans le coin supérieur droit. La page affichera le bon point de terminaison de service. Vous pouvez également trouver le point de terminaison dans Microsoft Dynamics Lifecycle Services, comme décrit dans [Rechercher le point de terminaison en fonction de votre environnement Lifecycle Services](inventory-visibility-api.md#endpoint-lcs).

> [!NOTE]
> L’utilisation d’un point de terminaison incorrect peut entraîner l’échec de l’installation d’Inventory Visibility et des erreurs lorsque Supply Chain Management est synchronisé avec Inventory Visibility. Si vous ne savez pas quel est votre point de terminaison, contactez votre administrateur système. Les URL de point de terminaison sont au format suivant : 
>
> `https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Configuration de la source de données

Chaque source de données représente un système d’où proviennent vos données. Les exemples de noms de source de données incluent `fno` (qui correspond à Supply Chain Management) et `pos` (qui signifie « point de vente »). Par défaut, Supply Chain Management est configuré comme source de données par défaut (`fno`) dans la visibilité des stocks.

> [!NOTE]
> La source de données `fno` est réservée pour Supply Chain Management. Si le complément Inventory Visibility est intégré dans un environnement Supply Chain Management, nous vous recommandons de ne pas supprimer les configurations liées à `fno` dans la source de données.

Pour ajouter une source de données, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Inventory Visibility**.
1. Ouvrez la page **Configuration**.
1. Dans l’onglet **Source de données**, sélectionnez **Nouvelle source de données** pour ajouter une source de données (par exemple, `ecommerce` ou un autre ID de source de données significatif).

> [!NOTE]
> Lorsque vous ajoutez une source de données, assurez-vous de valider le nom de votre source de données, les mesures physiques et les mappages de dimensions avant de mettre à jour la configuration pour le service de visibilité des stocks. Vous ne pourrez plus modifier ces paramètres après avoir sélectionné **Mettre à jour la configuration**.

La configuration de la source de données comprend les éléments suivants :

- Dimensions (mappage des dimensions)
- Mesures physiques
- Mesures calculées

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimensions (mappage des dimensions)

Le but de la configuration des dimensions est de standardiser l’intégration multi-système pour les événements et requêtes de publication, en fonction de combinaisons de dimensions. La visibilité des stocks fournit une liste de dimensions de base qui peuvent être mappées à partir des dimensions de votre source de données. Trente-trois dimensions sont disponibles pour le mappage.

- Si vous utilisez Supply Chain Management comme l’une de vos sources de données, 13 dimensions sont déjà mappées aux dimensions standard de Supply Chain Management par défaut. Les douze autres dimensions (de `inventDimension1` à `inventDimension12`) sont également mappées à des dimensions personnalisées dans Supply Chain Management. Les huit dimensions restantes (de `ExtendedDimension1` à `ExtendedDimension8`) sont des dimensions étendues que vous pouvez mapper à des sources de données externes.
- Si vous n’utilisez pas Supply Chain Management comme l’une de vos sources de données, vous pouvez librement mapper les dimensions. Le tableau suivant présente la liste complète des dimensions disponibles.

> [!NOTE]
> Si vous utilisez Supply Chain Management et modifiez les mappages de dimension par défaut entre Supply Chain Management et Inventory Visibility, la dimension modifiée ne synchronise pas les données. Ainsi, si votre dimension ne figure pas dans la liste des dimensions par défaut et que vous utilisez une source de données externe, nous vous recommandons d’utiliser `ExtendedDimension1` à `ExtendedDimension8` pour effectuer le mappage.

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
> Les types de dimension répertoriés dans le tableau précédent sont donnés à titre indicatif uniquement. Vous n’avez pas besoin de les définir dans la visibilité des stocks.
>
> Les dimensions de stock (personnalisées) peuvent être réservées pour Supply Chain Management. Dans ce cas, utilisez les dimensions étendues à la place.

Les systèmes externes peuvent accéder à la visibilité des stocks via ses API RESTful. Pour l’intégration, la visibilité des stocks vous permet de configurer la *source de données externe* et le mappage des *dimensions externes* aux *dimensions de base*. Voici un exemple d’une table de mappage des dimensions.

| Dimension externe | Dimension de base |
|---|---|
| `MyColorId` | `ColorId` |
| `MySizeId` | `SizeId` |
| `MyStyleId` | `StyleId` |
| `MyDimension1` | `ExtendedDimension1` |
| `MyDimension2` | `ExtendedDimension2` |

En configurant un mappage de dimensions, vous pouvez envoyer les dimensions externes directement à la visibilité des stocks. La visibilité des stocks convertira alors automatiquement les dimensions externes en dimensions de base.

Pour ajouter des mappages de dimensions, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Inventory Visibility**.
1. Ouvrez la page **Configuration**.
1. Dans l’onglet **Source de données**, sélectionnez la source de données dans laquelle vous souhaitez effectuer le mappage des dimensions. Ensuite, dans la section **Mises en correspondance de dimensions**, sélectionnez **Ajouter** pour ajouter les mises en correspondance de dimensions.

    ![Ajout des mappages de dimensions](media/inventory-visibility-dimension-mapping.png "Ajout des mappages de dimensions")

1. Dans le champ **Nom de la dimension**, spécifiez la dimension source.
1. Dans le champ **Vers dimension de base**, sélectionnez la dimension dans la visibilité des stocks que vous souhaitez mapper.
1. Cliquez sur **Enregistrer**.

Par exemple, vous avez déjà créé une source de données appelée `ecommerce` qui inclut une dimension de couleur du produit. Dans ce cas, pour faire la mise en correspondance, vous pouvez d’abord ajouter `ProductColor` au champ **Nom de la dimension** dans la source de données `ecommerce`, puis sélectionnez `ColorId` dans le champ **Vers dimension de base**.

### <a name="physical-measures"></a><a name="data-source-configuration-physical-measures"></a>Mesures physiques

Lorsqu’une source de données valide une modification de stock dans la visibilité des stocks, cette modification est validée en utilisant les *mesures physiques*. Les mesures physiques modifient la quantité et reflètent le statut des stocks. Vous pouvez définir vos propres mesures physiques selon vos besoins. Les requêtes peuvent être basées sur les mesures physiques.

Inventory Visibility fournit une liste de mesures physiques par défaut qui sont mappées à Supply Chain Management (la source de données `fno`). Ces mesures physiques par défaut sont extraites des statuts des transactions de stock sur la page **Liste stocks disponibles** dans Supply Chain Management (**Gestion des stocks \> Recherches et états \> Liste stocks disponibles**). Le tableau suivant fournit un exemple de mesures physiques.

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
| `Received` | Reçue |
| `Registered` | Enregistré |
| `ReservOrdered` | Commandé réservé |
| `ReservPhysical` | Physique réservé |

Si votre source de données est Supply Chain Management, inutile de recréer les mesures physiques par défaut. Cependant, pour les sources de données externes, vous pouvez créer de nouvelles mesures physiques en suivant ces étapes.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Inventory Visibility**.
1. Ouvrez la page **Configuration**.
1. Dans l’onglet **Source de données**, sélectionnez la source de données à laquelle ajouter des mesures physiques (par exemple, la source de données `ecommerce`). Puis, dans la section **Mesures physiques**, sélectionnez **Ajouter** et spécifiez le nom de la mesure (par exemple, `Returned` pour enregistrer les quantités retournées dans cette source de données dans Inventory Visibility). Enregistrez vos modifications.

### <a name="calculated-measures"></a>Mesures calculées

Vous pouvez utiliser la visibilité des stocks pour interroger à la fois les mesures physiques de stock et les *mesures calculées personnalisées*. Les mesures calculées fournissent une formule de calcul personnalisée qui consiste en une combinaison de mesures physiques. Cette fonctionnalité vous permet de définir un ensemble de mesures physiques qui seront ajoutées, et/ou un ensemble de mesures physiques qui seront soustraites, afin de former la mesure personnalisée.

> [!IMPORTANT]
> Une mesure calculée est une composition de mesures physiques. Sa formule ne peut inclure que des mesures physiques sans doublons, et non des mesures calculées.

La configuration permet de définir un ensemble de formules de mesure calculée qui inclut les modificateurs d’ajout ou de soustraction pour obtenir la quantité de sortie agrégée totale.

Pour configurer une mesure calculée personnalisée, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Inventory Visibility**.
1. Ouvrez la page **Configuration**.
1. Dans l’onglet **Mesure calculée**, sélectionnez **Nouvelle mesure de calcul** pour ajouter une mesure calculée.
1. Définissez les champs suivants pour la nouvelle mesure calculée :

    - **Nom de la nouvelle mesure calculée** – Entrez le nom de la mesure calculée.
    - **Source de données** : sélectionnez la source de données pour inclure la nouvelle mesure calculée. Le système d’interrogation est une source de données.

1. Sélectionnez **Ajouter** pour ajouter un modificateur à la nouvelle mesure calculée.
1. Définissez les champs suivants pour le nouveau modificateur :

    - **Modificateur** – Sélectionnez le type de modificateur (*Addition* ou *Soustraction*).
    - **Source de données** – Sélectionnez la source de données dans laquelle la mesure qui fournit la valeur du modificateur doit être trouvée.
    - **Mesure** – Sélectionnez le nom de la mesure (à partir de la source de données sélectionnée) qui fournit la valeur du modificateur.

1. Répétez les étapes 5 à 6 jusqu’à ce que vous ayez ajouté tous les modificateurs requis et terminé la formule de votre mesure calculée.
1. Cliquez sur **Enregistrer**.

Par exemple, une entreprise de mode opère à travers trois sources de données :

- `pos` : correspond au canal du magasin.
- `fno` : correspond à Supply Chain Management.
- `ecommerce` : correspond à votre canal web.

Sans mesures calculées, lorsque vous recherchez le produit D0002 (Armoire) sous le site 1, entrepôt 11 et une valeur de dimension `ColorID` définie sur `Red`, vous pouvez obtenir le résultat de requête suivant, qui affiche les quantités de stock sous chaque mesure physique préconfigurée. Cependant, vous n’avez pas de visibilité sur le total disponible pour les quantités de réservation sur l’ensemble de vos sources de données.

```json
[
    {
        "productId": "D0002",
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
            "ecommerce": {
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
| `CrossChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `received` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `scheduled` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `issued` | `Subtraction` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `reserved` | `Subtraction` |

Lorsque cette formule de calcul sera utilisée, le nouveau résultat de requête inclura la mesure personnalisée.

```json
[
    {
        "productId": "D0002",
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
            "ecommerce": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CrossChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

Le résultat `MyCustomAvailableforReservation`, basé sur la configuration du calcul dans les mesures personnalisées, est 100 + 50 – 10 + 80 – 20 + 90 + 30 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Configuration de la partition

Actuellement, la configuration de la partition se compose de deux dimensions de base (`SiteId` et `LocationId`) qui indiquent comment les données sont distribuées. Les opérations sous la même partition peuvent offrir des performances supérieures à moindre coût. Le tableau suivant affiche la configuration de partition par défaut fournie par le complément Inventory Visibility.

| Dimension de base | Hiérarchie |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

La solution inclut cette configuration de partition par défaut. Par conséquent, *vous n’avez pas à la définir vous-même*.

> [!IMPORTANT]
> Ne personnalisez pas la configuration de partition par défaut. Si vous la supprimez ou la modifiez, vous risquez de provoquer une erreur inattendue.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Configuration de la hiérarchie d’index des produits

La plupart du temps, la requête de stock disponible ne sera pas seulement au niveau « total » le plus élevé. Au lieu de cela, vous souhaiterez peut-être également voir les résultats agrégés en fonction des dimensions de stock.

Inventory Visibility offre de la flexibilité en vous permettant de configurer *index* pour améliorer les performances de vos requêtes. Ces index sont basés sur une dimension ou une combinaison de dimensions. Un index se compose d’un *numéro d’ensemble*, d’une *dimension* et d’une *hiérarchie*, tel que défini dans le tableau suivant.

| Nom | Description |
|---|---|
| Numéro d’ensemble | Les dimensions appartenant au même ensemble (index) seront regroupées et le même numéro d’ensemble leur sera attribué. |
| Dimension | Dimensions de base sur lesquelles le résultat de requête est agrégé. |
| Hiérarchie  | La hiérarchie vous permet d’augmenter les performances de combinaisons spécifiques de dimensions lorsqu’elles sont utilisées dans des paramètres de requête de filtrage et de regroupement. Par exemple, si vous configurez un ensemble de dimensions avec une séquence hiérarchique de `(ColorId, SizeId, StyleId)`, le système peut alors traiter plus rapidement les requêtes liées aux combinaisons à quatre dimensions. La première combinaison est vide, la seconde est `(ColorId)`, la troisième est `(ColorId, SizeId)` et la quatrième est `(ColorId, SizeId, StyleId)`. Les autres combinaisons ne seront pas accélérées. Les filtres ne sont pas limités par l’ordre, mais doivent être à l’intérieur de ces dimensions si vous souhaitez améliorer leurs performances. Pour plus d’informations, voir les exemples suivants. |

Pour paramétrer votre index de hiérarchie des produits, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Inventory Visibility**.
1. Ouvrez la page **Configuration**.
1. Sur l’onglet **Index de hiérarchie des produits**, dans la section **Mappages des dimensions**, sélectionnez **Ajouter** pour ajouter des mappages de dimensions.
1. Par défaut, une liste d’index est fournie. Pour modifier un index existant, sélectionnez **Modifier** ou **Ajouter** dans la section de l’index approprié. Pour créer un ensemble d’index, sélectionnez **Nouvel ensemble d’index**. Pour chaque ligne de chaque ensemble d’index, dans le champ **Dimension**, faites votre sélection dans la liste des dimensions de base. Les valeurs des champs suivants sont générées automatiquement :

    - **Numéro d’ensemble** : les dimensions appartenant au même groupe (index) seront regroupées et le même numéro d’ensemble leur sera attribué.
    - **Hiérarchie** : La hiérarchie vous permet d’augmenter les performances de combinaisons spécifiques de dimensions lorsqu’elles sont utilisées dans des paramètres de requête de filtrage et de regroupement.

> [!TIP]
> Voici quelques conseils à garder à l’esprit lors de la configuration de votre hiérarchie d’index :
>
> - Les dimensions de base définies dans la configuration de la partition ne doivent pas être définies dans les configurations d’index. Si une dimension de base est à nouveau définie dans la configuration de l’index, vous ne pourrez pas interroger par cet index.
> - Si vous devez interroger uniquement le stock qui est agrégé par toutes les combinaisons de dimensions, vous pouvez configurer un index unique qui contient la dimension de base `Empty`.

### <a name="example"></a>Exemple

Cette section fournit un exemple qui montre comment fonctionne la hiérarchie.

Le tableau suivant fournit une liste des stocks disponibles pour cet exemple.

| Article | ColorId | SizeId | StyleId | Quantity |
|---|---|---|---|---|
| D0002 | Noir | Petit | Paysage | 1 |
| D0002 | Noir | Petit | Régulier | 2 |
| D0002 | Noir | Grand | Paysage | 3 |
| D0002 | Noir | Grand | Régulier | 4 |
| D0002 | Rouge | Petit | Paysage | 5 |
| D0002 | Rouge | Petit | Régulier | 6 |
| D0002 | Rouge | Grand | Régulier | 7 |

Le tableau suivant montre comment la hiérarchie d’index est configurée.

| Numéro d’ensemble | Dimension | Hiérarchie |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

L’index vous permet d’interroger le stock disponible des manières suivantes :

- `()` – Groupé par tous

    - D0002, 28

- `(ColorId)` – Groupé par `ColorId`

    - D0002, Noir, 10
    - D0002, Rouge, 18

- `(ColorId, SizeId)` – Groupé par la combinaison de `ColorId` et `SizeId`

    - D0002, Noir, Petit modèle, 3
    - D0002, Noir, Grand modèle, 7
    - D0002, Rouge, Petit modèle, 11
    - D0002, Rouge, Grand modèle, 7

- `(ColorId, SizeId, StyleId)` – Groupé par combinaison de `ColorId`, `SizeId` et `StyleId`

    - D0002, Noir, Petit modèle, Large, 1
    - D0002, Noir, Petit modèle, Normal, 2
    - D0002, Noir, Grand modèle, Large, 3
    - D0002, Noir, Grand modèle, Normal, 4
    - D0002, Rouge, Petit modèle, Large, 5
    - D0002, Rouge, Petit modèle, Normal, 6
    - D0002, Rouge, Grand modèle, Normal, 7

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Configuration de la réservation (facultatif)

La configuration de la réservation est requise si vous souhaitez utiliser la fonction de réservation provisoire. La configuration se compose de deux parties fondamentales :

- Mappage de réservation provisoire
- Hiérarchie de réservation provisoire

### <a name="soft-reservation-mapping"></a>Mappage de réservation provisoire

Lorsque vous effectuerez une réservation, vous souhaiterez peut-être savoir si le stock disponible est actuellement disponible pour la réservation. La validation est liée à une mesure calculée qui représente une formule de calcul d’une combinaison de mesures physiques.

En configurant le mappage de la mesure physique à la mesure calculée, vous activez le service de visibilité des stocks pour valider automatiquement la disponibilité de la réservation, en fonction de la mesure physique.

Avant de configurer ce mappage, les mesures physiques, les mesures calculées et leurs sources de données doivent être définies dans les onglets **Source de données** et **Mesure calculée** de la page **Configuration** dans Power Apps (comme décrit plus haut dans cet article).

Pour définir le mappage de réservation provisoire, procédez comme suit.

1. Définissez la mesure physique qui sert de mesure de réservation provisoire (par exemple, `SoftReservPhysical`).
1. Dans l’onglet **Mesure calculée** de la page **Configuration**, définissez la mesure calculée *disponible à la réservation* (AFR) qui contient la formule de calcul AFR que vous souhaitez mapper à la mesure physique. Par exemple, vous pouvez configurer `AvailableToReserve` (disponible à la réservation) afin qu’il soit mappé sur la mesure physique `SoftReservPhysical` précédemment définie. De cette façon, vous pouvez rechercher quelles quantités ayant le statut de stock `SoftReservPhysical` seront disponibles à la réservation. Le tableau suivant présente la formule de calcul AFR.

    | Type de calcul | Source de données | Mesure physique |
    |---|---|---|
    | Ajout | `fno` | `AvailPhysical` |
    | Ajout | `pos` | `Inbound` |
    | Soustraction | `pos` | `Outbound` |
    | Soustraction | `iv` | `SoftReservPhysical` |

    Nous vous recommandons de configurer la mesure calculée de sorte qu’elle contienne la mesure physique sur laquelle la mesure de la réservation est basée. De cette manière, la quantité de mesure calculée sera affectée par la quantité de mesure de la réservation. Par conséquent, dans cet exemple, la mesure calculée `AvailableToReserve` de la source de données `iv` doit contenir la mesure physique `SoftReservPhysical` issue de `iv` en tant que composant.

1. Ouvrez la page **Configuration**.
1. Dans l’onglet **Mappage de réservation provisoire**, configurez le mappage de la mesure physique à la mesure calculée. Pour l’exemple précédent, vous pouvez utiliser les paramètres suivants pour mapper `AvailableToReserve` à la mesure physique `SoftReservPhysical` précédemment définie.

    | Source de données Mesure physique | Mesure physique | Source de données Disponible à la réservation | Mesure calculée Disponible à la réservation |
    |---|---|---|---|
    | `iv` | `SoftReservPhysical` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > Si vous ne pouvez pas modifier l’onglet **Mappage de réservation provisoire**, vous devez peut-être activer la fonctionnalité *OnHandReservation* sur l’onglet **Gestion des fonctionnalités**.

Maintenant, lorsque vous réserverez sur `SoftReservPhysical`, la visibilité des stocks trouvera automatiquement `AvailableToReserve` et sa formule de calcul associée pour effectuer la validation de la réservation.

Par exemple, vous disposez du stock disponible suivant dans la visibilité des stocks.

```json
{
    "productId": "D0002",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservPhysical": 90
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

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` – `pos.outbound` – `iv.SoftReservPhysical`  
= 70 + 50 – 20 – 90  
= 10

Par conséquent, si vous essayez de faire des réservations sur `iv.SoftReservPhysical` et que la quantité est inférieure ou égale à `AvailableToReserve` (10), la requête de réservation provisoire est réussie.

> [!NOTE]
> Lorsque vous appelez l’API de réservation, vous pouvez contrôler la validation de la réservation en spécifiant le paramètre booléen `ifCheckAvailForReserv` dans le corps de la requête. Une valeur `True` signifie que la validation est requise, alors qu’une valeur `False` signifie que la validation n’est pas requise (bien que vous puissiez vous retrouver avec une quantité `AvailableToReserve` négative, le système vous autorise toujours à effectuer une réservation provisoire). La valeur par défaut est `True`.

### <a name="soft-reservation-hierarchy"></a>Hiérarchie de réservation provisoire

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

## <a name="available-to-promise-configuration-optional"></a>Configuration de la quantité disponible à la vente (facultatif)

Vous pouvez configurer la Inventory Visibility pour vous permettre de planifier les futurs changements de stock et de calculer les quantités disponibles à la vente (DAV). Le DAV correspond à la quantité d’un article qui est disponible et peut être promise à un client dans le courant d’une période à venir. L’utilisation de ce calcul peut augmenter considérablement votre capacité de traitement des commandes. Pour utiliser cette fonction, vous devez l’activer sur l’onglet **Gestion des fonctionnalités**, puis la configurer sur l’onglet **Paramètres DAV**. Pour plus d’informations, voir [Plannings de changement du stock disponible et disponibilité à la vente de la Inventory Visibility](inventory-visibility-available-to-promise.md).

## <a name="complete-and-update-the-configuration"></a>Terminer et mettre à jour la configuration

Une fois la configuration terminée, vous devez valider toutes les modifications apportées à la visibilité des stocks. Pour valider vos modifications, procédez comme suit.

1. Dans Power Apps, sur la page **Configuration**, sélectionnez **Mettre à jour la configuration** dans le coin supérieur droit. 
1. Le système demande des identifiants de connexion. Entrez les valeurs suivantes :

    - **Identité du client** : ID d’application Azure que vous avez créé pour la visibilité des stocks.
    - **ID de locataire** : ID de locataire Azure.
    - **Clé secrète client** : clé secrète d’application Azure que vous avez créée pour la visibilité des stocks.

    Pour plus d’informations sur ces informations d’identification et comment les trouver, voir [Installer et configurer Inventory Visibility](inventory-visibility-setup.md).

    > [!IMPORTANT]
    > Assurez-vous de valider le nom de votre source de données, les mesures physiques et les mappages de dimensions avant de mettre à jour la configuration. Vous ne pouvez plus modifier ces paramètres après les avoir mis à jour.

1. Une fois connecté, sélectionnez de nouveau **Mettre à jour la configuration**. Le système applique vos paramètres et affiche les modifications.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Exemple de configuration par défaut

Lors de sa phase d’initialisation, la visibilité des stocks définit une configuration par défaut, qui est détaillée ici. Vous pouvez modifier cette configuration selon vos besoins.

### <a name="data-source-configuration"></a>Configuration de la source de données

#### <a name="configuration-of-the-iv-data-source"></a>Configuration de la source de données iv

Cette section décrit comment la source de données `iv` est configurée.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>Mesures physiques configurées pour la source de données "iv"

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

#### <a name="configuration-of-the-fno-data-source"></a>Configuration de la source de données "fno"

Cette section décrit comment la source de données `fno` est configurée.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>Mappages de dimensions pour la source de données "fno"

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

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>Mesures physiques configurées pour la source de données "fno"

Les mesures physiques suivantes sont configurées pour la source de données `fno` :

- `Arrived`
- `PhysicalInvent`
- `ReservPhysical`
- `onorder`
- `notspecified`
- `availordered`
- `availphysical`
- `picked`
- `postedqty`
- `quotationreceipt`
- `received`
- `ordered`
- `ReservOrdered`

#### <a name="configuration-of-the-pos-data-source"></a>Configuration de la source de données "pos"

Cette section décrit comment la source de données `pos` est configurée.

##### <a name="physical-measures-for-the-pos-data-source"></a>Mesures physiques pour la source de données "pos"

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

#### <a name="configuration-of-the-iom-data-source"></a>Configuration de la source de données "iom"

Les mesures physiques suivantes sont configurées pour la source de données `iom` (intelligent order management) :

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>Configuration de la source de données "erp"

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

Le tableau suivant montre le mappage de réservations par défaut.

| Source de données Mesure physique | Mesure physique | Source de données Disponible à la réservation | Mesure calculée Disponible à la réservation |
|---|---|---|---|
| `iv` | `SoftReservPhysical` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>Hiérarchie de réservation

Le tableau suivant montre la hiérarchie de réservation par défaut.

| Dimension de base | Hiérarchie  |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
