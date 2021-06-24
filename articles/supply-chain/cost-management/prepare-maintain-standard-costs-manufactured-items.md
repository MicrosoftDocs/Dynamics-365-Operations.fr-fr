---
title: Préparation de la mise à jour des coûts standard pour les articles fabriqués
description: Cette rubrique décrit les étapes de préparation de la mise à jour des coûts pour les articles fabriqués.
author: AndersGirke
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a82b0a205ac6b7a86b9aca0771303469c6666c1
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187744"
---
# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a><span data-ttu-id="26a69-103">Préparation de la mise à jour des coûts standard pour les articles fabriqués</span><span class="sxs-lookup"><span data-stu-id="26a69-103">Prepare to maintain standard costs for manufactured items</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26a69-104">Cette rubrique décrit les étapes de préparation de la mise à jour des coûts pour les articles fabriqués.</span><span class="sxs-lookup"><span data-stu-id="26a69-104">This topic describes the steps for preparing to maintain costs for manufactured items.</span></span> <span data-ttu-id="26a69-105">Les étapes pour les articles fabriqués diffèrent légèrement des étapes pour les articles achetés.</span><span class="sxs-lookup"><span data-stu-id="26a69-105">The steps for manufactured items differ slightly from the steps for purchased items.</span></span>

<span data-ttu-id="26a69-106">Les stratégies appliquées aux articles fabriqués peuvent affecter les calculs de coûts pour les articles fabriqués parents.</span><span class="sxs-lookup"><span data-stu-id="26a69-106">Policies that are assigned to manufactured items can affect the cost calculations for the parent manufactured items.</span></span> <span data-ttu-id="26a69-107">Pour préparer la mise à jour des coûts pour les articles fabriqués, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="26a69-107">To prepare to maintain costs for manufactured items, follow these steps.</span></span>

1. <span data-ttu-id="26a69-108">Affectez un groupe de modèles d’article à l’article fabriqué.</span><span class="sxs-lookup"><span data-stu-id="26a69-108">Assign an item model group to the manufactured item.</span></span> 

   <span data-ttu-id="26a69-109">Le groupe de modèles d’article identifie que les coûts standard sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="26a69-109">The item model group identifies that standard costs will be used.</span></span>

2. <span data-ttu-id="26a69-110">Affectez un groupe d’articles à l’objet fabriqué.</span><span class="sxs-lookup"><span data-stu-id="26a69-110">Assign an item group to the manufactured item.</span></span> 

   <span data-ttu-id="26a69-111">Le groupe d’articles contient des comptes généraux qui s’appliquent à l’article fabriqué.</span><span class="sxs-lookup"><span data-stu-id="26a69-111">The item group contains ledger accounts that apply to the manufactured item.</span></span> <span data-ttu-id="26a69-112">Les comptes généraux pour un article fabriqué avec un modèle de stock de coût standard comprennent plusieurs écarts de production, l’écart de modification des coûts et la réévaluation des coûts de stock.</span><span class="sxs-lookup"><span data-stu-id="26a69-112">The ledger accounts for a manufactured item that has a standard cost inventory model include several production variances, the cost change variance, and the inventory cost revaluation.</span></span>

3. <span data-ttu-id="26a69-113">Affectez l’unité de mesure de stock à l’article.</span><span class="sxs-lookup"><span data-stu-id="26a69-113">Assign the inventory unit of measure to the item.</span></span> 

   <span data-ttu-id="26a69-114">Les coûts de l’article sont toujours exprimés dans l’unité de mesure de stock de l’article.</span><span class="sxs-lookup"><span data-stu-id="26a69-114">The item's costs are always expressed in the item's inventory unit of measure.</span></span>

4. <span data-ttu-id="26a69-115">N’affectez pas un groupe de coûts à l’article fabriqué, à moins qu’il ne soit traité comme un article acheté.</span><span class="sxs-lookup"><span data-stu-id="26a69-115">Don't assign a cost group to the manufactured item unless the item will be treated as a purchased item.</span></span>

5. <span data-ttu-id="26a69-116">Affectez un groupe de calcul de nomenclature à l’article fabriqué.</span><span class="sxs-lookup"><span data-stu-id="26a69-116">Assign a bill of materials (BOM) calculation group to the manufactured item.</span></span> 

   <span data-ttu-id="26a69-117">Le groupe de calcul de nomenclature de l’article définit les conditions d’avertissement applicables.</span><span class="sxs-lookup"><span data-stu-id="26a69-117">The item's BOM calculation group defines warning conditions that apply.</span></span> <span data-ttu-id="26a69-118">Ainsi, lorsqu’un calcul de nomenclature est effectué, des messages d’avertissement peuvent être générés concernant les sources possibles des erreurs de calcul.</span><span class="sxs-lookup"><span data-stu-id="26a69-118">In that way, when a BOM calculation is done, warning messages can be generated about possible sources of calculation errors.</span></span> <span data-ttu-id="26a69-119">Par exemple, un message d’avertissement peut identifier si une nomenclature ou une gamme active n’existe pas.</span><span class="sxs-lookup"><span data-stu-id="26a69-119">For example, a warning message can identify when an active BOM or route doesn't exist.</span></span> <span data-ttu-id="26a69-120">Le groupe de calcul de nomenclature contient une stratégie d’arrêt d’éclatement qui indique quand un article fabriqué doit être traité comme un article acheté.</span><span class="sxs-lookup"><span data-stu-id="26a69-120">The BOM calculation group contains a stop explosion policy that indicates when a manufactured item should be treated as a purchased item.</span></span>

