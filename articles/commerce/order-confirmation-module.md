---
title: Module Confirmation de commande
description: Cette rubrique couvre les modules de confirmation de commande et décrit leur création dans Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698324"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="e1e4b-103">Module Confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="e1e4b-103">Order confirmation module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e1e4b-104">Cette rubrique couvre les modules de confirmation de commande et décrit leur création dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-104">This topic covers order confirmation modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e1e4b-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="e1e4b-105">Overview</span></span>

<span data-ttu-id="e1e4b-106">Un module de confirmation de commande est utilisé pour afficher un message de confirmation sur une page de confirmation de commande après une commande passée.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-106">An order confirmation module is used to show a confirmation message on an order confirmation page after an order is placed.</span></span> <span data-ttu-id="e1e4b-107">Le module de confirmation de commande affiche le numéro de confirmation de la commande et l'adresse e-mail du client qui a été fournie lors de l'extraction.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-107">The order confirmation module shows the order confirmation number and the customer email address that was provided during checkout.</span></span>

<span data-ttu-id="e1e4b-108">Lorsqu'une commande est effectuée lors de l'extraction, le numéro confirmation de commande et l'adresse e-mail du client sont transférés vers la page de confirmation de commande comme une chaîne de requête dans l'URL de la page.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-108">When an order is placed during checkout, the order confirmation number and customer email address are passed to the order confirmation page as a query string in the page's URL.</span></span> <span data-ttu-id="e1e4b-109">Le module de confirmation de commande reçoit ces informations et affiche le statut de la commande sur la page de confirmation de commande.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-109">The order confirmation module receives this information and renders the order status on the order confirmation page.</span></span> <span data-ttu-id="e1e4b-110">Le module de confirmation de commande nécessite ce contexte de page pour fournir le statut de la commande.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-110">The order confirmation module requires this page context to provide the status of the order.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="e1e4b-111">Propriétés du module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="e1e4b-111">Order confirmation module properties</span></span>

| <span data-ttu-id="e1e4b-112">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="e1e4b-112">Property name</span></span> | <span data-ttu-id="e1e4b-113">Valeurs</span><span class="sxs-lookup"><span data-stu-id="e1e4b-113">Values</span></span> | <span data-ttu-id="e1e4b-114">Description</span><span class="sxs-lookup"><span data-stu-id="e1e4b-114">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="e1e4b-115">En-tête</span><span class="sxs-lookup"><span data-stu-id="e1e4b-115">Heading</span></span>       | <span data-ttu-id="e1e4b-116">Texte d'en-tête et balise d'en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="e1e4b-116">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="e1e4b-117">Le module de confirmation de commande peut avoir un en-tête.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-117">The order confirmation module can have a heading.</span></span> <span data-ttu-id="e1e4b-118">Par défaut, la balise d'en-tête **H2** sert pour l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-118">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="e1e4b-119">Toutefois, la balise peut être modifiée pour satisfaire aux exigences d'accessibilité.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-119">However, the tag can be changed to meet accessibility requirements.</span></span> |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a><span data-ttu-id="e1e4b-120">Modules qui peuvent être utilisés dans un module de page de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="e1e4b-120">Modules that can be used in an order confirmation page module</span></span> 

- <span data-ttu-id="e1e4b-121">**Recommandations** – Le module de recommandations peut être placé sur la page de confirmation de commande pour suggérer d'autres produits au client.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-121">**Recommendations** – The recommendations module can be put on the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="e1e4b-122">**Marketing** – Le module de marketing peut ajouter du contenu marketing à la page de confirmation de commande.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-122">**Marketing** – The marketing module can add marketing content to the order confirmation page.</span></span>

## <a name="create-an-order-confirmation-page-module"></a><span data-ttu-id="e1e4b-123">Créer un module de page de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="e1e4b-123">Create an order confirmation page module</span></span>

1. <span data-ttu-id="e1e4b-124">Créez un modèle de page nommé **modèle de confirmation de commande**.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-124">Create a page template that is named **order confirmation template**.</span></span>
1. <span data-ttu-id="e1e4b-125">À l'emplacement **Principal** de la page par défaut, ajoutez un module de confirmation de commande.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-125">In the **Main** slot of the default page, add an order confirmation module.</span></span>
1. <span data-ttu-id="e1e4b-126">Dans le module de confirmation de commande, ajoutez un module de recommandations.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-126">In the order confirmation module, add a recommendations module.</span></span>
1. <span data-ttu-id="e1e4b-127">Enregistrez et affichez un aperçu du modèle.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-127">Save and preview the template.</span></span> <span data-ttu-id="e1e4b-128">Le module de confirmation de commande ne doit pas être affiché, car il nécessite le contexte du numéro de confirmation de commande.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-128">The order confirmation module should not be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="e1e4b-129">Archivez le modèle, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-129">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="e1e4b-130">Utilisez le modèle de confirmation de commande que vous venez de créer pour créer une page qui s'appelle **page Confirmation de commande**.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-130">Use the order confirmation template that you just created to create a page that is named **order confirmation page**.</span></span>
1. <span data-ttu-id="e1e4b-131">Ajoutez la page par défaut au contour de page.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-131">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="e1e4b-132">À l'emplacement **En-tête**, ajoutez un fragment d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-132">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="e1e4b-133">À l'emplacement **Pied de page**, ajoutez un fragment de pied de page.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-133">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="e1e4b-134">À l'emplacement **Principal**, ajoutez un module de confirmation de commande.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-134">In the **Main** slot, add an order confirmation module.</span></span>
1. <span data-ttu-id="e1e4b-135">Dans le volet de propriété du module de confirmation de commande, ajoutez l'en-tête **Confirmation de commande**.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-135">In the property pane of the order confirmation module, add the heading **Order confirmation**.</span></span>
1. <span data-ttu-id="e1e4b-136">Sous le module de confirmation de commande, ajoutez un module de recommandations, et configurez-le afin qu'il utilise les paramètres **Nouveau** et **Meilleure vente**.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-136">Below the order confirmation module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="e1e4b-137">Enregistrez et afficher un aperçu de la page, archivez-le, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="e1e4b-137">Save and preview the page, check it in, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e1e4b-138">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e1e4b-138">Additional resources</span></span>

[<span data-ttu-id="e1e4b-139">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="e1e4b-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="e1e4b-140">Module Container</span><span class="sxs-lookup"><span data-stu-id="e1e4b-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="e1e4b-141">Module Zone d'achat</span><span class="sxs-lookup"><span data-stu-id="e1e4b-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="e1e4b-142">Module Panier</span><span class="sxs-lookup"><span data-stu-id="e1e4b-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="e1e4b-143">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="e1e4b-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="e1e4b-144">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="e1e4b-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="e1e4b-145">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="e1e4b-145">Footer module</span></span>](author-footer-module.md)
