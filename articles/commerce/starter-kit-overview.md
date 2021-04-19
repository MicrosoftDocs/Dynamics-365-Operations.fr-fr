---
title: Vue d’ensemble de la bibliothèque de modules
description: Cette rubrique présente une vue d’ensemble de la bibliothèque de modules Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76fd75c2ed9a3ba4728129b77a43b50267be3bf3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795331"
---
# <a name="module-library-overview"></a><span data-ttu-id="c38f1-103">Vue d’ensemble de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="c38f1-103">Module library overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c38f1-104">Cette rubrique présente une vue d’ensemble de la bibliothèque de modules Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c38f1-104">This topic presents an overview of the Microsoft Dynamics 365 Commerce module library.</span></span>

<span data-ttu-id="c38f1-105">La bibliothèque de modules Dynamics 365 Commerce est une collection de modules qui peuvent être utilisés pour créer un site Web de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="c38f1-105">The Dynamics 365 Commerce module library is a collection of modules that can be used to build an e-Commerce website.</span></span> <span data-ttu-id="c38f1-106">Les modules ont des aspects de l’interface utilisateur et des aspects de comportement fonctionnel.</span><span class="sxs-lookup"><span data-stu-id="c38f1-106">Modules have both user interface (UI) aspects and functional behavior aspects.</span></span>

<span data-ttu-id="c38f1-107">Des thèmes peuvent être appliqués aux modules de la bibliothèque de modules pour modifier leur aspect.</span><span class="sxs-lookup"><span data-stu-id="c38f1-107">Themes can be applied to the modules in the module library to change their look and feel.</span></span> <span data-ttu-id="c38f1-108">Les thèmes utilisent des feuilles de style en cascade (CSS).</span><span class="sxs-lookup"><span data-stu-id="c38f1-108">The themes use Cascading Style Sheets (CSS).</span></span> <span data-ttu-id="c38f1-109">Un thème pour un site fictif de commerce électronique nommé « Fabrikam » est disponible dans le cadre de la bibliothèque de modules et peut être utilisé comme référence.</span><span class="sxs-lookup"><span data-stu-id="c38f1-109">A theme for a fictitious e-Commerce site that is named "Fabrikam" is provided as part of the module library and can be used as a reference.</span></span>

## <a name="module-library-modules"></a><span data-ttu-id="c38f1-110">Modules de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="c38f1-110">Module library modules</span></span>

<span data-ttu-id="c38f1-111">Les types de modules suivants sont fournis dans la bibliothèque de modules :</span><span class="sxs-lookup"><span data-stu-id="c38f1-111">The following types of modules are provided in the module library:</span></span>

