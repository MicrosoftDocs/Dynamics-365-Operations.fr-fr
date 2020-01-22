---
title: Modifier une page de site existante
description: Cette rubrique décrit comment ajouter une page existante du site dans Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 50373d3681e269bf6164b2a425bbafebdd93d64f
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945695"
---
# <a name="modify-an-existing-site-page"></a><span data-ttu-id="464c6-103">Modifier une page de site existante</span><span class="sxs-lookup"><span data-stu-id="464c6-103">Modify an existing site page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="464c6-104">Cette rubrique décrit comment ajouter une page existante du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="464c6-104">This topic describes how to modify an existing site page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="464c6-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="464c6-105">Overview</span></span>

<span data-ttu-id="464c6-106">Si vous devez modifier une page, la première étape consiste à l'ouvrir dans l'éditeur de page.</span><span class="sxs-lookup"><span data-stu-id="464c6-106">When you must modify a page, the first step is to open it in the page editor.</span></span> <span data-ttu-id="464c6-107">Aller au site qui contient la page, puis, dans la liste des pages, recherchez la page que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="464c6-107">Go to the site that contains your page, and then, in the list of pages, find the page that you want.</span></span> <span data-ttu-id="464c6-108">Si vous ne la trouvez pas, vous pouvez utiliser la fonctionnalité de recherche enrichie de l'outil de création.</span><span class="sxs-lookup"><span data-stu-id="464c6-108">If you can't find the page, you can use the authoring tool's rich search functionality.</span></span> <span data-ttu-id="464c6-109">Entrez le nom exact de page, ou tapez les premières lettres suivies d'un astérisque (\*).</span><span class="sxs-lookup"><span data-stu-id="464c6-109">Either type the exact page name, or type the first few letters of it and then an asterisk (\*).</span></span> <span data-ttu-id="464c6-110">Une liste filtrée des pages s'affiche.</span><span class="sxs-lookup"><span data-stu-id="464c6-110">A filtered list of pages appears.</span></span> <span data-ttu-id="464c6-111">Vous pouvez utiliser cette liste pour rechercher la page de votre choix.</span><span class="sxs-lookup"><span data-stu-id="464c6-111">You can use this list to find the page that you want.</span></span> <span data-ttu-id="464c6-112">Après avoir trouvé la page appropriée, sélectionnez le nom de page pour ouvrir la page dans l'éditeur de page.</span><span class="sxs-lookup"><span data-stu-id="464c6-112">After you find the correct page, select the page name to open the page in the page editor.</span></span>

> [!TIP]
> <span data-ttu-id="464c6-113">Si votre page est visible dans le contrôleur de page, vous pouvez la sélectionner et l'archiver avant de l'ouvrir dans l'éditeur de page.</span><span class="sxs-lookup"><span data-stu-id="464c6-113">If your page is visible in the page inspector, you can select it and check it out before you open it in the page editor.</span></span> <span data-ttu-id="464c6-114">De cette manière, vous pouvez vérifier les pages simultanément.</span><span class="sxs-lookup"><span data-stu-id="464c6-114">In this way, you can check out multiple pages at the same time.</span></span>

<span data-ttu-id="464c6-115">Une fois la page ouverte dans l'éditeur de page, vous devez vous assurer qu'elle extraite pour vous.</span><span class="sxs-lookup"><span data-stu-id="464c6-115">After the page is open in the page editor, you must make sure that it's checked out to you.</span></span> <span data-ttu-id="464c6-116">La barre de commande dans l'outil de création est dynamique, contextuelle, et sensible à l'état.</span><span class="sxs-lookup"><span data-stu-id="464c6-116">The command bar in the authoring tool is dynamic, context-sensitive, and state-sensitive.</span></span> <span data-ttu-id="464c6-117">Par conséquent, elle n'affiche que les actions que vous pouvez actuellement exécuter sur la page.</span><span class="sxs-lookup"><span data-stu-id="464c6-117">Therefore, it shows only the actions that you can curently perform on the page.</span></span> <span data-ttu-id="464c6-118">Par exemple, si la page n'est pas extraite pour vous, les boutons **Enregistrer** et **Archiver** n'apparaissent pas dans la barre de commande.</span><span class="sxs-lookup"><span data-stu-id="464c6-118">For example, if the page isn't checked out to you, the **Save** and **Check in** buttons don't appear on the command bar.</span></span> <span data-ttu-id="464c6-119">L'état de la page est également affiché à droite de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="464c6-119">The state of the page is also shown on the right side of the window.</span></span>

