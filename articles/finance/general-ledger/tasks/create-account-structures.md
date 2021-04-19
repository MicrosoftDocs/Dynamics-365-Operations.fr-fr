---
title: Créer des structures de compte
description: Ce guide accompagne l’utilisateur le long de la création d’une structure de compte.
author: aprilolson
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aece2b79633802d28ba3b4fd8b51788e26c17a67
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815162"
---
# <a name="create-account-structures"></a><span data-ttu-id="5ffad-103">Créer des structures de compte</span><span class="sxs-lookup"><span data-stu-id="5ffad-103">Create account structures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5ffad-104">Ce guide accompagne l’utilisateur le long de la création d’une structure de compte.</span><span class="sxs-lookup"><span data-stu-id="5ffad-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="5ffad-105">La société fictive USMF est citée en exemple dans les étapes.</span><span class="sxs-lookup"><span data-stu-id="5ffad-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="5ffad-106">Accédez au **Volet de navigation > Modules > Comptabilité > Plan de comptes > Structures > Configurer les structures de compte**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-106">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="5ffad-107">Dans le volet **Actions**, cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="5ffad-107">On the **Action pane**, click **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="5ffad-108">Dans le champ **Structure de compte**, entrez un nom pour décrire l’objectif de la structure de compte.</span><span class="sxs-lookup"><span data-stu-id="5ffad-108">In the **Account structure** field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="5ffad-109">Dans le champ **Description**, entrez une description pour préciser l’objectif de la structure de compte.</span><span class="sxs-lookup"><span data-stu-id="5ffad-109">In the **Description** field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="5ffad-110">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-110">Click **Create**.</span></span>
6. <span data-ttu-id="5ffad-111">Dans **Segments et valeurs autorisées**, cliquez sur **Ajouter un segment**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-111">In the **Segments and allowed values**, click **Add segment**.</span></span>
7. <span data-ttu-id="5ffad-112">Dans la liste des dimensions, sélectionnez la dimension à ajouter à la structure de compte.</span><span class="sxs-lookup"><span data-stu-id="5ffad-112">In the dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="5ffad-113">À la fin de la liste, cliquez sur **Ajouter un segment**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-113">At the end of the list, click **Add segment**.</span></span>
9. <span data-ttu-id="5ffad-114">Répétez les étapes 6 à 9 si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5ffad-114">Repeat step 6 to 9 as needed.</span></span>
10. <span data-ttu-id="5ffad-115">Dans la section **Détails des valeurs autorisées**, sélectionnez le segment pour modifier les valeurs autorisées.</span><span class="sxs-lookup"><span data-stu-id="5ffad-115">In the **Allowed value details** section, select the segment to edit the allowed values.</span></span>
    <span data-ttu-id="5ffad-116">Par exemple, cliquez dans le **compte principal**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-116">For example, click the **Main Account** field.</span></span>  
