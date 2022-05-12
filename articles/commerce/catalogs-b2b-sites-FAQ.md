---
title: FAQ sur les catalogues Commerce pour le B2B
description: Cette rubrique fournit des réponses aux questions fréquentes sur les catalogues Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 04/28/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 776820e8e77cd0884b3df5412bb95e6e80ca4fc7
ms.sourcegitcommit: 0abc777986112ea2332f5bf0e815b303b952356c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2022
ms.locfileid: "8656838"
---
# <a name="commerce-catalogs-for-b2b-faq"></a>FAQ sur les catalogues Commerce pour le B2B

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique fournit des réponses aux questions fréquentes sur les [catalogues interentreprises B2B](catalogs-b2b-sites.md) de Microsoft Dynamics 365 Commerce.

## <a name="why-cant-i-configure-a-catalog-specific-navigation-hierarchy-or-see-an-option-to-associate-a-customer-hierarchy"></a>Pourquoi ne puis-je pas configurer une hiérarchie de navigation spécifique au catalogue ou voir une option pour associer une hiérarchie client ?

Assurez-vous que la fonctionnalité **Activer l’utilisation de plusieurs catalogues sur les canaux de vente au détail** est activée dans l’espace de travail **Gestion des fonctionnalités** de Commerce headquarters. De plus, assurez-vous que votre environnement utilise la version 10.0.26 ou ultérieure de Commerce.

## <a name="can-i-view-the-catalog-specific-hierarchy-and-enrich-category-pages-in-commerce-site-builder"></a>Puis-je afficher la hiérarchie spécifique au catalogue et enrichir les pages de catégories dans le générateur de site Commerce ?

Oui, les utilisateurs du générateur de site Commerce qui ont accès à la page **Produits** du générateur de site peut sélectionner un catalogue et afficher la hiérarchie spécifique au catalogue. Sur la page **Produits**, les utilisateurs peuvent également enrichir une page de catégorie pour une catégorie spécifique dans le catalogue. Pour plus d’informations, voir [Enrichir une page d’arrivée de catégorie](enrich-category-page.md). Si vous souhaitez disposer d’un enrichissement spécifique à un catalogue, nous vous recommandons d’avoir une hiérarchie de navigation distincte et unique pour ce catalogue.

## <a name="can-a-b2b-shopper-purchase-from-multiple-catalogs-in-a-single-checkout"></a>Un acheteur B2B peut-il acheter à partir de plusieurs catalogues en un seul paiement ?

Oui, des achats à partir de plusieurs catalogues en un seul paiement sont autorisés. Les acheteurs B2B peuvent utiliser l’indicateur de catalogue dans la vue du panier pour déterminer quels articles ont été ajoutés à partir de quels catalogues.

## <a name="if-a-b2b-shopper-purchases-the-same-item-from-different-catalogs-what-is-the-expected-behavior"></a>Si un acheteur B2B achète le même article dans différents catalogues, quel est le comportement attendu ?

Bien qu’un utilisateur donné puisse avoir accès à plusieurs catalogues à un moment donné, on s’attend à ce que les produits de ces catalogues s’excluent mutuellement. En d’autres termes, idéalement, le même produit ne devrait pas faire partie de plus d’un catalogue pour un utilisateur donné.

Cependant, si une situation se présente où le même produit appartient à plusieurs catalogues, le système maintiendra plusieurs lignes de panier pour ce produit. Il y aura une ligne distincte pour chaque catalogue. Le même produit de deux catalogues différents ne sera pas fusionné au paiement.

## <a name="when-a-b2b-shopper-is-shopping-is-there-any-validation-for-catalog-availability"></a>Quand un acheteur B2B achète, y a-t-il une validation de la disponibilité du catalogue ?

Oui. Un acheteur B2B ne sera autorisé à passer au paiement que si tous les articles du panier proviennent de catalogues valides. Si des articles du panier proviennent de catalogues expirés ou retirés, ils seront supprimés et l’utilisateur en sera informé.

## <a name="during-the-shopping-experience-are-search-and-product-discovery-including-related-and-recommended-product-collections-catalog-specific"></a>Au cours de l’expérience d’achat, la recherche et la découverte de produits (y compris les collections de produits associés et recommandés) sont-elles spécifiques au catalogue ?

Oui. Dès qu’un utilisateur sélectionne un catalogue spécifique, l’ensemble du parcours d’achat devient spécifique au catalogue. Ce parcours comprend des expériences de découverte de produits telles que des suggestions de recherche, des résultats de recherche, des résultats de catégorie, des affinements, des prix, des attributs et des produits recommandés (tels que les produits nouveaux, les plus vendus, les tendances, fréquemment achetés ensemble et les produits connexes).

## <a name="can-a-b2b-shopper-purchase-from-the-default-assortment-catalogid0"></a>Un acheteur B2B peut-il acheter à partir de l’assortiment par défaut (catalogID=0) ?

Non, un acheteur B2B n’est pas autorisé à acheter à partir de l’assortiment par défaut. Cet assortiment est destiné uniquement à la navigation anonyme. S’il manque à un acheteur B2B des affectations de catalogue (en attente de mises à jour de son administration), il ne pourra pas voir les catalogues parmi lesquels il peut choisir et aucune hiérarchie de catégories ne sera visible.

## <a name="can-marketing-content-be-curated-for-a-product-that-is-specific-to-a-catalog"></a>Le contenu marketing peut-il être organisé pour un produit spécifique à un catalogue ?

Actuellement, l’enrichissement de produit n’est pris en charge qu’au niveau du site et du canal. En d’autres termes, si un produit est enrichi, il est partagé sur plusieurs catalogues et la page de détails du produit (PDP) correspondante pour ce produit sera rendue de la même manière dans tous les catalogues d’un site donné.

## <a name="is-catalog-support-available-for-both-b2b-and-business-to-consumer-b2c-online-channels"></a>La prise en charge du catalogue est-elle disponible pour les canaux en ligne B2B et entreprise-client (B2C) ?

Actuellement, les catalogues Commerce sont destinés à fonctionner uniquement avec les canaux B2B.

## <a name="can-we-set-up-catalog-specific-upsellcross-sell-items"></a>Peut-on configurer des articles de vente de gamme supérieure/croisée spécifiques au catalogue ?

Actuellement, seules les fonctionnalités des produits associés sont prises en charge. Cependant, les configurations d’articles de vente incitative et de vente croisée sont disponibles pour les centres d’appels.

Les fonctionnalités suivantes sont également prises en charge uniquement pour les centres d’appel :

- Codes sources de catalogue
- Utiliser les ID sourcee pour suivre les coûts et les taux de réponse
- Scripts de commande et d’article spécifiques au catalogue
- Analyse d’une page du catalogue
- Demandes de catalogue
- Echéanciers de paiement
- Produits gratuits basés sur les codes sources

## <a name="can-we-use-catalog-source-codes-for-b2b-orders-through-the-e-commerce-portal"></a>Pouvons-nous utiliser les codes sources du catalogue pour les commandes B2B via le portail e-commerce ?

Non Les codes sources du catalogue sont pris en charge uniquement pour les canaux du centre d’appels.

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer des catalogues Commerce pour les sites B2B](catalogs-b2b-sites.md)

[Impact d’extensibilité des catalogues Commerce pour les personnalisations B2B](catalogs-b2b-sites-dev.md)
