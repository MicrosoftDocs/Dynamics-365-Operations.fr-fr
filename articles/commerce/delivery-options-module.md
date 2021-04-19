---
title: Module Options de livraison
description: Cette rubrique couvre les modules d’options de livraison et explique comment les configurer dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: f97dcd42e22e319d9af7cbf57fce7c10d8565d04
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801989"
---
# <a name="delivery-options-module"></a><span data-ttu-id="0ded0-103">Module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="0ded0-103">Delivery options module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0ded0-104">Cette rubrique couvre les modules d’options de livraison et explique comment les configurer dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0ded0-104">This topic covers delivery options modules and explains how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="0ded0-105">Les modules d’options de livraison permettent aux clients de sélectionner un mode de livraison tel que l’expédition ou le retrait pour leur commande en ligne.</span><span class="sxs-lookup"><span data-stu-id="0ded0-105">Delivery options modules let customers select a mode of delivery such as shipping or pickup for their online order.</span></span> <span data-ttu-id="0ded0-106">Une adresse de livraison est nécessaire pour déterminer le mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="0ded0-106">A shipping address is required to determine the mode of delivery.</span></span> <span data-ttu-id="0ded0-107">Si l’adresse d’expédition change, les options de livraison doivent être extraites de nouveau.</span><span class="sxs-lookup"><span data-stu-id="0ded0-107">If the shipping address changes, the delivery options must be retrieved again.</span></span> <span data-ttu-id="0ded0-108">Si une commande inclut uniquement des articles qui sont retirés en magasin, ce module est automatiquement masqué.</span><span class="sxs-lookup"><span data-stu-id="0ded0-108">If an order includes only items that will be picked up in a store, this module is automatically hidden.</span></span>

