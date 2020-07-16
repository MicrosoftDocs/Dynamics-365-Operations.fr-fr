---
title: Vue d'ensemble de la page d'arrivée de catégories et de la page des résultats de la recherche par défaut
description: Cette rubrique fournit une vue d'ensemble de la page d'arrivée de catégories et la page des résultats de la recherche par défaut dans Dynamics 365 Commerce.
author: ashishmsft
manager: annbe
ms.date: 06/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e85449c10fa4a768a144ce423a77bd1fc2c94352
ms.sourcegitcommit: ce397c2759f642c595e30fef58a770b50360b2bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527466"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a><span data-ttu-id="da624-103">Vue d'ensemble de la page d'arrivée de catégories et de la page des résultats de la recherche par défaut</span><span class="sxs-lookup"><span data-stu-id="da624-103">Default category landing page and search results page overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="da624-104">Cette rubrique fournit une vue d'ensemble de la page d'arrivée de catégories et la page des résultats de la recherche par défaut dans Microsoft Dynamics 365 Commerce e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="da624-104">This topic provides an overview of the default category landing page and search results page in Microsoft Dynamics 365 Commerce e-Commerce.</span></span>

## <a name="default-category-landing-page"></a><span data-ttu-id="da624-105">Page d'arrivée de catégorie par défaut</span><span class="sxs-lookup"><span data-stu-id="da624-105">Default category landing page</span></span>

<span data-ttu-id="da624-106">La page par défaut d'atterrissage de catégorie est la page vers laquelle les utilisateurs du site web sont généralement dirigés lorsqu'ils sélectionnent une catégorie dans la hiérarchie de navigation.</span><span class="sxs-lookup"><span data-stu-id="da624-106">The default category landing page is the page that website users typically are taken to when they select a category in the navigation hierarchy.</span></span> <span data-ttu-id="da624-107">La page de catégorie vous permet de parcourir, et vous pouvez également trier et affiner les produits commandés par catégorie.</span><span class="sxs-lookup"><span data-stu-id="da624-107">The category page lets you browse, and you can also sort and refine the categorized products.</span></span>

