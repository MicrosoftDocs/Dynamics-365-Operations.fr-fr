---
title: Présentation de la bibliothèque de modules
description: Cette rubrique présente une vue d'ensemble de la bibliothèque de modules Microsoft Dynamics 365 Commerce.
author: anupamar-ms
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: dfc52dd8e14bb2e9f2f9c026ee0e058aee4cedcb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412340"
---
# <a name="module-library-overview"></a><span data-ttu-id="753b2-103">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="753b2-103">Module library overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="753b2-104">Cette rubrique présente une vue d'ensemble de la bibliothèque de modules Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="753b2-104">This topic presents an overview of the Microsoft Dynamics 365 Commerce module library.</span></span>

## <a name="overview"></a><span data-ttu-id="753b2-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="753b2-105">Overview</span></span>

<span data-ttu-id="753b2-106">La bibliothèque de modules Dynamics 365 Commerce est une collection de modules qui peuvent être utilisés pour créer un site Web de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="753b2-106">The Dynamics 365 Commerce module library is a collection of modules that can be used to build an e-Commerce website.</span></span> <span data-ttu-id="753b2-107">Les modules ont des aspects de l'interface utilisateur et des aspects de comportement fonctionnel.</span><span class="sxs-lookup"><span data-stu-id="753b2-107">Modules have both user interface (UI) aspects and functional behavior aspects.</span></span>

<span data-ttu-id="753b2-108">Des thèmes peuvent être appliqués aux modules de la bibliothèque de modules pour modifier leur aspect.</span><span class="sxs-lookup"><span data-stu-id="753b2-108">Themes can be applied to the modules in the module library to change their look and feel.</span></span> <span data-ttu-id="753b2-109">Les thèmes utilisent des feuilles de style en cascade (CSS).</span><span class="sxs-lookup"><span data-stu-id="753b2-109">The themes use Cascading Style Sheets (CSS).</span></span> <span data-ttu-id="753b2-110">Un thème pour un site fictif de commerce électronique nommé « Fabrikam » est disponible dans le cadre de la bibliothèque de modules et peut être utilisé comme référence.</span><span class="sxs-lookup"><span data-stu-id="753b2-110">A theme for a fictitious e-Commerce site that is named "Fabrikam" is provided as part of the module library and can be used as a reference.</span></span>

## <a name="module-library-modules"></a><span data-ttu-id="753b2-111">Modules de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="753b2-111">Module library modules</span></span>

<span data-ttu-id="753b2-112">Les types de modules suivants sont fournis dans la bibliothèque de modules :</span><span class="sxs-lookup"><span data-stu-id="753b2-112">The following types of modules are provided in the module library:</span></span>

