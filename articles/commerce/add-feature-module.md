---
title: Module Fonctionnalité
description: Cette rubrique couvre les modules de fonctionnalités et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785281"
---
# <a name="feature-module"></a><span data-ttu-id="3d5b5-103">Module Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="3d5b5-103">Feature module</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="3d5b5-104">Cette rubrique couvre les modules de fonctionnalités et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-104">This topic covers feature modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3d5b5-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="3d5b5-105">Overview</span></span>

<span data-ttu-id="3d5b5-106">Un module de fonctionnalités permet de publier des produits ou des promotions sur le marché via une combinaison des images et du texte.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-106">A feature module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="3d5b5-107">Par exemple, un détaillant peut ajouter un module de fonctionnalités à une page de détails des produits pour souligner les fonctionnalités du produit.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-107">For example, a retailer can add a feature module to a product details page to highlight the features of the product.</span></span>

<span data-ttu-id="3d5b5-108">Un module de fonctionnalités dépend des données du système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="3d5b5-108">A feature module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="3d5b5-109">Ce module autonome ne dépend du contexte d'un autre module sur la page.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="3d5b5-110">Un module de fonctionnalités peut être mis dans n'importe quelle page de site où un détaillant souhaite lancer sur le marché ou promouvoir un événement (par exemple les produits, les soldes ou des fonctionnalités).</span><span class="sxs-lookup"><span data-stu-id="3d5b5-110">A feature module can be put on any site page where a retailer wants to market or promote something (for example products, sales, or features).</span></span>

## <a name="examples-of-feature-modules-in-e-commerce"></a><span data-ttu-id="3d5b5-111">Exemples de modules de fonctionnalités dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="3d5b5-111">Examples of feature modules in e-Commerce</span></span>

<span data-ttu-id="3d5b5-112">Un module de fonctionnalités peut être utilisé sur les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="3d5b5-112">A feature module can used on the following pages:</span></span>

- <span data-ttu-id="3d5b5-113">Une page de détails du produit, pour présenter les fonctionnalités du produit</span><span class="sxs-lookup"><span data-stu-id="3d5b5-113">A product details page, to showcase product features</span></span>
- <span data-ttu-id="3d5b5-114">La page d'accueil, pour promouvoir des produits</span><span class="sxs-lookup"><span data-stu-id="3d5b5-114">The home page, to promote products</span></span>
- <span data-ttu-id="3d5b5-115">Une page de catégorie, pour mettre en valeur une catégorie de produits</span><span class="sxs-lookup"><span data-stu-id="3d5b5-115">A category page, to highlight a category of products</span></span>

## <a name="feature-module-properties"></a><span data-ttu-id="3d5b5-116">Propriétés du module de fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="3d5b5-116">Feature module properties</span></span>