![Page d'arrivée de catégorie par défaut](./media/SimpleCategoryLandingDressCategory.png)

<span data-ttu-id="da624-109">En haut de la page se trouve un en-tête qui affiche toutes les catégories de produits et d'autres pages que le responsable de la promotion des ventes a classés par catégorie.</span><span class="sxs-lookup"><span data-stu-id="da624-109">At the top of the page is a header that shows all the product categories and other pages that the merchandising manager has categorized.</span></span> <span data-ttu-id="da624-110">La configuration est effectuée dans le cadre de la configuration de la hiérarchie de navigation du canal.</span><span class="sxs-lookup"><span data-stu-id="da624-110">Configuration is done as part of the configuration of the channel navigation hierarchy.</span></span> <span data-ttu-id="da624-111">Au bas de la page se trouve un pied de page qui inclut des liens rapides vers diverses rubriques qui peuvent intéresser un client.</span><span class="sxs-lookup"><span data-stu-id="da624-111">At the bottom of the page is a footer that includes quick links to various topics that a shopper might be interested in.</span></span>

<span data-ttu-id="da624-112">Les composants suivants sont essentiels pour une catégorie :</span><span class="sxs-lookup"><span data-stu-id="da624-112">The following components are essential for a category:</span></span>

- <span data-ttu-id="da624-113">**Vignettes de placement de produit** affiche les produits que le responsable de promotion des ventes a définis dans une catégorie dans le cadre de la configuration de la hiérarchie de navigation.</span><span class="sxs-lookup"><span data-stu-id="da624-113">**Product placement tiles** show the products that the merchandising manager has defined in a category as part of the configuration of the navigation hierarchy.</span></span>
- <span data-ttu-id="da624-114">**Raffineurs et synthèse des choix** sont des filtres qui fournissent des nombres et qui peuvent être utilisés pour affiner les articles.</span><span class="sxs-lookup"><span data-stu-id="da624-114">**Refiners and choice summary** are filters that provide counts and that can be used to refine items.</span></span> <span data-ttu-id="da624-115">Le responsable de la promotion des ventes les configure dans le cadre de la configuration des métadonnées liées aux catégories de canaux et aux attributs de produit.</span><span class="sxs-lookup"><span data-stu-id="da624-115">The merchandising manager configures them as part of the configuration of the metadata related to channel categories and product attributes.</span></span>
- <span data-ttu-id="da624-116">Les **Options de tri** sont utilisés par les visiteurs de site web pour trier les produits.</span><span class="sxs-lookup"><span data-stu-id="da624-116">**Sorting options** are used by website visitors to sort the products.</span></span> <span data-ttu-id="da624-117">Par défaut, les options de tri suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="da624-117">By default, the following sorting options are available:</span></span>

    - <span data-ttu-id="da624-118">Prix – du plus bas au plus élevé</span><span class="sxs-lookup"><span data-stu-id="da624-118">Price – low to high</span></span>
    - <span data-ttu-id="da624-119">Prix – du plus élevé au plus bas</span><span class="sxs-lookup"><span data-stu-id="da624-119">Price – high to low</span></span>
    - <span data-ttu-id="da624-120">Nom du produit – \[A à Z\]</span><span class="sxs-lookup"><span data-stu-id="da624-120">Product name – \[A-Z\]</span></span>
    - <span data-ttu-id="da624-121">Nom du produit – \[Z à A\]</span><span class="sxs-lookup"><span data-stu-id="da624-121">Product name – \[Z-A\]</span></span>
    - <span data-ttu-id="da624-122">Classements – du plus bas au plus élevé</span><span class="sxs-lookup"><span data-stu-id="da624-122">Ratings – low to high</span></span>
    - <span data-ttu-id="da624-123">Classements – du plus élevé au plus bas</span><span class="sxs-lookup"><span data-stu-id="da624-123">Ratings – high to low</span></span>

- <span data-ttu-id="da624-124">La **Pagination** permet aux visiteurs de site web se déplacer d'une page de résultats de produit catégorisé à une autre page.</span><span class="sxs-lookup"><span data-stu-id="da624-124">**Pagination** lets website visitors move from one page of categorized product results to another page.</span></span>
- <span data-ttu-id="da624-125">Le **Nombre total** fournit le nombre total de produits définis dans une catégorie.</span><span class="sxs-lookup"><span data-stu-id="da624-125">**Total count** provides the total number of products that are defined in a category.</span></span>

## <a name="enrich-a-category-landing-page"></a><span data-ttu-id="da624-126">Enrichir une page d'arrivée de catégorie</span><span class="sxs-lookup"><span data-stu-id="da624-126">Enrich a category landing page</span></span>

<span data-ttu-id="da624-127">Si vous souhaitez une page d'arrivée de catégorie pour avoir une expérience plus personnalisée pour une catégorie spécifique, vous pouvez « enrichir » la page d'arrivée de catégorie pour cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="da624-127">If you want a category landing page to have a more tailored experience for a specific category, you can "enrich" the category landing page for that category.</span></span> <span data-ttu-id="da624-128">Par exemple, vous pouvez ajouter une vidéo de marketing et de la narration de catégorie pour obtenir l'attention du client.</span><span class="sxs-lookup"><span data-stu-id="da624-128">For example, you can add a marketing video and some category storytelling to get the shopper's attention.</span></span> <span data-ttu-id="da624-129">Pour plus d'informations, voir [Enrichir une page d'arrivée de catégorie](enrich-category-page.md).</span><span class="sxs-lookup"><span data-stu-id="da624-129">For more information, see [Enrich a category landing page](enrich-category-page.md).</span></span>