- <span data-ttu-id="753b2-113">**Module de conteneur** – Un module de conteneur est un module unique qui agit comme hôte pour d'autres modules.</span><span class="sxs-lookup"><span data-stu-id="753b2-113">**Container module** – A container module is a simple module that acts as a host for other modules.</span></span> <span data-ttu-id="753b2-114">Il contrôle la disposition des modules qui sont à l'intérieur de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="753b2-114">It controls the layout of the modules that are inside it.</span></span>
- <span data-ttu-id="753b2-115">**Modules de marketing** – Les modules de marketing incluent des modules de bloc de contenu, bloc de texte, lecteur vidéo et carrousel.</span><span class="sxs-lookup"><span data-stu-id="753b2-115">**Marketing modules** – Marketing modules include content block, text block, video player, and carousel modules.</span></span> <span data-ttu-id="753b2-116">Tous ces modules permettent de présenter du contenu.</span><span class="sxs-lookup"><span data-stu-id="753b2-116">All these modules can be used to showcase content.</span></span> <span data-ttu-id="753b2-117">Ils peuvent être placés sur n'importe quelle page et sont pilotés par les données du système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="753b2-117">They can be put on any page and are driven by data from the content management system (CMS).</span></span>
- <span data-ttu-id="753b2-118">**Modules d'en-tête et de pied de page** – Les modules d'en-tête et de pied de page s'affichent dans l'en-tête et le pied de page de toutes les pages du site.</span><span class="sxs-lookup"><span data-stu-id="753b2-118">**Header and footer modules** – Header and footer modules appear in the header and footer of all site pages.</span></span> <span data-ttu-id="753b2-119">Ces modules peuvent être configurés de la manière prescrite via les propriétés.</span><span class="sxs-lookup"><span data-stu-id="753b2-119">These modules can be configured as required through properties.</span></span>
- <span data-ttu-id="753b2-120">**Modules de recherche** – Les produits peuvent être détectés à l'aide de le module de recherche dans l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="753b2-120">**Search modules** – Products can be discovered by using the search module in the header.</span></span> <span data-ttu-id="753b2-121">Les résultats de la recherche s'affichent dans la page de résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="753b2-121">Search results appear on the search results page.</span></span> <span data-ttu-id="753b2-122">Les produits peuvent également être détectés dans les pages de catégorie, qui sont des pages dédiées à chaque catégorie prise en charge dans la hiérarchie de navigation du canal.</span><span class="sxs-lookup"><span data-stu-id="753b2-122">Products can also be discovered on category pages, which are dedicated pages for each category that is supported in the channel navigation hierarchy.</span></span> <span data-ttu-id="753b2-123">En outre, les modules de raffineur peuvent être utilisés pour filtrer davantage les résultats dans les résultats de la recherche et des pages de catégorie.</span><span class="sxs-lookup"><span data-stu-id="753b2-123">In addition, refiner modules can be used to further filter results on search results and category pages.</span></span>
- <span data-ttu-id="753b2-124">**Modules de page de détails des produits** – Les pages de détails de produit utilisent plusieurs modules pour afficher des informations sur le produit.</span><span class="sxs-lookup"><span data-stu-id="753b2-124">**Product details page modules** – Product details pages use several modules to show product information.</span></span> <span data-ttu-id="753b2-125">Le module de zone d'achat permet aux clients d'afficher les produits et de les ajouter au panier.</span><span class="sxs-lookup"><span data-stu-id="753b2-125">The buy box module lets customers view products and add them to the cart.</span></span> <span data-ttu-id="753b2-126">D'autres modules, comme le module des spécifications techniques, affichent les détails du produit.</span><span class="sxs-lookup"><span data-stu-id="753b2-126">Other modules, such as the tech specs module, show the product details.</span></span> <span data-ttu-id="753b2-127">Le module de classements et d'évaluations permet d'afficher et de fournir des évaluations.</span><span class="sxs-lookup"><span data-stu-id="753b2-127">The ratings and reviews module can used to view and provide reviews.</span></span>
- <span data-ttu-id="753b2-128">**Module Achat en ligne et prélèvement en magasin** – Le module Achat en ligne et prélèvement en magasin est intégré à Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="753b2-128">**Buy online pick up in store module** – The buy online pick up in store module is integrated with Bing Maps.</span></span> <span data-ttu-id="753b2-129">Il peut être utilisé pour rechercher des magasins à proximité où les clients peuvent prélever les produits qu'ils ont achetés.</span><span class="sxs-lookup"><span data-stu-id="753b2-129">It can be used to find nearby stores where customers can pick up products that they have purchased.</span></span>
- <span data-ttu-id="753b2-130">**Modules d'achat** – Les modules d'achat sont le module de panier, qui permet d'ajouter des articles au panier.</span><span class="sxs-lookup"><span data-stu-id="753b2-130">**Purchase modules** – Purchase modules include the cart module, which can be used to add items to the cart.</span></span> <span data-ttu-id="753b2-131">Le module de caisse capture l'adresse d'expédition, les options de livraison, et la carte cadeau, le programme de fidélité, et les informations de carte de crédit, afin que la commande puisse être traitée.</span><span class="sxs-lookup"><span data-stu-id="753b2-131">The checkout module captures the shipping address, delivery options, and gift card, loyalty program, and credit card information, so that an order can be processed.</span></span> <span data-ttu-id="753b2-132">Une fois la commande passée, le module de confirmation de commande peut être utilisé pour indiquer les détails de la confirmation.</span><span class="sxs-lookup"><span data-stu-id="753b2-132">After an order is placed, the order confirmation module can be used to show the confirmation details.</span></span>
- <span data-ttu-id="753b2-133">**Modules de gestion de compte** – Le module de connexion permet aux clients de se connecter à un compte existant, et le module d'inscription de créer un compte.</span><span class="sxs-lookup"><span data-stu-id="753b2-133">**Account management modules** – The sign-in module lets customers sign in to an existing account, and the sign-up module lets them create a new account.</span></span> <span data-ttu-id="753b2-134">Une fois qu'un compte est créé, le module d'historique de commande peut être utilisé pour afficher les commandes récentes, et le module de détails de commande peut être utilisé pour afficher les détails de la commande.</span><span class="sxs-lookup"><span data-stu-id="753b2-134">After an account is created, the order history module can be used to view recent orders, and the order details module can be used to view order details.</span></span>
- <span data-ttu-id="753b2-135">**Module de recommandations** – Les recommandations sont affichées à l'aide du module de placement de produit.</span><span class="sxs-lookup"><span data-stu-id="753b2-135">**Recommendations module** – Recommendations are shown by using the product placement module.</span></span> <span data-ttu-id="753b2-136">Ce module prend en charge les listes algorithmiques et éditoriales pouvant être affichées sur n'importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="753b2-136">This module supports algorithmic and editorial lists that can be showcased on any page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="753b2-137">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="753b2-137">Additional resources</span></span>

[<span data-ttu-id="753b2-138">Module Container</span><span class="sxs-lookup"><span data-stu-id="753b2-138">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="753b2-139">Module Zone d'achat</span><span class="sxs-lookup"><span data-stu-id="753b2-139">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="753b2-140">Module Panier</span><span class="sxs-lookup"><span data-stu-id="753b2-140">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="753b2-141">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="753b2-141">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="753b2-142">Module Confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="753b2-142">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="753b2-143">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="753b2-143">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="753b2-144">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="753b2-144">Footer module</span></span>](author-footer-module.md)
