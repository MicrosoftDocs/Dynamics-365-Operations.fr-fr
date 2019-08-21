---
title: Créer des structures de compte
description: Ce guide accompagne l'utilisateur le long de la création d'une structure de compte.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2183f88356fc8094781af147bf079c4e53ffb2b4
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846701"
---
# <a name="create-account-structures"></a><span data-ttu-id="2c669-103">Créer des structures de compte</span><span class="sxs-lookup"><span data-stu-id="2c669-103">Create account structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2c669-104">Ce guide accompagne l'utilisateur le long de la création d'une structure de compte.</span><span class="sxs-lookup"><span data-stu-id="2c669-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="2c669-105">La société fictive USMF est citée en exemple dans les étapes.</span><span class="sxs-lookup"><span data-stu-id="2c669-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="2c669-106">Accédez à Comptabilité > Plan de comptes > Structures > Configurer les structures de compte.</span><span class="sxs-lookup"><span data-stu-id="2c669-106">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
2. <span data-ttu-id="2c669-107">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2c669-107">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="2c669-108">Dans le champ Structure de compte, entrez un nom pour décrire l'objectif de la structure de compte.</span><span class="sxs-lookup"><span data-stu-id="2c669-108">In the Account structure field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="2c669-109">Dans le champ Description, entrez une description pour préciser l'objectif de la structure de compte.</span><span class="sxs-lookup"><span data-stu-id="2c669-109">In the Description field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="2c669-110">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="2c669-110">Click Create.</span></span>
6. <span data-ttu-id="2c669-111">Cliquez sur Ajouter un segment.</span><span class="sxs-lookup"><span data-stu-id="2c669-111">Click Add segment.</span></span>
7. <span data-ttu-id="2c669-112">Dans la liste des dimensions répertoriez, sélectionnez la dimension à ajouter à la structure de compte.</span><span class="sxs-lookup"><span data-stu-id="2c669-112">In the Dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="2c669-113">Cliquez sur Ajouter un segment.</span><span class="sxs-lookup"><span data-stu-id="2c669-113">Click Add segment.</span></span>
9. <span data-ttu-id="2c669-114">Cliquez sur Ajouter un segment.</span><span class="sxs-lookup"><span data-stu-id="2c669-114">Click Add segment.</span></span>
10. <span data-ttu-id="2c669-115">Dans la liste des dimensions répertoriez, sélectionnez la dimension à ajouter à la structure de compte.</span><span class="sxs-lookup"><span data-stu-id="2c669-115">In the Dimensions list, select the dimension to add to the account structure.</span></span>
11. <span data-ttu-id="2c669-116">Cliquez sur Ajouter un segment.</span><span class="sxs-lookup"><span data-stu-id="2c669-116">Click Add segment.</span></span>
12. <span data-ttu-id="2c669-117">Cliquez sur Ajouter un segment.</span><span class="sxs-lookup"><span data-stu-id="2c669-117">Click Add segment.</span></span>
13. <span data-ttu-id="2c669-118">Dans la liste des dimensions répertoriez, sélectionnez la dimension à ajouter à la structure de compte.</span><span class="sxs-lookup"><span data-stu-id="2c669-118">In the Dimensions list, select the dimension to add to the account structure.</span></span>
14. <span data-ttu-id="2c669-119">Cliquez sur Ajouter un segment.</span><span class="sxs-lookup"><span data-stu-id="2c669-119">Click Add segment.</span></span>
15. <span data-ttu-id="2c669-120">Dans la grille, sélectionnez le segment pour modifier les valeurs autorisées.</span><span class="sxs-lookup"><span data-stu-id="2c669-120">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="2c669-121">Par exemple, cliquez dans le compte principal.</span><span class="sxs-lookup"><span data-stu-id="2c669-121">For example, click in Main Account.</span></span>  
16. <span data-ttu-id="2c669-122">Dans le champ Opérateur, sélectionnez une option, comme Est compris entre et Comprend.</span><span class="sxs-lookup"><span data-stu-id="2c669-122">In the Operator field, select an option, such as is between and includes.</span></span>
17. <span data-ttu-id="2c669-123">Tapez une valeur dans le champ Valeur.</span><span class="sxs-lookup"><span data-stu-id="2c669-123">In the Value field, type a value.</span></span>
    * <span data-ttu-id="2c669-124">Par exemple, 600000.</span><span class="sxs-lookup"><span data-stu-id="2c669-124">For example, 600000.</span></span>  
18. <span data-ttu-id="2c669-125">Dans le champ À, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2c669-125">In the through field, type a value.</span></span>
    * <span data-ttu-id="2c669-126">Par exemple, 699999.</span><span class="sxs-lookup"><span data-stu-id="2c669-126">For example, 699999.</span></span>  
