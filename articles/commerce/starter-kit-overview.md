---
title: Vue d'ensemble du kit de démarrage
description: Cette rubrique présente une vue d'ensemble du kit de démarrage dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1960e1354744fe1034783177ba331f5877d0bee7
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025900"
---
# <a name="starter-kit-overview"></a>Vue d'ensemble du kit de démarrage


[!include [banner](includes/banner.md)]

Cette rubrique présente une vue d'ensemble du kit de démarrage dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Le kit de démarrage de Dynamics 365 Commerce est un ensemble de modules à utiliser pour créer un site web de commerce électronique. Les modules ont des aspects de l'interface utilisateur et des aspects de comportement fonctionnel.

Des thèmes peuvent être appliqués aux modules dans le kit de démarrage pour modifier leur aspect. Les thèmes utilisent des feuilles de style en cascade (CSS). Un thème pour un site fictif de commerce électronique nommé « Fabrikam » est disponible dans le cadre du kit de démarrage et peut être utilisé comme référence.

## <a name="starter-kit-modules"></a>Modules de kit de démarrage

Les types de modules suivants sont fournis dans le kit de démarrage :

- **Module de conteneur** – Un module de conteneur est un module unique qui agit comme hôte pour d'autres modules. Il contrôle la disposition des modules qui sont à l'intérieur de celui-ci.
- **Modules de marketing** – Les modules de marketing incluent des modules de bloc de contenu, bloc de texte, lecteur vidéo et carrousel. Tous ces modules permettent de présenter du contenu. Ils peuvent être placés sur n'importe quelle page et sont pilotés par les données du système de gestion de contenu (CMS).
- **Modules d'en-tête et de pied de page** – Les modules d'en-tête et de pied de page s'affichent dans l'en-tête et le pied de page de toutes les pages du site. Ces modules peuvent être configurés de la manière prescrite via les propriétés.
- **Modules de recherche** – Les produits peuvent être détectés à l'aide de le module de recherche dans l'en-tête. Les résultats de la recherche s'affichent dans la page de résultats de la recherche. Les produits peuvent également être détectés dans les pages de catégorie, qui sont des pages dédiées à chaque catégorie prise en charge dans la hiérarchie de navigation du canal. En outre, les modules de raffineur peuvent être utilisés pour filtrer davantage les résultats dans les résultats de la recherche et des pages de catégorie.
- **Modules de page de détails des produits** – Les pages de détails de produit utilisent plusieurs modules pour afficher des informations sur le produit. Le module de zone d'achat permet aux clients d'afficher les produits et de les ajouter au panier. D'autres modules, comme le module des spécifications techniques, affichent les détails du produit. Le module de classements et d'évaluations permet d'afficher et de fournir des évaluations.
- **Module Achat en ligne et prélèvement en magasin** – Le module Achat en ligne et prélèvement en magasin est intégré à Bing Maps. Il peut être utilisé pour rechercher des magasins à proximité où les clients peuvent prélever les produits qu'ils ont achetés.
- **Modules d'achat** – Les modules d'achat sont le module de panier, qui permet d'ajouter des articles au panier. Le module de caisse capture l'adresse d'expédition, les options de livraison, et la carte cadeau, le programme de fidélité, et les informations de carte de crédit, afin que la commande puisse être traitée. Une fois la commande passée, le module de confirmation de commande peut être utilisé pour indiquer les détails de la confirmation.
- **Modules de gestion de compte** – Le module de connexion permet aux clients de se connecter à un compte existant, et le module d'inscription de créer un compte. Une fois qu'un compte est créé, le module d'historique de commande peut être utilisé pour afficher les commandes récentes, et le module de détails de commande peut être utilisé pour afficher les détails de la commande.
- **Module de recommandations** – Les recommandations sont affichées à l'aide du module de placement de produit. Ce module prend en charge les listes algorithmiques et éditoriales pouvant être affichées sur n'importe quelle page.

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Container](add-container-module.md)

[Module Zone d'achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Paiement](add-checkout-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
