---
title: Module de galerie multimédia
description: Cet article couvre les modules galerie multimédia et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 5e2d0a4422341badee906c71bebdd491e18a38cc
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273456"
---
# <a name="media-gallery-module"></a>Module de galerie multimédia

[!include [banner](includes/banner.md)]

Cet article couvre les modules galerie multimédia et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Les modules galerie multimédia affichent une ou plusieurs images dans une vue de galerie. Les modules galerie multimédia prennent en charge les images miniatures, qui peuvent être organisées horizontalement (alignées sous l’image) ou verticalement (en colonne à côté de l’image). Les modules galerie multimédia fournissent également des fonctionnalités qui permettent d’effectuer un zoom sur les images (agrandir) ou de les afficher en mode plein écran. Pour être affichée dans un module galerie multimédia, une image doit être disponible dans la bibliothèque multimédia du générateur de site Commerce. Actuellement, les modules galerie multimédia ne prennent en charge que les images.

Dans le mode par défaut, un module galerie multimédia utilise l’ID produit disponible dans le contexte de page d’une page de détails de produit (PDP) pour afficher les images correspondantes du produit. Dans Commerce Headquarters, un chemin d’accès au fichier multimédia doit être défini pour tous les produits. Les images doivent ensuite être chargées dans la bibliothèque multimédia du générateur de site, en fonction du chemin d’accès au fichier défini pour les produits dans Commerce Headquarters. Ces images comprennent les images des produits et des variantes de produit. Pour plus d’informations sur le chargement des images dans la bibliothèque multimédia du générateur de site, voir [Charger des images](dam-upload-images.md).

Sinon, un module galerie multimédia peut héberger un ensemble d’images entièrement organisé sur une page de la galerie d’images, où il n’existe aucune dépendance sur l’ID produit ou le contexte de la page. Dans ce cas, les images doivent être chargées dans la bibliothèque multimédia du générateur de site et spécifiées dans le générateur de site.

Voici quelques exemples d’utilisation des modules galerie multimédia :

- Affichage des images de produit sur une page de détails de produit
- Affichage des images de produit sur une page marketing de produit
- Affichage d’un ensemble d’images organisé sur une page marketing, telle qu’une page de galerie

Dans l’exemple de l’illustration suivante, une zone d’achat sur une page de détails de produit héberge des images de produit en utilisant un module galerie multimédia.

![Exemple d’une zone d’achat sur une page de détails de produit qui héberge des images de produit en utilisant un module galerie multimédia.](./media/ecommerce-pdp-buybox.PNG)

## <a name="media-gallery-properties"></a>Propriétés de la galerie multimédia

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| Source de l’image | **Contexte de la page** ou **ID produit** | La valeur par défaut est **Contexte de la page**. Si **Contexte de la page** est sélectionné, le module s’attend à ce que la page fournisse les informations sur l’ID produit. Si **ID produit** est sélectionné, l’ID produit d’une image doit être fourni comme valeur de la propriété **ID produit**. Cette fonctionnalité est disponible dans la version 10.0.12 de Commerce. |
| ID produit | Un ID produit | Cette propriété n’est applicable que si la valeur de la propriété **Source de l’image** est **ID produit**. |
| Zoom sur l’image | **En ligne** ou **Conteneur** | Cette propriété permet à l’utilisateur d’effectuer un zoom sur les images dans le module galerie multimédia. Une image peut faire l’objet d’un zoom en ligne ou dans un conteneur distinct à côté de l’image. Cette fonctionnalité est disponible dans la version 10.0.12. |
| Facteur de zoom | Un nombre décimal | Cette propriété spécifie le facteur d’échelle du zoom sur les images. Par exemple, si la valeur est définie sur **2,5**, les images sont agrandies 2,5 fois. |
| Plein écran | **Vrai** ou **Faux** | Cette propriété spécifie si les images peuvent être affichées en mode plein écran. En mode plein écran, les images peuvent également être agrandies davantage si la fonctionnalité de zoom est activée. Cette fonctionnalité est disponible dans la version 10.0.13 de Commerce. |
| Qualité d’image agrandie | Un nombre compris entre 1 et 100 qui représente un pourcentage et qui est sélectionné à l’aide d’un contrôle de la barre de suivi | Cette propriété définit la qualité d’image pour les images zoomées. Elle peut être définie sur 100 % pour garantir qu’une image zoomée utilise toujours la résolution la plus élevée possible. Cette propriété ne s’applique pas aux fichiers PNG, car ils utilisent un format sans perte. Cette fonctionnalité est disponible à compter de la version 10.0.19 de Commerce. |
| Images | Images sélectionnées dans la bibliothèque multimédia du générateur de site | En plus de leur affichage à partir d’un produit, les images peuvent être organisées pour un module galerie multimédia. Ces images seront ajoutées à toutes les images de produit disponibles. Cette fonctionnalité est disponible dans la version 10.0.12 de Commerce. |
| Orientation miniature | **Vertical** ou **Horizontal** | Cette propriété spécifie si les images miniatures doivent être affichées dans une bande verticale ou une bande horizontale. |
| Masquer les images principales du produit pour la variante | **Vrai** ou **Faux** | Si cette propriété est définie sur **Vrai**, lorsqu’une variante est sélectionnée, les images du produit principal sont masquées à moins que la variante ne comporte aucune image. Cette propriété n’affecte pas les produits sans variantes. |
| Mettre à jour le média lors de la sélection des dimensions | **Vrai** ou **Faux** | Si cette propriété est définie sur **Vrai**, les images de la bibliothèque multimédia seront mises à jour lorsqu’une dimension (telle que la couleur, le style ou la taille) est sélectionnée et qu’une image est disponible. Cette propriété permet de simplifier l’expérience de navigation, car toutes les dimensions de variante de produit ne doivent pas être sélectionnées pour que l’image correspondante soit mise à jour. Cette propriété est disponible dans l’onglet **Avancé**. |

