--- 
title: "Créer et affecter une stratégie d'affectation des coûts à une unité de contrôle des coûts"
description: "Cette procédure permet de créer et d'affecter une stratégie de répartition des coûts et les règles correspondantes à une unité de contrôle des coûts."
author: YuyuScheller
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ff9b4ddeecfdb795c1eead0e9e2100c307f63db4
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="87272-103">Créer et affecter une stratégie d'affectation des coûts à une unité de contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="87272-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="87272-104">Cette procédure permet de créer et d'affecter une stratégie de répartition des coûts et les règles correspondantes à une unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="87272-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="87272-105">Cet enregistrement utilise la société fictive USP2.</span><span class="sxs-lookup"><span data-stu-id="87272-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="87272-106">Créer une stratégie</span><span class="sxs-lookup"><span data-stu-id="87272-106">Create a policy</span></span>
1. <span data-ttu-id="87272-107">Accédez à Contrôle de gestion > Stratégies > Stratégies de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="87272-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="87272-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="87272-108">Click New.</span></span>
3. <span data-ttu-id="87272-109">Dans le champ Nom de la stratégie, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="87272-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="87272-110">Dans le champ Hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="87272-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="87272-111">Sélectionnez Organisation.</span><span class="sxs-lookup"><span data-stu-id="87272-111">Select Organization.</span></span>  
5. <span data-ttu-id="87272-112">Dans le champ Dimension statistique, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="87272-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="87272-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="87272-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="87272-114">Créer des règles de répartition</span><span class="sxs-lookup"><span data-stu-id="87272-114">Create allocation rules</span></span>
1. <span data-ttu-id="87272-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="87272-115">Click New.</span></span>
2. <span data-ttu-id="87272-116">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="87272-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="87272-117">Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="87272-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="87272-118">Dans le champ Comportement de coût, sélectionnez « Total ».</span><span class="sxs-lookup"><span data-stu-id="87272-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="87272-119">Dans le champ Base de répartition, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="87272-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="87272-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="87272-120">Click New.</span></span>
7. <span data-ttu-id="87272-121">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="87272-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="87272-122">Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="87272-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="87272-123">Dans le champ Comportement de coût, sélectionnez « Total ».</span><span class="sxs-lookup"><span data-stu-id="87272-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="87272-124">Dans le champ Base de répartition, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="87272-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="87272-125">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="87272-125">Click New.</span></span>
12. <span data-ttu-id="87272-126">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="87272-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="87272-127">Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="87272-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="87272-128">Dans le champ Comportement de coût, sélectionnez « Total ».</span><span class="sxs-lookup"><span data-stu-id="87272-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="87272-129">Dans le champ Base de répartition, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="87272-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="87272-130">Continuez jusqu'à ce que vous ayez créé toutes les règles.</span><span class="sxs-lookup"><span data-stu-id="87272-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="87272-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="87272-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="87272-132">Affecter la stratégie à une unité de contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="87272-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="87272-133">Cliquez sur Affectations de stratégie pour l'unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="87272-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="87272-134">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="87272-134">Click New.</span></span>
3. <span data-ttu-id="87272-135">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="87272-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="87272-136">Dans le champ Valide à partir de la date comptable, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="87272-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="87272-137">Les règles ont une date d'effet.</span><span class="sxs-lookup"><span data-stu-id="87272-137">The rules are date-effective.</span></span> <span data-ttu-id="87272-138">Un utilisateur ou le système peut faire expirer les règles si une version plus récente est créée.</span><span class="sxs-lookup"><span data-stu-id="87272-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="87272-139">Dans le champ Unité de contrôle des coûts, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="87272-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="87272-140">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="87272-140">Click Save.</span></span>


