---
title: Module de carte cadeau
description: Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
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
ms.openlocfilehash: 70047376cec44523cc9cfe4df792bde23c776d8c
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261567"
---
# <a name="gift-card-module"></a><span data-ttu-id="39a90-103">Module de carte cadeau</span><span class="sxs-lookup"><span data-stu-id="39a90-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="39a90-104">Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="39a90-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="39a90-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="39a90-105">Overview</span></span>

<span data-ttu-id="39a90-106">Les cartes cadeaux sont un mode de paiement courant et le module de cartes cadeaux peut être utilisé dans un module de paiement pour accepter des cartes cadeaux.</span><span class="sxs-lookup"><span data-stu-id="39a90-106">Gift cards are a common form of payment, and the gift card module can be used in a checkout module to accept gift cards.</span></span> <span data-ttu-id="39a90-107">Le module de carte cadeau prend en charge les cartes cadeaux Dynamics 365, SVS et Givex.</span><span class="sxs-lookup"><span data-stu-id="39a90-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="39a90-108">Les cartes cadeaux SVS et Givex sont échangées via le fournisseur de paiement Adyen.</span><span class="sxs-lookup"><span data-stu-id="39a90-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span>

<span data-ttu-id="39a90-109">Pour plus d'informations sur la prise en charge des cartes cadeaux externes telles que SVS et Givex, consultez [Prise en charge des cartes cadeaux externes](./dev-itpro/gift-card.md)</span><span class="sxs-lookup"><span data-stu-id="39a90-109">For more information on support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md)</span></span>

## <a name="module-properties"></a><span data-ttu-id="39a90-110">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="39a90-110">Module properties</span></span>

- <span data-ttu-id="39a90-111">**Afficher des champs supplémentaires** - Cette propriété définit quels champs doivent être affichés pour les cartes cadeaux en plus du numéro de carte-cadeau, qui est toujours affiché par défaut.</span><span class="sxs-lookup"><span data-stu-id="39a90-111">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="39a90-112">Par exemple, certaines cartes cadeaux prennent en charge l'affichage d'un numéro d'identification personnel (PIN) et d'autres prennent en charge l'affichage d'un code PIN et d'une date d'expiration.</span><span class="sxs-lookup"><span data-stu-id="39a90-112">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="39a90-113">Alternativement, cette propriété peut être définie sur « Aucune », ce qui n'affichera que le numéro de la carte cadeau et aucun champ supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="39a90-113">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="39a90-114">Valeurs prises en charge :</span><span class="sxs-lookup"><span data-stu-id="39a90-114">Supported values:</span></span>
-   <span data-ttu-id="39a90-115">PIN</span><span class="sxs-lookup"><span data-stu-id="39a90-115">PIN</span></span>
-   <span data-ttu-id="39a90-116">Date d'expiration</span><span class="sxs-lookup"><span data-stu-id="39a90-116">Expiration date</span></span>
-   <span data-ttu-id="39a90-117">Code PIN et date d'expiration</span><span class="sxs-lookup"><span data-stu-id="39a90-117">PIN and expiration date</span></span> 
-   <span data-ttu-id="39a90-118">None</span><span class="sxs-lookup"><span data-stu-id="39a90-118">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="39a90-119">Paramètres du site pour les modules de cartes cadeaux</span><span class="sxs-lookup"><span data-stu-id="39a90-119">Site settings for gift card modules</span></span>

<span data-ttu-id="39a90-120">Dans le générateur de site Commerce, sous **Paramètres du site \> Extensions**, il y a un paramètre de module de carte cadeau appelé **Type de carte cadeau pris en charge**.</span><span class="sxs-lookup"><span data-stu-id="39a90-120">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="39a90-121">Ce paramètre prend en charge trois valeurs :</span><span class="sxs-lookup"><span data-stu-id="39a90-121">This setting supports three values:</span></span>
- <span data-ttu-id="39a90-122">**Carte cadeau Dynamics 365** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="39a90-122">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="39a90-123">Ce paramètre n'est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="39a90-123">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="39a90-124">**Cartes cadeaux SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Givex et SVS.</span><span class="sxs-lookup"><span data-stu-id="39a90-124">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="39a90-125">Ce paramètre est pris en charge pour les utilisateurs connectés et anonymes sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="39a90-125">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="39a90-126">**Cartes cadeaux Dynamics 365, SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365, Givex et SVS.</span><span class="sxs-lookup"><span data-stu-id="39a90-126">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="39a90-127">Ce paramètre n'est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="39a90-127">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="39a90-128">Ajouter un module de carte cadeau à une page</span><span class="sxs-lookup"><span data-stu-id="39a90-128">Add a gift card module to a page</span></span>

<span data-ttu-id="39a90-129">Pour obtenir des instructions sur la façon d'ajouter un module de carte cadeau à une page de paiement et de définir les propriétés requises, voir [Module de paiement ](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="39a90-129">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="39a90-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="39a90-130">Additional resources</span></span>

[<span data-ttu-id="39a90-131">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="39a90-131">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="39a90-132">Module de validation</span><span class="sxs-lookup"><span data-stu-id="39a90-132">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="39a90-133">Prendre en charge des cartes cadeaux externes</span><span class="sxs-lookup"><span data-stu-id="39a90-133">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
