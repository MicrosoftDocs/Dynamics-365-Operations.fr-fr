---
title: Configuration des évaluations et avis
description: Cette rubrique décrit la procédure de configuration de votre site de commerce électronique pour afficher les classements et les évaluations des clients dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0612b32e7751b32ad851f627a53bce2ac491870f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770479"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="a9502-103">Configuration des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="a9502-103">Configure ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a9502-104">Cette rubrique décrit la procédure de configuration de votre site de commerce électronique pour afficher les classements et les évaluations des clients dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a9502-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a9502-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="a9502-105">Overview</span></span>

<span data-ttu-id="a9502-106">Les classements et les évaluations des sites web de commerce électronique permettent aux clients d'en savoir plus sur les produits avant de prendre une décision d'achat, en leur affichant ce que d'autres clients pensent de ces produits.</span><span class="sxs-lookup"><span data-stu-id="a9502-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, by showing them what other customers think about those products.</span></span> <span data-ttu-id="a9502-107">Pour les sites web de commerce électronique, les classements et les évaluations sont également un mécanisme de collecte des commentaires des clients sur les produits.</span><span class="sxs-lookup"><span data-stu-id="a9502-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="a9502-108">Les classements sont affichés dans les pages de liste de produit, les pages de liste de catégorie, les pages de résultats de la recherche, et d'autres pages du site.</span><span class="sxs-lookup"><span data-stu-id="a9502-108">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> <span data-ttu-id="a9502-109">Les histogrammes de classement et les évaluations de produits sont affichés sur les pages de détails des produits.</span><span class="sxs-lookup"><span data-stu-id="a9502-109">Ratings histograms and product reviews are shown on product details pages (PDPs).</span></span> <span data-ttu-id="a9502-110">Un bouton **Écrire une évaluation** permet aux clients envoyer des classements et les évaluations d'un produit.</span><span class="sxs-lookup"><span data-stu-id="a9502-110">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="a9502-111">Modules de classements et d'évaluations sur les pages de détails des produits</span><span class="sxs-lookup"><span data-stu-id="a9502-111">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="a9502-112">Trois modules affichent le récapitulatif des classements et des évaluations sur les pages de détails des produits :</span><span class="sxs-lookup"><span data-stu-id="a9502-112">Three modules show the ratings and reviews summary on PDPs:</span></span>

- <span data-ttu-id="a9502-113">Module Écrire une évaluation</span><span class="sxs-lookup"><span data-stu-id="a9502-113">Write review module</span></span>
- <span data-ttu-id="a9502-114">Module Liste de classements de produit</span><span class="sxs-lookup"><span data-stu-id="a9502-114">Product reviews list module</span></span>
- <span data-ttu-id="a9502-115">Module d'histogramme de classements</span><span class="sxs-lookup"><span data-stu-id="a9502-115">Ratings histogram module</span></span>
 
