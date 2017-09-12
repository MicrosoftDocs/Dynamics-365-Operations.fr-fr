---
title: "Configuration de produit basée dur les dimensions"
description: "la configuration de produit basée sur les dimensions représente une solution simple pour créer plusieurs variantes de produit à partir d'un produit générique unique et de sa nomenclature."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 89f01401f1d937a72ae7e59b784cf034b48aaf1f
ms.contentlocale: fr-fr
ms.lasthandoff: 07/18/2017

---

# <a name="dimension-based-product-configuration"></a><span data-ttu-id="c5542-103">Configuration de produit basée dur les dimensions</span><span class="sxs-lookup"><span data-stu-id="c5542-103">Dimension-based product configuration</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c5542-104">la configuration de produit basée sur les dimensions représente une solution simple pour créer plusieurs variantes de produit à partir d'un produit générique unique et de sa nomenclature.</span><span class="sxs-lookup"><span data-stu-id="c5542-104">Dimension-based product configuration represents a simple solution for creating many product variants from a single product master and its bill of materials.</span></span>

<span data-ttu-id="c5542-105">La configuration de produit basée sur les dimensions est l'une des trois technologies intégrées de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="c5542-105">Dimension-based product configuration is one of the three built-in product configuration technologies.</span></span> <span data-ttu-id="c5542-106">Les deux autres technologies sont les variantes prédéfinies et la configuration basée sur les contraintes.</span><span class="sxs-lookup"><span data-stu-id="c5542-106">The two other technologies are predefined variants and constraint-based configuration.</span></span> <span data-ttu-id="c5542-107">Les trois technologies utilise un produit générique comme point de départ et permettent à l'utilisateur de créer plusieurs variantes de produit pour un produit générique.</span><span class="sxs-lookup"><span data-stu-id="c5542-107">All three technologies use a product master as the starting point and allow the user to create many product variants for one product master.</span></span>

## <a name="key-concepts"></a><span data-ttu-id="c5542-108">Concepts clés</span><span class="sxs-lookup"><span data-stu-id="c5542-108">Key concepts</span></span>
<span data-ttu-id="c5542-109">La configuration de produit basée sur les dimensions repose sur les concepts clés suivants :</span><span class="sxs-lookup"><span data-stu-id="c5542-109">Dimension-based product configuration is based on the following key concepts:</span></span>

-   <span data-ttu-id="c5542-110">Produits génériques</span><span class="sxs-lookup"><span data-stu-id="c5542-110">Product masters</span></span>
-   <span data-ttu-id="c5542-111">Dimension de produit de configuration</span><span class="sxs-lookup"><span data-stu-id="c5542-111">Configuration product dimension</span></span>
-   <span data-ttu-id="c5542-112">Groupes de configurations</span><span class="sxs-lookup"><span data-stu-id="c5542-112">Configuration groups</span></span>
-   <span data-ttu-id="c5542-113">Nomenclature</span><span class="sxs-lookup"><span data-stu-id="c5542-113">Bill of materials (BOM)</span></span>
-   <span data-ttu-id="c5542-114">Gamme de configuration</span><span class="sxs-lookup"><span data-stu-id="c5542-114">Configuration route</span></span>
-   <span data-ttu-id="c5542-115">Règles de configuration</span><span class="sxs-lookup"><span data-stu-id="c5542-115">Configuration rules</span></span>

### <a name="product-masters"></a><span data-ttu-id="c5542-116">Produits génériques</span><span class="sxs-lookup"><span data-stu-id="c5542-116">Product masters</span></span>

<span data-ttu-id="c5542-117">Un produit générique est le point de départ de tout processus de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="c5542-117">A product master is the starting point for any product configuration process.</span></span> <span data-ttu-id="c5542-118">Pour la configuration de produit basée sur les dimensions, vous avez besoin d'un produit générique avec cette technologie de configuration et un groupe de dimensions de produit qui inclut la dimension de produit de configuration.</span><span class="sxs-lookup"><span data-stu-id="c5542-118">For the dimension-based product configuration, you need a product master with this particular configuration technology and a product dimension group that includes the configuration product dimension.</span></span>

