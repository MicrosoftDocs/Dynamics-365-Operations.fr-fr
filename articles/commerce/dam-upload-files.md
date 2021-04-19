---
title: Télécharger des fichiers autres que des images et des vidéos
description: Cette rubrique décrit comment télécharger des fichiers binaires autres que des images et des vidéos dans le générateur de site Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 380bcccd1053cbcc276e964ce97f16d1d39ea75a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799251"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="5623e-103">Télécharger des fichiers autres que des images et des vidéos</span><span class="sxs-lookup"><span data-stu-id="5623e-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5623e-104">Cette rubrique décrit comment télécharger des fichiers autres que des images et des vidéos dans le générateur de site Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5623e-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="5623e-105">La bibliothèque multimédia du générateur de site Commerce prend en charge le téléchargement d’actifs binaires autres que des images ou des vidéos.</span><span class="sxs-lookup"><span data-stu-id="5623e-105">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="5623e-106">Par exemple, vous souhaiterez peut-être télécharger des fichiers Microsoft Excel, Microsoft Word, Microsoft PowerPoint ou PDF.</span><span class="sxs-lookup"><span data-stu-id="5623e-106">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="5623e-107">Les types de document suivants sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="5623e-107">The following document types are supported:</span></span>
- <span data-ttu-id="5623e-108">7Z</span><span class="sxs-lookup"><span data-stu-id="5623e-108">7Z</span></span>
- <span data-ttu-id="5623e-109">AVI</span><span class="sxs-lookup"><span data-stu-id="5623e-109">AVI</span></span>
- <span data-ttu-id="5623e-110">CS</span><span class="sxs-lookup"><span data-stu-id="5623e-110">CS</span></span>
- <span data-ttu-id="5623e-111">CSS</span><span class="sxs-lookup"><span data-stu-id="5623e-111">CSS</span></span>
- <span data-ttu-id="5623e-112">DOC</span><span class="sxs-lookup"><span data-stu-id="5623e-112">DOC</span></span>
- <span data-ttu-id="5623e-113">DOCX</span><span class="sxs-lookup"><span data-stu-id="5623e-113">DOCX</span></span>
- <span data-ttu-id="5623e-114">EPUB</span><span class="sxs-lookup"><span data-stu-id="5623e-114">EPUB</span></span>
- <span data-ttu-id="5623e-115">GIF</span><span class="sxs-lookup"><span data-stu-id="5623e-115">GIF</span></span>
- <span data-ttu-id="5623e-116">INDD</span><span class="sxs-lookup"><span data-stu-id="5623e-116">INDD</span></span>
- <span data-ttu-id="5623e-117">JAR</span><span class="sxs-lookup"><span data-stu-id="5623e-117">JAR</span></span>
- <span data-ttu-id="5623e-118">JPG</span><span class="sxs-lookup"><span data-stu-id="5623e-118">JPG</span></span>
- <span data-ttu-id="5623e-119">JPEG</span><span class="sxs-lookup"><span data-stu-id="5623e-119">JPEG</span></span>
- <span data-ttu-id="5623e-120">JS</span><span class="sxs-lookup"><span data-stu-id="5623e-120">JS</span></span>
- <span data-ttu-id="5623e-121">MP3</span><span class="sxs-lookup"><span data-stu-id="5623e-121">MP3</span></span>
- <span data-ttu-id="5623e-122">MP4</span><span class="sxs-lookup"><span data-stu-id="5623e-122">MP4</span></span>
- <span data-ttu-id="5623e-123">MPEG</span><span class="sxs-lookup"><span data-stu-id="5623e-123">MPEG</span></span>
- <span data-ttu-id="5623e-124">MPG</span><span class="sxs-lookup"><span data-stu-id="5623e-124">MPG</span></span>
- <span data-ttu-id="5623e-125">ODP</span><span class="sxs-lookup"><span data-stu-id="5623e-125">ODP</span></span>
- <span data-ttu-id="5623e-126">ODS</span><span class="sxs-lookup"><span data-stu-id="5623e-126">ODS</span></span>
- <span data-ttu-id="5623e-127">ODT</span><span class="sxs-lookup"><span data-stu-id="5623e-127">ODT</span></span>
- <span data-ttu-id="5623e-128">PDF</span><span class="sxs-lookup"><span data-stu-id="5623e-128">PDF</span></span>
- <span data-ttu-id="5623e-129">PNG</span><span class="sxs-lookup"><span data-stu-id="5623e-129">PNG</span></span>
- <span data-ttu-id="5623e-130">PPT</span><span class="sxs-lookup"><span data-stu-id="5623e-130">PPT</span></span>
- <span data-ttu-id="5623e-131">PPTX</span><span class="sxs-lookup"><span data-stu-id="5623e-131">PPTX</span></span>
- <span data-ttu-id="5623e-132">PS</span><span class="sxs-lookup"><span data-stu-id="5623e-132">PS</span></span>
- <span data-ttu-id="5623e-133">QXP</span><span class="sxs-lookup"><span data-stu-id="5623e-133">QXP</span></span>
- <span data-ttu-id="5623e-134">RAR</span><span class="sxs-lookup"><span data-stu-id="5623e-134">RAR</span></span>
- <span data-ttu-id="5623e-135">RTF</span><span class="sxs-lookup"><span data-stu-id="5623e-135">RTF</span></span>
- <span data-ttu-id="5623e-136">SVG</span><span class="sxs-lookup"><span data-stu-id="5623e-136">SVG</span></span>
- <span data-ttu-id="5623e-137">TAR</span><span class="sxs-lookup"><span data-stu-id="5623e-137">TAR</span></span>
- <span data-ttu-id="5623e-138">TGZ</span><span class="sxs-lookup"><span data-stu-id="5623e-138">TGZ</span></span>
- <span data-ttu-id="5623e-139">TXT</span><span class="sxs-lookup"><span data-stu-id="5623e-139">TXT</span></span>
- <span data-ttu-id="5623e-140">WMV</span><span class="sxs-lookup"><span data-stu-id="5623e-140">WMV</span></span>
- <span data-ttu-id="5623e-141">XLS</span><span class="sxs-lookup"><span data-stu-id="5623e-141">XLS</span></span>
- <span data-ttu-id="5623e-142">XLSX</span><span class="sxs-lookup"><span data-stu-id="5623e-142">XLSX</span></span>
- <span data-ttu-id="5623e-143">XML</span><span class="sxs-lookup"><span data-stu-id="5623e-143">XML</span></span>
- <span data-ttu-id="5623e-144">ZIP</span><span class="sxs-lookup"><span data-stu-id="5623e-144">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="5623e-145">Charger un fichier</span><span class="sxs-lookup"><span data-stu-id="5623e-145">Upload a file</span></span>

