--- 
title: "Paramétrer une hiérarchie financière dérivée dans le secteur public"
description: "Pour répondre aux exigences des principales classifications comptables applicables au niveau gouvernemental, les organisations du secteur public peuvent utiliser des hiérarchies financières dérivées afin de recueillir et d'analyser des données de transaction validées pour des numéros de compte principal, des numéros de compte complet et des valeurs de dimension financière spécifiques."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1677d92119704ff2540f706512b383eeaa065ed9
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-a-derived-financial-hierarchy-in-the-public-sector"></a><span data-ttu-id="34fa4-103">Paramétrer une hiérarchie financière dérivée dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="34fa4-103">Set up a derived financial hierarchy in the public sector</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="34fa4-104">Pour répondre aux exigences des principales classifications comptables applicables au niveau gouvernemental, les organisations du secteur public peuvent utiliser des hiérarchies financières dérivées afin de recueillir et d'analyser des données de transaction validées pour des numéros de compte principal, des numéros de compte complet et des valeurs de dimension financière spécifiques.</span><span class="sxs-lookup"><span data-stu-id="34fa4-104">To meet Common Government-wide Accounting Classification (CGAC) requirements, public sector organizations can use derived financial hierarchies to collect and analyze posted transaction data for specific main account numbers, full account numbers, and financial dimension values.</span></span> <span data-ttu-id="34fa4-105">Cette procédure a été créée à l'aide des données de la société fictive PSUS dans la partition du secteur public.</span><span class="sxs-lookup"><span data-stu-id="34fa4-105">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>


## <a name="create-a-category-hierarchy"></a><span data-ttu-id="34fa4-106">Créer une hiérarchie de catégories</span><span class="sxs-lookup"><span data-stu-id="34fa4-106">Create a category hierarchy</span></span>
1. <span data-ttu-id="34fa4-107">Accédez à Gestion des informations sur les produits > Paramétrage > Catégories et d'attributs > Hiérarchies de catégories.</span><span class="sxs-lookup"><span data-stu-id="34fa4-107">Go to Product information management > Setup > Categories and attributes > Category hierarchies.</span></span>
2. <span data-ttu-id="34fa4-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="34fa4-108">Click New.</span></span>
3. <span data-ttu-id="34fa4-109">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="34fa4-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="34fa4-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="34fa4-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="34fa4-111">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="34fa4-111">Click Create.</span></span>
6. <span data-ttu-id="34fa4-112">Cliquez sur Nouveau nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="34fa4-112">Click New category node.</span></span>
7. <span data-ttu-id="34fa4-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="34fa4-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="34fa4-114">Dans le champ Code, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="34fa4-114">In the Code field, type a value.</span></span>
9. <span data-ttu-id="34fa4-115">Cliquez sur Nouveau nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="34fa4-115">Click New category node.</span></span>
10. <span data-ttu-id="34fa4-116">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="34fa4-116">In the Name field, type a value.</span></span>
11. <span data-ttu-id="34fa4-117">Dans le champ Code, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="34fa4-117">In the Code field, type a value.</span></span>
    * <span data-ttu-id="34fa4-118">(Facultatif) Ajoutez des nœuds enfants supplémentaires, ou définissez des options supplémentaires pour les nœuds que vous avez créés.</span><span class="sxs-lookup"><span data-stu-id="34fa4-118">(Optional) Add additional child nodes, or set additional options for the nodes that you have created.</span></span>  
12. <span data-ttu-id="34fa4-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="34fa4-119">Click Save.</span></span>

## <a name="assign-the-derived-financial-hierarchy-category-type"></a><span data-ttu-id="34fa4-120">Affecter le type de catégorie Hiérarchie financière dérivée</span><span class="sxs-lookup"><span data-stu-id="34fa4-120">Assign the Derived financial hierarchy category type</span></span>
1. <span data-ttu-id="34fa4-121">Accédez à Gestion des informations sur les produits > Paramétrage > Catégories et attributs > Associations de rôles de hiérarchie de catégories.</span><span class="sxs-lookup"><span data-stu-id="34fa4-121">Go to Product information management > Setup > Categories and attributes > Category hierarchy role associations.</span></span>
2. <span data-ttu-id="34fa4-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="34fa4-122">Click New.</span></span>
3. <span data-ttu-id="34fa4-123">Dans le champ Type de hiérarchie de catégories, sélectionnez « Hiérarchie financière dérivée ».</span><span class="sxs-lookup"><span data-stu-id="34fa4-123">In the Category hierarchy type field, select 'Derived financial hierarchy'.</span></span>
4. <span data-ttu-id="34fa4-124">Dans le champ Hiérarchie de catégories, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="34fa4-124">In the Category hierarchy field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="34fa4-125">Dans la liste, cliquez sur la hiérarchie de catégories à associer au type Hiérarchie financière dérivée.</span><span class="sxs-lookup"><span data-stu-id="34fa4-125">In the list, click the Category hierarchy to associate with the Derived financial hierarchy type.</span></span>
6. <span data-ttu-id="34fa4-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="34fa4-126">Click Save.</span></span>

