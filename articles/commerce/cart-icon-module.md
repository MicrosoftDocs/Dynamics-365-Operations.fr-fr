---
title: Module Icône de panier
description: Cette rubrique couvre le module Icône de panier de magasins et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
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
ms.openlocfilehash: d9e3850d98e716d1bbea2017f6e8c9d75f19adc9
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2021
ms.locfileid: "6637999"
---
# <a name="cart-icon-module"></a>Module Icône de panier

[!include [banner](includes/banner.md)]

Cette rubrique couvre le module Icône de panier de magasins et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Le module Icône de panier représente le panier dans le module d’en-tête de la page et indique le nombre d’articles dans le panier. Le module Icône de panier affiche également un récapitulatif du panier (également appelé mini-panier) lorsque la souris survole l’icône de panier. Le mini-panier offre à l’utilisateur un récapitulatif des articles du panier sans avoir à parcourir la page du panier. En outre, il permet également à l’utilisateur d’accéder directement à la page de paiement si le récapitulatif le satisfait. Cela réduit le nombre de navigations de page et accélère l’opération de paiement. 

L’image suivante montre un exemple de module d’icône de panier qui affiche un mini panier dans l’en-tête Fabrikam.

![Exemple d’un module d’icône de panier.](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Propriétés du module

- **Afficher le mini panier** - Lorsqu’elle est définie sur True, cette propriété permet d’afficher un récapitulatif du panier (mini-panier) lorsque l’icône de panier est survolée. Cette fonctionnalité n’est prise en charge que pour les ports de vue du bureau.

## <a name="module-properties-in-the-adventure-works-theme"></a>Propriétés du module dans le thème Adventure Works

Dans le thème Adventure Works, le module d'icônes de panier comprend deux emplacements supplémentaires pour le mini-panier. Ces emplacements sont inclus en tant qu'extension de définition de module.

- **Promotions panier vide** – Cet emplacement accepte un module de bloc de contenu. Lorsque le panier est vide, le module de bloc de contenu spécifié est affiché. Le module de bloc de contenu peut être utilisé pour les promotions, le contenu marketing et les liens vers les pages de catégorie, afin d'aider les clients à poursuivre leur parcours d'achat.
- **Contenu promotionnel** – Cet emplacement peut être utilisé pour présenter des promotions, telles que « Livraison gratuite sur les commandes dépassant 100 € ». Les modules de bloc de contenu, de bloc de texte et de liste d'images peuvent être utilisés dans l'emplacement de contenu promotionnel.

L'image suivante montre un exemple de module d'icône de panier dans le thème Adventure Works qui affiche du contenu promotionnel dans le mini-panier.

![Exemple de module d'icône de panier dans le thème Adventure Works](./media/AW_minicart.PNG)

> [!IMPORTANT]
> Les emplacements du thème Adventure Works sont disponibles à partir de la version 10.0.20 de Dynamics 365 Commerce.

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