<span data-ttu-id="464c6-120">Si la page n'est pas déjà extraite pour vous, sélectionnez **Extraire** dans la barre de commande.</span><span class="sxs-lookup"><span data-stu-id="464c6-120">If the page isn't already checked out to you, select **Check out** on the command bar.</span></span> <span data-ttu-id="464c6-121">La barre de commande change pour refléter le nouvel état de la page.</span><span class="sxs-lookup"><span data-stu-id="464c6-121">The command bar changes to reflect the new state of the page.</span></span> <span data-ttu-id="464c6-122">Vous recevez également une notification indiquant que la page a été extraite pour vous.</span><span class="sxs-lookup"><span data-stu-id="464c6-122">You also receive a notification that states that the page was checked out to you.</span></span>

<span data-ttu-id="464c6-123">L'étape suivante consiste à apporter vos modifications.</span><span class="sxs-lookup"><span data-stu-id="464c6-123">The next step is to make your actual changes.</span></span> <span data-ttu-id="464c6-124">Souvent, vous allez utiliser l'arborescence de contour de page à gauche pour rechercher et sélectionner le module à modifier, puis apporter des modifications dans le volet de propriétés à droite.</span><span class="sxs-lookup"><span data-stu-id="464c6-124">Often, you will use the page outline tree on the left to find and select the module that you want to change, and then make changes in the properties pane on the right.</span></span> 

<span data-ttu-id="464c6-125">Toutefois, la modification peut impliquer parfois d'ajouter ou de supprimer des modèles ou des fragments.</span><span class="sxs-lookup"><span data-stu-id="464c6-125">However, your change might sometimes involve adding or removing models or fragments.</span></span> <span data-ttu-id="464c6-126">Pour ajouter un fragment ou un module, utilisez l'arborescence de contour de page pour rechercher l'emplacement auquel vous souhaitez ajouter le module ou le fragment, puis sélectionnez le bouton représentant des points de suspension (**...**) pour cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="464c6-126">To add a fragment or module, use the page outline tree to find the slot that you want to add the module or fragment to, and then select the ellipsis button (**...**) for that slot.</span></span> <span data-ttu-id="464c6-127">Un menu apparaît qui inclut des commandes pour ajouter un module ou un fragment.</span><span class="sxs-lookup"><span data-stu-id="464c6-127">A menu appears that includes commands for adding a module or fragment.</span></span> <span data-ttu-id="464c6-128">Pour supprimer un module ou un fragment, recherchez et sélectionnez-le dans l'arborescence de contour de page, sélectionnez le bouton représentant des points de suspension, puis sélectionnez la commande pour supprimer le module ou le fragment.</span><span class="sxs-lookup"><span data-stu-id="464c6-128">To remove a module or fragment, find and select it in the page outline tree, select the ellipsis button, and then select the command to delete the module or fragment.</span></span>

> [!TIP]
> <span data-ttu-id="464c6-129">Vous pouvez également afficher et de modifier les propriétés d'un module qui est visible dans l'aperçu « Tel écrit, tel écran » en le sélectionnant directement.</span><span class="sxs-lookup"><span data-stu-id="464c6-129">You can also view and edit the properties for any module that is visible in the "what you see is what you get" (WYSIWYG) preview by selecting it directly.</span></span>

<span data-ttu-id="464c6-130">Après avoir terminé d'apporter vos modifications et prévisualisé leurs effets, vous devez archiver la page en sélectionnant **Archiver** dans la barre de commande.</span><span class="sxs-lookup"><span data-stu-id="464c6-130">After you've finished making your changes and previewing their effect, you should check in the page by selecting **Check in** on the command bar.</span></span> 

<span data-ttu-id="464c6-131">Pour envoyer vos modifications immédiatement, sélectionnez **Publier** dans la barre de commande.</span><span class="sxs-lookup"><span data-stu-id="464c6-131">To publish your changes immediately, select **Publish** on the command bar.</span></span> <span data-ttu-id="464c6-132">La dernière version archivée depuis la page que vous avez modifiée est utilisée et devient disponible aux utilisateurs externes qui affichent votre site.</span><span class="sxs-lookup"><span data-stu-id="464c6-132">The latest checked-in version of the page that you modified is published and becomes available to external users who view your site.</span></span> 

## <a name="example-change-the-video-on-the-home-page"></a><span data-ttu-id="464c6-133">Exemple : Modifier la vidéo dans la page d'accueil</span><span class="sxs-lookup"><span data-stu-id="464c6-133">Example: Change the video on the home page</span></span>

