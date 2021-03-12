---
title: Télécharger des fichiers autres que des images et des vidéos
description: Cette rubrique décrit comment télécharger des fichiers binaires autres que des images et des vidéos dans le générateur de site Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 3392f5f36d04e8cb0a9d6e6b7db31ff62c987649
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995768"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="0db23-103">Télécharger des fichiers autres que des images et des vidéos</span><span class="sxs-lookup"><span data-stu-id="0db23-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0db23-104">Cette rubrique décrit comment télécharger des fichiers autres que des images et des vidéos dans le générateur de site Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0db23-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="0db23-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="0db23-105">Overview</span></span>

<span data-ttu-id="0db23-106">La bibliothèque multimédia du générateur de site Commerce prend en charge le téléchargement d'actifs binaires autres que des images ou des vidéos.</span><span class="sxs-lookup"><span data-stu-id="0db23-106">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="0db23-107">Par exemple, vous souhaiterez peut-être télécharger des fichiers Microsoft Excel, Microsoft Word, Microsoft PowerPoint ou PDF.</span><span class="sxs-lookup"><span data-stu-id="0db23-107">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="0db23-108">Les types de document suivants sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="0db23-108">The following document types are supported:</span></span>
- <span data-ttu-id="0db23-109">7Z</span><span class="sxs-lookup"><span data-stu-id="0db23-109">7Z</span></span>
- <span data-ttu-id="0db23-110">AVI</span><span class="sxs-lookup"><span data-stu-id="0db23-110">AVI</span></span>
- <span data-ttu-id="0db23-111">CS</span><span class="sxs-lookup"><span data-stu-id="0db23-111">CS</span></span>
- <span data-ttu-id="0db23-112">CSS</span><span class="sxs-lookup"><span data-stu-id="0db23-112">CSS</span></span>
- <span data-ttu-id="0db23-113">DOC</span><span class="sxs-lookup"><span data-stu-id="0db23-113">DOC</span></span>
- <span data-ttu-id="0db23-114">DOCX</span><span class="sxs-lookup"><span data-stu-id="0db23-114">DOCX</span></span>
- <span data-ttu-id="0db23-115">EPUB</span><span class="sxs-lookup"><span data-stu-id="0db23-115">EPUB</span></span>
- <span data-ttu-id="0db23-116">GIF</span><span class="sxs-lookup"><span data-stu-id="0db23-116">GIF</span></span>
- <span data-ttu-id="0db23-117">INDD</span><span class="sxs-lookup"><span data-stu-id="0db23-117">INDD</span></span>
- <span data-ttu-id="0db23-118">JAR</span><span class="sxs-lookup"><span data-stu-id="0db23-118">JAR</span></span>
- <span data-ttu-id="0db23-119">JPG</span><span class="sxs-lookup"><span data-stu-id="0db23-119">JPG</span></span>
- <span data-ttu-id="0db23-120">JPEG</span><span class="sxs-lookup"><span data-stu-id="0db23-120">JPEG</span></span>
- <span data-ttu-id="0db23-121">JS</span><span class="sxs-lookup"><span data-stu-id="0db23-121">JS</span></span>
- <span data-ttu-id="0db23-122">MP3</span><span class="sxs-lookup"><span data-stu-id="0db23-122">MP3</span></span>
- <span data-ttu-id="0db23-123">MP4</span><span class="sxs-lookup"><span data-stu-id="0db23-123">MP4</span></span>
- <span data-ttu-id="0db23-124">MPEG</span><span class="sxs-lookup"><span data-stu-id="0db23-124">MPEG</span></span>
- <span data-ttu-id="0db23-125">MPG</span><span class="sxs-lookup"><span data-stu-id="0db23-125">MPG</span></span>
- <span data-ttu-id="0db23-126">ODP</span><span class="sxs-lookup"><span data-stu-id="0db23-126">ODP</span></span>
- <span data-ttu-id="0db23-127">ODS</span><span class="sxs-lookup"><span data-stu-id="0db23-127">ODS</span></span>
- <span data-ttu-id="0db23-128">ODT</span><span class="sxs-lookup"><span data-stu-id="0db23-128">ODT</span></span>
- <span data-ttu-id="0db23-129">PDF</span><span class="sxs-lookup"><span data-stu-id="0db23-129">PDF</span></span>
- <span data-ttu-id="0db23-130">PNG</span><span class="sxs-lookup"><span data-stu-id="0db23-130">PNG</span></span>
- <span data-ttu-id="0db23-131">PPT</span><span class="sxs-lookup"><span data-stu-id="0db23-131">PPT</span></span>
- <span data-ttu-id="0db23-132">PPTX</span><span class="sxs-lookup"><span data-stu-id="0db23-132">PPTX</span></span>
- <span data-ttu-id="0db23-133">PS</span><span class="sxs-lookup"><span data-stu-id="0db23-133">PS</span></span>
- <span data-ttu-id="0db23-134">QXP</span><span class="sxs-lookup"><span data-stu-id="0db23-134">QXP</span></span>
- <span data-ttu-id="0db23-135">RAR</span><span class="sxs-lookup"><span data-stu-id="0db23-135">RAR</span></span>
- <span data-ttu-id="0db23-136">RTF</span><span class="sxs-lookup"><span data-stu-id="0db23-136">RTF</span></span>
- <span data-ttu-id="0db23-137">SVG</span><span class="sxs-lookup"><span data-stu-id="0db23-137">SVG</span></span>
- <span data-ttu-id="0db23-138">TAR</span><span class="sxs-lookup"><span data-stu-id="0db23-138">TAR</span></span>
- <span data-ttu-id="0db23-139">TGZ</span><span class="sxs-lookup"><span data-stu-id="0db23-139">TGZ</span></span>
- <span data-ttu-id="0db23-140">TXT</span><span class="sxs-lookup"><span data-stu-id="0db23-140">TXT</span></span>
- <span data-ttu-id="0db23-141">WMV</span><span class="sxs-lookup"><span data-stu-id="0db23-141">WMV</span></span>
- <span data-ttu-id="0db23-142">XLS</span><span class="sxs-lookup"><span data-stu-id="0db23-142">XLS</span></span>
- <span data-ttu-id="0db23-143">XLSX</span><span class="sxs-lookup"><span data-stu-id="0db23-143">XLSX</span></span>
- <span data-ttu-id="0db23-144">XML</span><span class="sxs-lookup"><span data-stu-id="0db23-144">XML</span></span>
- <span data-ttu-id="0db23-145">ZIP</span><span class="sxs-lookup"><span data-stu-id="0db23-145">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="0db23-146">Charger un fichier</span><span class="sxs-lookup"><span data-stu-id="0db23-146">Upload a file</span></span>

