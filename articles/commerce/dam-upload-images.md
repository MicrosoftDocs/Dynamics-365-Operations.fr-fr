---
title: Importer des images
description: Cette rubrique décrit comment télécharger des images dans le générateur de site Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f562d3376fde6a24e6a1e1a3f7f4192cf290ae90
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594282"
---
# <a name="upload-images"></a><span data-ttu-id="a49a4-103">Importer des images</span><span class="sxs-lookup"><span data-stu-id="a49a4-103">Upload images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a49a4-104">Cette rubrique décrit comment télécharger des images dans le générateur de site Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a49a4-104">This topic describes how to upload images in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="a49a4-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="a49a4-105">Overview</span></span>

<span data-ttu-id="a49a4-106">La bibliothèque multimédia du générateur de site Commerce vous permet de télécharger des images, individuellement ou en bloc, à l'aide de dossiers.</span><span class="sxs-lookup"><span data-stu-id="a49a4-106">The Commerce site builder Media Library allows you to upload images, either singly or in bulk using folders.</span></span> <span data-ttu-id="a49a4-107">Vous devez toujours télécharger la version de l'image avec la résolution et la qualité les plus élevées, car le composant du redimensionneur d'image optimisera automatiquement l'image pour différentes fenêtres d'affichage et leurs points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="a49a4-107">You should always upload the version of the image with highest resolution and quality, because the image resizer component will automatically optimize the image for different viewports and their breakpoints.</span></span>

### <a name="image-information-specified-during-upload"></a><span data-ttu-id="a49a4-108">Informations d'image spécifiées lors du téléchargement</span><span class="sxs-lookup"><span data-stu-id="a49a4-108">Image information specified during upload</span></span>

<span data-ttu-id="a49a4-109">Lors du téléchargement d'une image, les informations suivantes peuvent être spécifiées.</span><span class="sxs-lookup"><span data-stu-id="a49a4-109">When uploading an image, the following information can be specified.</span></span>

- <span data-ttu-id="a49a4-110">**Titre, texte alternatif, description, mots-clés** : métadonnées de l'image ou des images.</span><span class="sxs-lookup"><span data-stu-id="a49a4-110">**Title, Alt Text, Description, Keywords**: Metadata of the image or images.</span></span> <span data-ttu-id="a49a4-111">Le titre et le texte alternatif sont des valeurs obligatoires.</span><span class="sxs-lookup"><span data-stu-id="a49a4-111">Title and alt text are required values.</span></span>
- <span data-ttu-id="a49a4-112">**Sélectionner une catégorie** :</span><span class="sxs-lookup"><span data-stu-id="a49a4-112">**Select category**:</span></span>
    - <span data-ttu-id="a49a4-113">**Aucun** : Utilisé pour une ou plusieurs images de narration de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="a49a4-113">**None**: Used for an e-Commerce storytelling image or images.</span></span>
    - <span data-ttu-id="a49a4-114">**Produit, catégorie, client, employé, catalogue** : Utilisé pour l'image ou les images omnicanal Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a49a4-114">**Product, Category, Customer, Employee, Catalog**: Used for Dynamics 365 Commerce omni-channel image or images.</span></span>
- <span data-ttu-id="a49a4-115">**Publier les actifs après chargement** : lorsque cette case est cochée, la ou les images sont publiées immédiatement après le chargement.</span><span class="sxs-lookup"><span data-stu-id="a49a4-115">**Publish assets after upload**: When this check box is selected, the image or images are published immediately after upload.</span></span>

> [!NOTE]
> <span data-ttu-id="a49a4-116">Les actifs d'image auxquels une catégorie a été affectée sont également automatiquement étiquetés avec la catégorie en tant que mot clé pour faciliter la recherche d'éléments de catégorie spécifique.</span><span class="sxs-lookup"><span data-stu-id="a49a4-116">Image assets with a category assigned are also automatically tagged with the category as a keyword to aid searching for assets of a specific category.</span></span>

### <a name="naming-conventions-for-omni-channel-images"></a><span data-ttu-id="a49a4-117">Conventions de dénomination des images omnicanal</span><span class="sxs-lookup"><span data-stu-id="a49a4-117">Naming conventions for omni-channel images</span></span> 

<span data-ttu-id="a49a4-118">Si vous avez configuré la bibliothèque multimédia comme processus d'arrière-plan d'image omnicanal, vous pouvez utiliser des catégories d'images pour indiquer à quelle catégorie l'image téléchargée appartient.</span><span class="sxs-lookup"><span data-stu-id="a49a4-118">If you have configured the Media Library as the omni-channel image backend, you can use image categories to indicate which category the uploaded image belongs to.</span></span> <span data-ttu-id="a49a4-119">Il convient également de suivre une convention de dénomination pour garantir que les images sont correctement récupérées par d'autres canaux, tels que le point de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="a49a4-119">There is also a naming convention that should be followed to ensure that images are retrieved correctly by other channels, such as point of sale (POS).</span></span>

