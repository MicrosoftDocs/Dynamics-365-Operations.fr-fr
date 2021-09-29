---
title: Réservations dans la visibilité des stocks
description: Cette rubrique explique comment configurer la fonctionnalité de réservation pour créer des réservations, consommer des réservations et/ou annuler la réservation de quantités en stock spécifiées à l’aide de la visibilité des stocks.
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
ms.openlocfilehash: 4a85520c0911bb7eed5842b3fd5bd706009351e5
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500353"
---
# <a name="inventory-visibility-reservations"></a>Réservations dans la visibilité des stocks

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Cette rubrique explique comment configurer la fonctionnalité de réservation pour créer des réservations, consommer des réservations et/ou annuler la réservation de quantités en stock spécifiées à l’aide de la visibilité des stocks.

Les réservations marquent une quantité en stock qui sera utilisée à l’avenir. Lorsque vous créez une réservation, le système empêche d’autres commandes de réserver ou de consommer les marchandises réservées jusqu’à ce que la réservation soit consommée ou annulée. Les réservations sont créées, consommées et annulées à l’aide d’appels d’API au service de visibilité des stocks.

Vous pouvez éventuellement configurer Microsoft Dynamics 365 Supply Chain Management (et d’autres systèmes tiers) pour compenser automatiquement la quantité qui a été réservée à l’aide de la visibilité des stocks. La quantité compensée est supprimée des enregistrements de réservation dans la visibilité des stocks.

Lorsque vous activez la fonction de réservation, Supply Chain Management est automatiquement prêt à compenser les réservations effectuées à l’aide de la visibilité des stocks.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>Activer et configurer la fonction de réservation

Pour activer la fonctionnalité de réservation, procédez comme suit.

