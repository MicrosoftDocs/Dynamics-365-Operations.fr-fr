---
title: Module Icône de panier
description: Cette rubrique couvre le module Icône de panier de magasins et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5ff514f07e8b31abe79775e5011bd3f1b24b2935
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793079"
---
# <a name="cart-icon-module"></a>Module Icône de panier

[!include [banner](includes/banner.md)]

Cette rubrique couvre le module Icône de panier de magasins et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Le module Icône de panier représente le panier dans le module d’en-tête de la page et indique le nombre d’articles dans le panier. Le module Icône de panier affiche également un récapitulatif du panier (également appelé mini-panier) lorsque la souris survole l’icône de panier. Le mini-panier offre à l’utilisateur un récapitulatif des articles du panier sans avoir à parcourir la page du panier. En outre, il permet également à l’utilisateur d’accéder directement à la page de paiement si le récapitulatif le satisfait. Cela réduit le nombre de navigations de page et accélère l’opération de paiement. 

> [!NOTE]
> La prise en charge du module d’icône de panier est disponible dans Dynamics 365 Commerce Version 10.0.11.

L’image suivante montre un exemple de module d’icône de panier qui affiche un mini panier dans l’en-tête Fabrikam.

![Exemple d’un module d’icône de panier](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Propriétés du module

- **Afficher le mini panier** - Lorsqu’elle est définie sur True, cette propriété permet d’afficher un récapitulatif du panier (mini-panier) lorsque l’icône de panier est survolée. Cette fonctionnalité n’est prise en charge que pour les ports de vue du bureau.

## <a name="add-a-cart-icon-module-to-a-page"></a>Ajouter un module d’icône de panier à une page

Pour ajouter un module d’icône de panier, voir [Module d’en-tête](author-header-module.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Panier](add-cart-module.md)

[Module Validation](add-checkout-module.md)

[Module Paiement](payment-module.md)

[Module Adresse d’expédition](ship-address-module.md)

[Module Options de livraison](delivery-options-module.md)

[Module d’information sur le retrait](pickup-info-module.md)

[Module Détails de la commande](order-confirmation-module.md)

[Module Carte cadeau](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]