---
title: Modules de classements et d'évaluations
description: Cette rubrique couvre les modules de classements et d’évaluations utilisés sur les pages de détails des produits dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: 26658ebdbc70613baf30c344664133b9cf5911ca
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243767"
---
# <a name="ratings-and-reviews-modules"></a><span data-ttu-id="bdfa6-103">Modules Classements et Évaluations</span><span class="sxs-lookup"><span data-stu-id="bdfa6-103">Ratings and reviews modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bdfa6-104">Cette rubrique couvre les modules de classements et d’évaluations utilisés sur les pages de détails des produits dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-104">This topic covers ratings and reviews modules used on product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="bdfa6-105">Les classements et les évaluations des sites web de commerce électronique permettent aux clients d'en savoir plus sur les produits avant de prendre une décision d'achat. Ce sont également un mécanisme de collecte des commentaires des clients sur les produits.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-105">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, and are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="bdfa6-106">Les classements sont affichés dans les pages de liste de produit, les pages de liste de catégorie, les pages de résultats de la recherche, et d'autres pages du site.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-106">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> 

<span data-ttu-id="bdfa6-107">Les histogrammes de classement et les évaluations de produits sont affichés sur les pages de détails des produits.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-107">Ratings histograms and product reviews are shown on PDPs.</span></span> <span data-ttu-id="bdfa6-108">Un bouton **Écrire une évaluation** permet aux clients envoyer des classements et les évaluations d'un produit.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-108">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span> <span data-ttu-id="bdfa6-109">Ces fonctionnalités des pages de détails des produits sont contrôlées par des modules de classement et d'évaluation.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-109">These PDP features are controlled by ratings and review modules.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="bdfa6-110">Modules de classements et d'évaluations sur les pages de détails des produits</span><span class="sxs-lookup"><span data-stu-id="bdfa6-110">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="bdfa6-111">Trois modules affichent le récapitulatif des classements et des évaluations sur les pages de détails des produits :</span><span class="sxs-lookup"><span data-stu-id="bdfa6-111">Three modules show the ratings and reviews summary on PDPs:</span></span>
- <span data-ttu-id="bdfa6-112">Module Écrire une évaluation</span><span class="sxs-lookup"><span data-stu-id="bdfa6-112">Write review module</span></span>
- <span data-ttu-id="bdfa6-113">Module Liste de classements de produit</span><span class="sxs-lookup"><span data-stu-id="bdfa6-113">Product reviews list module</span></span>
- <span data-ttu-id="bdfa6-114">Module d'histogramme de classements</span><span class="sxs-lookup"><span data-stu-id="bdfa6-114">Ratings histogram module</span></span>
 
