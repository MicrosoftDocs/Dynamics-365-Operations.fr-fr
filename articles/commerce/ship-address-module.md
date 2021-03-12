---
title: Module Adresse d’expédition
description: Cette rubrique couvre le module Adresse d’expédition et explique comment le configurer dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 6a5eb69c7746be419779b1a844ee35ec375a324c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985634"
---
# <a name="shipping-address-module"></a><span data-ttu-id="fe84d-103">Module Adresse d’expédition</span><span class="sxs-lookup"><span data-stu-id="fe84d-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fe84d-104">Cette rubrique décrit le module Adresse d’expédition et explique comment le configurer dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe84d-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fe84d-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="fe84d-105">Overview</span></span>

<span data-ttu-id="fe84d-106">Le module Adresse d’expédition permet aux clients d’ajouter ou de sélectionner l’adresse d’expédition pour une commande pendant le flux de paiement.</span><span class="sxs-lookup"><span data-stu-id="fe84d-106">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="fe84d-107">Si un client est connecté, toutes les adresses précédemment enregistrées pour ce client sont affichées et le client peut sélectionner parmi celles-ci.</span><span class="sxs-lookup"><span data-stu-id="fe84d-107">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="fe84d-108">Le client peut également ajouter une nouvelle adresse.</span><span class="sxs-lookup"><span data-stu-id="fe84d-108">The customer can also add a new address.</span></span> <span data-ttu-id="fe84d-109">Le module Adresse de livraison est utilisé pour tous les articles sur une commande qui nécessitent l’expédition.</span><span class="sxs-lookup"><span data-stu-id="fe84d-109">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="fe84d-110">Les formats d’adresse de livraison peuvent être définis dans le siège Commerce pour chaque pays ou région, et le module d’adresse de livraison applique alors les règles spécifiques au pays ou à la région.</span><span class="sxs-lookup"><span data-stu-id="fe84d-110">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="fe84d-111">Lorsque les clients saisissent une adresse de livraison pendant le processus de paiement, ils ont la possibilité d’enregistrer l’adresse en tant qu’adresse principale.</span><span class="sxs-lookup"><span data-stu-id="fe84d-111">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="fe84d-112">Cette option n’est affichée que si un client est connecté.</span><span class="sxs-lookup"><span data-stu-id="fe84d-112">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="fe84d-113">Bien que le module Adresse de livraison ne fournisse pas la validation d’adresse, cette fonctionnalité peut être implémentée à la personnalisation.</span><span class="sxs-lookup"><span data-stu-id="fe84d-113">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="fe84d-114">L’illustration suivante montre un exemple d’un nouveau module d’adresse de livraison dans une page de caisse.</span><span class="sxs-lookup"><span data-stu-id="fe84d-114">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Exemple de module Adresse de livraison sur une page de paiement](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="fe84d-116">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="fe84d-116">Module properties</span></span>

| <span data-ttu-id="fe84d-117">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="fe84d-117">Property name</span></span> | <span data-ttu-id="fe84d-118">Valeurs</span><span class="sxs-lookup"><span data-stu-id="fe84d-118">Values</span></span> | <span data-ttu-id="fe84d-119">Description</span><span class="sxs-lookup"><span data-stu-id="fe84d-119">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="fe84d-120">Titre</span><span class="sxs-lookup"><span data-stu-id="fe84d-120">Heading</span></span> | <span data-ttu-id="fe84d-121">Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="fe84d-121">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="fe84d-122">Rubrique optionnelle pour le module Adresse de livraison.</span><span class="sxs-lookup"><span data-stu-id="fe84d-122">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="fe84d-123">Afficher le type d’adresse</span><span class="sxs-lookup"><span data-stu-id="fe84d-123">Show address type</span></span> | <span data-ttu-id="fe84d-124">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="fe84d-124">**True** or **False**</span></span> | <span data-ttu-id="fe84d-125">Si cette propriété facultative est définie sur **True**, un type d’adresse, tel que **Domicile** ou **Professionnelle**, sera affiché.</span><span class="sxs-lookup"><span data-stu-id="fe84d-125">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="fe84d-126">Si aucun type d’adresse n’est spécifié, l’adresse sera automatiquement enregistrée sous **Type**=**Autre**.</span><span class="sxs-lookup"><span data-stu-id="fe84d-126">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="fe84d-127">Ajouter un module Adresse de livraison à une page de caisse et définir les propriétés requises</span><span class="sxs-lookup"><span data-stu-id="fe84d-127">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="fe84d-128">Un module Adresse de livraison ne peut être ajouté qu’à un module de caisse.</span><span class="sxs-lookup"><span data-stu-id="fe84d-128">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="fe84d-129">Pour plus d’informations sur la configuration d’un module Adresse de livraison et son ajout à une page de caisse, voir [Module de caisse](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="fe84d-129">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fe84d-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fe84d-130">Additional resources</span></span>

[<span data-ttu-id="fe84d-131">Module Panier</span><span class="sxs-lookup"><span data-stu-id="fe84d-131">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="fe84d-132">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="fe84d-132">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="fe84d-133">Module Validation</span><span class="sxs-lookup"><span data-stu-id="fe84d-133">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="fe84d-134">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="fe84d-134">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="fe84d-135">Module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="fe84d-135">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="fe84d-136">Module d'information sur le retrait</span><span class="sxs-lookup"><span data-stu-id="fe84d-136">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="fe84d-137">Module Détails de la commande</span><span class="sxs-lookup"><span data-stu-id="fe84d-137">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="fe84d-138">Module Carte cadeau</span><span class="sxs-lookup"><span data-stu-id="fe84d-138">Gift card module</span></span>](add-giftcard.md)
