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
ms.openlocfilehash: a4a16391f7eb8b75ea77fe524593c089e24b0cb7
ms.sourcegitcommit: 074fe7e77feb795148c3daf2e6ccbb8a88679343
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2020
ms.locfileid: "3645882"
---
# <a name="media-gallery-module"></a><span data-ttu-id="8eba9-103">Module Galerie multimédia</span><span class="sxs-lookup"><span data-stu-id="8eba9-103">Media gallery module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="8eba9-104">Cette rubrique couvre les modules Galerie multimédia et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8eba9-104">This topic covers media gallery modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8eba9-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="8eba9-105">Overview</span></span>

<span data-ttu-id="8eba9-106">Les modules Galerie multimédia affichent une ou plusieurs images dans une vue de galerie.</span><span class="sxs-lookup"><span data-stu-id="8eba9-106">Media gallery modules show one or more images in a gallery view.</span></span> <span data-ttu-id="8eba9-107">Ils prennent en charge les images miniatures, qui peuvent être organisées horizontalement (alignées sous l’image) ou verticalement (sous forme de colonne en regard de l’image).</span><span class="sxs-lookup"><span data-stu-id="8eba9-107">Media gallery modules support thumbnail images, which can be arranged either horizontally (as a row below the image) or vertically (as a column next to the image).</span></span> <span data-ttu-id="8eba9-108">Ils fournissent également des fonctionnalités qui permettent d’effectuer un zoom sur les images (agrandir) ou de les afficher en mode plein écran.</span><span class="sxs-lookup"><span data-stu-id="8eba9-108">Media gallery modules also provide capabilities that enable images to be zoomed (magnified) or viewed in full-screen mode.</span></span> <span data-ttu-id="8eba9-109">Pour être affichée dans un module Galerie multimédia, une image doit être disponible dans la bibliothèque multimédia du générateur de site Commerce.</span><span class="sxs-lookup"><span data-stu-id="8eba9-109">To be rendered in a media gallery module, an image must be available in the Commerce site builder Media Library.</span></span> <span data-ttu-id="8eba9-110">Pour le moment, les modules Galerie multimédia ne prennent en charge que les images.</span><span class="sxs-lookup"><span data-stu-id="8eba9-110">Currently, media gallery modules support only images.</span></span>

<span data-ttu-id="8eba9-111">Dans le mode par défaut, un module Galerie multimédia utilise l’ID produit disponible dans le contexte de page d’une page de détails de produit pour afficher les images correspondantes du produit.</span><span class="sxs-lookup"><span data-stu-id="8eba9-111">In the default mode, a media gallery module uses the product ID that is available from the page context of a product details page (PDP) to render the corresponding product images.</span></span> <span data-ttu-id="8eba9-112">Dans Commerce Headquarters, un chemin d’accès au fichier multimédia doit être défini pour tous les produits.</span><span class="sxs-lookup"><span data-stu-id="8eba9-112">In Commerce headquarters, a media file path must be defined for all products.</span></span> <span data-ttu-id="8eba9-113">Les images doivent ensuite être chargées dans la bibliothèque multimédia du générateur de site, en fonction du chemin d’accès au fichier défini pour les produits dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="8eba9-113">Images should then be uploaded to the site builder Media Library according to the file path that was defined for the products in Commerce headquarters.</span></span> <span data-ttu-id="8eba9-114">Ces images comprennent les images des produits et des variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="8eba9-114">These images include images for products and any product variants.</span></span> <span data-ttu-id="8eba9-115">Pour plus d’informations sur le chargement des images dans la bibliothèque multimédia du générateur de site, voir [Charger des images](dam-upload-images.md).</span><span class="sxs-lookup"><span data-stu-id="8eba9-115">For more information about how to upload images to site builder Media Library, see [Upload images](dam-upload-images.md).</span></span>