6. <span data-ttu-id="26a69-121">Si l’article fabriqué a des coûts constants, affectez-lui une quantité de commande standard.</span><span class="sxs-lookup"><span data-stu-id="26a69-121">If the manufactured item has constant costs, assign a standard order quantity to it.</span></span> 

   <span data-ttu-id="26a69-122">La quantité de commande standard fait office de taille de lot comptable pour l’amortissement des coûts constants.</span><span class="sxs-lookup"><span data-stu-id="26a69-122">The standard order quantity is an accounting lot size for amortizing constant costs.</span></span> <span data-ttu-id="26a69-123">Les coûts standard sont, par exemple, les temps de réglage des opérations de gamme et une quantité de composant constante dans la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="26a69-123">Examples of constant costs include setup times in routing operations and a constant component quantity in the BOM.</span></span>

7. <span data-ttu-id="26a69-124">Définissez la nomenclature pour l’article fabriqué.</span><span class="sxs-lookup"><span data-stu-id="26a69-124">Define the BOM for the manufactured item.</span></span> 

   <span data-ttu-id="26a69-125">Une ou plusieurs versions de nomenclature peuvent être définies pour l’article fabriqué.</span><span class="sxs-lookup"><span data-stu-id="26a69-125">One or more BOM versions can be defined for the manufactured item.</span></span> <span data-ttu-id="26a69-126">Vérifiez que les versions que vous souhaitez sont marquées comme approuvées et actives et qu’elles ont les dates effectives que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="26a69-126">Verify that the versions that you want have been marked as approved and active, and that they have the effective dates that you want.</span></span> <span data-ttu-id="26a69-127">La version de nomenclature peut s’appliquer à toute la société ou être spécifique aux sites.</span><span class="sxs-lookup"><span data-stu-id="26a69-127">The BOM version can be company-wide or site-specific.</span></span>

8. <span data-ttu-id="26a69-128">Définissez la gamme pour l’article fabriqué.</span><span class="sxs-lookup"><span data-stu-id="26a69-128">Define the routing for the manufactured item.</span></span> 

   <span data-ttu-id="26a69-129">Une ou plusieurs versions de gamme peuvent être définies pour l’article fabriqué.</span><span class="sxs-lookup"><span data-stu-id="26a69-129">One or more route versions can be defined for the manufactured item.</span></span> <span data-ttu-id="26a69-130">Vérifiez que les versions que vous souhaitez sont marquées comme approuvées et actives et qu’elles ont les dates effectives que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="26a69-130">Verify that the versions that you want have been marked as approved and active, and that they have the effective dates that you want.</span></span> <span data-ttu-id="26a69-131">La version de gamme doit être spécifique aux sites.</span><span class="sxs-lookup"><span data-stu-id="26a69-131">The route version must be site-specific.</span></span>

<span data-ttu-id="26a69-132">Si vous souhaitez utiliser les informations de gamme à des fins d’évaluation des coûts, des étapes de préparation supplémentaires sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="26a69-132">If you want to use routing information for costing purposes, additional preparation steps are required.</span></span> <span data-ttu-id="26a69-133">Par exemple, les catégories de coûts qui sont affectées aux opérations de gamme doivent être correctes et complétées.</span><span class="sxs-lookup"><span data-stu-id="26a69-133">For example, the cost categories that are assigned to routing operations must be correct and completed.</span></span>

## <a name="related-topics"></a><span data-ttu-id="26a69-134">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="26a69-134">Related topics</span></span>

[<span data-ttu-id="26a69-135">Amortissement des coûts constants pour un article fabriqué</span><span class="sxs-lookup"><span data-stu-id="26a69-135">Amortize constant costs for a manufactured item</span></span>](amortize-constant-costs-manufactured-item.md)

[<span data-ttu-id="26a69-136">Paramétrer les produits pouvant être produits ou approvisionnés</span><span class="sxs-lookup"><span data-stu-id="26a69-136">Set up products that can be produced or procured</span></span>](manufactured-items-treated-as-purchased-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]