---
title: Modules de classements et d'évaluations
description: Cette rubrique couvre les modules de classements et d'évaluations utilisés sur les pages de détails des produits dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: 85fb1272103eed7d6e44635b7c20438471d96b34
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412369"
---
# <a name="ratings-and-reviews-modules"></a><span data-ttu-id="82208-103">Modules de classements et d'évaluations</span><span class="sxs-lookup"><span data-stu-id="82208-103">Ratings and reviews modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="82208-104">Cette rubrique couvre les modules de classements et d'évaluations utilisés sur les pages de détails des produits dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="82208-104">This topic covers ratings and reviews modules used on product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="82208-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="82208-105">Overview</span></span>

<span data-ttu-id="82208-106">Les classements et les évaluations des sites web de commerce électronique permettent aux clients d'en savoir plus sur les produits avant de prendre une décision d'achat. Ce sont également un mécanisme de collecte des commentaires des clients sur les produits.</span><span class="sxs-lookup"><span data-stu-id="82208-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, and are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="82208-107">Les classements sont affichés dans les pages de liste de produit, les pages de liste de catégorie, les pages de résultats de la recherche, et d'autres pages du site.</span><span class="sxs-lookup"><span data-stu-id="82208-107">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> 

<span data-ttu-id="82208-108">Les histogrammes de classement et les évaluations de produits sont affichés sur les pages de détails des produits.</span><span class="sxs-lookup"><span data-stu-id="82208-108">Ratings histograms and product reviews are shown on PDPs.</span></span> <span data-ttu-id="82208-109">Un bouton **Écrire une évaluation** permet aux clients envoyer des classements et les évaluations d'un produit.</span><span class="sxs-lookup"><span data-stu-id="82208-109">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span> <span data-ttu-id="82208-110">Ces fonctionnalités des pages de détails des produits sont contrôlées par des modules de classement et d'évaluation.</span><span class="sxs-lookup"><span data-stu-id="82208-110">These PDP features are controlled by ratings and review modules.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="82208-111">Modules de classements et d'évaluations sur les pages de détails des produits</span><span class="sxs-lookup"><span data-stu-id="82208-111">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="82208-112">Trois modules affichent le récapitulatif des classements et des évaluations sur les pages de détails des produits :</span><span class="sxs-lookup"><span data-stu-id="82208-112">Three modules show the ratings and reviews summary on PDPs:</span></span>
- <span data-ttu-id="82208-113">Module Écrire une évaluation</span><span class="sxs-lookup"><span data-stu-id="82208-113">Write review module</span></span>
- <span data-ttu-id="82208-114">Module Liste de classements de produit</span><span class="sxs-lookup"><span data-stu-id="82208-114">Product reviews list module</span></span>
- <span data-ttu-id="82208-115">Module d'histogramme de classements</span><span class="sxs-lookup"><span data-stu-id="82208-115">Ratings histogram module</span></span>
 
