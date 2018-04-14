---
title: Inventaire tournant de l'emplacement partiel
description: "Les plans d'inventaire tournant guident les opérations tournantes réelles. Vous pouvez demander que seuls des produits et des variantes de produit spécifiques soient comptabilisés au lieu de tout le stock disponible à un emplacement."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 0e72df11e8fc4a43d74a6fe596a223266ddf5b09
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="partial-location-cycle-counting"></a><span data-ttu-id="6ec59-104">Inventaire tournant de l'emplacement partiel</span><span class="sxs-lookup"><span data-stu-id="6ec59-104">Partial location cycle counting</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="6ec59-105">Les plans d'inventaire tournant guident les opérations tournantes réelles.</span><span class="sxs-lookup"><span data-stu-id="6ec59-105">Cycle count plans guide the actual counting operations.</span></span> <span data-ttu-id="6ec59-106">Vous pouvez demander que seuls des produits et des variantes de produit spécifiques soient comptabilisés au lieu de tout le stock disponible à un emplacement.</span><span class="sxs-lookup"><span data-stu-id="6ec59-106">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span>

<span data-ttu-id="6ec59-107">En utilisant des plans d'inventaire tournant pour créer un travail d'inventaire, vous pouvez guider les opérations d'inventaire réelles.</span><span class="sxs-lookup"><span data-stu-id="6ec59-107">By using cycle count plans to create counting work, you can guide the actual counting operations.</span></span> <span data-ttu-id="6ec59-108">Vous pouvez demander que seuls des produits et des variantes de produit spécifiques soient comptabilisés au lieu de tout le stock disponible à un emplacement.</span><span class="sxs-lookup"><span data-stu-id="6ec59-108">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span> <span data-ttu-id="6ec59-109">Lorsque vous appliquez un filtre sur les produits spécifiques, le gestionnaire d'entrepôt peut réduire les frais généraux de révision, éviter toute erreur de consolidation et gagner du temps.</span><span class="sxs-lookup"><span data-stu-id="6ec59-109">By filtering on specific products, the warehouse manager can reduce review overhead, avoid consolidation mistakes, and save time.</span></span>

## <a name="how-to-configure-partial-location-cycle-counting"></a><span data-ttu-id="6ec59-110">Procédure de configuration d'un inventaire tournant partiel</span><span class="sxs-lookup"><span data-stu-id="6ec59-110">How to configure partial location cycle counting</span></span>
<span data-ttu-id="6ec59-111">Lorsque vous utilisez le processus de travail de l'entrepôt pour les opérations d'inventaire, l'en-tête de travail est créé pour chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="6ec59-111">When you use the warehouse work process for counting operations, a work header is created for each location.</span></span> <span data-ttu-id="6ec59-112">Lorsque vous définissez le plan d'inventaire tournant, vous pouvez utiliser la requête **Sélectionner des emplacements** pour limiter le travail d'inventaire qui est créé.</span><span class="sxs-lookup"><span data-stu-id="6ec59-112">When you define the cycle count plan, you can use the **Select locations** query to limit the cycle counting work that is created.</span></span> <span data-ttu-id="6ec59-113">Lorsque vous sélectionnez des produits pour le plan d'inventaire tournant, vous pouvez sélectionner des requêtes de produits et de variantes de produit pour affiner l'inventaire.</span><span class="sxs-lookup"><span data-stu-id="6ec59-113">When you select products for the cycle count plan, you can select both product and product variant queries to refine what is counted.</span></span> 

<span data-ttu-id="6ec59-114">Vous pouvez associer un **modèle de travail** à un plan d'inventaire tournant afin de définir la manière dont le travail d'inventaire tournant doit être créé.</span><span class="sxs-lookup"><span data-stu-id="6ec59-114">You can associate a **work template** with a cycle count plan to define how the cycle count work should be created.</span></span> <span data-ttu-id="6ec59-115">Le modèle de travail pour les opérations d'inventaire est directement référencé à partir du plan d'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="6ec59-115">The work template for counting operations is directly referenced from the cycle count plan.</span></span> 

<span data-ttu-id="6ec59-116">Lorsque vous définissez les détails du modèle de travail, vous pouvez utiliser l'option **Pauses de ligne de travail** pour spécifier si les lignes de comptage traitées doivent être regroupées par numéro d'article ou de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="6ec59-116">When you define the work template details, you can use the **Work line breaks** option to specify whether the counting work lines must be grouped by item number or product variant number.</span></span> <span data-ttu-id="6ec59-117">Ce paramétrage est nécessaire si vous voulez compter le stock disponible uniquement pour les produits spécifiques d'un emplacement.</span><span class="sxs-lookup"><span data-stu-id="6ec59-117">This setup is required if you want to count on-hand inventory only for specific products in a location.</span></span> <span data-ttu-id="6ec59-118">Les lignes de travail d'inventaire tournant qui sont créées disposeront du niveau d'information que vous définissez ici, et l'opération de comptage guidée sera gérée en fonction de ce niveau.</span><span class="sxs-lookup"><span data-stu-id="6ec59-118">The cycle counting work lines that are created will have the level of information that you define here, and the guided counting operation will be handled based on this level.</span></span> 

