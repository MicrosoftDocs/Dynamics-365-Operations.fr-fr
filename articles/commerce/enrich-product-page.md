---
title: Enrichir une page de produit
description: Cette rubrique décrit comment enrichir une page de produit dans Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: 12508a80c440894ec6e2073b5e550846480e6c45
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412192"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="e5627-103">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="e5627-103">Enrich a product page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e5627-104">Cette rubrique décrit comment enrichir une page de produit dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e5627-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e5627-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="e5627-105">Overview</span></span>

<span data-ttu-id="e5627-106">Par défaut, votre site utilise une page générique pour afficher les données de produit.</span><span class="sxs-lookup"><span data-stu-id="e5627-106">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="e5627-107">Cette page inclut des informations de base sur le produit et les contrôles qui sont requis pour le vendre.</span><span class="sxs-lookup"><span data-stu-id="e5627-107">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="e5627-108">Toutefois, vous pouvez compléter les informations provenant de l'unité d'échelle commerciale avec des images ou du texte supplémentaire pour un produit spécifique.</span><span class="sxs-lookup"><span data-stu-id="e5627-108">However, you can supplement the information that comes from the Commerce Scale Unit with additional images or text for a specific product.</span></span> <span data-ttu-id="e5627-109">Ce processus est identifié comme un enrichissement de la page de produit.</span><span class="sxs-lookup"><span data-stu-id="e5627-109">This process is known as enriching the product page.</span></span>

<span data-ttu-id="e5627-110">Dans de nombreux cas, vous souhaiterez utiliser du contenu supplémentaire spécifique pour vos produits.</span><span class="sxs-lookup"><span data-stu-id="e5627-110">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="e5627-111">Lorsque vous accédez à **Commerce et vente au détail** dans l'outil de création, vous obtenez une liste des produits du canal affecté au site.</span><span class="sxs-lookup"><span data-stu-id="e5627-111">When you go to **Retail and Commerce** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="e5627-112">Dans cette liste, la colonne **Enrichi** indique si la page de produit pour un produit a été enrichie.</span><span class="sxs-lookup"><span data-stu-id="e5627-112">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="e5627-113">Si une coche apparaît dans la colonne, une page enrichie de produit existe pour le produit.</span><span class="sxs-lookup"><span data-stu-id="e5627-113">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="e5627-114">Si aucun coche ne s'affiche, la page et le contenu par défaut du produit sont utilisés pour le produit.</span><span class="sxs-lookup"><span data-stu-id="e5627-114">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="e5627-115">Vous pouvez prévisualiser les pages de produits enrichies et non enrichies en sélectionnant un nom de produit dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e5627-115">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="e5627-116">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="e5627-116">Enrich a product page</span></span>

<span data-ttu-id="e5627-117">Pour enrichir une page de produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e5627-117">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="e5627-118">Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).</span><span class="sxs-lookup"><span data-stu-id="e5627-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="e5627-119">Dans le volet de navigation sur la gauche, sélectionnez **Produits**.</span><span class="sxs-lookup"><span data-stu-id="e5627-119">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="e5627-120">Sélectionnez tout produit qui n'a pas de page de produit enrichie.</span><span class="sxs-lookup"><span data-stu-id="e5627-120">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="e5627-121">Dans le volet Actions, sélectionnez **Page de produit enrichie**.</span><span class="sxs-lookup"><span data-stu-id="e5627-121">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="e5627-122">Sélectionnez **Modèle PDF**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5627-122">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="e5627-123">Dans l'arborescence d'ensemble de page à gauche, développez l'emplacement **Principal**.</span><span class="sxs-lookup"><span data-stu-id="e5627-123">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="e5627-124">Sélectionnez le bouton représentant des points de suspension (**...**) en regard de l'emplacement **Principale**, et sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="e5627-124">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="e5627-125">Sélectionnez **Conteneur 2**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5627-125">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="e5627-126">Sélectionnez le bouton représentant des points de suspension pour **Conteneur 2**, puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="e5627-126">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="e5627-127">Sélectionnez **Fonctionnalité**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5627-127">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="e5627-128">Dans le volet de propriétés de droite, dans le champ **Texte enrichi**, entrez la description mise à jour du produit.</span><span class="sxs-lookup"><span data-stu-id="e5627-128">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="e5627-129">Dans le champ **En-tête**, entrez le texte d'en-tête, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5627-129">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="e5627-130">Sélectionnez **Enregistrer**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="e5627-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e5627-131">Dans le champ **Commentaires**, entrez **A enrichi un produit**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5627-131">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="e5627-132">Sélectionnez **Aperçu** pour afficher un aperçu de la page de produit enrichie.</span><span class="sxs-lookup"><span data-stu-id="e5627-132">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="e5627-133">Lorsque vous avez terminé, fermez l'onglet d'aperçu pour revenir à l'outil d'édition.</span><span class="sxs-lookup"><span data-stu-id="e5627-133">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="e5627-134">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="e5627-134">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e5627-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e5627-135">Additional resources</span></span>

[<span data-ttu-id="e5627-136">Modifier une page de site existante</span><span class="sxs-lookup"><span data-stu-id="e5627-136">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="e5627-137">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="e5627-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="e5627-138">Sélectionner des dispositions de page</span><span class="sxs-lookup"><span data-stu-id="e5627-138">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="e5627-139">Gestion des métadonnées SEO</span><span class="sxs-lookup"><span data-stu-id="e5627-139">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="e5627-140">Enregistrer, afficher un aperçu et publier une page</span><span class="sxs-lookup"><span data-stu-id="e5627-140">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="e5627-141">Enrichir une page d'arrivée de catégorie</span><span class="sxs-lookup"><span data-stu-id="e5627-141">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="e5627-142">Vérifier l'accessibilité du contenu de la page</span><span class="sxs-lookup"><span data-stu-id="e5627-142">Verify page content accessibility</span></span>](verify-accessibility.md)
