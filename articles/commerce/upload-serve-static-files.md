---
title: Télécharger et diffuser des fichiers statiques
description: Cette rubrique décrit comment charger un fichier statique dans le générateur de site Microsoft Dynamics 365 Commerce et comment créer une URL et un nom de fichier personnalisés pouvant être utilisés pour demander ce fichier.
author: StuHarg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: aba9dde2ed9d5fa09e92fcdd784a53f208930eda
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211017"
---
# <a name="upload-and-serve-static-files"></a><span data-ttu-id="adabf-103">Télécharger et diffuser des fichiers statiques</span><span class="sxs-lookup"><span data-stu-id="adabf-103">Upload and serve static files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="adabf-104">Cette rubrique décrit comment charger un fichier statique dans le générateur de site Microsoft Dynamics 365 Commerce et comment créer une URL et un nom de fichier personnalisés pouvant être utilisés pour demander ce fichier.</span><span class="sxs-lookup"><span data-stu-id="adabf-104">This topic describes how to upload a static file into Microsoft Dynamics 365 Commerce site builder, and how to create a custom URL and file name that can be used to request that file.</span></span>

<span data-ttu-id="adabf-105">Certains connecteurs tiers nécessitent qu'un fichier soit hébergé et diffusé à partir du site d'e-commerce.</span><span class="sxs-lookup"><span data-stu-id="adabf-105">Some third-party connectors require that a file be hosted and served from the e-commerce site.</span></span> <span data-ttu-id="adabf-106">Ces connecteurs s'attendent à ce que le fichier soit renvoyé par des requêtes adressées à un chemin d'URL de rappel et à un nom de fichier spécifiques.</span><span class="sxs-lookup"><span data-stu-id="adabf-106">These connectors expect that the file will be returned by requests to a specific callback URL path and file name.</span></span> <span data-ttu-id="adabf-107">Par conséquent, cette rubrique explique comment charger et diffuser un fichier statique qui a une URL et un nom de fichier définissables par l'utilisateur sur un site d'e-commerce Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="adabf-107">Therefore, this topic explains how to upload and serve a static file that has a user-definable URL and file name on a Dynamics 365 Commerce e-commerce site.</span></span>

## <a name="create-a-site-url-that-returns-a-static-file"></a><span data-ttu-id="adabf-108">Créer une URL de site qui renvoie un fichier statique</span><span class="sxs-lookup"><span data-stu-id="adabf-108">Create a site URL that returns a static file</span></span>

<span data-ttu-id="adabf-109">Pour créer une URL de site qui renvoie un fichier statique dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="adabf-109">To create a site URL that returns a static file in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="adabf-110">Accédez à la médiathèque de votre site et chargez le fichier qui doit être servi par les requêtes à l'URL que vous définirez.</span><span class="sxs-lookup"><span data-stu-id="adabf-110">Go to your site's Media library, and upload the file that should be served by requests to the URL that you will define.</span></span> <span data-ttu-id="adabf-111">Si vous avez déjà chargé le fichier, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="adabf-111">If you've already uploaded the file, you can skip this step.</span></span>
1. <span data-ttu-id="adabf-112">Aller à **URL** pour votre site.</span><span class="sxs-lookup"><span data-stu-id="adabf-112">Go to **URLs** for your site.</span></span>
1. <span data-ttu-id="adabf-113">Sélectionnez **Nouveau \> Nouvelle URL**.</span><span class="sxs-lookup"><span data-stu-id="adabf-113">Select **New \> New URL**.</span></span>
1. <span data-ttu-id="adabf-114">Dans la boîte de dialogue **Nouvelle URL**, sélectionnez **Élément de bibliothèque multimédia**.</span><span class="sxs-lookup"><span data-stu-id="adabf-114">In the **New URL** dialog box, select **Media library asset**.</span></span>
1. <span data-ttu-id="adabf-115">Dans le champ **Chemin de l'URL**, entrez le chemin de l'URL.</span><span class="sxs-lookup"><span data-stu-id="adabf-115">In the **URL path** field, enter the URL path.</span></span> <span data-ttu-id="adabf-116">Incluez le nom du fichier dans le chemin.</span><span class="sxs-lookup"><span data-stu-id="adabf-116">Include the file name in the path.</span></span>
1. <span data-ttu-id="adabf-117">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="adabf-117">Select **Next**.</span></span> <span data-ttu-id="adabf-118">La médiathèque s'ouvre et affiche tous les éléments multimédias de type **document** qui ont été chargés.</span><span class="sxs-lookup"><span data-stu-id="adabf-118">The Media library is opened and shows all media assets of the **document** type that have been uploaded.</span></span>
1. <span data-ttu-id="adabf-119">Sélectionnez le fichier qui doit être servi pour les demandes à l'URL que vous avez définie à l'étape 5.</span><span class="sxs-lookup"><span data-stu-id="adabf-119">Select the file that should be served for requests to the URL that you defined in step 5.</span></span>
1. <span data-ttu-id="adabf-120">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="adabf-120">Select **Save**.</span></span>

