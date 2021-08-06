---
title: Module de fonctionnalité interactive
description: Cette rubrique couvre les modules de fonctionnalités interactives et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
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
ms.openlocfilehash: b1d00b9173fd1d5faee71e0fec6c9d1546989e41
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638852"
---
# <a name="interactive-feature-module"></a>Module de fonctionnalité interactive

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de fonctionnalités interactives et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Les modules de fonctionnalités interactives sont de type mosaïque et peuvent être utilisés pour commercialiser plusieurs catégories de produits ou marques de produits en utilisant une combinaison d’images et de texte. Par exemple, un détaillant peut ajouter un module de fonctionnalité interactive à la page d’accueil d’un site de commerce électronique pour promouvoir les catégories les plus vendues. Le module de fonction interactive ressemble au module de liste de vignettes, mais il a une disposition différente et des fonctionnalités d’interaction différentes.

Chaque module de fonction interactive est une collection de modules d’éléments de fonctionnalités interactives. Chaque module d’élément de fonctionnalité dépend des données du système de gestion de contenu (CMS). Il ne dépend d’aucun autre module ou donnée du siège de Commerce. Le module de fonctionnalités interactives peut être ajouté à n’importe quelle page de site où un détaillant souhaite lancer sur le marché ou promouvoir un événement (par exemple les produits, les catégories ou les marques).

> [!IMPORTANT]
> - Le module de fonctionnalités interactives est disponible à partir de la version 10.0.20 de Dynamics 365 Commerce.
> - Le module de fonctionnalités interactives est présenté dans le thème Adventure Works.

L’illustration suivante montre un exemple de module de fonctionnalités interactives sur la page d’accueil Adventure Works.

![Exemple de module de fonctionnalités interactives sur la page d’accueil d’Adventure Works](./media/Feature.PNG)

## <a name="interactive-feature-module-and-themes"></a>Module et thèmes de fonctionnalités interactives

Le module de fonctionnalité interactive peut prendre en charge diverses dispositions et styles basés sur un thème. Par exemple, dans le thème Adventure Works, le module de fonctionnalité interactive a une disposition en deux colonnes qui affiche des effets d’animation lorsqu’un utilisateur du site survole chaque élément. Le module de fonction interactive est optimisé pour un nombre pair d’images disposées dans une disposition à deux colonnes.

## <a name="interactive-feature-module-properties"></a>Propriétés du module de fonctionnalité interactive

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| Titre       | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Un en-tête de texte pour le module de fonctionnalité interactive. |

## <a name="interactive-feature-item-module-properties"></a>Propriétés du module d’élément de fonctionnalité interactive

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| Image         | Fichier image | Image qui représente un produit ou une catégorie. L’image peut être chargée dans le générateur de site de la bibliothèque multimédia dans Commerce, ou une image existante peut être utilisée. |
| Titre       | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Par défaut, la balise d'en-tête **H2** est utilisée pour le titre, mais la balise peut être modifiée pour répondre aux besoins en accessibilité. |
| Paragraphe     | Texte du paragraphe | Les modules prennent en charge le texte de paragraphe dans en format de texte enrichi. Certains capacités de texte enrichi de base sont prises en charge, telles que les liens hypertexte, le gras, le souligné, et l'italique. Certaines de ces fonctionnalités peuvent être remplacées par le thème de la page qui s’applique au module. |
| Lien          | Texte du lien, URL du lien, étiquette ARIA (Applications Internet enrichie accessibles), et sélecteur **Ouvrir le lien dans le nouvel onglet** | Le module prend en charge un ou plusieurs liens d’« appels à l’action ». Si un lien est ajouté, un texte de lien, une URL, et une étiquette ARIA sont requis. Les étiquettes ARIA doivent être descriptives pour satisfaire aux exigences d’accessibilité. Les liens peuvent être configurés de sorte qu’ils sont ouverts sur un nouvel onglet. |

## <a name="add-an-interactive-feature-module-to-a-new-page"></a>Ajouter un module de fonctionnalité interactive à une nouvelle page

Pour ajouter un module de fonctionnalité interactive à une nouvelle page et définir les propriétés requises dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **Modèles** et ouvrez le modèle marketing pour la page d’accueil de votre site (ou créez un nouveau modèle marketing).
1. Dans l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Fonctionnalité interactive**, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages** et ouvrez la page d’accueil du site (ou créez une nouvelle page d’accueil à l’aide du modèle marketing).
1. À l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis le sélectionnez **Ajoutez le module**.
1. Dans la boîte de dialogue **Ajouter le module**, sous **Sélectionner les modules**, sélectionnez le module **Fonctionnalité interactive**, puis sélectionnez **OK**.
1. Dans le volet de propriété du module de fonctionnalité interactive, ajoutez un en-tête.
1. Dans l’emplacement **Fonctionnalité interactive**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Élément de fonctionnalité interactive**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module d’élément de fonctionnalité interactive, ajoutez une image, un texte d’en-tête, un texte de paragraphe et une URL.
1. Ajoutez et configurez des modules d’élément de fonctionnalités interactives supplémentaires selon vos besoins.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Thème Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