<span data-ttu-id="a49a4-120">La convention de dénomination par défaut varie en fonction de la catégorie :</span><span class="sxs-lookup"><span data-stu-id="a49a4-120">The default naming convention varies based on the category:</span></span>
- <span data-ttu-id="a49a4-121">Les images du catalogue doivent être intitulées "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="a49a4-121">Catalog images should be named "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span></span>
- <span data-ttu-id="a49a4-122">Les images de catégorie doivent être intitulées "**/Categories/\{CategoryName\}.png**"</span><span class="sxs-lookup"><span data-stu-id="a49a4-122">Category images should be named "**/Categories/\{CategoryName\}.png**"</span></span>
- <span data-ttu-id="a49a4-123">Les images de client doivent être intitulées "**/Customers/\{CustomerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="a49a4-123">Customer images should be named "**/Customers/\{CustomerNumber\}.jpg**"</span></span>
- <span data-ttu-id="a49a4-124">Les images d'employé doivent être intitulées "**/Workers/\{WorkerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="a49a4-124">Employee images should be named "**/Workers/\{WorkerNumber\}.jpg**"</span></span>
- <span data-ttu-id="a49a4-125">Les images de produit doivent être intitulées "**/Products/\{ProductNumber\}_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="a49a4-125">Product images should be named "**/Products/\{ProductNumber\}_000_001.png**"</span></span>
    - <span data-ttu-id="a49a4-126">001 est la séquence de l'image et peut être 001, 002, 003, 004 ou 005</span><span class="sxs-lookup"><span data-stu-id="a49a4-126">001 is the sequence of the image and it can be 001, 002, 003, 004 or 005</span></span>
- <span data-ttu-id="a49a4-127">Les images de variante de produit doivent être intitulées "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="a49a4-127">Product variant images should be named "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"</span></span>

## <a name="upload-an-image"></a><span data-ttu-id="a49a4-128">Télécharger une image</span><span class="sxs-lookup"><span data-stu-id="a49a4-128">Upload an image</span></span>

<span data-ttu-id="a49a4-129">Pour télécharger une image dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a49a4-129">To upload an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="a49a4-130">Dans le volet de navigation de gauche, cliquez sur **Bibliothèque multimédia**.</span><span class="sxs-lookup"><span data-stu-id="a49a4-130">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="a49a4-131">Dans la barre de commandes, sélectionnez **Télécharger \> Télécharger des éléments multimédias**.</span><span class="sxs-lookup"><span data-stu-id="a49a4-131">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="a49a4-132">Dans la fenêtre de l'Explorateur de fichiers, recherchez et sélectionnez un ou plusieurs fichiers image à télécharger, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="a49a4-132">In the File Explorer window, navigate to and select one or more image files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="a49a4-133">Dans la boîte de dialogue **Télécharger un élément multimédia**, entrez le titre et le texte de remplacement requis.</span><span class="sxs-lookup"><span data-stu-id="a49a4-133">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="a49a4-134">Entrez une description et des mots clés facultatifs et sélectionnez une catégorie si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="a49a4-134">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="a49a4-135">Si vous souhaitez publier les images immédiatement après le téléchargement, sélectionnez la case à cocher **Publier les éléments multimédia après le téléchargement**.</span><span class="sxs-lookup"><span data-stu-id="a49a4-135">If you want to publish the image(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="a49a4-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a49a4-136">Select **OK**.</span></span>

## <a name="upload-a-folder-of-images"></a><span data-ttu-id="a49a4-137">Télécharger un dossier d'images</span><span class="sxs-lookup"><span data-stu-id="a49a4-137">Upload a folder of images</span></span>

<span data-ttu-id="a49a4-138">Pour télécharger en bloc un dossier d'images dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a49a4-138">To bulk upload a folder of images in site builder, follow these steps.</span></span>

1. <span data-ttu-id="a49a4-139">Dans le volet de navigation de gauche, cliquez sur **Bibliothèque multimédia**.</span><span class="sxs-lookup"><span data-stu-id="a49a4-139">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="a49a4-140">Dans la barre de commandes, sélectionnez **Télécharger \> Télécharger le dossier**.</span><span class="sxs-lookup"><span data-stu-id="a49a4-140">On the command bar, select **Upload \> Upload Folder**.</span></span>
1. <span data-ttu-id="a49a4-141">Dans la fenêtre de l'Explorateur de fichiers, recherchez et sélectionnez un dossier à télécharger, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="a49a4-141">In the File Explorer window, navigate to and select a folder to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="a49a4-142">Dans la boîte de dialogue **Télécharger des éléments multimédia**, entrez des mots clés facultatifs et sélectionnez une catégorie si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="a49a4-142">In the **Upload Media Items** dialog box, enter optional keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="a49a4-143">Si vous souhaitez publier les images dans le dossier immédiatement après le téléchargement, sélectionnez la case à cocher **Publier les éléments multimédia après le téléchargement**.</span><span class="sxs-lookup"><span data-stu-id="a49a4-143">If you want to publish the images in the folder immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="a49a4-144">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a49a4-144">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a49a4-145">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a49a4-145">Additional resources</span></span>

[<span data-ttu-id="a49a4-146">Vue d'ensemble de la gestion des actifs numériques</span><span class="sxs-lookup"><span data-stu-id="a49a4-146">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="a49a4-147">Télécharger une vidéo</span><span class="sxs-lookup"><span data-stu-id="a49a4-147">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="a49a4-148">Télécharger des fichiers</span><span class="sxs-lookup"><span data-stu-id="a49a4-148">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="a49a4-149">Rogner les images</span><span class="sxs-lookup"><span data-stu-id="a49a4-149">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="a49a4-150">Personnaliser les points focaux de l’image</span><span class="sxs-lookup"><span data-stu-id="a49a4-150">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="a49a4-151">Charger et diffuser des fichiers statiques</span><span class="sxs-lookup"><span data-stu-id="a49a4-151">Upload and serve static files</span></span>](upload-serve-static-files.md)
