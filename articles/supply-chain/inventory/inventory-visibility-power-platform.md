---
title: Application de visibilité des stocks
description: Cette rubrique décrit comment utiliser l’application de visibilité des stocks.
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
ms.openlocfilehash: cc09dd82547ec42041889e9a96662cd17549a3ea
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345000"
---
# <a name="inventory-visibility-app"></a>Application de visibilité des stocks

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Cette rubrique décrit comment utiliser l’application de visibilité des stocks.

La visibilité des stocks fournit une application pilotée par modèle pour la visualisation. Cette application contient trois pages : **Configuration**, **Visibilité opérationnelle** et **Récapitulatif des stocks**. Elle présente les fonctionnalités suivantes :

- Elle fournit une interface utilisateur (IU) pour la configuration du stock disponible et la configuration de la réservation provisoire.
- Elle prend en charge les requêtes de stock disponible en temps réel sur diverses combinaisons de dimensions.
- Elle fournit une IU pour la validation des requêtes de réservation.
- Elle fournit une vue personnalisée des stocks disponibles pour les produits avec toutes les dimensions

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer, installez et configurez le complément de visibilité des stocks comme décrit dans [Configurer la visibilité des stocks](inventory-visibility-setup.md).

## <a name="configuration"></a><a name="configuration"></a>Configuration

La page **Configuration** vous aide à paramétrer la configuration du stock disponible et la configuration de la réservation provisoire. Une fois le complément installé, la configuration par défaut inclut la valeur de Microsoft Dynamics 365 Supply Chain Management (la source de données `fno`). Vous pouvez examiner le paramètre par défaut. De plus, en fonction des besoins de votre entreprise et des exigences de validation de stock de votre système externe, vous pouvez modifier la configuration dans [Dataverse](/powerapps/maker/common-data-service/data-platform-intro) pour standardiser la manière dont les modifications de stock peuvent être validées, organisées et interrogées sur les multiples systèmes.

### <a name="define-data-sources"></a>Définir les sources de données

Vous définissez chaque *source de données* que vous souhaitez intégrer à la visibilité des stocks. La visibilité des stocks prend en charge l’intégration avec diverses sources de données, telles que votre système de point de vente (PDV), Supply Chain Management et d’autres systèmes externes. Par défaut, Supply Chain Management est configuré comme source de données par défaut (`fno`) dans la visibilité des stocks.

Pour ajouter une source de données, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Visibilité des stocks**.
1. Ouvrez la page **Configuration**.
1. Dans l’onglet **Source de données**, sélectionnez **Nouvelle source de données** pour ajouter une source de données.

> [!NOTE]
> Lorsque vous ajoutez une source de données, assurez-vous de valider le nom de votre source de données, les mesures physiques et les mappages de dimensions avant de mettre à jour la configuration pour le service de visibilité des stocks. Vous ne pourrez plus modifier ces paramètres après avoir sélectionné **Mettre à jour la configuration**.

### <a name="set-up-dimension-mappings"></a>Configurer des mappages de dimensions

La visibilité des stocks fournit une liste de dimensions de base qui peuvent être mappées à partir des dimensions de votre source de données. Trente-trois dimensions sont disponibles pour le mappage.

- Par défaut, si vous utilisez Supply Chain Management comme l’une de vos sources de données, 13 dimensions sont mappées aux dimensions standard de Supply Chain Management. Douze autres dimensions (`inventDimension1` à `inventDimension12`) sont mappées à des dimensions personnalisées dans Supply Chain Management. Les huit dimensions restantes sont des dimensions étendues que vous pouvez mapper à des sources de données externes.
- Si vous n’utilisez pas Supply Chain Management comme l’une de vos sources de données, vous pouvez librement mapper les dimensions. Le tableau suivant présente la liste complète des dimensions disponibles.

