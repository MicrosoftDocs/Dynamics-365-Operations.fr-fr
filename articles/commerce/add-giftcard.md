---
title: Module de carte cadeau
description: Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: a8428963e105e422dcd048863c17df0926a409ac
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411110"
---
# <a name="gift-card-module"></a><span data-ttu-id="e0865-103">Module de carte cadeau</span><span class="sxs-lookup"><span data-stu-id="e0865-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e0865-104">Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e0865-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e0865-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="e0865-105">Overview</span></span>

<span data-ttu-id="e0865-106">Les cartes cadeaux sont un mode de paiement courant et le module de cartes cadeaux peut être utilisé dans un module de paiement pour accepter des cartes cadeaux.</span><span class="sxs-lookup"><span data-stu-id="e0865-106">Gift cards are a common form of payment, and the gift card module can be used in a checkout module to accept gift cards.</span></span> <span data-ttu-id="e0865-107">Le module de carte cadeau prend en charge les cartes cadeaux Dynamics 365, SVS et Givex.</span><span class="sxs-lookup"><span data-stu-id="e0865-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="e0865-108">Les cartes cadeaux SVS et Givex sont échangées via le fournisseur de paiement Adyen.</span><span class="sxs-lookup"><span data-stu-id="e0865-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span>

<span data-ttu-id="e0865-109">Pour plus d'informations sur la prise en charge des cartes cadeaux externes telles que SVS et Givex, consultez [Prise en charge des cartes cadeaux externes](./dev-itpro/gift-card.md)</span><span class="sxs-lookup"><span data-stu-id="e0865-109">For more information on support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md)</span></span>

<span data-ttu-id="e0865-110">L'image suivante montre un exemple de module de carte cadeau dans une page de caisse.</span><span class="sxs-lookup"><span data-stu-id="e0865-110">The following image shows an example of a gift card module on a checkout page.</span></span>

![Exemple d'un module de carte cadeau](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="e0865-112">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="e0865-112">Module properties</span></span>

- <span data-ttu-id="e0865-113">**Afficher des champs supplémentaires** - Cette propriété définit quels champs doivent être affichés pour les cartes cadeaux en plus du numéro de carte-cadeau, qui est toujours affiché par défaut.</span><span class="sxs-lookup"><span data-stu-id="e0865-113">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="e0865-114">Par exemple, certaines cartes cadeaux prennent en charge l'affichage d'un numéro d'identification personnel (PIN) et d'autres prennent en charge l'affichage d'un code PIN et d'une date d'expiration.</span><span class="sxs-lookup"><span data-stu-id="e0865-114">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="e0865-115">Alternativement, cette propriété peut être définie sur « Aucune », ce qui n'affichera que le numéro de la carte cadeau et aucun champ supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="e0865-115">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="e0865-116">Valeurs prises en charge :</span><span class="sxs-lookup"><span data-stu-id="e0865-116">Supported values:</span></span>
-   <span data-ttu-id="e0865-117">PIN</span><span class="sxs-lookup"><span data-stu-id="e0865-117">PIN</span></span>
-   <span data-ttu-id="e0865-118">Date d'expiration</span><span class="sxs-lookup"><span data-stu-id="e0865-118">Expiration date</span></span>
-   <span data-ttu-id="e0865-119">Code PIN et date d'expiration</span><span class="sxs-lookup"><span data-stu-id="e0865-119">PIN and expiration date</span></span> 
-   <span data-ttu-id="e0865-120">None</span><span class="sxs-lookup"><span data-stu-id="e0865-120">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="e0865-121">Paramètres du site pour les modules de cartes cadeaux</span><span class="sxs-lookup"><span data-stu-id="e0865-121">Site settings for gift card modules</span></span>

<span data-ttu-id="e0865-122">Dans le générateur de site Commerce, sous **Paramètres du site \> Extensions**, il y a un paramètre de module de carte cadeau appelé **Type de carte cadeau pris en charge**.</span><span class="sxs-lookup"><span data-stu-id="e0865-122">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="e0865-123">Ce paramètre prend en charge trois valeurs :</span><span class="sxs-lookup"><span data-stu-id="e0865-123">This setting supports three values:</span></span>
- <span data-ttu-id="e0865-124">**Carte cadeau Dynamics 365** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e0865-124">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="e0865-125">Ce paramètre n'est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="e0865-125">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="e0865-126">**Cartes cadeaux SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Givex et SVS.</span><span class="sxs-lookup"><span data-stu-id="e0865-126">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="e0865-127">Ce paramètre est pris en charge pour les utilisateurs connectés et anonymes sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="e0865-127">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="e0865-128">**Cartes cadeaux Dynamics 365, SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365, Givex et SVS.</span><span class="sxs-lookup"><span data-stu-id="e0865-128">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="e0865-129">Ce paramètre n'est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="e0865-129">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="e0865-130">Ajouter un module de carte cadeau à une page</span><span class="sxs-lookup"><span data-stu-id="e0865-130">Add a gift card module to a page</span></span>

<span data-ttu-id="e0865-131">Pour obtenir des instructions sur la façon d'ajouter un module de carte cadeau à une page de paiement et de définir les propriétés requises, voir [Module de paiement ](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="e0865-131">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e0865-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e0865-132">Additional resources</span></span>

[<span data-ttu-id="e0865-133">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="e0865-133">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="e0865-134">Module de validation</span><span class="sxs-lookup"><span data-stu-id="e0865-134">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="e0865-135">Prendre en charge des cartes cadeaux externes</span><span class="sxs-lookup"><span data-stu-id="e0865-135">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
