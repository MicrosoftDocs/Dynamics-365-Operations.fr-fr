---
title: Niveau de calcul des coûts
description: Cette rubrique décrit le niveau de nomenclature nommé niveau de calcul des coûts. Ce niveau de nomenclature exclut les ordres de fabrication et les commandes par lots de ses calculs.
author: AndersGirke
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 1cfbbb6aadbd24a0352776285f6c60ff10f59549
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251024"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="403b8-104">Niveau de calcul des coûts</span><span class="sxs-lookup"><span data-stu-id="403b8-104">Cost calculation level</span></span>

<span data-ttu-id="403b8-105">Le niveau de nomenclature nommé **Niveau de calcul des coûts** exclut les ordres de fabrication et les commandes par lots de ses calculs.</span><span class="sxs-lookup"><span data-stu-id="403b8-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="403b8-106">Le système utilise ce niveau lorsqu’il exécute des calculs de coût dans les versions d’évaluation des coûts.</span><span class="sxs-lookup"><span data-stu-id="403b8-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="403b8-107">Dans les processus tels que le recalcul et la clôture de stock, le système utilise le niveau de nomenclature **Niveau d’évaluation des coûts** à la place.</span><span class="sxs-lookup"><span data-stu-id="403b8-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="403b8-108">Le scénario simple suivant montre les différences entre le niveau de nomenclature **Niveau de calcul des coûts** et le niveau de nomenclature **Niveau d’évaluation des coûts**.</span><span class="sxs-lookup"><span data-stu-id="403b8-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="403b8-109">Vous avez trois produits : A, B et C. Le produit C est un composant du produit B et le produit B est un composant du produit A.</span><span class="sxs-lookup"><span data-stu-id="403b8-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="403b8-110">Le **Niveau d’évaluation des coûts** attribue les niveaux de nomenclature suivants :</span><span class="sxs-lookup"><span data-stu-id="403b8-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="403b8-111">**Produit A :** 0</span><span class="sxs-lookup"><span data-stu-id="403b8-111">**Product A:** 0</span></span>
    - <span data-ttu-id="403b8-112">**Produit B :** 1</span><span class="sxs-lookup"><span data-stu-id="403b8-112">**Product B:** 1</span></span>
    - <span data-ttu-id="403b8-113">**Produit C :** 2</span><span class="sxs-lookup"><span data-stu-id="403b8-113">**Product C:** 2</span></span>

- <span data-ttu-id="403b8-114">Le **Niveau de calcul des coûts** attribue les niveaux de nomenclature suivants :</span><span class="sxs-lookup"><span data-stu-id="403b8-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="403b8-115">**Produit A :** 0</span><span class="sxs-lookup"><span data-stu-id="403b8-115">**Product A:** 0</span></span>
    - <span data-ttu-id="403b8-116">**Produit B :** 1</span><span class="sxs-lookup"><span data-stu-id="403b8-116">**Product B:** 1</span></span>
    - <span data-ttu-id="403b8-117">**Produit C :** 2</span><span class="sxs-lookup"><span data-stu-id="403b8-117">**Product C:** 2</span></span>

<span data-ttu-id="403b8-118">Un ordre de fabrication pour le produit C est ensuite créé et le produit A est ajouté à la nomenclature de l’ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="403b8-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="403b8-119">Une fois la commande estimée, les niveaux de nomenclature sont mis à jour de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="403b8-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="403b8-120">Le **Niveau d’évaluation des coûts** attribue les niveaux de nomenclature suivants :</span><span class="sxs-lookup"><span data-stu-id="403b8-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="403b8-121">**Produit B :** 1</span><span class="sxs-lookup"><span data-stu-id="403b8-121">**Product B:** 1</span></span>
    - <span data-ttu-id="403b8-122">**Produit C :** 2</span><span class="sxs-lookup"><span data-stu-id="403b8-122">**Product C:** 2</span></span>
    - <span data-ttu-id="403b8-123">**Produit A :** 3</span><span class="sxs-lookup"><span data-stu-id="403b8-123">**Product A:** 3</span></span>

- <span data-ttu-id="403b8-124">Le **Niveau de calcul des coûts** attribue les niveaux de nomenclature suivants :</span><span class="sxs-lookup"><span data-stu-id="403b8-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="403b8-125">**Produit A :** 0</span><span class="sxs-lookup"><span data-stu-id="403b8-125">**Product A:** 0</span></span>
    - <span data-ttu-id="403b8-126">**Produit B :** 1</span><span class="sxs-lookup"><span data-stu-id="403b8-126">**Product B:** 1</span></span>
    - <span data-ttu-id="403b8-127">**Produit C :** 2</span><span class="sxs-lookup"><span data-stu-id="403b8-127">**Product C:** 2</span></span>

<span data-ttu-id="403b8-128">Ce comportement garantit que les modifications apportées aux nomenclatures des ordres de fabrication n’affectent pas les calculs de coûts ultérieurs.</span><span class="sxs-lookup"><span data-stu-id="403b8-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]