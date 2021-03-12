---
title: Module Options de livraison
description: Cette rubrique couvre les modules d’options de livraison et explique comment les configurer dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 9d8945348cbe3255ecc497f129d125ad11e9ceab
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000847"
---
# <a name="delivery-options-module"></a>Module Options de livraison

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules d’options de livraison et explique comment les configurer dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Les modules d’options de livraison permettent aux clients de sélectionner un mode de livraison tel que l’expédition ou le retrait pour leur commande en ligne. Une adresse de livraison est nécessaire pour déterminer le mode de livraison. Si l’adresse d’expédition change, les options de livraison doivent être extraites de nouveau. Si une commande inclut uniquement des articles qui sont retirés en magasin, ce module est automatiquement masqué.

Pour plus d’informations sur la configuration des modes de livraison, voir [Configuration des canaux en ligne](channel-setup-online.md) et [Configurer les modes de livraison](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Chaque mode de livraison peut avoir des frais associés. Pour plus d’informations sur la configuration de frais pour un commerce en ligne, consultez [Frais automatiques avancés omnicanaux](omni-auto-charges.md).

Dans Commerce version 10.0.13, le module des options de livraison a été mis à jour pour prendre en charge les fonctionnalités **Frais d’en-tête sans prorata** et **Expédition sous forme de frais de ligne**. Si le prorata est désactivé, on s’attend à ce que le workflow d’e-Commerce n’autorise pas un mode de livraison mixte pour les articles du panier (c’est-à-dire que certains articles sont sélectionnés pour l’expédition, mais d’autres sont sélectionnés pour le retrait). La fonctionnalité **Frais d’en-tête sans prorata** nécessite que l’indicateur **Activer la gestion cohérente du mode de livraison dans le canal** soit activé dans le siège Commerce. Lorsque cet indicateur est activé, les frais d’expédition seront appliqués au niveau de l’en-tête ou au niveau de la ligne, en fonction de la configuration au siège Commerce.

Le thème Fabrikam prend en charge un mode de livraison mixte, dans lequel certains articles sont sélectionnés pour l’expédition mais d’autres sont sélectionnés pour le retrait. Dans ce mode, les frais d’expédition seront calculés au prorata pour tous les articles sélectionnés pour le mode d’expédition de livraison. Pour qu’un mode de livraison mixte fonctionne, vous devez d’abord configurer la fonctionnalité **Frais d’en-tête au prorata** au siège Commerce. Pour plus d’informations sur cette configuration, consultez [Frais d’en-tête au prorata correspondent aux lignes de vente](pro-rate-charges-matching-lines.md).

Si des frais d’expédition s’appliquent aux articles de ligne, ils peuvent être affichés sur la ligne du panier pour chaque article. Cette fonctionnalité nécessite que la propriété **Afficher les frais d’expédition en ligne** soit activée à la fois pour le module Panier et le module Paiement. Pour plus d’informations, consultez [Module Panier](add-cart-module.md) et [Module Paiement](add-checkout-module.md).

L’illustration suivante montre un exemple de module d’options de livraison dans une page de caisse.

![Exemple de module d’options de livraison sur une page de paiement](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a>Propriétés du module Options de livraison

| Propriété | Valeurs | Description |
|----------|--------|-------------|
| Titre | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Rubrique optionnelle pour le module Options de livraison. |
| Nom de classe CSS personnalisé | Détails | Nom de classe de feuille de style en cascade personnalisée (CSS) qui sera utilisé pour afficher ce module, le cas échéant. |
| Option Filtrer le mode de livraison | **Ne pas filtrer** ou **Modes hors expédition** | Une valeur qui spécifie si le module Options de livraison doit filtrer tous les modes de livraison hors expédition. |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a>Ajouter un module Options de livraison à une page de caisse et définir les propriétés requises

Un module Options de livraison ne peut être ajouté qu’à un module de caisse. Pour plus d’informations sur la configuration d’un module Options de livraison et son ajout à une page de caisse, voir [Module de caisse](add-checkout-module.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Panier](add-cart-module.md)

[Module Validation](add-checkout-module.md)

[Module Paiement](payment-module.md)

[Module Adresse d’expédition](ship-address-module.md)

[Module d'information sur le retrait](pickup-info-module.md)

[Module Détails de la commande](order-confirmation-module.md)

[Module Carte cadeau](add-giftcard.md)

[Configuration d’un canal en ligne](channel-setup-online.md)

[Frais automatiques avancés omnicanaux](omni-auto-charges.md)

[Calcul au prorata des frais d’en-tête correspondent aux lignes de vente](pro-rate-charges-matching-lines.md)

[Paramétrer des modes de livraison](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
