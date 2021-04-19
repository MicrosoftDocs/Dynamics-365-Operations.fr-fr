---
title: Enrichir une page de produit
description: Cette rubrique décrit comment enrichir une page de produit dans Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f6c1a9474ed514426386b1d7b4a72b62129cdb8a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799040"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="d0029-103">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="d0029-103">Enrich a product page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d0029-104">Cette rubrique décrit comment enrichir une page de produit dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d0029-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d0029-105">Par défaut, votre site utilise une page générique pour afficher les données de produit.</span><span class="sxs-lookup"><span data-stu-id="d0029-105">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="d0029-106">Cette page inclut des informations de base sur le produit et les contrôles qui sont requis pour le vendre.</span><span class="sxs-lookup"><span data-stu-id="d0029-106">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="d0029-107">Toutefois, vous pouvez compléter les informations provenant de l’unité d’échelle commerciale avec des images ou du texte supplémentaire pour un produit spécifique.</span><span class="sxs-lookup"><span data-stu-id="d0029-107">However, you can supplement the information that comes from the Commerce Scale Unit with additional images or text for a specific product.</span></span> <span data-ttu-id="d0029-108">Ce processus est identifié comme un enrichissement de la page de produit.</span><span class="sxs-lookup"><span data-stu-id="d0029-108">This process is known as enriching the product page.</span></span>

<span data-ttu-id="d0029-109">Dans de nombreux cas, vous souhaiterez utiliser du contenu supplémentaire spécifique pour vos produits.</span><span class="sxs-lookup"><span data-stu-id="d0029-109">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="d0029-110">Lorsque vous accédez à **Commerce et vente au détail** dans l’outil de création, vous obtenez une liste des produits du canal affecté au site.</span><span class="sxs-lookup"><span data-stu-id="d0029-110">When you go to **Retail and Commerce** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="d0029-111">Dans cette liste, la colonne **Enrichi** indique si la page de produit pour un produit a été enrichie.</span><span class="sxs-lookup"><span data-stu-id="d0029-111">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="d0029-112">Si une coche apparaît dans la colonne, une page enrichie de produit existe pour le produit.</span><span class="sxs-lookup"><span data-stu-id="d0029-112">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="d0029-113">Si aucun coche ne s’affiche, la page et le contenu par défaut du produit sont utilisés pour le produit.</span><span class="sxs-lookup"><span data-stu-id="d0029-113">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="d0029-114">Vous pouvez prévisualiser les pages de produits enrichies et non enrichies en sélectionnant un nom de produit dans la liste.</span><span class="sxs-lookup"><span data-stu-id="d0029-114">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="d0029-115">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="d0029-115">Enrich a product page</span></span>

<span data-ttu-id="d0029-116">Pour enrichir une page de produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d0029-116">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="d0029-117">Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).</span><span class="sxs-lookup"><span data-stu-id="d0029-117">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="d0029-118">Dans le volet de navigation sur la gauche, sélectionnez **Produits**.</span><span class="sxs-lookup"><span data-stu-id="d0029-118">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="d0029-119">Sélectionnez tout produit qui n’a pas de page de produit enrichie.</span><span class="sxs-lookup"><span data-stu-id="d0029-119">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="d0029-120">Dans le volet Actions, sélectionnez **Page de produit enrichie**.</span><span class="sxs-lookup"><span data-stu-id="d0029-120">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="d0029-121">Sélectionnez **Modèle PDF**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0029-121">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="d0029-122">Dans l’arborescence d’ensemble de page à gauche, développez l’emplacement **Principal**.</span><span class="sxs-lookup"><span data-stu-id="d0029-122">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="d0029-123">Sélectionnez le bouton représentant des points de suspension (**...**) en regard de l’emplacement **Principale**, et sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="d0029-123">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="d0029-124">Sélectionnez **Conteneur 2**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0029-124">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="d0029-125">Sélectionnez le bouton représentant des points de suspension pour **Conteneur 2**, puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="d0029-125">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="d0029-126">Sélectionnez **Fonctionnalité**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0029-126">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="d0029-127">Dans le volet de propriétés de droite, dans le champ **Texte enrichi**, entrez la description mise à jour du produit.</span><span class="sxs-lookup"><span data-stu-id="d0029-127">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="d0029-128">Dans le champ **En-tête**, entrez le texte d’en-tête, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0029-128">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="d0029-129">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="d0029-129">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="d0029-130">Dans le champ **Commentaires**, entrez **A enrichi un produit**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0029-130">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="d0029-131">Sélectionnez **Aperçu** pour afficher un aperçu de la page de produit enrichie.</span><span class="sxs-lookup"><span data-stu-id="d0029-131">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="d0029-132">Lorsque vous avez terminé, fermez l’onglet d’aperçu pour revenir à l’outil d’édition.</span><span class="sxs-lookup"><span data-stu-id="d0029-132">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="d0029-133">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="d0029-133">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d0029-134">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d0029-134">Additional resources</span></span>

[<span data-ttu-id="d0029-135">Modifier une page de site existante</span><span class="sxs-lookup"><span data-stu-id="d0029-135">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="d0029-136">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="d0029-136">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="d0029-137">Sélectionner des dispositions de page</span><span class="sxs-lookup"><span data-stu-id="d0029-137">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="d0029-138">Gestion des métadonnées SEO</span><span class="sxs-lookup"><span data-stu-id="d0029-138">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="d0029-139">Enregistrer, afficher un aperçu et publier une page</span><span class="sxs-lookup"><span data-stu-id="d0029-139">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="d0029-140">Enrichir une page d’arrivée de catégorie</span><span class="sxs-lookup"><span data-stu-id="d0029-140">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="d0029-141">Vérifier l’accessibilité du contenu de la page</span><span class="sxs-lookup"><span data-stu-id="d0029-141">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="d0029-142">Créer des pages e-commerce dynamiques basées sur des paramètres d’URL</span><span class="sxs-lookup"><span data-stu-id="d0029-142">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
