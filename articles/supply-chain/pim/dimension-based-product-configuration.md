---
title: Vue d'ensemble de la configuration des produits basée sur les dimensions
description: la configuration de produit basée sur les dimensions représente une solution simple pour créer plusieurs variantes de produit à partir d'un produit générique unique et de sa nomenclature.
author: cvocph
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 45688f1882d2711cd43b9b7c199f1fca7ff089ea
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985531"
---
# <a name="dimension-based-product-configuration-overview"></a><span data-ttu-id="7aa73-103">Vue d'ensemble de la configuration des produits basée sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="7aa73-103">Dimension-based product configuration overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7aa73-104">la configuration de produit basée sur les dimensions représente une solution simple pour créer plusieurs variantes de produit à partir d'un produit générique unique et de sa nomenclature.</span><span class="sxs-lookup"><span data-stu-id="7aa73-104">Dimension-based product configuration represents a simple solution for creating many product variants from a single product master and its bill of materials.</span></span>

<span data-ttu-id="7aa73-105">La configuration de produit basée sur les dimensions est l'une des trois technologies intégrées de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="7aa73-105">Dimension-based product configuration is one of the three built-in product configuration technologies.</span></span> <span data-ttu-id="7aa73-106">Les deux autres technologies sont les variantes prédéfinies et la configuration basée sur les contraintes.</span><span class="sxs-lookup"><span data-stu-id="7aa73-106">The two other technologies are predefined variants and constraint-based configuration.</span></span> <span data-ttu-id="7aa73-107">Les trois technologies utilise un produit générique comme point de départ et permettent à l'utilisateur de créer plusieurs variantes de produit pour un produit générique.</span><span class="sxs-lookup"><span data-stu-id="7aa73-107">All three technologies use a product master as the starting point and allow the user to create many product variants for one product master.</span></span>

## <a name="key-concepts"></a><span data-ttu-id="7aa73-108">Concepts clés</span><span class="sxs-lookup"><span data-stu-id="7aa73-108">Key concepts</span></span>
<span data-ttu-id="7aa73-109">La configuration de produit basée sur les dimensions repose sur les concepts clés suivants :</span><span class="sxs-lookup"><span data-stu-id="7aa73-109">Dimension-based product configuration is based on the following key concepts:</span></span>

-   <span data-ttu-id="7aa73-110">Produits génériques</span><span class="sxs-lookup"><span data-stu-id="7aa73-110">Product masters</span></span>
-   <span data-ttu-id="7aa73-111">Dimension de produit de configuration</span><span class="sxs-lookup"><span data-stu-id="7aa73-111">Configuration product dimension</span></span>
-   <span data-ttu-id="7aa73-112">Groupes de configurations</span><span class="sxs-lookup"><span data-stu-id="7aa73-112">Configuration groups</span></span>
-   <span data-ttu-id="7aa73-113">Nomenclature</span><span class="sxs-lookup"><span data-stu-id="7aa73-113">Bill of materials (BOM)</span></span>
-   <span data-ttu-id="7aa73-114">Gamme de configuration</span><span class="sxs-lookup"><span data-stu-id="7aa73-114">Configuration route</span></span>
-   <span data-ttu-id="7aa73-115">Règles de configuration</span><span class="sxs-lookup"><span data-stu-id="7aa73-115">Configuration rules</span></span>

### <a name="product-masters"></a><span data-ttu-id="7aa73-116">Produits génériques</span><span class="sxs-lookup"><span data-stu-id="7aa73-116">Product masters</span></span>

<span data-ttu-id="7aa73-117">Un produit générique est le point de départ de tout processus de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="7aa73-117">A product master is the starting point for any product configuration process.</span></span> <span data-ttu-id="7aa73-118">Pour la configuration de produit basée sur les dimensions, vous avez besoin d'un produit générique avec cette technologie de configuration et un groupe de dimensions de produit qui inclut la dimension de produit de configuration.</span><span class="sxs-lookup"><span data-stu-id="7aa73-118">For the dimension-based product configuration, you need a product master with this particular configuration technology and a product dimension group that includes the configuration product dimension.</span></span>

### <a name="configuration-product-dimension"></a><span data-ttu-id="7aa73-119">Dimension de produit de configuration</span><span class="sxs-lookup"><span data-stu-id="7aa73-119">Configuration product dimension</span></span>

<span data-ttu-id="7aa73-120">La dimension de produit de configuration sert à identifier les variantes de produit d'un produit générique avec la technologie de configuration basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="7aa73-120">The configuration product dimension is used to identify the product variants for a product master with the dimension-based configuration technology.</span></span> <span data-ttu-id="7aa73-121">La valeur de la dimension de configuration est entrée par l'utilisateur et doit aider à identifier les différentes variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="7aa73-121">The configuration dimension value is entered by the user and should help to identify the individual product variants.</span></span>

