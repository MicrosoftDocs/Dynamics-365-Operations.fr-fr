---
title: Ajustements de prix et remises
description: Cet article offre des informations relatives aux ajustements de prix et aux rabais dans Dynamics 365 Commerce.
author: scott-tucker
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: 0c2adaa5cd935d5b593bfbb3215d3466fcafab7b
ms.sourcegitcommit: 1d74636bf9db5fb33e998322899504b709b4f89f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/19/2020
ms.locfileid: "4584313"
---
# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="649c1-103">Ajustements de prix et remises</span><span class="sxs-lookup"><span data-stu-id="649c1-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="649c1-104">Cet article offre des informations relatives aux ajustements de prix et aux rabais dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="649c1-104">This article provides information about price adjustments and discounts in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="649c1-105">Dans Commerce, procédez des ajustements de prix sur les produits et paramétrez des remises appliquées à une ligne ou une transaction au point de vente (PDV), au niveau d'une commande client enregistrée par un centre d'appels ou au niveau d'une commande en ligne.</span><span class="sxs-lookup"><span data-stu-id="649c1-105">In Commerce, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="649c1-106">Tant les ajustements de prix que les remises peuvent être liés à des groupes de prix.</span><span class="sxs-lookup"><span data-stu-id="649c1-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="649c1-107">Pour les ajustements de prix et les remises, vous pouvez spécifier une date de début et une date de fin uniques ou une période récurrente, un code remise et quelques attributs supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="649c1-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> 

<span data-ttu-id="649c1-108">Les ajustements de prix et les remises peuvent être appliqués aux produits, variantes ou catégories.</span><span class="sxs-lookup"><span data-stu-id="649c1-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="649c1-109">Si plusieurs remises s'appliquent à un produit, un client peut recevoir une des remises ou une remise combinée, selon la configuration de la remise.</span><span class="sxs-lookup"><span data-stu-id="649c1-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="649c1-110">Commerce applique automatiquement la remise ou une combinaison de remises qui fournit le meilleur prix au client.</span><span class="sxs-lookup"><span data-stu-id="649c1-110">Commerce automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="649c1-111">Lorsque vous paramétrez un ajustement de prix ou une remise, veillez à confirmer que les groupes de prix sont affectés aux canaux, catalogues, affiliations ou programmes de fidélité appropriés auxquels vous souhaitez appliquer la remise.</span><span class="sxs-lookup"><span data-stu-id="649c1-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="649c1-112">En outre, si vous souhaitez générer automatiquement l'ID de remise, configurez les souches de numéros dans la page **Paramètres de commerce** avant de définir un nouvel ajustement de prix ou une nouvelle remise.</span><span class="sxs-lookup"><span data-stu-id="649c1-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Commerce parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="649c1-113">Vous pouvez supprimer un ajustement de prix ou une remise.</span><span class="sxs-lookup"><span data-stu-id="649c1-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="649c1-114">Toutefois, les informations statistiques sont perdues.</span><span class="sxs-lookup"><span data-stu-id="649c1-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="649c1-115">Types de remises</span><span class="sxs-lookup"><span data-stu-id="649c1-115">Types of discounts</span></span>

<span data-ttu-id="649c1-116">Il existe plusieurs types de remise :</span><span class="sxs-lookup"><span data-stu-id="649c1-116">There are many types of discounts:</span></span>

- <span data-ttu-id="649c1-117">**Remise simple** – Un pourcentage ou montant individuel.</span><span class="sxs-lookup"><span data-stu-id="649c1-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="649c1-118">**Remise sur quantité** – Une remise est appliquée lorsqu'au moins deux produits sont achetés.</span><span class="sxs-lookup"><span data-stu-id="649c1-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="649c1-119">**Remise mix and match** – Une remise est appliquée lorsqu'une combinaison spécifique de produits est achetée.</span><span class="sxs-lookup"><span data-stu-id="649c1-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="649c1-120">**Remise seuil** – Une remise est appliquée lorsque le total de la transaction est supérieur à un montant spécifié.</span><span class="sxs-lookup"><span data-stu-id="649c1-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>
- <span data-ttu-id="649c1-121">**Remise sur appel d'offres** – Remise appliquée lorsque le total de la transaction est supérieur à un montant spécifié et qu'un type de paiement spécifique (par exemple, espèces, carte de crédit ou de débit) est utilisé pour le paiement.</span><span class="sxs-lookup"><span data-stu-id="649c1-121">**Tender-based discount** – A discount that is applied when the transaction total is more than a specified amount and a specific payment type (for example, cash, credit, or debit card) is used for payment.</span></span>
- <span data-ttu-id="649c1-122">**Remise sur l'expédition** – Une remise qui est appliquée lorsque le total de la transaction est supérieur à un montant spécifié et qu'un mode de livraison spécifique (par exemple, expédition sous deux jours ou livraison le lendemain) est utilisé sur la commande.</span><span class="sxs-lookup"><span data-stu-id="649c1-122">**Shipping discount** – A discount that is applied when the transaction total is more than a specified amount and a specific mode of delivery (for example, two day shipping or overnight shipping) is used on the order.</span></span>

<span data-ttu-id="649c1-123">Tant les ajustements de prix que les remises peuvent être associés à des groupes de prix.</span><span class="sxs-lookup"><span data-stu-id="649c1-123">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="649c1-124">Les groupes de prix peuvent ensuite être associés à des canaux, catalogues, affiliations et programmes de fidélité.</span><span class="sxs-lookup"><span data-stu-id="649c1-124">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>
