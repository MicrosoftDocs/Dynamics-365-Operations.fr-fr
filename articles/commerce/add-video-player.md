---
title: Module Lecteur vidéo
description: Cette rubrique couvre les modules de lecteur vidéo et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025644"
---
# <a name="video-player-module"></a><span data-ttu-id="95465-103">Module Lecteur vidéo</span><span class="sxs-lookup"><span data-stu-id="95465-103">Video player module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="95465-104">Cette rubrique couvre les modules de lecteur vidéo et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="95465-104">This topic covers video player modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="95465-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="95465-105">Overview</span></span>

<span data-ttu-id="95465-106">Le module de lecteur vidéo permet de prendre en charge la lecture de vidéos.</span><span class="sxs-lookup"><span data-stu-id="95465-106">The video player module is used to support video playback.</span></span> <span data-ttu-id="95465-107">Il peut être ajouté à n'importe quelle page, à condition que le contenu vidéo soit téléchargé et disponible dans le système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="95465-107">It can be added to any page, provided that video content is uploaded to and available in the content management system (CMS).</span></span> <span data-ttu-id="95465-108">Le module lecteur vidéo prend en charge le type de média .mp4.</span><span class="sxs-lookup"><span data-stu-id="95465-108">The video player module supports the .mp4 media type.</span></span>

## <a name="video-player-module"></a><span data-ttu-id="95465-109">Module de lecture vidéo</span><span class="sxs-lookup"><span data-stu-id="95465-109">Video player module</span></span>

<span data-ttu-id="95465-110">Le module de lecteur vidéo peut être utilisé pour présenter des vidéos sur un site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="95465-110">The video player module can be used to showcase videos on an e-Commerce site.</span></span> <span data-ttu-id="95465-111">Il prend en charge toutes les fonctionnalités de lecture, telles que la lecture, la pause, le mode plein écran, les descriptions audio et les sous-titres codés.</span><span class="sxs-lookup"><span data-stu-id="95465-111">It supports all playback capabilities, such as play, pause, full-size mode, audio descriptions, and closed captions.</span></span> <span data-ttu-id="95465-112">Le module de lecteur vidéo prend également en charge la personnalisation des sous-titres codés pour satisfaire aux normes d'accessibilité Microsoft.</span><span class="sxs-lookup"><span data-stu-id="95465-112">The video player module also supports customization of closed captions to meet Microsoft accessibility standards.</span></span> <span data-ttu-id="95465-113">Par exemple, vous pouvez personnaliser la taille de police et la couleur d'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="95465-113">For example, you can customize the font size and background color.</span></span>

<span data-ttu-id="95465-114">Le module lecteur vidéo prend également en charge les pistes audio secondaires.</span><span class="sxs-lookup"><span data-stu-id="95465-114">The video player module also supports secondary audio tracks.</span></span> <span data-ttu-id="95465-115">Lorsqu'une vidéo est téléchargée vers le CMS, une piste audio secondaire peut également être téléchargée.</span><span class="sxs-lookup"><span data-stu-id="95465-115">When a video is uploaded to the CMS, a secondary audio track can also be uploaded.</span></span> <span data-ttu-id="95465-116">Le module lecteur vidéo peut ensuite lire la piste audio secondaire si un utilisateur la sélectionne.</span><span class="sxs-lookup"><span data-stu-id="95465-116">The video player module can then play the secondary audio track if a user selects it.</span></span>

### <a name="examples-of-video-player-modules-in-e-commerce"></a><span data-ttu-id="95465-117">Exemples de modules de lecteur vidéo dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="95465-117">Examples of video player modules in e-Commerce</span></span>

- <span data-ttu-id="95465-118">Vidéos de formation sur les pages de détails des produits ou des pages marketing</span><span class="sxs-lookup"><span data-stu-id="95465-118">Instructional videos on product details pages or marketing pages</span></span>
- <span data-ttu-id="95465-119">Vidéos publicitaires ou vidéos sur les stratégies sur une page marketing</span><span class="sxs-lookup"><span data-stu-id="95465-119">Promotional videos or videos about policies on any marketing page</span></span>
- <span data-ttu-id="95465-120">Vidéos marketing qui mettent en avant des fonctionnalités du produit sur les pages de détails des produits ou des pages marketing</span><span class="sxs-lookup"><span data-stu-id="95465-120">Marketing videos that highlight product features on product details pages or marketing pages</span></span>

### <a name="video-player-module-properties"></a><span data-ttu-id="95465-121">Propriétés du module de lecture vidéo</span><span class="sxs-lookup"><span data-stu-id="95465-121">Video player module properties</span></span>

