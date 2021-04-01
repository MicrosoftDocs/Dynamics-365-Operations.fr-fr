---
title: Vente et retourner des produits ne faisant pas partie de l'assortiment d'un magasin
description: Avec Dynamics 365 Commerce, vous pouvez vendre et renvoyer les produits en dehors des assortiments.
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 18d91287bfdcca272b5dd5e8dc8e04b1fd937a6d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254695"
---
# <a name="sell-and-return-products-that-arent-part-of-a-stores-assortment"></a><span data-ttu-id="dffe8-103">Vente et retourner des produits ne faisant pas partie de l'assortiment d'un magasin</span><span class="sxs-lookup"><span data-stu-id="dffe8-103">Sell and return products that aren't part of a store's assortment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dffe8-104">Un scénario courant pour un détaillant est de vendre des produits à ses clients ou d'accepter des retours de ses clients même s'il ne propose pas les produits spécifiques dans son magasin (autrement dit, les produits ne sont pas assortis au magasin).</span><span class="sxs-lookup"><span data-stu-id="dffe8-104">A common scenario for any retailer is to sell products to their customers or accept returns from their customers even if they don't carry the specific products in their store (in other words, the products are not assorted to the store).</span></span>

<span data-ttu-id="dffe8-105">Voici quelques scénarios classiques :</span><span class="sxs-lookup"><span data-stu-id="dffe8-105">Here are some typical scenarios:</span></span>

+ <span data-ttu-id="dffe8-106">Un détaillant ne propose pas tous ses produits dans un magasin spécifique.</span><span class="sxs-lookup"><span data-stu-id="dffe8-106">A retailer doesn't carry all its products in a specific store.</span></span> <span data-ttu-id="dffe8-107">Les articles restants sont stockés dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="dffe8-107">The remaining products are stored in the warehouse.</span></span> <span data-ttu-id="dffe8-108">L'associé du magasin aide le client en recherchant ou en parcourant les produits dans l'entrepôt, les ajoute au chariot et procède à la validation en sélectionnant un mode de livraison, par exemple expédier le produit une adresse à partir de l'entrepôt ou laisser le client récupérer le produit dans le magasin actuel ou dans un autre magasin.</span><span class="sxs-lookup"><span data-stu-id="dffe8-108">The store associate can assist the customer by searching or browsing for the products in the warehouse, add them to the cart, and complete the checkout by selecting a delivery method, such as shipping to an address from the warehouse or letting the customer pick up the product from the current store or from another store.</span></span>
+ <span data-ttu-id="dffe8-109">Un détaillant ne propose pas des produits spécifiques dans le magasin ou n'en a pas en stock dans le magasin où le client s'est rendu, mais les produits sont disponibles dans d'autres magasins.</span><span class="sxs-lookup"><span data-stu-id="dffe8-109">A retailer doesn't carry specific products in the store or doesn't have them in stock at the store the customer visited, but the products are available in other stores.</span></span> <span data-ttu-id="dffe8-110">L'associé du magasin aide le client en recherchant ou en parcourant les produits dans l'autre magasin, les ajoute au chariot et procède à la validation en sélectionnant un mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="dffe8-110">The store associate can assist the customer by searching or browsing the products in the other store, add them to the cart, and complete the checkout by selecting a delivery method.</span></span>
+ <span data-ttu-id="dffe8-111">Un détaillant a plusieurs magasins dans et autour d'une ville ou d'un code postal spécifique et ne souhaite pas obliger les clients à retourner les produits dans le magasin d'achat.</span><span class="sxs-lookup"><span data-stu-id="dffe8-111">A retailer has many stores in and around a specific city or zip code and doesn't want to force the customers to return products to the same store they were purchased in.</span></span> <span data-ttu-id="dffe8-112">À la place, les clients peuvent retourner les produits dans n'importe quel magasin.</span><span class="sxs-lookup"><span data-stu-id="dffe8-112">Instead, customers can return products to any store.</span></span>

<span data-ttu-id="dffe8-113">Ces scénarios courants sont disponibles aux détaillants qui utilisent Commerce.</span><span class="sxs-lookup"><span data-stu-id="dffe8-113">Those common scenarios are available for retailers using Commerce.</span></span> <span data-ttu-id="dffe8-114">Avec Commerce, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="dffe8-114">With Commerce, you can:</span></span>

+ <span data-ttu-id="dffe8-115">Rechercher ou parcourir les produits dans d'autres magasins.</span><span class="sxs-lookup"><span data-stu-id="dffe8-115">Search or browse products at other stores.</span></span>
+ <span data-ttu-id="dffe8-116">Rechercher ou parcourir tous les produits lancés.</span><span class="sxs-lookup"><span data-stu-id="dffe8-116">Search or browse all released products.</span></span>
+ <span data-ttu-id="dffe8-117">Créer des transactions ou des commandes client avec paiement comptant sans livraison.</span><span class="sxs-lookup"><span data-stu-id="dffe8-117">Create cash-and-carry transactions or customer orders.</span></span>
+ <span data-ttu-id="dffe8-118">Sélectionner les options de livraison pour les commandes client.</span><span class="sxs-lookup"><span data-stu-id="dffe8-118">Select delivery options for customer orders.</span></span>
+ <span data-ttu-id="dffe8-119">Récupérer les produits dans le magasin actuel ou un autre magasin.</span><span class="sxs-lookup"><span data-stu-id="dffe8-119">Pick up products at the current store or another store.</span></span>
+ <span data-ttu-id="dffe8-120">Annuler une commande dans le magasin actuel ou un autre magasin.</span><span class="sxs-lookup"><span data-stu-id="dffe8-120">Cancel an order at the current store or another store.</span></span>
+ <span data-ttu-id="dffe8-121">Retourner une commande avec ou sans l'accusé de réception dans le magasin actuel ou un autre magasin.</span><span class="sxs-lookup"><span data-stu-id="dffe8-121">Return an order with or without the receipt at the current store or another store.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]