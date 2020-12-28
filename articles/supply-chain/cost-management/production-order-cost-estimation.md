---
title: Estimation de coût de l'ordre de fabrication
description: Cet article fournit des informations sur l'estimation du coût de production. L'estimation du coût de production fournit les coûts de consommation de matière et de capacité projetés liés à la production d'un article dans la quantité de l'ordre de fabrication planifiée.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a101f82e60113941d389421b19cddc1ad123ce9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427973"
---
# <a name="production-order-cost-estimation"></a><span data-ttu-id="0cfe6-104">Estimation de coût de l'ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="0cfe6-104">Production order cost estimation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0cfe6-105">Cet article fournit des informations sur l'estimation du coût de production.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-105">This article provides information about production cost estimation.</span></span> <span data-ttu-id="0cfe6-106">L'estimation du coût de production fournit les coûts de consommation de matière et de capacité projetés liés à la production d'un article dans la quantité de l'ordre de fabrication planifiée.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-106">Production cost estimation provides the projected material and capacity consumption costs of producing an item in the planned production order quantity.</span></span> 

<span data-ttu-id="0cfe6-107">Après avoir créé un ordre de fabrication, vous devez estimer les coûts de production.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-107">After you create a production order, you must estimate production costs.</span></span> <span data-ttu-id="0cfe6-108">L'objectif consiste à évaluer la consommation d'article et de gamme pour le processus de production parce que ces estimations sont utilisées en guise de base des processus de planification et de fabrication suivants.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-108">The purpose is to estimate item and route consumption for the production process, because these estimates are used as the basis for subsequent scheduling and production processes.</span></span>

## <a name="production-cost-estimation"></a><span data-ttu-id="0cfe6-109">Estimation de coût de production</span><span class="sxs-lookup"><span data-stu-id="0cfe6-109">Production cost estimation</span></span>
<span data-ttu-id="0cfe6-110">Les estimations des coûts de production sont basées sur les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0cfe6-110">Estimates of production costs are based on the following information:</span></span>

-   <span data-ttu-id="0cfe6-111">La quantité figurant sur l'ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="0cfe6-111">The quantity on the production order</span></span>
-   <span data-ttu-id="0cfe6-112">Les composants figurant sur les nomenclatures de production</span><span class="sxs-lookup"><span data-stu-id="0cfe6-112">The components on the production bills of materials (BOMs)</span></span>
-   <span data-ttu-id="0cfe6-113">Les opérations d'acheminement de la gamme de production</span><span class="sxs-lookup"><span data-stu-id="0cfe6-113">The routing operations in the production route</span></span>
-   <span data-ttu-id="0cfe6-114">Les coûts indirects qui s'appliquent aux composants et aux opérations</span><span class="sxs-lookup"><span data-stu-id="0cfe6-114">The indirect costs that apply to the components and operations</span></span>
-   <span data-ttu-id="0cfe6-115">Les données actives de coûts à la date du calcul</span><span class="sxs-lookup"><span data-stu-id="0cfe6-115">The active cost data as of the calculation date</span></span>

<span data-ttu-id="0cfe6-116">S'il y a une ligne fantôme dans les nomenclatures de production, les calculs reflètent les composants et les opérations de gamme du fantôme.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-116">If there is a phantom line item on the production BOMs, the calculations reflect the phantom’s components and route operations.</span></span> <span data-ttu-id="0cfe6-117">Vous pouvez utiliser la tâche d'estimation pour recalculer les coûts estimés afin qu'ils reflètent les informations mises à jour.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-117">You can use the estimation task to recalculate estimated costs so that they reflect updated information.</span></span> <span data-ttu-id="0cfe6-118">Par exemple, les informations mises à jour peuvent être des modifications de la quantité de l'ordre de fabrication, les composants des nomenclatures de production, les opérations de gamme dans la gamme de production, les coûts indirects qui s'appliquent à ces composants et opérations ou les données actives de coûts telles que la date de recalcul.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-118">For example, the updated information might be changes to the quantity on the production order, the components on the production BOMs, the routing operations in the production route, the indirect costs that apply to these components and operations, or the active cost data as of the recalculation date.</span></span> <span data-ttu-id="0cfe6-119">Les calculs des coûts estimés suggèrent également un prix de vente pour l'article de production basé sur une approche coût plus marge sur coûts d'achat.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-119">The calculations of estimated cost also suggest a sales price for the production item, based on a cost-plus-markup approach.</span></span> <span data-ttu-id="0cfe6-120">Les calculs des coûts estimés peuvent éventuellement s'appliquer aux documents de référence qui reflètent les autres ordres de fabrication associés à l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-120">The calculations of estimated cost can optionally apply to reference orders that reflect other production orders that are linked to the production order.</span></span>