<span data-ttu-id="6ec59-119">Si vous associez des plans de comptage d'inventaire tournant à des modèles de travail à l'aide de l'option **Pauses de ligne de travail**, le champ **Inventaire tournant partiel** est sélectionné pour le travail d'inventaire tournant créé, et plusieurs lignes de travail d'inventaire tournant sont créées en fonction de la définition du modèle de travail.</span><span class="sxs-lookup"><span data-stu-id="6ec59-119">If you associate cycle count plans with work templates by using the **Work lines breaks** option, the **Partial cycle count** field is selected for the cycle counting work that is created, and multiple cycle counting work lines will be created based on the definition of the work template.</span></span> 

<span data-ttu-id="6ec59-120">Avant que le travail d'inventaire tournant partiel puisse être traité, vous devez, au moins, sélectionner **Afficher le numéro d'article** pour l'option de menu de l'appareil mobile dans le cadre du paramétrage de l'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="6ec59-120">Before partial cycle count work can be processed, you must, at a minimum, select **Display item number** for the mobile device menu item as part of the cycle counting setup.</span></span> <span data-ttu-id="6ec59-121">L'opérateur d'entrepôt est invité à enregistrer uniquement les informations d'inventaire liées aux lignes de comptage (numéros d'article et dimensions de produit).</span><span class="sxs-lookup"><span data-stu-id="6ec59-121">The warehouse operator will be asked to record only counting information that is related to the counting lines (item numbers and product dimensions).</span></span> <span data-ttu-id="6ec59-122">Tout autre stock disponible est ignoré pour ce processus de comptage.</span><span class="sxs-lookup"><span data-stu-id="6ec59-122">All other on-hand inventory will be ignored for this counting process.</span></span> 

<span data-ttu-id="6ec59-123">Pour le processus d'inventaire tournant partiel, la date et l'heure du **dernier inventaire tournant** ne sont pas mises à jour pour l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="6ec59-123">For the partial cycle count process, the **Last cycle count** date/time won’t be updated for the location.</span></span>

## <a name="example"></a><span data-ttu-id="6ec59-124">Exemple</span><span class="sxs-lookup"><span data-stu-id="6ec59-124">Example</span></span>
<span data-ttu-id="6ec59-125">Pour cet exemple, seul le numéro d'article A0001 doit être compté dans l'entrepôt 61.</span><span class="sxs-lookup"><span data-stu-id="6ec59-125">For this example, only item number A0001 must be counted in warehouse 61.</span></span>

1.  <span data-ttu-id="6ec59-126">Un modèle de travail pour l'inventaire tournant est créé.</span><span class="sxs-lookup"><span data-stu-id="6ec59-126">A new work template for cycle counting is created.</span></span> <span data-ttu-id="6ec59-127">L'option **Pauses de ligne de travail** permet de regrouper des lignes de comptage traitées par numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="6ec59-127">The **Work line breaks** option is used to group counting work lines by item number.</span></span> <span data-ttu-id="6ec59-128">Par conséquent, le travail d'inventaire tournant créé aura des lignes par numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="6ec59-128">Therefore, the cycle counting work that is created will have lines per item number.</span></span> <span data-ttu-id="6ec59-129">Vous pouvez aussi regrouper les lignes par numéro de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="6ec59-129">You can also group the lines by product variant number.</span></span>
2.  <span data-ttu-id="6ec59-130">Un nouveau plan d'inventaire tournant est créé qui référence le nouveau modèle de travail créé.</span><span class="sxs-lookup"><span data-stu-id="6ec59-130">A new cycle counting plan is created that references the newly created work template.</span></span> <span data-ttu-id="6ec59-131">Le plan d'inventaire tournant inclut tous les emplacements de l'entrepôt 61 (requête **Sélectionner des emplacements**) renfermant le numéro d'article A0001.</span><span class="sxs-lookup"><span data-stu-id="6ec59-131">The cycle counting plan includes all locations in warehouse 61 (**Select locations** query) that hold inventory for item number A0001.</span></span> <span data-ttu-id="6ec59-132">La sélection de produits spécifiques est définie dans la section **Sélections de produits du plan d'inventaire tournant**.</span><span class="sxs-lookup"><span data-stu-id="6ec59-132">The selection of specific products is defined in the **Cycle count product selections** section.</span></span>
3.  <span data-ttu-id="6ec59-133">Vous pouvez sélectionner des produits pour les plans d'inventaire tournant en définissant le champ **Emplacements vides** sur **Vides exclus**.</span><span class="sxs-lookup"><span data-stu-id="6ec59-133">You can select products for cycle counting plans by setting the **Empty locations** field to **Exclude empty**.</span></span> <span data-ttu-id="6ec59-134">Une fois le plan d'inventaire tournant traité, le travail d'inventaire tournant partiel du numéro d'article A0001 est créé.</span><span class="sxs-lookup"><span data-stu-id="6ec59-134">When the cycle counting plan is processed, partial cycle count work for item number A0001 is created.</span></span> <span data-ttu-id="6ec59-135">Le processus de comptage réel peut être exécuté à l'aide d'une option de menu du périphérique mobile pour l'inventaire tournant guidé.</span><span class="sxs-lookup"><span data-stu-id="6ec59-135">The actual counting process can be performed by using a mobile device menu item for guided cycle counting.</span></span>



<a name="see-also"></a><span data-ttu-id="6ec59-136">Voir également :</span><span class="sxs-lookup"><span data-stu-id="6ec59-136">See also</span></span>
--------

[<span data-ttu-id="6ec59-137">Inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="6ec59-137">Cycle counting</span></span>](cycle-counting.md)