1. Connectez-vous à Power Apps et ouvrez la **Visibilité du stock**.
1. Ouvrez la page **Configuration**.
1. Sur l’onglet **Gestion des fonctionnalités**, activez la fonctionnalité *OnHandReservation*.
1. Connectez-vous à Supply Chain Management.
1. Accédez à l’espace de travail **[Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** et activez la fonction *Intégration de la visibilité du stock avec compensation de réservation* (nécessite la version 10.0.22 ou ultérieure).
1. Accédez à **Gestion des stocks \> Paramétrage \> Paramètres d’intégration de la visibilité du stock**, ouvrez l’onglet **Compensation de réservation** et effectuez les réglages suivants :
    - **Activer la compensation des réservations** : définissez-le sur *Oui* pour activer cette fonctionnalité.
    - **Modificateur de la compensation des réservations** : sélectionnez le statut de la transaction de stock qui compensera les réservations effectuées sur la visibilité des stocks. Ce paramètre détermine l’étape de traitement de la commande qui déclenche les compensations. L’étape est tracée par le statut du mouvement de stock de la commande. Choisissez l’une des méthodes suivantes :
        - *Sur commande* - Pour le statut *Sur transaction*, une commande enverra une demande de compensation lors de sa création. La quantité de compensation sera la quantité de la commande créée.
        - *Réserve* - Pour le statut *Réserver la transaction commandée*, une commande enverra une demande de compensation lorsqu’elle est réservée, prélevée, validée par bon de livraison ou facturée. La demande ne sera déclenchée qu’une seule fois, pour la première étape lorsque le processus mentionné se produit. La quantité de compensation sera la quantité pour laquelle le statut de la transaction de stock sera passé de *En commande* à *Réservé commandé* (ou statut ultérieur) sur la ligne de commande correspondante.

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Utiliser la fonction de réservation dans la visibilité des stocks

Lorsque vous appelez l’API de réservation, le système marque la réservation des marchandises et des quantités spécifiées. Vous devez définir une hiérarchie de réservation et des requêtes POST qui correspondent à cette hiérarchie de réservation. Les réservations peuvent ensuite être effectuées en appelant directement les API de réservation.

### <a name="configure-the-reservation-hierarchy"></a>Configurer la hiérarchie de réservation

La hiérarchie de réservation décrit la séquence de dimensions qui doit être spécifiée lors des réservations. EIle fonctionne de la même manière que la hiérarchie d’indexation pour les requêtes disponibles.

La hiérarchie de réservation peut différer de la hiérarchie d’indexation. Cette indépendance vous permet de mettre en œuvre une gestion des catégories où les utilisateurs peuvent décomposer les dimensions en détails pour spécifier les exigences nécessaires pour effectuer des réservations plus précises.

Pour configurer une hiérarchie de réservation provisoire dans Power Apps, ouvrez la page **Configuration**, puis, sur l’onglet **Hiérarchie de réservation provisoire**, paramétrez la hiérarchie des réservations en ajoutant et/ou en modifiant des dimensions et leurs niveaux hiérarchiques.

Votre hiérarchie de réservation provisoire doit contenir `SiteId` et `LocationId` en tant que composants, car ils construisent la configuration de la partition.

Pour plus d’informations sur la configuration des réservations, consultez la rubrique [Configuration des réservations](inventory-visibility-configuration.md#reservation-configuration).

### <a name="call-the-reservation-api"></a>Appeler l’API de réservation

Les réservations se font dans le service de visibilité des stocks en soumettant une requête POST à l’URL du service, telle que `/api/environment/{environment-ID}/onhand/reserve`.

Pour une réservation, le corps de la requête doit contenir un ID d’organisation, un ID de produit, des quantités réservées et des dimensions. La demande génère un ID de réservation unique pour chaque enregistrement de réservation. L’enregistrement de réservation contient la combinaison unique de l’ID du produit et des dimensions.

Lorsque vous appelez l’API de réservation, vous pouvez contrôler la validation de la réservation en spécifiant le paramètre booléen `ifCheckAvailForReserv` dans le corps de la requête. Une valeur `True` signifie que la validation est requise, alors qu’une valeur `False` signifie que la validation n’est pas requise. La valeur par défaut est `True`.

Si vous souhaitez annuler une réservation ou annuler la réservation de quantités de stock spécifiées, définissez la quantité sur une valeur négative et définissez le paramètre `ifCheckAvailForReserv` sur `False` pour ignorer la validation.

Voici un exemple du corps de la requête, pour référence.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
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
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "SoftReservOrdered",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

## <a name="offset-reservations-in-supply-chain-management"></a>Compenser des réservations dans Supply Chain Management

Pour les statuts de mouvement de stock qui incluent un modificateur de compensation de réserve spécifié, la mise à jour de la transaction compensera l’enregistrement de réservation correspondant lorsque toutes les conditions suivantes sont remplies :

- L’ID de réservation sur le mouvement de stock correspond à l’ID de réservation de l’enregistrement de réservation dans le service de visibilité des stocks.
- Les dimensions du mouvement de stock sont identiques aux dimensions de l’enregistrement de réservation dans le service de visibilité des stocks.
- Les modifications du statut du mouvement de stock déclenchent des compensations pour les réservations lorsque le statut du mouvement de stock reflète le fait qu’un processus de commande a été terminé ou ignoré.

La quantité compensée suit la quantité en stock qui est spécifiée sur les mouvement de stock. La compensation ne prend pas effet s’il ne reste aucune quantité réservée dans le service de visibilité des stocks.

### <a name="set-up-the-reservation-offset-modifier"></a>Configurer le modificateur de compensation des réservations

Si vous ne l’avez pas déjà fait, configurez le modificateur de réservation comme décrit dans [Activer et configurer la fonction de réservation](#turn-on).

### <a name="set-up-reservation-ids"></a>Définir des ID de réservation

L’ID de réservation marque de manière unique un enregistrement de réservation dans la visibilité des stocks. Dans Supply Chain Management, les utilisateurs placent des réservations sur les lignes de commande pour marquer la compensation pour l’enregistrement de réservation correspondant.

Pour configurer des ID de réservation dans Supply Chain Management, procédez comme suit.

1. Ouvrez une commande client (par exemple, à partir de la page **Toutes les commandes**).
1. Dans le raccourci **Lignes de commande client**, sélectionnez une ligne de commande.
1. Sur le raccourci **Lignes de commande client**, dans la barre d’outils, sélectionnez **Mettre à jour la ligne \> Stock \> Intégration de la visibilité des stocks**.
1. Saisissez les ID de réservation correspondants.

Le changement de statut du stock correspond à la configuration du modificateur de compensation.