<span data-ttu-id="8eba9-116">Sinon, un module Galerie multimédia peut héberger un ensemble d’images entièrement organisé sur une page de la galerie d’images, où il n’existe aucune dépendance sur l’ID produit ou le contexte de la page.</span><span class="sxs-lookup"><span data-stu-id="8eba9-116">Alternatively, a media gallery module can host a fully curated set of images on an image gallery page, where there are no dependencies on the product ID or page context.</span></span> <span data-ttu-id="8eba9-117">Dans ce cas, les images doivent être chargées dans la bibliothèque multimédia du générateur de site et spécifiées dans le générateur de site.</span><span class="sxs-lookup"><span data-stu-id="8eba9-117">In this case, images must be uploaded to site builder Media Library and specified in site builder.</span></span>

<span data-ttu-id="8eba9-118">Voici quelques exemples d’utilisation des modules Galerie multimédia :</span><span class="sxs-lookup"><span data-stu-id="8eba9-118">Here are some usage examples for media gallery modules:</span></span>

- <span data-ttu-id="8eba9-119">Affichage des images de produit sur une page de détails de produit</span><span class="sxs-lookup"><span data-stu-id="8eba9-119">Rendering product images on a PDP</span></span>
- <span data-ttu-id="8eba9-120">Affichage des images de produit sur une page marketing de produit</span><span class="sxs-lookup"><span data-stu-id="8eba9-120">Rendering product images on a product marketing page</span></span>
- <span data-ttu-id="8eba9-121">Affichage d’un ensemble d’images organisé sur une page marketing, telle qu’une page de galerie</span><span class="sxs-lookup"><span data-stu-id="8eba9-121">Showcasing a curated set of images on a marketing page, such as a gallery page</span></span>

<span data-ttu-id="8eba9-122">Dans l’exemple de l’illustration suivante, une zone d’achat sur une page de détails de produit héberge des images de produit en utilisant un module Galerie multimédia.</span><span class="sxs-lookup"><span data-stu-id="8eba9-122">In the example in the following illustration, a buy box on a PDP hosts product images by using a media gallery module.</span></span>

![Exemple d’une zone d’achat sur une page de détails de produit qui héberge des images de produit en utilisant un module Galerie multimédia](./media/ecommerce-pdp-buybox.PNG)

## <a name="media-gallery-properties"></a><span data-ttu-id="8eba9-124">Propriétés de la galerie multimédia</span><span class="sxs-lookup"><span data-stu-id="8eba9-124">Media gallery properties</span></span>

