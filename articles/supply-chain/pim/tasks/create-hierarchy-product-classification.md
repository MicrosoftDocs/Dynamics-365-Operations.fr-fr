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
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole, EcoResProductCategory, EcoResCategorySearchList, EcoResCategoryHierarchyFactbox, EcoResCategoryFriendlyName, EcoResCategoryAddProduct
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 59631148dbd2ad27ce2bb5c268d78e625daef6bb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224449"
---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="bb672-103">Créer une hiérarchie de classification de produit</span><span class="sxs-lookup"><span data-stu-id="bb672-103">Create a hierarchy of product classification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bb672-104">Cette procédure indique comment créer une nouvelle hiérarchie de catégories et affecter un type de hiérarchie des nomenclatures douanières.</span><span class="sxs-lookup"><span data-stu-id="bb672-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="bb672-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="bb672-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="bb672-106">Cette procédure est destinée au gestionnaire de catégories.</span><span class="sxs-lookup"><span data-stu-id="bb672-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="bb672-107">Créer la nouvelle hiérarchie de catégories</span><span class="sxs-lookup"><span data-stu-id="bb672-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="bb672-108">Accédez à **Volet de navigation > Modules > Gestion des informations sur les produits > Configuration > Catégories et attributs > Hiérarchies de catégories**.</span><span class="sxs-lookup"><span data-stu-id="bb672-108">Go to **Navigation pane > Modules > Product information management > Setup > Categories and attributes > Category hierarchies**.</span></span>
2. <span data-ttu-id="bb672-109">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bb672-109">Click **New**.</span></span>
3. <span data-ttu-id="bb672-110">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="bb672-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="bb672-111">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="bb672-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="bb672-112">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="bb672-112">Click **Create**.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="bb672-113">Créer la hiérarchie</span><span class="sxs-lookup"><span data-stu-id="bb672-113">Build the hierarchy</span></span>
1. <span data-ttu-id="bb672-114">Cliquez sur **Nouveau** nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="bb672-114">Click **New** category node.</span></span>
2. <span data-ttu-id="bb672-115">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="bb672-115">In the **Name** field, type a value.</span></span>
3. <span data-ttu-id="bb672-116">Dans le champ **Code**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bb672-116">In the **Code** field, type a value.</span></span>
4. <span data-ttu-id="bb672-117">Dans le champ **Nom convivial**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bb672-117">In the **Friendly name** field, type a value.</span></span>
5. <span data-ttu-id="bb672-118">Cliquez sur **Nouveau** nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="bb672-118">Click **New** category node.</span></span>
6. <span data-ttu-id="bb672-119">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="bb672-119">In the **Name** field, type a value.</span></span>
7. <span data-ttu-id="bb672-120">Dans le champ **Code**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bb672-120">In the **Code** field, type a value.</span></span>
8. <span data-ttu-id="bb672-121">Dans le champ **Nom convivial**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bb672-121">In the **Friendly name** field, type a value.</span></span>
9. <span data-ttu-id="bb672-122">Cliquez sur **Nouveau** nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="bb672-122">Click **New** category node.</span></span>
10. <span data-ttu-id="bb672-123">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="bb672-123">In the **Name** field, type a value.</span></span>
11. <span data-ttu-id="bb672-124">Dans le champ **Code**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bb672-124">In the **Code** field, type a value.</span></span>
12. <span data-ttu-id="bb672-125">Dans le champ **Nom convivial**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bb672-125">In the **Friendly name** field, type a value.</span></span>
13. <span data-ttu-id="bb672-126">Cliquez sur **Nouveau** nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="bb672-126">Click **New** category node.</span></span>
14. <span data-ttu-id="bb672-127">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="bb672-127">In the **Name** field, type a value.</span></span>
15. <span data-ttu-id="bb672-128">Dans le champ **Code**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bb672-128">In the **Code** field, type a value.</span></span>
16. <span data-ttu-id="bb672-129">Dans le champ **Nom convivial**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bb672-129">In the **Friendly name** field, type a value.</span></span>
17. <span data-ttu-id="bb672-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bb672-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="bb672-131">Classifier la hiérarchie</span><span class="sxs-lookup"><span data-stu-id="bb672-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="bb672-132">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="bb672-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="bb672-133">Dans le **volet Actions**, cliquez sur **Hiérarchie de catégories**.</span><span class="sxs-lookup"><span data-stu-id="bb672-133">On the **Action Pane**, click **Category hierarchy**.</span></span>
3. <span data-ttu-id="bb672-134">Cliquez sur **Associer le type de hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="bb672-134">Click **Associate hierarchy type**.</span></span>
4. <span data-ttu-id="bb672-135">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bb672-135">Click **New**.</span></span>
5. <span data-ttu-id="bb672-136">Dans le champ **Type de hiérarchie de catégories**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="bb672-136">In the **Category hierarchy type** field, select an option.</span></span> <span data-ttu-id="bb672-137">Sélectionnez le **type de hiérarchie de catégories des nomenclatures douanières pour la classification de produit**.</span><span class="sxs-lookup"><span data-stu-id="bb672-137">Select the **Commodity code category hierarchy type for product classification**.</span></span>  
6. <span data-ttu-id="bb672-138">Dans le champ **Hiérarchie de catégories**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="bb672-138">In the **Category hierarchy** field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="bb672-139">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="bb672-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="bb672-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bb672-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="bb672-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bb672-141">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]