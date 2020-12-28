---
title: Vue d'ensemble des pages de détails de produit
description: Cette rubrique fournit une vue d'ensemble des pages de détails de produit dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c53e74204fad2960dfba972a38c511df7d6672d8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412373"
---
# <a name="product-details-pages-overview"></a>Vue d'ensemble des pages de détails de produit

[!include [banner](includes/banner.md)]

Cette rubrique fournit une vue d'ensemble des pages de détails de produit dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Une page de détails de produit fournit des informations détaillées sur un produit, et permet aux clients de sélectionner des options de produit comme une taille, un style, et une couleur. Une page de détails de produit doit présenter toutes les informations sur le produit dont un client a besoin pour effectuer une décision d'achat.

L'illustration suivante présente un exemple de page de détails de produit.

![Exemple de page de détails de produit](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a>Modules d'en-tête et de pied de page

Le haut de la page de détails de produit comporte en-tête qui affiche toutes les catégories de produits et d'autres pages que le détaillant souhaite que les clients parcourent. Le bas de la page comporte un pied de page qui contient des liens rapides vers diverses rubriques qui peuvent intéresser les clients.

## <a name="buy-box-module"></a>Module de zone d'achat

Le module le plus important sur une page de détails de produit est le module de zone d'achat, qui apparaît en premier dans la section principale de la page. Un module de zone d'achat affiche des informations importantes sur le produit, telles que son nom, sa description, son prix, des images du produit et les classements du produit.

Le module de zone d'achat permet au client de sélectionner des options de produit (par exemple, une taille, un style, et une couleur) et d'ajouter le produit au panier. Il permet également au client d'acheter les produits en ligne et de les prélever en magasin. Le module d'achat en ligne et prélèvement en magasin utilise l'intégration avec des interface de programmation d'application (API) Bing Maps pour rechercher les magasins à proximité ou les magasins à un autre emplacement que le client spécifie.

Un module de zone d'achat requiert un ID produit. Cet ID est dérivé du contexte de page. Si un module de zone d'achat est ajouté à une page où le contexte de page n'inclut pas un ID produit, il n'affichera pas les informations correctement.

## <a name="product-specifications-module"></a>Module de spécifications du produit

Le module de spécifications du produit peut être utilisé pour présenter des informations supplémentaires sur le produit. Ces détails sont extraits des attributs de produit dans Commerce. Le module de spécifications de produit affiche chaque attribut où la propriété **visible** est définie sur **vrai**. Il nécessite un ID produit pour récupérer les attributs du produit.

## <a name="recommendations-module"></a>Module de recommandations

Le module de recommandations est un important module sur une page des détails de produit. Bien que les clients parcourent les produits, des options de produit supplémentaires doivent leur être présentées, afin qu'ils puissent trouver le produit approprié et effectuer un achat. Les recommandations aident les clients à découvrir facilement le contenu associé et à continuer d'effectuer des achats.

Différents types de listes de recommandations sont disponibles :

- La liste **D'autres clients aiment également** est basée sur le Machine Learning. Elle utilise l'historique des transactions d'autres clients pour fournir des recommandations. Cette liste est générée par le service de recommandations et ressemble aux listes « Les clients qui ont acheté ce produit ont également acheté... ». Un ID produit est obligatoire pour générer la liste.
- Une liste **Associé** peut être configurée pour un produit dans Commerce. Par exemple, pour un sac de voyage en cuir marron, davantage de sacs en cuir ou conçus pour les voyages peuvent être configurés pour la liste associée. Les autres types de liste associée, telles que **Accessoires** et **Plus comme celui-ci**, peuvent également être configurées dans Commerce. Un ID produit est obligatoire pour générer la liste. Par conséquent, si elle est ajoutée à une page d'accueil, où le contexte de page n'inclut pas d'ID produit, la liste est vide.
- Les listes de recommandations algorithmiquement générées, comme **Tendance**, **Meilleures ventes**, **Nouveauté**, peuvent être utilisées sur les pages de détails de produit. Bien que ces listes ne soient pas directement liées au produit sur la page de détails de produit, elles permettent aux clients de trouver autrement les produits qui pourraient les intéresser. Ces types de listes ne nécessitent pas d'ID produit. Ce sont des listes génériques basées sur les modèles d'achat du le site.
- Les listes éditoriales sont des listes manuellement éditées. Par exemple, un détaillant peut décider d'éditer manuellement les listes de produits qu'il souhaite présenter.

## <a name="ratings-and-reviews-modules"></a>Modules de classements et d'évaluations

3 modules peuvent être utilisés pour afficher et ajouter des évaluations :

- **Évaluations** : ce module répertorie les classements et les évaluations fournis par les autres clients. Les clients peuvent trier et filtrer ces évaluations. Ce module permet également aux clients d'émettre un avis favorable ou défavorable sur les évaluations et de signaler des problèmes.
- **Écrire une évaluation** : ce module permet aux clients d'écrire leurs évaluations sur un produit.
- **Histogramme de classements** : ce module comprend un histogramme qui montre la tendance des classements pour un produit.

Pour plus de détails, voir [Vue d'ensemble des classements et des évaluations](ratings-reviews-overview.md).

## <a name="marketing-modules"></a>Modules de marketing

Si le contenu de marketing est unique à un produit spécifique, un module de marketing peut être ajouté à la page de détails de produit. Vous pouvez ajouter des modules de marketing à une page de détails de produit en « enrichissant » la page. Pour plus de détails, voir [Enrichir une page de produit](enrich-product-page.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble de la page d'accueil](quick-tour-home-page.md)

[Vue d'ensemble des pages de panier et de caisse](quick-tour-cart-checkout.md)

[Vue d'ensemble des pages de gestion des comptes](quick-tour-account-management.md)

[Enrichir une page de détails sur un produit](enrich-product-page.md)