### <a name="configuration-groups"></a><span data-ttu-id="7aa73-122">Groupes de configurations</span><span class="sxs-lookup"><span data-stu-id="7aa73-122">Configuration groups</span></span>

<span data-ttu-id="7aa73-123">Les groupes de configurations sont définis dans un référentiel central et peuvent être utilisés pour tous les modèles de configuration de produit basés sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="7aa73-123">Configuration groups are defined in a central repository and can be used for all dimension-based product configuration models.</span></span> <span data-ttu-id="7aa73-124">Les groupes de configurations sont associés aux lignes de nomenclature individuelles et lient un groupe de lignes qui s'excluent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="7aa73-124">Configuration groups are associated to the individual BOM lines and hold together a group of lines that are mutually exclusive.</span></span> <span data-ttu-id="7aa73-125">Cela signifie qu'une seule ligne par groupe peut être activée pour une seule variante de produit.</span><span class="sxs-lookup"><span data-stu-id="7aa73-125">This means that only one line in a group can be selected for a single product variant.</span></span>

### <a name="bill-of-materials-bom"></a><span data-ttu-id="7aa73-126">Nomenclature</span><span class="sxs-lookup"><span data-stu-id="7aa73-126">Bill of materials (BOM)</span></span>

<span data-ttu-id="7aa73-127">La nomenclature représentent les éléments constitutifs pour une configuration de produit basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="7aa73-127">The BOM represent the building blocks for a dimension-based product configuration.</span></span> <span data-ttu-id="7aa73-128">Elle doit inclure tous les différents produits qui peuvent être utilisés dans n'importe quelle variante de produit.</span><span class="sxs-lookup"><span data-stu-id="7aa73-128">It must include all the different products that can be used in any product variant.</span></span> <span data-ttu-id="7aa73-129">Chaque ligne de la nomenclature peut faire référence à un groupe de configurations.</span><span class="sxs-lookup"><span data-stu-id="7aa73-129">Each line in the BOM can reference a configuration group.</span></span> <span data-ttu-id="7aa73-130">Si une ligne ne fait pas référence à un groupe de configurations, elle est incluse dans toutes les variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="7aa73-130">If a line doesn’t reference a configuration group, it will be included in all product variants.</span></span>

### <a name="configuration-route"></a><span data-ttu-id="7aa73-131">Gamme de configuration</span><span class="sxs-lookup"><span data-stu-id="7aa73-131">Configuration route</span></span>

<span data-ttu-id="7aa73-132">La gamme de configuration détermine l'ordre des groupes de configurations, tels qu'ils seront affichés à l'utilisateur au cours du processus de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="7aa73-132">The configuration route determines the sequence of the configuration groups, as they will be displayed to the user during the product configuration process.</span></span>

### <a name="configuration-rules"></a><span data-ttu-id="7aa73-133">Règles de configuration</span><span class="sxs-lookup"><span data-stu-id="7aa73-133">Configuration rules</span></span>

<span data-ttu-id="7aa73-134">Les règles de configuration sont un mécanisme qui garantit qu'un produit inclus dans un groupe de configurations dans une nomenclature applique soit une inclusion soit une exclusion d'un produit dans un groupe de configurations différent dans la même nomenclature.</span><span class="sxs-lookup"><span data-stu-id="7aa73-134">The configuration rules represent a mechanism for ensuring that a product included in one configuration group in a BOM enforces either an inclusion or an exclusion of a product in a different configuration group in the same BOM.</span></span>

