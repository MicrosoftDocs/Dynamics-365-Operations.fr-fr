---
title: Réservations dans la visibilité des stocks
description: Cette rubrique explique comment configurer la fonctionnalité de réservation pour créer des réservations, consommer des réservations et/ou annuler la réservation de quantités en stock spécifiées à l'aide de la visibilité des stocks.
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
ms.openlocfilehash: 6c87018cbfbe22fbbc441a1a23aee0ac44af9ddc
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345147"
---
# <a name="inventory-visibility-reservations"></a>Réservations dans la visibilité des stocks

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Cette rubrique explique comment configurer la fonctionnalité de réservation pour créer des réservations, consommer des réservations et/ou annuler la réservation de quantités en stock spécifiées à l'aide de la visibilité des stocks.

Les réservations marquent une quantité en stock qui sera utilisée à l'avenir. Lorsque vous créez une réservation, le système empêche d'autres commandes de réserver ou de consommer les marchandises réservées jusqu'à ce que la réservation soit consommée ou annulée. Les réservations sont créées, consommées et annulées à l'aide d'appels d'API au service de visibilité des stocks.

Vous pouvez éventuellement configurer Microsoft Dynamics 365 Supply Chain Management (et d'autres systèmes tiers) pour compenser automatiquement la quantité qui a été réservée à l'aide de la visibilité des stocks. La quantité compensée est supprimée des enregistrements de réservation dans la visibilité des stocks.

Lorsque vous activez la fonction de réservation, Supply Chain Management est automatiquement prêt à compenser les réservations effectuées à l'aide de la visibilité des stocks.

> [!NOTE]
> La fonctionnalité de compensation nécessite Supply Chain Management version 10.0.22 ou ultérieure. Si vous souhaitez utiliser les réservations de visibilité des stocks, nous vous recommandons d'attendre d'avoir mis à niveau Supply Chain Management vers la version 10.0.22 ou ultérieure.

## <a name="turn-on-the-reservation-feature"></a>Activer la fonction de réservation

Pour activer la fonctionnalité de réservation, procédez comme suit.

1. Dans Power Apps, ouvrez **Visibilité des stocks**.
1. Ouvrez la page **Configuration**.
1. Sur l'onglet **Gestion des fonctionnalités**, activez la fonctionnalité *OnHandReservation*.
1. Connectez-vous à Supply Chain Management.
1. Allez dans **Gestion des stocks \> Configuration \> Paramètres d'intégration de la visibilité des stocks**.
1. Sous **Compensation de réservation**, définissez l'option **Activer la compensation de réservation** sur *Oui*.

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Utiliser la fonction de réservation dans la visibilité des stocks

Lorsque vous appelez l'API de réservation, le système marque la réservation des marchandises et des quantités spécifiées. Vous devez définir une hiérarchie de réservation et des requêtes POST qui correspondent à cette hiérarchie de réservation. Les réservations peuvent ensuite être effectuées en appelant directement les API de réservation.

### <a name="configure-the-reservation-hierarchy"></a>Configurer la hiérarchie de réservation

La hiérarchie de réservation décrit la séquence de dimensions qui doit être spécifiée lors des réservations. EIle fonctionne de la même manière que la hiérarchie d'indexation pour les requêtes disponibles.

La hiérarchie de réservation peut différer de la hiérarchie d'indexation. Cette indépendance vous permet de mettre en œuvre une gestion des catégories où les utilisateurs peuvent décomposer les dimensions en détails pour spécifier les exigences nécessaires pour effectuer des réservations plus précises.

Pour configurer une hiérarchie de réservation provisoire dans Power Apps, ouvrez la page **Configuration**, puis, sur l'onglet **Mappage de réservation provisoire**, paramétrez la hiérarchie des réservations en ajoutant et/ou en modifiant des dimensions et leurs niveaux hiérarchiques.

### <a name="call-the-reservation-api"></a>Appeler l'API de réservation

Les réservations se font dans le service de visibilité des stocks en soumettant une requête POST à l'URL du service, telle que `/api/environment/{environment-ID}/onhand/reserve`.

Pour une réservation, le corps de la requête doit contenir un ID d'organisation, un ID de produit, des quantités réservées et des dimensions. La demande génère un ID de réservation unique pour chaque enregistrement de réservation. L'enregistrement de réservation contient la combinaison unique de l'ID du produit et des dimensions.

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

Pour les statuts de mouvement de stock qui incluent un modificateur de compensation de réserve spécifié, la mise à jour de la transaction compensera l'enregistrement de réservation correspondant lorsque toutes les conditions suivantes sont remplies :

- L'ID de réservation sur le mouvement de stock correspond à l'ID de réservation de l'enregistrement de réservation dans le service de visibilité des stocks.
- Les dimensions du mouvement de stock sont identiques aux dimensions de l'enregistrement de réservation dans le service de visibilité des stocks.
- Les modifications du statut du mouvement de stock déclenchent des compensations pour les réservations lorsque le statut du mouvement de stock reflète le fait qu'un processus de commande a été terminé ou ignoré.

La quantité compensée suit la quantité en stock qui est spécifiée sur les mouvement de stock. La compensation ne prend pas effet s'il ne reste aucune quantité réservée dans le service de visibilité des stocks.

> [!NOTE]
> La fonctionnalité de compensation est disponible à partir de la version 10.0.22

### <a name="set-up-the-reserve-offset-modifier"></a>Configurer le modificateur de compensation de réserve

Le modificateur de compensation de réserve détermine l'étape de traitement de la commande qui déclenche les compensations. L'étape est tracée par le statut du mouvement de stock de la commande. Pour paramétrer le modificateur de compensation de réserve, procédez comme suit.

1. Allez dans **Gestion des stocks \> Configuration \> Paramètres d'intégration de la visibilité des stocks \> Compensation de réservation**.
1. Définissez le champ **Modificateur de compensation de réserve** sur l’une des valeurs suivantes :

    - *Sur commande* - Pour le statut *Sur transaction*, une commande enverra une demande de compensation lors de sa création.
    - *Réserve* - Pour le statut *Réserver la transaction commandée*, une commande enverra une demande de compensation lorsqu'elle est réservée, prélevée, validée par bon de livraison ou facturée. La demande ne sera déclenchée qu'une seule fois, pour la première étape lorsque le processus mentionné se produit.

### <a name="set-up-reservation-ids"></a>Définir des ID de réservation

L'ID de réservation marque de manière unique un enregistrement de réservation dans la visibilité des stocks. Dans Supply Chain Management, les utilisateurs placent des réservations sur les lignes de commande pour marquer la compensation pour l'enregistrement de réservation correspondant.

Pour configurer des ID de réservation dans Supply Chain Management, procédez comme suit.

1. Ouvrez une commande client (par exemple, à partir de la page **Toutes les commandes**).
1. Dans le raccourci **Lignes de commande client**, sélectionnez une ligne de commande.
1. Sur le raccourci **Lignes de commande client**, dans la barre d'outils, sélectionnez **Mettre à jour la ligne \> Stock \> Intégration de la visibilité des stocks**.
1. Saisissez les ID de réservation correspondants.

Le changement de statut du stock correspond à la configuration du modificateur de compensation.