## <a name="view-the-estimated-costs"></a><span data-ttu-id="0cfe6-121">Afficher les coûts estimés</span><span class="sxs-lookup"><span data-stu-id="0cfe6-121">View the estimated costs</span></span>
<span data-ttu-id="0cfe6-122">Après avoir exécuté l'estimation, vous pouvez afficher les résultats sur la page **Calcul du prix**.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-122">After you run estimation, you can view the results on the **Price calculation** page.</span></span> <span data-ttu-id="0cfe6-123">L'estimation calcule les valeur suivantes :</span><span class="sxs-lookup"><span data-stu-id="0cfe6-123">The estimation calculates the following values:</span></span>

-   <span data-ttu-id="0cfe6-124">**Coût de production** : le coût de production correspond à la ligne supérieure de l'estimation.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-124">**Production cost** – The production cost is the top line of the estimate.</span></span> <span data-ttu-id="0cfe6-125">Elle présente le coût complet de l'exécution de l'ordre de fabrication et le prix de vente total de la production.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-125">It shows the complete cost of running the production order and the total sales price for the production.</span></span> <span data-ttu-id="0cfe6-126">C'est la somme de toutes les lignes de coût de l'estimation.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-126">It's the sum of all the cost lines on the estimate.</span></span>
-   <span data-ttu-id="0cfe6-127">**Coûts de gamme ou de ressource** : les coûts de gamme ou de ressources correspondent aux coûts des opérations de production.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-127">**Route or resource costs** – Route or resource costs are the costs for the production operations.</span></span> <span data-ttu-id="0cfe6-128">Ils incluent le coût d'éléments comme le temps de réglage, le temps d'exécution, et les frais généraux.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-128">They include the cost of elements such as setup time, run time, and overhead.</span></span>
-   <span data-ttu-id="0cfe6-129">**Coûts des matières** : les coûts des matières correspondent aux coûts et aux prix des composants de la nomenclature nécessaires pour produire l'article.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-129">**Material costs** – Material costs are the costs and prices of the BOM components that are required in order to produce the item.</span></span> <span data-ttu-id="0cfe6-130">Ces coûts ont été précédemment établis et entrés dans le système.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-130">These costs have previously been established and entered into the system.</span></span>

## <a name="other-uses-of-cost-estimation"></a><span data-ttu-id="0cfe6-131">Autres usages d'une estimation des coûts</span><span class="sxs-lookup"><span data-stu-id="0cfe6-131">Other uses of cost estimation</span></span>
<span data-ttu-id="0cfe6-132">Une estimation des coûts fournit également les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0cfe6-132">A cost estimate also provides the following information:</span></span>

-   <span data-ttu-id="0cfe6-133">des devis significatifs ;</span><span class="sxs-lookup"><span data-stu-id="0cfe6-133">Meaningful price quotations</span></span>
-   <span data-ttu-id="0cfe6-134">des estimations de la rentabilité de la commande ;</span><span class="sxs-lookup"><span data-stu-id="0cfe6-134">Estimates of the profitability of the order</span></span>
-   <span data-ttu-id="0cfe6-135">des estimations de l'utilisation de matières premières ;</span><span class="sxs-lookup"><span data-stu-id="0cfe6-135">Estimates of raw material usage</span></span>
-   <span data-ttu-id="0cfe6-136">des comparaisons d'informations de coûts à partir de productions précédentes ;</span><span class="sxs-lookup"><span data-stu-id="0cfe6-136">Comparisons of cost information from previous productions</span></span>
-   <span data-ttu-id="0cfe6-137">des informations de budget et de prévision ;</span><span class="sxs-lookup"><span data-stu-id="0cfe6-137">Budget and forecasting information</span></span>
-   <span data-ttu-id="0cfe6-138">des estimations de la taille de production requise pour maintenir un coût particulier.</span><span class="sxs-lookup"><span data-stu-id="0cfe6-138">Estimates of the production size that is required in order to maintain a particular cost</span></span>




