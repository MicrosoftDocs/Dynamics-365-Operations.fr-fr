---
title: Module de bloc de contenu
description: Cette rubrique couvre les modules de bloc de contenu et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: a6359c915d053bb00c969b166325f675c0003ead
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980355"
---
# <a name="content-block-module"></a>Module de bloc de contenu


[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de bloc de contenu et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module de bloc de contenu permet de publier des produits ou des promotions sur le marché via une combinaison des images et du texte. Par exemple, un détaillant peut ajouter un module de bloc de contenu à la page d'accueil d'un site de commerce électronique qui permet de promouvoir un nouveau produit et d'attirer l'attention des clients.

Un module de bloc de contenu dépend des données du système de gestion de contenu (CMS). Ce module autonome ne dépend du contexte d'un autre module sur la page. Un module de bloc de contenu peut être mis dans n'importe quelle page de site où un détaillant souhaite lancer sur le marché ou promouvoir un événement (par exemple produits, soldes ou fonctionnalités).

## <a name="examples-of-content-block-module-in-e-commerce"></a>Exemples de module de bloc de contenu dans le commerce électronique

- Un module de bloc de contenu peut être utilisé sur la page d'accueil d'un site de commerce électronique pour mettre en valeur des promotions et de nouveaux produits.
- Un module de bloc de contenu peut être utilisé sur une page de détails de produit pour présenter des informations sur les produits.
- Plusieurs modules de bloc de contenu peuvent être placés à l'intérieur d'un module de carrousel pour mettre en valeur plusieurs produits ou promotions.

## <a name="content-block-modules-and-themes"></a>Modules et thèmes de blocs de contenu

Les modules de bloc de contenu peuvent prendre en charge diverses dispositions et styles basés sur un thème. Par exemple, le thème Fabrikam prend en charge trois variantes de disposition d'un module de bloc de contenu : bannière, fonctionnalité et vignette. La disposition de bannière montre une image en arrière-plan avec une superposition de texte. La disposition de fonctionnalité montre une image et du texte côte à côte. La disposition de vignette permet plusieurs blocs de contenu dans un format de vignette.

De plus, le thème peut exposer différentes propriétés pour chaque disposition. Un développeur de thème peut créer plus de dispositions avec davantage de styles à l'aide du module de bloc de contenu.

L'image suivante montre un exemple d'un module de bloc de contenu avec une disposition de bannière.

![Exemple d'un module de bannière](./media/Hero.PNG)

L'image suivante montre un exemple d'un module de bloc de contenu avec une disposition de fonctionnalité.

![Exemples de modules de fonctionnalités](./media/Feature.PNG)

## <a name="content-block-module-properties"></a>Propriétés du module de bloc de contenu

| Nom de la propriété  | Valeurs | Description |
|----------------|--------|-------------|
| Image          | Fichier image | Une image peut être utilisée pour présenter un produit ou une promotion. Une image peut être chargée dans la galerie d'images, ou une image existante peut être utilisée. |
| En-tête        | Texte d'en-tête et balise d'en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Chaque module de bannière peut avoir un en-tête. Par défaut, la balise d'en-tête **H2** sert pour l'en-tête. Toutefois, la balise peut être modifiée pour satisfaire aux exigences d'accessibilité. |
| Paragraphe      | Texte du paragraphe | Les modules de bannière prennent en charge le texte de paragraphe dans en format de texte enrichi. Certains capacités de texte enrichi de base sont prises en charge, telles que gras, souligné, et italiques, et des liens hypertexte. Certaines de ces fonctionnalités peuvent être remplacées par le thème de la page qui s'applique au module. |
| Lien           | Texte du lien, URL du lien, étiquette ARIA (Applications Internet enrichie accessibles), et **Ouvrir le lien dans le nouvel onglet** | Les modules de bannière prennent en charge un ou plusieurs liens d'« appels à l'action ». Si un lien est ajouté, un texte de lien, une URL, et une étiquette ARIA sont requis. Les étiquettes ARIA doivent être descriptives pour satisfaire aux exigences d'accessibilité. Les liens peuvent être configurés de sorte qu'ils sont ouverts sur un nouvel onglet. |

## <a name="content-block-module-properties-exposed-by-the-fabrikam-theme"></a>Propriétés du module de bloc de contenu exposées par le thème Fabrikam 

| Nom de la propriété  | Valeurs | Description |
|----------------|--------|-------------|
| Emplacement du texte | **Gauche**, **Droite**, **Centre** | Cette propriété définit la position du texte sur l'image. Cela ne s'applique qu'à la disposition de bannière. |
| Thème du texte     | **Clair** ou **Foncé** | Un modèle de couleurs peut être défini pour le texte, selon l'image d'arrière-plan. Par exemple, si l'image a un arrière-plan foncé, un thème clair peut être appliqué pour rendre le texte plus visible et respecter les taux de contraste de couleur à des fins d'accessibilité. Cela ne s'applique qu'à la disposition de bannière.|
| Placement de l'image       | **Gauche**,  **Droite** | Cette propriété spécifie si l'image doit être à gauche ou à droite du texte. Cela ne s'applique qu'à la disposition de fonctionnalité.  |

## <a name="add-a-content-block-module-to-a-new-page"></a>Ajouter un module de bloc de contenu à une nouvelle page

Pour ajouter un module de bannière à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Modèles**, puis créez un modèle de page nommé **Modèle de bloc de contenu**.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un module de bannière.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Utilisez le modèle de bannière que vous venez de créer pour créer une page qui s'appelle **Page de bloc de contenu**.
1. À l'emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis le sélectionnez **Ajoutez le module**.
1. Dans la boîte de dialogue **Ajouter le module**, sous **Sélectionner les modules**, sélectionnez un module de bannière, et sélectionnez **OK**.
1. Dans l'arborescence de plan à gauche, sélectionnez le module de bloc de contenu.
1. Dans le volet de propriétés de droite, sélectionnez **Ajouter une image**. Puis sélectionnez une image existante ou téléchargez une nouvelle image.
1. Sélectionnez **En-tête**.
1. Dans la boîte de dialogue **En-tête**, ajoutez le texte de l'en-tête, sélectionnez le niveau d'en-tête, puis sélectionnez **OK**.
1. Sous **Texte enrichi**, ajoutez le texte comme vous le souhaitez.
1. Sélectionnez **Ajouter un lien**.
1. Dans la boîte de dialogue **Lien**, ajoutez le texte du lien, une URL de lien et une étiquette ARIA pour le lien, puis sélectionnez **OK**.
1. Sélectionnez la disposition **Bannière**.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier. 

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Bannière promotionnelle](add-alert.md)

[Module Carrousel](add-carousel.md)

[Module de bloc de texte](add-content-rich-block.md)

[Module de lecture vidéo](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]