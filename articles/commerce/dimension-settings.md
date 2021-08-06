---
title: Appliquer les paramètres d’affichage pour les dimensions du produit
description: Cette rubrique couvre les paramètres d’affichage des dimensions du produit et explique comment les appliquer dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
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
ms.openlocfilehash: 43f402c62cd7c9aab184152820e4fac9499c6f20
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638167"
---
# <a name="apply-display-settings-for-product-dimensions"></a>Appliquer les paramètres d’affichage pour les dimensions du produit

[!include [banner](includes/banner.md)]


Cette rubrique couvre les paramètres d’affichage des dimensions du produit et explique comment les appliquer dans Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce prend en charge les dimensions de taille, de style et de couleur pour distinguer les variantes du produit. Les dimensions sont généralement affichées comme valeurs de texte, telles que « Petit », « Moyen » et « Grand » pour les tailles et « Noir » et « Marron » pour les couleurs. Cependant, si un produit prend en charge de nombreuses variantes, il peut être difficile de parcourir les variantes du produit, car plusieurs sélections sont nécessaires pour afficher l’image de chaque variante. Pour faciliter la recherche de variantes de produit, la version 10.0.20 de Commerce peut utiliser des images et des codes hexadécimaux (hex) pour afficher les dimensions comme échantillons.

Dans le générateur de sites de Commerce, les paramètres de dimension sont définis dans **Paramètres du site \> Extensions \> Paramètres de dimension**. L’illustration suivante montre un exemple de paramètres de dimension dans le générateur de sites.

![Exemple de paramètres de site dans le générateur de sites de Commerce.](./dev-itpro/media/swatch_site_settings.PNG)

Deux paramètres de dimension sont disponibles :

- **Dimensions à afficher comme image** : spécifiez les dimensions qui doivent apparaître comme échantillons dans les pages du site d’e-commerce, telles que les pages de détails du produit (PDP) et les pages de la liste de résultats de recherche. Toute combinaison de dimensions de couleur, de taille et de style peut être affichée comme échantillon. Si une dimension est sélectionnée pour être affichée comme échantillon, le rendu du module Commerce recherchera une configuration disponible d’un échantillon de code hexadécimal. Si aucun code hexadécimal n’est configuré, la logique système recherchera une configuration d’un échantillon d’URL d’image. Si ni un code hexadécimal ni une URL d’image ne sont configurés, le texte sera affiché.

    L’illustration suivante montre un exemple dans lequel la page des détails d’un produit sur un site d’e-commerce comprend des échantillons de couleur et de taille. Dans cet exemple, un code hexadécimal est configuré pour la dimension de couleur. Par conséquent, les échantillons sont affichés comme couleurs. Cependant, ni un code hexadécimal ni une URL d’image ne sont configurés pour la dimension de taille. Par conséquent, le texte est affiché.

    ![Exemple de la dimension de couleur affichée comme échantillons dans la page des détails d’un produit d’e-commerce.](./dev-itpro/media/swatch_pdp.png)

- **Dimensions à afficher dans la fiche produit** : spécifiez les dimensions qui doivent apparaître sur les fiches produit affichées dans les listes et dans les pages de liste. Pour qu’une dimension puisse apparaître sur une fiche produit, ce paramètre doit être activé pour cette dimension. Le paramètre **Dimensions à afficher comme image** doit également être activé. Le comportement de sélection d’échantillons dans les fiches produit est optimisé pour la dimension de couleur. Pour les autres dimensions, une extension de vue peut être nécessaire pour personnaliser le comportement de sélection d’échantillons.

    L’illustration suivante montre un exemple dans lequel une page de liste sur un site d’e-commerce contient des fiches produit incluant des échantillons de couleur.

    ![Exemple de la dimension de couleur affichée comme échantillons dans une page de liste d’e-commerce.](./dev-itpro/media/swatch_searchresults.PNG)

Pour plus d’informations sur la configuration des dimensions du produit afin qu’elles s’affichent comme échantillons dans les pages du site, consultez [Configurer les valeurs des dimensions du produit pour qu’elles apparaissent en tant qu’échantillons](./dev-itpro/dimensions-swatch.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module de résultats de recherche](search-result-module.md)

[Module de zone d’achat](add-buy-box.md)

[Configurer les valeurs des dimensions du produit pour qu’elles apparaissent en tant qu’échantillons](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