| <span data-ttu-id="8eba9-125">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="8eba9-125">Property name</span></span> | <span data-ttu-id="8eba9-126">Valeurs</span><span class="sxs-lookup"><span data-stu-id="8eba9-126">Values</span></span> | <span data-ttu-id="8eba9-127">Description</span><span class="sxs-lookup"><span data-stu-id="8eba9-127">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="8eba9-128">Source de l’image</span><span class="sxs-lookup"><span data-stu-id="8eba9-128">Image source</span></span> | <span data-ttu-id="8eba9-129">**Contexte de la page** ou **ID produit**</span><span class="sxs-lookup"><span data-stu-id="8eba9-129">**Page context** or **Product ID**</span></span> | <span data-ttu-id="8eba9-130">La valeur par défaut est **Contexte de la page**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-130">The default value is **Page context**.</span></span> <span data-ttu-id="8eba9-131">Si l’option **Contexte de la page** est sélectionnée, le module s’attend à ce que la page fournisse les informations sur l’ID produit.</span><span class="sxs-lookup"><span data-stu-id="8eba9-131">If **Page context** is selected, the module expects the page to provide the product ID information.</span></span> <span data-ttu-id="8eba9-132">Si l’option **ID produit** est sélectionnée, l’ID produit d’une image doit être fourni comme valeur de la propriété **ID produit**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-132">If **Product ID** is selected, the product ID for an image must be provided as the value of the **Product ID** property.</span></span> <span data-ttu-id="8eba9-133">Cette fonctionnalité est disponible dans la version 10.0.12 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="8eba9-133">This capability is available in Commerce version 10.0.12.</span></span> |
| <span data-ttu-id="8eba9-134">ID produit</span><span class="sxs-lookup"><span data-stu-id="8eba9-134">Product ID</span></span> | <span data-ttu-id="8eba9-135">ID produit</span><span class="sxs-lookup"><span data-stu-id="8eba9-135">A product ID</span></span> | <span data-ttu-id="8eba9-136">Cette propriété n’est applicable que si la valeur de la propriété **Source de l’image** est **ID produit**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-136">This property is applicable only if the value of the **Image source** property is **Product ID**.</span></span> |
| <span data-ttu-id="8eba9-137">Zoom sur l’image</span><span class="sxs-lookup"><span data-stu-id="8eba9-137">Image zoom</span></span> | <span data-ttu-id="8eba9-138">**En ligne** ou **Conteneur**</span><span class="sxs-lookup"><span data-stu-id="8eba9-138">**Inline** or **Container**</span></span> | <span data-ttu-id="8eba9-139">Cette propriété permet à l’utilisateur d’effectuer un zoom sur les images dans le module Galerie multimédia.</span><span class="sxs-lookup"><span data-stu-id="8eba9-139">This property lets the user zoom images in the media gallery module.</span></span> <span data-ttu-id="8eba9-140">Une image peut faire l’objet d’un zoom en ligne ou dans un conteneur distinct en regard de l’image.</span><span class="sxs-lookup"><span data-stu-id="8eba9-140">An image can be zoomed either inline or in a separate container next to the image.</span></span> <span data-ttu-id="8eba9-141">Cette fonctionnalité est disponible dans la version 10.0.12</span><span class="sxs-lookup"><span data-stu-id="8eba9-141">This capability is available in 10.0.12</span></span> |
| <span data-ttu-id="8eba9-142">Échelle de zoom</span><span class="sxs-lookup"><span data-stu-id="8eba9-142">Zoom scale</span></span> | <span data-ttu-id="8eba9-143">Nombre décimal</span><span class="sxs-lookup"><span data-stu-id="8eba9-143">A decimal number</span></span> | <span data-ttu-id="8eba9-144">Cette propriété spécifie le facteur d’échelle du zoom sur les images.</span><span class="sxs-lookup"><span data-stu-id="8eba9-144">This property specifies the scale factor for zooming images.</span></span> <span data-ttu-id="8eba9-145">Par exemple, si la valeur est définie sur **2,5**, les images sont agrandies 2,5 fois.</span><span class="sxs-lookup"><span data-stu-id="8eba9-145">For example, if the value is set to **2.5**, images are magnified 2.5 times.</span></span>|
| <span data-ttu-id="8eba9-146">Plein écran</span><span class="sxs-lookup"><span data-stu-id="8eba9-146">Full screen</span></span> | <span data-ttu-id="8eba9-147">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="8eba9-147">**True** or **False**</span></span> | <span data-ttu-id="8eba9-148">Cette propriété spécifie si les images peuvent être affichées en mode plein écran.</span><span class="sxs-lookup"><span data-stu-id="8eba9-148">This property specifies whether images can be viewed in full-screen mode.</span></span> <span data-ttu-id="8eba9-149">En mode plein écran, les images peuvent également être agrandies davantage si la fonctionnalité de zoom est activée.</span><span class="sxs-lookup"><span data-stu-id="8eba9-149">In full-screen mode, images can be also be further magnified if the zoom capability is turned on.</span></span> <span data-ttu-id="8eba9-150">Cette fonctionnalité est disponible dans la version 10.0.13 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="8eba9-150">This capability is available in Commerce version 10.0.13.</span></span> |
| <span data-ttu-id="8eba9-151">Images</span><span class="sxs-lookup"><span data-stu-id="8eba9-151">Images</span></span> | <span data-ttu-id="8eba9-152">Images sélectionnées dans la bibliothèque multimédia du générateur de site</span><span class="sxs-lookup"><span data-stu-id="8eba9-152">Images that are selected from site builder Media Library</span></span> | <span data-ttu-id="8eba9-153">En plus de leur affichage à partir d’un produit, les images peuvent être organisées pour un module Galerie multimédia.</span><span class="sxs-lookup"><span data-stu-id="8eba9-153">In addition to being rendered from a product, images can be curated for a media gallery module.</span></span> <span data-ttu-id="8eba9-154">Ces images sont ajoutées à toutes les images de produit disponibles.</span><span class="sxs-lookup"><span data-stu-id="8eba9-154">These images will be appended to any product images that are available.</span></span> <span data-ttu-id="8eba9-155">Cette fonctionnalité est disponible dans la version 10.0.12 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="8eba9-155">This capability is available in Commerce version 10.0.12.</span></span> |
| <span data-ttu-id="8eba9-156">Orientation des miniatures</span><span class="sxs-lookup"><span data-stu-id="8eba9-156">Thumbnail orientation</span></span> | <span data-ttu-id="8eba9-157">**Vertical** ou **Horizontal**</span><span class="sxs-lookup"><span data-stu-id="8eba9-157">**Vertical** or **Horizontal**</span></span> | <span data-ttu-id="8eba9-158">Cette propriété spécifie si les images miniatures doivent être affichées dans une bande verticale ou une bande horizontale.</span><span class="sxs-lookup"><span data-stu-id="8eba9-158">This property specifies whether thumbnail images should be shown in a vertical strip or a horizontal strip.</span></span> |

