---
title: Configuration des évaluations et avis
description: Cette rubrique décrit la procédure de configuration de votre site de commerce électronique pour afficher les classements et les évaluations des clients dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0aac4b680590a95f465d33950f2933c4a4582e54
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002195"
---
# <a name="configure-ratings-and-reviews"></a>Configuration des évaluations et avis


[!include [banner](includes/banner.md)]

Cette rubrique décrit la procédure de configuration de votre site de commerce électronique pour afficher les classements et les évaluations des clients dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Les classements et les évaluations des sites web de commerce électronique permettent aux clients d'en savoir plus sur les produits avant de prendre une décision d'achat, en leur affichant ce que d'autres clients pensent de ces produits. Pour les sites web de commerce électronique, les classements et les évaluations sont également un mécanisme de collecte des commentaires des clients sur les produits. 

Les classements sont affichés dans les pages de liste de produit, les pages de liste de catégorie, les pages de résultats de la recherche, et d'autres pages du site. Les histogrammes de classement et les évaluations de produits sont affichés sur les pages de détails des produits. Un bouton **Écrire une évaluation** permet aux clients envoyer des classements et les évaluations d'un produit.

## <a name="ratings-and-reviews-modules-on-pdps"></a>Modules de classements et d'évaluations sur les pages de détails des produits 

Trois modules affichent le récapitulatif des classements et des évaluations sur les pages de détails des produits :

- Module Écrire une évaluation
- Module Liste de classements de produit
- Module d'histogramme de classements
 
L'illustration suivante présente à quoi les modules de classements et d'évaluation ressemble sur une page de détails de produit.