### <a name="configuration-product-dimension"></a><span data-ttu-id="c5542-119">Dimension de produit de configuration</span><span class="sxs-lookup"><span data-stu-id="c5542-119">Configuration product dimension</span></span>

<span data-ttu-id="c5542-120">La dimension de produit de configuration sert à identifier les variantes de produit d'un produit générique avec la technologie de configuration basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="c5542-120">The configuration product dimension is used to identify the product variants for a product master with the dimension-based configuration technology.</span></span> <span data-ttu-id="c5542-121">La valeur de la dimension de configuration est entrée par l'utilisateur et doit aider à identifier les différentes variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="c5542-121">The configuration dimension value is entered by the user and should help to identify the individual product variants.</span></span>

### <a name="configuration-groups"></a><span data-ttu-id="c5542-122">Groupes de configurations</span><span class="sxs-lookup"><span data-stu-id="c5542-122">Configuration groups</span></span>

<span data-ttu-id="c5542-123">Les groupes de configurations sont définis dans un référentiel central et peuvent être utilisés pour tous les modèles de configuration de produit basés sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="c5542-123">Configuration groups are defined in a central repository and can be used for all dimension-based product configuration models.</span></span> <span data-ttu-id="c5542-124">Les groupes de configurations sont associés aux lignes de nomenclature individuelles et lient un groupe de lignes qui s'excluent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="c5542-124">Configuration groups are associated to the individual BOM lines and hold together a group of lines that are mutually exclusive.</span></span> <span data-ttu-id="c5542-125">Cela signifie qu'une seule ligne par groupe peut être activée pour une seule variante de produit.</span><span class="sxs-lookup"><span data-stu-id="c5542-125">This means that only one line in a group can be selected for a single product variant.</span></span>

### <a name="bill-of-materials-bom"></a><span data-ttu-id="c5542-126">Nomenclature</span><span class="sxs-lookup"><span data-stu-id="c5542-126">Bill of materials (BOM)</span></span>

<span data-ttu-id="c5542-127">La nomenclature représentent les éléments constitutifs pour une configuration de produit basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="c5542-127">The BOM represent the building blocks for a dimension-based product configuration.</span></span> <span data-ttu-id="c5542-128">Elle doit inclure tous les différents produits qui peuvent être utilisés dans n'importe quelle variante de produit.</span><span class="sxs-lookup"><span data-stu-id="c5542-128">It must include all the different products that can be used in any product variant.</span></span> <span data-ttu-id="c5542-129">Chaque ligne de la nomenclature peut faire référence à un groupe de configurations.</span><span class="sxs-lookup"><span data-stu-id="c5542-129">Each line in the BOM can reference a configuration group.</span></span> <span data-ttu-id="c5542-130">Si une ligne ne fait pas référence à un groupe de configurations, elle est incluse dans toutes les variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="c5542-130">If a line doesn’t reference a configuration group, it will be included in all product variants.</span></span>

### <a name="configuration-route"></a><span data-ttu-id="c5542-131">Gamme de configuration</span><span class="sxs-lookup"><span data-stu-id="c5542-131">Configuration route</span></span>

<span data-ttu-id="c5542-132">La gamme de configuration détermine l'ordre des groupes de configurations, tels qu'ils seront affichés à l'utilisateur au cours du processus de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="c5542-132">The configuration route determines the sequence of the configuration groups, as they will be displayed to the user during the product configuration process.</span></span>

### <a name="configuration-rules"></a><span data-ttu-id="c5542-133">Règles de configuration</span><span class="sxs-lookup"><span data-stu-id="c5542-133">Configuration rules</span></span>

<span data-ttu-id="c5542-134">Les règles de configuration sont un mécanisme qui garantit qu'un produit inclus dans un groupe de configurations dans une nomenclature applique soit une inclusion soit une exclusion d'un produit dans un groupe de configurations différent dans la même nomenclature.</span><span class="sxs-lookup"><span data-stu-id="c5542-134">The configuration rules represent a mechanism for ensuring that a product included in one configuration group in a BOM enforces either an inclusion or an exclusion of a product in a different configuration group in the same BOM.</span></span>