19. <span data-ttu-id="2c669-127">Cliquez sur Appliquer.</span><span class="sxs-lookup"><span data-stu-id="2c669-127">Click Apply.</span></span>
20. <span data-ttu-id="2c669-128">Dans la grille, sélectionnez le segment pour modifier les valeurs autorisées.</span><span class="sxs-lookup"><span data-stu-id="2c669-128">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="2c669-129">Par exemple, Département.</span><span class="sxs-lookup"><span data-stu-id="2c669-129">For example, Department.</span></span>  
21. <span data-ttu-id="2c669-130">Dans le champ Opérateur, sélectionnez une option, comme Est compris entre et Comprend.</span><span class="sxs-lookup"><span data-stu-id="2c669-130">In the Operator field, select an option, such as is between and includes.</span></span>
22. <span data-ttu-id="2c669-131">Tapez une valeur dans le champ Valeur.</span><span class="sxs-lookup"><span data-stu-id="2c669-131">In the Value field, type a value.</span></span>
    * <span data-ttu-id="2c669-132">Par exemple, 022.</span><span class="sxs-lookup"><span data-stu-id="2c669-132">For example, 022.</span></span>  
23. <span data-ttu-id="2c669-133">Dans le champ À, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2c669-133">In the through field, type a value.</span></span>
    * <span data-ttu-id="2c669-134">Par exemple, 031.</span><span class="sxs-lookup"><span data-stu-id="2c669-134">For example, 031.</span></span>  
24. <span data-ttu-id="2c669-135">Cliquez sur Ajouter de nouveaux critères.</span><span class="sxs-lookup"><span data-stu-id="2c669-135">Click Add new criteria.</span></span>
25. <span data-ttu-id="2c669-136">Dans le champ Opérateur, sélectionnez une option, comme Est compris entre et Comprend.</span><span class="sxs-lookup"><span data-stu-id="2c669-136">In the Operator field, select an option, such as is between and includes.</span></span>
26. <span data-ttu-id="2c669-137">Tapez une valeur dans le champ Valeur.</span><span class="sxs-lookup"><span data-stu-id="2c669-137">In the Value field, type a value.</span></span>
    * <span data-ttu-id="2c669-138">Par exemple, 033.</span><span class="sxs-lookup"><span data-stu-id="2c669-138">For example, 033.</span></span>  
27. <span data-ttu-id="2c669-139">Dans le champ À, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2c669-139">In the through field, type a value.</span></span>
    * <span data-ttu-id="2c669-140">Par exemple, 034.</span><span class="sxs-lookup"><span data-stu-id="2c669-140">For example, 034.</span></span>  
28. <span data-ttu-id="2c669-141">Cliquez sur Appliquer.</span><span class="sxs-lookup"><span data-stu-id="2c669-141">Click Apply.</span></span>
29. <span data-ttu-id="2c669-142">Dans la grille, sélectionnez le segment pour modifier les valeurs autorisées.</span><span class="sxs-lookup"><span data-stu-id="2c669-142">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="2c669-143">Par exemple, Centre de coût.</span><span class="sxs-lookup"><span data-stu-id="2c669-143">For example, Cost Center.</span></span>  
30. <span data-ttu-id="2c669-144">Dans le champ Centre de coût, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2c669-144">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="2c669-145">Par exemple, 007..021.</span><span class="sxs-lookup"><span data-stu-id="2c669-145">For example, 007..021.</span></span>  
31. <span data-ttu-id="2c669-146">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="2c669-146">Click Add.</span></span>
32. <span data-ttu-id="2c669-147">Dans le champ Compte principal, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2c669-147">In the MainAccount field, type a value.</span></span>
    * <span data-ttu-id="2c669-148">Par exemple, 600000..699999</span><span class="sxs-lookup"><span data-stu-id="2c669-148">For example, 600000..699999</span></span>  
33. <span data-ttu-id="2c669-149">Dans la grille, sélectionnez le segment pour modifier les valeurs autorisées.</span><span class="sxs-lookup"><span data-stu-id="2c669-149">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="2c669-150">Par exemple, Département.</span><span class="sxs-lookup"><span data-stu-id="2c669-150">For example, Department.</span></span>  
34. <span data-ttu-id="2c669-151">Dans le champ Département, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2c669-151">In the Department field, type a value.</span></span>
    * <span data-ttu-id="2c669-152">Par exemple, 032.</span><span class="sxs-lookup"><span data-stu-id="2c669-152">For example, 032.</span></span>  
35. <span data-ttu-id="2c669-153">Dans le champ Centre de coût, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2c669-153">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="2c669-154">Par exemple, 086.</span><span class="sxs-lookup"><span data-stu-id="2c669-154">For example, 086.</span></span>  
36. <span data-ttu-id="2c669-155">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="2c669-155">Click Validate.</span></span>
37. <span data-ttu-id="2c669-156">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="2c669-156">Click Activate.</span></span>
38. <span data-ttu-id="2c669-157">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="2c669-157">Click Activate.</span></span>