<span data-ttu-id="464c6-134">L'exemple suivant montre comment modifier la page d'accueil en modifiant la vidéo qui apparaît dans le module de lecteur de vidéo.</span><span class="sxs-lookup"><span data-stu-id="464c6-134">The following example shows how to modify the home page by changing the video that appears in the video player module.</span></span>

1. <span data-ttu-id="464c6-135">Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).</span><span class="sxs-lookup"><span data-stu-id="464c6-135">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="464c6-136">Dans le volet de navigation sur la gauche, sélectionnez **Pages**.</span><span class="sxs-lookup"><span data-stu-id="464c6-136">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="464c6-137">Recherchez et sélectionnez la page d'accueil pour l'ouvrir dans l'éditeur de page.</span><span class="sxs-lookup"><span data-stu-id="464c6-137">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="464c6-138">Dans la barre de commande, sélectionnez **Extraire**.</span><span class="sxs-lookup"><span data-stu-id="464c6-138">On the command bar, select **Check Out**.</span></span>
1. <span data-ttu-id="464c6-139">Dans le contour de page, sélectionnez l'emplacement **Principal**.</span><span class="sxs-lookup"><span data-stu-id="464c6-139">In the page outline, select the **Main** slot.</span></span>
1. <span data-ttu-id="464c6-140">Sous l'emplacement **Principal**, développez tous les modules de conteneur fluides.</span><span class="sxs-lookup"><span data-stu-id="464c6-140">Under the **Main** slot, expand all the fluid container modules.</span></span>
1. <span data-ttu-id="464c6-141">Recherchez et sélectionnez le module de lecteur vidéo.</span><span class="sxs-lookup"><span data-stu-id="464c6-141">Find and select the video player module.</span></span>
1. <span data-ttu-id="464c6-142">Dans le volet de propriétés de droite, sélectionnez la propriété **vidéo**.</span><span class="sxs-lookup"><span data-stu-id="464c6-142">In the properties pane on the right, select the **video** property.</span></span> <span data-ttu-id="464c6-143">Le sélectionneur d'actif s'affiche.</span><span class="sxs-lookup"><span data-stu-id="464c6-143">The asset picker appears.</span></span>
1. <span data-ttu-id="464c6-144">Dans le sélecteur d'actifs, sélectionnez un actif vidéo disponible, ou sélectionnez **Charger le nouvel actif** pour charger un nouvel actif vidéo.</span><span class="sxs-lookup"><span data-stu-id="464c6-144">In the asset picker, select an available video asset, or select **Upload new asset** to upload a new video asset.</span></span>
1. <span data-ttu-id="464c6-145">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="464c6-145">Select **OK**.</span></span>
1. <span data-ttu-id="464c6-146">Sélectionnez **Enregistrer**, puis sélectionnez **Archiver**.</span><span class="sxs-lookup"><span data-stu-id="464c6-146">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="464c6-147">Dans le champ **Commentaires**, entrez **A modifié la vidéo**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="464c6-147">In the **Comments** field, enter **Changed the video**, and then select **OK**.</span></span>
1. <span data-ttu-id="464c6-148">Sélectionnez **Aperçu** pour afficher un aperçu de la page mise à jour.</span><span class="sxs-lookup"><span data-stu-id="464c6-148">Select **Preview** to preview the updated page.</span></span> <span data-ttu-id="464c6-149">Lorsque vous avez terminé, fermez l'onglet d'aperçu pour revenir à l'outil d'édition.</span><span class="sxs-lookup"><span data-stu-id="464c6-149">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="464c6-150">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="464c6-150">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="464c6-151">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="464c6-151">Additional resources</span></span>

[<span data-ttu-id="464c6-152">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="464c6-152">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="464c6-153">Sélectionner des dispositions de page</span><span class="sxs-lookup"><span data-stu-id="464c6-153">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="464c6-154">Gestion des métadonnées SEO</span><span class="sxs-lookup"><span data-stu-id="464c6-154">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="464c6-155">Enregistrer, afficher un aperçu et publier une page</span><span class="sxs-lookup"><span data-stu-id="464c6-155">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="464c6-156">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="464c6-156">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="464c6-157">Enrichir une page d'arrivée de catégorie</span><span class="sxs-lookup"><span data-stu-id="464c6-157">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="464c6-158">Vérifier l'accessibilité du contenu de la page</span><span class="sxs-lookup"><span data-stu-id="464c6-158">Verify page content accessibility</span></span>](verify-accessibility.md)