![Modules de classements et d'évaluations sur une page de détails de produit](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> Pour plus d'informations sur la procédure d'optimisation des modèles et des dispositions de page de détails de produit afin de partager les configurations des modules de classements et d'évaluation entre plusieurs pages de détails des produits sur votre site de commerce électronique, voir [Vue d'ensemble des modèles et dispositions](templates-layouts-overview.md).

L'illustration ci-dessous indique comment la boîte de dialogue **Ajouter un module** présente les modules de classements et d'évaluation dans Dynamics 365 Commerce.

![Boîte de dialogue Ajouter un module](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a>Module Écrire une évaluation

Le module Écrire une évaluation inclut un bouton **Écrire une évaluation** qui permet aux utilisateurs de se connecter, d'affecter un classement, et d'écrire une évaluation de produit. Ce module permet également aux utilisateurs de modifier un classement ou une évaluation qu'il a précédemment soumis. Ce module apparaît généralement au-dessus des modules d'histogramme des classements et de liste d'évaluations de produit sur une page de détails de produit.

L'illustration suivante présente la boîte de dialogue **Écrire une évaluation** qui s'affiche lorsqu'un client sélectionne **Écrire une évaluation**. Le client peut utiliser cette boîte de dialogue pour envoyer un classement et une évaluation.

![Boîte de dialogue Écrire une évaluation](media/rnr-eCommerce-write-review-module.png)

Le tableau suivant montre la propriété du module Écrire une évaluation qui doit être configurée dans l'outil de création.

| Nom de la propriété | Valeur        | Description de la propriété                 |
|---------------|--------------|--------------------------------------|
| Nom          | Écrire une évaluation | Nom du module Écrire une évaluation. |

### <a name="ratings-histogram-module"></a>Module d'histogramme de classements

Le module d'histogramme de classements affiche un histogramme de classements. Ce module s'affiche généralement entre le module Écrire une évaluation et le module de liste d'évaluations de produit sur une page de détails de produit.

Le module d'histogramme de classements ne requiert aucune configuration. Vous devez simplement ajouter le module dans modèle de page de détails de produit. 

Les illustrations suivantes présentent à quoi un modèle de page de détails de produit dans Dynamics 365 Commerce lorsque des modules de classements et d'évaluations sont configurés pour s'afficher sur les pages de détails de produit.

![Modèle de page de détails de produit lorsque les classements et les évaluations sont configurés pour s'afficher sur des pages de détails de produit](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a>Module Liste de classements de produit

Le modules de liste d'évaluations de produit affiche une liste des évaluations de produit avec des options de tri, de filtre, et de numérotation de pages. Ce module s'affiche généralement après le module d'histogramme de classements sur une page de détails de produit.

Le tableau suivant montre les propriétés du module de liste d'évaluations de produits qui doivent être configurées dans l'outil de création.

| Nom de la propriété              | Valeur | Description de la propriété |
|----------------------------|-------| ---------------------|
| Évaluations affichés sur chaque page | 10    | Nombre d'évaluations qui doivent figurer à la fois sur une page de détails de produit. Les boutons **Suivant** et **Précédent** sont inclus, afin que les utilisateurs puissent circuler entre les pages d'évaluations. |

#### <a name="ratings-histogram--summary-view"></a>Histogramme de classements – Vue de synthèse

Le module de liste d'évaluations de produit inclut un emplacement dans lequel vous pouvez ajouter un module d'histogramme des classements. L'illustration ci-dessous indique comment vous pouvez ajouter un module d'histogramme de classements dans le module de liste d'évaluations de produit dans Dynamics 365 Commerce.

![Ajout d'un module histogramme de classements dans un module de liste d'évaluations de produit](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Configuration d'un site pour afficher des classements et des évaluations

Les valeurs de configuration pour les classements et les évaluations, telles que l'ID client, vérifier la longueur du texte, et analyser la longueur du titre, sont configurées au niveau de le site. 

Pour configurer un site afin d'afficher des classements et des évaluations, procédez comme suit. 

1. Accédez à **Accueil \> Sites**.
1. Sélectionnez le nom de votre site. 
1. Accédez à **Gestion du site \> Extensibilité**. 
1. Dans le champ **Vérifier la longueur maximale du texte**, entrez le nombre maximal de caractères que le texte d'évaluation peut comporter (par exemple, **1 000**). 
1. Dans le champ **Vérifier la longueur maximale du titre**, entrez le nombre maximal de caractères que les titres d'évaluation peuvent comporter (par exemple, **55**). 
1. Sélectionnez **Enregistrer et publier**. 

L'illustration suivante présente à quoi cette configuration ressemble dans Dynamics 365 Commerce.

![Configuration d'un site pour afficher des classements et des évaluations](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Association d'un classement de produit à la section Évaluation d'une page de détails de produit

Un classement de produit apparaît sous le titre de produit en haut de la page de détails de produit. Le classement de produit peut être configuré pour qu'il soit lié à la section **Évaluations** de la même page de détails du produit. 

Pour lier un classement de produit à la section **Évaluations** de la page de détails de produit, procédez comme suit.

1. Ouvrez le modèle de page de détails de produit. 
1. Accédez à **Paramètres du module de conteneur Zone d'achat**.
1. Sous **Zone d'achat**, sélectionnez **Classements de produit**, puis activez la case à cocher **Lier le clic au module complet d'évaluations**.

L'illustration suivante présente à quoi cette configuration ressemble dans Dynamics 365 Commerce.

![Association d'un classement de produit à la section Évaluation d'une page de détails de produit](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Configurer le lien de la page de confidentialité et de politique

Pour configurer le lien de la page de confidentialité et de politique, procédez comme suit.

1. Accédez à **Accueil \> Sites**.
1. Sélectionnez le nom de votre site. 
1. Accédez à **Gestion du site \> Extensibilité**
1. Dans l'onglet **Acheminements**, sous **Confidentialité et politique RNR**, sélectionnez **Ajouter un lien**. Si un lien est déjà entré, et si vous souhaitez le remplacer, sélectionnez le lien. 
1. Dans la boîte de dialogue **Ajouter un lien**, sélectionnez le lien de la page de confidentialité et de politique, puis sélectionnez **OK**. 
1. Sélectionnez **Enregistrer et publier**. 

L'illustration suivante présente à quoi cette configuration ressemble dans Dynamics 365 Commerce.

![Configuration du lien de la page de confidentialité et de politique](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des évaluations et avis](ratings-reviews-overview.md)

[Choix d'utilisation des évaluations et avis](opt-in-ratings-reviews.md)

[Gestion des évaluations et avis](manage-reviews.md)

[Synchronisation des évaluations de produit dans Dynamics 365 Retail](sync-product-ratings.md)
