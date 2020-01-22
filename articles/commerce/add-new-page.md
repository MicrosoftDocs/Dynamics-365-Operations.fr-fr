---
title: Ajouter une nouvelle page de site
description: Cette rubrique décrit comment ajouter une nouvelle page du site dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 1993e58108ad73aad4adf382bb03ec2e62231add
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945603"
---
# <a name="add-a-new-site-page"></a><span data-ttu-id="6cc01-103">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="6cc01-103">Add a new site page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="6cc01-104">Cette rubrique décrit comment ajouter une nouvelle page du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6cc01-104">This topic describes how to add a new site page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6cc01-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="6cc01-105">Overview</span></span>

<span data-ttu-id="6cc01-106">Après avoir créé des modèles et des fragments pour votre site, l'étape suivante consiste à commencer à créer des pages qui les utilisent.</span><span class="sxs-lookup"><span data-stu-id="6cc01-106">After you've created templates and fragments for your site, the next step is to start to create pages that use them.</span></span> <span data-ttu-id="6cc01-107">Pour démarrer, vous devez sélectionner un modèle ou une disposition, un nom de page, et une URL de page.</span><span class="sxs-lookup"><span data-stu-id="6cc01-107">To get started, you must select a template or layout, a page name, and a page URL.</span></span>

## <a name="template-or-layout"></a><span data-ttu-id="6cc01-108">Modèle ou disposition</span><span class="sxs-lookup"><span data-stu-id="6cc01-108">Template or layout</span></span>

