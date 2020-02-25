---
title: Vue d'ensemble des pages détaillées du produit
description: Cette rubrique fournit une vue d'ensemble des pages détaillées du produit dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: dbf8f4c1ea479a508f4a0294020b7201b32fe228
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025923"
---
# <a name="overview-of-product-details-pages"></a><span data-ttu-id="f0e44-103">Vue d'ensemble des pages détaillées du produit</span><span class="sxs-lookup"><span data-stu-id="f0e44-103">Overview of product details pages</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f0e44-104">Cette rubrique fournit une vue d'ensemble des pages détaillées du produit dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0e44-104">This topic provides an overview of product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f0e44-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="f0e44-105">Overview</span></span>

<span data-ttu-id="f0e44-106">Une page détaillée du produit fournit des informations détaillées sur un produit, et permet aux clients de sélectionner des options de produit comme une taille, un style, et une couleur.</span><span class="sxs-lookup"><span data-stu-id="f0e44-106">A PDP provides detailed information about a product, and lets customers select product options such as a size, style, and color.</span></span> <span data-ttu-id="f0e44-107">Une page détaillée du produit doit présenter toutes les informations sur le produit dont un client a besoin pour effectuer une décision d'achat.</span><span class="sxs-lookup"><span data-stu-id="f0e44-107">A PDP should showcase all the product information that a customer requires to make a purchase decision.</span></span>

<span data-ttu-id="f0e44-108">L'illustration suivante présente un exemple de page détaillée du produit.</span><span class="sxs-lookup"><span data-stu-id="f0e44-108">The following illustration shows an example of a PDP.</span></span>

