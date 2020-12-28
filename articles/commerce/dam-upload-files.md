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
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4acd3bec32cdfe627f6eb33dd5dc652f7cff74a8
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594210"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="6710d-103">Télécharger des fichiers autres que des images et des vidéos</span><span class="sxs-lookup"><span data-stu-id="6710d-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6710d-104">Cette rubrique décrit comment télécharger des fichiers autres que des images et des vidéos dans le générateur de site Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6710d-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="6710d-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="6710d-105">Overview</span></span>

<span data-ttu-id="6710d-106">La bibliothèque multimédia du générateur de site Commerce prend en charge le téléchargement d'actifs binaires autres que des images ou des vidéos.</span><span class="sxs-lookup"><span data-stu-id="6710d-106">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="6710d-107">Par exemple, vous souhaiterez peut-être télécharger des fichiers Microsoft Excel, Microsoft Word, Microsoft PowerPoint ou PDF.</span><span class="sxs-lookup"><span data-stu-id="6710d-107">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="6710d-108">Les types de document suivants sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="6710d-108">The following document types are supported:</span></span>
- <span data-ttu-id="6710d-109">7Z</span><span class="sxs-lookup"><span data-stu-id="6710d-109">7Z</span></span>
- <span data-ttu-id="6710d-110">AVI</span><span class="sxs-lookup"><span data-stu-id="6710d-110">AVI</span></span>
- <span data-ttu-id="6710d-111">CS</span><span class="sxs-lookup"><span data-stu-id="6710d-111">CS</span></span>
- <span data-ttu-id="6710d-112">CSS</span><span class="sxs-lookup"><span data-stu-id="6710d-112">CSS</span></span>
- <span data-ttu-id="6710d-113">DOC</span><span class="sxs-lookup"><span data-stu-id="6710d-113">DOC</span></span>
- <span data-ttu-id="6710d-114">DOCX</span><span class="sxs-lookup"><span data-stu-id="6710d-114">DOCX</span></span>
- <span data-ttu-id="6710d-115">EPUB</span><span class="sxs-lookup"><span data-stu-id="6710d-115">EPUB</span></span>
- <span data-ttu-id="6710d-116">GIF</span><span class="sxs-lookup"><span data-stu-id="6710d-116">GIF</span></span>
- <span data-ttu-id="6710d-117">INDD</span><span class="sxs-lookup"><span data-stu-id="6710d-117">INDD</span></span>
- <span data-ttu-id="6710d-118">JAR</span><span class="sxs-lookup"><span data-stu-id="6710d-118">JAR</span></span>
- <span data-ttu-id="6710d-119">JPG</span><span class="sxs-lookup"><span data-stu-id="6710d-119">JPG</span></span>
- <span data-ttu-id="6710d-120">JPEG</span><span class="sxs-lookup"><span data-stu-id="6710d-120">JPEG</span></span>
- <span data-ttu-id="6710d-121">JS</span><span class="sxs-lookup"><span data-stu-id="6710d-121">JS</span></span>
- <span data-ttu-id="6710d-122">MP3</span><span class="sxs-lookup"><span data-stu-id="6710d-122">MP3</span></span>
- <span data-ttu-id="6710d-123">MP4</span><span class="sxs-lookup"><span data-stu-id="6710d-123">MP4</span></span>
- <span data-ttu-id="6710d-124">MPEG</span><span class="sxs-lookup"><span data-stu-id="6710d-124">MPEG</span></span>
- <span data-ttu-id="6710d-125">MPG</span><span class="sxs-lookup"><span data-stu-id="6710d-125">MPG</span></span>
- <span data-ttu-id="6710d-126">ODP</span><span class="sxs-lookup"><span data-stu-id="6710d-126">ODP</span></span>
- <span data-ttu-id="6710d-127">ODS</span><span class="sxs-lookup"><span data-stu-id="6710d-127">ODS</span></span>
- <span data-ttu-id="6710d-128">ODT</span><span class="sxs-lookup"><span data-stu-id="6710d-128">ODT</span></span>
- <span data-ttu-id="6710d-129">PDF</span><span class="sxs-lookup"><span data-stu-id="6710d-129">PDF</span></span>
- <span data-ttu-id="6710d-130">PNG</span><span class="sxs-lookup"><span data-stu-id="6710d-130">PNG</span></span>
- <span data-ttu-id="6710d-131">PPT</span><span class="sxs-lookup"><span data-stu-id="6710d-131">PPT</span></span>
- <span data-ttu-id="6710d-132">PPTX</span><span class="sxs-lookup"><span data-stu-id="6710d-132">PPTX</span></span>
- <span data-ttu-id="6710d-133">PS</span><span class="sxs-lookup"><span data-stu-id="6710d-133">PS</span></span>
- <span data-ttu-id="6710d-134">QXP</span><span class="sxs-lookup"><span data-stu-id="6710d-134">QXP</span></span>
- <span data-ttu-id="6710d-135">RAR</span><span class="sxs-lookup"><span data-stu-id="6710d-135">RAR</span></span>
- <span data-ttu-id="6710d-136">RTF</span><span class="sxs-lookup"><span data-stu-id="6710d-136">RTF</span></span>
- <span data-ttu-id="6710d-137">SVG</span><span class="sxs-lookup"><span data-stu-id="6710d-137">SVG</span></span>
- <span data-ttu-id="6710d-138">TAR</span><span class="sxs-lookup"><span data-stu-id="6710d-138">TAR</span></span>
- <span data-ttu-id="6710d-139">TGZ</span><span class="sxs-lookup"><span data-stu-id="6710d-139">TGZ</span></span>
- <span data-ttu-id="6710d-140">TXT</span><span class="sxs-lookup"><span data-stu-id="6710d-140">TXT</span></span>
- <span data-ttu-id="6710d-141">WMV</span><span class="sxs-lookup"><span data-stu-id="6710d-141">WMV</span></span>
- <span data-ttu-id="6710d-142">XLS</span><span class="sxs-lookup"><span data-stu-id="6710d-142">XLS</span></span>
- <span data-ttu-id="6710d-143">XLSX</span><span class="sxs-lookup"><span data-stu-id="6710d-143">XLSX</span></span>
- <span data-ttu-id="6710d-144">XML</span><span class="sxs-lookup"><span data-stu-id="6710d-144">XML</span></span>
- <span data-ttu-id="6710d-145">ZIP</span><span class="sxs-lookup"><span data-stu-id="6710d-145">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="6710d-146">Charger un fichier</span><span class="sxs-lookup"><span data-stu-id="6710d-146">Upload a file</span></span>

