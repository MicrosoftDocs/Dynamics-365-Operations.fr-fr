---
title: Module Galerie multimédia
description: Cette rubrique couvre les modules Galerie multimédia et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 9df2b91b0a57c73e395242f840c423fa8c7f2c9f
ms.sourcegitcommit: 629988f1a704d62648d98649056931b8c33b9e08
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2020
ms.locfileid: "3811156"
---
# <a name="media-gallery-module"></a>Module Galerie multimédia

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules Galerie multimédia et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Les modules Galerie multimédia affichent une ou plusieurs images dans une vue de galerie. Ils prennent en charge les images miniatures, qui peuvent être organisées horizontalement (alignées sous l’image) ou verticalement (sous forme de colonne en regard de l’image). Ils fournissent également des fonctionnalités qui permettent d’effectuer un zoom sur les images (agrandir) ou de les afficher en mode plein écran. Pour être affichée dans un module Galerie multimédia, une image doit être disponible dans la bibliothèque multimédia du générateur de site Commerce. Pour le moment, les modules Galerie multimédia ne prennent en charge que les images.

Dans le mode par défaut, un module Galerie multimédia utilise l’ID produit disponible dans le contexte de page d’une page de détails de produit pour afficher les images correspondantes du produit. Dans Commerce Headquarters, un chemin d’accès au fichier multimédia doit être défini pour tous les produits. Les images doivent ensuite être chargées dans la bibliothèque multimédia du générateur de site, en fonction du chemin d’accès au fichier défini pour les produits dans Commerce Headquarters. Ces images comprennent les images des produits et des variantes de produit. Pour plus d’informations sur le chargement des images dans la bibliothèque multimédia du générateur de site, voir [Charger des images](dam-upload-images.md).

Sinon, un module Galerie multimédia peut héberger un ensemble d’images entièrement organisé sur une page de la galerie d’images, où il n’existe aucune dépendance sur l’ID produit ou le contexte de la page. Dans ce cas, les images doivent être chargées dans la bibliothèque multimédia du générateur de site et spécifiées dans le générateur de site.

Voici quelques exemples d’utilisation des modules Galerie multimédia :

- Affichage des images de produit sur une page de détails de produit
- Affichage des images de produit sur une page marketing de produit
- Affichage d’un ensemble d’images organisé sur une page marketing, telle qu’une page de galerie

Dans l’exemple de l’illustration suivante, une zone d’achat sur une page de détails de produit héberge des images de produit en utilisant un module Galerie multimédia.

![Exemple d’une zone d’achat sur une page de détails de produit qui héberge des images de produit en utilisant un module Galerie multimédia](./media/ecommerce-pdp-buybox.PNG)

## <a name="media-gallery-properties"></a>Propriétés de la galerie multimédia

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| Source de l’image | **Contexte de la page** ou **ID produit** | La valeur par défaut est **Contexte de la page**. Si l’option **Contexte de la page** est sélectionnée, le module s’attend à ce que la page fournisse les informations sur l’ID produit. Si l’option **ID produit** est sélectionnée, l’ID produit d’une image doit être fourni comme valeur de la propriété **ID produit**. Cette fonctionnalité est disponible dans la version 10.0.12 de Commerce. |
| ID produit | ID produit | Cette propriété n’est applicable que si la valeur de la propriété **Source de l’image** est **ID produit**. |
| Zoom sur l’image | **En ligne** ou **Conteneur** | Cette propriété permet à l’utilisateur d’effectuer un zoom sur les images dans le module Galerie multimédia. Une image peut faire l’objet d’un zoom en ligne ou dans un conteneur distinct en regard de l’image. Cette fonctionnalité est disponible dans la version 10.0.12 |
| Échelle de zoom | Nombre décimal | Cette propriété spécifie le facteur d’échelle du zoom sur les images. Par exemple, si la valeur est définie sur **2,5**, les images sont agrandies 2,5 fois.|
| Plein écran | **Vrai** ou **Faux** | Cette propriété spécifie si les images peuvent être affichées en mode plein écran. En mode plein écran, les images peuvent également être agrandies davantage si la fonctionnalité de zoom est activée. Cette fonctionnalité est disponible dans la version 10.0.13 de Commerce. |
| Images | Images sélectionnées dans la bibliothèque multimédia du générateur de site | En plus de leur affichage à partir d’un produit, les images peuvent être organisées pour un module Galerie multimédia. Ces images sont ajoutées à toutes les images de produit disponibles. Cette fonctionnalité est disponible dans la version 10.0.12 de Commerce. |
| Orientation des miniatures | **Vertical** ou **Horizontal** | Cette propriété spécifie si les images miniatures doivent être affichées dans une bande verticale ou une bande horizontale. |

L’illustration suivante montre un exemple de module Galerie multimédia où les options Plein écran et Zoom sont disponibles.

![Exemple de module Galerie multimédia où les options Plein écran et Zoom sont disponibles](./media/ecommerce-media-zoom.png)

L’illustration suivante montre un exemple de module Galerie multimédia contenant des images organisées (c’est-à-dire que les images spécifiées ne dépendent pas de l’ID produit ou du contexte de la page).

![Exemple de module Galerie multimédia contenant des images organisées](./media/ecommerce-media-curated.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interaction avec Commerce Scale Unit

Lorsque la source de l’image est dérivée du contexte de la page, l’ID produit de la page de détails de produit est utilisé pour récupérer les images. Le module Galerie multimédia extrait le chemin d’accès du fichier image des produits à l’aide des API (Application Programming Interfaces) de Commerce Scale Unit. Les images sont ensuite extraites de la bibliothèque multimédia afin de pouvoir les afficher dans le module.

## <a name="add-a-media-gallery-module-to-a-page"></a>Ajouter un module Galerie multimédia à une page

Pour ajouter un module Galerie multimédia à une page marketing, procédez comme suit.

1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle marketing**, puis cliquez sur **OK**.
1. Dans l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Page par défaut**, puis sélectionnez **OK**.
1. Dans l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle **Modèle marketing**. Sous **Nom de la page**, entrez **Page de la galerie multimédia**, puis cliquez sur **OK**.
1. Dans l’emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Galerie de supports**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module Galerie multimédia, sous **Source de l’image**, sélectionnez **Productid**. Puis, dans le champ **ID produit**, entrez un ID produit.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page. Vous devriez pouvoir voir les images du produit dans une vue de galerie.
1. Pour utiliser uniquement des images organisées, dans le volet des propriétés, sous **Source de l’image**, sélectionnez **Productid**. Puis, sous **Images**, sélectionnez **Ajouter une image** autant de fois que nécessaire pour ajouter des images à partir de la bibliothèque multimédia.
1. Définissez les propriétés supplémentaires que vous souhaitez définir, telles que **Zoom sur l’image**, **Facteur de zoom** et **Orientation des miniatures**.
1. Lorsque vous avez terminé, sélectionnez **Enregistrer**, sélectionnez **Terminer la modification** pour archiver la page, puis sélectionnez **Publier** pour la publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble du kit de démarrage](starter-kit-overview.md)

[Module de zone d’achat](add-buy-box.md)

[Module Conteneur](add-container-module.md)

[Importer des images](dam-upload-images.md)