- <span data-ttu-id="c38f1-112">**Module de conteneur** – Un module de conteneur est un module unique qui agit comme hôte pour d’autres modules.</span><span class="sxs-lookup"><span data-stu-id="c38f1-112">**Container module** – A container module is a simple module that acts as a host for other modules.</span></span> <span data-ttu-id="c38f1-113">Il contrôle la disposition des modules qui sont à l’intérieur de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="c38f1-113">It controls the layout of the modules that are inside it.</span></span>
- <span data-ttu-id="c38f1-114">**Modules de marketing** – Les modules de marketing incluent des modules de bloc de contenu, bloc de texte, lecteur vidéo et carrousel.</span><span class="sxs-lookup"><span data-stu-id="c38f1-114">**Marketing modules** – Marketing modules include content block, text block, video player, and carousel modules.</span></span> <span data-ttu-id="c38f1-115">Tous ces modules permettent de présenter du contenu.</span><span class="sxs-lookup"><span data-stu-id="c38f1-115">All these modules can be used to showcase content.</span></span> <span data-ttu-id="c38f1-116">Ils peuvent être placés sur n’importe quelle page et sont pilotés par les données du système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="c38f1-116">They can be put on any page and are driven by data from the content management system (CMS).</span></span>
- <span data-ttu-id="c38f1-117">**Modules d’en-tête et de pied de page** – Les modules d’en-tête et de pied de page s’affichent dans l’en-tête et le pied de page de toutes les pages du site.</span><span class="sxs-lookup"><span data-stu-id="c38f1-117">**Header and footer modules** – Header and footer modules appear in the header and footer of all site pages.</span></span> <span data-ttu-id="c38f1-118">Ces modules peuvent être configurés de la manière prescrite via les propriétés.</span><span class="sxs-lookup"><span data-stu-id="c38f1-118">These modules can be configured as required through properties.</span></span>
- <span data-ttu-id="c38f1-119">**Modules de recherche** – Les produits peuvent être détectés à l’aide de le module de recherche dans l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="c38f1-119">**Search modules** – Products can be discovered by using the search module in the header.</span></span> <span data-ttu-id="c38f1-120">Les résultats de la recherche s’affichent dans la page de résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="c38f1-120">Search results appear on the search results page.</span></span> <span data-ttu-id="c38f1-121">Les produits peuvent également être détectés dans les pages de catégorie, qui sont des pages dédiées à chaque catégorie prise en charge dans la hiérarchie de navigation du canal.</span><span class="sxs-lookup"><span data-stu-id="c38f1-121">Products can also be discovered on category pages, which are dedicated pages for each category that is supported in the channel navigation hierarchy.</span></span> <span data-ttu-id="c38f1-122">En outre, les modules de raffineur peuvent être utilisés pour filtrer davantage les résultats dans les résultats de la recherche et des pages de catégorie.</span><span class="sxs-lookup"><span data-stu-id="c38f1-122">In addition, refiner modules can be used to further filter results on search results and category pages.</span></span>
- <span data-ttu-id="c38f1-123">**Modules de page de détails des produits** – Les pages de détails de produit utilisent plusieurs modules pour afficher des informations sur le produit.</span><span class="sxs-lookup"><span data-stu-id="c38f1-123">**Product details page modules** – Product details pages use several modules to show product information.</span></span> <span data-ttu-id="c38f1-124">Le module de zone d’achat permet aux clients d’afficher les produits et de les ajouter au panier.</span><span class="sxs-lookup"><span data-stu-id="c38f1-124">The buy box module lets customers view products and add them to the cart.</span></span> <span data-ttu-id="c38f1-125">D’autres modules, comme le module des spécifications techniques, affichent les détails du produit.</span><span class="sxs-lookup"><span data-stu-id="c38f1-125">Other modules, such as the tech specs module, show the product details.</span></span> <span data-ttu-id="c38f1-126">Le module de classements et d’évaluations permet d’afficher et de fournir des évaluations.</span><span class="sxs-lookup"><span data-stu-id="c38f1-126">The ratings and reviews module can used to view and provide reviews.</span></span>
- <span data-ttu-id="c38f1-127">**Module Achat en ligne et prélèvement en magasin** – Le module Achat en ligne et prélèvement en magasin est intégré à Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="c38f1-127">**Buy online pick up in store module** – The buy online pick up in store module is integrated with Bing Maps.</span></span> <span data-ttu-id="c38f1-128">Il peut être utilisé pour rechercher des magasins à proximité où les clients peuvent prélever les produits qu’ils ont achetés.</span><span class="sxs-lookup"><span data-stu-id="c38f1-128">It can be used to find nearby stores where customers can pick up products that they have purchased.</span></span>
- <span data-ttu-id="c38f1-129">**Modules d’achat** – Les modules d’achat sont le module de panier, qui permet d’ajouter des articles au panier.</span><span class="sxs-lookup"><span data-stu-id="c38f1-129">**Purchase modules** – Purchase modules include the cart module, which can be used to add items to the cart.</span></span> <span data-ttu-id="c38f1-130">Le module de caisse capture l’adresse d’expédition, les options de livraison, et la carte cadeau, le programme de fidélité, et les informations de carte de crédit, afin que la commande puisse être traitée.</span><span class="sxs-lookup"><span data-stu-id="c38f1-130">The checkout module captures the shipping address, delivery options, and gift card, loyalty program, and credit card information, so that an order can be processed.</span></span> <span data-ttu-id="c38f1-131">Une fois la commande passée, le module de confirmation de commande peut être utilisé pour indiquer les détails de la confirmation.</span><span class="sxs-lookup"><span data-stu-id="c38f1-131">After an order is placed, the order confirmation module can be used to show the confirmation details.</span></span>
- <span data-ttu-id="c38f1-132">**Modules de gestion de compte** – Le module de connexion permet aux clients de se connecter à un compte existant, et le module d’inscription de créer un compte.</span><span class="sxs-lookup"><span data-stu-id="c38f1-132">**Account management modules** – The sign-in module lets customers sign in to an existing account, and the sign-up module lets them create a new account.</span></span> <span data-ttu-id="c38f1-133">Une fois qu’un compte est créé, le module d’historique de commande peut être utilisé pour afficher les commandes récentes, et le module de détails de commande peut être utilisé pour afficher les détails de la commande.</span><span class="sxs-lookup"><span data-stu-id="c38f1-133">After an account is created, the order history module can be used to view recent orders, and the order details module can be used to view order details.</span></span>
- <span data-ttu-id="c38f1-134">**Module de recommandations** – Les recommandations sont affichées à l’aide du module de placement de produit.</span><span class="sxs-lookup"><span data-stu-id="c38f1-134">**Recommendations module** – Recommendations are shown by using the product placement module.</span></span> <span data-ttu-id="c38f1-135">Ce module prend en charge les listes algorithmiques et éditoriales pouvant être affichées sur n’importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="c38f1-135">This module supports algorithmic and editorial lists that can be showcased on any page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c38f1-136">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c38f1-136">Additional resources</span></span>

[<span data-ttu-id="c38f1-137">Module Container</span><span class="sxs-lookup"><span data-stu-id="c38f1-137">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="c38f1-138">Module Zone d’achat</span><span class="sxs-lookup"><span data-stu-id="c38f1-138">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="c38f1-139">Module Panier</span><span class="sxs-lookup"><span data-stu-id="c38f1-139">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c38f1-140">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="c38f1-140">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c38f1-141">Module Confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="c38f1-141">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="c38f1-142">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="c38f1-142">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="c38f1-143">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="c38f1-143">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]