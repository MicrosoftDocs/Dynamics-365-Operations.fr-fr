---
title: Module Icône de panier
description: Cet article couvre le module Icône de panier de magasins et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/02/2021
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
ms.openlocfilehash: a5b86b0c843a680dd0c46295a69e12d6e3542619
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859111"
---
# <a name="cart-icon-module"></a>Module Icône de panier

[!include [banner](includes/banner.md)]

Cet article couvre le module Icône de panier de magasins et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Le module Icône de panier représente le panier dans le module d’en-tête de la page et indique le nombre d’articles dans le panier. Le module Icône de panier affiche également un récapitulatif du panier (également appelé mini-panier) lorsque la souris survole l’icône de panier. Le mini-panier offre à l’utilisateur un récapitulatif des articles du panier sans avoir à parcourir la page du panier. En outre, il permet également à l’utilisateur d’accéder directement à la page de paiement si le récapitulatif le satisfait. Cela réduit le nombre de navigations de page et accélère l’opération de paiement. 

L’image suivante montre un exemple de module d’icône de panier qui affiche un mini panier dans l’en-tête Fabrikam.

![Exemple d’un module d’icône de panier.](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Propriétés du module

- **Afficher le mini panier** – Lorsque cette propriété est définie sur **True**, un récapitulatif du panier (mini panier) s'affiche lorsque les utilisateurs survolent l’icône de panier. Cette fonctionnalité n’est prise en charge que pour les ports de vue du bureau.
- **Autoriser le paiement anonyme** – Lorsque cette propriété est définie sur **True**, le mini panier permet aux utilisateurs qui ne sont pas connectés de régler une commande en tant qu'invité. Cette propriété est disponible dans Commerce version 10.0.21, dans le cadre du package de bibliothèque du module Commerce.
- **Ordre des articles** – Cette propriété contrôle l'ordre dans lequel les articles apparaissent dans le mini panier. Quand l'option **Nouveaux éléments ajoutés en haut de la liste** est sélectionnée, les nouveaux articles ajoutés au panier apparaissent en haut de la liste des articles du mini panier. Quand l'option par défaut **Nouveaux éléments ajoutés en bas de la liste** est sélectionnée, les nouveaux articles ajoutés au panier apparaissent en bas de la liste des articles du mini panier. Cette propriété est disponible à partir de Commerce version 10.0.21, dans le cadre du package de bibliothèque du module Commerce.

> [!IMPORTANT]
> Les propriétés **Autoriser le paiement anonyme** et **Ordre des articles** sont disponibles à partir de la version 10.0.21 de Commerce. Elles nécessitent l'installation du package de bibliothèque du module Commerce version 9.31.

## <a name="module-properties-and-slots-in-the-adventure-works-theme"></a>Propriétés et emplacements des modules dans le thème Adventure Works

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