> [!NOTE]
> Si votre dimension ne figure pas dans la liste des dimensions par défaut et que vous utilisez une source de données externe, nous vous recommandons d’utiliser `ExtendedDimension1` à `ExtendedDimension8` pour effectuer le mappage.

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
| Spécifique à l’entrepôt | `WMSLocationId` |
| Spécifique à l’entrepôt | `WMSPalletId` |
| Spécifique à l’entrepôt | `LicensePlateId` |
| Autres | `VersionId` |
| Stock (personnalisé) | `InventDimension1` à `InventDimension12` |
| Autres | `ExtendedDimension1` à `ExtendedDimension8` |

Pour ajouter des mappages de dimensions, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Visibilité des stocks**.
1. Ouvrez la page **Configuration**.
1. Sur l’onglet **Source de données**, dans la section **Mappages de dimensions**, sélectionnez **Ajouter** pour ajouter des mappages de dimensions.
1. Dans le champ **Nom de la dimension**, spécifiez la dimension source.
1. Dans le champ **Vers dimension de base**, sélectionnez la dimension dans la visibilité des stocks que vous souhaitez mapper.
1. Sélectionnez **Enregistrer**.

![Ajout des mappages de dimensions](media/inventory-visibility-dimension-mapping.png "Ajout des mappages de dimensions")

Par exemple, si votre source de données inclut une dimension de couleur de produit, vous pouvez la mapper à la dimension de base `ColorId` pour ajouter une dimension personnalisée `ProductColor` dans la source de données `exterchannel`. Elle sera ensuite mappée à la dimension de base `ColorId`.

## <a name="create-a-physical-measure"></a>Créer une mesure physique

Lorsqu’une source de données valide une modification de stock dans la visibilité des stocks, cette modification est validée en utilisant les *mesures physiques*. Les mesures physiques sont des modificateurs qui reflètent les statuts des récapitulatifs des transactions de stock. Les requêtes peuvent être basées sur les mesures physiques.

La visibilité des stocks contient une liste des mesures physiques par défaut. Ces mesures physiques par défaut sont extraites des statuts des transactions de stock sur la page **Liste stocks disponibles** dans Supply Chain Management (**Gestion des stocks \> Recherches et états \> Liste stocks disponibles**).

| Modificateur | Nom |
|---|---|
| `PhysicalInvent` | Stock physique |
| `ReservPhysical` | Physique réservé |
| `AvailPhysical` | Physique disponible |
| `ReservOrdered` | Commandé réservé |
| `PostedQty` | Quantité validée |
| `Deducted` | Déduit |
| `Picked` | Prélevée |
| `Received` | Réceptions |
| `Registered` | Enregistré |
| `Arrived` | Arrivé |
| `Ordered` | Commandée |
| `OnOrder` | Sur commande |
| `QuotationReceipt` | Réception de devis |
| `QuotationIssue` | Sortie de devis |

Si la source de données est Supply Chain Management, vous n’avez pas besoin de recréer les mesures physiques par défaut. Cependant, pour les sources de données externes, vous pouvez créer de nouvelles mesures physiques en suivant ces étapes.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Visibilité des stocks**.
1. Ouvrez la page **Configuration**.
1. Sur l’onglet **Source de données**, dans la section **Mesures physiques**, sélectionnez **Ajouter**, spécifiez un nom de mesure source et enregistrez vos modifications.

## <a name="define-the-product-hierarchy-index"></a>Définir l’index de hiérarchie des produits

En configurant des groupes de dimensions agrégés, vous pouvez utiliser la visibilité des stocks pour interroger l’état des stocks disponibles. Dans la visibilité des stocks, chaque groupe de dimensions est appelé *index*. Chaque index correspond à un numéro d’ensemble. Vous pouvez décider quelles dimensions seront utilisées pour configurer l’indexation, en fonction de la manière dont vous interrogerez la visibilité des stocks.

