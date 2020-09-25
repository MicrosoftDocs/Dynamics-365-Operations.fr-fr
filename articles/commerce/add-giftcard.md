---
title: Module de carte cadeau
description: Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4cc947b9d6f3cfa51bce2155170c49e9529d0f7d
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761079"
---
# <a name="gift-card-module"></a><span data-ttu-id="49cf5-103">Module de carte cadeau</span><span class="sxs-lookup"><span data-stu-id="49cf5-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="49cf5-104">Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="49cf5-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="49cf5-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="49cf5-105">Overview</span></span>

<span data-ttu-id="49cf5-106">Les modules de cartes cadeaux peuvent être utilisé dans les modules de paiement pour accepter des cartes cadeaux, moyen de paiement courant utilisé dans les transactions d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="49cf5-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="49cf5-107">Le module de carte cadeau prend en charge les cartes cadeaux Dynamics 365, SVS et Givex.</span><span class="sxs-lookup"><span data-stu-id="49cf5-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="49cf5-108">Les cartes cadeaux SVS et Givex sont échangées via le fournisseur de paiement Adyen.</span><span class="sxs-lookup"><span data-stu-id="49cf5-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="49cf5-109">Pour plus d’informations sur la prise en charge des cartes cadeaux externes telles que SVS et Givex, voir [Prise en charge des cartes cadeaux externes](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="49cf5-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

<span data-ttu-id="49cf5-110">Deux modules de cartes-cadeaux sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="49cf5-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="49cf5-111">**Carte cadeau** – Ce module peut être utilisé sur une page de paiement pour utiliser une carte-cadeau comme offre.</span><span class="sxs-lookup"><span data-stu-id="49cf5-111">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="49cf5-112">**Vérification du solde de la carte-cadeau** – Ce module peut être utilisé sur n’importe quelle page pour vérifier le solde d’une carte cadeau.</span><span class="sxs-lookup"><span data-stu-id="49cf5-112">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="49cf5-113">Ce module est disponible dans Commerce version 10.0.14 et ultérieure.</span><span class="sxs-lookup"><span data-stu-id="49cf5-113">This module is available in Commerce release 10.0.14 and later.</span></span>

<span data-ttu-id="49cf5-114">L’image suivante montre un exemple de module de carte cadeau dans une page de caisse.</span><span class="sxs-lookup"><span data-stu-id="49cf5-114">The following image shows an example of a gift card module on a checkout page.</span></span>

![Exemple d’un module de carte cadeau](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="49cf5-116">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="49cf5-116">Module properties</span></span>

- <span data-ttu-id="49cf5-117">**Afficher des champs supplémentaires** - Cette propriété définit quels champs doivent être affichés pour les cartes cadeaux en plus du numéro de carte-cadeau, qui est toujours affiché par défaut.</span><span class="sxs-lookup"><span data-stu-id="49cf5-117">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="49cf5-118">Par exemple, certaines cartes cadeaux prennent en charge l’affichage d’un numéro d’identification personnel (PIN) et d’autres prennent en charge l’affichage d’un code PIN et d’une date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="49cf5-118">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="49cf5-119">Alternativement, cette propriété peut être définie sur « Aucune », ce qui n’affichera que le numéro de la carte cadeau et aucun champ supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="49cf5-119">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="49cf5-120">Valeurs prises en charge :</span><span class="sxs-lookup"><span data-stu-id="49cf5-120">Supported values:</span></span>
-   <span data-ttu-id="49cf5-121">PIN</span><span class="sxs-lookup"><span data-stu-id="49cf5-121">PIN</span></span>
-   <span data-ttu-id="49cf5-122">Date d’expiration</span><span class="sxs-lookup"><span data-stu-id="49cf5-122">Expiration date</span></span>
-   <span data-ttu-id="49cf5-123">Code PIN et date d’expiration</span><span class="sxs-lookup"><span data-stu-id="49cf5-123">PIN and expiration date</span></span> 
-   <span data-ttu-id="49cf5-124">None</span><span class="sxs-lookup"><span data-stu-id="49cf5-124">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="49cf5-125">Paramètres du site pour les modules de cartes cadeaux</span><span class="sxs-lookup"><span data-stu-id="49cf5-125">Site settings for gift card modules</span></span>

<span data-ttu-id="49cf5-126">Dans le générateur de site Commerce, sous **Paramètres du site \> Extensions**, il y a un paramètre de module de carte cadeau appelé **Type de carte cadeau pris en charge**.</span><span class="sxs-lookup"><span data-stu-id="49cf5-126">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="49cf5-127">Ce paramètre prend en charge trois valeurs :</span><span class="sxs-lookup"><span data-stu-id="49cf5-127">This setting supports three values:</span></span>
- <span data-ttu-id="49cf5-128">**Carte cadeau Dynamics 365** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="49cf5-128">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="49cf5-129">Ce paramètre n’est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="49cf5-129">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="49cf5-130">**Cartes cadeaux SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Givex et SVS.</span><span class="sxs-lookup"><span data-stu-id="49cf5-130">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="49cf5-131">Ce paramètre est pris en charge pour les utilisateurs connectés et anonymes sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="49cf5-131">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="49cf5-132">**Cartes cadeaux Dynamics 365, SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365, Givex et SVS.</span><span class="sxs-lookup"><span data-stu-id="49cf5-132">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="49cf5-133">Ce paramètre n’est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="49cf5-133">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="49cf5-134">Ajouter un module de carte cadeau à une page</span><span class="sxs-lookup"><span data-stu-id="49cf5-134">Add a gift card module to a page</span></span>

<span data-ttu-id="49cf5-135">Pour obtenir des instructions sur la façon d’ajouter un module de carte cadeau à une page de paiement et de définir les propriétés requises, voir [Module de paiement ](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="49cf5-135">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="49cf5-136">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="49cf5-136">Additional resources</span></span>

[<span data-ttu-id="49cf5-137">Module Panier</span><span class="sxs-lookup"><span data-stu-id="49cf5-137">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="49cf5-138">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="49cf5-138">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="49cf5-139">Module Validation</span><span class="sxs-lookup"><span data-stu-id="49cf5-139">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="49cf5-140">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="49cf5-140">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="49cf5-141">Module Adresse d’expédition</span><span class="sxs-lookup"><span data-stu-id="49cf5-141">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="49cf5-142">Module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="49cf5-142">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="49cf5-143">Module Détails de la commande</span><span class="sxs-lookup"><span data-stu-id="49cf5-143">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="49cf5-144">Prendre en charge des cartes cadeaux externes</span><span class="sxs-lookup"><span data-stu-id="49cf5-144">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
