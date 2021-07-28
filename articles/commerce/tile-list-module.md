---
title: Module de liste de titres
description: Cette rubrique couvre les modules de liste de vignettes et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 2da3c0415e996cadb5261d90c6353aa28bff3abb
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479456"
---
# <a name="tile-list-module"></a>Module de liste de titres

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique couvre les modules de liste de vignettes et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Un module de liste de vignettes est une collection de vignettes dans un carrousel. Il est utilisé pour commercialiser des catégories de produits ou des marques de produits à travers des images et du texte. Par exemple, un détaillant peut ajouter un module de liste de vignettes à la page d’accueil d’un site de commerce électronique pour promouvoir toutes les catégories les plus vendues.

Un module de liste de vignettes dépend des données du système de gestion de contenu (CMS). Il ne dépend d’aucun autre module ou donnée du siège de Commerce. Le module de liste de vignettes peut être ajouté à n’importe quelle page de site où un détaillant souhaite lancer sur le marché ou promouvoir un événement (par exemple les produits, les catégories ou les marques).

L’illustration suivante montre un exemple de module de liste de vignettes et de modules de vignettes sur la page d’accueil Adventure Works.

![L’exemple montre un module de liste de vignettes et de modules de vignettes sur la page d’accueil Adventure Works.](./media/Tile_list.PNG)

> [!IMPORTANT]
> Le module de liste de vignettes est disponible à partir de la version 10.0.20 de Dynamics 365 Commerce.
> Le module de liste de vignettes est présenté dans le thème Adventure Works.

## <a name="tile-list-modules-and-themes"></a>Modules et thèmes de liste de vignettes

Le module de liste de vignettes peut prendre en charge diverses dispositions et styles basés sur un thème. Par exemple, dans le thème Adventure Works, les vignettes affichent un effet d’animation lorsque les utilisateurs du site les survolent. Chaque thème peut contenir des propriétés supplémentaires pour la liste de vignettes et les modules de vignettes. Les développeurs de thèmes peuvent également créer des dispositions supplémentaires pour la liste de vignettes et les modules de vignettes.

## <a name="tile-list-module-properties"></a>Propriétés du module de liste de vignettes

| Nom de la propriété | Valeurs | Description  |
|---------------|--------|-------------|
| Titre       | Texte d’en-tête et balise d’en-tête | Un en-tête de texte pour le module de liste de vignettes. |

## <a name="tile-module-properties"></a>Propriétés du module de vignettes

| Nom de la propriété | Valeurs | Description  |
|---------------|--------|-------------|
| Image         | Fichier image | Une image peut être utilisée pour présenter un produit ou une catégorie. L’image peut être chargée dans le générateur de site de la bibliothèque multimédia dans Commerce, ou une image existante peut être utilisée. |
| Titre       | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Par défaut, la balise d'en-tête **H2** est utilisée pour le titre, mais la balise peut être modifiée pour répondre aux besoins en accessibilité. |
| Paragraphe     | Texte du paragraphe | Les modules prennent en charge le texte de paragraphe dans en format de texte enrichi. Certains capacités de texte enrichi de base sont prises en charge, telles que les liens hypertexte, le gras, le souligné, et l'italique. Certaines de ces fonctionnalités peuvent être remplacées par le thème de la page qui s’applique au module. |
| Lien          | Texte du lien, URL du lien, étiquette ARIA (Applications Internet enrichie accessibles), et **Ouvrir le lien dans le nouvel onglet** | Les modules prennent en charge un ou plusieurs liens d’« appels à l’action ». Si un lien est ajouté, un texte de lien, une URL, et une étiquette ARIA sont requis. Les étiquettes ARIA doivent être descriptives pour satisfaire aux exigences d’accessibilité. Les liens peuvent être configurés de sorte qu’ils sont ouverts sur un nouvel onglet. |
| Lien de vignette     | Texte du lien, URL du lien, étiquette ARIA et sélecteur **Ouvrir le lien dans le nouvel onglet** | Cette propriété permet de définir un lien « appel à l’action ». Si un lien est ajouté, un texte de lien, une URL, et une étiquette ARIA sont requis. Les étiquettes ARIA doivent être descriptives pour satisfaire aux exigences d’accessibilité. Les liens peuvent être configurés de sorte qu’ils sont ouverts sur un nouvel onglet.|
| Icône          | Image | En plus d’une image de produit ou de catégorie, un symbole d’icône peut être ajouté. L’image du symbole de l’icône apparaîtra au-dessus de l’image du produit ou de la catégorie. |

## <a name="add-a-tile-list-module-to-a-new-page"></a>Ajouter un module de liste de vignettes à une nouvelle page

Pour ajouter un module de liste de vignettes à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Modèles** et ouvrez le modèle marketing pour la page d’accueil de votre site (ou créez un nouveau modèle marketing).
1. Dans l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Liste de vignettes**, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages** et ouvrez la page d’accueil du site (ou créez une nouvelle page d’accueil à l’aide du modèle marketing).
1. À l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis le sélectionnez **Ajoutez le module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Liste de vignettes**, puis sélectionnez **OK**.
1. Dans le volet de propriété du module de liste de vignettes, ajoutez un en-tête.
1. Dans l’emplacement **Liste de vignettes**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Module de vignettes**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module de vignettes, ajoutez une image, un en-tête et une image de symbole d’icône.
1. Ajoutez et configurez des modules de vignettes supplémentaires selon vos besoins.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Thème Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