Pour paramétrer votre index de hiérarchie des produits, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Visibilité des stocks**.
1. Ouvrez la page **Configuration**.
1. Sur l’onglet **Index de hiérarchie des produits**, dans la section **Mappages des dimensions**, sélectionnez **Ajouter** pour ajouter des mappages de dimensions.
1. Par défaut, une liste d’index est fournie. Pour modifier un index existant, sélectionnez **Modifier** ou **Ajouter** dans la section de l’index approprié. Pour créer un ensemble d’index, sélectionnez **Nouvel ensemble d’index**. Pour chaque ligne de chaque ensemble d’index, dans le champ **Dimension**, faites votre sélection dans la liste des dimensions de base. Les valeurs des champs suivants sont générées automatiquement :

    - **Numéro d’ensemble** : les dimensions appartenant au même groupe (index) seront regroupées et le même numéro d’ensemble leur sera attribué.
    - **Hiérarchie** : la hiérarchie est utilisée pour définir les combinaisons de dimensions prises en charge qui peuvent être interrogées dans un groupe de dimensions (index). Par exemple, si vous configurez un groupe de dimensions ayant une séquence hiérarchique *Style*, *Couleur* et *Taille*, le système prend en charge le résultat de trois groupes de requêtes. Le premier groupe concerne uniquement le style. Le deuxième groupe est une combinaison de style et de couleur. Et le troisième groupe est une combinaison de style, couleur et taille. Les autres combinaisons ne sont pas prises en charge.

