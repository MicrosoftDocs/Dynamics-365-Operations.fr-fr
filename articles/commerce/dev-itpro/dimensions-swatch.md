---
title: Configurer les valeurs des dimensions du produit pour qu’elles apparaissent en tant qu’échantillons
description: Cette rubrique décrit comment configurer les valeurs des dimensions du produit comme échantillons dans Microsoft Dynamics 365 Commerce Headquarters.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.20 update
ms.openlocfilehash: 513ec2f48a3c7c81a41fd64a9752067d12eb4ec8
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353860"
---
# <a name="configure-product-dimension-values-to-appear-as-swatches"></a>Configurer les valeurs des dimensions du produit pour qu’elles apparaissent en tant qu’échantillons

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Cette rubrique décrit comment configurer les valeurs des dimensions du produit comme échantillons dans Microsoft Dynamics 365 Commerce Headquarters. Pour plus d’informations sur les dimensions du produit, consultez [Dimensions du produit](../../supply-chain/pim/product-dimensions.md).

Dynamics 365 Commerce prend en charge l’utilisation de dimensions de taille, de style et de couleur pour représenter les variantes du produit. Les dimensions du produit ont des noms conviviaux qui sont affichés sur les pages de détails du produit (PDP) pour permettre la sélection des variantes du produit. Parmi les exemples de noms conviviaux, on peut citer « Petit », « Moyen » et « Grand » pour les tailles et « Noir » et « Marron » pour les couleurs. Cependant, si un produit prend en charge de nombreuses variations, plusieurs sélections sont nécessaires pour afficher l’image de chaque variante du produit. Par conséquent, il peut être lent et fastidieux pour les clients de parcourir et de sélectionner les variantes du produit.

Lorsque les dimensions sont affichées comme échantillons sur les pages de détails du produit, les clients obtiennent un aperçu visuel des variations d’un produit. Ils peuvent facilement parcourir un large éventail de couleurs, motifs et textures et ils peuvent visualiser rapidement différentes combinaisons de variations du produit.

La fonction d’affichage des dimensions comme échantillons permet à Commerce d’utiliser des images et des codes hexadécimaux (hex) pour afficher les dimensions comme échantillons. En outre, les dimensions similaires, telles que les couleurs, peuvent être regroupées dans les pages de la liste de produits. Par exemple, un client recherche des produits bleus. Si les différentes valeurs de dimension bleu sont regroupées ensemble, la page de la liste de résultats de recherche affiche les produits qui ont différentes nuances de bleu. Le regroupement des dimensions améliore considérablement l’expérience d’affinement des produits et aide les clients à trouver plus de produits par le biais d’une seule requête de recherche de produits.

> [!NOTE]
> La fonction d’affichage des dimensions comme échantillons est disponible à partir du lancement de la version 10.0.20 de Dynamics 365 Commerce.

L’illustration suivante montre un exemple où les couleurs apparaissent comme échantillons sur la page des détails d’un produit de Commerce.

![Exemple de couleurs affichées comme échantillons sur la page des détails d’un produit.](../dev-itpro/media/swatch_pdp.png)

L’illustration suivante montre un exemple où les couleurs apparaissent comme échantillons dans une page de liste de résultats de recherche de Commerce.

![Exemple de couleurs affichées comme échantillons dans une page de liste de résultats de recherche.](../dev-itpro/media/swatch_searchresults.PNG)

## <a name="enable-the-display-dimensions-as-swatches-feature-in-commerce-headquarters"></a>Activer la fonction d’affichage des dimensions comme échantillon dans Commerce Headquarters

Pour activer la fonction d’affichage des dimensions comme échantillons dans Commerce Headquarters, accédez à **Espaces de travail \> Gestion des fonctionnalités** et activez la fonctionnalité **Activer la prise en charge des images pour les valeurs de dimension du produit**. Lorsque cet indicateur de fonction est activé, trois nouveaux champs sont ajoutés pour chaque dimension dans les tables appropriées dans Commerce Headquarters : **Code hexadécimal**, **URL** (pour les images) et **RefinerGroup**.

## <a name="configure-dimension-values-in-commerce-headquarters"></a>Configurer les valeurs de dimension dans Commerce Headquarters

La fonction d’affichage des dimensions comme échantillons est prise en charge pour les dimensions de taille, de style et de couleur. Les valeurs de code hexadécimal et d’URL d’image pour les dimensions appropriées peuvent être spécifiées dans Commerce Headquarters. Par défaut, si les valeurs de code hexadécimal et d’URL d’image ne sont pas fournies pour une dimension, le système affichera le texte du nom convivial de la dimension.

La configuration peut être effectuée dans l’un des niveaux suivants :