![Page d'arrivée de catégorie enrichie](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a><span data-ttu-id="da624-131">Suggestion automatique et pages de résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="da624-131">Auto-suggest and search results pages</span></span>

<span data-ttu-id="da624-132">Les utilisateurs du site web peuvent explorer un site en accédant à une catégorie de la hiérarchie de navigation ou en entrant un terme de recherche dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="da624-132">Website users can explore a site either by going to a category from the navigation hierarchy or by entering a search term in the search field.</span></span>

<span data-ttu-id="da624-133">Dès que les utilisateurs commencent à saisir dans le champ de recherche, ils rencontrent la fonctionnalité de suggestion automatique immersive qui suggère des termes de recherche.</span><span class="sxs-lookup"><span data-stu-id="da624-133">As soon as users start to type in the search field, they experience the immersive auto-suggest functionality that suggests search terms.</span></span>

<span data-ttu-id="da624-134">Voici certains types de suggestions qui peuvent être affichés :</span><span class="sxs-lookup"><span data-stu-id="da624-134">Here are some of the types of suggestions that might be shown:</span></span>

- <span data-ttu-id="da624-135">Les **Mots clés** permettent de rechercher des articles parmi tous les produits qui sont assortis au canal.</span><span class="sxs-lookup"><span data-stu-id="da624-135">**Keywords** are used to find items across all products that are assorted to the channel.</span></span>
- <span data-ttu-id="da624-136">Les **Produits** fournissent des liens directs vers la page de détails des produits.</span><span class="sxs-lookup"><span data-stu-id="da624-136">**Products** provide direct links to the product details page.</span></span>
- <span data-ttu-id="da624-137">Les **Suggestions de recherche de catégorie étendue** répertorie différentes catégories et permettent aux utilisateurs de rechercher le mot clé dans une catégorie spécifique.</span><span class="sxs-lookup"><span data-stu-id="da624-137">**Scoped category search suggestions** list various categories and let users search for the keyword in a specific category.</span></span>

![Suggestion automatique immersive](./media/ImmersiveAutoSuggestUX.png)

<span data-ttu-id="da624-139">Lorsque les utilisateurs sélectionnent l'un des mot clé ou des suggestions de recherche de catégorie étendue, ou lorsqu'il n'y a aucune suggestion de terme de recherche qu'ils saisissent, ils sont redirigés à une page de résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="da624-139">When users select one of the keyword or scoped category search suggestions, or when there are no suggestions for the search term that they enter, they are redirected to a search results page.</span></span> <span data-ttu-id="da624-140">Les utilisateurs peuvent alors parcourir, trier et affiner la liste des résultats de la recherche pour rechercher l'article souhaité.</span><span class="sxs-lookup"><span data-stu-id="da624-140">The users can then browse, sort, and refine the list of search results to find the desired item.</span></span>

![Rechercher la page de destination](./media/SearchLanding.png)

<span data-ttu-id="da624-142">Les composants suivants sont essentiels pour une page de résultats de recherche :</span><span class="sxs-lookup"><span data-stu-id="da624-142">The following components are essential for a search results page:</span></span>

- <span data-ttu-id="da624-143">Les **Vignettes de placement de produit** affiche les produits pour la recherche d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="da624-143">**Product placement tiles** show the products for the user's search.</span></span> <span data-ttu-id="da624-144">Par défaut, ces vignettes sont triées par le score de pertinence de la recherche optimisée par le cloud pour la recherche d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="da624-144">By default, these tiles are sorted by the cloud-powered search relevancy score for the user search.</span></span>
- <span data-ttu-id="da624-145">**Raffineurs et synthèse des choix** sont des filtres qui fournissent des nombres et qui peuvent être utilisés pour affiner les articles.</span><span class="sxs-lookup"><span data-stu-id="da624-145">**Refiners and choice summary** are filters that provide counts and that can be used to refine items.</span></span> <span data-ttu-id="da624-146">Le responsable de la promotion des ventes les configure dans le cadre de la configuration des métadonnées des « catégories de canaux et aux attributs de produit ».</span><span class="sxs-lookup"><span data-stu-id="da624-146">The merchandising manager configures them as part of the configuration of the "channel categories and product attributes" metadata.</span></span>
- <span data-ttu-id="da624-147">Les **Options de tri** sont utilisés par les visiteurs de site web pour trier les produits.</span><span class="sxs-lookup"><span data-stu-id="da624-147">**Sorting options** are used by website visitors to sort the products.</span></span> <span data-ttu-id="da624-148">Par défaut, les options de tri suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="da624-148">By default, the following sorting options are available:</span></span>

    - <span data-ttu-id="da624-149">Prix – du plus bas au plus élevé</span><span class="sxs-lookup"><span data-stu-id="da624-149">Price – low to high</span></span>
    - <span data-ttu-id="da624-150">Prix – du plus élevé au plus bas</span><span class="sxs-lookup"><span data-stu-id="da624-150">Price – high to low</span></span>
    - <span data-ttu-id="da624-151">Nom du produit – \[A à Z\]</span><span class="sxs-lookup"><span data-stu-id="da624-151">Product name – \[A-Z\]</span></span>
    - <span data-ttu-id="da624-152">Nom du produit – \[Z à A\]</span><span class="sxs-lookup"><span data-stu-id="da624-152">Product name – \[Z-A\]</span></span>
    - <span data-ttu-id="da624-153">Classements – du plus bas au plus élevé</span><span class="sxs-lookup"><span data-stu-id="da624-153">Ratings – low to high</span></span>
    - <span data-ttu-id="da624-154">Classements – du plus élevé au plus bas</span><span class="sxs-lookup"><span data-stu-id="da624-154">Ratings – high to low</span></span>
    - <span data-ttu-id="da624-155">Par défaut</span><span class="sxs-lookup"><span data-stu-id="da624-155">Default</span></span>

- <span data-ttu-id="da624-156">La **Pagination** permet aux visiteurs de site web se déplacer d'une page de résultats de produit catégorisé à une autre page.</span><span class="sxs-lookup"><span data-stu-id="da624-156">**Pagination** lets website visitors move from one page of categorized product results to another page.</span></span>
- <span data-ttu-id="da624-157">Le **Nombre total** fournit le nombre total de produits définis dans une catégorie et qui correspondent aux critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="da624-157">**Total count** provides the total number of products that are defined in a category and that match the search criteria.</span></span>

>[!NOTE]
><span data-ttu-id="da624-158">Ces fonctionnalités de recherche dans le cloud sont disponibles à partir de la version 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="da624-158">These cloud-powered search capabilities are available starting in version 10.0.8.</span></span> <span data-ttu-id="da624-159">Assurez-vous que sous **Paramètres Commerce > Paramètres de configuration**, il existe une entrée pour « ProductSearch.UseAzureSearch » définie sur « true ».</span><span class="sxs-lookup"><span data-stu-id="da624-159">Ensure that under **Commerce Parameters > Configuration Parameters** there is an entry for "ProductSearch.UseAzureSearch set to 'true'".</span></span> 
<span data-ttu-id="da624-160">![Paramètres de configuration pour la recherche dans le cloud](./media/CloudPoweredSearchConfigurationParameters.png)</span><span class="sxs-lookup"><span data-stu-id="da624-160">![Configuration parameters for cloud-powered search](./media/CloudPoweredSearchConfigurationParameters.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="da624-161">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="da624-161">Additional resources</span></span>

[<span data-ttu-id="da624-162">Vue d'ensemble de la recherche dans le cloud</span><span class="sxs-lookup"><span data-stu-id="da624-162">Cloud-powered search overview</span></span>](cloud-powered-search-overview.md)

[<span data-ttu-id="da624-163">Vue d'ensemble de la page d'accueil</span><span class="sxs-lookup"><span data-stu-id="da624-163">Home page overview</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="da624-164">Vue d'ensemble des pages de détails de produit</span><span class="sxs-lookup"><span data-stu-id="da624-164">Product details pages overview</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="da624-165">Vue d'ensemble des pages de panier et de caisse</span><span class="sxs-lookup"><span data-stu-id="da624-165">Cart and checkout pages overview</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="da624-166">Vue d'ensemble des pages de gestion des comptes</span><span class="sxs-lookup"><span data-stu-id="da624-166">Account management pages overview</span></span>](quick-tour-account-management.md)

