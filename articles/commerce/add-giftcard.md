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
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c024cc1b16ca60b2277eba2d7045020c2e67c3a0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206293"
---
# <a name="gift-card-module"></a><span data-ttu-id="4f93a-103">Module Carte cadeau</span><span class="sxs-lookup"><span data-stu-id="4f93a-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4f93a-104">Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4f93a-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4f93a-105">Les modules de cartes cadeaux peuvent être utilisé dans les modules de paiement pour accepter des cartes cadeaux, moyen de paiement courant utilisé dans les transactions d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="4f93a-105">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="4f93a-106">Le module de carte cadeau prend en charge les cartes cadeaux Dynamics 365, SVS et Givex.</span><span class="sxs-lookup"><span data-stu-id="4f93a-106">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="4f93a-107">Les cartes cadeaux SVS et Givex sont échangées via le fournisseur de paiement Adyen.</span><span class="sxs-lookup"><span data-stu-id="4f93a-107">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="4f93a-108">Pour plus d’informations sur la prise en charge des cartes cadeaux externes telles que SVS et Givex, voir [Prise en charge des cartes cadeaux externes](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="4f93a-108">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4f93a-109">La prise en charge du remboursement des cartes cadeaux SVS et Givex pendant le processus de paiement est disponible dans la version 10.0.11 de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4f93a-109">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="4f93a-110">Deux modules de cartes-cadeaux sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="4f93a-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="4f93a-111">**Carte cadeau** – Ce module peut être utilisé sur une page de paiement pour utiliser une carte-cadeau comme offre.</span><span class="sxs-lookup"><span data-stu-id="4f93a-111">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="4f93a-112">**Vérification du solde de la carte-cadeau** – Ce module peut être utilisé sur n’importe quelle page pour vérifier le solde d’une carte cadeau.</span><span class="sxs-lookup"><span data-stu-id="4f93a-112">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="4f93a-113">Ce module est disponible dans Commerce version 10.0.14 et ultérieure.</span><span class="sxs-lookup"><span data-stu-id="4f93a-113">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="4f93a-114">La prise en charge du module de vérification du solde de la carte cadeau est disponible dans la version 10.0.14 de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4f93a-114">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="4f93a-115">L’image suivante montre un exemple de module de carte cadeau dans une page de caisse.</span><span class="sxs-lookup"><span data-stu-id="4f93a-115">The following image shows an example of a gift card module on a checkout page.</span></span>

![Exemple d’un module de carte cadeau](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="4f93a-117">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="4f93a-117">Module properties</span></span>

- <span data-ttu-id="4f93a-118">**Afficher des champs supplémentaires** - Cette propriété définit quels champs doivent être affichés pour les cartes cadeaux en plus du numéro de carte-cadeau, qui est toujours affiché par défaut.</span><span class="sxs-lookup"><span data-stu-id="4f93a-118">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="4f93a-119">Par exemple, certaines cartes cadeaux prennent en charge l’affichage d’un numéro d’identification personnel (PIN) et d’autres prennent en charge l’affichage d’un code PIN et d’une date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="4f93a-119">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="4f93a-120">Alternativement, cette propriété peut être définie sur « Aucune », ce qui n’affichera que le numéro de la carte cadeau et aucun champ supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="4f93a-120">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="4f93a-121">Valeurs prises en charge :</span><span class="sxs-lookup"><span data-stu-id="4f93a-121">Supported values:</span></span>
-   <span data-ttu-id="4f93a-122">PIN</span><span class="sxs-lookup"><span data-stu-id="4f93a-122">PIN</span></span>
-   <span data-ttu-id="4f93a-123">Date d’expiration</span><span class="sxs-lookup"><span data-stu-id="4f93a-123">Expiration date</span></span>
-   <span data-ttu-id="4f93a-124">Code PIN et date d’expiration</span><span class="sxs-lookup"><span data-stu-id="4f93a-124">PIN and expiration date</span></span> 
-   <span data-ttu-id="4f93a-125">None</span><span class="sxs-lookup"><span data-stu-id="4f93a-125">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="4f93a-126">Paramètres du site pour les modules de cartes cadeaux</span><span class="sxs-lookup"><span data-stu-id="4f93a-126">Site settings for gift card modules</span></span>

<span data-ttu-id="4f93a-127">Dans le générateur de site Commerce, sous **Paramètres du site \> Extensions**, il y a un paramètre de module de carte cadeau appelé **Type de carte cadeau pris en charge**.</span><span class="sxs-lookup"><span data-stu-id="4f93a-127">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="4f93a-128">Ce paramètre prend en charge trois valeurs :</span><span class="sxs-lookup"><span data-stu-id="4f93a-128">This setting supports three values:</span></span>
- <span data-ttu-id="4f93a-129">**Carte cadeau Dynamics 365** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="4f93a-129">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="4f93a-130">Ce paramètre n’est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="4f93a-130">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="4f93a-131">**Cartes cadeaux SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Givex et SVS.</span><span class="sxs-lookup"><span data-stu-id="4f93a-131">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="4f93a-132">Ce paramètre est pris en charge pour les utilisateurs connectés et anonymes sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="4f93a-132">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="4f93a-133">**Cartes cadeaux Dynamics 365, SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365, Givex et SVS.</span><span class="sxs-lookup"><span data-stu-id="4f93a-133">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="4f93a-134">Ce paramètre n’est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="4f93a-134">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f93a-135">Ces paramètres sont disponibles dans la version 10.0.11 de Dynamics 365 Commerce et ne sont requis que si vous avez besoin d'assistance pour les cartes cadeaux SVS ou Givex.</span><span class="sxs-lookup"><span data-stu-id="4f93a-135">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="4f93a-136">Si vous effectuez une mise à jour à partir d'une ancienne version de Dynamics 365 Commerce, vous devez mettre à jour manuellement le fichier appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="4f93a-136">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="4f93a-137">Pour obtenir des instructions de mise à jour du fichier appsettings.json, consultez [Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="4f93a-137">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="4f93a-138">Ajouter un module de carte cadeau à une page</span><span class="sxs-lookup"><span data-stu-id="4f93a-138">Add a gift card module to a page</span></span>

<span data-ttu-id="4f93a-139">Pour obtenir des instructions sur la façon d’ajouter un module de carte cadeau à une page de paiement et de définir les propriétés requises, voir [Module de paiement ](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="4f93a-139">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4f93a-140">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4f93a-140">Additional resources</span></span>

[<span data-ttu-id="4f93a-141">Module Panier</span><span class="sxs-lookup"><span data-stu-id="4f93a-141">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="4f93a-142">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="4f93a-142">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="4f93a-143">Module Validation</span><span class="sxs-lookup"><span data-stu-id="4f93a-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="4f93a-144">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="4f93a-144">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="4f93a-145">Module Adresse d’expédition</span><span class="sxs-lookup"><span data-stu-id="4f93a-145">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="4f93a-146">Module Options de livraison</span><span class="sxs-lookup"><span data-stu-id="4f93a-146">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="4f93a-147">Module d'information sur le retrait</span><span class="sxs-lookup"><span data-stu-id="4f93a-147">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="4f93a-148">Module Détails de la commande</span><span class="sxs-lookup"><span data-stu-id="4f93a-148">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="4f93a-149">Prendre en charge des cartes cadeaux externes</span><span class="sxs-lookup"><span data-stu-id="4f93a-149">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="4f93a-150">Mise à jour du kit de développement logiciel et de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="4f93a-150">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]