---
title: Module de carte cadeau
description: Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: fa6b98bb41c0845cfa3ab36767f304ad70f46399
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2020
ms.locfileid: "4412432"
---
# <a name="gift-card-module"></a><span data-ttu-id="1a897-103">Module de carte cadeau</span><span class="sxs-lookup"><span data-stu-id="1a897-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1a897-104">Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1a897-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1a897-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="1a897-105">Overview</span></span>

<span data-ttu-id="1a897-106">Les modules de cartes cadeaux peuvent être utilisé dans les modules de paiement pour accepter des cartes cadeaux, moyen de paiement courant utilisé dans les transactions d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="1a897-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="1a897-107">Le module de carte cadeau prend en charge les cartes cadeaux Dynamics 365, SVS et Givex.</span><span class="sxs-lookup"><span data-stu-id="1a897-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="1a897-108">Les cartes cadeaux SVS et Givex sont échangées via le fournisseur de paiement Adyen.</span><span class="sxs-lookup"><span data-stu-id="1a897-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="1a897-109">Pour plus d’informations sur la prise en charge des cartes cadeaux externes telles que SVS et Givex, voir [Prise en charge des cartes cadeaux externes](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="1a897-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1a897-110">La prise en charge du remboursement des cartes cadeaux SVS et Givex pendant le processus de paiement est disponible dans la version 10.0.11 de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1a897-110">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="1a897-111">Deux modules de cartes-cadeaux sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="1a897-111">There are two gift card modules available:</span></span>

- <span data-ttu-id="1a897-112">**Carte cadeau** – Ce module peut être utilisé sur une page de paiement pour utiliser une carte-cadeau comme offre.</span><span class="sxs-lookup"><span data-stu-id="1a897-112">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="1a897-113">**Vérification du solde de la carte-cadeau** – Ce module peut être utilisé sur n’importe quelle page pour vérifier le solde d’une carte cadeau.</span><span class="sxs-lookup"><span data-stu-id="1a897-113">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="1a897-114">Ce module est disponible dans Commerce version 10.0.14 et ultérieure.</span><span class="sxs-lookup"><span data-stu-id="1a897-114">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="1a897-115">La prise en charge du module de vérification du solde de la carte cadeau est disponible dans la version 10.0.14 de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1a897-115">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="1a897-116">L’image suivante montre un exemple de module de carte cadeau dans une page de caisse.</span><span class="sxs-lookup"><span data-stu-id="1a897-116">The following image shows an example of a gift card module on a checkout page.</span></span>

![Exemple d’un module de carte cadeau](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="1a897-118">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="1a897-118">Module properties</span></span>

- <span data-ttu-id="1a897-119">**Afficher des champs supplémentaires** - Cette propriété définit quels champs doivent être affichés pour les cartes cadeaux en plus du numéro de carte-cadeau, qui est toujours affiché par défaut.</span><span class="sxs-lookup"><span data-stu-id="1a897-119">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="1a897-120">Par exemple, certaines cartes cadeaux prennent en charge l’affichage d’un numéro d’identification personnel (PIN) et d’autres prennent en charge l’affichage d’un code PIN et d’une date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="1a897-120">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="1a897-121">Alternativement, cette propriété peut être définie sur « Aucune », ce qui n’affichera que le numéro de la carte cadeau et aucun champ supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="1a897-121">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="1a897-122">Valeurs prises en charge :</span><span class="sxs-lookup"><span data-stu-id="1a897-122">Supported values:</span></span>
-   <span data-ttu-id="1a897-123">PIN</span><span class="sxs-lookup"><span data-stu-id="1a897-123">PIN</span></span>
-   <span data-ttu-id="1a897-124">Date d’expiration</span><span class="sxs-lookup"><span data-stu-id="1a897-124">Expiration date</span></span>
-   <span data-ttu-id="1a897-125">Code PIN et date d’expiration</span><span class="sxs-lookup"><span data-stu-id="1a897-125">PIN and expiration date</span></span> 
-   <span data-ttu-id="1a897-126">None</span><span class="sxs-lookup"><span data-stu-id="1a897-126">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="1a897-127">Paramètres du site pour les modules de cartes cadeaux</span><span class="sxs-lookup"><span data-stu-id="1a897-127">Site settings for gift card modules</span></span>

<span data-ttu-id="1a897-128">Dans le générateur de site Commerce, sous **Paramètres du site \> Extensions**, il y a un paramètre de module de carte cadeau appelé **Type de carte cadeau pris en charge**.</span><span class="sxs-lookup"><span data-stu-id="1a897-128">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="1a897-129">Ce paramètre prend en charge trois valeurs :</span><span class="sxs-lookup"><span data-stu-id="1a897-129">This setting supports three values:</span></span>
- <span data-ttu-id="1a897-130">**Carte cadeau Dynamics 365** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1a897-130">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="1a897-131">Ce paramètre n’est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="1a897-131">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="1a897-132">**Cartes cadeaux SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Givex et SVS.</span><span class="sxs-lookup"><span data-stu-id="1a897-132">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="1a897-133">Ce paramètre est pris en charge pour les utilisateurs connectés et anonymes sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="1a897-133">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="1a897-134">**Cartes cadeaux Dynamics 365, SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365, Givex et SVS.</span><span class="sxs-lookup"><span data-stu-id="1a897-134">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="1a897-135">Ce paramètre n’est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="1a897-135">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a897-136">Ces paramètres sont disponibles dans la version 10.0.11 de Dynamics 365 Commerce et ne sont requis que si vous avez besoin d'assistance pour les cartes cadeaux SVS ou Givex.</span><span class="sxs-lookup"><span data-stu-id="1a897-136">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="1a897-137">Si vous effectuez une mise à jour à partir d'une ancienne version de Dynamics 365 Commerce, vous devez mettre à jour manuellement le fichier appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="1a897-137">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="1a897-138">Pour obtenir des instructions de mise à jour du fichier appsettings.json, consultez [Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="1a897-138">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="1a897-139">Ajouter un module de carte cadeau à une page</span><span class="sxs-lookup"><span data-stu-id="1a897-139">Add a gift card module to a page</span></span>

<span data-ttu-id="1a897-140">Pour obtenir des instructions sur la façon d’ajouter un module de carte cadeau à une page de paiement et de définir les propriétés requises, voir [Module de paiement ](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="1a897-140">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a897-141">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1a897-141">Additional resources</span></span>

[<span data-ttu-id="1a897-142">Module Panier</span><span class="sxs-lookup"><span data-stu-id="1a897-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="1a897-143">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="1a897-143">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="1a897-144">Module Validation</span><span class="sxs-lookup"><span data-stu-id="1a897-144">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="1a897-145">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="1a897-145">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="1a897-146">Module Adresse d’expédition</span><span class="sxs-lookup"><span data-stu-id="1a897-146">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="1a897-147">Module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="1a897-147">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="1a897-148">Module d'information sur le retrait</span><span class="sxs-lookup"><span data-stu-id="1a897-148">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="1a897-149">Module Détails de la commande</span><span class="sxs-lookup"><span data-stu-id="1a897-149">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="1a897-150">Prendre en charge des cartes cadeaux externes</span><span class="sxs-lookup"><span data-stu-id="1a897-150">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="1a897-151">Mise à jour du kit de développement logiciel et de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="1a897-151">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)
