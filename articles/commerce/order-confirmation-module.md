---
title: Module Confirmation de commande
description: Cette rubrique couvre les modules de confirmation de commande et décrit leur création dans Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698324"
---
# <a name="order-confirmation-module"></a>Module Confirmation de commande

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de confirmation de commande et décrit leur création dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module de confirmation de commande est utilisé pour afficher un message de confirmation sur une page de confirmation de commande après une commande passée. Le module de confirmation de commande affiche le numéro de confirmation de la commande et l'adresse e-mail du client qui a été fournie lors de l'extraction.

Lorsqu'une commande est effectuée lors de l'extraction, le numéro confirmation de commande et l'adresse e-mail du client sont transférés vers la page de confirmation de commande comme une chaîne de requête dans l'URL de la page. Le module de confirmation de commande reçoit ces informations et affiche le statut de la commande sur la page de confirmation de commande. Le module de confirmation de commande nécessite ce contexte de page pour fournir le statut de la commande.

## <a name="order-confirmation-module-properties"></a>Propriétés du module de confirmation de commande

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| En-tête       | Texte d'en-tête et balise d'en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Le module de confirmation de commande peut avoir un en-tête. Par défaut, la balise d'en-tête **H2** sert pour l'en-tête. Toutefois, la balise peut être modifiée pour satisfaire aux exigences d'accessibilité. |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a>Modules qui peuvent être utilisés dans un module de page de confirmation de commande 

- **Recommandations** – Le module de recommandations peut être placé sur la page de confirmation de commande pour suggérer d'autres produits au client.
- **Marketing** – Le module de marketing peut ajouter du contenu marketing à la page de confirmation de commande.

## <a name="create-an-order-confirmation-page-module"></a>Créer un module de page de confirmation de commande

1. Créez un modèle de page nommé **modèle de confirmation de commande**.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un module de confirmation de commande.
1. Dans le module de confirmation de commande, ajoutez un module de recommandations.
1. Enregistrez et affichez un aperçu du modèle. Le module de confirmation de commande ne doit pas être affiché, car il nécessite le contexte du numéro de confirmation de commande.
1. Archivez le modèle, et publiez-le.
1. Utilisez le modèle de confirmation de commande que vous venez de créer pour créer une page qui s'appelle **page Confirmation de commande**.
1. Ajoutez la page par défaut au contour de page.
1. À l'emplacement **En-tête**, ajoutez un fragment d'en-tête.
1. À l'emplacement **Pied de page**, ajoutez un fragment de pied de page.
1. À l'emplacement **Principal**, ajoutez un module de confirmation de commande.
1. Dans le volet de propriété du module de confirmation de commande, ajoutez l'en-tête **Confirmation de commande**.
1. Sous le module de confirmation de commande, ajoutez un module de recommandations, et configurez-le afin qu'il utilise les paramètres **Nouveau** et **Meilleure vente**.
1. Enregistrez et afficher un aperçu de la page, archivez-le, et publiez-le.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Container](add-container-module.md)

[Module Zone d'achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Paiement](add-checkout-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
