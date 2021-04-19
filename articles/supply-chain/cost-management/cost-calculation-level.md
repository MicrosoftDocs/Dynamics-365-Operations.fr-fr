---
title: Niveau de calcul des coûts
description: Cette rubrique décrit le niveau de nomenclature nommé niveau de calcul des coûts. Ce niveau de nomenclature exclut les ordres de fabrication et les commandes par lots de ses calculs.
author: AndersGirke
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f7cde239107528a6bc2aeb0e424d024d4f3fb2a6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839485"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="32420-104">Niveau de calcul des coûts</span><span class="sxs-lookup"><span data-stu-id="32420-104">Cost calculation level</span></span>

<span data-ttu-id="32420-105">Le niveau de nomenclature nommé **Niveau de calcul des coûts** exclut les ordres de fabrication et les commandes par lots de ses calculs.</span><span class="sxs-lookup"><span data-stu-id="32420-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="32420-106">Le système utilise ce niveau lorsqu’il exécute des calculs de coût dans les versions d’évaluation des coûts.</span><span class="sxs-lookup"><span data-stu-id="32420-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="32420-107">Dans les processus tels que le recalcul et la clôture de stock, le système utilise le niveau de nomenclature **Niveau d’évaluation des coûts** à la place.</span><span class="sxs-lookup"><span data-stu-id="32420-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="32420-108">Le scénario simple suivant montre les différences entre le niveau de nomenclature **Niveau de calcul des coûts** et le niveau de nomenclature **Niveau d’évaluation des coûts**.</span><span class="sxs-lookup"><span data-stu-id="32420-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="32420-109">Vous avez trois produits : A, B et C. Le produit C est un composant du produit B et le produit B est un composant du produit A.</span><span class="sxs-lookup"><span data-stu-id="32420-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="32420-110">Le **Niveau d’évaluation des coûts** attribue les niveaux de nomenclature suivants :</span><span class="sxs-lookup"><span data-stu-id="32420-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="32420-111">**Produit A :** 0</span><span class="sxs-lookup"><span data-stu-id="32420-111">**Product A:** 0</span></span>
    - <span data-ttu-id="32420-112">**Produit B :** 1</span><span class="sxs-lookup"><span data-stu-id="32420-112">**Product B:** 1</span></span>
    - <span data-ttu-id="32420-113">**Produit C :** 2</span><span class="sxs-lookup"><span data-stu-id="32420-113">**Product C:** 2</span></span>

- <span data-ttu-id="32420-114">Le **Niveau de calcul des coûts** attribue les niveaux de nomenclature suivants :</span><span class="sxs-lookup"><span data-stu-id="32420-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="32420-115">**Produit A :** 0</span><span class="sxs-lookup"><span data-stu-id="32420-115">**Product A:** 0</span></span>
    - <span data-ttu-id="32420-116">**Produit B :** 1</span><span class="sxs-lookup"><span data-stu-id="32420-116">**Product B:** 1</span></span>
    - <span data-ttu-id="32420-117">**Produit C :** 2</span><span class="sxs-lookup"><span data-stu-id="32420-117">**Product C:** 2</span></span>

<span data-ttu-id="32420-118">Un ordre de fabrication pour le produit C est ensuite créé et le produit A est ajouté à la nomenclature de l’ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="32420-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="32420-119">Une fois la commande estimée, les niveaux de nomenclature sont mis à jour de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="32420-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="32420-120">Le **Niveau d’évaluation des coûts** attribue les niveaux de nomenclature suivants :</span><span class="sxs-lookup"><span data-stu-id="32420-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="32420-121">**Produit B :** 1</span><span class="sxs-lookup"><span data-stu-id="32420-121">**Product B:** 1</span></span>
    - <span data-ttu-id="32420-122">**Produit C :** 2</span><span class="sxs-lookup"><span data-stu-id="32420-122">**Product C:** 2</span></span>
    - <span data-ttu-id="32420-123">**Produit A :** 3</span><span class="sxs-lookup"><span data-stu-id="32420-123">**Product A:** 3</span></span>

- <span data-ttu-id="32420-124">Le **Niveau de calcul des coûts** attribue les niveaux de nomenclature suivants :</span><span class="sxs-lookup"><span data-stu-id="32420-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="32420-125">**Produit A :** 0</span><span class="sxs-lookup"><span data-stu-id="32420-125">**Product A:** 0</span></span>
    - <span data-ttu-id="32420-126">**Produit B :** 1</span><span class="sxs-lookup"><span data-stu-id="32420-126">**Product B:** 1</span></span>
    - <span data-ttu-id="32420-127">**Produit C :** 2</span><span class="sxs-lookup"><span data-stu-id="32420-127">**Product C:** 2</span></span>

<span data-ttu-id="32420-128">Ce comportement garantit que les modifications apportées aux nomenclatures des ordres de fabrication n’affectent pas les calculs de coûts ultérieurs.</span><span class="sxs-lookup"><span data-stu-id="32420-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]