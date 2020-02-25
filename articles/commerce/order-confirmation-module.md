---
title: Module des détails de la commande
description: Cette rubrique aborde les modules des détails de la commande et explique comment les utiliser dans Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026015"
---
# <a name="order-details-module"></a><span data-ttu-id="6f516-103">Module des détails de la commande</span><span class="sxs-lookup"><span data-stu-id="6f516-103">Order details module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6f516-104">Cette rubrique aborde les modules des détails de la commande et explique comment les utiliser dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6f516-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6f516-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="6f516-105">Overview</span></span>

<span data-ttu-id="6f516-106">Le module des détails de la commande permet d'afficher les détails de confirmation de commande une fois la commande passée.</span><span class="sxs-lookup"><span data-stu-id="6f516-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="6f516-107">Il indique l'ID de confirmation de la commande, les coordonnées de contact de la commande et d'autres détails de commande comme les articles achetés, les informations de paiement et le mode d'expédition.</span><span class="sxs-lookup"><span data-stu-id="6f516-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="6f516-108">Propriétés du module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="6f516-108">Order confirmation module properties</span></span>

| <span data-ttu-id="6f516-109">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="6f516-109">Property name</span></span>  | <span data-ttu-id="6f516-110">Valeurs</span><span class="sxs-lookup"><span data-stu-id="6f516-110">Values</span></span> | <span data-ttu-id="6f516-111">Description</span><span class="sxs-lookup"><span data-stu-id="6f516-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="6f516-112">En-tête</span><span class="sxs-lookup"><span data-stu-id="6f516-112">Heading</span></span>        | <span data-ttu-id="6f516-113">Texte d'en-tête et balise d'en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="6f516-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="6f516-114">Le module de confirmation de commande peut avoir un en-tête.</span><span class="sxs-lookup"><span data-stu-id="6f516-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="6f516-115">Par défaut, la balise d'en-tête **H2** sert pour l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="6f516-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="6f516-116">Toutefois, la balise peut être modifiée pour satisfaire aux exigences d'accessibilité.</span><span class="sxs-lookup"><span data-stu-id="6f516-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="6f516-117">Numéro du contact</span><span class="sxs-lookup"><span data-stu-id="6f516-117">Contact number</span></span> | <span data-ttu-id="6f516-118">Texte</span><span class="sxs-lookup"><span data-stu-id="6f516-118">Text</span></span> | <span data-ttu-id="6f516-119">Un numéro de contact peut être fourni pour les questions liées à la commande.</span><span class="sxs-lookup"><span data-stu-id="6f516-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="6f516-120">Modules pouvant être utilisés dans une page de détails de la commande</span><span class="sxs-lookup"><span data-stu-id="6f516-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="6f516-121">Lorsque vous créez une page de détails de la commande, vous pouvez ajouter d'autres modules pertinents au module de détails de la commande existant.</span><span class="sxs-lookup"><span data-stu-id="6f516-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="6f516-122">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="6f516-122">Here are some examples:</span></span>

- <span data-ttu-id="6f516-123">**Module de recommandations** : il peut être ajouté à la page de détails de la commande pour suggérer d'autres produits au client.</span><span class="sxs-lookup"><span data-stu-id="6f516-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="6f516-124">**Modules de marketing** : tout module de marketing peut être ajouté à la page de détails de la commande pour afficher le contenu marketing.</span><span class="sxs-lookup"><span data-stu-id="6f516-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="create-an-order-details-page-module"></a><span data-ttu-id="6f516-125">Créer un module de page de détails de la commande</span><span class="sxs-lookup"><span data-stu-id="6f516-125">Create an order details page module</span></span>

1. <span data-ttu-id="6f516-126">Créez un modèle de page nommé **Modèle de détails de la commande**.</span><span class="sxs-lookup"><span data-stu-id="6f516-126">Create a page template that is named **Order details template**.</span></span>
1. <span data-ttu-id="6f516-127">Dans l'emplacement **Principal** de la page par défaut, ajoutez un module de détails de la commande.</span><span class="sxs-lookup"><span data-stu-id="6f516-127">In the **Main** slot of the default page, add an order details module.</span></span>
1. <span data-ttu-id="6f516-128">Dans le module de détails de la commande, ajoutez un module de recommandations.</span><span class="sxs-lookup"><span data-stu-id="6f516-128">In the order details module, add a recommendations module.</span></span>
1. <span data-ttu-id="6f516-129">Enregistrez et affichez un aperçu du modèle.</span><span class="sxs-lookup"><span data-stu-id="6f516-129">Save and preview the template.</span></span> <span data-ttu-id="6f516-130">Le module de détails de la commande ne s'affiche pas car il a besoin du contexte du numéro de confirmation de commande.</span><span class="sxs-lookup"><span data-stu-id="6f516-130">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="6f516-131">Terminez la modification du modèle et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="6f516-131">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="6f516-132">Utilisez le modèle de détails de la commande que vous venez de créer pour créer une page nommée **page de détails de la commande**.</span><span class="sxs-lookup"><span data-stu-id="6f516-132">Use the order details template that you just created to create a page that is named **order details page**.</span></span>
1. <span data-ttu-id="6f516-133">Ajoutez la page par défaut au contour de page.</span><span class="sxs-lookup"><span data-stu-id="6f516-133">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="6f516-134">À l'emplacement **En-tête**, ajoutez un fragment d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="6f516-134">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="6f516-135">À l'emplacement **Pied de page**, ajoutez un fragment de pied de page.</span><span class="sxs-lookup"><span data-stu-id="6f516-135">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="6f516-136">Dans l'emplacement **Principal**, ajoutez un module de détails de la commande.</span><span class="sxs-lookup"><span data-stu-id="6f516-136">In the **Main** slot, add an order details module.</span></span>
1. <span data-ttu-id="6f516-137">Dans le volet de propriétés du module de détails de la commande, ajoutez l'en-tête **Détails de la commande**.</span><span class="sxs-lookup"><span data-stu-id="6f516-137">In the property pane for the order details module, add the heading **Order details**.</span></span>
1. <span data-ttu-id="6f516-138">Sous le module de détails de la commande, ajoutez un module de recommandations et configurez-le afin qu'il utilise les paramètres **Nouveau** et **Meilleure vente**.</span><span class="sxs-lookup"><span data-stu-id="6f516-138">Below the order details module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="6f516-139">Enregistrez et affichez un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="6f516-139">Save and preview the page.</span></span>
1. <span data-ttu-id="6f516-140">Terminez la modification de la page et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="6f516-140">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f516-141">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6f516-141">Additional resources</span></span>

[<span data-ttu-id="6f516-142">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="6f516-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="6f516-143">Module Container</span><span class="sxs-lookup"><span data-stu-id="6f516-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="6f516-144">Module Zone d'achat</span><span class="sxs-lookup"><span data-stu-id="6f516-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="6f516-145">Module Panier</span><span class="sxs-lookup"><span data-stu-id="6f516-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="6f516-146">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="6f516-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="6f516-147">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="6f516-147">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="6f516-148">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="6f516-148">Footer module</span></span>](author-footer-module.md)