<span data-ttu-id="bdfa6-115">L'illustration suivante présente à quoi les modules de classements et d'évaluation ressemble sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-115">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Modules de classements et d'évaluations sur une page de détails de produit](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="bdfa6-117">Pour plus d'informations sur la procédure d'optimisation des modèles et des dispositions de page de détails de produit afin de partager les configurations des modules de classements et d'évaluation entre plusieurs pages de détails des produits sur votre site de commerce électronique, voir [Vue d'ensemble des modèles et dispositions](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bdfa6-117">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="bdfa6-118">L'illustration ci-dessous indique comment la boîte de dialogue **Ajouter un module** présente les modules de classements et d'évaluation dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-118">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>
<span data-ttu-id="bdfa6-119">![Boîte de dialogue Ajouter un module](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span><span class="sxs-lookup"><span data-stu-id="bdfa6-119">![Add module dialog box](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span></span>

### <a name="write-review-module"></a><span data-ttu-id="bdfa6-120">Module Écrire une évaluation</span><span class="sxs-lookup"><span data-stu-id="bdfa6-120">Write review module</span></span>

<span data-ttu-id="bdfa6-121">Le module Écrire une évaluation inclut un bouton **Écrire une évaluation** qui permet aux utilisateurs de se connecter, d'affecter un classement, et d'écrire une évaluation de produit.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-121">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="bdfa6-122">Ce module permet également aux utilisateurs de modifier un classement ou une évaluation qu'il a précédemment soumis.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-122">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="bdfa6-123">Ce module apparaît généralement au-dessus des modules d'histogramme des classements et de liste d'évaluations de produit sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-123">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>
<span data-ttu-id="bdfa6-124">L'illustration suivante présente la boîte de dialogue **Écrire une évaluation** qui s'affiche lorsqu'un client sélectionne **Écrire une évaluation**.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-124">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="bdfa6-125">Le client peut utiliser cette boîte de dialogue pour envoyer un classement et une évaluation.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-125">The customer can use this dialog box to submit a rating and a review.</span></span>
<span data-ttu-id="bdfa6-126">![Boîte de dialogue Écrire une évaluation](media/rnr-eCommerce-write-review-module.png) Le tableau suivant montre la propriété du module Écrire une évaluation qui doit être configurée dans l'outil de création.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-126">![Write a review dialog box](media/rnr-eCommerce-write-review-module.png) The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>
| <span data-ttu-id="bdfa6-127">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="bdfa6-127">Property name</span></span> | <span data-ttu-id="bdfa6-128">Valeur</span><span class="sxs-lookup"><span data-stu-id="bdfa6-128">Value</span></span>        | <span data-ttu-id="bdfa6-129">Description de la propriété</span><span class="sxs-lookup"><span data-stu-id="bdfa6-129">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="bdfa6-130">Nom</span><span class="sxs-lookup"><span data-stu-id="bdfa6-130">Name</span></span>          | <span data-ttu-id="bdfa6-131">Écrire une évaluation</span><span class="sxs-lookup"><span data-stu-id="bdfa6-131">Write review</span></span> | <span data-ttu-id="bdfa6-132">Nom du module Écrire une évaluation.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-132">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="bdfa6-133">Module d'histogramme de classements</span><span class="sxs-lookup"><span data-stu-id="bdfa6-133">Ratings histogram module</span></span>

<span data-ttu-id="bdfa6-134">Le module d'histogramme de classements affiche un histogramme de classements.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-134">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="bdfa6-135">Ce module s'affiche généralement entre le module Écrire une évaluation et le module de liste d'évaluations de produit sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-135">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>
<span data-ttu-id="bdfa6-136">Le module d'histogramme de classements ne requiert aucune configuration.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-136">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="bdfa6-137">Vous devez simplement ajouter le module dans modèle de page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-137">You just have to add the module in the PDP template.</span></span> <span data-ttu-id="bdfa6-138">Les illustrations suivantes présentent à quoi un modèle de page de détails de produit dans Dynamics 365 Commerce lorsque des modules de classements et d'évaluations sont configurés pour s'afficher sur les pages de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-138">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>
<span data-ttu-id="bdfa6-139">![Modèle de page de détails de produit lorsque les classements et les évaluations sont configurés pour s'afficher sur des pages de détails de produit](media/rnr-eCommerce-pdp-reviews-modules.png)</span><span class="sxs-lookup"><span data-stu-id="bdfa6-139">![PDP template when ratings and reviews are configured for display on PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)</span></span>

### <a name="product-reviews-list-module"></a><span data-ttu-id="bdfa6-140">Module Liste de classements de produit</span><span class="sxs-lookup"><span data-stu-id="bdfa6-140">Product reviews list module</span></span>

<span data-ttu-id="bdfa6-141">Le modules de liste d'évaluations de produit affiche une liste des évaluations de produit avec des options de tri, de filtre, et de numérotation de pages.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-141">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="bdfa6-142">Ce module s'affiche généralement après le module d'histogramme de classements sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-142">This module typically appears after the ratings histogram module on a PDP.</span></span>
<span data-ttu-id="bdfa6-143">Le tableau suivant montre les propriétés du module de liste d'évaluations de produits qui doivent être configurées dans l'outil de création.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-143">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="bdfa6-144">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="bdfa6-144">Property name</span></span>              | <span data-ttu-id="bdfa6-145">Valeur</span><span class="sxs-lookup"><span data-stu-id="bdfa6-145">Value</span></span> | <span data-ttu-id="bdfa6-146">Description de la propriété</span><span class="sxs-lookup"><span data-stu-id="bdfa6-146">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="bdfa6-147">Évaluations affichés sur chaque page</span><span class="sxs-lookup"><span data-stu-id="bdfa6-147">Reviews shown on each page</span></span> | <span data-ttu-id="bdfa6-148">10</span><span class="sxs-lookup"><span data-stu-id="bdfa6-148">10</span></span>    | <span data-ttu-id="bdfa6-149">Nombre d'évaluations qui doivent figurer à la fois sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-149">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="bdfa6-150">Les boutons **Suivant** et **Précédent** sont inclus, afin que les utilisateurs puissent circuler entre les pages d'évaluations.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-150">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="bdfa6-151">Histogramme de classements – Vue de synthèse</span><span class="sxs-lookup"><span data-stu-id="bdfa6-151">Ratings histogram – Summary view</span></span>

<span data-ttu-id="bdfa6-152">Le module de liste d'évaluations de produit inclut un emplacement dans lequel vous pouvez ajouter un module d'histogramme des classements.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-152">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="bdfa6-153">L'illustration ci-dessous indique comment vous pouvez ajouter un module d'histogramme de classements dans le module de liste d'évaluations de produit dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-153">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Ajout d'un module histogramme de classements dans un module de liste d'évaluations de produit](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a><span data-ttu-id="bdfa6-155">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="bdfa6-155">Additional resources</span></span>

[<span data-ttu-id="bdfa6-156">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="bdfa6-156">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="bdfa6-157">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="bdfa6-157">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="bdfa6-158">Module Panier</span><span class="sxs-lookup"><span data-stu-id="bdfa6-158">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="bdfa6-159">Module Validation</span><span class="sxs-lookup"><span data-stu-id="bdfa6-159">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="bdfa6-160">Module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="bdfa6-160">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="bdfa6-161">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="bdfa6-161">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="bdfa6-162">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="bdfa6-162">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]