| <span data-ttu-id="95465-122">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="95465-122">Property name</span></span>         | <span data-ttu-id="95465-123">Valeur</span><span class="sxs-lookup"><span data-stu-id="95465-123">Value</span></span>                               | <span data-ttu-id="95465-124">Description</span><span class="sxs-lookup"><span data-stu-id="95465-124">Description</span></span> |
|-----------------------|-------------------------------------|-------------|
| <span data-ttu-id="95465-125">Lecture automatique</span><span class="sxs-lookup"><span data-stu-id="95465-125">Auto play</span></span>             | <span data-ttu-id="95465-126">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="95465-126">**True** or **False**</span></span>               | <span data-ttu-id="95465-127">Si la valeur est définie sur **Vrai**, la vidéo est automatiquement lue.</span><span class="sxs-lookup"><span data-stu-id="95465-127">When the value is set to **True**, the video is automatically played.</span></span> |
| <span data-ttu-id="95465-128">Sourdine</span><span class="sxs-lookup"><span data-stu-id="95465-128">Mute</span></span>                  | <span data-ttu-id="95465-129">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="95465-129">**True** or **False**</span></span>               | <span data-ttu-id="95465-130">Si la valeur est définie sur **Vrai**, l'audio est automatiquement mis en sourdine.</span><span class="sxs-lookup"><span data-stu-id="95465-130">When the value is set to **True**, the audio is muted.</span></span> <span data-ttu-id="95465-131">Pour ce lecteur, la valeur par défaut est **Faux**.</span><span class="sxs-lookup"><span data-stu-id="95465-131">For this player, the default value is **False**.</span></span> <span data-ttu-id="95465-132">Dans le navigateur Chrome, les vidéos en lecture automatique sont mises en sourdine par défaut, et l'audio est joué si l'utilisateur lit manuellement le vidéo.</span><span class="sxs-lookup"><span data-stu-id="95465-132">In the Chrome browser, autoplay videos are muted by default, and the audio is played only if the user manually plays the video.</span></span> |
| <span data-ttu-id="95465-133">Boucle</span><span class="sxs-lookup"><span data-stu-id="95465-133">Loop</span></span>                  | <span data-ttu-id="95465-134">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="95465-134">**True** or **False**</span></span>               | <span data-ttu-id="95465-135">Si la valeur est définie sur **Vrai**, la vidéo est répétée en boucle.</span><span class="sxs-lookup"><span data-stu-id="95465-135">When the value is set to **True**, the video is repeated in a loop.</span></span> |
| <span data-ttu-id="95465-136">Supports</span><span class="sxs-lookup"><span data-stu-id="95465-136">Media</span></span>                 | <span data-ttu-id="95465-137">Chemin d'accès et nom du fichier vidéo</span><span class="sxs-lookup"><span data-stu-id="95465-137">Video file path and name</span></span> | <span data-ttu-id="95465-138">Fichier vidéo lu dans le lecteur vidéo.</span><span class="sxs-lookup"><span data-stu-id="95465-138">The video file that is played in the video player.</span></span> |
| <span data-ttu-id="95465-139">Lecture plein écran</span><span class="sxs-lookup"><span data-stu-id="95465-139">Play fullscreen</span></span>       | <span data-ttu-id="95465-140">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="95465-140">**True** or **False**</span></span>               | <span data-ttu-id="95465-141">Si la valeur est définie sur **Vrai**, la vidéo est lue en mode plein écran.</span><span class="sxs-lookup"><span data-stu-id="95465-141">When the value is set to **True**, the video is played in full-screen mode.</span></span> |
| <span data-ttu-id="95465-142">Activer le déclencheur de pause</span><span class="sxs-lookup"><span data-stu-id="95465-142">Play pause trigger</span></span>    | <span data-ttu-id="95465-143">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="95465-143">**True** or **False**</span></span>               | <span data-ttu-id="95465-144">Si la valeur est définie sur **Vrai**, un bouton lecture/pause s'affiche dans la vidéo.</span><span class="sxs-lookup"><span data-stu-id="95465-144">When the value is set to **True**, a play/pause button is shown on the video.</span></span> |
| <span data-ttu-id="95465-145">Contrôles du lecteur vidéo</span><span class="sxs-lookup"><span data-stu-id="95465-145">Video player controls</span></span> | <span data-ttu-id="95465-146">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="95465-146">**True** or **False**</span></span>               | <span data-ttu-id="95465-147">Si la valeur est définie sur **Vrai**, tous les contrôles du lecteur vidéo sont affichés.</span><span class="sxs-lookup"><span data-stu-id="95465-147">When the value is set to **True**, all video player controls are shown.</span></span> <span data-ttu-id="95465-148">Ceux-ci incluent les boutons de lecture et de pause, un indicateur de progression et des options de sous-titres codés.</span><span class="sxs-lookup"><span data-stu-id="95465-148">These controls include play and pause buttons, a progress indicator, and closed caption options.</span></span> |
| <span data-ttu-id="95465-149">Masquer l’affiche</span><span class="sxs-lookup"><span data-stu-id="95465-149">Hide poster image</span></span>     | <span data-ttu-id="95465-150">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="95465-150">**True** or **False**</span></span>               | <span data-ttu-id="95465-151">Une vidéo peut avoir un contour de poster.</span><span class="sxs-lookup"><span data-stu-id="95465-151">A video can have a poster frame.</span></span> <span data-ttu-id="95465-152">Lorsque la valeur de cette propriété est définie sur **Vrai**, le cadre du poster est masqué.</span><span class="sxs-lookup"><span data-stu-id="95465-152">When the value of this property is set to **True**, the poster frame is hidden.</span></span> |
| <span data-ttu-id="95465-153">Niveau du masque</span><span class="sxs-lookup"><span data-stu-id="95465-153">Mask level</span></span>            | <span data-ttu-id="95465-154">Nombre de **0** à **100**</span><span class="sxs-lookup"><span data-stu-id="95465-154">A number from **0** through **100**</span></span> | <span data-ttu-id="95465-155">Masque qui est appliqué à la vidéo pour le style.</span><span class="sxs-lookup"><span data-stu-id="95465-155">The mask that is applied to the video for styling.</span></span> |

