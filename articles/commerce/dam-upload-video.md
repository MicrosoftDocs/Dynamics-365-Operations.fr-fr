---
title: Télécharger des vidéos
description: Cette rubrique décrit comment télécharger des vidéos dans le générateur de site Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 8dd9e710f9a6ea593a0673e7902fadf84ca05cff
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594306"
---
# <a name="upload-videos"></a><span data-ttu-id="cfdfd-103">Télécharger des vidéos</span><span class="sxs-lookup"><span data-stu-id="cfdfd-103">Upload videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cfdfd-104">Cette rubrique décrit comment télécharger des vidéos dans le générateur de site Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-104">This topic describes how to upload videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="cfdfd-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="cfdfd-105">Overview</span></span>

<span data-ttu-id="cfdfd-106">La bibliothèque multimédia du générateur de site Commerce vous permet de télécharger des vidéos.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-106">The Commerce site builder Media Library allows you to upload videos.</span></span> <span data-ttu-id="cfdfd-107">Vous devez toujours télécharger la version d'une vidéo avec le bitrate et la résolution les plus élevés, car la vidéo sera automatiquement convertie pour être appropriée aux différentes fenêtres d'affichage et leurs points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-107">You should always upload the version of a video with the highest bitrate and resolution, because the video will be automatically converted to be suitable for different viewports and their breakpoints.</span></span>

### <a name="video-information-specified-during-upload"></a><span data-ttu-id="cfdfd-108">Informations vidéo spécifiées lors du téléchargement</span><span class="sxs-lookup"><span data-stu-id="cfdfd-108">Video information specified during upload</span></span>

<span data-ttu-id="cfdfd-109">Lors du téléchargement d'une vidéo, les informations suivantes peuvent être spécifiées.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-109">When uploading a video, the following information can be specified.</span></span>

- <span data-ttu-id="cfdfd-110">**Titre, description, mots clés** : Métadonnées de la vidéo.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-110">**Title, Description, Keywords**: Metadata of the video.</span></span>
- <span data-ttu-id="cfdfd-111">**Générer automatiquement des sous-titres codés** : spécifie si les sous-titres doivent être générés automatiquement pour la vidéo.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-111">**Automatically generate closed captions**: Specifies whether closed captions should be automatically generated for the video.</span></span>
- <span data-ttu-id="cfdfd-112">**Sous-titrage** : spécifie les sous-titres codés à utiliser.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-112">**Closed Caption**: Specifies the closed captions to be used.</span></span>
- <span data-ttu-id="cfdfd-113">**Audio régulier** : spécifie la piste audio standard à utiliser.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-113">**Regular Audio**: Specifies the regular audio track to be used.</span></span>
- <span data-ttu-id="cfdfd-114">**Vignette** : spécifie la vignette de la vidéo.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-114">**Thumbnail**: Specifies the thumbnail for the video.</span></span> <span data-ttu-id="cfdfd-115">Si non spécifié, elle sera générée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-115">If not specified, it will be generated automatically.</span></span>
- <span data-ttu-id="cfdfd-116">**Audio descriptif** : spécifie la piste audio descriptive à utiliser.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-116">**Descriptive Audio**: Specifies the descriptive audio track to be used.</span></span>

## <a name="upload-a-video"></a><span data-ttu-id="cfdfd-117">Télécharger une vidéo</span><span class="sxs-lookup"><span data-stu-id="cfdfd-117">Upload a video</span></span>

<span data-ttu-id="cfdfd-118">Pour télécharger une vidéo dans le générateur de site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-118">To upload a video in site builder, follow these steps.</span></span>

1. <span data-ttu-id="cfdfd-119">Dans le volet de navigation de gauche, cliquez sur **Bibliothèque multimédia**.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-119">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="cfdfd-120">Dans la barre de commandes, sélectionnez **Télécharger \> Télécharger des éléments multimédias**.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-120">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="cfdfd-121">Dans la fenêtre de l'Explorateur de fichiers, recherchez et sélectionnez un ou plusieurs fichiers vidéo à télécharger, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-121">In the File Explorer window, navigate to and select one or more video files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="cfdfd-122">Dans la boîte de dialogue **Télécharger un élément multimédia**, entrez le titre et le texte de remplacement requis.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-122">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="cfdfd-123">Entrez une description et des mots clés facultatifs et sélectionnez une catégorie si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-123">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="cfdfd-124">Si vous souhaitez publier les images immédiatement après le téléchargement, sélectionnez la case à cocher **Publier les éléments multimédia après le téléchargement**.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-124">If you want to publish the image(s) after immediately upload, select the **Publish media items after upload** check box</span></span>
1. <span data-ttu-id="cfdfd-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-125">Select **OK**.</span></span>

<span data-ttu-id="cfdfd-126">Si vous importez plusieurs types d'actifs simultanément (par exemple, des images et des vidéos), dans la boîte de dialogue **Télécharger un élément multimédia**, vous ne pourrez spécifier que des mots clés, si les fichiers doivent être publiés immédiatement après le téléchargement et si les sous-titres codés doivent être générés automatiquement pour les fichiers vidéo.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-126">If you are uploading multiple types of assets simultaneously (for example, images and videos), in the **Upload Media Item** dialog box you will only be able to specify keywords, whether the files should be published immediately after upload, and whether closed captions should be automatically generated for video files.</span></span> <span data-ttu-id="cfdfd-127">Tous les actifs partageront les mêmes mots clés.</span><span class="sxs-lookup"><span data-stu-id="cfdfd-127">All the assets will share the same keywords.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cfdfd-128">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="cfdfd-128">Additional resources</span></span>

[<span data-ttu-id="cfdfd-129">Vue d'ensemble de la gestion des actifs numériques</span><span class="sxs-lookup"><span data-stu-id="cfdfd-129">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="cfdfd-130">Importer des images</span><span class="sxs-lookup"><span data-stu-id="cfdfd-130">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="cfdfd-131">Télécharger des fichiers</span><span class="sxs-lookup"><span data-stu-id="cfdfd-131">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="cfdfd-132">Rogner les images</span><span class="sxs-lookup"><span data-stu-id="cfdfd-132">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="cfdfd-133">Personnaliser les points focaux de l’image</span><span class="sxs-lookup"><span data-stu-id="cfdfd-133">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="cfdfd-134">Charger et diffuser des fichiers statiques</span><span class="sxs-lookup"><span data-stu-id="cfdfd-134">Upload and serve static files</span></span>](upload-serve-static-files.md)