<span data-ttu-id="82208-116">L'illustration suivante présente à quoi les modules de classements et d'évaluation ressemble sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="82208-116">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Modules de classements et d'évaluations sur une page de détails de produit](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="82208-118">Pour plus d'informations sur la procédure d'optimisation des modèles et des dispositions de page de détails de produit afin de partager les configurations des modules de classements et d'évaluation entre plusieurs pages de détails des produits sur votre site de commerce électronique, voir [Vue d'ensemble des modèles et dispositions](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="82208-118">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="82208-119">L'illustration ci-dessous indique comment la boîte de dialogue **Ajouter un module** présente les modules de classements et d'évaluation dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="82208-119">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>
<span data-ttu-id="82208-120">![Boîte de dialogue Ajouter un module](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span><span class="sxs-lookup"><span data-stu-id="82208-120">![Add module dialog box](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span></span>

### <a name="write-review-module"></a><span data-ttu-id="82208-121">Module Écrire une évaluation</span><span class="sxs-lookup"><span data-stu-id="82208-121">Write review module</span></span>

<span data-ttu-id="82208-122">Le module Écrire une évaluation inclut un bouton **Écrire une évaluation** qui permet aux utilisateurs de se connecter, d'affecter un classement, et d'écrire une évaluation de produit.</span><span class="sxs-lookup"><span data-stu-id="82208-122">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="82208-123">Ce module permet également aux utilisateurs de modifier un classement ou une évaluation qu'il a précédemment soumis.</span><span class="sxs-lookup"><span data-stu-id="82208-123">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="82208-124">Ce module apparaît généralement au-dessus des modules d'histogramme des classements et de liste d'évaluations de produit sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="82208-124">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>
<span data-ttu-id="82208-125">L'illustration suivante présente la boîte de dialogue **Écrire une évaluation** qui s'affiche lorsqu'un client sélectionne **Écrire une évaluation**.</span><span class="sxs-lookup"><span data-stu-id="82208-125">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="82208-126">Le client peut utiliser cette boîte de dialogue pour envoyer un classement et une évaluation.</span><span class="sxs-lookup"><span data-stu-id="82208-126">The customer can use this dialog box to submit a rating and a review.</span></span>
<span data-ttu-id="82208-127">![Boîte de dialogue Écrire une évaluation](media/rnr-eCommerce-write-review-module.png) Le tableau suivant montre la propriété du module Écrire une évaluation qui doit être configurée dans l'outil de création.</span><span class="sxs-lookup"><span data-stu-id="82208-127">![Write a review dialog box](media/rnr-eCommerce-write-review-module.png) The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>
| <span data-ttu-id="82208-128">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="82208-128">Property name</span></span> | <span data-ttu-id="82208-129">Valeur</span><span class="sxs-lookup"><span data-stu-id="82208-129">Value</span></span>        | <span data-ttu-id="82208-130">Description de la propriété</span><span class="sxs-lookup"><span data-stu-id="82208-130">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="82208-131">Nom</span><span class="sxs-lookup"><span data-stu-id="82208-131">Name</span></span>          | <span data-ttu-id="82208-132">Écrire une évaluation</span><span class="sxs-lookup"><span data-stu-id="82208-132">Write review</span></span> | <span data-ttu-id="82208-133">Nom du module Écrire une évaluation.</span><span class="sxs-lookup"><span data-stu-id="82208-133">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="82208-134">Module d'histogramme de classements</span><span class="sxs-lookup"><span data-stu-id="82208-134">Ratings histogram module</span></span>

<span data-ttu-id="82208-135">Le module d'histogramme de classements affiche un histogramme de classements.</span><span class="sxs-lookup"><span data-stu-id="82208-135">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="82208-136">Ce module s'affiche généralement entre le module Écrire une évaluation et le module de liste d'évaluations de produit sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="82208-136">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>
<span data-ttu-id="82208-137">Le module d'histogramme de classements ne requiert aucune configuration.</span><span class="sxs-lookup"><span data-stu-id="82208-137">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="82208-138">Vous devez simplement ajouter le module dans modèle de page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="82208-138">You just have to add the module in the PDP template.</span></span> <span data-ttu-id="82208-139">Les illustrations suivantes présentent à quoi un modèle de page de détails de produit dans Dynamics 365 Commerce lorsque des modules de classements et d'évaluations sont configurés pour s'afficher sur les pages de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="82208-139">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>
<span data-ttu-id="82208-140">![Modèle de page de détails de produit lorsque les classements et les évaluations sont configurés pour s'afficher sur des pages de détails de produit](media/rnr-eCommerce-pdp-reviews-modules.png)</span><span class="sxs-lookup"><span data-stu-id="82208-140">![PDP template when ratings and reviews are configured for display on PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)</span></span>

### <a name="product-reviews-list-module"></a><span data-ttu-id="82208-141">Module Liste de classements de produit</span><span class="sxs-lookup"><span data-stu-id="82208-141">Product reviews list module</span></span>

<span data-ttu-id="82208-142">Le modules de liste d'évaluations de produit affiche une liste des évaluations de produit avec des options de tri, de filtre, et de numérotation de pages.</span><span class="sxs-lookup"><span data-stu-id="82208-142">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="82208-143">Ce module s'affiche généralement après le module d'histogramme de classements sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="82208-143">This module typically appears after the ratings histogram module on a PDP.</span></span>
<span data-ttu-id="82208-144">Le tableau suivant montre les propriétés du module de liste d'évaluations de produits qui doivent être configurées dans l'outil de création.</span><span class="sxs-lookup"><span data-stu-id="82208-144">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="82208-145">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="82208-145">Property name</span></span>              | <span data-ttu-id="82208-146">Valeur</span><span class="sxs-lookup"><span data-stu-id="82208-146">Value</span></span> | <span data-ttu-id="82208-147">Description de la propriété</span><span class="sxs-lookup"><span data-stu-id="82208-147">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="82208-148">Évaluations affichés sur chaque page</span><span class="sxs-lookup"><span data-stu-id="82208-148">Reviews shown on each page</span></span> | <span data-ttu-id="82208-149">10</span><span class="sxs-lookup"><span data-stu-id="82208-149">10</span></span>    | <span data-ttu-id="82208-150">Nombre d'évaluations qui doivent figurer à la fois sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="82208-150">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="82208-151">Les boutons **Suivant** et **Précédent** sont inclus, afin que les utilisateurs puissent circuler entre les pages d'évaluations.</span><span class="sxs-lookup"><span data-stu-id="82208-151">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="82208-152">Histogramme de classements – Vue de synthèse</span><span class="sxs-lookup"><span data-stu-id="82208-152">Ratings histogram – Summary view</span></span>

<span data-ttu-id="82208-153">Le module de liste d'évaluations de produit inclut un emplacement dans lequel vous pouvez ajouter un module d'histogramme des classements.</span><span class="sxs-lookup"><span data-stu-id="82208-153">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="82208-154">L'illustration ci-dessous indique comment vous pouvez ajouter un module d'histogramme de classements dans le module de liste d'évaluations de produit dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="82208-154">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Ajout d'un module histogramme de classements dans un module de liste d'évaluations de produit](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a><span data-ttu-id="82208-156">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="82208-156">Additional resources</span></span>

[<span data-ttu-id="82208-157">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="82208-157">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="82208-158">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="82208-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="82208-159">Module Panier</span><span class="sxs-lookup"><span data-stu-id="82208-159">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="82208-160">Module Validation</span><span class="sxs-lookup"><span data-stu-id="82208-160">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="82208-161">Module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="82208-161">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="82208-162">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="82208-162">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="82208-163">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="82208-163">Footer module</span></span>](author-footer-module.md)
