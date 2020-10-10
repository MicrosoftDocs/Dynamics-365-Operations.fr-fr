---
title: Sources courantes des écarts de production
description: Cet article décrit diverses sources typiques de chaque type d'écart de production.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcVarianceTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc310f1d5e1f99a320b803f68395d0926d39780b
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826741"
---
# <a name="common-sources-of-production-variances"></a><span data-ttu-id="c6fa1-103">Sources courantes des écarts de production</span><span class="sxs-lookup"><span data-stu-id="c6fa1-103">Common sources of production variances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6fa1-104">Cet article décrit diverses sources typiques de chaque type d'écart de production.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-104">This article explains various typical sources of each type of production variance.</span></span> 

<span data-ttu-id="c6fa1-105">Voici quelques sources typiques d'écart de **taille de lot** :</span><span class="sxs-lookup"><span data-stu-id="c6fa1-105">Here are some typical sources of a **lot size** variance:</span></span>

-   <span data-ttu-id="c6fa1-106">La quantité correcte d'un ordre de fabrication diffère de la quantité de calcul utilisée dans le calcul de coût standard.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-106">The good quantity for a production order differs from the calculation quantity that is used in the standard cost calculation.</span></span> <span data-ttu-id="c6fa1-107">La quantité fournit la base pour l'amortissement des coûts constants.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-107">The quantity provides the basis for amortizing constant costs.</span></span>
-   <span data-ttu-id="c6fa1-108">La valeur des coûts constants de l'ordre de fabrication diffère des coûts constants utilisés dans le calcul du coût standard.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-108">The value of constant costs on the production order differs from the constant costs that are used in the standard cost calculation.</span></span> <span data-ttu-id="c6fa1-109">Les coûts constants de l'ordre de fabrication peuvent être différents pour plusieurs raisons.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-109">The constant costs on the production order can differ for several reasons.</span></span> <span data-ttu-id="c6fa1-110">Par exemple, les coûts constants peuvent refléter les facteurs suivants :</span><span class="sxs-lookup"><span data-stu-id="c6fa1-110">For example, the constant costs might reflect the following factors:</span></span>
    -   <span data-ttu-id="c6fa1-111">les modifications manuelles apportées à la nomenclature de production ou gamme ;</span><span class="sxs-lookup"><span data-stu-id="c6fa1-111">Manual changes to the production bill of materials (BOM) or route</span></span>
    -   <span data-ttu-id="c6fa1-112">la sélection d'une autre version de nomenclature ou version de gamme lors de la création de l'ordre de fabrication ;</span><span class="sxs-lookup"><span data-stu-id="c6fa1-112">The selection of a different BOM version or route version when you create the production order</span></span>
    -   <span data-ttu-id="c6fa1-113">des modifications d'ingénierie planifiées à la version de nomenclature ou version de gamme affectée à l'article.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-113">Planned engineering changes to the BOM version or route version that is assigned to the item</span></span>

<span data-ttu-id="c6fa1-114">Voici quelques sources typiques d'écart de **prix de production** :</span><span class="sxs-lookup"><span data-stu-id="c6fa1-114">Here are some typical sources of a **production price** variance:</span></span>

-   <span data-ttu-id="c6fa1-115">La catégorie de coûts (et son prix de catégorie de coûts) pour la consommation déclarée d'une opération d'acheminement diffère de la catégorie de coûts utilisée dans le calcul de coûts standard.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-115">The cost category (and cost category price) for the reported consumption of a routing operation differs from the cost category that is used in standard cost calculation.</span></span>
-   <span data-ttu-id="c6fa1-116">Le coût actif pour le prix de la catégorie de coûts diffère du prix de la catégorie de coûts utilisé dans le calcul du coût standard.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-116">The active cost for the cost category price differs from the cost category price that is used in standard cost calculation.</span></span>

<span data-ttu-id="c6fa1-117">Voici quelques sources typiques d'écart de **quantité de production** :</span><span class="sxs-lookup"><span data-stu-id="c6fa1-117">Here are some typical sources of a **production quantity** variance:</span></span>

-   <span data-ttu-id="c6fa1-118">Vous effectuez une sortie excessive ou insuffisante d'un composant de matériau.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-118">You over-issue or under-issue a material component.</span></span>
-   <span data-ttu-id="c6fa1-119">Vous déclarez des heures excessives ou insuffisantes pour une opération d'acheminement.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-119">You over-report or under-report the time for a routing operation.</span></span>
-   <span data-ttu-id="c6fa1-120">Vous déclarez la réception de manière excédentaire ou insuffisante de la quantité correcte de l'article parent par rapport à la quantité commandée.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-120">You over-receive or under-receive the good quantity of the parent item, relative to the order quantity.</span></span> <span data-ttu-id="c6fa1-121">Toutefois, vous sortez les composants et déclarez les opérations selon la quantité de la commande pour l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-121">However, you issue components and report operations completely, based on the order quantity for the production order.</span></span>

<span data-ttu-id="c6fa1-122">Voici quelques sources typiques d'écart d'une **substitution de production** :</span><span class="sxs-lookup"><span data-stu-id="c6fa1-122">Here are some typical sources of a **production substitution** variance:</span></span>

-   <span data-ttu-id="c6fa1-123">Vous sortez un composant de matériau absent de la nomenclature de production.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-123">You issue a material component that isn't on the production BOM.</span></span>
-   <span data-ttu-id="c6fa1-124">Vous ajoutez manuellement un composant à la nomenclature de production et déclarez ce composant comme étant consommé.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-124">You manually add a component to the production BOM and report that component as consumed.</span></span>
-   <span data-ttu-id="c6fa1-125">Vous déclarez un article comme étant consommé sans l'ajouter manuellement à la nomenclature de production.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-125">You report an item as consumed but don't manually add it to the production BOM.</span></span>
-   <span data-ttu-id="c6fa1-126">Vous ajoutez manuellement une opération à la gamme de production et déclarez cette opération comme étant consommée.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-126">You manually add an operation to the production route and report that operation as consumed.</span></span>
-   <span data-ttu-id="c6fa1-127">Lorsque vous créez l'ordre de fabrication, vous sélectionnez une version de nomenclature différente de celle utilisée dans le calcul de coûts standard.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-127">When you create the production order, you select a BOM version that differs from the BOM version that is used in the standard cost calculation.</span></span>
-   <span data-ttu-id="c6fa1-128">Lorsque vous créez l'ordre de fabrication, vous sélectionnez une version de gamme différente de celle utilisée dans le calcul de coûts standard.</span><span class="sxs-lookup"><span data-stu-id="c6fa1-128">When you create the production order, you select a route version that differs from the route version that is used in the standard cost calculation.</span></span>




