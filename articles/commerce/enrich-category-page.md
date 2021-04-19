---
title: Enrichir une page d’arrivée de catégorie
description: Cette rubrique couvre l’enrichissement des pages de catégorie dans Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5e18439fc0e91619cade33b83b87be0d5c4d1040
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799009"
---
# <a name="enrich-a-category-landing-page"></a><span data-ttu-id="4cec0-103">Enrichir une page d’arrivée de catégorie</span><span class="sxs-lookup"><span data-stu-id="4cec0-103">Enrich a category landing page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4cec0-104">Cette rubrique couvre l’enrichissement des pages de catégorie dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4cec0-104">This topic covers the enrichment of category pages in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4cec0-105">Commerce fournit une page de destination de catégorie par défaut utilisée lorsque les données de catégorie sont affichées.</span><span class="sxs-lookup"><span data-stu-id="4cec0-105">Commerce provides a default category landing page that is used when category data is shown.</span></span> <span data-ttu-id="4cec0-106">Une page de catégorie par défaut contient des éléments nécessaires, comme les raffineurs, le placement de produit catégorisé, les options de tri, une synthèse des choix, et des contrôles pagination.</span><span class="sxs-lookup"><span data-stu-id="4cec0-106">A default category page contains required elements, such as refiners, categorized product placement, sorting options, a choice summary, and pagination controls.</span></span> 

<span data-ttu-id="4cec0-107">Toutefois, au lieu d’utiliser la page par défaut de catégorie, vous pouvez utiliser une page de destination de catégorie « enrichie » avec plus de contenu et autres éléments spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4cec0-107">However, instead of using the default category page, you might want to use an "enriched" category landing page that has more content and more specific elements.</span></span> <span data-ttu-id="4cec0-108">Un enrichissement standard pourrait impliquer d’ajouter du contenu marketing spécifique à la catégorie sur la page de catégorie.</span><span class="sxs-lookup"><span data-stu-id="4cec0-108">A typical enrichment might involve adding category-specific marketing content to the category page.</span></span> <span data-ttu-id="4cec0-109">Ce contenu peut inclure un placement de produit entre les catégories à des fins de vente croisée, listes éditoriales, images, vidéos, et autre texte.</span><span class="sxs-lookup"><span data-stu-id="4cec0-109">This content might include cross-category product placement for cross-sell purposes, editorial lists, images, videos, and other text.</span></span> <span data-ttu-id="4cec0-110">Vous pouvez modifier la page par défaut de catégorie ou définir une autre page de catégorie pour une catégorie spécifique.</span><span class="sxs-lookup"><span data-stu-id="4cec0-110">You can either modify the default category page or define a different category page for a specific category.</span></span>

![Page d’arrivée de catégorie enrichie](./media/CategoryLandingPages.png)

<span data-ttu-id="4cec0-112">Dans le générateur de site Commerce, la page **Produits** inclut une liste de catégories du canal qui sont affectées au site.</span><span class="sxs-lookup"><span data-stu-id="4cec0-112">In Commerce site builder, the **Products** page includes a list of categories from the channel that are assigned to the site.</span></span> <span data-ttu-id="4cec0-113">Si le statut **Enrichi** est sélectionné pour une page de catégorie, cette page de catégorie a été enrichie.</span><span class="sxs-lookup"><span data-stu-id="4cec0-113">If the **Enriched** status is selected for a category page, that category page has been enriched.</span></span> <span data-ttu-id="4cec0-114">Sinon, la page de catégorie et le contenu par défaut sont utilisés pour la catégorie.</span><span class="sxs-lookup"><span data-stu-id="4cec0-114">Otherwise, the default category page and content are used for the category.</span></span> <span data-ttu-id="4cec0-115">Vous pouvez prévisualiser les pages de catégorie enrichies et non enrichies pour une catégorie en sélectionnant le nom de la catégorie.</span><span class="sxs-lookup"><span data-stu-id="4cec0-115">You can preview both the enriched and non-enriched category pages for a category by selecting the category name.</span></span>