![Exemple de page de détails des produits](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a><span data-ttu-id="f0e44-110">Modules d'en-tête et de pied de page</span><span class="sxs-lookup"><span data-stu-id="f0e44-110">Header and footer modules</span></span>

<span data-ttu-id="f0e44-111">Le haut de la page détaillée du produit comporte en-tête qui affiche toutes les catégories de produits et d'autres pages que le détaillant souhaite que les clients parcourent.</span><span class="sxs-lookup"><span data-stu-id="f0e44-111">The top of a PDP has a header that shows all the product categories and other pages that the retailer wants customers to browse.</span></span> <span data-ttu-id="f0e44-112">Le bas de la page comporte un pied de page qui contient des liens rapides vers diverses rubriques qui peuvent intéresser les clients.</span><span class="sxs-lookup"><span data-stu-id="f0e44-112">The bottom of the page has a footer that contains quick links to various topics that might interest customers.</span></span>

## <a name="buy-box-module"></a><span data-ttu-id="f0e44-113">Module de zone d'achat</span><span class="sxs-lookup"><span data-stu-id="f0e44-113">Buy box module</span></span>

<span data-ttu-id="f0e44-114">Le module le plus important sur une page de détails de produit est le module de boîte d'achat, qui apparaît en premier dans la section principale de la page.</span><span class="sxs-lookup"><span data-stu-id="f0e44-114">The most important module on a PDP is the buy box module, which appears as the first item in the main section of the page.</span></span> <span data-ttu-id="f0e44-115">Un module de boîte d'achat affiche des informations importantes sur le produit, telles que son nom, sa description, son prix, des images du produit et les classements du produit.</span><span class="sxs-lookup"><span data-stu-id="f0e44-115">A buy box module shows important product information, such as the product name, the product description, the product price, product images, and product ratings.</span></span>

<span data-ttu-id="f0e44-116">Le module de zone d'achat permet au client de sélectionner des options de produit (par exemple, une taille, un style, et une couleur) et d'ajouter le produit au panier.</span><span class="sxs-lookup"><span data-stu-id="f0e44-116">The buy box module lets the customer select product options (for example, a size, style, and color) and add the product to the cart.</span></span> <span data-ttu-id="f0e44-117">Il permet également au client d'acheter les produits en ligne et de les prélever en magasin.</span><span class="sxs-lookup"><span data-stu-id="f0e44-117">It also lets the customer buy the product online and pick it up in a store.</span></span> <span data-ttu-id="f0e44-118">Le module d'achat en ligne et prélèvement en magasin utilise l'intégration avec des interface de programmation d'application (API) Bing Maps pour rechercher les magasins à proximité ou les magasins à un autre emplacement que le client spécifie.</span><span class="sxs-lookup"><span data-stu-id="f0e44-118">The buy online and pick up in store module uses integration with Bing Maps application programming interfaces (APIs) to find nearby stores or stores in another location that the customer specifies.</span></span>

<span data-ttu-id="f0e44-119">Un module de zone d'achat requiert un ID produit.</span><span class="sxs-lookup"><span data-stu-id="f0e44-119">A buy box module requires a product ID.</span></span> <span data-ttu-id="f0e44-120">Cet ID est dérivé du contexte de page.</span><span class="sxs-lookup"><span data-stu-id="f0e44-120">This ID is derived from the page context.</span></span> <span data-ttu-id="f0e44-121">Si un module de zone d'achat est ajouté à une page où le contexte de page n'inclut pas un ID produit, il n'affichera pas les informations correctement.</span><span class="sxs-lookup"><span data-stu-id="f0e44-121">If a buy box module is added to a page where the page context doesn't include a product ID, it won't render the information correctly.</span></span>

## <a name="product-specifications-module"></a><span data-ttu-id="f0e44-122">Module de spécifications du produit</span><span class="sxs-lookup"><span data-stu-id="f0e44-122">Product specifications module</span></span>

<span data-ttu-id="f0e44-123">Le module de spécifications du produit peut être utilisé pour présenter des informations supplémentaires sur le produit.</span><span class="sxs-lookup"><span data-stu-id="f0e44-123">The product specifications module can be used to showcase additional details about the product.</span></span> <span data-ttu-id="f0e44-124">Ces détails sont extraits des attributs de produit dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0e44-124">These details are taken from product attributes in Commerce.</span></span> <span data-ttu-id="f0e44-125">Le module de spécifications de produit affiche chaque attribut où la propriété **visible** est définie sur **vrai**.</span><span class="sxs-lookup"><span data-stu-id="f0e44-125">The product specifications module shows every attribute where the **visible** property is set to **true**.</span></span> <span data-ttu-id="f0e44-126">Il nécessite un ID produit pour récupérer les attributs du produit.</span><span class="sxs-lookup"><span data-stu-id="f0e44-126">It requires a product ID to retrieve the product attributes.</span></span>

## <a name="recommendations-module"></a><span data-ttu-id="f0e44-127">Module de recommandations</span><span class="sxs-lookup"><span data-stu-id="f0e44-127">Recommendations module</span></span>

<span data-ttu-id="f0e44-128">Le module de recommandations est un important module sur une page détaillée du produit.</span><span class="sxs-lookup"><span data-stu-id="f0e44-128">The recommendations module is an important module on a PDP.</span></span> <span data-ttu-id="f0e44-129">Bien que les clients parcourent les produits, des options de produit supplémentaires doivent leur être présentées, afin qu'ils puissent trouver le produit approprié et effectuer un achat.</span><span class="sxs-lookup"><span data-stu-id="f0e44-129">While customers browse for products, more product options should be presented to them, so that they can find the correct product and make a purchase.</span></span> <span data-ttu-id="f0e44-130">Les recommandations aident les clients à découvrir facilement le contenu associé et à continuer d'effectuer des achats.</span><span class="sxs-lookup"><span data-stu-id="f0e44-130">Recommendations help customers easily discover related content and continue to shop.</span></span>

<span data-ttu-id="f0e44-131">Différents types de listes de recommandations sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="f0e44-131">Different types of recommendation lists are available:</span></span>

- <span data-ttu-id="f0e44-132">La liste **D'autres clients aiment également** est basée sur le Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="f0e44-132">The **People also like** list is based on machine learning.</span></span> <span data-ttu-id="f0e44-133">Elle utilise l'historique des transactions d'autres clients pour fournir des recommandations.</span><span class="sxs-lookup"><span data-stu-id="f0e44-133">It uses the transaction history of other customers to provide recommendations.</span></span> <span data-ttu-id="f0e44-134">Cette liste est générée par le service de recommandations et ressemble aux listes « Les clients qui ont acheté ce produit ont également acheté... ».</span><span class="sxs-lookup"><span data-stu-id="f0e44-134">This list is generated by the recommendations service and resembles "Customers who bought this also bought..." lists.</span></span> <span data-ttu-id="f0e44-135">Un ID produit est obligatoire pour générer la liste.</span><span class="sxs-lookup"><span data-stu-id="f0e44-135">A product ID is required to generate this list.</span></span>
- <span data-ttu-id="f0e44-136">Une liste **Associé** peut être configurée pour un produit dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0e44-136">A **Related** list can be configured for a product in Commerce.</span></span> <span data-ttu-id="f0e44-137">Par exemple, pour un sac de voyage en cuir marron, davantage de sacs en cuir ou conçus pour les voyages peuvent être configurés pour la liste associée.</span><span class="sxs-lookup"><span data-stu-id="f0e44-137">For example, for a brown leather travel handbag, more handbags that are leather-based or designed for travel purposes can be configured for the related list.</span></span> <span data-ttu-id="f0e44-138">Les autres types de liste associée, telles que **Accessoires** et **Plus comme celui-ci**, peuvent également être configurées dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0e44-138">Other types of related lists, such as **Accessories** and **More like this**, can also be configured in Commerce.</span></span> <span data-ttu-id="f0e44-139">Un ID produit est obligatoire pour générer la liste.</span><span class="sxs-lookup"><span data-stu-id="f0e44-139">A product ID is required to generate this list.</span></span> <span data-ttu-id="f0e44-140">Par conséquent, si elle est ajoutée à une page d'accueil, où le contexte de page n'inclut pas d'ID produit, la liste est vide.</span><span class="sxs-lookup"><span data-stu-id="f0e44-140">Therefore, if it's added to a home page, where the page context doesn't include a product ID, the list will be empty.</span></span>
- <span data-ttu-id="f0e44-141">Les listes de recommandations algorithmiquement générées, comme **Tendance**, **Meilleures ventes**, **Nouveauté**, peuvent être utilisées sur les pages de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="f0e44-141">Algorithmically generated recommendation lists, such as **Trending**, **Best Selling**, and **New**, can be used on PDPs.</span></span> <span data-ttu-id="f0e44-142">Bien que ces listes ne soient pas directement liées au produit sur la page de détails de produit, elles permettent aux clients de trouver autrement les produits qui pourraient les intéresser.</span><span class="sxs-lookup"><span data-stu-id="f0e44-142">Although these lists might not be directly related to the product on the PDP, they are another way to help customers find products that might interest them.</span></span> <span data-ttu-id="f0e44-143">Ces types de listes ne nécessitent pas d'ID produit.</span><span class="sxs-lookup"><span data-stu-id="f0e44-143">These types of lists don't require a product ID.</span></span> <span data-ttu-id="f0e44-144">Ce sont des listes génériques basées sur les modèles d'achat du le site.</span><span class="sxs-lookup"><span data-stu-id="f0e44-144">They are generic lists that are generated based on shopping patterns across the site.</span></span>
- <span data-ttu-id="f0e44-145">Les listes éditoriales sont des listes manuellement éditées.</span><span class="sxs-lookup"><span data-stu-id="f0e44-145">Editorial lists are manually curated lists.</span></span> <span data-ttu-id="f0e44-146">Par exemple, un détaillant peut décider d'éditer manuellement les listes de produits qu'il souhaite présenter.</span><span class="sxs-lookup"><span data-stu-id="f0e44-146">For example, a retailer might decide to manually curate lists of products that it wants to showcase.</span></span>

## <a name="ratings-and-reviews-modules"></a><span data-ttu-id="f0e44-147">Modules de classements et d'évaluations</span><span class="sxs-lookup"><span data-stu-id="f0e44-147">Ratings and reviews modules</span></span>

<span data-ttu-id="f0e44-148">3 modules peuvent être utilisés pour afficher et ajouter des évaluations :</span><span class="sxs-lookup"><span data-stu-id="f0e44-148">Three modules can be used to show and add reviews:</span></span>

- <span data-ttu-id="f0e44-149">**Évaluations** : ce module répertorie les classements et les évaluations fournis par les autres clients.</span><span class="sxs-lookup"><span data-stu-id="f0e44-149">**Reviews** – This module lists ratings and reviews that have been provided by other customers.</span></span> <span data-ttu-id="f0e44-150">Les clients peuvent trier et filtrer ces évaluations.</span><span class="sxs-lookup"><span data-stu-id="f0e44-150">Customers can sort and filter the reviews.</span></span> <span data-ttu-id="f0e44-151">Ce module permet également aux clients d'émettre un avis favorable ou défavorable sur les évaluations et de signaler des problèmes.</span><span class="sxs-lookup"><span data-stu-id="f0e44-151">This module also lets customers like or dislike reviews, and report issues.</span></span>
- <span data-ttu-id="f0e44-152">**Écrire une évaluation** : ce module permet aux clients d'écrire leurs évaluations sur un produit.</span><span class="sxs-lookup"><span data-stu-id="f0e44-152">**Write review** – This module lets customers write their own reviews of a product.</span></span>
- <span data-ttu-id="f0e44-153">**Histogramme de classements** : ce module comprend un histogramme qui montre la tendance des classements pour un produit.</span><span class="sxs-lookup"><span data-stu-id="f0e44-153">**Ratings histogram** – This module includes a histogram that shows the ratings trend for a product.</span></span>

<span data-ttu-id="f0e44-154">Pour plus de détails, voir [Vue d'ensemble des classements et des évaluations](ratings-reviews-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f0e44-154">For more details, see [Ratings and reviews overview](ratings-reviews-overview.md).</span></span>

## <a name="marketing-modules"></a><span data-ttu-id="f0e44-155">Modules de marketing</span><span class="sxs-lookup"><span data-stu-id="f0e44-155">Marketing modules</span></span>

<span data-ttu-id="f0e44-156">Si le contenu de marketing est unique à un produit spécifique, un module de marketing peut être ajouté à la page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="f0e44-156">If marketing content is unique to a specific product, any marketing module can be added to the PDP.</span></span> <span data-ttu-id="f0e44-157">Vous pouvez ajouter des modules de marketing à une page de détails de produit en « enrichissant » la page.</span><span class="sxs-lookup"><span data-stu-id="f0e44-157">You can add marketing modules to a PDP by "enriching" the page.</span></span> <span data-ttu-id="f0e44-158">Pour plus de détails, voir [Enrichir une page de produit](enrich-product-page.md).</span><span class="sxs-lookup"><span data-stu-id="f0e44-158">For more details, see [Enrich a product page](enrich-product-page.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f0e44-159">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f0e44-159">Additional resources</span></span>

[<span data-ttu-id="f0e44-160">Vue d'ensemble de la page d'accueil</span><span class="sxs-lookup"><span data-stu-id="f0e44-160">Overview of the home page</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="f0e44-161">Vue d'ensemble de la page d'arrivée de la catégorie par défaut et de la page des résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="f0e44-161">Overview of default category landing page and search results page</span></span>](category-search-page-overview.md)

[<span data-ttu-id="f0e44-162">Vue d'ensemble des pages de chariot et de validation</span><span class="sxs-lookup"><span data-stu-id="f0e44-162">Overview of cart and checkout pages</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="f0e44-163">Vue d'ensemble des pages de gestion de compte</span><span class="sxs-lookup"><span data-stu-id="f0e44-163">Overview of account management pages</span></span>](quick-tour-account-management.md)

[<span data-ttu-id="f0e44-164">Enrichir une page de détails sur un produit</span><span class="sxs-lookup"><span data-stu-id="f0e44-164">Enrich a product details page</span></span>](enrich-product-page.md)
