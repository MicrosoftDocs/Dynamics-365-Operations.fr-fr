---
title: Module Fonctionnalité
description: Cette rubrique couvre les modules de fonctionnalités et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785281"
---
# <a name="feature-module"></a>Module Fonctionnalité 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de fonctionnalités et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module de fonctionnalités permet de publier des produits ou des promotions sur le marché via une combinaison des images et du texte. Par exemple, un détaillant peut ajouter un module de fonctionnalités à une page de détails des produits pour souligner les fonctionnalités du produit.

Un module de fonctionnalités dépend des données du système de gestion de contenu (CMS). Ce module autonome ne dépend du contexte d'un autre module sur la page. Un module de fonctionnalités peut être mis dans n'importe quelle page de site où un détaillant souhaite lancer sur le marché ou promouvoir un événement (par exemple les produits, les soldes ou des fonctionnalités).

## <a name="examples-of-feature-modules-in-e-commerce"></a>Exemples de modules de fonctionnalités dans le commerce électronique

Un module de fonctionnalités peut être utilisé sur les pages suivantes :

- Une page de détails du produit, pour présenter les fonctionnalités du produit
- La page d'accueil, pour promouvoir des produits
- Une page de catégorie, pour mettre en valeur une catégorie de produits

## <a name="feature-module-properties"></a>Propriétés du module de fonctionnalités

| Nom de la propriété     | Valeurs | Description |
|-------------------|--------|-------------|
| Image             | Fichier image | Une image peut être utilisée pour commercialiser le produit ou la promotion. Une image peut être chargée dans la galerie d'images, ou une image existante peut être utilisée. |
| En-tête           | Texte d'en-tête et balise d'en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Chaque module de fonctionnalités peut avoir un en-tête. Par défaut, la balise d'en-tête **H2** sert pour l'en-tête. Toutefois, la balise peut être modifiée pour satisfaire aux exigences d'accessibilité. |
| Paragraphe         | Texte du paragraphe | Les modules de fonctionnalités prennent en charge le texte de paragraphe dans en format de texte enrichi. Certains capacités de texte enrichi de base sont prises en charge, telles que gras, souligné, et italiques, et des liens hypertexte. Certaines de ces fonctionnalités peuvent être remplacées par le thème de la page qui s'applique au module. |
| Lien              | Texte du lien, URL du lien, étiquette ARIA (Applications Internet enrichie accessibles), et **Ouvrir le lien dans le nouvel onglet** | Les modules de fonctionnalités prennent en charge un ou plusieurs liens d'« appels à l'action ». Si un lien est ajouté, un texte de lien, une URL, et une étiquette ARIA sont requis. Les étiquettes ARIA doivent être descriptives pour satisfaire aux exigences d'accessibilité. Les liens peuvent être configurés de sorte qu'ils sont ouverts sur un nouvel onglet. |
| Placement de l'image   | **Droite**, **Gauche**, **Haut** ou **Bas** | Cette propriété définit la position de l'image par rapport à le texte. Par exemple, si **Droite** est sélectionné, l'image apparaît à droite du texte. |
| Taille de colonne d’image | Une valeur de **1** à **12** | Cette propriété définit la taille de l'image par rapport à le texte. La taille est exprimée sous forme de nombre de colonnes dans la page. Il y a 12 colonnes dans une page. Par défaut, le texte et l'image sont de taille égale (six colonnes chacun). Toutefois, la taille peut être ajustée au besoin. |

## <a name="add-a-feature-module-to-a-new-page"></a>Ajouter un module de fonctionnalités à une nouvelle page 

Pour ajouter un module de fonctionnalités à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Modèles**, puis créez un modèle de page nommé **modèle de fonctionnalité**.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un module de fonctionnalités.
1. Archivez le modèle, et publiez-le.
1. Utilisez le modèle de fonctionnalités que vous venez de créer pour créer une page qui s'appelle **page Fonctionnalités**.
1. À l'emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis le sélectionnez **Ajoutez le module**.
1. Dans la boîte de dialogue **Ajouter le module**, sous **Sélectionner les modules**, sélectionnez un module de fonctionnalités, et sélectionnez **OK**.
1. Dans l'arborescence de contour à gauche, sélectionnez le module de fonctionnalités.
1. Dans le volet de propriétés de droite, sélectionnez **Ajouter une image**. Puis sélectionnez une image existante ou téléchargez une nouvelle image.
1. Sélectionnez **En-tête**.
1. Dans la boîte de dialogue **En-tête**, ajoutez le texte de l'en-tête, sélectionnez le niveau d'en-tête, puis sélectionnez **OK**.
1. Sous **Texte enrichi**, ajoutez le texte comme vous le souhaitez.
1. Sélectionnez **Ajouter le lien d'action**.
1. Dans la boîte de dialogue **Lien d'action**, ajoutez le texte du lien, une URL de lien, et une étiquette ARIA pour le lien, puis sélectionnez **OK**.
1. Enregistrer la page et affichez un aperçu vos modifications.
1. Archivez la page, et publiez-la.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Alerte](add-alert.md)

[Module Carrousel](add-carousel.md)

[Module de bloc de contenu riche](add-content-rich-block.md)

[Module Placement de contenu](add-content-placement-modules.md)

[Module Bannière](add-hero-module.md)

[Module Lecteur vidéo](add-video-player.md)