## <a name="associate-the-derived-financial-hierarchy-with-a-legal-entity"></a><span data-ttu-id="34fa4-127">Associer la hiérarchie financière dérivée à une entité juridique</span><span class="sxs-lookup"><span data-stu-id="34fa4-127">Associate the derived financial hierarchy with a legal entity</span></span>
1. <span data-ttu-id="34fa4-128">Accédez à Comptabilité > Plan de comptes > Dimensions > Associer des hiérarchies financières.</span><span class="sxs-lookup"><span data-stu-id="34fa4-128">Go to General ledger > Chart of accounts > Dimensions > Associate financial hierarchies.</span></span>
2. <span data-ttu-id="34fa4-129">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="34fa4-129">Click New.</span></span>
3. <span data-ttu-id="34fa4-130">Dans le champ Entité juridique, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="34fa4-130">In the Legal entity field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="34fa4-131">Dans la liste, sélectionnez l'entité juridique à associer à la hiérarchie financière dérivée.</span><span class="sxs-lookup"><span data-stu-id="34fa4-131">In the list, select the legal entity to associate with the derived financial hierarchy.</span></span>
5. <span data-ttu-id="34fa4-132">Dans le champ Hiérarchie financière dérivée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="34fa4-132">In the Derived financial hierarchy field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="34fa4-133">Dans la liste, sélectionnez la hiérarchie financière dérivée à associer à l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="34fa4-133">In the list, select the derived financial hierarchy to associate with the legal entity.</span></span>
7. <span data-ttu-id="34fa4-134">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="34fa4-134">Click Save.</span></span>

## <a name="create-filter-rules-for-the-derived-financial-hierarchy"></a><span data-ttu-id="34fa4-135">Créer des règles de filtre pour la hiérarchie financière dérivée</span><span class="sxs-lookup"><span data-stu-id="34fa4-135">Create filter rules for the derived financial hierarchy</span></span>
1. <span data-ttu-id="34fa4-136">Accédez à Comptabilité > Plan de comptes > Dimensions > Hiérarchies financières dérivées.</span><span class="sxs-lookup"><span data-stu-id="34fa4-136">Go to General ledger > Chart of accounts > Dimensions > Derived financial hierarchies.</span></span>
2. <span data-ttu-id="34fa4-137">Dans le champ Hiérarchie financière dérivée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="34fa4-137">In the Derived financial hierarchy field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="34fa4-138">Dans la liste, cliquez sur la hiérarchie pour laquelle créer des règles de filtre.</span><span class="sxs-lookup"><span data-stu-id="34fa4-138">In the list, click the hierarchy to create filter rules for.</span></span>
4. <span data-ttu-id="34fa4-139">Dans l'arborescence, sélectionnez un nœud enfant.</span><span class="sxs-lookup"><span data-stu-id="34fa4-139">In the tree, select 'In the tree, select a child node.'.</span></span>
5. <span data-ttu-id="34fa4-140">Cliquez sur Modifier le filtre.</span><span class="sxs-lookup"><span data-stu-id="34fa4-140">Click Edit filter.</span></span>
    * <span data-ttu-id="34fa4-141">Cliquez sur Ajouter de nouveaux critères pour commencer à ajouter des règles au filtre.</span><span class="sxs-lookup"><span data-stu-id="34fa4-141">Click Add new criteria to begin adding rules to the filter.</span></span> <span data-ttu-id="34fa4-142">Après avoir ajouté tous les critères, cliquez sur Activer le filtre.</span><span class="sxs-lookup"><span data-stu-id="34fa4-142">After you've added all of the criteria, click Activate filter.</span></span>  


