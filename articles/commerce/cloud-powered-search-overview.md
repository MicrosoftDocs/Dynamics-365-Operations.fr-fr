---
title: Vue d’ensemble de la recherche dans le cloud
description: Cet article fournit une vue d’ensemble de recherche optimisée par le cloud dans Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 02/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.assetid: ''
ms.openlocfilehash: ed80ff42ea5c6e6a904ea2855953d006f66aad37
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273664"
---
# <a name="cloud-powered-search-overview"></a>Vue d’ensemble de la recherche dans le cloud

[!include [banner](includes/banner.md)]

Cet article fournit une vue d’ensemble de recherche optimisée par le cloud dans Microsoft Dynamics 365 Commerce.

La détectabilité du produit garantit que les clients peuvent rapidement et facilement trouver des produits en parcourant les catégories, en les recherchant, et en les filtrant. Les détaillants considèrent la découverte de produits comme un outil principal pour l’interaction client sur tous les canaux optimisés par Cloud Scale Unit (CSU), tels que le commerce électronique et les points de vente (PDV).

Les clients sont accoutumés aux temps de réponse presque instantanés des moteurs de recherche web, sites web sophistiqués de commerce électronique, applications des réseaux sociaux, des suggestions automatiques qui apparaissent lorsqu’ils entrent des termes de recherche, la navigation à facettes, et la mise en surbrillance. Si les clients ne peuvent pas trouver rapidement le produit qu’ils recherchent assez rapidement dans un magasin de commerce électronique, ils n’hésiteront pas à aller voir un autre magasin de commerce électronique.

Le détectabilité du produit optimisée par le cloud dans Commerce permet aux détaillants de continuer à augmenter la rétention de consommateur et les taux de conversion entre les canaux, à la fois les canaux de commerce électronique et les canaux du point de vente (CSU).

L’expérience de recherche Commerce a des fonctionnalités améliorées pour aider les détaillants à atteindre une meilleur détectabilité de produit. En même temps, ces fonctionnalités fournissent une évolutivité et des performances requises pour le trafic de commerce électronique.

## <a name="browse-and-search"></a>Parcourir et rechercher

La pertinence et les performances de la recherche sont des facteurs clés dans l’expérience omnicanale, car la détectabilité de produit repose principalement sur la fonctionnalité de recherche pour l’extraction d’informations et la navigation de contenu. Une expérience de navigation et de recherche efficace permet d’augmenter la conversion.

L’illustration suivante affiche un exemple de fonctionnalité navigation et de recherche classique.

![Rechercher la page de destination.](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a>Navigation à facettes et synthèse des choix 

La navigation à facettes permet aux clients d’accéder plus facilement au contenu en les laissant filtrer des raffineurs liés aux termes dans un ensemble de termes. Une fois qu’un client a sélectionné et appliqué les raffineurs, une synthèse des choix s’affiche. 

Grâce à la navigation à facettes, vous pouvez configurer des raffineurs pour différents termes dans un ensemble de termes, sans devoir créer des pages supplémentaires. 

L’illustration suivante présente un exemple dans lequel la navigation à facettes est utilisé dans une recherche.

![Synthèse des choix.](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a>Suggestion automatique immersive

La fonctionnalité de suggestion automatique affiche des mots clés qui déclenchent une recherche du mot clé correspondant. En raison de nouvelles améliorations dans Commerce, les clients peuvent souvent découvrir des liens vers des produits avant qu’ils aient terminé leur saisie.

Commerce prend également en charge la fonctionnalité des correspondances de mot clé dans différentes catégories. Cette fonctionnalité permet aux clients d’afficher le nombre de rapprochements de mots clés dans les catégories et déclencher une recherche d’un mot clé dans d’autres catégories.

L’illustration suivante présente un exemple dans lequel la suggestion automatique immersive est utilisée.

![suggestion automatique immersive.](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Trier

La fonctionnalité de tri permet aux clients de trier, de rechercher et de parcourir des catégories, puis d’affiner les résultats par critères de prix, de nom du produit, et de numéro de produit. Si vous activez [Recommandations de produits](product-recommendations.md) dans votre environnement, les clients peuvent également trier les résultats en fonction de critères de tri avancés tels que les nouveautés, les meilleures ventes et les tendances.


> [!NOTE]
> Ces fonctionnalités de recherche dans le cloud sont disponibles à partir de la version 10.0.8. Assurez-vous que sous **Paramètres Commerce > Paramètres de configuration**, il existe une entrée pour « ProductSearch.UseAzureSearch » définie sur « true ». 
![Paramètres de configuration pour la recherche dans le cloud.](./media/CloudPoweredSearchConfigurationParameters.png)
>Des options de tri avancées telles que les nouveautés, les meilleures ventes et les tendances sont disponibles avec la version 9.35+ de Commerce SSK et la version 10.0.20 de Dynamics 365 Commerce.  


## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la page d’arrivée de catégories et de la page des résultats de la recherche par défaut](category-search-page-overview.md)

[Gestion des métadonnées SEO](manage-seo-metadata.md)


[!INCLUDE [footer-include](../includes/footer-banner.md)]
