---
title: Enrichir une page de produit
description: Cette rubrique décrit comment enrichir une page de produit dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: ef9e65b2027a41ca152afaf20ac2fb9a69cd9b96
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698140"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="e9216-103">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="e9216-103">Enrich a product page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e9216-104">Cette rubrique décrit comment enrichir une page de produit dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e9216-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e9216-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="e9216-105">Overview</span></span>

<span data-ttu-id="e9216-106">Par défaut, votre site utilise une page générique pour afficher les données de produit.</span><span class="sxs-lookup"><span data-stu-id="e9216-106">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="e9216-107">Cette page inclut des informations de base sur le produit et les contrôles qui sont requis pour le vendre.</span><span class="sxs-lookup"><span data-stu-id="e9216-107">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="e9216-108">Toutefois, vous pouvez compléter les informations provenant du Retail Server avec des images ou du texte supplémentaire pour un produit spécifique.</span><span class="sxs-lookup"><span data-stu-id="e9216-108">However, you can supplement the information that comes from the Retail Server with additional images or text for a specific product.</span></span> <span data-ttu-id="e9216-109">Ce processus est identifié comme un enrichissement de la page de produit.</span><span class="sxs-lookup"><span data-stu-id="e9216-109">This process is known as enriching the product page.</span></span>

<span data-ttu-id="e9216-110">Dans de nombreux cas, vous souhaiterez utiliser du contenu supplémentaire spécifique pour vos produits.</span><span class="sxs-lookup"><span data-stu-id="e9216-110">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="e9216-111">Lorsque vous accédez à **Vente au détail** dans l'outil de création, vous obtenez une liste des produits du canal affecté au site.</span><span class="sxs-lookup"><span data-stu-id="e9216-111">When you go to **Retail** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="e9216-112">Dans cette liste, la colonne **Enrichi** indique si la page de produit pour un produit a été enrichie.</span><span class="sxs-lookup"><span data-stu-id="e9216-112">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="e9216-113">Si une coche apparaît dans la colonne, une page enrichie de produit existe pour le produit.</span><span class="sxs-lookup"><span data-stu-id="e9216-113">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="e9216-114">Si aucun coche ne s'affiche, la page et le contenu par défaut du produit sont utilisés pour le produit.</span><span class="sxs-lookup"><span data-stu-id="e9216-114">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="e9216-115">Vous pouvez prévisualiser les pages de produits enrichies et non enrichies en sélectionnant un nom de produit dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e9216-115">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="e9216-116">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="e9216-116">Enrich a product page</span></span>

<span data-ttu-id="e9216-117">Pour enrichir une page de produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e9216-117">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="e9216-118">Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).</span><span class="sxs-lookup"><span data-stu-id="e9216-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="e9216-119">Dans le volet de navigation sur la gauche, sélectionnez **Produits**.</span><span class="sxs-lookup"><span data-stu-id="e9216-119">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="e9216-120">Sélectionnez tout produit qui n'a pas de page de produit enrichie.</span><span class="sxs-lookup"><span data-stu-id="e9216-120">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="e9216-121">Dans le volet Actions, sélectionnez **Page de produit enrichie**.</span><span class="sxs-lookup"><span data-stu-id="e9216-121">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="e9216-122">Sélectionnez **Modèle PDF**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9216-122">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="e9216-123">Dans l'arborescence d'ensemble de page à gauche, développez l'emplacement **Principal**.</span><span class="sxs-lookup"><span data-stu-id="e9216-123">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="e9216-124">Sélectionnez le bouton représentant des points de suspension (**...**) en regard de l'emplacement **Principale**, et sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="e9216-124">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="e9216-125">Sélectionnez **Conteneur 2**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9216-125">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="e9216-126">Sélectionnez le bouton représentant des points de suspension pour **Conteneur 2**, puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="e9216-126">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="e9216-127">Sélectionnez **Fonctionnalité**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9216-127">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="e9216-128">Dans le volet de propriétés de droite, dans le champ **Texte enrichi**, entrez la description mise à jour du produit.</span><span class="sxs-lookup"><span data-stu-id="e9216-128">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="e9216-129">Dans le champ **En-tête**, entrez le texte d'en-tête, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9216-129">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="e9216-130">Sélectionnez **Enregistrer**, puis sélectionnez **Archiver**.</span><span class="sxs-lookup"><span data-stu-id="e9216-130">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="e9216-131">Dans le champ **Commentaires**, entrez **A enrichi un produit**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9216-131">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="e9216-132">Sélectionnez **Aperçu** pour afficher un aperçu de la page de produit enrichie.</span><span class="sxs-lookup"><span data-stu-id="e9216-132">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="e9216-133">Lorsque vous avez terminé, fermez l'onglet d'aperçu pour revenir à l'outil d'édition.</span><span class="sxs-lookup"><span data-stu-id="e9216-133">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="e9216-134">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="e9216-134">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e9216-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e9216-135">Additional resources</span></span>

[<span data-ttu-id="e9216-136">Modifier une page de site existante</span><span class="sxs-lookup"><span data-stu-id="e9216-136">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="e9216-137">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="e9216-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="e9216-138">Sélectionner des dispositions de page</span><span class="sxs-lookup"><span data-stu-id="e9216-138">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="e9216-139">Gestion des métadonnées SEO</span><span class="sxs-lookup"><span data-stu-id="e9216-139">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="e9216-140">Enregistrer, afficher un aperçu et publier une page</span><span class="sxs-lookup"><span data-stu-id="e9216-140">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="e9216-141">Enrichir une page d'arrivée de catégorie</span><span class="sxs-lookup"><span data-stu-id="e9216-141">Enrich a category landing page</span></span>](enrich-category-page.md)