- **Dimension** : dans Commerce Headquarters, ouvrez la page d’une dimension en recherchant **Couleur**, **Taille** ou **Style**. Dans chaque page, une grille répertorie les valeurs de dimension. Vous pouvez gérer les valeurs d’ordre d’affichage, de code hexadécimal et d’URL d’image. L’illustration suivante montre un exemple de configuration dans la page **Couleurs**.

    ![Exemple de configuration de dimensions dans la page Couleurs.](../dev-itpro/media/swatch_Color.PNG)

- **Groupe de dimensions** : dans Dynamics 365 Commerce, vous pouvez utiliser la propriété **RefinerGroup** pour créer des groupes de dimensions. Si les groupes de dimensions sont définis, ouvrez la page appropriée en recherchant **Groupe de couleurs**, **Groupe de tailles** ou **Groupe de styles**. Sur chaque page, vous pouvez gérer les valeurs de code hexadécimal, d’URL d’image et de groupe d’affinement. L’illustration suivante montre un exemple de configuration dans la page **Groupes de couleurs**.

    ![Exemple de configuration de dimensions dans la page Groupes de couleurs.](../dev-itpro/media/swatch_colorGroup.PNG)

- **Dimension du produit (lors de la création du produit)**  : lorsque vous créez un nouveau produit, vous pouvez utiliser la page **Dimensions du produit** pour saisir les valeurs de dimension. Pour les produits existants, les champs **Code hexadécimal**, **URL** (pour les images) et **RefinerGroup** sont peut-être déjà définis. Vous pouvez néanmoins modifier les valeurs au besoin. L’illustration suivante montre un exemple de configuration dans la page **Dimensions du produit**.

    ![Exemple de configuration de dimensions dans la page Dimensions du produit.](../dev-itpro/media/swatch_product_dimensions.PNG)

> [!NOTE]
> Le processus de gestion des configurations de code hexadécimal et d’URL d’image suit le même modèle que celui utilisé pour gérer l’ordre d’affichage des dimensions.

## <a name="configure-dimension-values-by-using-hex-codes"></a>Configurer les valeurs de dimension à l’aide de codes hexadécimaux

Pour la plupart des dimensions de couleur, une valeur de couleur de code hexadécimal doit être fournie dans les pages de dimension de Commerce Headquarters. Par exemple, la couleur noire doit avoir une valeur de code hexadécimal de **#00000**. Lorsque Commerce affiche une page de site, le code hexadécimal est représenté par un échantillon de couleur.

L’illustration suivante montre un exemple dans lequel les dimensions de couleur sont configurées à l’aide de valeurs de code hexadécimal.

![Exemple de configuration de dimensions qui utilise des codes hexadécimaux.](../dev-itpro/media/swatch_color_hexcode.png)

## <a name="configure-dimension-values-by-using-image-urls"></a>Configurer les valeurs de dimension à l’aide d’URL d’image

Certaines dimensions de couleur représentent des motifs, et non des couleurs unies. Par exemple, une dimension de couleur peut être décrite comme « léopard ». Dans ces cas, vous pouvez représenter plus efficacement les dimensions de couleur en utilisant des images publiées au lieu de codes hexadécimaux pour les échantillons.

Vous devez charger chaque image dans le générateur de sites de Commerce et la publier. Saisissez ensuite l’URL de l’image publiée dans les pages de dimensions appropriées dans Commerce Headquarters. Si une dimension a été sélectionnée pour s’afficher comme échantillon, mais qu’aucun code hexadécimal n’est défini, Commerce effectuera une recherche d’images lors de l’affichage de la page. Si la recherche d’images échoue, Commerce affichera le texte du nom convivial de la dimension.

L’illustration suivante montre un exemple dans lequel les URL d’image sont utilisées pour la configuration de la page **Couleurs**.

![Exemple de configuration de dimensions qui utilise les URL d’image.](../dev-itpro/media/swatch_color_urls.PNG)

Vous pouvez utiliser un modèle multimédia pour définir les URL d’image, tout comme vous le pouvez pour les images de produit et de catégorie. Lorsque vous chargez des images dans le générateur de sites, les conventions de nom de fichier et les chemins d’accès de fichier doivent être cohérents.

L’illustration suivante montre un exemple dans lequel les URL d’image sont utilisées pour la configuration d’un modèle multimédia.

![Exemple de configuration d’un modèle multimédia.](../dev-itpro/media/swatch_media_template.PNG)

## <a name="configure-dimension-values-by-using-both-hex-codes-and-image-urls"></a>Configurer les valeurs de dimension en utilisant à la fois des codes hexadécimaux et des URL d’image

Pour la plupart des dimensions de couleur, vous pouvez configurer à la fois des codes hexadécimaux et des URL d’image. La logique de secours d’affichage de Commerce recherchera automatiquement un code hexadécimal ou une URL d’image pour afficher un échantillon de couleur. En utilisant à la fois des codes hexadécimaux et des URL d’image pour configurer les dimensions de couleur, vous aidez à simplifier la gestion des images lorsque le nombre de couleurs est important.