<span data-ttu-id="0db23-147">Pour télécharger un fichier dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="0db23-147">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="0db23-148">Dans le volet de navigation de gauche, cliquez sur **Bibliothèque multimédia**.</span><span class="sxs-lookup"><span data-stu-id="0db23-148">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="0db23-149">Dans la barre de commandes, sélectionnez **Télécharger \> Télécharger des éléments multimédias**.</span><span class="sxs-lookup"><span data-stu-id="0db23-149">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="0db23-150">Dans l'Explorateur de fichiers, sélectionnez un ou plusieurs fichiers, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="0db23-150">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="0db23-151">Dans la boîte de dialogue **Télécharger des éléments multimédia**, entrez le titre, la description et les métadonnées des mots clés selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="0db23-151">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="0db23-152">Pour publier les fichiers immédiatement après le téléchargement, sélectionnez la case à cocher **Publier les éléments multimédia après le téléchargement**.</span><span class="sxs-lookup"><span data-stu-id="0db23-152">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="0db23-153">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0db23-153">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0db23-154">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0db23-154">Additional resources</span></span>

[<span data-ttu-id="0db23-155">Vue d'ensemble de la gestion des actifs numériques</span><span class="sxs-lookup"><span data-stu-id="0db23-155">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="0db23-156">Importer des images</span><span class="sxs-lookup"><span data-stu-id="0db23-156">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="0db23-157">Télécharger une vidéo</span><span class="sxs-lookup"><span data-stu-id="0db23-157">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="0db23-158">Rogner les images</span><span class="sxs-lookup"><span data-stu-id="0db23-158">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="0db23-159">Personnaliser les points focaux de l’image</span><span class="sxs-lookup"><span data-stu-id="0db23-159">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="0db23-160">Charger et diffuser des fichiers statiques</span><span class="sxs-lookup"><span data-stu-id="0db23-160">Upload and serve static files</span></span>](upload-serve-static-files.md)