<span data-ttu-id="5623e-146">Pour télécharger un fichier dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="5623e-146">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="5623e-147">Dans le volet de navigation de gauche, cliquez sur **Bibliothèque multimédia**.</span><span class="sxs-lookup"><span data-stu-id="5623e-147">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="5623e-148">Dans la barre de commandes, sélectionnez **Télécharger \> Télécharger des éléments multimédias**.</span><span class="sxs-lookup"><span data-stu-id="5623e-148">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="5623e-149">Dans l’Explorateur de fichiers, sélectionnez un ou plusieurs fichiers, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="5623e-149">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="5623e-150">Dans la boîte de dialogue **Télécharger des éléments multimédia**, entrez le titre, la description et les métadonnées des mots clés selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="5623e-150">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="5623e-151">Pour publier les fichiers immédiatement après le téléchargement, sélectionnez la case à cocher **Publier les éléments multimédia après le téléchargement**.</span><span class="sxs-lookup"><span data-stu-id="5623e-151">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="5623e-152">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5623e-152">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5623e-153">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5623e-153">Additional resources</span></span>

[<span data-ttu-id="5623e-154">Vue d’ensemble de la gestion des actifs numériques</span><span class="sxs-lookup"><span data-stu-id="5623e-154">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="5623e-155">Importer des images</span><span class="sxs-lookup"><span data-stu-id="5623e-155">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="5623e-156">Télécharger une vidéo</span><span class="sxs-lookup"><span data-stu-id="5623e-156">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="5623e-157">Rogner les images</span><span class="sxs-lookup"><span data-stu-id="5623e-157">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="5623e-158">Personnaliser les points focaux de l’image</span><span class="sxs-lookup"><span data-stu-id="5623e-158">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="5623e-159">Charger et diffuser des fichiers statiques</span><span class="sxs-lookup"><span data-stu-id="5623e-159">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