L’illustration suivante montre un exemple dans lequel les codes hexadécimaux et les URL d’image sont utilisés pour la configuration de la page **Couleurs**.

![Exemple de configuration de dimensions qui utilise à la fois des codes hexadécimaux et des URL d’image.](../dev-itpro/media/swatch_color_hexandimage.png)

## <a name="configure-refiner-groups"></a>Configurer les groupes d’affinement

Lorsque vous définissez un code hexadécimal ou une URL d’image pour une valeur de dimension, vous pouvez également spécifier une valeur pour le champ **RefinerGroup**. Ce champ définit la dimension à utiliser pour regrouper des valeurs de dimension similaires dans l’expérience d’affinement.

Par exemple, si vos valeurs de dimension de couleur sont « bleu », « plaid bleu », « bleu délavé » et « bleu foncé », chaque valeur est associée à un code hexadécimal différent ou à une URL d’image différente. Par conséquent, chaque valeur apparaîtra sous une couleur différente dans les pages de détails du produit et les fiches produit pour les produits appropriés. Cependant, si vous associez toutes ces valeurs de dimension de couleur à une valeur **RefinerGroup** de **Bleu**, une recherche de produits « bleus » générera des résultats de recherche dans la page de liste pour les produits dont les valeurs de couleur de dimension sont « bleu », « plaid bleu », « bleu délavé » et « bleu foncé ».

L’exemple de l’illustration suivante montre la relation entre les propriétés **Couleur** et **RefinerGroup** dans Commerce Headquarters.

![Exemple de gestion des groupes d’affinement.](../dev-itpro/media/swatch_refiner_group.png)

## <a name="manage-images-in-commerce-site-builder"></a>Gérer les images dans le générateur de sites de Commerce

Si les URL d’image sont utilisées pour des valeurs de dimension, les images correspondantes doivent être chargées dans le générateur de sites de Commerce. L’emplacement de chaque image doit correspondre au nom de fichier et au chemin d’accès du dossier définis pour l’image dans Commerce Headquarters. Les fichiers image doivent être chargés dans les emplacements de catégorie appropriés du générateur de sites. Par exemple, les images de couleur doivent être chargées dans le dossier de catégorie **Couleur**. Pour plus d’informations sur le chargement d’images dans le générateur de sites, consultez [Charger des images](../dam-upload-images.md).

L'illustration suivante montre un exemple dans lequel la boîte de dialogue **Charger les fichiers** est utilisée pour charger des images dans la bibliothèque multimédia du générateur de sites. Elle met en surbrillance les catégories **Taille**, **Couleur** et **Style** disponibles pour sélection.

![Exemple de catégories de fichier image lors du chargement dans la bibiothèque multimédia du générateur de sites.](../dev-itpro/media/swatch_sitebuilder.png)

## <a name="enable-swatch-display-on-e-commerce-site-pages"></a>Activer l’affichage d’échantillons dans les pages du site d’e-commerce

Avant que les échantillons puissent apparaître dans les pages du site d’e-commerce qui nécessitent la sélection de dimensions, comme les pages de détails du produit et les pages de liste, vous devez configurer les paramètres du site de dimensions dans Commerce Headquarters. Pour plus d’informations, consultez [Appliquer les paramètres du site pour les dimensions](../dimension-settings.md).

De plus, vous devez activer la propriété **Inclure les attributs du produit dans les résultats de la recherche** pour les modules de résultats de la recherche. Si votre site utilise des pages de catégorie personnalisées, vous devez mettre à jour les modules de résultats de la recherche qui sont utilisés dans ces pages, afin que la propriété **Inclure les attributs du produit dans les résultats de la recherche** soit activée. Pour plus d’informations, consultez [Module de résultats de la recherche](../search-result-module.md).

## <a name="display-swatches-in-pos-and-other-channels"></a>Afficher les échantillons dans le PDV et d’autres canaux

Actuellement, Commerce n’a pas d’implémentation prédéfinie qui prend en charge l’affichage des échantillons dans le point de vente (PDV) et d’autres canaux. Cependant, vous pouvez implémenter la fonctionnalité d’affichage d’échantillons comme une extension qui oblige les API de canal à renvoyer les codes hexadécimaux et les URL d’image nécessaires à l’affichage des échantillons.

## <a name="additional-resources"></a>Ressources supplémentaires

[Module de résultats de recherche](../search-result-module.md)

[Appliquer les paramètres du site pour les dimensions](../dimension-settings.md)

[Dimensions de produit](../../supply-chain/pim/product-dimensions.md)

[Télécharger l'image](../dam-upload-images.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
