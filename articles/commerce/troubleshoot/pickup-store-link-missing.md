---
title: L’option Retrait n’apparaît pas sur la page du panier ou sur les pages de détails du produit
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque l’option de retrait en magasin n’apparaît pas sur la page du panier ou sur les pages de détails du produit.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f692d73bf1755422e9bfc8314c1156e043ccf761
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020803"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a><span data-ttu-id="5dc9a-103">L’option « Retrait » n’apparaît pas sur le panier ou sur les pages de détails du produit</span><span class="sxs-lookup"><span data-stu-id="5dc9a-103">"Pick this up" option doesn't appear on cart or product details pages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5dc9a-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque l’option de retrait en magasin n’apparaît pas sur la page du panier ou sur les pages de détails du produit.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-104">This topic provides troubleshooting guidance that can help when the option for in-store pickup doesn't appear on the cart page or product details pages.</span></span>

## <a name="description"></a><span data-ttu-id="5dc9a-105">Description</span><span class="sxs-lookup"><span data-stu-id="5dc9a-105">Description</span></span>

<span data-ttu-id="5dc9a-106">Le bouton **Retrait** n’apparaît pas sur la page du panier ou sur les pages de détails du produit.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-106">The **Pick this up** button doesn't appear on the cart page or product details pages.</span></span>

<span data-ttu-id="5dc9a-107">L’illustration suivante montre un exemple de page qui inclut le bouton **Retrait**.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-107">The following illustration shows an example of a page that includes the **Pick this up** button.</span></span>

![Bouton Retrait](media/pickup-button-missing.jpg)

## <a name="resolution"></a><span data-ttu-id="5dc9a-109">Résolution</span><span class="sxs-lookup"><span data-stu-id="5dc9a-109">Resolution</span></span>

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a><span data-ttu-id="5dc9a-110">Activer l’extension BOPIS dans le générateur de site Commerce</span><span class="sxs-lookup"><span data-stu-id="5dc9a-110">Enable the BOPIS extension in Commerce site builder</span></span>

<span data-ttu-id="5dc9a-111">Pour activer l’extension « Acheter en ligne, retirer en magasin » (BOPIS) dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-111">To enable the "buy online, pick up in store" (BOPIS) extension in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="5dc9a-112">Sélectionnez votre site.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-112">Select your site.</span></span>
1. <span data-ttu-id="5dc9a-113">Sélectionnez **Paramètres du site**, puis **Extensions**.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-113">Select **Site settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="5dc9a-114">Assurez-vous que l’option **Désactiver BOPIS** n’est pas cochée.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-114">Make sure that the **Disable BOPIS** option is cleared.</span></span>

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a><span data-ttu-id="5dc9a-115">Configurer les modes de livraison dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="5dc9a-115">Configure modes of delivery in Commerce headquarters</span></span>

<span data-ttu-id="5dc9a-116">Pour configurer les modes de livraison dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-116">To configure modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="5dc9a-117">Accédez à **Approvisionnements \> Paramétrage \> Modes de livraison**.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-117">Go to **Procurement and sourcing \> Setup \> Modes of delivery**.</span></span>
1. <span data-ttu-id="5dc9a-118">Assurez-vous que le mode de livraison **Retrait par le client** a été créé et que des produits et des adresses lui sont affectés.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-118">Make sure that a **Customer pickup** mode of delivery has been created, and that products and addresses are assigned to it.</span></span>
1. <span data-ttu-id="5dc9a-119">Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="5dc9a-120">Dans le volet de navigation de gauche, sélectionnez **Commandes client**.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-120">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="5dc9a-121">Assurez-vous que **Mode de livraison en retrait** est correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-121">Make sure that **Pickup mode of delivery** is correctly configured.</span></span>

### <a name="configure-customer-orders-payments"></a><span data-ttu-id="5dc9a-122">Configurer les paiements des commandes client</span><span class="sxs-lookup"><span data-stu-id="5dc9a-122">Configure customer orders payments</span></span>

<span data-ttu-id="5dc9a-123">Pour configurer les paiements des commandes client dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-123">To configure customer orders payments in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="5dc9a-124">Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-124">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="5dc9a-125">Dans le volet de navigation de gauche, sélectionnez **Commandes client**.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-125">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="5dc9a-126">Sur le raccourci **Paiements**, assurez-vous que les champs **Conditions de paiement** et **Mode de paiement** sont correctement définis.</span><span class="sxs-lookup"><span data-stu-id="5dc9a-126">On the **Payments** FastTab, make sure that the **Terms of payment** and **Method of payment** fields are correctly set.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5dc9a-127">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5dc9a-127">Additional resources</span></span>

[<span data-ttu-id="5dc9a-128">Configurer BOPIS</span><span class="sxs-lookup"><span data-stu-id="5dc9a-128">Configure BOPIS</span></span>](../cpe-bopis.md)

[<span data-ttu-id="5dc9a-129">Activer plusieurs modes de livraison de retrait pour les commandes des clients</span><span class="sxs-lookup"><span data-stu-id="5dc9a-129">Enable multiple pickup delivery modes for customer orders</span></span>](../multiple-pickup-modes.md)

[<span data-ttu-id="5dc9a-130">Paiements de commandes de Commerce omnicanal</span><span class="sxs-lookup"><span data-stu-id="5dc9a-130">Omni-channel Commerce order payments</span></span>](../dev-itpro/commerce-payments.md)

[<span data-ttu-id="5dc9a-131">Module Sélection de magasin</span><span class="sxs-lookup"><span data-stu-id="5dc9a-131">Store selector module</span></span>](../store-selector.md)