| <span data-ttu-id="3d5b5-117">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="3d5b5-117">Property name</span></span>     | <span data-ttu-id="3d5b5-118">Valeurs</span><span class="sxs-lookup"><span data-stu-id="3d5b5-118">Values</span></span> | <span data-ttu-id="3d5b5-119">Description</span><span class="sxs-lookup"><span data-stu-id="3d5b5-119">Description</span></span> |
|-------------------|--------|-------------|
| <span data-ttu-id="3d5b5-120">Image</span><span class="sxs-lookup"><span data-stu-id="3d5b5-120">Image</span></span>             | <span data-ttu-id="3d5b5-121">Fichier image</span><span class="sxs-lookup"><span data-stu-id="3d5b5-121">Image file</span></span> | <span data-ttu-id="3d5b5-122">Une image peut être utilisée pour commercialiser le produit ou la promotion.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-122">An image can be used to market the product or promotion.</span></span> <span data-ttu-id="3d5b5-123">Une image peut être chargée dans la galerie d'images, ou une image existante peut être utilisée.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-123">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="3d5b5-124">En-tête</span><span class="sxs-lookup"><span data-stu-id="3d5b5-124">Heading</span></span>           | <span data-ttu-id="3d5b5-125">Texte d'en-tête et balise d'en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="3d5b5-125">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="3d5b5-126">Chaque module de fonctionnalités peut avoir un en-tête.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-126">Every feature module can have a heading.</span></span> <span data-ttu-id="3d5b5-127">Par défaut, la balise d'en-tête **H2** sert pour l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-127">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="3d5b5-128">Toutefois, la balise peut être modifiée pour satisfaire aux exigences d'accessibilité.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-128">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="3d5b5-129">Paragraphe</span><span class="sxs-lookup"><span data-stu-id="3d5b5-129">Paragraph</span></span>         | <span data-ttu-id="3d5b5-130">Texte du paragraphe</span><span class="sxs-lookup"><span data-stu-id="3d5b5-130">Paragraph text</span></span> | <span data-ttu-id="3d5b5-131">Les modules de fonctionnalités prennent en charge le texte de paragraphe dans en format de texte enrichi.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-131">Feature modules support paragraph text in rich text format.</span></span> <span data-ttu-id="3d5b5-132">Certains capacités de texte enrichi de base sont prises en charge, telles que gras, souligné, et italiques, et des liens hypertexte.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-132">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="3d5b5-133">Certaines de ces fonctionnalités peuvent être remplacées par le thème de la page qui s'applique au module.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-133">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="3d5b5-134">Lien</span><span class="sxs-lookup"><span data-stu-id="3d5b5-134">Link</span></span>              | <span data-ttu-id="3d5b5-135">Texte du lien, URL du lien, étiquette ARIA (Applications Internet enrichie accessibles), et **Ouvrir le lien dans le nouvel onglet**</span><span class="sxs-lookup"><span data-stu-id="3d5b5-135">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="3d5b5-136">Les modules de fonctionnalités prennent en charge un ou plusieurs liens d'« appels à l'action ».</span><span class="sxs-lookup"><span data-stu-id="3d5b5-136">Feature modules support one or more "call to action" links.</span></span> <span data-ttu-id="3d5b5-137">Si un lien est ajouté, un texte de lien, une URL, et une étiquette ARIA sont requis.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-137">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="3d5b5-138">Les étiquettes ARIA doivent être descriptives pour satisfaire aux exigences d'accessibilité.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-138">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="3d5b5-139">Les liens peuvent être configurés de sorte qu'ils sont ouverts sur un nouvel onglet.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-139">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="3d5b5-140">Placement de l'image</span><span class="sxs-lookup"><span data-stu-id="3d5b5-140">Image placement</span></span>   | <span data-ttu-id="3d5b5-141">**Droite**, **Gauche**, **Haut** ou **Bas**</span><span class="sxs-lookup"><span data-stu-id="3d5b5-141">**Right**, **Left**, **Top**, or **Bottom**</span></span> | <span data-ttu-id="3d5b5-142">Cette propriété définit la position de l'image par rapport à le texte.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-142">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="3d5b5-143">Par exemple, si **Droite** est sélectionné, l'image apparaît à droite du texte.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-143">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="3d5b5-144">Taille de colonne d’image</span><span class="sxs-lookup"><span data-stu-id="3d5b5-144">Image column size</span></span> | <span data-ttu-id="3d5b5-145">Une valeur de **1** à **12**</span><span class="sxs-lookup"><span data-stu-id="3d5b5-145">A value from **1** through **12**</span></span> | <span data-ttu-id="3d5b5-146">Cette propriété définit la taille de l'image par rapport à le texte.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-146">This property defines the size of the image relative to the text.</span></span> <span data-ttu-id="3d5b5-147">La taille est exprimée sous forme de nombre de colonnes dans la page.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-147">Size is expressed as a number of columns on the page.</span></span> <span data-ttu-id="3d5b5-148">Il y a 12 colonnes dans une page.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-148">There are 12 columns on a page.</span></span> <span data-ttu-id="3d5b5-149">Par défaut, le texte et l'image sont de taille égale (six colonnes chacun).</span><span class="sxs-lookup"><span data-stu-id="3d5b5-149">By default, the image and text have equal size (six columns each).</span></span> <span data-ttu-id="3d5b5-150">Toutefois, la taille peut être ajustée au besoin.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-150">However, the size can be adjusted as required.</span></span> |

