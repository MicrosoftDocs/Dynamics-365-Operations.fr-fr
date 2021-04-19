---
title: Vue d’ensemble de la bibliothèque de modules
description: Cette rubrique présente une vue d’ensemble de la bibliothèque de modules Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76fd75c2ed9a3ba4728129b77a43b50267be3bf3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795331"
---
# <a name="module-library-overview"></a>Vue d’ensemble de la bibliothèque de modules

[!include [banner](includes/banner.md)]

Cette rubrique présente une vue d’ensemble de la bibliothèque de modules Microsoft Dynamics 365 Commerce.

La bibliothèque de modules Dynamics 365 Commerce est une collection de modules qui peuvent être utilisés pour créer un site Web de commerce électronique. Les modules ont des aspects de l’interface utilisateur et des aspects de comportement fonctionnel.

Des thèmes peuvent être appliqués aux modules de la bibliothèque de modules pour modifier leur aspect. Les thèmes utilisent des feuilles de style en cascade (CSS). Un thème pour un site fictif de commerce électronique nommé « Fabrikam » est disponible dans le cadre de la bibliothèque de modules et peut être utilisé comme référence.

## <a name="module-library-modules"></a>Modules de la bibliothèque de modules

Les types de modules suivants sont fournis dans la bibliothèque de modules :

- **Module de conteneur** – Un module de conteneur est un module unique qui agit comme hôte pour d’autres modules. Il contrôle la disposition des modules qui sont à l’intérieur de celui-ci.
- **Modules de marketing** – Les modules de marketing incluent des modules de bloc de contenu, bloc de texte, lecteur vidéo et carrousel. Tous ces modules permettent de présenter du contenu. Ils peuvent être placés sur n’importe quelle page et sont pilotés par les données du système de gestion de contenu (CMS).
- **Modules d’en-tête et de pied de page** – Les modules d’en-tête et de pied de page s’affichent dans l’en-tête et le pied de page de toutes les pages du site. Ces modules peuvent être configurés de la manière prescrite via les propriétés.
- **Modules de recherche** – Les produits peuvent être détectés à l’aide de le module de recherche dans l’en-tête. Les résultats de la recherche s’affichent dans la page de résultats de la recherche. Les produits peuvent également être détectés dans les pages de catégorie, qui sont des pages dédiées à chaque catégorie prise en charge dans la hiérarchie de navigation du canal. En outre, les modules de raffineur peuvent être utilisés pour filtrer davantage les résultats dans les résultats de la recherche et des pages de catégorie.
- **Modules de page de détails des produits** – Les pages de détails de produit utilisent plusieurs modules pour afficher des informations sur le produit. Le module de zone d’achat permet aux clients d’afficher les produits et de les ajouter au panier. D’autres modules, comme le module des spécifications techniques, affichent les détails du produit. Le module de classements et d’évaluations permet d’afficher et de fournir des évaluations.
- **Module Achat en ligne et prélèvement en magasin** – Le module Achat en ligne et prélèvement en magasin est intégré à Bing Maps. Il peut être utilisé pour rechercher des magasins à proximité où les clients peuvent prélever les produits qu’ils ont achetés.
- **Modules d’achat** – Les modules d’achat sont le module de panier, qui permet d’ajouter des articles au panier. Le module de caisse capture l’adresse d’expédition, les options de livraison, et la carte cadeau, le programme de fidélité, et les informations de carte de crédit, afin que la commande puisse être traitée. Une fois la commande passée, le module de confirmation de commande peut être utilisé pour indiquer les détails de la confirmation.
- **Modules de gestion de compte** – Le module de connexion permet aux clients de se connecter à un compte existant, et le module d’inscription de créer un compte. Une fois qu’un compte est créé, le module d’historique de commande peut être utilisé pour afficher les commandes récentes, et le module de détails de commande peut être utilisé pour afficher les détails de la commande.
- **Module de recommandations** – Les recommandations sont affichées à l’aide du module de placement de produit. Ce module prend en charge les listes algorithmiques et éditoriales pouvant être affichées sur n’importe quelle page.

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Container](add-container-module.md)

[Module Zone d’achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Paiement](add-checkout-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]