Pour plus d’informations, voir [Configuration de la hiérarchie d’index des produits](inventory-visibility-configuration.md#index-configuration).

### <a name="example"></a>Exemple

Cette section fournit un exemple qui montre comment fonctionne la hiérarchie. Le tableau suivant fournit une liste des stocks disponibles pour cet exemple.

| Article | Style | Couleur | Taille  | Quantité |
|---|---|---|---|---|
| I0001 | Paysage | Noir | Petite | 1 |
| I0001 | Paysage | Noir | Etendu | 2 |
| I0001 | Paysage | Rouge | Petite | 3 |
| I0001 | Régulier | Noir | Petite | 4 |
| I0001 | Régulier | Noir | Etendu | 5 |
| I0001 | Régulier | Rouge | Petite | 6 |
| I0001 | Régulier | Rouge | Etendu | 7 |

Le tableau suivant montre comment la hiérarchie d’index est configurée.

| Clé | Numéro d’ensemble | Hiérarchie  |
|---|---|---|
| `StyleId` | 1 | 1 |
| `ColorId` | 1 | 2 |
| `SizeId` | 1 | 3 |

Sur la base des paramètres précédents, la combinaison de dimensions pour la requête de visibilité des stocks est *Style*, *Couleur* et *Taille*. La configuration de la hiérarchie permet aux systèmes externes d’interroger le stock disponible des manières suivantes :

- `()` – Groupé par tous. Voici la sortie :

    - I0001, 28

- `(StyleId)` – Groupe par style. Voici la sortie :

    - I0001, Ample, 6
    - I0001, Normal, 22

- `(StyleId, ColorId)` – Groupé par la combinaison de style et couleur. Voici la sortie :

    - I0001, Ample, Noir, 3
    - I0001, Ample, Rouge, 3
    - I0001, Normal, Noir, 9
    - I0001, Normal, Rouge, 13

- `(StyleId, ColorId, SizeId)` – Groupé par la combinaison de style, couleur et taille. Voici la sortie :

    - I0001, Ample, Noir, Petit, 1
    - I0001, Ample, Noir, Grand, 2
    - I0001, Ample, Rouge, Petit, 3
    - I0001, Normal, Noir, Petit, 4
    - I0001, Normal, Noir, Grand, 5
    - I0001, Normal, Rouge, Petit, 6
    - I0001, Normal, Rouge, Grand, 7

## <a name="set-up-a-custom-calculated-measure"></a>Configurer une mesure calculée personnalisée

Vous pouvez utiliser la visibilité des stocks pour interroger à la fois les mesures physiques de stock et les *mesures calculées personnalisées*.

La configuration vous permet de définir un ensemble de modificateurs qui sont ajoutés ou soustraits pour obtenir la quantité de sortie agrégée totale.

1. Connectez-vous à votre environnement Power Apps et ouvrez **Visibilité des stocks**.
1. Ouvrez la page **Configuration**.
1. Dans l’onglet **Mesure calculée**, sélectionnez **Nouvelle mesure de calcul** pour ajouter une mesure calculée. Ensuite, définissez les champs comme décrit dans le tableau suivant.

    | Champ | Valeur  |
    |---|---|
    | Nouveau nom de la mesure calculée | Entrez le nom de la mesure calculée. |
    | Source de données | Le système d’interrogation est une source de données. |
    | Source de données du modificateur | Entrez la source de données du modificateur. |
    | Modificateur | Entrez le nom du modificateur. |
    | Type de modificateur | Sélectionnez le type de modificateur (*Addition* ou *Soustraction*). |

Le tableau suivant montre un exemple de mesure calculée personnalisée `MyCustomAvailableforReservation`. Pour plus d’informations sur cet exemple, consultez [Configuration de la source de données](inventory-visibility-configuration.md#data-source-configuration).

| Source de données Mesure calculée | Mesure calculée | Source de données Modificateur | Modificateur | Type de modificateur |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `Exteexterchannelrchannel` | `reserved` | `Subtraction` |

### <a name="set-up-a-soft-reservation-mapping"></a><a name="setup-reservation-mapping"></a>Configurer un mappage de réservation provisoire

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Avant de pouvoir modifier l’onglet **Mappage de réservation provisoire**, vous devez activer la fonctionnalité *OnHandReservation* sur l’onglet **Gestion des fonctionnalités**.

En configurant le mappage de la mesure physique à la mesure calculée, vous activez le service de visibilité des stocks pour valider automatiquement la disponibilité de la réservation, en fonction de la mesure physique.

Avant de configurer ce mappage, les mesures physiques, les mesures calculées et leurs sources de données doivent être définies dans les onglets **Source de données** et **Mesure calculée** de la page **Configuration** dans Power Apps (comme décrit plus haut dans cette rubrique).

Pour définir le mappage de réservation provisoire, procédez comme suit.

1. Définissez la mesure physique qui sert de mesure de réservation provisoire (par exemple, `softreservordered`).
1. Dans l’onglet **Mesure calculée** de la page **Configuration**, définissez la mesure calculée *disponible à la réservation* (AFR) qui contient la formule de calcul AFR que vous souhaitez mapper à la mesure physique. Par exemple, vous pouvez configurer `availforreserv` (disponible à la réservation) afin qu’il soit mappé sur la mesure physique `softreservordered` précédemment définie. De cette façon, vous pouvez rechercher quelles quantités ayant le statut de stock `softreservordered` seront disponibles à la réservation. Le tableau suivant présente la formule de calcul AFR.

    | Modificateur | Source de données | Mesure |
    |---|---|---|
    | `Addition` | `fno` | `availphysical` |
    | `Addition` | `pos` | `inbound` |
    | `Subtraction` | `pos` | `outbound` |
    | `Subtraction` | `iv` | `softreservordered` |

1. Ouvrez la page **Configuration**.
1. Dans l’onglet **Mappage de réservation provisoire**, configurez le mappage de la mesure physique à la mesure calculée. Pour l’exemple précédent, vous pouvez utiliser les paramètres suivants pour mapper `availforreserv` à la mesure physique `softreservordered` précédemment définie.

    | Source de données Mesure physique | Mesure physique | Source de données Disponible à la réservation | Mesure calculée Disponible à la réservation |
    |---|---|---|---|
    | `iv` | `softreservordered` | `iv` | `availforreserv` |

### <a name="set-up-a-soft-reservation-hierarchy"></a><a name="setup-reservation-hierarchy"></a>Configurer une hiérarchie de réservation provisoire

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Avant de pouvoir modifier l’onglet **Hiérarchie de réservation provisoire**, vous devez activer la fonctionnalité *OnHandReservation* dans l’onglet **Gestion des fonctionnalités**.

La hiérarchie de réservation décrit la séquence de dimensions qui doit être spécifiée lors des réservations. EIle fonctionne de la même manière que la hiérarchie d’index des produits pour les requêtes de stock disponible.

La hiérarchie de réservation peut différer de la hiérarchie d’index de stock disponible. Cette indépendance vous permet de mettre en œuvre une gestion des catégories où les utilisateurs peuvent décomposer les dimensions en détails pour spécifier les exigences nécessaires pour effectuer des réservations plus précises.

#### <a name="example"></a>Exemple

La hiérarchie de réservation suivante est configurée dans votre système.

| Dimension | Hiérarchie  |
|---|---|
| `ColorId` | 1 |
| `SizeId ` | 2 |
| `StyleId` | 3 |

Étant donné cette hiérarchie de réservation, vous pouvez effectuer une réservation dans les ordres de dimensions suivants :

- `()` – Aucune dimension n’est donnée.
- `(ColorId)`
- `(ColorId, SizeId)`
- `(ColorId, SizeId, StyleId)`

L’ordre de dimension doit suivre strictement la séquence hiérarchique de réservation, dimension par dimension. Par exemple, les réservations avec `(ColorId, StyleId)` ne seront pas autorisées dans cet exemple, car cette séquence n’est pas définie dans la hiérarchie de réservation.

### <a name="control-feature-management"></a><a name="feature-switch"></a>Gestion de la fonctionnalité de contrôle

Le complément de visibilité des stocks fournit des fonctionnalités telles que *OnHandReservation* et *OnHandMostSpecificBackgroundService*. Par défaut, ces fonctionnalités sont désactivées. Pour les utiliser, ouvrez la page **Configuration** dans Power Apps, puis, dans l’onglet **Gestion des fonctionnalités**, activez-les.

### <a name="complete-and-update-the-configuration"></a>Terminez et mettez à jour la configuration.

Une fois la configuration terminée, vous devez valider toutes les modifications apportées à la visibilité des stocks. Pour valider les modifications, sélectionnez **Mettre à jour la configuration** dans le coin supérieur droit de la page **Configuration** dans Power Apps.

La première fois que vous sélectionnez **Mettre à jour la configuration**, le système demande vos informations d’identification.

- **Identité du client** : ID d’application Azure que vous avez créé pour la visibilité des stocks.
- **ID de locataire** : ID de locataire Azure.
- **Clé secrète client** : clé secrète d’application Azure que vous avez créée pour la visibilité des stocks.

Une fois que vous êtes connecté, la configuration est mise à jour dans le service de visibilité des stocks.

> [!NOTE]
> Assurez-vous de valider le nom de votre source de données, les mesures physiques et les mappages de dimensions avant de mettre à jour la configuration pour le service de visibilité des stocks. Vous ne pourrez plus modifier ces paramètres après avoir sélectionné **Mettre à jour la configuration**.

### <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Rechercher le point de terminaison de service

Si vous ne connaissez pas le bon point de terminaison de service de visibilité des stocks, ouvrez la page **Configuration** dans Power Apps, puis sélectionnez **Afficher le point de terminaison de service** dans le coin supérieur droit. La page affichera le bon point de terminaison de service.

## <a name="operational-visibility"></a>Visibilité opérationnelle

La page **Visibilité opérationnelle** fournit les résultats d’une requête de stock disponible en temps réel, basée sur diverses combinaisons de dimensions. Quand la fonctionnalité *OnHandReservation* est activée, vous pouvez également valider des requêtes de réservation à partir de la page **Visibilité opérationnelle**.

### <a name="on-hand-query"></a>Requête de stock disponible

L’onglet **Requête de stock disponible** affiche les résultats d’une requête de stock disponible en temps réel.

Lorsque vous sélectionnez l’onglet **Requête de stock disponible**, le système demande vos informations d’identification afin d’obtenir le jeton du porteur requis pour interroger le service de visibilité des stocks. Vous pouvez simplement coller le jeton du porteur dans le champ **BearerToken** et fermer la boîte de dialogue. Vous pouvez ensuite valider une requête de stock disponible.

Si le jeton du porteur n’est pas valide, ou s’il a expiré, vous devez en coller un nouveau dans le champ **BearerToken**. Entrez le valeurs appropriées pour **ID client**, **ID de locataire**, **Clé secrète client**, puis sélectionnez **Actualiser**. Le système obtiendra automatiquement un nouveau jeton du porteur valide.

Pour valider une requête de stock disponible, saisissez la requête dans le corps de la demande. Utilisez le modèle décrit dans [Interroger en utilisant la méthode post](inventory-visibility-api.md#query-with-post-method).

![Paramètres de requête de stock disponible](media/inventory-visibility-query-settings.png "Paramètres de requête de stock disponible")

### <a name="reservation-posting"></a>Validation de réservation

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Utilisez l’onglet **Validation de la réservation** pour valider une requête de réservation. Avant de pouvoir valider une requête de réservation, vous devez activer la fonctionnalité *OnHandReservation*. Pour plus d’informations sur cette fonctionnalité, consultez [Réservations de visibilité des stocks](inventory-visibility-reservations.md).

Pour valider une requête de réservation, vous devez saisir une valeur dans le corps de la demande. Utilisez le modèle décrit dans [Créer un événement de réservation](inventory-visibility-api.md#create-one-reservation-event). Sélectionnez ensuite **Valider**. Pour afficher les détails de la réponse à la requête, sélectionnez **Afficher les détails**. Vous pouvez également obtenir la valeur **reservationId** à partir des détails de la réponse.

## <a name="inventory-summary"></a>Récapitulatif du stock

**Récapitulatif du stock** est une vue personnalisée de l’*Entité de somme de stock disponible*. Elle fournit un récapitulatif du stock pour les produits avec toutes les dimensions. En utilisant l’option **Filtre avancé** fournie par Dataverse, vous pouvez créer une vue personnelle qui affiche les lignes qui sont importantes pour vous. Les options de filtrage avancées vous permettent de créer un large éventail de vues, des plus simples aux plus complexes. Elles vous permettent également d’ajouter des conditions groupées et imbriquées aux filtres.

Pour en savoir plus sur l’utilisation de l’option **Filtre avancé**, voir [Modifier ou créer des vues personnelles à l’aide de filtres de grille avancés](/powerapps/user/grid-filters-advanced)

La partie supérieure de la vue personnalisée fournit trois champs : **Dimension par défaut**, **Dimension personnalisée** et **Mesure**. Vous pouvez utiliser ces champs pour contrôler les colonnes visibles.

Vous pouvez sélectionner l’en-tête de colonne pour filtrer ou trier le résultat actuel.

Le bas de la vue personnalisée affiche des informations telles que « 50 enregistrements (29 sélectionnés) » ou « 50 enregistrements ». Ces informations se réfèrent aux enregistrements actuellement chargés à partir du résultat **Filtre avancé**. Le texte « 29 sélectionnés » fait référence au nombre d’enregistrements qui ont été sélectionnés à l’aide du filtre d’en-tête de colonne pour les enregistrements chargés.

Au bas de la vue se trouve un bouton **Charger plus** que vous pouvez utiliser pour charger des enregistrements supplémentaires à partir de Dataverse. Le nombre par défaut d’enregistrements chargés est de 50. Lorsque vous sélectionnez **Charger plus**, les 1 000 enregistrements disponibles suivants sont chargés dans la vue. Le nombre affiché sur le bouton **Charger plus** indique les enregistrements actuellement chargés et le nombre total d’enregistrements pour le résultat **Filtre avancé**.

![Récapitulatif du stock](media/inventory-visibility-onhand-list.png "Récapitulatif du stock")