<span data-ttu-id="0ded0-109">Pour plus d’informations sur la configuration des modes de livraison, voir [Configuration des canaux en ligne](channel-setup-online.md) et [Configurer les modes de livraison](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="0ded0-109">For information about how to configure modes of delivery, see [Online channel setup](channel-setup-online.md) and [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="0ded0-110">Chaque mode de livraison peut avoir des frais associés.</span><span class="sxs-lookup"><span data-stu-id="0ded0-110">Each delivery mode can have an associated charge.</span></span> <span data-ttu-id="0ded0-111">Pour plus d’informations sur la configuration de frais pour un commerce en ligne, consultez [Frais automatiques avancés omnicanaux](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="0ded0-111">For more information about how to configure charges for an online store, see [Omni-channel Advanced auto-charges](omni-auto-charges.md).</span></span>

<span data-ttu-id="0ded0-112">Dans Commerce version 10.0.13, le module des options de livraison a été mis à jour pour prendre en charge les fonctionnalités **Frais d’en-tête sans prorata** et **Expédition sous forme de frais de ligne**.</span><span class="sxs-lookup"><span data-stu-id="0ded0-112">In Commerce version 10.0.13, the delivery options module has been updated to support the **Header charges without proration** and **Shipping as a line charge** features.</span></span> <span data-ttu-id="0ded0-113">Si le prorata est désactivé, on s’attend à ce que le workflow d’e-Commerce n’autorise pas un mode de livraison mixte pour les articles du panier (c’est-à-dire que certains articles sont sélectionnés pour l’expédition, mais d’autres sont sélectionnés pour le retrait).</span><span class="sxs-lookup"><span data-stu-id="0ded0-113">If proration is turned off, the expectation is that the e-Commerce workflow won't allow a mixed mode of delivery for the items in the cart (that is, some items are selected for shipment, but others are selected for pickup).</span></span> <span data-ttu-id="0ded0-114">La fonctionnalité **Frais d’en-tête sans prorata** nécessite que l’indicateur **Activer la gestion cohérente du mode de livraison dans le canal** soit activé dans le siège Commerce.</span><span class="sxs-lookup"><span data-stu-id="0ded0-114">The **Header charges without proration** feature requires that the **Enable consistent delivery mode handling in channel** flag be turned on in Commerce headquarters.</span></span> <span data-ttu-id="0ded0-115">Lorsque cet indicateur est activé, les frais d’expédition seront appliqués au niveau de l’en-tête ou au niveau de la ligne, en fonction de la configuration au siège Commerce.</span><span class="sxs-lookup"><span data-stu-id="0ded0-115">When that flag is turned on, shipping charges will be applied at either the header level or the line level, depending on the configuration in Commerce headquarters.</span></span>

<span data-ttu-id="0ded0-116">Le thème Fabrikam prend en charge un mode de livraison mixte, dans lequel certains articles sont sélectionnés pour l’expédition mais d’autres sont sélectionnés pour le retrait.</span><span class="sxs-lookup"><span data-stu-id="0ded0-116">The Fabrikam theme supports a mixed mode of delivery, where some items are selected for shipment but others are selected for pickup.</span></span> <span data-ttu-id="0ded0-117">Dans ce mode, les frais d’expédition seront calculés au prorata pour tous les articles sélectionnés pour le mode d’expédition de livraison.</span><span class="sxs-lookup"><span data-stu-id="0ded0-117">In this mode, shipping charges will be prorated for all items that are selected for the shipping mode of delivery.</span></span> <span data-ttu-id="0ded0-118">Pour qu’un mode de livraison mixte fonctionne, vous devez d’abord configurer la fonctionnalité **Frais d’en-tête au prorata** au siège Commerce.</span><span class="sxs-lookup"><span data-stu-id="0ded0-118">For a mixed mode of delivery to work, you must first configure the **Header charges with proration** feature in Commerce headquarters.</span></span> <span data-ttu-id="0ded0-119">Pour plus d’informations sur cette configuration, consultez [Frais d’en-tête au prorata correspondent aux lignes de vente](pro-rate-charges-matching-lines.md).</span><span class="sxs-lookup"><span data-stu-id="0ded0-119">For more information about this configuration, see [Prorate header charges to match sales lines](pro-rate-charges-matching-lines.md).</span></span>

<span data-ttu-id="0ded0-120">Si des frais d’expédition s’appliquent aux articles de ligne, ils peuvent être affichés sur la ligne du panier pour chaque article.</span><span class="sxs-lookup"><span data-stu-id="0ded0-120">If shipping charges apply to line items, they can be shown on the cart line for each item.</span></span> <span data-ttu-id="0ded0-121">Cette fonctionnalité nécessite que la propriété **Afficher les frais d’expédition en ligne** soit activée à la fois pour le module Panier et le module Paiement.</span><span class="sxs-lookup"><span data-stu-id="0ded0-121">This functionality requires that the **Show shipping charges on line item** property be turned on for both the cart module and the checkout module.</span></span> <span data-ttu-id="0ded0-122">Pour plus d’informations, consultez [Module Panier](add-cart-module.md) et [Module Paiement](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="0ded0-122">For more information, see [Cart module](add-cart-module.md) and [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="0ded0-123">L’illustration suivante montre un exemple de module d’options de livraison dans une page de caisse.</span><span class="sxs-lookup"><span data-stu-id="0ded0-123">The following illustration shows an example of a delivery options module on a checkout page.</span></span>

![Exemple de module d’options de livraison sur une page de paiement](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a><span data-ttu-id="0ded0-125">Propriétés du module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="0ded0-125">Delivery options module properties</span></span>

| <span data-ttu-id="0ded0-126">Propriété</span><span class="sxs-lookup"><span data-stu-id="0ded0-126">Property</span></span> | <span data-ttu-id="0ded0-127">Valeurs</span><span class="sxs-lookup"><span data-stu-id="0ded0-127">Values</span></span> | <span data-ttu-id="0ded0-128">Description</span><span class="sxs-lookup"><span data-stu-id="0ded0-128">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="0ded0-129">Titre</span><span class="sxs-lookup"><span data-stu-id="0ded0-129">Heading</span></span> | <span data-ttu-id="0ded0-130">Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="0ded0-130">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="0ded0-131">Rubrique optionnelle pour le module Options de livraison.</span><span class="sxs-lookup"><span data-stu-id="0ded0-131">An optional heading for the delivery options module.</span></span> |
| <span data-ttu-id="0ded0-132">Nom de classe CSS personnalisé</span><span class="sxs-lookup"><span data-stu-id="0ded0-132">Custom CSS class name</span></span> | <span data-ttu-id="0ded0-133">Détails</span><span class="sxs-lookup"><span data-stu-id="0ded0-133">Text</span></span> | <span data-ttu-id="0ded0-134">Nom de classe de feuille de style en cascade personnalisée (CSS) qui sera utilisé pour afficher ce module, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="0ded0-134">A custom Cascading Style Sheets (CSS) class name that will be used to render this module, if applicable.</span></span> |
| <span data-ttu-id="0ded0-135">Option Filtrer le mode de livraison</span><span class="sxs-lookup"><span data-stu-id="0ded0-135">Filter Delivery Mode Option</span></span> | <span data-ttu-id="0ded0-136">**Ne pas filtrer** ou **Modes hors expédition**</span><span class="sxs-lookup"><span data-stu-id="0ded0-136">**Do not filter** or **Non-shipping modes**</span></span> | <span data-ttu-id="0ded0-137">Une valeur qui spécifie si le module Options de livraison doit filtrer tous les modes de livraison hors expédition.</span><span class="sxs-lookup"><span data-stu-id="0ded0-137">A value that specifies whether the delivery options module should filter out all non-shipping delivery modes.</span></span> |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="0ded0-138">Ajouter un module Options de livraison à une page de caisse et définir les propriétés requises</span><span class="sxs-lookup"><span data-stu-id="0ded0-138">Add a delivery options module to a checkout page and set the required properties</span></span>

<span data-ttu-id="0ded0-139">Un module Options de livraison ne peut être ajouté qu’à un module de caisse.</span><span class="sxs-lookup"><span data-stu-id="0ded0-139">A delivery options module can be added only to a checkout module.</span></span> <span data-ttu-id="0ded0-140">Pour plus d’informations sur la configuration d’un module Options de livraison et son ajout à une page de caisse, voir [Module de caisse](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="0ded0-140">For more information about how to configure the delivery options module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0ded0-141">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0ded0-141">Additional resources</span></span>

[<span data-ttu-id="0ded0-142">Module Panier</span><span class="sxs-lookup"><span data-stu-id="0ded0-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="0ded0-143">Module Validation</span><span class="sxs-lookup"><span data-stu-id="0ded0-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="0ded0-144">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="0ded0-144">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="0ded0-145">Module Adresse d’expédition</span><span class="sxs-lookup"><span data-stu-id="0ded0-145">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="0ded0-146">Module d’information sur le retrait</span><span class="sxs-lookup"><span data-stu-id="0ded0-146">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="0ded0-147">Module Détails de la commande</span><span class="sxs-lookup"><span data-stu-id="0ded0-147">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="0ded0-148">Module Carte cadeau</span><span class="sxs-lookup"><span data-stu-id="0ded0-148">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="0ded0-149">Configuration d’un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="0ded0-149">Online channel setup</span></span>](channel-setup-online.md)

[<span data-ttu-id="0ded0-150">Frais automatiques avancés omnicanaux</span><span class="sxs-lookup"><span data-stu-id="0ded0-150">Omni-channel Advanced auto-charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="0ded0-151">Calcul au prorata des frais d’en-tête correspondent aux lignes de vente</span><span class="sxs-lookup"><span data-stu-id="0ded0-151">Prorate header charges to match sales lines</span></span>](pro-rate-charges-matching-lines.md)

[<span data-ttu-id="0ded0-152">Paramétrer des modes de livraison</span><span class="sxs-lookup"><span data-stu-id="0ded0-152">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)


[!INCLUDE[footer-include](../includes/footer-banner.md)]