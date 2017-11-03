---
title: "Dimensions d'éléments de coût"
description: "En tant que l'un des piliers de base du contrôle de gestion, les dimensions d'éléments de coût sont utilisées pour catégoriser et suivre le flux des coûts."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0f47c75b6f6f4533501070f78698de82cf70f9bd
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="cost-element-dimensions"></a><span data-ttu-id="5c61b-103">Dimensions d'éléments de coût</span><span class="sxs-lookup"><span data-stu-id="5c61b-103">Cost element dimensions</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5c61b-104">En tant que l'un des piliers de base du contrôle de gestion, les dimensions d'éléments de coût sont utilisées pour catégoriser et suivre le flux des coûts.</span><span class="sxs-lookup"><span data-stu-id="5c61b-104">As one of the core pillars in Cost accounting, cost element dimensions are used to categorize and track where costs flow to.</span></span> 

<span data-ttu-id="5c61b-105">Un élément de coût correspond à un article dont le coût est pertinent dans le plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="5c61b-105">A cost element corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="5c61b-106">Fondamentalement, il peut s'agir de n'importe quel type d'élément au niveau le plus bas d'une société vers lequel les coûts peuvent se diriger.</span><span class="sxs-lookup"><span data-stu-id="5c61b-106">Basically, it can be any type of element at the lowest level in a business where costs can flow to.</span></span> <span data-ttu-id="5c61b-107">Les éléments de coûts comme plage de concept des comptes généraux à toutes les ressources dont le coût est pertinent.</span><span class="sxs-lookup"><span data-stu-id="5c61b-107">Cost elements as a concept range from ledger accounts to all cost-relevant resources.</span></span> <span data-ttu-id="5c61b-108">Actuellement, le contrôle de gestion prend en charge les comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="5c61b-108">Currently, Cost accounting supports ledger accounts.</span></span>

## <a name="two-types-of-cost-elements"></a><span data-ttu-id="5c61b-109">Deux types d'éléments de coût</span><span class="sxs-lookup"><span data-stu-id="5c61b-109">Two types of cost elements</span></span>
<span data-ttu-id="5c61b-110">Il existe deux types d'éléments de coût : les éléments de coût principaux et les éléments de coût secondaires.</span><span class="sxs-lookup"><span data-stu-id="5c61b-110">There are two types of cost elements: primary cost elements and secondary cost elements.</span></span> <span data-ttu-id="5c61b-111">Le tableau suivant décrit les différences entre les deux types.</span><span class="sxs-lookup"><span data-stu-id="5c61b-111">The following table describes the difference between the two types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5c61b-112"><strong>Éléments de coût principaux</strong></span><span class="sxs-lookup"><span data-stu-id="5c61b-112"><strong>Primary cost elements</strong></span></span></td>
<td><span data-ttu-id="5c61b-113"><strong>Éléments de coût secondaires</strong></span><span class="sxs-lookup"><span data-stu-id="5c61b-113"><strong>Secondary cost elements</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5c61b-114">Les éléments de coûts principaux représentent le flux des coûts entre la comptabilité financière et le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="5c61b-114">The primary cost elements represent the flow of costs from financial accounting to cost accounting.</span></span> <span data-ttu-id="5c61b-115">La structure d'élément de coût correspond à la structure de compte de résultat dans la comptabilité, dans laquelle un élément de coût peut correspondre à un compte principal.</span><span class="sxs-lookup"><span data-stu-id="5c61b-115">The cost element structure corresponds to the profit and loss account structure in the general ledger, where a cost element can correspond to a main account.</span></span> <span data-ttu-id="5c61b-116">Tous les comptes principaux ne doivent pas nécessairement être représentés en tant qu'éléments de coûts, en fonction des besoins de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="5c61b-116">Not all main accounts may necessarily be represented as cost elements depending on the business needs.</span></span> <span data-ttu-id="5c61b-117">Voici quelques exemples d'éléments de coût principaux :</span><span class="sxs-lookup"><span data-stu-id="5c61b-117">Examples of primary cost elements include:</span></span>
<ul>
<li><span data-ttu-id="5c61b-118">Coûts des marchandises vendues</span><span class="sxs-lookup"><span data-stu-id="5c61b-118">Costs of goods sold (COGs)</span></span></li>
<li><span data-ttu-id="5c61b-119">Coûts indirects liés aux matières</span><span class="sxs-lookup"><span data-stu-id="5c61b-119">Indirect material costs</span></span></li>
<li><span data-ttu-id="5c61b-120">Coûts de personnel</span><span class="sxs-lookup"><span data-stu-id="5c61b-120">Personnel costs</span></span></li>
<li><span data-ttu-id="5c61b-121">Coûts énergétiques</span><span class="sxs-lookup"><span data-stu-id="5c61b-121">Energy costs</span></span></li>
</ul></td>
<td><span data-ttu-id="5c61b-122">Les éléments des coûts secondaires représentent le flux interne des coûts, car ces coûts sont créés et utilisées uniquement dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="5c61b-122">The secondary cost elements represent the flow of costs internally because these costs are created and used only in Cost accounting.</span></span> <span data-ttu-id="5c61b-123">Ils sont utilisés pour s'assurer que la source de coûts peut être retracée.</span><span class="sxs-lookup"><span data-stu-id="5c61b-123">They are used to secure that the source of costs can be traced.</span></span> <span data-ttu-id="5c61b-124">Ces éléments de coût sont utilisés dans les répartitions de coûts et les calculs des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="5c61b-124">These cost elements are used in cost allocations and overhead calculations.</span></span> <span data-ttu-id="5c61b-125">Voici quelques exemples d'éléments de coût secondaires :</span><span class="sxs-lookup"><span data-stu-id="5c61b-125">Examples of secondary cost elements include:</span></span>
<ul>
<li><span data-ttu-id="5c61b-126">Coûts de production</span><span class="sxs-lookup"><span data-stu-id="5c61b-126">Production costs</span></span></li>
<li><span data-ttu-id="5c61b-127">Production, matières, et frais généraux de marketing</span><span class="sxs-lookup"><span data-stu-id="5c61b-127">Production, material, and marketing overheads</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a><span data-ttu-id="5c61b-128">Dimensions d'éléments de coût et membres de la dimension d'élément de coût</span><span class="sxs-lookup"><span data-stu-id="5c61b-128">Cost element dimensions and cost element dimension members</span></span>
<span data-ttu-id="5c61b-129">Les éléments de coût sont appelés des *dimensions d'éléments de coût*.</span><span class="sxs-lookup"><span data-stu-id="5c61b-129">Cost elements are referred to as *cost element dimensions* .</span></span> <span data-ttu-id="5c61b-130">Les valeurs de dimension individuelle sont appelées *membres de la dimension d'élément de coût*.</span><span class="sxs-lookup"><span data-stu-id="5c61b-130">The individual dimension values are called *cost element dimension members*.</span></span> <span data-ttu-id="5c61b-131">Par exemple, vous disposez d'une structure de plan de comptes américain qui est la base de la génération d'états statutaires.</span><span class="sxs-lookup"><span data-stu-id="5c61b-131">For example, you have a US chart of accounts structure (COA) that is the base for your statutory reporting.</span></span> <span data-ttu-id="5c61b-132">Cette structure de plan de comptes est utilisée comme dimension d'élément de coût.</span><span class="sxs-lookup"><span data-stu-id="5c61b-132">This COA is used as the cost element dimension.</span></span> <span data-ttu-id="5c61b-133">Les comptes, qui sont des éléments de coût principaux, sont représentées comme les membres de la dimension d'élément de coût dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="5c61b-133">The accounts, which are primary cost elements, are represented as the cost element dimension members in Cost accounting.</span></span> <span data-ttu-id="5c61b-134">La capture d'écran suivante illustre un exemple de comptes principaux comme dimension d'élément de coût avec ses comptes principaux réels comme membres de la dimension d'élément de coût.</span><span class="sxs-lookup"><span data-stu-id="5c61b-134">The following screenshot shows an example of Main Accounts as the cost element dimension with its actual main accounts as the cost element dimension members.</span></span> 

