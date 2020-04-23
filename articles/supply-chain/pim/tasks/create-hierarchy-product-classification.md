---
title: Créer une hiérarchie de classification de produit
description: Cette procédure indique comment créer une nouvelle hiérarchie de catégories et affecter un type de hiérarchie des nomenclatures douanières.
author: ShylaThompson
manager: tfehr
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0ff1a2ba20059d3fcb0347220e6e81130e03ac0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203731"
---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="b54f2-103">Créer une hiérarchie de classification de produit</span><span class="sxs-lookup"><span data-stu-id="b54f2-103">Create a hierarchy of product classification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b54f2-104">Cette procédure indique comment créer une nouvelle hiérarchie de catégories et affecter un type de hiérarchie des nomenclatures douanières.</span><span class="sxs-lookup"><span data-stu-id="b54f2-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="b54f2-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="b54f2-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="b54f2-106">Cette procédure est destinée au gestionnaire de catégories.</span><span class="sxs-lookup"><span data-stu-id="b54f2-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="b54f2-107">Créer la nouvelle hiérarchie de catégories</span><span class="sxs-lookup"><span data-stu-id="b54f2-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="b54f2-108">Accédez à **Volet de navigation > Modules > Gestion des informations sur les produits > Configuration > Catégories et attributs > Hiérarchies de catégories**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-108">Go to **Navigation pane > Modules > Product information management > Setup > Categories and attributes > Category hierarchies**.</span></span>
2. <span data-ttu-id="b54f2-109">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-109">Click **New**.</span></span>
3. <span data-ttu-id="b54f2-110">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="b54f2-111">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="b54f2-112">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-112">Click **Create**.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="b54f2-113">Créer la hiérarchie</span><span class="sxs-lookup"><span data-stu-id="b54f2-113">Build the hierarchy</span></span>
1. <span data-ttu-id="b54f2-114">Cliquez sur **Nouveau** nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="b54f2-114">Click **New** category node.</span></span>
2. <span data-ttu-id="b54f2-115">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-115">In the **Name** field, type a value.</span></span>
3. <span data-ttu-id="b54f2-116">Dans le champ **Code**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b54f2-116">In the **Code** field, type a value.</span></span>
4. <span data-ttu-id="b54f2-117">Dans le champ **Nom convivial**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b54f2-117">In the **Friendly name** field, type a value.</span></span>
5. <span data-ttu-id="b54f2-118">Cliquez sur **Nouveau** nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="b54f2-118">Click **New** category node.</span></span>
6. <span data-ttu-id="b54f2-119">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-119">In the **Name** field, type a value.</span></span>
7. <span data-ttu-id="b54f2-120">Dans le champ **Code**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b54f2-120">In the **Code** field, type a value.</span></span>
8. <span data-ttu-id="b54f2-121">Dans le champ **Nom convivial**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b54f2-121">In the **Friendly name** field, type a value.</span></span>
9. <span data-ttu-id="b54f2-122">Cliquez sur **Nouveau** nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="b54f2-122">Click **New** category node.</span></span>
10. <span data-ttu-id="b54f2-123">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-123">In the **Name** field, type a value.</span></span>
11. <span data-ttu-id="b54f2-124">Dans le champ **Code**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b54f2-124">In the **Code** field, type a value.</span></span>
12. <span data-ttu-id="b54f2-125">Dans le champ **Nom convivial**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b54f2-125">In the **Friendly name** field, type a value.</span></span>
13. <span data-ttu-id="b54f2-126">Cliquez sur **Nouveau** nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="b54f2-126">Click **New** category node.</span></span>
14. <span data-ttu-id="b54f2-127">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-127">In the **Name** field, type a value.</span></span>
15. <span data-ttu-id="b54f2-128">Dans le champ **Code**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b54f2-128">In the **Code** field, type a value.</span></span>
16. <span data-ttu-id="b54f2-129">Dans le champ **Nom convivial**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b54f2-129">In the **Friendly name** field, type a value.</span></span>
17. <span data-ttu-id="b54f2-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b54f2-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="b54f2-131">Classifier la hiérarchie</span><span class="sxs-lookup"><span data-stu-id="b54f2-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="b54f2-132">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b54f2-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="b54f2-133">Dans le **volet Actions**, cliquez sur **Hiérarchie de catégories**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-133">On the **Action Pane**, click **Category hierarchy**.</span></span>
3. <span data-ttu-id="b54f2-134">Cliquez sur **Associer le type de hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-134">Click **Associate hierarchy type**.</span></span>
4. <span data-ttu-id="b54f2-135">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-135">Click **New**.</span></span>
5. <span data-ttu-id="b54f2-136">Dans le champ **Type de hiérarchie de catégories**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="b54f2-136">In the **Category hierarchy type** field, select an option.</span></span> <span data-ttu-id="b54f2-137">Sélectionnez le **type de hiérarchie de catégories des nomenclatures douanières pour la classification de produit**.</span><span class="sxs-lookup"><span data-stu-id="b54f2-137">Select the **Commodity code category hierarchy type for product classification**.</span></span>  
6. <span data-ttu-id="b54f2-138">Dans le champ **Hiérarchie de catégories**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="b54f2-138">In the **Category hierarchy** field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="b54f2-139">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b54f2-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="b54f2-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b54f2-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="b54f2-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b54f2-141">Close the page.</span></span>

