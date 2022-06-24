---
title: Module de visualisation rapide
description: Cet article couvre les modules de visualisation rapide et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e9066357fda4f5d91c547622ac64d8c4eef253ae
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847573"
---
# <a name="quick-view-module"></a>Module de visualisation rapide

[!include [banner](includes/banner.md)]

Cet article couvre les modules de visualisation rapide et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Le module de visualisation rapide permet aux utilisateurs d’afficher rapidement les informations sur les produits lorsqu’ils les parcourent sur une page de liste et d’ajouter un ou plusieurs produits au panier à partir de la page de liste, sans avoir à accéder à la page de détails du produit (PDP). Le module de visualisation rapide fournit un aperçu des informations sur le produit dont les utilisateurs ont besoin pour décider de l’ajouter au panier. Il fournit également un lien vers le PDP, afin que les utilisateurs puissent afficher des détails supplémentaires sur le produit et des options d’achat.

Le module de visualisation rapide est pris en charge par les modules [Collecte de produits](product-collection-module-overview.md) et [Résultats de recherche](search-result-module.md).

> [!IMPORTANT]
> Le module de visualisation rapide est disponible à partir de la version 10.0.17 de Commerce.

L’illustration suivante montre un exemple du module de visualisation rapide sur une page de liste de produits.

![Exemple de module de visualisation rapide sur une page de liste de produits.](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a>Propriétés du module

Le module de visualisation rapide prend en charge certaines des fonctions du module de zone d’achat. Par conséquent, les propriétés d’un module de visualisation rapide ressemblent à celles d’un module de zone d’achat.

| Propriété | Valeurs | Description |
|----------------|--------|-------------|
| Balise d’en-tête | **H1**, **H2**, **H3**, **H4**, **H5** ou **H6** | Cette propriété définit la balise d’en-tête du titre du produit. Si le module de visualisation rapide se trouve en haut de la page, cette propriété doit être définie sur **H1** pour répondre aux normes d’accessibilité. |
| Autoriser un prix personnalisé | **Vrai** ou **Faux** | Si cette propriété est définie sur **True**, l’utilisateur peut saisir un prix personnalisé. |
| Prix minimal | Entier | Cette propriété n’est applicable que si la propriété **Autoriser un prix personnalisé** est définie sur **True**. Elle définit le prix minimum que l’utilisateur peut saisir (par exemple, 1 $). |
| Prix maximal | Entier | Cette propriété n’est applicable que si la propriété **Autoriser un prix personnalisé** est définie sur **True**. Elle définit le prix maximal que l’utilisateur peut saisir (par exemple, 1 000 $). |

## <a name="commerce-site-builder-settings"></a>Paramètres du générateur de site Commerce

Tout comme le module de zone d’achat, le module de visualisation rapide respecte les paramètres de **Paramètres du site \> Extensions \> Ajouter un article au panier**. Cependant, le paramètre **Page Accéder au panier** est ignoré, car il est incompatible avec l’objectif du module de visualisation rapide, qui est de permettre aux utilisateurs de parcourir plusieurs produits sur une page de liste et de les ajouter au panier sans s’éloigner de la page de liste.

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a>Ajouter un module de visualisation rapide à un module de collecte de produits

Il est possible d’ajouter un module de visualisation rapide aux modules de collecte de produits et des résultats de recherche.

Pour ajouter un module de visualisation rapide à un module de collecte de produits dans le générateur de site Commerce, procédez comme suit.

1. Allez dans **Pages**, puis sélectionnez la page d’accueil du site Fabrikam.
1. Allez dans n’importe quel module **Collecte de produits** sur la page d’accueil, sélectionnez les points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module de **visualisation rapide**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module de **visualisation rapide**, sélectionnez **En-tête**. Dans la boîte de dialogue **En-tête**, définissez le champ **Niveau d’en-tête** sur **H2**, puis cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module de zone d’achat](add-buy-box.md)

[Module de collecte de produits](product-collection-module-overview.md)

[Module des résultats de recherche](search-result-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