<span data-ttu-id="adabf-121">À ce stade, l'URL créée est dans un état de brouillon.</span><span class="sxs-lookup"><span data-stu-id="adabf-121">At this point, the URL that you created is in a draft state.</span></span> <span data-ttu-id="adabf-122">Le fichier vers lequel pointe l'URL ne sera pas renvoyé tant que vous n'aurez pas publié l'URL.</span><span class="sxs-lookup"><span data-stu-id="adabf-122">The file that the URL points to won't be returned until you publish the URL.</span></span> <span data-ttu-id="adabf-123">Avant de publier l'URL, vous pouvez valider qu'elle renvoie les données correctes.</span><span class="sxs-lookup"><span data-stu-id="adabf-123">Before you publish the URL, you can validate that it returns the correct data.</span></span>

## <a name="validate-and-publish-a-url"></a><span data-ttu-id="adabf-124">Validation et publication d'une URL</span><span class="sxs-lookup"><span data-stu-id="adabf-124">Validate and publish a URL</span></span>

<span data-ttu-id="adabf-125">Pour valider une URL avant de la oublier, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="adabf-125">To validate an URL before you publish it, follow these steps.</span></span>

1. <span data-ttu-id="adabf-126">Aller à **URL** pour votre site et sélectionnez l'URL à prévisualiser.</span><span class="sxs-lookup"><span data-stu-id="adabf-126">Go to **URLs** for your site, and select the URL to preview.</span></span>
2. <span data-ttu-id="adabf-127">Dans le volet des propriétés à droite, sous le bouton **Modifier**, sélectionnez le lien URL correct.</span><span class="sxs-lookup"><span data-stu-id="adabf-127">In the properties pane on the right, below the **Edit** button, select the correct URL link.</span></span> <span data-ttu-id="adabf-128">Une nouvelle fenêtre de navigateur s'ouvre et vous devriez recevoir une erreur 404.</span><span class="sxs-lookup"><span data-stu-id="adabf-128">A new browser window is opened, and you should receive a 404 error.</span></span>
3. <span data-ttu-id="adabf-129">Ajouter la chaîne de requête **?preview=inprogress** à l'URL (par exemple, `https://yoursite.com/callback.html?preview=inprogress`) et rechargez la page.</span><span class="sxs-lookup"><span data-stu-id="adabf-129">Append the **?preview=inprogress** query string to the URL (for example, `https://yoursite.com/callback.html?preview=inprogress`), and reload the page.</span></span> <span data-ttu-id="adabf-130">Le fichier que vous avez chargé dans la médiathèque doit être renvoyé dans la réponse.</span><span class="sxs-lookup"><span data-stu-id="adabf-130">The file that you uploaded to the Media library should be returned in the response.</span></span>

<span data-ttu-id="adabf-131">Après avoir validé l'URL, vous pouvez la publier.</span><span class="sxs-lookup"><span data-stu-id="adabf-131">After you've validated the URL, you can publish it.</span></span>

1. <span data-ttu-id="adabf-132">Aller à **URL** pour votre site et sélectionnez l'URL.</span><span class="sxs-lookup"><span data-stu-id="adabf-132">Go to **URLs** for your site, and select the URL.</span></span>
2. <span data-ttu-id="adabf-133">Sélectionnez **Publier** dans la barre de commande.</span><span class="sxs-lookup"><span data-stu-id="adabf-133">Select **Publish** on the command bar.</span></span>

## <a name="update-the-file-that-a-url-points-to"></a><span data-ttu-id="adabf-134">Mettre à jour le fichier vers lequel pointe une URL</span><span class="sxs-lookup"><span data-stu-id="adabf-134">Update the file that a URL points to</span></span>

<span data-ttu-id="adabf-135">Une fois l'URL publiée, vous pouvez la mettre à jour afin qu'elle pointe vers un autre fichier.</span><span class="sxs-lookup"><span data-stu-id="adabf-135">After a URL is published, you can update it so that it points to a different file.</span></span> <span data-ttu-id="adabf-136">Vous pouvez également mettre à jour l'URL afin qu'elle pointe vers un autre type de ressource, comme décrit dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="adabf-136">Alternatively, you can update the URL so that it points to a different the type of resource, as described in the next section.</span></span> <span data-ttu-id="adabf-137">Par exemple, vous pouvez pointer l'URL vers une page interne ou une redirection.</span><span class="sxs-lookup"><span data-stu-id="adabf-137">For example, you can point the URL to an internal page or a redirect.</span></span>

<span data-ttu-id="adabf-138">Pour mettre à jour le fichier vers lequel pointe une URL, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="adabf-138">To update the file that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="adabf-139">Aller à **URL** pour votre site et sélectionnez l'URL à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="adabf-139">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="adabf-140">Dans le volet de propriétés de droite, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="adabf-140">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="adabf-141">Sous **Attribution d'URL**, sélectionnez la zone **Étape 2**, puis sélectionnez un nouveau document dans la bibliothèque multimédia.</span><span class="sxs-lookup"><span data-stu-id="adabf-141">Under **URL assignment**, select the **Step 2** box, and then select a new document from the Media library.</span></span>
1. <span data-ttu-id="adabf-142">Sélectionnez **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="adabf-142">Select **Apply**.</span></span>