<span data-ttu-id="5c61b-135">[![cost-element-dimensions](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="5c61b-135">[![cost-element-dimensions](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)</span></span>

## <a name="import-cost-element-dimension-members-through-data-connectors"></a><span data-ttu-id="5c61b-136">Importer les membres de la dimension d'élément de coût à l'aide de connecteurs de données</span><span class="sxs-lookup"><span data-stu-id="5c61b-136">Import cost element dimension members through data connectors</span></span>
<span data-ttu-id="5c61b-137">Pour faciliter le paramétrage des membres de la dimension d'élément de coût dans le contrôle de gestion, vous pouvez utiliser des connecteurs de données qui sont préconçus ou personnalisés pour récupérer les éléments de coût principaux d'un ou plusieurs systèmes sources.</span><span class="sxs-lookup"><span data-stu-id="5c61b-137">To ease the setup of cost element dimension members in Cost accounting, you can use data connectors that are either pre-built or your custom build to retrieve the primary cost elements from one or more source systems.</span></span>

## <a name="implementation-considerations"></a><span data-ttu-id="5c61b-138">Considérations d'implémentation</span><span class="sxs-lookup"><span data-stu-id="5c61b-138">Implementation considerations</span></span>
<span data-ttu-id="5c61b-139">Puisque les éléments de coûts représentent le niveau le plus bas des détails de coût, vous devez vous assurer que tous les éléments de coût requis pour la génération d'états de gestionnaire sont inclus lorsque vous implémentez la structure d'éléments de coût.</span><span class="sxs-lookup"><span data-stu-id="5c61b-139">As cost elements represent the lowest level of cost details, you should make sure that all the cost elements required to make the managerial reporting are included when you implement the cost elements structure.</span></span> <span data-ttu-id="5c61b-140">Cela peut être un défi de rechercher un numéro d'éléments de coût approprié pour le contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="5c61b-140">It can be a challenge to find an appropriate number of cost elements for cost control.</span></span> <span data-ttu-id="5c61b-141">Avoir des milliers d'éléments de coût peut rendre difficile le contrôle de chaque élément de coût.</span><span class="sxs-lookup"><span data-stu-id="5c61b-141">Having thousands of cost elements can make it difficult to control each cost element.</span></span> <span data-ttu-id="5c61b-142">À la place, vous pouvez regrouper des éléments de coût et gérer le contrôle des coûts à un niveau agrégé.</span><span class="sxs-lookup"><span data-stu-id="5c61b-142">As an alternative, you can group cost elements and manage cost control at an aggregated level.</span></span>