<span data-ttu-id="8eba9-159">L’illustration suivante montre un exemple de module Galerie multimédia où les options Plein écran et Zoom sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="8eba9-159">The following illustration shows an example of a media gallery module where the full-screen and zoom options are available.</span></span>

![Exemple de module Galerie multimédia où les options Plein écran et Zoom sont disponibles](./media/ecommerce-media-zoom.png)

<span data-ttu-id="8eba9-161">L’illustration suivante montre un exemple de module Galerie multimédia contenant des images organisées (c’est-à-dire que les images spécifiées ne dépendent pas de l’ID produit ou du contexte de la page).</span><span class="sxs-lookup"><span data-stu-id="8eba9-161">The following illustration shows an example of a media gallery module that has curated images (that is, the specified images aren't dependent on the product ID or page context).</span></span>

![Exemple de module Galerie multimédia contenant des images organisées](./media/ecommerce-media-curated.PNG)

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="8eba9-163">Interaction avec Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="8eba9-163">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="8eba9-164">Lorsque la source de l’image est dérivée du contexte de la page, l’ID produit de la page de détails de produit est utilisé pour récupérer les images.</span><span class="sxs-lookup"><span data-stu-id="8eba9-164">When the image source is derived from the page context, the product ID from the PDP is used to retrieve the images.</span></span> <span data-ttu-id="8eba9-165">Le module Galerie multimédia extrait le chemin d’accès du fichier image des produits à l’aide des API (Application Programming Interfaces) de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="8eba9-165">The media gallery module retrieves the image file path for products by using Commerce Scale Unit application programming interfaces (APIs).</span></span> <span data-ttu-id="8eba9-166">Les images sont ensuite extraites de la bibliothèque multimédia afin de pouvoir les afficher dans le module.</span><span class="sxs-lookup"><span data-stu-id="8eba9-166">The images are then pulled from the Media Library so that they can be rendered in the module.</span></span>

## <a name="add-a-media-gallery-module-to-a-page"></a><span data-ttu-id="8eba9-167">Ajouter un module Galerie multimédia à une page</span><span class="sxs-lookup"><span data-stu-id="8eba9-167">Add a media gallery module to a page</span></span>

<span data-ttu-id="8eba9-168">Pour ajouter un module Galerie multimédia à une page marketing, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="8eba9-168">To add a media gallery module to a marketing page, follow these steps.</span></span>

1. <span data-ttu-id="8eba9-169">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="8eba9-169">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="8eba9-170">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle marketing**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-170">In the **New Template** dialog box, under **Template name**, enter **Marketing template**, and then select **OK**.</span></span>
1. <span data-ttu-id="8eba9-171">Dans l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-171">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8eba9-172">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Page par défaut**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-172">In the **Add Module** dialog box, select the **Default Page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8eba9-173">Dans l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-173">In the **Main** slot of the default page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8eba9-174">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-174">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8eba9-175">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="8eba9-175">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="8eba9-176">Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.</span><span class="sxs-lookup"><span data-stu-id="8eba9-176">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="8eba9-177">Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle **Modèle marketing**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-177">In the **Choose a template** dialog box, select the **Marketing template** template.</span></span> <span data-ttu-id="8eba9-178">Sous **Nom de la page**, entrez **Page de la galerie multimédia**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-178">Under **Page name**, enter **Media gallery page**, and then select **OK**.</span></span>
1. <span data-ttu-id="8eba9-179">Dans l’emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-179">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8eba9-180">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-180">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8eba9-181">Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-181">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8eba9-182">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Galerie de supports**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-182">In the **Add Module** dialog box, select the **Media gallery** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8eba9-183">Dans le volet des propriétés du module Galerie multimédia, sous **Source de l’image**, sélectionnez **Productid**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-183">In the property pane for the media gallery module, under **Image source**, select **Productid**.</span></span> <span data-ttu-id="8eba9-184">Puis, dans le champ **ID produit**, entrez un ID produit.</span><span class="sxs-lookup"><span data-stu-id="8eba9-184">Then, in the **Product id** field, enter a product ID.</span></span>
1. <span data-ttu-id="8eba9-185">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="8eba9-185">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="8eba9-186">Vous devriez pouvoir voir les images du produit dans une vue de galerie.</span><span class="sxs-lookup"><span data-stu-id="8eba9-186">You should be able to see the images for the product in a gallery view.</span></span>
1. <span data-ttu-id="8eba9-187">Pour utiliser uniquement des images organisées, dans le volet des propriétés, sous **Source de l’image**, sélectionnez **Productid**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-187">To use only curated images, in the property pane, under **Image source**, select **Productid**.</span></span> <span data-ttu-id="8eba9-188">Puis, sous **Images**, sélectionnez **Ajouter une image** autant de fois que nécessaire pour ajouter des images à partir de la bibliothèque multimédia.</span><span class="sxs-lookup"><span data-stu-id="8eba9-188">Then, under **Images**, select **Add an image** as many times as required to add images from the Media Library.</span></span>
1. <span data-ttu-id="8eba9-189">Définissez les propriétés supplémentaires que vous souhaitez définir, telles que **Zoom sur l’image**, **Facteur de zoom** et **Orientation des miniatures**.</span><span class="sxs-lookup"><span data-stu-id="8eba9-189">Set any additional properties that you want to set, such as **Image zoom**, **Zoom factor**, and **Thumbnails orientation**.</span></span>
1. <span data-ttu-id="8eba9-190">Lorsque vous avez terminé, sélectionnez **Enregistrer**, sélectionnez **Terminer la modification** pour archiver la page, puis sélectionnez **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="8eba9-190">When you've finished, select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8eba9-191">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8eba9-191">Additional resources</span></span>

[<span data-ttu-id="8eba9-192">Vue d’ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="8eba9-192">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8eba9-193">Module de zone d’achat</span><span class="sxs-lookup"><span data-stu-id="8eba9-193">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="8eba9-194">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="8eba9-194">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="8eba9-195">Importer des images</span><span class="sxs-lookup"><span data-stu-id="8eba9-195">Upload images</span></span>](dam-upload-images.md)