## <a name="add-a-feature-module-to-a-new-page"></a><span data-ttu-id="3d5b5-151">Ajouter un module de fonctionnalités à une nouvelle page</span><span class="sxs-lookup"><span data-stu-id="3d5b5-151">Add a feature module to a new page</span></span> 

<span data-ttu-id="3d5b5-152">Pour ajouter un module de fonctionnalités à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-152">To add a feature module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="3d5b5-153">Accédez à **Modèles**, puis créez un modèle de page nommé **modèle de fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-153">Go to **Templates**, and create a page template that is named **feature template**.</span></span>
1. <span data-ttu-id="3d5b5-154">À l'emplacement **Principal** de la page par défaut, ajoutez un module de fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-154">In the **Main** slot of the default page, add a feature module.</span></span>
1. <span data-ttu-id="3d5b5-155">Archivez le modèle, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-155">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="3d5b5-156">Utilisez le modèle de fonctionnalités que vous venez de créer pour créer une page qui s'appelle **page Fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-156">Use the feature template that you just created to create a page that is named **feature page**.</span></span>
1. <span data-ttu-id="3d5b5-157">À l'emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis le sélectionnez **Ajoutez le module**.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-157">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3d5b5-158">Dans la boîte de dialogue **Ajouter le module**, sous **Sélectionner les modules**, sélectionnez un module de fonctionnalités, et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-158">In the **Add Module** dialog box, under **Select Modules**, select a feature module, and then select **OK**.</span></span>
1. <span data-ttu-id="3d5b5-159">Dans l'arborescence de contour à gauche, sélectionnez le module de fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-159">In the outline tree on the left, select the feature module.</span></span>
1. <span data-ttu-id="3d5b5-160">Dans le volet de propriétés de droite, sélectionnez **Ajouter une image**.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-160">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="3d5b5-161">Puis sélectionnez une image existante ou téléchargez une nouvelle image.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-161">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="3d5b5-162">Sélectionnez **En-tête**.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-162">Select **Heading**.</span></span>
1. <span data-ttu-id="3d5b5-163">Dans la boîte de dialogue **En-tête**, ajoutez le texte de l'en-tête, sélectionnez le niveau d'en-tête, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-163">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="3d5b5-164">Sous **Texte enrichi**, ajoutez le texte comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-164">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="3d5b5-165">Sélectionnez **Ajouter le lien d'action**.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-165">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="3d5b5-166">Dans la boîte de dialogue **Lien d'action**, ajoutez le texte du lien, une URL de lien, et une étiquette ARIA pour le lien, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-166">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="3d5b5-167">Enregistrer la page et affichez un aperçu vos modifications.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-167">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="3d5b5-168">Archivez la page, et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="3d5b5-168">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3d5b5-169">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3d5b5-169">Additional resources</span></span>

[<span data-ttu-id="3d5b5-170">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="3d5b5-170">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3d5b5-171">Module Alerte</span><span class="sxs-lookup"><span data-stu-id="3d5b5-171">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="3d5b5-172">Module Carrousel</span><span class="sxs-lookup"><span data-stu-id="3d5b5-172">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="3d5b5-173">Module de bloc de contenu riche</span><span class="sxs-lookup"><span data-stu-id="3d5b5-173">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="3d5b5-174">Module Placement de contenu</span><span class="sxs-lookup"><span data-stu-id="3d5b5-174">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="3d5b5-175">Module Bannière</span><span class="sxs-lookup"><span data-stu-id="3d5b5-175">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="3d5b5-176">Module Lecteur vidéo</span><span class="sxs-lookup"><span data-stu-id="3d5b5-176">Video player module</span></span>](add-video-player.md)