<span data-ttu-id="a9502-116">L'illustration suivante présente à quoi les modules de classements et d'évaluation ressemble sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="a9502-116">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Modules de classements et d'évaluations sur une page de détails de produit](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="a9502-118">Pour plus d'informations sur la procédure d'optimisation des modèles et des dispositions de page de détails de produit afin de partager les configurations des modules de classements et d'évaluation entre plusieurs pages de détails des produits sur votre site de commerce électronique, voir [Vue d'ensemble des modèles et dispositions](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a9502-118">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="a9502-119">L'illustration ci-dessous indique comment la boîte de dialogue **Ajouter un module** présente les modules de classements et d'évaluation dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a9502-119">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>

![Boîte de dialogue Ajouter un module](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a><span data-ttu-id="a9502-121">Module Écrire une évaluation</span><span class="sxs-lookup"><span data-stu-id="a9502-121">Write review module</span></span>

<span data-ttu-id="a9502-122">Le module Écrire une évaluation inclut un bouton **Écrire une évaluation** qui permet aux utilisateurs de se connecter, d'affecter un classement, et d'écrire une évaluation de produit.</span><span class="sxs-lookup"><span data-stu-id="a9502-122">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="a9502-123">Ce module permet également aux utilisateurs de modifier un classement ou une évaluation qu'il a précédemment soumis.</span><span class="sxs-lookup"><span data-stu-id="a9502-123">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="a9502-124">Ce module apparaît généralement au-dessus des modules d'histogramme des classements et de liste d'évaluations de produit sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="a9502-124">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>

<span data-ttu-id="a9502-125">L'illustration suivante présente la boîte de dialogue **Écrire une évaluation** qui s'affiche lorsqu'un client sélectionne **Écrire une évaluation**.</span><span class="sxs-lookup"><span data-stu-id="a9502-125">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="a9502-126">Le client peut utiliser cette boîte de dialogue pour envoyer un classement et une évaluation.</span><span class="sxs-lookup"><span data-stu-id="a9502-126">The customer can use this dialog box to submit a rating and a review.</span></span>

![Boîte de dialogue Écrire une évaluation](media/rnr-eCommerce-write-review-module.png)

<span data-ttu-id="a9502-128">Le tableau suivant montre la propriété du module Écrire une évaluation qui doit être configurée dans l'outil de création.</span><span class="sxs-lookup"><span data-stu-id="a9502-128">The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>

| <span data-ttu-id="a9502-129">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="a9502-129">Property name</span></span> | <span data-ttu-id="a9502-130">Valeur</span><span class="sxs-lookup"><span data-stu-id="a9502-130">Value</span></span>        | <span data-ttu-id="a9502-131">Description de la propriété</span><span class="sxs-lookup"><span data-stu-id="a9502-131">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="a9502-132">Nom</span><span class="sxs-lookup"><span data-stu-id="a9502-132">Name</span></span>          | <span data-ttu-id="a9502-133">Écrire une évaluation</span><span class="sxs-lookup"><span data-stu-id="a9502-133">Write review</span></span> | <span data-ttu-id="a9502-134">Nom du module Écrire une évaluation.</span><span class="sxs-lookup"><span data-stu-id="a9502-134">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="a9502-135">Module d'histogramme de classements</span><span class="sxs-lookup"><span data-stu-id="a9502-135">Ratings histogram module</span></span>

<span data-ttu-id="a9502-136">Le module d'histogramme de classements affiche un histogramme de classements.</span><span class="sxs-lookup"><span data-stu-id="a9502-136">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="a9502-137">Ce module s'affiche généralement entre le module Écrire une évaluation et le module de liste d'évaluations de produit sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="a9502-137">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>

<span data-ttu-id="a9502-138">Le module d'histogramme de classements ne requiert aucune configuration.</span><span class="sxs-lookup"><span data-stu-id="a9502-138">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="a9502-139">Vous devez simplement ajouter le module dans modèle de page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="a9502-139">You just have to add the module in the PDP template.</span></span> 

<span data-ttu-id="a9502-140">Les illustrations suivantes présentent à quoi un modèle de page de détails de produit dans Dynamics 365 Commerce lorsque des modules de classements et d'évaluations sont configurés pour s'afficher sur les pages de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="a9502-140">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>

![Modèle de page de détails de produit lorsque les classements et les évaluations sont configurés pour s'afficher sur des pages de détails de produit](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a><span data-ttu-id="a9502-142">Module Liste de classements de produit</span><span class="sxs-lookup"><span data-stu-id="a9502-142">Product reviews list module</span></span>

<span data-ttu-id="a9502-143">Le modules de liste d'évaluations de produit affiche une liste des évaluations de produit avec des options de tri, de filtre, et de numérotation de pages.</span><span class="sxs-lookup"><span data-stu-id="a9502-143">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="a9502-144">Ce module s'affiche généralement après le module d'histogramme de classements sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="a9502-144">This module typically appears after the ratings histogram module on a PDP.</span></span>

<span data-ttu-id="a9502-145">Le tableau suivant montre les propriétés du module de liste d'évaluations de produits qui doivent être configurées dans l'outil de création.</span><span class="sxs-lookup"><span data-stu-id="a9502-145">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="a9502-146">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="a9502-146">Property name</span></span>              | <span data-ttu-id="a9502-147">Valeur</span><span class="sxs-lookup"><span data-stu-id="a9502-147">Value</span></span> | <span data-ttu-id="a9502-148">Description de la propriété</span><span class="sxs-lookup"><span data-stu-id="a9502-148">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="a9502-149">Évaluations affichés sur chaque page</span><span class="sxs-lookup"><span data-stu-id="a9502-149">Reviews shown on each page</span></span> | <span data-ttu-id="a9502-150">10</span><span class="sxs-lookup"><span data-stu-id="a9502-150">10</span></span>    | <span data-ttu-id="a9502-151">Nombre d'évaluations qui doivent figurer à la fois sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="a9502-151">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="a9502-152">Les boutons **Suivant** et **Précédent** sont inclus, afin que les utilisateurs puissent circuler entre les pages d'évaluations.</span><span class="sxs-lookup"><span data-stu-id="a9502-152">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="a9502-153">Histogramme de classements – Vue de synthèse</span><span class="sxs-lookup"><span data-stu-id="a9502-153">Ratings histogram – Summary view</span></span>

<span data-ttu-id="a9502-154">Le module de liste d'évaluations de produit inclut un emplacement dans lequel vous pouvez ajouter un module d'histogramme des classements.</span><span class="sxs-lookup"><span data-stu-id="a9502-154">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="a9502-155">L'illustration ci-dessous indique comment vous pouvez ajouter un module d'histogramme de classements dans le module de liste d'évaluations de produit dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a9502-155">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Ajout d'un module histogramme de classements dans un module de liste d'évaluations de produit](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="a9502-157">Configuration d'un site pour afficher des classements et des évaluations</span><span class="sxs-lookup"><span data-stu-id="a9502-157">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="a9502-158">Les valeurs de configuration pour les classements et les évaluations, telles que l'ID client, vérifier la longueur du texte, et analyser la longueur du titre, sont configurées au niveau de le site.</span><span class="sxs-lookup"><span data-stu-id="a9502-158">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="a9502-159">Pour configurer un site afin d'afficher des classements et des évaluations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a9502-159">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="a9502-160">Accédez à **Accueil \> Sites**.</span><span class="sxs-lookup"><span data-stu-id="a9502-160">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="a9502-161">Sélectionnez le nom de votre site.</span><span class="sxs-lookup"><span data-stu-id="a9502-161">Select the name of your site.</span></span> 
1. <span data-ttu-id="a9502-162">Accédez à **Gestion du site \> Extensibilité**.</span><span class="sxs-lookup"><span data-stu-id="a9502-162">Go to **Site management \> Extensibility**.</span></span> 
1. <span data-ttu-id="a9502-163">Dans le champ **Vérifier la longueur maximale du texte**, entrez le nombre maximal de caractères que le texte d'évaluation peut comporter (par exemple, **1 000**).</span><span class="sxs-lookup"><span data-stu-id="a9502-163">In the **Review Text Max Length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="a9502-164">Dans le champ **Vérifier la longueur maximale du titre**, entrez le nombre maximal de caractères que les titres d'évaluation peuvent comporter (par exemple, **55**).</span><span class="sxs-lookup"><span data-stu-id="a9502-164">In the **Review Title Max Length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="a9502-165">Sélectionnez **Enregistrer et publier**.</span><span class="sxs-lookup"><span data-stu-id="a9502-165">Select **Save and Publish**.</span></span> 

<span data-ttu-id="a9502-166">L'illustration suivante présente à quoi cette configuration ressemble dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a9502-166">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configuration d'un site pour afficher des classements et des évaluations](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="a9502-168">Association d'un classement de produit à la section Évaluation d'une page de détails de produit</span><span class="sxs-lookup"><span data-stu-id="a9502-168">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="a9502-169">Un classement de produit apparaît sous le titre de produit en haut de la page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="a9502-169">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="a9502-170">Le classement de produit peut être configuré pour qu'il soit lié à la section **Évaluations** de la même page de détails du produit.</span><span class="sxs-lookup"><span data-stu-id="a9502-170">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="a9502-171">Pour lier un classement de produit à la section **Évaluations** de la page de détails de produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a9502-171">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="a9502-172">Ouvrez le modèle de page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="a9502-172">Open the PDP template.</span></span> 
1. <span data-ttu-id="a9502-173">Accédez à **Paramètres du module de conteneur Zone d'achat**.</span><span class="sxs-lookup"><span data-stu-id="a9502-173">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="a9502-174">Sous **Zone d'achat**, sélectionnez **Classements de produit**, puis activez la case à cocher **Lier le clic au module complet d'évaluations**.</span><span class="sxs-lookup"><span data-stu-id="a9502-174">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="a9502-175">L'illustration suivante présente à quoi cette configuration ressemble dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a9502-175">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Association d'un classement de produit à la section Évaluation d'une page de détails de produit](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="a9502-177">Configurer le lien de la page de confidentialité et de politique</span><span class="sxs-lookup"><span data-stu-id="a9502-177">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="a9502-178">Pour configurer le lien de la page de confidentialité et de politique, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a9502-178">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="a9502-179">Accédez à **Accueil \> Sites**.</span><span class="sxs-lookup"><span data-stu-id="a9502-179">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="a9502-180">Sélectionnez le nom de votre site.</span><span class="sxs-lookup"><span data-stu-id="a9502-180">Select the name of your site.</span></span> 
1. <span data-ttu-id="a9502-181">Accédez à **Gestion du site \> Extensibilité**</span><span class="sxs-lookup"><span data-stu-id="a9502-181">Go to **Site management \> Extensibility**</span></span>
1. <span data-ttu-id="a9502-182">Dans l'onglet **Acheminements**, sous **Confidentialité et politique RNR**, sélectionnez **Ajouter un lien**.</span><span class="sxs-lookup"><span data-stu-id="a9502-182">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="a9502-183">Si un lien est déjà entré, et si vous souhaitez le remplacer, sélectionnez le lien.</span><span class="sxs-lookup"><span data-stu-id="a9502-183">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="a9502-184">Dans la boîte de dialogue **Ajouter un lien**, sélectionnez le lien de la page de confidentialité et de politique, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9502-184">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="a9502-185">Sélectionnez **Enregistrer et publier**.</span><span class="sxs-lookup"><span data-stu-id="a9502-185">Select **Save and Publish**.</span></span> 

<span data-ttu-id="a9502-186">L'illustration suivante présente à quoi cette configuration ressemble dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a9502-186">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configuration du lien de la page de confidentialité et de politique](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a><span data-ttu-id="a9502-188">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a9502-188">Additional resources</span></span>

[<span data-ttu-id="a9502-189">Vue d'ensemble des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="a9502-189">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="a9502-190">Choix d'utilisation des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="a9502-190">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="a9502-191">Gestion des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="a9502-191">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="a9502-192">Synchronisation des évaluations de produit dans Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="a9502-192">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
