---
title: Vente et retour de produits en dehors d'un assortiment
description: "Avec Dynamics 365 for Retail, vous pouvez vendre et retourner des produits en dehors d'assortiments."
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 82b3076eba0d374c80e37572233cf7ba440cc65a
ms.contentlocale: fr-fr
ms.lasthandoff: 03/07/2018

---

# <a name="sell-and-return-products-outside-of-an-assortment"></a><span data-ttu-id="45aa3-103">Vente et retour de produits en dehors d'un assortiment</span><span class="sxs-lookup"><span data-stu-id="45aa3-103">Sell and return products outside of an assortment</span></span>

[!include[banner](includes/banner.md)]

<span data-ttu-id="45aa3-104">Un scénario courant pour un détaillant est de vendre des produits à ses clients ou d'accepter des retours de ses clients même s'il ne propose pas les produits spécifiques dans son magasin (autrement dit, les produits ne sont pas assortis au magasin).</span><span class="sxs-lookup"><span data-stu-id="45aa3-104">A common scenario for any retailer is to sell products to their customers or accept returns from their customers even if they don’t carry the specific products in their store (in other words, the products are not assorted to the store).</span></span>
<span data-ttu-id="45aa3-105">Voici quelques scénarios classiques :</span><span class="sxs-lookup"><span data-stu-id="45aa3-105">Here are some typical scenarios:</span></span>

+ <span data-ttu-id="45aa3-106">Un détaillant ne propose pas tous ses produits dans un magasin spécifique.</span><span class="sxs-lookup"><span data-stu-id="45aa3-106">A retailer doesn’t carry all its products in a specific store.</span></span> <span data-ttu-id="45aa3-107">Les articles restants sont stockés dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="45aa3-107">The remaining products are stored in the warehouse.</span></span> <span data-ttu-id="45aa3-108">L'associé du magasin aide le client en recherchant ou en parcourant les produits dans l'entrepôt, les ajoute au chariot et procède à la validation en sélectionnant un mode de livraison, par exemple expédier le produit une adresse à partir de l'entrepôt ou laisser le client récupérer le produit dans le magasin actuel ou dans un autre magasin.</span><span class="sxs-lookup"><span data-stu-id="45aa3-108">The store associate can assist the customer by searching or browsing for the products in the warehouse, add them to the cart, and complete the checkout by selecting a delivery method, such as shipping to an address from the warehouse or letting the customer pick up the product from the current store or from another store.</span></span>
+ <span data-ttu-id="45aa3-109">Un détaillant ne propose pas des produits spécifiques dans le magasin ou n'en a pas en stock dans le magasin où le client s'est rendu, mais les produits sont disponibles dans d'autres magasins.</span><span class="sxs-lookup"><span data-stu-id="45aa3-109">A retailer doesn’t carry specific products in the store or doesn’t have them in stock at the store the customer visited, but the products are available in other stores.</span></span> <span data-ttu-id="45aa3-110">L'associé du magasin aide le client en recherchant ou en parcourant les produits dans l'autre magasin, les ajoute au chariot et procède à la validation en sélectionnant un mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="45aa3-110">The store associate can assist the customer by searching or browsing the products in the other store, add them to the cart, and complete the checkout by selecting a delivery method.</span></span>
+ <span data-ttu-id="45aa3-111">Un détaillant a plusieurs magasins dans et autour d'une ville ou d'un code postal spécifique et ne souhaite pas obliger les clients à retourner les produits dans le magasin d'achat.</span><span class="sxs-lookup"><span data-stu-id="45aa3-111">A retailer has many stores in and around a specific city or zip code and doesn’t want to force the customers to return products to the same store they were purchased in.</span></span> <span data-ttu-id="45aa3-112">À la place, les clients peuvent retourner les produits dans n'importe quel magasin.</span><span class="sxs-lookup"><span data-stu-id="45aa3-112">Instead, customers can return products to any store.</span></span>


<span data-ttu-id="45aa3-113">Ces scénarios courants sont disponibles pour les détaillants qui utilisent Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="45aa3-113">Those common scenarios are available for retailers using Dynamics 365 for Retail.</span></span> <span data-ttu-id="45aa3-114">Retail vous permet de :</span><span class="sxs-lookup"><span data-stu-id="45aa3-114">With Retail, you can:</span></span>
+ <span data-ttu-id="45aa3-115">Rechercher ou parcourir les produits dans d'autres magasins.</span><span class="sxs-lookup"><span data-stu-id="45aa3-115">Search or browse products at other stores.</span></span>
+ <span data-ttu-id="45aa3-116">Rechercher ou parcourir tous les produits lancés.</span><span class="sxs-lookup"><span data-stu-id="45aa3-116">Search or browse all released products.</span></span>
+ <span data-ttu-id="45aa3-117">Créer des transactions ou des commandes client avec paiement comptant sans livraison.</span><span class="sxs-lookup"><span data-stu-id="45aa3-117">Create cash-and-carry transactions or customer orders.</span></span>
+ <span data-ttu-id="45aa3-118">Sélectionner les options de livraison pour les commandes client.</span><span class="sxs-lookup"><span data-stu-id="45aa3-118">Select delivery options for customer orders.</span></span>
+ <span data-ttu-id="45aa3-119">Récupérer les produits dans le magasin actuel ou un autre magasin.</span><span class="sxs-lookup"><span data-stu-id="45aa3-119">Pick up products at the current store or another store.</span></span>
+ <span data-ttu-id="45aa3-120">Annuler une commande dans le magasin actuel ou un autre magasin.</span><span class="sxs-lookup"><span data-stu-id="45aa3-120">Cancel an order at the current store or another store.</span></span>
+ <span data-ttu-id="45aa3-121">Retourner une commande avec ou sans l'accusé de réception dans le magasin actuel ou un autre magasin.</span><span class="sxs-lookup"><span data-stu-id="45aa3-121">Return an order with or without the receipt at the current store or another store.</span></span>

