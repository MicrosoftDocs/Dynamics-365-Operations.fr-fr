---
title: Module Icône de panier
description: Cette rubrique couvre le module Icône de panier de magasins et décrit comment l'ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6771a84118504cd5c8e44302380eb970e4658902
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411087"
---
# <a name="cart-icon-module"></a>Module Icône de panier

[!include [banner](includes/banner.md)]

Cette rubrique couvre le module Icône de panier de magasins et décrit comment l'ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Le module Icône de panier représente le panier dans le module d'en-tête de la page et indique le nombre d'articles dans le panier. Le module Icône de panier affiche également un récapitulatif du panier (également appelé mini-panier) lorsque la souris survole l'icône de panier. Le mini-panier offre à l'utilisateur un récapitulatif des articles du panier sans avoir à parcourir la page du panier. En outre, il permet également à l'utilisateur d'accéder directement à la page de paiement si le récapitulatif le satisfait. Cela réduit le nombre de navigations de page et accélère l'opération de paiement. 

L'image suivante montre un exemple de module d'icône de panier qui affiche un mini panier dans l'en-tête Fabrikam.

![Exemple d'un module d'icône de panier](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Propriétés du module

- **Afficher le mini panier** - Lorsqu'elle est définie sur True, cette propriété permet d'afficher un récapitulatif du panier (mini-panier) lorsque l'icône de panier est survolée. Cette fonctionnalité n'est prise en charge que pour les ports de vue du bureau.


## <a name="add-a-cart-icon-module-to-a-page"></a>Ajouter un module d'icône de panier à une page

Pour ajouter un module d'icône de panier, voir [Module d'en-tête](author-header-module.md).


## <a name="additional-resources"></a>Ressources supplémentaires

[Module de zone d'achat](add-buy-box.md)

[Module de panier](add-cart-module.md)

[Module de validation](add-checkout-module.md)

[Module de confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
