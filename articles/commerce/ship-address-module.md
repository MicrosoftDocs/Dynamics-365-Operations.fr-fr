---
title: Module Adresse d’expédition
description: Cette rubrique couvre le module Adresse d’expédition et explique comment le configurer dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 02/11/2021
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
ms.openlocfilehash: e590c966ca6bd8111df5f91cbac0485afaa45c78
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234411"
---
# <a name="shipping-address-module"></a><span data-ttu-id="c6322-103">Module Adresse d’expédition</span><span class="sxs-lookup"><span data-stu-id="c6322-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c6322-104">Cette rubrique décrit le module Adresse d’expédition et explique comment le configurer dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c6322-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c6322-105">Le module Adresse d’expédition permet aux clients d’ajouter ou de sélectionner l’adresse d’expédition pour une commande pendant le flux de paiement.</span><span class="sxs-lookup"><span data-stu-id="c6322-105">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="c6322-106">Si un client est connecté, toutes les adresses précédemment enregistrées pour ce client sont affichées et le client peut sélectionner parmi celles-ci.</span><span class="sxs-lookup"><span data-stu-id="c6322-106">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="c6322-107">Le client peut également ajouter une nouvelle adresse.</span><span class="sxs-lookup"><span data-stu-id="c6322-107">The customer can also add a new address.</span></span> <span data-ttu-id="c6322-108">Le module Adresse de livraison est utilisé pour tous les articles sur une commande qui nécessitent l’expédition.</span><span class="sxs-lookup"><span data-stu-id="c6322-108">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="c6322-109">Les formats d’adresse de livraison peuvent être définis dans le siège Commerce pour chaque pays ou région, et le module d’adresse de livraison applique alors les règles spécifiques au pays ou à la région.</span><span class="sxs-lookup"><span data-stu-id="c6322-109">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="c6322-110">Lorsque les clients saisissent une adresse de livraison pendant le processus de paiement, ils ont la possibilité d’enregistrer l’adresse en tant qu’adresse principale.</span><span class="sxs-lookup"><span data-stu-id="c6322-110">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="c6322-111">Cette option n’est affichée que si un client est connecté.</span><span class="sxs-lookup"><span data-stu-id="c6322-111">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="c6322-112">Bien que le module Adresse de livraison ne fournisse pas la validation d’adresse, cette fonctionnalité peut être implémentée à la personnalisation.</span><span class="sxs-lookup"><span data-stu-id="c6322-112">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="c6322-113">L’illustration suivante montre un exemple d’un nouveau module d’adresse de livraison dans une page de caisse.</span><span class="sxs-lookup"><span data-stu-id="c6322-113">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Exemple de module Adresse de livraison sur une page de paiement](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="c6322-115">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="c6322-115">Module properties</span></span>

| <span data-ttu-id="c6322-116">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="c6322-116">Property name</span></span> | <span data-ttu-id="c6322-117">Valeurs</span><span class="sxs-lookup"><span data-stu-id="c6322-117">Values</span></span> | <span data-ttu-id="c6322-118">Description</span><span class="sxs-lookup"><span data-stu-id="c6322-118">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="c6322-119">Titre</span><span class="sxs-lookup"><span data-stu-id="c6322-119">Heading</span></span> | <span data-ttu-id="c6322-120">Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="c6322-120">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="c6322-121">Rubrique optionnelle pour le module Adresse de livraison.</span><span class="sxs-lookup"><span data-stu-id="c6322-121">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="c6322-122">Afficher le type d’adresse</span><span class="sxs-lookup"><span data-stu-id="c6322-122">Show address type</span></span> | <span data-ttu-id="c6322-123">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="c6322-123">**True** or **False**</span></span> | <span data-ttu-id="c6322-124">Si cette propriété facultative est définie sur **True**, un type d’adresse, tel que **Domicile** ou **Professionnelle**, sera affiché.</span><span class="sxs-lookup"><span data-stu-id="c6322-124">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="c6322-125">Si aucun type d’adresse n’est spécifié, l’adresse sera automatiquement enregistrée sous **Type**=**Autre**.</span><span class="sxs-lookup"><span data-stu-id="c6322-125">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |
| <span data-ttu-id="c6322-126">Activer la suggestion automatique</span><span class="sxs-lookup"><span data-stu-id="c6322-126">Enable auto suggestion</span></span>| <span data-ttu-id="c6322-127">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="c6322-127">**True** or **False**</span></span> | <span data-ttu-id="c6322-128">Si cette propriété facultative est définie sur **Vrai**, des suggestions d’adresses automatiques seront fournies.</span><span class="sxs-lookup"><span data-stu-id="c6322-128">If this optional property is set to **True**, automatic address suggestions will be provided.</span></span> <span data-ttu-id="c6322-129">Ces suggestions sont générées par Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="c6322-129">These suggestions are powered by Bing Maps.</span></span> <span data-ttu-id="c6322-130">Pour plus d’informations sur la configuration de l’intégration de Bing Maps pour votre site, voir [Module de sélection de magasin](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="c6322-130">For information about how to set up Bing Maps integration for your site, see [Store selector module](store-selector.md).</span></span> <span data-ttu-id="c6322-131">Cette fonctionnalité est disponible à partir de la version 10.0.15 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c6322-131">This feature is available as of the Commerce version 10.0.15 release.</span></span>|
|<span data-ttu-id="c6322-132">Options de suggestion automatique</span><span class="sxs-lookup"><span data-stu-id="c6322-132">Auto suggest options</span></span>| <span data-ttu-id="c6322-133">Nombre</span><span class="sxs-lookup"><span data-stu-id="c6322-133">A number</span></span>| <span data-ttu-id="c6322-134">Si les suggestions d’adresses automatiques sont activées, vous pouvez spécifier des options supplémentaires, par exemple le nombre maximal de suggestions à fournir.</span><span class="sxs-lookup"><span data-stu-id="c6322-134">If automatic address suggestions are enabled, you can specify additional options, such as the maximum number of suggestions that should be provided.</span></span>|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="c6322-135">Ajouter un module Adresse de livraison à une page de caisse et définir les propriétés requises</span><span class="sxs-lookup"><span data-stu-id="c6322-135">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="c6322-136">Un module Adresse de livraison ne peut être ajouté qu’à un module de caisse.</span><span class="sxs-lookup"><span data-stu-id="c6322-136">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="c6322-137">Pour plus d’informations sur la configuration d’un module Adresse de livraison et son ajout à une page de caisse, voir [Module de caisse](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="c6322-137">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c6322-138">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c6322-138">Additional resources</span></span>

[<span data-ttu-id="c6322-139">Module Panier</span><span class="sxs-lookup"><span data-stu-id="c6322-139">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c6322-140">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="c6322-140">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="c6322-141">Module Validation</span><span class="sxs-lookup"><span data-stu-id="c6322-141">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c6322-142">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="c6322-142">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="c6322-143">Module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="c6322-143">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="c6322-144">Module Information sur les prélèvements</span><span class="sxs-lookup"><span data-stu-id="c6322-144">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="c6322-145">Module Détails de la commande</span><span class="sxs-lookup"><span data-stu-id="c6322-145">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="c6322-146">Module Carte cadeau</span><span class="sxs-lookup"><span data-stu-id="c6322-146">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="c6322-147">Module Sélection de magasin</span><span class="sxs-lookup"><span data-stu-id="c6322-147">Store selector module</span></span>](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]