> [!IMPORTANT]
> La propriété **Mettre à jour le média lors de la sélection des dimensions** est disponible à partir de la version 10.0.21 de Commerce. Elle nécessite l’installation du package de bibliothèque du module Commerce version 9.31.

L’illustration suivante montre un exemple de module galerie multimédia où les options Plein écran et Zoom sont disponibles.

![Exemple de module galerie multimédia où les options Plein écran et Zoom sont disponibles.](./media/ecommerce-media-zoom.png)

L’illustration suivante montre un exemple de module galerie multimédia contenant des images organisées (c’est-à-dire que les images spécifiées ne dépendent pas de l’ID produit ou du contexte de la page).

![Exemple de module galerie multimédia contenant des images organisées.](./media/ecommerce-media-curated.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interaction avec Commerce Scale Unit

Lorsque la source de l’image est dérivée du contexte de la page, l’ID produit de la page de détails de produit est utilisé pour récupérer les images. Le module galerie multimédia extrait le chemin d’accès du fichier image des produits à l’aide des interfaces de programmation d'applications (API) de Commerce Scale Unit. Les images sont ensuite extraites de la bibliothèque multimédia afin de pouvoir les afficher dans le module.

## <a name="add-a-media-gallery-module-to-a-page"></a>Ajouter un module galerie multimédia à une page

Pour ajouter un module galerie multimédia à une page marketing, suivez ces étapes :

1. Accédez à **Modèles**, puis sélectionnez **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle marketing**, puis sélectionnez **OK**.
1. Dans l’emplacement **Corps**, sélectionnez les points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Page par défaut**, puis **OK**.
1. Dans l’emplacement **Principal** de la page par défaut, sélectionnez les points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une nouvelle page.
1. Dans la boîte de dialogue **Créer une nouvelle page**, sous **Nom de la page**, entrez **Page galerie multimédia**, puis sélectionnez **Suivant**.
1. Sous **Choisir un modèle**, sélectionnez le **Modèle marketing** que vous avez créé, puis sélectionnez **Suivant**.
1. Sous **Choisir une disposition**, sélectionnez une disposition de page (par exemple, **Disposition flexible**), puis sélectionnez **Suivant**.
1. Sous **Revoir et terminer**, vérifiez la configuration de la page. Si vous devez modifier les informations de la page, sélectionnez **Précédent**. Si les informations de la page sont correctes, sélectionnez **Créer une page**. 
1. Dans l’emplacement **Principal** de la nouvelle page, sélectionnez les points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans l’emplacement **Conteneur**, sélectionnez les points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Galerie média**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module galerie multimédia, sous **Source de l’image**, sélectionnez **Productid**. Puis, dans le champ **ID produit**, entrez un ID produit.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page. Vous devriez pouvoir voir les images du produit dans une vue de galerie.
1. Pour utiliser uniquement des images organisées, dans le volet des propriétés, sous **Source de l’image**, sélectionnez **Productid**. Puis, sous **Images**, sélectionnez **Ajouter une image** autant de fois que nécessaire pour ajouter des images à partir de la bibliothèque multimédia.
1. Définissez les propriétés supplémentaires que vous souhaitez définir, telles que **Zoom sur l’image**, **Facteur de zoom** et **Orientation des miniatures**.
1. Lorsque vous avez terminé, sélectionnez **Enregistrer**, sélectionnez **Terminer la modification** pour archiver la page, puis sélectionnez **Publier** pour la publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Zone d’achat](add-buy-box.md)

[Module Conteneur](add-container-module.md)

[Chargement des images](dam-upload-images.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
