---
title: Module Image active
description: Cet article couvre les modules Image active et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3d532d21f847a80a16af814eeaf097a616605795
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853848"
---
# <a name="active-image-module"></a>Module Image active

[!include [banner](includes/banner.md)]

Cet article couvre les modules Image active et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Un module Image active peut être utilisé pour incorporer des étiquettes de produits dans une image. Les utilisateurs du site d’e-commerce peuvent ensuite survoler les balises pour prévisualiser les produits affichés dans l’image. Les aperçus sont affichés dans des fenêtres contextuelles. En sélectionnant une fenêtre contextuelle d’aperçu, les utilisateurs peuvent accéder directement à la page de détails du produit (PDP) pour le produit correspondant.

Les balises sont définies en utilisant les coordonnées X et Y sur l’image. Chaque point avec balise doit être configuré avec l’ID de produit du produit affiché dans l’image.

L’illustration suivante montre un exemple de fenêtre contextuelle d’aperçu sur une image de bannière sur la page d’accueil d’Adventure Works.

![Exemple de fenêtre pop-up de prévisualisation dans un module Image active](./media/Active_image.PNG)

> [!IMPORTANT]
> - Le module Image active est disponible à partir de la version 10.0.20 de Dynamics 365 Commerce.
> - Le module Image active est présenté dans le thème Adventure Works.

## <a name="active-image-module-properties"></a>Propriétés du module Image active

| Nom de la propriété      | Valeurs | Description |
|--------------------|--------|-------------|
| Image              | Fichier image | Une image peut être utilisée pour présenter un ou plusieurs produits. L’image peut être chargée dans le générateur de site de la bibliothèque multimédia dans Commerce, ou une image existante peut être utilisée. |
| Largeur              | Nombre de pixels | Cette propriété définit la largeur de l’image. Les coordonnées actives sont calculées en fonction de la largeur de l’image.|
| Coordonnées actives | Coordonnées X et Y, et un numéro d’identification du produit | Chaque tableau d’images actif se compose de coordonnées X et Y et d’un numéro d’identification de produit.|
| Titre            | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Par défaut, la balise d’en-tête **H2** est utilisée pour le titre, mais la balise peut être modifiée pour répondre aux besoins en accessibilité. |
| Paragraphe          | Texte du paragraphe | Les modules prennent en charge le texte de paragraphe dans en format de texte enrichi. Certains capacités de texte enrichi de base sont prises en charge, telles que les liens hypertexte, le gras, le souligné, et l’italique. Certaines de ces fonctionnalités peuvent être remplacées par le thème de la page qui s’applique au module. |
| Lien               | Texte du lien, URL du lien, étiquette ARIA (Applications Internet enrichie accessibles), et sélecteur **Ouvrir le lien dans le nouvel onglet** | Le module prend en charge un ou plusieurs liens d’« appels à l’action ». Si un lien est ajouté, un texte de lien, une URL, et une étiquette ARIA sont requis. Les étiquettes ARIA doivent être descriptives pour satisfaire aux exigences d’accessibilité. Les liens peuvent être configurés de sorte qu’ils sont ouverts sur un nouvel onglet. |
| Sous-texte           | Titre, texte et liens | Un contexte supplémentaire pour l’image peut être ajouté, tel qu’un nom d’auteur ou de concepteur, ou des liens vers des blogs personnels.|
| Thème du texte         | **Clair** ou **Foncé** | Cette propriété permet à un utilisateur de définir le texte sur clair ou foncé, en fonction de l’image d’arrière-plan. Il est disponible en tant qu’extension de thème dans le thème Adventure Works. |

## <a name="add-an-active-image-module-to-a-new-page"></a>Ajouter un module Image active à une nouvelle page

Pour ajouter un module Image active à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Modèles** et ouvrez le modèle marketing pour la page d’accueil de votre site (ou créez un nouveau modèle marketing).
1. Dans l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Image active**, puis cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages** et ouvrez la page d’accueil du site (ou créez une nouvelle page d’accueil à l’aide du modèle marketing).
1. À l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajoutez un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Image active**, puis cliquez sur **OK**.
1. Dans le volet des propriétés du module Image active, ajoutez une image et définissez la largeur du canevas sur la taille de l’image.
1. Définissez les coordonnées X et Y et ajoutez le numéro d’identification du produit approprié.
1. Ajoutez et configurez des modules Image active supplémentaires selon vos besoins.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Thème Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
