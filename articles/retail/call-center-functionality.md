---
title: "Fonctionnalité de centre d'appels"
description: "Cet article fournit une vue d'ensemble de la fonctionnalité de vente des centres d'appels dans Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2c58f71230a0781ee957632b453ced86ca03b15a
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="call-center-functionality"></a><span data-ttu-id="24379-103">Fonctionnalité de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="24379-103">Call center functionality</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="24379-104">Cet article fournit une vue d'ensemble de la fonctionnalité de vente des centres d'appels dans Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="24379-104">This article provides an overview of the call center sales functionality in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="24379-105">Dynamics 365 for Retail prend également en charge les centres d'appels comme type de canal de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="24379-105">Dynamics 365 for Retail supports call centers as a type of retail channel.</span></span> <span data-ttu-id="24379-106">Dans un centre d'appels, les collaborateurs prennent les commandes des clients par téléphone et créent les commandes client.</span><span class="sxs-lookup"><span data-stu-id="24379-106">In a call center, workers take orders from customers over the phone and create sales orders.</span></span> <span data-ttu-id="24379-107">La fonctionnalité de centre d'appels inclut les fonctionnalités conçues pour faciliter la prise de commandes par téléphone et la gestion du service client via le processus d'exécution de commande.</span><span class="sxs-lookup"><span data-stu-id="24379-107">Call center functionality includes features that are designed to make it easier to take phone orders and handle customer service throughout the order fulfillment process.</span></span> <span data-ttu-id="24379-108">Par exemple, les collaborateurs de centre d'appels peuvent entrer des informations de paiement directement dans la commande client, et peuvent afficher un résumé détaillé des frais et des paiements avant d'envoyer la commande.</span><span class="sxs-lookup"><span data-stu-id="24379-108">For example, call center workers can enter payment information directly into the sales order, and can view a detailed summary of charges and payments before they submit the order.</span></span> <span data-ttu-id="24379-109">Les collaborateurs disposent également d'options pour contrôler la tarification, et peuvent accéder à diverses données sur les clients, les produits, et les prix à partir de la page **Commande client**.</span><span class="sxs-lookup"><span data-stu-id="24379-109">Workers also have options for controlling pricing, and can access various data about customers, products, and prices from the **Sales order** page.</span></span> <span data-ttu-id="24379-110">En outre, les centres d'appel disposent d'une fonctionnalité améliorée de suivi de l'historique client et du statut des commandes.</span><span class="sxs-lookup"><span data-stu-id="24379-110">Additionally, call centers have enhanced functionality for tracking customer history and order status.</span></span> <span data-ttu-id="24379-111">Chaque centre d'appels peut avoir ses propres utilisateurs, modes de paiement, groupes de prix, dimensions financières, et modes de livraison.</span><span class="sxs-lookup"><span data-stu-id="24379-111">Each call center can have its own users, payment methods, price groups, financial dimensions, and modes of delivery.</span></span> <span data-ttu-id="24379-112">Vous pouvez configurer ces options lorsque vous créez les centres d'appels.</span><span class="sxs-lookup"><span data-stu-id="24379-112">You can configure these options when you create the call center.</span></span> <span data-ttu-id="24379-113">Vous pouvez également utiliser la page **Centre d'appels** pour activer ou désactiver les groupes de fonctions suivants, qui sont uniques aux centres d'appels :</span><span class="sxs-lookup"><span data-stu-id="24379-113">Additionally, you can use the **Call center** page to enable or disable the following groups of features that are unique to call centers:</span></span>

-   <span data-ttu-id="24379-114">**Achèvement de commande** – Ce groupe inclut les fonctionnalités liées aux paiements et à l'achèvement des commandes sur la page **Commande client**.</span><span class="sxs-lookup"><span data-stu-id="24379-114">**Order completion** – This group includes features that are related to payments and order completion on the **Sales order** page.</span></span>
-   <span data-ttu-id="24379-115">**Vente directe** – Ce groupe inclut les fonctionnalités associées aux codes sources, aux scripts, et aux demandes de catalogue.</span><span class="sxs-lookup"><span data-stu-id="24379-115">**Directed selling** – This group includes features that are related to source codes, scripts, and catalog requests.</span></span>

<span data-ttu-id="24379-116">Une fois que vous avez activé ces fonctionnalités dans les paramètres du centre d'appels, elles sont disponibles sur la page **Commande client** pour les utilisateurs associés au centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="24379-116">After you enable these features in the call center settings, they are available on the **Sales order** page to users who are associated with the call center.</span></span> <span data-ttu-id="24379-117">La plupart de ces fonctions requièrent un paramétrage supplémentaire avant d'être utilisées.</span><span class="sxs-lookup"><span data-stu-id="24379-117">Most of these features require additional setup before they can be used.</span></span> <span data-ttu-id="24379-118">Avant que les utilisateurs puissent créer des commandes de centre d'appels, vous devez ajouter ces utilisateurs au centre d'appels en tant qu'utilisateurs du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="24379-118">Before users can create call center orders, you must add those users to the call center as call center users.</span></span> <span data-ttu-id="24379-119">Cette étape active la configuration et la fonctionnalité spécifiques au canal de centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="24379-119">This step enables the call center channel-specific configuration and functionality.</span></span> <span data-ttu-id="24379-120">Voici quelques exemples de fonctionnalités qui deviennent disponibles :</span><span class="sxs-lookup"><span data-stu-id="24379-120">Here are some examples of the functionality that becomes available:</span></span>

-   <span data-ttu-id="24379-121">La vente guidée fournit des options de configuration pour les scripts de téléventes et les images de produits, afin d'aider et guider les commis aux ventes lors de la prise de commandes.</span><span class="sxs-lookup"><span data-stu-id="24379-121">Guided selling provides configuration options for telesales scripts and product images to help and guide sales clerks while they take orders.</span></span>
-   <span data-ttu-id="24379-122">Les commandes ne peuvent pas être bouclées tant que les commis aux ventes n'ont pas capturé au moins un mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="24379-122">Orders can't be completed until sales clerks have captured at least one payment method.</span></span>
-   <span data-ttu-id="24379-123">Les règles de vente de gamme supérieure et de vente croisée peuvent être configurés de sorte à inviter les commis aux vente à promouvoir des produits spécifiques auprès des clients.</span><span class="sxs-lookup"><span data-stu-id="24379-123">Upsell and cross-sell rules can be configured to prompt sales clerks to promote specific products to the customer.</span></span>
-   <span data-ttu-id="24379-124">Les commis aux ventes peuvent capturer le code source pour le catalogue à partir duquel un client passe sa commande.</span><span class="sxs-lookup"><span data-stu-id="24379-124">Sales clerks can capture the source code for the catalog that a customer is ordering from.</span></span>
-   <span data-ttu-id="24379-125">Les commis aux ventes peuvent ajouter les coupons d'un détaillant à une commande.</span><span class="sxs-lookup"><span data-stu-id="24379-125">Sales clerks can add a retailer's coupons to the order.</span></span>
-   <span data-ttu-id="24379-126">Les commis aux ventes peuvent vendre des programmes périodiques.</span><span class="sxs-lookup"><span data-stu-id="24379-126">Sales clerks can sell continuity programs.</span></span>
-   <span data-ttu-id="24379-127">Les commandes peuvent être mise en attente manuellement ou automatiquement, de sorte à indiquer que des recherches complémentaires sont nécessaires avant que la commande puisse être traitée.</span><span class="sxs-lookup"><span data-stu-id="24379-127">Orders can be put on hold manually or automatically, to indicate that additional investigation is required before the order can be processed.</span></span>