<span data-ttu-id="6cc01-109">Vous pouvez utiliser un modèle ou une disposition pour votre nouvelle page.</span><span class="sxs-lookup"><span data-stu-id="6cc01-109">You can use either a template or a layout for your new page.</span></span> <span data-ttu-id="6cc01-110">Pour plus d'informations, voir [Vue d'ensemble des modèles et des dispositions](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6cc01-110">For more information, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="page-name"></a><span data-ttu-id="6cc01-111">Nom de la page</span><span class="sxs-lookup"><span data-stu-id="6cc01-111">Page name</span></span>

<span data-ttu-id="6cc01-112">Le nom de la page doit être unique à la page.</span><span class="sxs-lookup"><span data-stu-id="6cc01-112">The page name must be unique to your page.</span></span> <span data-ttu-id="6cc01-113">Il doit être descriptif, afin que vous puissiez facilement la trouver et que d'autres personnes sachent pour quoi la page est prévue.</span><span class="sxs-lookup"><span data-stu-id="6cc01-113">It should be descriptive, so that you can easily find it and other people know what the page is intended for.</span></span> <span data-ttu-id="6cc01-114">Choisissez le nom de page avec soin, car il ne peut pas être modifié ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="6cc01-114">Choose the page name carefully, because it can't be changed later.</span></span>

## <a name="page-url"></a><span data-ttu-id="6cc01-115">URL de la page</span><span class="sxs-lookup"><span data-stu-id="6cc01-115">Page URL</span></span>

<span data-ttu-id="6cc01-116">Vous pouvez avoir l'option d'entrer une URL pour votre nouvelle page.</span><span class="sxs-lookup"><span data-stu-id="6cc01-116">You can have the option to enter a URL for your new page.</span></span> <span data-ttu-id="6cc01-117">Lorsque vous créez une page, vous pouvez entrer une chaîne à utiliser pour former une URL complète.</span><span class="sxs-lookup"><span data-stu-id="6cc01-117">When you create a page, you can enter a string that will be used to form a complete URL.</span></span> <span data-ttu-id="6cc01-118">Cette chaîne s'appelle URL relative ou URL slug.</span><span class="sxs-lookup"><span data-stu-id="6cc01-118">This string is known as a relative URL or a URL slug.</span></span> <span data-ttu-id="6cc01-119">Une URL complète est ensuite générée selon le slug d'URL, et la nouvelle page lui est affectée.</span><span class="sxs-lookup"><span data-stu-id="6cc01-119">A complete URL is then generated based on the URL slug, and the new page is assigned to it.</span></span> <span data-ttu-id="6cc01-120">Vous pouvez modifier le slug URL ultérieurement, avant la publication de la page.</span><span class="sxs-lookup"><span data-stu-id="6cc01-120">You can change the URL slug later, before you publish the page.</span></span> <span data-ttu-id="6cc01-121">Pour plus d'informations, voir [Création d'une URL de page](create-page-URL.md).</span><span class="sxs-lookup"><span data-stu-id="6cc01-121">For more information, see [Create a page URL](create-page-URL.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6cc01-122">Dynamics 365 Commerce découple les URL et le contenu.</span><span class="sxs-lookup"><span data-stu-id="6cc01-122">Dynamics 365 Commerce decouples URLs and content.</span></span> <span data-ttu-id="6cc01-123">En d'autres termes, vous pouvez créer une page qui n'est pas associée à une URL, et une URL peut être créée qui n'est pas associé à une page.</span><span class="sxs-lookup"><span data-stu-id="6cc01-123">In other words, a page can be created that isn't associated with an URL, and a URL can be created that isn't associated with a page.</span></span> <span data-ttu-id="6cc01-124">Par conséquent, l'échange de contenu peut être effectuée pour une URL et n'a pas besoin d'interruption, et les redirections sont plus facile à gérer.</span><span class="sxs-lookup"><span data-stu-id="6cc01-124">Therefore, content swapping can be done for a URL and doesn't require downtime, and redirects are easier to manage.</span></span>

## <a name="add-a-new-page"></a><span data-ttu-id="6cc01-125">Ajouter une nouvelle page</span><span class="sxs-lookup"><span data-stu-id="6cc01-125">Add a new page</span></span>

<span data-ttu-id="6cc01-126">Pour ajouter une nouvelle page de site à votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6cc01-126">To add a new site page to your site, follow these steps.</span></span>

1. <span data-ttu-id="6cc01-127">Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).</span><span class="sxs-lookup"><span data-stu-id="6cc01-127">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="6cc01-128">Sélectionnez **Nouvelle page**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-128">Select **New Page**.</span></span>
1. <span data-ttu-id="6cc01-129">Dans la boîte de dialogue **Nouvelle page**, sélectionnez un modèle, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-129">In the **New Page** dialog box, select a template, and then select **OK**.</span></span>
1. <span data-ttu-id="6cc01-130">Dans le champ **Nom de la page**, entrez un nom de page (par exemple, **Ma nouvelle page**).</span><span class="sxs-lookup"><span data-stu-id="6cc01-130">In the **Page Name** field, enter a page name (for example, **My New Page**).</span></span>
1. <span data-ttu-id="6cc01-131">Dans le champ **URL**, entrez une chaîne (slug d'URL) pour terminer l'URL (par exemple, **manouvellepage**).</span><span class="sxs-lookup"><span data-stu-id="6cc01-131">In the **URL** field, enter a string (URL slug) to complete the URL (for example, **mynewpage**).</span></span>
1. <span data-ttu-id="6cc01-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-132">Select **OK**.</span></span> <span data-ttu-id="6cc01-133">L'éditeur de page s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6cc01-133">The page editor appears.</span></span> <span data-ttu-id="6cc01-134">Notez qu'un en-tête ou un pied de page sont automatiquement ajoutés à la page, selon le modèle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="6cc01-134">Notice that a header and a footer are automatically added to the page, based on the template that you selected.</span></span>
1. <span data-ttu-id="6cc01-135">Dans le contour de page, sélectionnez l'emplacement **Principal**, sélectionnez le bouton représentant des points de suspension (**...**), puis le sélectionnez **Ajoutez le module**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-135">In the page outline, select the **Main** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="6cc01-136">Sélectionnez **Conteneur**, puis sélectionnez **OK**</span><span class="sxs-lookup"><span data-stu-id="6cc01-136">Select **Container**, and then select **OK**</span></span>
1. <span data-ttu-id="6cc01-137">Sélectionnez **Conteneur fluide**, sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Ajoutez le module**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-137">Select **Fluid Container**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="6cc01-138">Sélectionnez **Bloc de contenu riche**, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-138">Select **Content Rich block**, and then select **OK**.</span></span>
1. <span data-ttu-id="6cc01-139">Sélectionnez **Bloc de contenu riche**, sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Ajoutez le module**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-139">Select **Content Rich Block**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="6cc01-140">Sélectionnez **Article de bloc de contenu riche**, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-140">Select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="6cc01-141">Dans le volet des propriétés de droite, sélectionnez **Paragraphe**, puis, dans le champ, **Mon texte de test**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-141">In the properties pane on the right, select **Paragraph**, and then, in the field, enter **My test text**.</span></span>
1. <span data-ttu-id="6cc01-142">Sélectionnez **Enregistrer**, puis sélectionnez **Archiver**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-142">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="6cc01-143">Dans le champ **Commentaires**, entrez **Nouvelle page ajoutée**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-143">In the **Comments** field, enter **Added new page**, and then select **OK**.</span></span>
1. <span data-ttu-id="6cc01-144">Sélectionnez **Aperçu** pour prévisualiser votre page avant impression.</span><span class="sxs-lookup"><span data-stu-id="6cc01-144">Select **Preview** to preview your page.</span></span> <span data-ttu-id="6cc01-145">Lorsque vous avez terminé, fermez l'onglet d'aperçu pour revenir à l'outil d'édition.</span><span class="sxs-lookup"><span data-stu-id="6cc01-145">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="6cc01-146">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-146">Select **Publish**.</span></span>
1. <span data-ttu-id="6cc01-147">Dans le chemin de navigation (barres de navigation), sélectionnez **Fabrikam** (ou le nom de votre site).</span><span class="sxs-lookup"><span data-stu-id="6cc01-147">In the navigation path (breadcrumbs), select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="6cc01-148">Dans le volet de navigation sur la gauche, sélectionnez **URL**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-148">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="6cc01-149">Recherchez et sélectionnez votre URL (**manouvellepage**) dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6cc01-149">Find and select your URL (**mynewpage**) in the list.</span></span>
1. <span data-ttu-id="6cc01-150">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="6cc01-150">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6cc01-151">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6cc01-151">Additional resources</span></span>

[<span data-ttu-id="6cc01-152">Modifier une page de site existante</span><span class="sxs-lookup"><span data-stu-id="6cc01-152">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="6cc01-153">Sélectionner des dispositions de page</span><span class="sxs-lookup"><span data-stu-id="6cc01-153">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="6cc01-154">Gestion des métadonnées SEO</span><span class="sxs-lookup"><span data-stu-id="6cc01-154">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="6cc01-155">Enregistrer, afficher un aperçu et publier une page</span><span class="sxs-lookup"><span data-stu-id="6cc01-155">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="6cc01-156">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="6cc01-156">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="6cc01-157">Enrichir une page d'arrivée de catégorie</span><span class="sxs-lookup"><span data-stu-id="6cc01-157">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="6cc01-158">Vérifier l'accessibilité du contenu de la page</span><span class="sxs-lookup"><span data-stu-id="6cc01-158">Verify page content accessibility</span></span>](verify-accessibility.md)