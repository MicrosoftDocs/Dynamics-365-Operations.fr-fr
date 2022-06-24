---
title: L’option Retrait n’apparaît pas sur la page du panier ou sur les pages de détails du produit
description: Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque l’option de retrait en magasin n’apparaît pas sur la page du panier ou sur les pages de détails du produit.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 88367e13b4d079edb0816e301901828b65c437ae
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900306"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a>L’option « Retrait » n’apparaît pas sur le panier ou sur les pages de détails du produit

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque l’option de retrait en magasin n’apparaît pas sur la page du panier ou sur les pages de détails du produit.

## <a name="description"></a>Description

Le bouton **Retrait** n’apparaît pas sur la page du panier ou sur les pages de détails du produit.

L’illustration suivante montre un exemple de page qui inclut le bouton **Retrait**.

![Bouton Retrait.](media/pickup-button-missing.jpg)

## <a name="resolution"></a>Résolution

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a>Activer l’extension BOPIS dans le générateur de site Commerce

Pour activer l’extension « Acheter en ligne, retirer en magasin » (BOPIS) dans le générateur de site Commerce, procédez comme suit.

1. Sélectionnez votre site.
1. Sélectionnez **Paramètres du site**, puis **Extensions**.
1. Assurez-vous que l’option **Désactiver BOPIS** n’est pas cochée.

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a>Configurer les modes de livraison dans Commerce Headquarters

Pour configurer les modes de livraison dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Approvisionnements \> Paramétrage \> Modes de livraison**.
1. Assurez-vous que le mode de livraison **Retrait par le client** a été créé et que des produits et des adresses lui sont affectés.
1. Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres**.
1. Dans le volet de navigation de gauche, sélectionnez **Commandes client**.
1. Assurez-vous que **Mode de livraison en retrait** est correctement configuré.

### <a name="configure-customer-orders-payments"></a>Configurer les paiements des commandes client

Pour configurer les paiements des commandes client dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres**.
1. Dans le volet de navigation de gauche, sélectionnez **Commandes client**.
1. Sur le raccourci **Paiements**, assurez-vous que les champs **Conditions de paiement** et **Mode de paiement** sont correctement définis.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer BOPIS](../cpe-bopis.md)

[Activer plusieurs modes de livraison de retrait pour les commandes des clients](../multiple-pickup-modes.md)

[Paiements de commandes de Commerce omnicanal](../dev-itpro/commerce-payments.md)

[Module Sélection de magasin](../store-selector.md)
