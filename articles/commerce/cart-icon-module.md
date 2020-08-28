---
title: Module Icône de panier
description: Cette rubrique couvre le module Icône de panier de magasins et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 137debe3f4cad3948d20b2902ea80e66fa74ffd4
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661145"
---
# <a name="cart-icon-module"></a><span data-ttu-id="65134-103">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="65134-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="65134-104">Cette rubrique couvre le module Icône de panier de magasins et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="65134-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="65134-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="65134-105">Overview</span></span>

<span data-ttu-id="65134-106">Le module Icône de panier représente le panier dans le module d’en-tête de la page et indique le nombre d’articles dans le panier.</span><span class="sxs-lookup"><span data-stu-id="65134-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="65134-107">Le module Icône de panier affiche également un récapitulatif du panier (également appelé mini-panier) lorsque la souris survole l’icône de panier.</span><span class="sxs-lookup"><span data-stu-id="65134-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="65134-108">Le mini-panier offre à l’utilisateur un récapitulatif des articles du panier sans avoir à parcourir la page du panier.</span><span class="sxs-lookup"><span data-stu-id="65134-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="65134-109">En outre, il permet également à l’utilisateur d’accéder directement à la page de paiement si le récapitulatif le satisfait.</span><span class="sxs-lookup"><span data-stu-id="65134-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="65134-110">Cela réduit le nombre de navigations de page et accélère l’opération de paiement.</span><span class="sxs-lookup"><span data-stu-id="65134-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

<span data-ttu-id="65134-111">L’image suivante montre un exemple de module d’icône de panier qui affiche un mini panier dans l’en-tête Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="65134-111">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Exemple d’un module d’icône de panier](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="65134-113">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="65134-113">Module properties</span></span>

- <span data-ttu-id="65134-114">**Afficher le mini panier** - Lorsqu’elle est définie sur True, cette propriété permet d’afficher un récapitulatif du panier (mini-panier) lorsque l’icône de panier est survolée.</span><span class="sxs-lookup"><span data-stu-id="65134-114">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="65134-115">Cette fonctionnalité n’est prise en charge que pour les ports de vue du bureau.</span><span class="sxs-lookup"><span data-stu-id="65134-115">This functionality is only supported for desktop view ports.</span></span>

## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="65134-116">Ajouter un module d’icône de panier à une page</span><span class="sxs-lookup"><span data-stu-id="65134-116">Add a cart icon module to a page</span></span>

<span data-ttu-id="65134-117">Pour ajouter un module d’icône de panier, voir [Module d’en-tête](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="65134-117">To add a cart icon module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="65134-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="65134-118">Additional resources</span></span>

[<span data-ttu-id="65134-119">Module Panier</span><span class="sxs-lookup"><span data-stu-id="65134-119">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="65134-120">Module Validation</span><span class="sxs-lookup"><span data-stu-id="65134-120">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="65134-121">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="65134-121">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="65134-122">Module Adresse d’expédition</span><span class="sxs-lookup"><span data-stu-id="65134-122">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="65134-123">Module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="65134-123">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="65134-124">Module Détails de la commande</span><span class="sxs-lookup"><span data-stu-id="65134-124">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="65134-125">Module Carte cadeau</span><span class="sxs-lookup"><span data-stu-id="65134-125">Gift card module</span></span>](add-giftcard.md)