## <a name="product-modeling-process"></a><span data-ttu-id="c5542-135">Processus de modélisation de produits</span><span class="sxs-lookup"><span data-stu-id="c5542-135">Product modeling process</span></span>
<span data-ttu-id="c5542-136">La séquence naturelle pour générer un modèle de produit basé sur les dimensions commence par définir les groupes de configurations pertinents.</span><span class="sxs-lookup"><span data-stu-id="c5542-136">The natural sequence for building a product model for a dimension-based product starts with defining the relevant configuration groups.</span></span> <span data-ttu-id="c5542-137">Il est important de vérifier que tous les produits qui seront utilisés dans la nomenclature ont été lancés vers la société pour laquelle le modèle de produit est établi.</span><span class="sxs-lookup"><span data-stu-id="c5542-137">It is important to ensure that all products which will be used in the BOM have been relased to the company that the product model is built for.</span></span> <span data-ttu-id="c5542-138">Avec ces éléments constitutifs en place, l'utilisateur peut créer la nomenclature et affecter des groupes de configurations à toutes les lignes de nomenclature appropriées.</span><span class="sxs-lookup"><span data-stu-id="c5542-138">With these building blocks in place, the user can create the BOM and assign configuration groups to all relevant BOM lines.</span></span> <span data-ttu-id="c5542-139">Lorsque la nomenclature est terminée, une gamme de configuration peut être définie pour organiser les groupes de configurations dans l'ordre approprié.</span><span class="sxs-lookup"><span data-stu-id="c5542-139">When the BOM is complete, a configuration route can be defined for ordering the configuration groups in the proper sequence.</span></span> <span data-ttu-id="c5542-140">\[caption id="attachment\_282671" align="alignnone" width="1187"\][![Processus de modélisation de produit basé sur les dimensions](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Processus de modélisation de produit basé sur les dimensions\[/caption\] Si certains produits issus de différents groupes de configuration doivent être utilisés ensemble ou pas, vous pouvez créer des règles de configuration qui feront appliquer ces relations entre les produits.</span><span class="sxs-lookup"><span data-stu-id="c5542-140">\[caption id="attachment\_282671" align="alignnone" width="1187"\][![Dimension-based product modeling process](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Dimension-based product modeling process\[/caption\] If there are certain products from different configuration groups that either must or must not be used together, you can create configuration rules that will enforce these product relationships.</span></span> <span data-ttu-id="c5542-141">Une fois la nomenclature liée avec un produit générique basé sur les dimensions par l'intermédiaire d'une version de nomenclature et que les deux ont été approuvés et activés, vous pouvez créer des configurations de produit et entrer un nom pour chaque configuration.</span><span class="sxs-lookup"><span data-stu-id="c5542-141">After the BOM has been tied together with a dimension-based product master through a BOM version and both have been approved and activated, you can create product configurations and enter a name for each configuration.</span></span> <span data-ttu-id="c5542-142">Les configurations peuvent être définies avant qu'une transaction quelconque soit générée, ou avant qu'une certaine configuration devienne nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c5542-142">The configurations can be defined before any transactions are generated or it can be done when the need for a certain configuration occurs.</span></span>

### <a name="suggested-use"></a><span data-ttu-id="c5542-143">Suggestion d'utilisation</span><span class="sxs-lookup"><span data-stu-id="c5542-143">Suggested use</span></span>

<span data-ttu-id="c5542-144">La technologie de configuration basée sur les dimensions est optimale pour les produits à variabilité limitée et quand la combinaison des dimensions de produit standard (taille, couleur, style, et configuration) est inappropriée pour identifier une variante de produit spécifique.</span><span class="sxs-lookup"><span data-stu-id="c5542-144">The dimension-based configuration technology is best used for products with limited variability and the combination of the standard product dimensions size, color, style, and configuration is unsuitable for identifying a specific product variant.</span></span> <span data-ttu-id="c5542-145">Un exemple peut être une bicyclette avec une hauteur de cadre, une taille de roue, des types de frein, et différents dérailleurs.</span><span class="sxs-lookup"><span data-stu-id="c5542-145">An example could be bicycle with frame height, wheel size, brake types, and different gears.</span></span>