<span data-ttu-id="4cec0-116">Pour enrichir une page de catégorie, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="4cec0-116">To enrich a category page, do the following.</span></span>

1. <span data-ttu-id="4cec0-117">Dans la page **Produits**, sélectionnez le nom de la catégorie pour laquelle vous souhaitez enrichir la page de catégorie.</span><span class="sxs-lookup"><span data-stu-id="4cec0-117">On the **Products** page, select the name of the category for which you want to enrich the category page.</span></span> <span data-ttu-id="4cec0-118">La page de catégorie par défaut pour la catégorie sélectionnée est ouverte dans l’éditeur de page.</span><span class="sxs-lookup"><span data-stu-id="4cec0-118">The default category page for the selected category is opened in the page editor.</span></span>
2. <span data-ttu-id="4cec0-119">Sélectionnez **Enrichir la page de catégorie**.</span><span class="sxs-lookup"><span data-stu-id="4cec0-119">Select **Enrich category page**.</span></span>
3. <span data-ttu-id="4cec0-120">Sélectionnez un modèle pour la page de catégorie enrichie.</span><span class="sxs-lookup"><span data-stu-id="4cec0-120">Select a template for the enriched category page.</span></span> <span data-ttu-id="4cec0-121">Si vous n’apportez que de petites modifications, vous pouvez sélectionner la page par défaut de catégorie.</span><span class="sxs-lookup"><span data-stu-id="4cec0-121">If you're making only minor changes, you can select the default category page.</span></span> <span data-ttu-id="4cec0-122">Sinon, vous pouvez sélectionner un modèle spécifique de la page de catégorie.</span><span class="sxs-lookup"><span data-stu-id="4cec0-122">Alternatively, you can select a specific category page template.</span></span> <span data-ttu-id="4cec0-123">Lorsque vous sélectionnez le modèle, l’éditeur de page est ouvert, et le modèle sélectionné permet de créer une page de catégorie pour la catégorie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4cec0-123">When you select the template, the page editor is opened, and the selected template is used to create a new category page for the selected category.</span></span> <span data-ttu-id="4cec0-124">La page est extraite pour vous, et vous pouvez désormais effectuer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="4cec0-124">The page is checked out to you, and you can now make your changes.</span></span>

> [!NOTE]
> <span data-ttu-id="4cec0-125">Les modules qui utilisent des données de spécification de catégorie utilisent les données de votre catégorie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4cec0-125">Modules that use category specification data use the data from your selected category.</span></span> <span data-ttu-id="4cec0-126">Les paramètres du modèle que vous sélectionnez détermine les modifications que vous pouvez apporter.</span><span class="sxs-lookup"><span data-stu-id="4cec0-126">The settings of the template that you select determine the changes that you can make.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4cec0-127">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4cec0-127">Additional resources</span></span>

[<span data-ttu-id="4cec0-128">Modifier une page de site existante</span><span class="sxs-lookup"><span data-stu-id="4cec0-128">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="4cec0-129">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="4cec0-129">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="4cec0-130">Sélectionner des dispositions de page</span><span class="sxs-lookup"><span data-stu-id="4cec0-130">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="4cec0-131">Gestion des métadonnées SEO</span><span class="sxs-lookup"><span data-stu-id="4cec0-131">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="4cec0-132">Enregistrer, afficher un aperçu et publier une page</span><span class="sxs-lookup"><span data-stu-id="4cec0-132">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="4cec0-133">Enrichir une page de produit</span><span class="sxs-lookup"><span data-stu-id="4cec0-133">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="4cec0-134">Vérifier l’accessibilité du contenu de la page</span><span class="sxs-lookup"><span data-stu-id="4cec0-134">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="4cec0-135">Créer des pages e-commerce dynamiques basées sur des paramètres d’URL</span><span class="sxs-lookup"><span data-stu-id="4cec0-135">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
