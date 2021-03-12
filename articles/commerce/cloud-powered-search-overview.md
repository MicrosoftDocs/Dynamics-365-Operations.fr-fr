---
title: Vue d'ensemble de la recherche dans le cloud
description: Cette rubrique fournit une vue d'ensemble de recherche optimisée par le cloud dans Microsoft Dynamics 365 Commerce.
author: ashishmsft
manager: annbe
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5a9cb82053640b7abdba420e087d0707208979de
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997648"
---
# <a name="cloud-powered-search-overview"></a>Vue d'ensemble de la recherche dans le cloud


[!include [banner](includes/banner.md)]

Cette rubrique fournit une vue d'ensemble de recherche optimisée par le cloud dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

La détectabilité du produit garantit que les clients peuvent rapidement et facilement trouver des produits en parcourant les catégories, en les recherchant, et en les filtrant. Les détaillants considèrent que la découverte d'un produit est l'outil principal pour l'interaction de clients entre les canaux.

Les clients sont accoutumés aux temps de réponse presque instantanés des moteurs de recherche web, sites web sophistiqués de commerce électronique, applications des réseaux sociaux, des suggestions automatiques qui apparaissent lorsqu'ils entrent des termes de recherche, la navigation à facettes, et la mise en surbrillance. Si les clients ne peuvent pas trouver le produit qu'ils recherchent assez rapidement dans un magasin de commerce électronique, ils n'hésiteront pas à aller voir un autre magasin de commerce électronique.

Le détectabilité du produit optimisée par le cloud dans Dynamics 365 Commerce permet aux détaillants de continuer à augmenter la rétention de consommateur et les taux de conversion entre les canaux, à la fois les canaux de commerce électronique et les canaux du point de vente (PDV).

L'expérience de recherche Dynamics 365 Commerce a des fonctionnalités améliorées pour aider les détaillants à atteindre une meilleur détectabilité de produit. En même temps, ces fonctionnalités fournissent une évolutivité et des performances requises pour le trafic de commerce électronique.

## <a name="browse-and-search"></a>Parcourir et rechercher

La pertinence et les performances de la recherche sont des facteurs clés dans l'expérience omnicanale, car la détectabilité de produit repose principalement sur la fonctionnalité de recherche pour l'extraction d'informations et la navigation de contenu. Une expérience de navigation et de recherche efficace permet d'augmenter la conversion.

L'illustration suivante affiche un exemple de fonctionnalité navigation et de recherche classique.

![Rechercher la page de destination](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a>Navigation à facettes et synthèse des choix 

La navigation à facettes permet aux clients d'accéder plus facilement au contenu en les laissant filtrer des raffineurs liés aux termes dans un ensemble de termes. Une fois qu'un client a sélectionné et appliqué les raffineurs, une synthèse des choix s'affiche. 

Grâce à la navigation à facettes, vous pouvez configurer des raffineurs pour différents termes dans un ensemble de termes, sans devoir créer des pages supplémentaires. 

L'illustration suivante présente un exemple dans lequel la navigation à facettes est utilisé dans une recherche.

![Synthèse des choix](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a>Suggestion automatique immersive

La fonctionnalité de suggestion automatique affiche simplement des mots clés qui déclenchent une recherche du mot clé correspondant. En raison de nouvelles améliorations dans Dynamics 365 Commerce, les clients peuvent souvent découvrir des liens vers des produits avant qu'ils aient terminé leur saisie.

Dynamics 365 Commerce prend également en charge la fonctionnalité des correspondances de mot clé dans différentes catégories. Cette fonctionnalité permet aux clients d'afficher le nombre de rapprochements de mots clés dans les catégories et déclencher une recherche d'un mot clé dans d'autres catégories.

L'illustration suivante présente un exemple dans lequel la suggestion automatique immersive est utilisée.

![suggestion automatique immersive](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Trier

Le tri amélioré dans Dynamics 365 Commerce permet aux clients de trier, rechercher et accéder aux résultats de la recherche, et de les raffiner par critères de prix, de nom du produit, et de numéro de produit. Les clients peuvent également trier les résultats selon si un produit est nouveau, parmi les meilleurs ventes ou récemment ajouté.

>[!NOTE]
>Ces fonctionnalités de recherche dans le cloud sont disponibles à partir de la version 10.0.8. Assurez-vous que sous **Paramètres Commerce > Paramètres de configuration**, il existe une entrée pour « ProductSearch.UseAzureSearch » définie sur « true ». 
![Paramètres de configuration pour la recherche dans le cloud](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble de la page d'arrivée de catégories et de la page des résultats de la recherche par défaut](category-search-page-overview.md)

[Gestion des métadonnées SEO](manage-seo-metadata.md)