## <a name="update-the-asset-type-that-a-url-points-to"></a><span data-ttu-id="adabf-143">Mettre à jour le type d'actif vers lequel pointe une URL</span><span class="sxs-lookup"><span data-stu-id="adabf-143">Update the asset type that a URL points to</span></span>

<span data-ttu-id="adabf-144">Vous pouvez également mettre à jour une URL afin qu'elle pointe vers un autre type d'actif (ressource), tel qu'une page interne ou une redirection.</span><span class="sxs-lookup"><span data-stu-id="adabf-144">You can also update a URL so that it points to a different type of asset (resource), such as an internal page or a redirect.</span></span>

<span data-ttu-id="adabf-145">Pour mettre à jour le type d'actif vers lequel pointe une URL, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="adabf-145">To update the asset type that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="adabf-146">Aller à **URL** pour votre site et sélectionnez l'URL à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="adabf-146">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="adabf-147">Dans le volet de propriétés de droite, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="adabf-147">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="adabf-148">Sous **Attribution d'URL**, sous **Étape 1**, sélectionnez un autre type d'actif.</span><span class="sxs-lookup"><span data-stu-id="adabf-148">Under **URL assignment**, under **Step 1**, select a different asset type.</span></span>
1. <span data-ttu-id="adabf-149">Sélectionnez la zone **Étape 2**, puis sélectionnez le nouvel actif.</span><span class="sxs-lookup"><span data-stu-id="adabf-149">Select the **Step 2** box, and then select the new asset.</span></span>
1. <span data-ttu-id="adabf-150">Sélectionnez **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="adabf-150">Select **Apply**.</span></span>

## <a name="change-the-url-path"></a><span data-ttu-id="adabf-151">Changer le chemin de l'URL</span><span class="sxs-lookup"><span data-stu-id="adabf-151">Change the URL path</span></span>

<span data-ttu-id="adabf-152">Une fois l'URL créée, son chemin ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="adabf-152">After a URL is created, its path can't be changed.</span></span> <span data-ttu-id="adabf-153">Si vous devez modifier le chemin d'URL qui sert un fichier ou tout autre type de ressource, vous devez créer une URL, la mapper au fichier existant ou à une autre ressource, puis annuler la publication et supprimer l'ancienne URL.</span><span class="sxs-lookup"><span data-stu-id="adabf-153">If you must change the URL path that serves a file or any other type of resource, you have to create a new URL, map it to the existing file or other resource, and then unpublish and delete the old URL.</span></span>

<span data-ttu-id="adabf-154">Pour modifier le chemin de l'URL, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="adabf-154">To change the URL path, follow these steps.</span></span>

1. <span data-ttu-id="adabf-155">Pour créer une URL et la mapper au fichier existant ou à une autre ressource, suivez les instructions de la section précédente [Créer une URL de site qui renvoie un fichier statique](#create-a-site-url-that-returns-a-static-file) dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="adabf-155">To create a new URL and map it to the existing file or another resource, follow the instructions in the [Create a site URL that returns a static file](#create-a-site-url-that-returns-a-static-file) section earlier in this topic.</span></span>
1. <span data-ttu-id="adabf-156">Sélectionnez la nouvelle URL, puis sélectionnez **Publier** sur la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="adabf-156">Select the new URL, and select **Publish** on the command bar.</span></span> <span data-ttu-id="adabf-157">La nouvelle URL est publiée.</span><span class="sxs-lookup"><span data-stu-id="adabf-157">The new URL is published.</span></span>
1. <span data-ttu-id="adabf-158">Pour annuler la publication de l'ancienne URL, sélectionnez-la, puis sélectionnez **Annuler la publication** sur la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="adabf-158">To unpublish the old URL, select it, and then select **Unpublish** on the command bar.</span></span> <span data-ttu-id="adabf-159">Vous pouvez à présent supprimer l'ancienne URL si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="adabf-159">You can now delete the old URL if you want.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="adabf-160">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="adabf-160">Additional resources</span></span>

[<span data-ttu-id="adabf-161">Vue d’ensemble de la gestion des actifs numériques</span><span class="sxs-lookup"><span data-stu-id="adabf-161">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="adabf-162">Importer des images</span><span class="sxs-lookup"><span data-stu-id="adabf-162">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="adabf-163">Télécharger des vidéos</span><span class="sxs-lookup"><span data-stu-id="adabf-163">Upload videos</span></span>](dam-upload-video.md)

[<span data-ttu-id="adabf-164">Télécharger des fichiers autres que des images et des vidéos</span><span class="sxs-lookup"><span data-stu-id="adabf-164">Upload files other than images and videos</span></span>](dam-upload-files.md)

[<span data-ttu-id="adabf-165">Rogner les images</span><span class="sxs-lookup"><span data-stu-id="adabf-165">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="adabf-166">Personnaliser les points focaux de l’image</span><span class="sxs-lookup"><span data-stu-id="adabf-166">Customize image focal points</span></span>](dam-custom-focal-point.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]