--- 
title: "Créer une stratégie de repositionnement des coûts"
description: "Cette procédure indique comment créer une stratégie de repositionnement des coûts et créer des règles pour la stratégie."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e6eddaf80d7b508a2d477bdd731b2b19cb02acd5
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-cost-rollup-policy"></a><span data-ttu-id="5b769-103">Créer une stratégie de repositionnement des coûts</span><span class="sxs-lookup"><span data-stu-id="5b769-103">Create a cost rollup policy</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5b769-104">Cette procédure indique comment créer une stratégie de repositionnement des coûts et créer des règles pour la stratégie.</span><span class="sxs-lookup"><span data-stu-id="5b769-104">This procedure shows how to create a cost rollup policy and create rules for the policy.</span></span> <span data-ttu-id="5b769-105">Les données de démonstration utilisées pour créer cette procédure sont USP2.</span><span class="sxs-lookup"><span data-stu-id="5b769-105">The demo data used to create this procedure is USP2.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="5b769-106">Créer une stratégie</span><span class="sxs-lookup"><span data-stu-id="5b769-106">Create a policy</span></span>
1. <span data-ttu-id="5b769-107">Accédez à Contrôle de gestion > Stratégies > Stratégies de repositionnement des coûts.</span><span class="sxs-lookup"><span data-stu-id="5b769-107">Go to Cost accounting > Policies > Cost rollup policies.</span></span>
2. <span data-ttu-id="5b769-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="5b769-108">Click New.</span></span>
3. <span data-ttu-id="5b769-109">Dans le champ Nom de la stratégie, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="5b769-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5b769-111">Dans le champ Hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-111">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="5b769-112">Sélectionnez le centre de coût Repositionnement des coûts.</span><span class="sxs-lookup"><span data-stu-id="5b769-112">Select Cost rollup CC.</span></span>  
6. <span data-ttu-id="5b769-113">Dans le champ Hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-113">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="5b769-114">Sélectionnez le centre de coût Repositionnement des coûts.</span><span class="sxs-lookup"><span data-stu-id="5b769-114">Select Cost rollup CC.</span></span>  
7. <span data-ttu-id="5b769-115">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="5b769-115">Click Save.</span></span>

## <a name="create-rules-for-the-cost-rollup-policy"></a><span data-ttu-id="5b769-116">Créer des règles pour la stratégie de repositionnement des coûts</span><span class="sxs-lookup"><span data-stu-id="5b769-116">Create rules for the cost rollup policy</span></span>
1. <span data-ttu-id="5b769-117">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="5b769-117">Click New.</span></span>
2. <span data-ttu-id="5b769-118">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5b769-118">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="5b769-119">Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-119">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5b769-120">Sélectionnez 007.</span><span class="sxs-lookup"><span data-stu-id="5b769-120">Select 007.</span></span>  
4. <span data-ttu-id="5b769-121">Dans le champ Nœud de hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-121">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5b769-122">Sélectionnez le CE Repositionnement des coûts.</span><span class="sxs-lookup"><span data-stu-id="5b769-122">Select Cost rollup CE.</span></span>  
5. <span data-ttu-id="5b769-123">Dans le champ Élément de coût secondaire, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-123">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="5b769-124">Pour cet exemple, mettez en correspondance l'élément de coût secondaire CC-007 avec le centre de coût.</span><span class="sxs-lookup"><span data-stu-id="5b769-124">For this example, map the secondary cost element CC-007 to the cost center.</span></span>  
6. <span data-ttu-id="5b769-125">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="5b769-125">Click New.</span></span>
7. <span data-ttu-id="5b769-126">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5b769-126">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="5b769-127">Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5b769-128">Sélectionnez 008.</span><span class="sxs-lookup"><span data-stu-id="5b769-128">Select 008.</span></span>  
9. <span data-ttu-id="5b769-129">Dans le champ Nœud de hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-129">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5b769-130">Sélectionnez le CE Repositionnement des coûts.</span><span class="sxs-lookup"><span data-stu-id="5b769-130">Select Cost rollup CE.</span></span>  
10. <span data-ttu-id="5b769-131">Dans le champ Élément de coût secondaire, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-131">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="5b769-132">Pour cet exemple, mettez en correspondance l'élément de coût secondaire CC-008 avec le centre de coût.</span><span class="sxs-lookup"><span data-stu-id="5b769-132">For this example, map the secondary cost element CC-008 to the cost center.</span></span>  
11. <span data-ttu-id="5b769-133">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="5b769-133">Click New.</span></span>
12. <span data-ttu-id="5b769-134">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5b769-134">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="5b769-135">Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-135">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5b769-136">Sélectionnez 009.</span><span class="sxs-lookup"><span data-stu-id="5b769-136">Select 009.</span></span>  
14. <span data-ttu-id="5b769-137">Dans le champ Nœud de hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-137">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5b769-138">Sélectionnez le CE Repositionnement des coûts.</span><span class="sxs-lookup"><span data-stu-id="5b769-138">Select Cost rollup CE.</span></span>  
15. <span data-ttu-id="5b769-139">Dans le champ Élément de coût secondaire, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b769-139">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="5b769-140">Pour cet exemple, mettez en correspondance l'élément de coût secondaire CC-009 avec le centre de coût.</span><span class="sxs-lookup"><span data-stu-id="5b769-140">For this example, map the secondary cost element CC-009 to the cost center.</span></span>  
    * <span data-ttu-id="5b769-141">Continuez jusqu'à ce que tous les centres de coût soient mis en correspondance avec leurs éléments de coût secondaires correspondants.</span><span class="sxs-lookup"><span data-stu-id="5b769-141">Continue until all cost centers are mapped to their corresponding secondary cost elements.</span></span>  
16. <span data-ttu-id="5b769-142">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="5b769-142">Click Save.</span></span>