11. <span data-ttu-id="5ffad-117">Dans le champ **Opérateur**, sélectionnez une option, comme Est compris entre et Comprend.</span><span class="sxs-lookup"><span data-stu-id="5ffad-117">In the **Operator** field, select an option, such as is between and includes.</span></span>
12. <span data-ttu-id="5ffad-118">Tapez une valeur dans le champ **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-118">In the **Value** field, type a value.</span></span> <span data-ttu-id="5ffad-119">Par exemple, 600000.</span><span class="sxs-lookup"><span data-stu-id="5ffad-119">For example, 600000.</span></span>  
13. <span data-ttu-id="5ffad-120">Dans le champ **À**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5ffad-120">In the **through** field, type a value.</span></span> <span data-ttu-id="5ffad-121">Par exemple, 699999.</span><span class="sxs-lookup"><span data-stu-id="5ffad-121">For example, 699999.</span></span>  
14. <span data-ttu-id="5ffad-122">Dans la section **Détails de valeur autorisées**, cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-122">In the **Allowed value details** section, click **Apply**.</span></span>
15. <span data-ttu-id="5ffad-123">Répétez les étapes 10 à 15 si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5ffad-123">Repeat step 10 to 15 as needed.</span></span>  
16. <span data-ttu-id="5ffad-124">Dans la section **Détails de valeur autorisées**, cliquez sur **Ajouter de nouveaux critères**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-124">In the **Allowed value details** section, click **Add new criteria**.</span></span>
17. <span data-ttu-id="5ffad-125">Dans le champ Opérateur, sélectionnez une option, comme Est compris entre et Comprend.</span><span class="sxs-lookup"><span data-stu-id="5ffad-125">In the Operator field, select an option, such as is between and includes.</span></span>
18. <span data-ttu-id="5ffad-126">Tapez une valeur dans le champ **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-126">In the **Value** field, type a value.</span></span> <span data-ttu-id="5ffad-127">Par exemple, 033.</span><span class="sxs-lookup"><span data-stu-id="5ffad-127">For example, 033.</span></span>  
19. <span data-ttu-id="5ffad-128">Dans le champ **À**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5ffad-128">In the **through** field, type a value.</span></span> <span data-ttu-id="5ffad-129">Par exemple, 034.</span><span class="sxs-lookup"><span data-stu-id="5ffad-129">For example, 034.</span></span>  
20. <span data-ttu-id="5ffad-130">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-130">Click **Apply**.</span></span>
21. <span data-ttu-id="5ffad-131">Dans la grille, sélectionnez le segment pour modifier les valeurs autorisées.</span><span class="sxs-lookup"><span data-stu-id="5ffad-131">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="5ffad-132">Par exemple, Centre de coût.</span><span class="sxs-lookup"><span data-stu-id="5ffad-132">For example, Cost Center.</span></span>  
22. <span data-ttu-id="5ffad-133">Dans le champ **Centre de coût**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5ffad-133">In the **CostCenter field**, type a value.</span></span> <span data-ttu-id="5ffad-134">Par exemple, 007..021.</span><span class="sxs-lookup"><span data-stu-id="5ffad-134">For example, 007..021.</span></span>  
23. <span data-ttu-id="5ffad-135">Dans **Segments et valeurs autorisées**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-135">In the **Segments and allowed values**, click **Add**.</span></span>
24. <span data-ttu-id="5ffad-136">Tapez une valeur dans le champ **Compte principal**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-136">In the **MainAccount** field, type a value.</span></span> <span data-ttu-id="5ffad-137">Par exemple, 600000..699999</span><span class="sxs-lookup"><span data-stu-id="5ffad-137">For example, 600000..699999</span></span>  
25. <span data-ttu-id="5ffad-138">Dans la grille, sélectionnez le segment pour modifier les valeurs autorisées.</span><span class="sxs-lookup"><span data-stu-id="5ffad-138">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="5ffad-139">Par exemple, Département.</span><span class="sxs-lookup"><span data-stu-id="5ffad-139">For example, Department.</span></span>  
26. <span data-ttu-id="5ffad-140">Dans le champ Département, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5ffad-140">In the Department field, type a value.</span></span> <span data-ttu-id="5ffad-141">Par exemple, 032.</span><span class="sxs-lookup"><span data-stu-id="5ffad-141">For example, 032.</span></span>  
27. <span data-ttu-id="5ffad-142">Dans le champ Centre de coût, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5ffad-142">In the CostCenter field, type a value.</span></span> <span data-ttu-id="5ffad-143">Par exemple, 086.</span><span class="sxs-lookup"><span data-stu-id="5ffad-143">For example, 086.</span></span>  
28. <span data-ttu-id="5ffad-144">Dans le volet **Actions**, cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-144">On the **Action pane**, click **Validate**.</span></span>
29. <span data-ttu-id="5ffad-145">Dans le volet **Actions**, cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-145">On the **Action pane**, click **Activate**.</span></span>
30. <span data-ttu-id="5ffad-146">Cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="5ffad-146">Click **Activate**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]