<span data-ttu-id="6710d-147">Pour télécharger un fichier dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6710d-147">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="6710d-148">Dans le volet de navigation de gauche, cliquez sur **Bibliothèque multimédia**.</span><span class="sxs-lookup"><span data-stu-id="6710d-148">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="6710d-149">Dans la barre de commandes, sélectionnez **Télécharger \> Télécharger des éléments multimédias**.</span><span class="sxs-lookup"><span data-stu-id="6710d-149">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="6710d-150">Dans l'Explorateur de fichiers, sélectionnez un ou plusieurs fichiers, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="6710d-150">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="6710d-151">Dans la boîte de dialogue **Télécharger des éléments multimédia**, entrez le titre, la description et les métadonnées des mots clés selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6710d-151">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="6710d-152">Pour publier les fichiers immédiatement après le téléchargement, sélectionnez la case à cocher **Publier les éléments multimédia après le téléchargement**.</span><span class="sxs-lookup"><span data-stu-id="6710d-152">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="6710d-153">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6710d-153">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6710d-154">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6710d-154">Additional resources</span></span>

[<span data-ttu-id="6710d-155">Vue d'ensemble de la gestion des actifs numériques</span><span class="sxs-lookup"><span data-stu-id="6710d-155">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="6710d-156">Importer des images</span><span class="sxs-lookup"><span data-stu-id="6710d-156">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="6710d-157">Télécharger une vidéo</span><span class="sxs-lookup"><span data-stu-id="6710d-157">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="6710d-158">Rogner les images</span><span class="sxs-lookup"><span data-stu-id="6710d-158">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="6710d-159">Personnaliser les points focaux de l’image</span><span class="sxs-lookup"><span data-stu-id="6710d-159">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="6710d-160">Charger et diffuser des fichiers statiques</span><span class="sxs-lookup"><span data-stu-id="6710d-160">Upload and serve static files</span></span>](upload-serve-static-files.md)
