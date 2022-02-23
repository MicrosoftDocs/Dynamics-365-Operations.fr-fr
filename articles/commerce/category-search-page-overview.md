---
title: Vue d'ensemble de la page d'arrivée de catégories et de la page des résultats de la recherche par défaut
description: Cette rubrique fournit une vue d'ensemble de la page d'arrivée de catégories et la page des résultats de la recherche par défaut dans Dynamics 365 Commerce.
author: ashishmsft
manager: annbe
ms.date: 06/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e85449c10fa4a768a144ce423a77bd1fc2c94352
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412234"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a>Vue d'ensemble de la page d'arrivée de catégories et de la page des résultats de la recherche par défaut

[!include [banner](includes/banner.md)]

Cette rubrique fournit une vue d'ensemble de la page d'arrivée de catégories et la page des résultats de la recherche par défaut dans Microsoft Dynamics 365 Commerce e-Commerce.

## <a name="default-category-landing-page"></a>Page d'arrivée de catégorie par défaut

La page par défaut d'atterrissage de catégorie est la page vers laquelle les utilisateurs du site web sont généralement dirigés lorsqu'ils sélectionnent une catégorie dans la hiérarchie de navigation. La page de catégorie vous permet de parcourir, et vous pouvez également trier et affiner les produits commandés par catégorie.

![Page d'arrivée de catégorie par défaut](./media/SimpleCategoryLandingDressCategory.png)

En haut de la page se trouve un en-tête qui affiche toutes les catégories de produits et d'autres pages que le responsable de la promotion des ventes a classés par catégorie. La configuration est effectuée dans le cadre de la configuration de la hiérarchie de navigation du canal. Au bas de la page se trouve un pied de page qui inclut des liens rapides vers diverses rubriques qui peuvent intéresser un client.

Les composants suivants sont essentiels pour une catégorie :

- **Vignettes de placement de produit** affiche les produits que le responsable de promotion des ventes a définis dans une catégorie dans le cadre de la configuration de la hiérarchie de navigation.
- **Raffineurs et synthèse des choix** sont des filtres qui fournissent des nombres et qui peuvent être utilisés pour affiner les articles. Le responsable de la promotion des ventes les configure dans le cadre de la configuration des métadonnées liées aux catégories de canaux et aux attributs de produit.
- Les **Options de tri** sont utilisés par les visiteurs de site web pour trier les produits. Par défaut, les options de tri suivantes sont disponibles :

    - Prix – du plus bas au plus élevé
    - Prix – du plus élevé au plus bas
    - Nom du produit – \[A à Z\]
    - Nom du produit – \[Z à A\]
    - Classements – du plus bas au plus élevé
    - Classements – du plus élevé au plus bas

- La **Pagination** permet aux visiteurs de site web se déplacer d'une page de résultats de produit catégorisé à une autre page.
- Le **Nombre total** fournit le nombre total de produits définis dans une catégorie.

## <a name="enrich-a-category-landing-page"></a>Enrichir une page d'arrivée de catégorie

Si vous souhaitez une page d'arrivée de catégorie pour avoir une expérience plus personnalisée pour une catégorie spécifique, vous pouvez « enrichir » la page d'arrivée de catégorie pour cette catégorie. Par exemple, vous pouvez ajouter une vidéo de marketing et de la narration de catégorie pour obtenir l'attention du client. Pour plus d'informations, voir [Enrichir une page d'arrivée de catégorie](enrich-category-page.md).

![Page d'arrivée de catégorie enrichie](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a>Suggestion automatique et pages de résultats de la recherche

Les utilisateurs du site web peuvent explorer un site en accédant à une catégorie de la hiérarchie de navigation ou en entrant un terme de recherche dans le champ de recherche.

Dès que les utilisateurs commencent à saisir dans le champ de recherche, ils rencontrent la fonctionnalité de suggestion automatique immersive qui suggère des termes de recherche.

Voici certains types de suggestions qui peuvent être affichés :

- Les **Mots clés** permettent de rechercher des articles parmi tous les produits qui sont assortis au canal.
- Les **Produits** fournissent des liens directs vers la page de détails des produits.
- Les **Suggestions de recherche de catégorie étendue** répertorie différentes catégories et permettent aux utilisateurs de rechercher le mot clé dans une catégorie spécifique.

![Suggestion automatique immersive](./media/ImmersiveAutoSuggestUX.png)

Lorsque les utilisateurs sélectionnent l'un des mot clé ou des suggestions de recherche de catégorie étendue, ou lorsqu'il n'y a aucune suggestion de terme de recherche qu'ils saisissent, ils sont redirigés à une page de résultats de la recherche. Les utilisateurs peuvent alors parcourir, trier et affiner la liste des résultats de la recherche pour rechercher l'article souhaité.

![Rechercher la page de destination](./media/SearchLanding.png)

Les composants suivants sont essentiels pour une page de résultats de recherche :

- Les **Vignettes de placement de produit** affiche les produits pour la recherche d'utilisateur. Par défaut, ces vignettes sont triées par le score de pertinence de la recherche optimisée par le cloud pour la recherche d'utilisateur.
- **Raffineurs et synthèse des choix** sont des filtres qui fournissent des nombres et qui peuvent être utilisés pour affiner les articles. Le responsable de la promotion des ventes les configure dans le cadre de la configuration des métadonnées des « catégories de canaux et aux attributs de produit ».
- Les **Options de tri** sont utilisés par les visiteurs de site web pour trier les produits. Par défaut, les options de tri suivantes sont disponibles :

    - Prix – du plus bas au plus élevé
    - Prix – du plus élevé au plus bas
    - Nom du produit – \[A à Z\]
    - Nom du produit – \[Z à A\]
    - Classements – du plus bas au plus élevé
    - Classements – du plus élevé au plus bas
    - Par défaut

- La **Pagination** permet aux visiteurs de site web se déplacer d'une page de résultats de produit catégorisé à une autre page.
- Le **Nombre total** fournit le nombre total de produits définis dans une catégorie et qui correspondent aux critères de recherche.

>[!NOTE]
>Ces fonctionnalités de recherche dans le cloud sont disponibles à partir de la version 10.0.8. Assurez-vous que sous **Paramètres Commerce > Paramètres de configuration**, il existe une entrée pour « ProductSearch.UseAzureSearch » définie sur « true ». 
![Paramètres de configuration pour la recherche dans le cloud](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble de la recherche dans le cloud](cloud-powered-search-overview.md)

[Vue d'ensemble de la page d'accueil](quick-tour-home-page.md)

[Vue d'ensemble des pages de détails de produit](quick-tour-pdp.md)

[Vue d'ensemble des pages de panier et de caisse](quick-tour-cart-checkout.md)

[Vue d'ensemble des pages de gestion des comptes](quick-tour-account-management.md)

