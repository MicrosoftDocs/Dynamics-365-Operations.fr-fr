---
title: Modules de classements et d’évaluations
description: Cette rubrique couvre les modules de classements et d’évaluations utilisés sur les pages de détails des produits dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: dee9a6a7e2a5278f069958ce00689b1beb9b1bd7
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792145"
---
# <a name="ratings-and-reviews-modules"></a>Modules Classements et Évaluations

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de classements et d’évaluations utilisés sur les pages de détails des produits dans Microsoft Dynamics 365 Commerce.

Les classements et les évaluations des sites web de commerce électronique permettent aux clients d’en savoir plus sur les produits avant de prendre une décision d’achat. Ce sont également un mécanisme de collecte des commentaires des clients sur les produits. 

Les classements sont affichés dans les pages de liste de produit, les pages de liste de catégorie, les pages de résultats de la recherche, et d’autres pages du site. 

Les histogrammes de classement et les évaluations de produits sont affichés sur les pages de détails des produits. Un bouton **Écrire une évaluation** permet aux clients envoyer des classements et les évaluations d’un produit. Ces fonctionnalités des pages de détails des produits sont contrôlées par des modules de classement et d’évaluation.

## <a name="ratings-and-reviews-modules-on-pdps"></a>Modules de classements et d’évaluations sur les pages de détails des produits 

Trois modules affichent le récapitulatif des classements et des évaluations sur les pages de détails des produits :
- Module Écrire une évaluation
- Module Liste de classements de produit
- Module d’histogramme de classements
 
L’illustration suivante présente à quoi les modules de classements et d’évaluation ressemble sur une page de détails de produit.

![Modules de classements et d’évaluations sur une page de détails de produit](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> Pour plus d’informations sur la procédure d’optimisation des modèles et des dispositions de page de détails de produit afin de partager les configurations des modules de classements et d’évaluation entre plusieurs pages de détails des produits sur votre site de commerce électronique, voir [Vue d’ensemble des modèles et dispositions](templates-layouts-overview.md).

L’illustration ci-dessous indique comment la boîte de dialogue **Ajouter un module** présente les modules de classements et d’évaluation dans Dynamics 365 Commerce.
![Boîte de dialogue Ajouter un module](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a>Module Écrire une évaluation

Le module Écrire une évaluation inclut un bouton **Écrire une évaluation** qui permet aux utilisateurs de se connecter, d’affecter un classement, et d’écrire une évaluation de produit. Ce module permet également aux utilisateurs de modifier un classement ou une évaluation qu’il a précédemment soumis. Ce module apparaît généralement au-dessus des modules d’histogramme des classements et de liste d’évaluations de produit sur une page de détails de produit.
L’illustration suivante présente la boîte de dialogue **Écrire une évaluation** qui s’affiche lorsqu’un client sélectionne **Écrire une évaluation**. Le client peut utiliser cette boîte de dialogue pour envoyer un classement et une évaluation.
![Boîte de dialogue Écrire une évaluation](media/rnr-eCommerce-write-review-module.png) Le tableau suivant montre la propriété du module Écrire une évaluation qui doit être configurée dans l’outil de création.
| Nom de la propriété | Valeur        | Description de la propriété                 |
|---------------|--------------|--------------------------------------|
| Nom          | Écrire une évaluation | Nom du module Écrire une évaluation. |

### <a name="ratings-histogram-module"></a>Module d’histogramme de classements

Le module d’histogramme de classements affiche un histogramme de classements. Ce module s’affiche généralement entre le module Écrire une évaluation et le module de liste d’évaluations de produit sur une page de détails de produit.
Le module d’histogramme de classements ne requiert aucune configuration. Vous devez simplement ajouter le module dans modèle de page de détails de produit. Les illustrations suivantes présentent à quoi un modèle de page de détails de produit dans Dynamics 365 Commerce lorsque des modules de classements et d’évaluations sont configurés pour s’afficher sur les pages de détails de produit.
![Modèle de page de détails de produit lorsque les classements et les évaluations sont configurés pour s’afficher sur des pages de détails de produit](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a>Module Liste de classements de produit

Le modules de liste d’évaluations de produit affiche une liste des évaluations de produit avec des options de tri, de filtre, et de numérotation de pages. Ce module s’affiche généralement après le module d’histogramme de classements sur une page de détails de produit.
Le tableau suivant montre les propriétés du module de liste d’évaluations de produits qui doivent être configurées dans l’outil de création.

| Nom de la propriété              | Valeur | Description de la propriété |
|----------------------------|-------| ---------------------|
| Évaluations affichés sur chaque page | 10    | Nombre d’évaluations qui doivent figurer à la fois sur une page de détails de produit. Les boutons **Suivant** et **Précédent** sont inclus, afin que les utilisateurs puissent circuler entre les pages d’évaluations. |

#### <a name="ratings-histogram--summary-view"></a>Histogramme de classements – Vue de synthèse

Le module de liste d’évaluations de produit inclut un emplacement dans lequel vous pouvez ajouter un module d’histogramme des classements. L’illustration ci-dessous indique comment vous pouvez ajouter un module d’histogramme de classements dans le module de liste d’évaluations de produit dans Dynamics 365 Commerce.

![Ajout d’un module histogramme de classements dans un module de liste d’évaluations de produit](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Conteneur](add-container-module.md)

[Module Panier](add-cart-module.md)

[Module Validation](add-checkout-module.md)

[Module de confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]