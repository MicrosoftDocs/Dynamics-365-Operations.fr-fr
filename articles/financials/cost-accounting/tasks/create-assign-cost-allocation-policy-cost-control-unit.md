---
title: Créer et affecter une stratégie d'affectation des coûts à une unité de contrôle des coûts
description: Cette procédure permet de créer et d'affecter une stratégie de répartition des coûts et les règles correspondantes à une unité de contrôle des coûts.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f0422a9aaf95184b556293bf6ebcaf4dcfb5b59
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841391"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="9199b-103">Créer et affecter une stratégie d'affectation des coûts à une unité de contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="9199b-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9199b-104">Cette procédure permet de créer et d'affecter une stratégie de répartition des coûts et les règles correspondantes à une unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="9199b-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="9199b-105">Cet enregistrement utilise la société fictive USP2.</span><span class="sxs-lookup"><span data-stu-id="9199b-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="9199b-106">Créer une stratégie</span><span class="sxs-lookup"><span data-stu-id="9199b-106">Create a policy</span></span>
1. <span data-ttu-id="9199b-107">Accédez à Contrôle de gestion > Stratégies > Stratégies de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="9199b-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="9199b-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9199b-108">Click New.</span></span>
3. <span data-ttu-id="9199b-109">Dans le champ Nom de la stratégie, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9199b-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="9199b-110">Dans le champ Hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9199b-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="9199b-111">Sélectionnez Organisation.</span><span class="sxs-lookup"><span data-stu-id="9199b-111">Select Organization.</span></span>  
5. <span data-ttu-id="9199b-112">Dans le champ Dimension statistique, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9199b-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="9199b-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9199b-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="9199b-114">Créer des règles de répartition</span><span class="sxs-lookup"><span data-stu-id="9199b-114">Create allocation rules</span></span>
1. <span data-ttu-id="9199b-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9199b-115">Click New.</span></span>
2. <span data-ttu-id="9199b-116">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9199b-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="9199b-117">Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9199b-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="9199b-118">Dans le champ Comportement de coût, sélectionnez « Total ».</span><span class="sxs-lookup"><span data-stu-id="9199b-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="9199b-119">Dans le champ Base de répartition, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9199b-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="9199b-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9199b-120">Click New.</span></span>
7. <span data-ttu-id="9199b-121">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9199b-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="9199b-122">Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9199b-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="9199b-123">Dans le champ Comportement de coût, sélectionnez « Total ».</span><span class="sxs-lookup"><span data-stu-id="9199b-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="9199b-124">Dans le champ Base de répartition, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9199b-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="9199b-125">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9199b-125">Click New.</span></span>
12. <span data-ttu-id="9199b-126">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9199b-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="9199b-127">Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9199b-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="9199b-128">Dans le champ Comportement de coût, sélectionnez « Total ».</span><span class="sxs-lookup"><span data-stu-id="9199b-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="9199b-129">Dans le champ Base de répartition, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9199b-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="9199b-130">Continuez jusqu'à ce que vous ayez créé toutes les règles.</span><span class="sxs-lookup"><span data-stu-id="9199b-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="9199b-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9199b-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="9199b-132">Affecter la stratégie à une unité de contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="9199b-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="9199b-133">Cliquez sur Affectations de stratégie pour l'unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="9199b-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="9199b-134">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9199b-134">Click New.</span></span>
3. <span data-ttu-id="9199b-135">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9199b-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="9199b-136">Dans le champ Valide à partir de la date comptable, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="9199b-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="9199b-137">Les règles ont une date d'effet.</span><span class="sxs-lookup"><span data-stu-id="9199b-137">The rules are date-effective.</span></span> <span data-ttu-id="9199b-138">Un utilisateur ou le système peut faire expirer les règles si une version plus récente est créée.</span><span class="sxs-lookup"><span data-stu-id="9199b-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="9199b-139">Dans le champ Unité de contrôle des coûts, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9199b-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="9199b-140">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9199b-140">Click Save.</span></span>