## <a name="add-a-video-player-module-to-a-page"></a><span data-ttu-id="95465-156">Ajouter un module de lecture vidéo à une page</span><span class="sxs-lookup"><span data-stu-id="95465-156">Add a video player module to a page</span></span>

> [!NOTE] 
> <span data-ttu-id="95465-157">Avant de créer un module de lecteur vidéo, vous devez d'abord télécharger une vidéo dans la bibliothèque multimédia.</span><span class="sxs-lookup"><span data-stu-id="95465-157">Before you create a video player module, you must first upload a video to the Media Library.</span></span>

<span data-ttu-id="95465-158">Pour ajouter un module de lecteur vidéo à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="95465-158">To add a video player module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="95465-159">Créez un modèle de page nommé **modèle de lecteur vidéo**.</span><span class="sxs-lookup"><span data-stu-id="95465-159">Create a page template that is named **video player template**.</span></span>
1. <span data-ttu-id="95465-160">À l'emplacement **Principal** de la page par défaut, ajoutez un module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="95465-160">In the **Main** slot of the default page, add a container module.</span></span>
1. <span data-ttu-id="95465-161">Dans le module de conteneur, ajoutez le lecteur vidéo et les modules de lecteur de vidéo d'ambiance.</span><span class="sxs-lookup"><span data-stu-id="95465-161">In the container module, add video player and ambient video player modules.</span></span>
1. <span data-ttu-id="95465-162">Terminez la modification du modèle et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="95465-162">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="95465-163">Utilisez le modèle de lecteur vidéo que vous avez créé pour générer une page qui s'appelle **page Lecteur vidéo**.</span><span class="sxs-lookup"><span data-stu-id="95465-163">Use the video player template that you created to create a page that is named **video player page**.</span></span>
1. <span data-ttu-id="95465-164">À l'emplacement **Principal** de la nouvelle page, ajoutez un module de lecteur de vidéo.</span><span class="sxs-lookup"><span data-stu-id="95465-164">In the **Main** slot of the new page, add a video player module.</span></span>
1. <span data-ttu-id="95465-165">Dans le volet des propriétés du module lecteur vidéo, sélectionnez **Ajouter une vidéo**.</span><span class="sxs-lookup"><span data-stu-id="95465-165">In the property pane for the video player module, select **Add a video**.</span></span>
1. <span data-ttu-id="95465-166">Dans la boîte de dialogue **Sélecteur multimédia**, sélectionnez une vidéo, puis sélectionnez **Importer un nouvel élément multimédia**.</span><span class="sxs-lookup"><span data-stu-id="95465-166">In the **Media Picker** dialog box, select a video, and then select **Upload new media item**.</span></span>
1. <span data-ttu-id="95465-167">Enregistrez et affichez un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="95465-167">Save and preview the page.</span></span> <span data-ttu-id="95465-168">Vous devez voir le module vidéo sur la page.</span><span class="sxs-lookup"><span data-stu-id="95465-168">You should see the video module on the page.</span></span> <span data-ttu-id="95465-169">Vous pouvez modifier des paramètres supplémentaires pour personnaliser le comportement du module.</span><span class="sxs-lookup"><span data-stu-id="95465-169">You can change additional settings to customize the behavior of the module.</span></span>
1. <span data-ttu-id="95465-170">Terminez la modification de la page et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="95465-170">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="95465-171">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="95465-171">Additional resources</span></span>

[<span data-ttu-id="95465-172">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="95465-172">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="95465-173">Module de bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="95465-173">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="95465-174">Module de carrousel</span><span class="sxs-lookup"><span data-stu-id="95465-174">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="95465-175">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="95465-175">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="95465-176">Module de bloc de contenu</span><span class="sxs-lookup"><span data-stu-id="95465-176">Content block module</span></span>](add-hero-module.md)
