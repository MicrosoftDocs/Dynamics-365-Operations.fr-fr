---
title: Module de liste d’images
description: Cet article couvre les modules de liste d’images et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 8e47c9806c21de24f0e519d0132374d2e1ff2bbf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892798"
---
# <a name="image-list-module"></a>Module de liste d’images

[!include [banner](includes/banner.md)]

Cet article couvre les modules de liste d’images et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Le module de liste d’images peut être utilisé pour ajouter facilement une collection (un tableau) d’images aux pages du site. Chaque image du tableau peut être configurée avec du texte de paragraphe et des URL de lien. Le module de liste d’images est le mieux adapté pour afficher des logos de marque ou une liste qui comprend des logos.

> [!IMPORTANT]
> - Le module de liste d’images est disponible dans la bibliothèque du module Commerce dès la version Dynamics 365 Commerce 10.0.20.
> - Le module de liste d’images est présenté dans le thème Adventure Works.

L’illustration suivante montre un exemple dans lequel un module de liste d’images affiche une liste de texte qui inclut des logos sur une page de site entreprise-à-consommateur (B2C) Adventure Works.

![Exemple de module de liste d’images qui affiche une liste de texte incluant des logos](./media/Image_list.PNG)

L’illustration suivante montre un exemple dans lequel un module de liste d’images affiche des logos de marque sur une page de site entreprise-à-centreprise (B2B) Adventure Works.

![Exemple de module de liste d’images affichant les logos de la marque](./media/Image_list_B2B.PNG)

## <a name="image-list-module-properties"></a>Propriétés du module de liste d’images

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| Titre       | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Un en-tête de texte pour le module de liste d’images. |
| Liste d’images    | Images, texte et URL | Chaque élément du tableau est une image accompagnée d’un texte de paragraphe et d’une URL. |

## <a name="add-an-image-list-module-to-a-new-page"></a>Ajouter un module de liste d’images à une nouvelle page

Pour ajouter un module de liste d’images à une nouvelle page et définir les propriétés requises dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **Modèles** et ouvrez le modèle marketing pour la page d’accueil de votre site (ou créez un nouveau modèle marketing).
1. Dans l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Liste d’images**, puis cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages** et ouvrez la page d’accueil du site (ou créez une nouvelle page d’accueil à l’aide du modèle marketing).
1. À l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajoutez un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Liste d’images**, puis cliquez sur **OK**.
1. Dans le volet des propriétés du module de liste d’images, ajoutez un en-tête (par exemple, **Nos marques**).
1. Ajoutez un élément de liste d’images et spécifiez une image, du texte de paragraphe et une URL de redirection.
1. Ajoutez et configurez des modules de listes d’images supplémentaires selon vos besoins.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Thème Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
