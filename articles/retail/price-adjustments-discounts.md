---
title: Ajustements de prix et remises
description: Cet article fournit des informations sur les ajustements de prix et les remises dans Microsoft Dynamics 365 for Retail.
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 61ac8e5fbdc4d91bb5bc5372a7fb96633043473a
ms.contentlocale: fr-fr
ms.lasthandoff: 01/04/2019

---

# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="1d784-103">Ajustements de prix et remises</span><span class="sxs-lookup"><span data-stu-id="1d784-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1d784-104">Cet article fournit des informations sur les ajustements de prix et les remises dans Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="1d784-104">This article provides information about price adjustments and discounts in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="1d784-105">Dans Dynamics 365 for Retail, vous pouvez procéder à des ajustements de prix des produits, et aussi définir des remises à appliquer à une ligne ou une transaction au point de vente, dans une commande client du centre d'appels ou dans une commande en ligne.</span><span class="sxs-lookup"><span data-stu-id="1d784-105">In Dynamics 365 for Retail, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="1d784-106">Tant les ajustements de prix que les remises peuvent être liés à des groupes de prix.</span><span class="sxs-lookup"><span data-stu-id="1d784-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="1d784-107">Pour les ajustements de prix et les remises, vous pouvez spécifier une date de début et une date de fin uniques ou une période récurrente, un code remise et quelques attributs supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="1d784-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> <span data-ttu-id="1d784-108">Les ajustements de prix et les remises peuvent être appliqués aux produits, variantes ou catégories.</span><span class="sxs-lookup"><span data-stu-id="1d784-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="1d784-109">Si plusieurs remises s'appliquent à un produit, un client peut recevoir une des remises ou une remise combinée, selon la configuration de la remise.</span><span class="sxs-lookup"><span data-stu-id="1d784-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="1d784-110">Dynamics 365 for Retail applique automatiquement la remise ou une combinaison de remises qui fournit le meilleur prix au client.</span><span class="sxs-lookup"><span data-stu-id="1d784-110">Dynamics 365 for Retail automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="1d784-111">Lorsque vous paramétrez un ajustement de prix ou une remise, veillez à confirmer que les groupes de prix sont affectés aux canaux, catalogues, affiliations ou programmes de fidélité appropriés auxquels vous souhaitez appliquer la remise.</span><span class="sxs-lookup"><span data-stu-id="1d784-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="1d784-112">En outre, si vous souhaitez générer automatiquement l'ID remise, définissez des souches de numéros dans la page **Paramètres des ventes au détail** avant de définir un nouvel ajustement de prix ou une nouvelle remise.</span><span class="sxs-lookup"><span data-stu-id="1d784-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Retail parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="1d784-113">Vous pouvez supprimer un ajustement de prix ou une remise.</span><span class="sxs-lookup"><span data-stu-id="1d784-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="1d784-114">Toutefois, les informations statistiques sont perdues.</span><span class="sxs-lookup"><span data-stu-id="1d784-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="1d784-115">Types de remises</span><span class="sxs-lookup"><span data-stu-id="1d784-115">Types of discounts</span></span>

<span data-ttu-id="1d784-116">Il existe quatre types de remises de vente au détail :</span><span class="sxs-lookup"><span data-stu-id="1d784-116">There are four types of retail discounts:</span></span>

- <span data-ttu-id="1d784-117">**Remise simple** – Un pourcentage ou montant individuel.</span><span class="sxs-lookup"><span data-stu-id="1d784-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="1d784-118">**Remise sur quantité** – Une remise est appliquée lorsqu'au moins deux produits sont achetés.</span><span class="sxs-lookup"><span data-stu-id="1d784-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="1d784-119">**Remise mix and match** – Une remise est appliquée lorsqu'une combinaison spécifique de produits est achetée.</span><span class="sxs-lookup"><span data-stu-id="1d784-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="1d784-120">**Remise seuil** – Une remise est appliquée lorsque le total de la transaction est supérieur à un montant spécifié.</span><span class="sxs-lookup"><span data-stu-id="1d784-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>

<span data-ttu-id="1d784-121">Tant les ajustements de prix que les remises peuvent être associés à des groupes de prix.</span><span class="sxs-lookup"><span data-stu-id="1d784-121">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="1d784-122">Les groupes de prix peuvent ensuite être associés à des canaux, catalogues, affiliations et programmes de fidélité.</span><span class="sxs-lookup"><span data-stu-id="1d784-122">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>