## <a name="product-modeling-process"></a><span data-ttu-id="7aa73-135">Processus de modélisation de produits</span><span class="sxs-lookup"><span data-stu-id="7aa73-135">Product modeling process</span></span>
<span data-ttu-id="7aa73-136">La séquence naturelle pour générer un modèle de produit basé sur les dimensions commence par définir les groupes de configurations pertinents.</span><span class="sxs-lookup"><span data-stu-id="7aa73-136">The natural sequence for building a product model for a dimension-based product starts with defining the relevant configuration groups.</span></span> <span data-ttu-id="7aa73-137">Il est important de vérifier que tous les produits qui seront utilisés dans la nomenclature ont été lancés vers la société pour laquelle le modèle de produit est établi.</span><span class="sxs-lookup"><span data-stu-id="7aa73-137">It is important to ensure that all products which will be used in the BOM have been released to the company that the product model is built for.</span></span> <span data-ttu-id="7aa73-138">Avec ces éléments constitutifs en place, l'utilisateur peut créer la nomenclature et affecter des groupes de configurations à toutes les lignes de nomenclature appropriées.</span><span class="sxs-lookup"><span data-stu-id="7aa73-138">With these building blocks in place, the user can create the BOM and assign configuration groups to all relevant BOM lines.</span></span> <span data-ttu-id="7aa73-139">Lorsque la nomenclature est terminée, une gamme de configuration peut être définie pour organiser les groupes de configurations dans l'ordre approprié.</span><span class="sxs-lookup"><span data-stu-id="7aa73-139">When the BOM is complete, a configuration route can be defined for ordering the configuration groups in the proper sequence.</span></span> <span data-ttu-id="7aa73-140">[![Processus de modélisation de produit basé sur les dimensions](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Si certains produits de différents groupes de configuration doivent être ou ne doivent pas être utilisés ensemble, vous pouvez créer des règles de configuration qui appliqueront ces relations de produit.</span><span class="sxs-lookup"><span data-stu-id="7aa73-140">[![Dimension-based product modeling process](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) If there are certain products from different configuration groups that either must or must not be used together, you can create configuration rules that will enforce these product relationships.</span></span> <span data-ttu-id="7aa73-141">Une fois la nomenclature liée avec un produit générique basé sur les dimensions par l'intermédiaire d'une version de nomenclature et que les deux ont été approuvés et activés, vous pouvez créer des configurations de produit et entrer un nom pour chaque configuration.</span><span class="sxs-lookup"><span data-stu-id="7aa73-141">After the BOM has been tied together with a dimension-based product master through a BOM version and both have been approved and activated, you can create product configurations and enter a name for each configuration.</span></span> <span data-ttu-id="7aa73-142">Les configurations peuvent être définies avant qu'une transaction quelconque soit générée, ou avant qu'une certaine configuration devienne nécessaire.</span><span class="sxs-lookup"><span data-stu-id="7aa73-142">The configurations can be defined before any transactions are generated or it can be done when the need for a certain configuration occurs.</span></span>

### <a name="suggested-use"></a><span data-ttu-id="7aa73-143">Suggestion d'utilisation</span><span class="sxs-lookup"><span data-stu-id="7aa73-143">Suggested use</span></span>

<span data-ttu-id="7aa73-144">La technologie de configuration basée sur les dimensions est optimale pour les produits à variabilité limitée et quand la combinaison des dimensions de produit standard (taille, couleur, style, et configuration) est inappropriée pour identifier une variante de produit spécifique.</span><span class="sxs-lookup"><span data-stu-id="7aa73-144">The dimension-based configuration technology is best used for products with limited variability and the combination of the standard product dimensions size, color, style, and configuration is unsuitable for identifying a specific product variant.</span></span> <span data-ttu-id="7aa73-145">Un exemple peut être une bicyclette avec une hauteur de cadre, une taille de roue, des types de frein, et différents dérailleurs.</span><span class="sxs-lookup"><span data-stu-id="7aa73-145">An example could be bicycle with frame height, wheel size, brake types, and different gears.</span></span>

### <a name="next-step"></a><span data-ttu-id="7aa73-146">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="7aa73-146">Next step</span></span> 

<span data-ttu-id="7aa73-147">Les huit guides de tâches suivants sont répertoriés dans l'ordre dans lequel vous devez les utiliser.</span><span class="sxs-lookup"><span data-stu-id="7aa73-147">The following eight task guides are listed in the order in which you should complete them.</span></span> 

1.  [<span data-ttu-id="7aa73-148">Créer un produit générique fondé sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="7aa73-148">Create a dimension-based product master</span></span>](tasks/create-dimension-based-product-master.md)
2.  [<span data-ttu-id="7aa73-149">Lancer un produit générique fondé sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="7aa73-149">Release a dimension-based product master</span></span>](tasks/release-dimension-based-product-master.md)
3.  [<span data-ttu-id="7aa73-150">Finaliser le paramétrage de base d’un produit générique lancé</span><span class="sxs-lookup"><span data-stu-id="7aa73-150">Complete basic setup of a released product master</span></span>](tasks/complete-basic-setup-released-product-master.md)
4.  [<span data-ttu-id="7aa73-151">Définir des groupes de configuration</span><span class="sxs-lookup"><span data-stu-id="7aa73-151">Define configuration groups</span></span>](tasks/define-configuration-groups.md)
5.  [<span data-ttu-id="7aa73-152">Créer une nomenclature pour un produit générique fondé sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="7aa73-152">Create a bill of materials for a dimension-based product master</span></span>](tasks/create-bill-materials-dimension-based-product-master.md)
6.  [<span data-ttu-id="7aa73-153">Définir des gammes de configuration</span><span class="sxs-lookup"><span data-stu-id="7aa73-153">Define configuration routes</span></span>](tasks/define-configuration-route.md)
7.  [<span data-ttu-id="7aa73-154">Créer des règles de configuration</span><span class="sxs-lookup"><span data-stu-id="7aa73-154">Create configuration rules</span></span>](tasks/create-configuration-rules.md)
8.  [<span data-ttu-id="7aa73-155">Créer des configurations basées sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="7aa73-155">Create dimension-based configurations</span></span>](tasks/create-dimension-based-configurations.md)

