---
title: Module Bannière
description: Cette rubrique couvre les modules de bannière et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c43704992e9759e7207f1b1c9bc958449daa6d1d
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785387"
---
# <a name="hero-module"></a>Module Bannière

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de bannière et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module de bannière permet de publier des produits ou des promotions sur le marché via une combinaison des images et du texte. Par exemple, un détaillant peut ajouter un module de bannière à la page d'accueil d'un site de commerce électronique qui permet de promouvoir un nouveau produit et d'attirer l'attention des clients.

Un module de bannière dépend des données du système de gestion de contenu (CMS). Ce module autonome ne dépend du contexte d'un autre module sur la page. Un module de bannière peut être mis dans n'importe quelle page de site où un détaillant souhaite lancer sur le marché ou promouvoir un événement (par exemple les produits, les soldes ou des fonctionnalités).

## <a name="examples-of-hero-module-in-e-commerce"></a>Exemples de modules de bannière dans le commerce électronique

- Un module de bannière peut être utilisé sur la page d'accueil d'un site de commerce électronique pour mettre en valeur des promotions et de nouveaux produits.
- Un module de bannière peut être utilisé sur une page de détails de produit pour présenter des informations sur les produits.
- Plusieurs modules de bannière peuvent être placés à l'intérieur d'un module de carrousel pour mettre en valeur plusieurs produits ou promotions.

## <a name="hero-module-properties"></a>Propriétés du module de bannière

| Nom de la propriété  | Valeurs | Description |
|----------------|--------|-------------|
| Image          | Fichier image | Une image peut être utilisée pour présenter un produit ou une promotion. Une image peut être chargée dans la galerie d'images, ou une image existante peut être utilisée. |
| En-tête        | Texte d'en-tête et balise d'en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Chaque module de bannière peut avoir un en-tête. Par défaut, la balise d'en-tête **H2** sert pour l'en-tête. Toutefois, la balise peut être modifiée pour satisfaire aux exigences d'accessibilité. |
| Paragraphe      | Texte du paragraphe | Les modules de bannière prennent en charge le texte de paragraphe dans en format de texte enrichi. Certains capacités de texte enrichi de base sont prises en charge, telles que gras, souligné, et italiques, et des liens hypertexte. Certaines de ces fonctionnalités peuvent être remplacées par le thème de la page qui s'applique au module. |
| Lien           | Texte du lien, URL du lien, étiquette ARIA (Applications Internet enrichie accessibles), et **Ouvrir le lien dans le nouvel onglet** | Les modules de bannière prennent en charge un ou plusieurs liens d'« appels à l'action ». Si un lien est ajouté, un texte de lien, une URL, et une étiquette ARIA sont requis. Les étiquettes ARIA doivent être descriptives pour satisfaire aux exigences d'accessibilité. Les liens peuvent être configurés de sorte qu'ils sont ouverts sur un nouvel onglet. |
| Emplacement du texte | **Haut-Gauche**, **Haut-Droite**, **Haut-Centre**, **Bas-Gauche**, **Bas-droite**, **Bas-Centre**, **Centre-gauche**, **Centre-droite** ou **Centre-centre** | Cette propriété définit la position de l'image par rapport à le texte. Par exemple, si **Droite** est sélectionné, l'image apparaît à droite du texte. |
| Thème du texte     | **Clair** ou **Foncé** | Un modèle de couleurs peut être défini pour le texte, selon l'image d'arrière-plan. Par exemple, si l'image a un arrière-plan foncé, un thème clair peut être appliqué pour rendre le texte plus visible et respecter les taux de contraste de couleur à des fins d'accessibilité. |
| Dégradé       | **Vrai** ou **Faux** | Un dégradé peut être appliqué à l'image pour respecter les taux de contraste de couleur à des fins d'accessibilité. |

## <a name="add-a-hero-module-to-a-new-page"></a>Ajouter un module de bannière à une nouvelle page

Pour ajouter un module de bannière à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Modèles**, puis créez un modèle de page nommé **modèle de bannière**.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un module de bannière.
1. Archivez le modèle, et publiez-le.
1. Utilisez le modèle de bannière que vous venez de créer pour créer une page qui s'appelle **page de bannière**.
1. À l'emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis le sélectionnez **Ajoutez le module**.
1. Dans la boîte de dialogue **Ajouter le module**, sous **Sélectionner les modules**, sélectionnez un module de bannière, et sélectionnez **OK**.
1. Dans l'arborescence de contour à gauche, sélectionnez le module de bannière.
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

[Module Fonctionnalité](add-feature-module.md)

[Module Lecteur vidéo](add-video-player.md)
