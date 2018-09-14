--- 
title: "Créer un catalogue d'approvisionnement"
description: "Ce guide vous indique comment créer un catalogue d'approvisionnement."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 6f2a010e21f16b3908a6ee5f18d8f144c5130be7
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-procurement-catalog"></a><span data-ttu-id="57357-103">Créer un catalogue d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="57357-103">Create a procurement catalog</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="57357-104">Ce guide vous indique comment créer un catalogue d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="57357-104">This guide shows you how to create a procurement catalog.</span></span> <span data-ttu-id="57357-105">Cette tâche est généralement effectuée par un professionnel de l'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="57357-105">This task would typically be carried out by a procurement professional.</span></span> <span data-ttu-id="57357-106">Vous apprendrez également comment les employés peuvent utiliser le catalogue quand ils créent une demande.</span><span class="sxs-lookup"><span data-stu-id="57357-106">You will also learn how employees can use the catalog when they create a requisition.</span></span> <span data-ttu-id="57357-107">Avant que vous puissiez créer un catalogue, il doit y avoir une hiérarchie des catégories d'approvisionnement dans votre système.</span><span class="sxs-lookup"><span data-stu-id="57357-107">Before you can create a catalog, there must be a procurement category hierarchy in your system.</span></span> <span data-ttu-id="57357-108">La hiérarchie est héritée par le nouveau catalogue, avec tous les produits qui sont dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="57357-108">The hierarchy is inherited by the new catalog, along with all the products that are in the hierarchy.</span></span> <span data-ttu-id="57357-109">Vous pouvez utiliser ce guide dans les données de démonstration de la société USMF où la hiérarchie des catégories d'approvisionnement est disponible, ainsi que les exemples utilisés dans les étapes de procédure.</span><span class="sxs-lookup"><span data-stu-id="57357-109">You can use this guide in demo data company USMF where the procurement category hierarchy is available, as well as the examples used in the procedure steps.</span></span>


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a><span data-ttu-id="57357-110">Assurez-vous qu'une hiérarchie des catégories d'approvisionnement existe</span><span class="sxs-lookup"><span data-stu-id="57357-110">Ensure that a procurement category hierarchy exists</span></span>
1. <span data-ttu-id="57357-111">Accédez à Approvisionnements > Catégories d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="57357-111">Go to Procurement and sourcing > Procurement categories.</span></span>
    * <span data-ttu-id="57357-112">Une hiérarchie de catégories d'approvisionnement est disponible dans la société fictive USMF et les produits ont été ajoutés à la catégorie Équipements de bureau/Ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="57357-112">A procurement category hierarchy is available in the USMF demo data company and products have been added to the Office machines/Computers category.</span></span> <span data-ttu-id="57357-113">Si vous exécutez cette procédure en tant que guide des tâches, vous devrez peut-être déverrouiller le guide pour parcourir la catégorie.</span><span class="sxs-lookup"><span data-stu-id="57357-113">If you’re running this procedure as a task guide, you’ll need to unlock the guide if you want to browse through the category.</span></span> <span data-ttu-id="57357-114">Si une hiérarchie n'est pas disponible, vous devez la créer en cliquant sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="57357-114">If a hierarchy was not available, you’d create it by clicking New.</span></span> <span data-ttu-id="57357-115">Ceci peut seulement être fait une fois.</span><span class="sxs-lookup"><span data-stu-id="57357-115">This can only be done once.</span></span>  
2. <span data-ttu-id="57357-116">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="57357-116">Close the page.</span></span>

## <a name="create-a-catalog"></a><span data-ttu-id="57357-117">Création d'un catalogue</span><span class="sxs-lookup"><span data-stu-id="57357-117">Create a catalog</span></span>
1. <span data-ttu-id="57357-118">Allez dans Approvisionnements > Catalogues > Catalogues d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="57357-118">Go to Procurement and sourcing > Catalogs > Procurement catalogs.</span></span>
2. <span data-ttu-id="57357-119">Cliquez sur Nouveau catalogue d'approvisionnement pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="57357-119">Click New procurement catalog to open the drop dialog.</span></span>
3. <span data-ttu-id="57357-120">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="57357-120">In the Name field, type a value.</span></span>
4. <span data-ttu-id="57357-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57357-121">Click OK.</span></span>
5. <span data-ttu-id="57357-122">Dans l'arborescence, développez « CATÉGORIES D'APPROVISIONNEMENT DE L'ENTREPRISE ».</span><span class="sxs-lookup"><span data-stu-id="57357-122">In the tree, expand 'CORP PROCUREMENT CATEGORIES'.</span></span>
6. <span data-ttu-id="57357-123">Dans l'arborescence, développez ORDINATEURS DE BUREAU.</span><span class="sxs-lookup"><span data-stu-id="57357-123">In the tree, expand 'OFFICE MACHINES'.</span></span>
7. <span data-ttu-id="57357-124">Dans l'arborescence, sélectionnez Ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="57357-124">In the tree, select 'Computers'.</span></span>
    * <span data-ttu-id="57357-125">Les produits du catalogue d'approvisionnement sont affichés dans la liste.</span><span class="sxs-lookup"><span data-stu-id="57357-125">The products from the procurement category are displayed in the list.</span></span> <span data-ttu-id="57357-126">Si vous voulez ajouter un produit à la catégorie vous devez le faire sur la page Hiérarchie des catégories d'approvisionnement ou sur la page Détails de l'article.</span><span class="sxs-lookup"><span data-stu-id="57357-126">If you want to add a product to the category you need to do this on the Procurement category hierarchy page or on the Item details page.</span></span>  
    * <span data-ttu-id="57357-127">Le type de mise à jour de défaut détermine si de nouveaux produits nouveaux qui ont été ajoutés à la hiérarchie des catégories d'approvisionnement sont immédiatement visibles dans le catalogue.</span><span class="sxs-lookup"><span data-stu-id="57357-127">The Default update type determines whether new products that have been added to the procurement category hierarchy are immediately visible in the catalog.</span></span> <span data-ttu-id="57357-128">Si le type de mise à jour est défini sur Dynamique, les changements sont visibles immédiatement.</span><span class="sxs-lookup"><span data-stu-id="57357-128">If the update type is set to Dynamic, changes are visible immediately.</span></span> <span data-ttu-id="57357-129">Si le type de mise à jour est Statique, les nouveaux produits sont seulement visibles pour les utilisateurs employant le catalogue une fois qu'il a été republié.</span><span class="sxs-lookup"><span data-stu-id="57357-129">If the update type is Static, new products are only visible to people using the catalog after the catalog has been re-published.</span></span> <span data-ttu-id="57357-130">L'action Publier est disponible sur le volet Action en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="57357-130">The Publish action is available on the Action Pane at the top of the page.</span></span> <span data-ttu-id="57357-131">Si des produits sont supprimés de la hiérarchie des catégories d'approvisionnement, le changement est immédiatement visible, indépendamment de la valeur du champ Type de mise à jour par défaut.</span><span class="sxs-lookup"><span data-stu-id="57357-131">If products are removed from the procurement category hierarchy, the change is immediately visible, regardless of the value in the Default update type field.</span></span>  
8. <span data-ttu-id="57357-132">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="57357-132">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="57357-133">Cliquez sur Masquer.</span><span class="sxs-lookup"><span data-stu-id="57357-133">Click Hide.</span></span>
10. <span data-ttu-id="57357-134">Dans le volet Action, cliquez sur Navigation de catégorie.</span><span class="sxs-lookup"><span data-stu-id="57357-134">On the Action Pane, click Category navigation.</span></span>
11. <span data-ttu-id="57357-135">Cliquez sur Désactiver.</span><span class="sxs-lookup"><span data-stu-id="57357-135">Click Disable.</span></span>
12. <span data-ttu-id="57357-136">Dans le volet Action, cliquez sur Navigation de catégorie.</span><span class="sxs-lookup"><span data-stu-id="57357-136">On the Action Pane, click Category navigation.</span></span>
13. <span data-ttu-id="57357-137">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="57357-137">Click Enable.</span></span>
14. <span data-ttu-id="57357-138">Cliquez sur Activer le catalogue.</span><span class="sxs-lookup"><span data-stu-id="57357-138">Click Activate catalog.</span></span>
15. <span data-ttu-id="57357-139">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="57357-139">Close the page.</span></span>

## <a name="make-the-catalog-visible"></a><span data-ttu-id="57357-140">Rendre le contrôle visible</span><span class="sxs-lookup"><span data-stu-id="57357-140">Make the catalog visible</span></span>
1. <span data-ttu-id="57357-141">Allez dans Approvisionnements > Paramétrage > Stratégies > Politiques d'achat.</span><span class="sxs-lookup"><span data-stu-id="57357-141">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="57357-142">Choisissez Stratégie d'approvisionnement USMF.</span><span class="sxs-lookup"><span data-stu-id="57357-142">Select Procurement Policy USMF.</span></span>
    * <span data-ttu-id="57357-143">Vous devez choisir la politique d'achat pour l'entité juridique pour laquelle le collaborateur associé à votre profil utilisateur est autorisé à commander des produits.</span><span class="sxs-lookup"><span data-stu-id="57357-143">You need to select the purchasing policy for the legal entity that the worker connected to your user profile is allowed to order products in.</span></span> <span data-ttu-id="57357-144">Dans les données de démonstration de la société fictive USMF, l'utilisateur Admin est relié à la collaboratrice appelée Julia Funderburk, et elle commande des produits dans USMF par défaut.</span><span class="sxs-lookup"><span data-stu-id="57357-144">In the USMF demo data, the Admin user is connected to the worker called Julia Funderburk, and she orders products in USMF by default.</span></span>  
3. <span data-ttu-id="57357-145">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="57357-145">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="57357-146">Sélectionnez le catalogue que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="57357-146">Select the catalog that you’ve just created.</span></span>
5. <span data-ttu-id="57357-147">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57357-147">Click OK.</span></span>
6. <span data-ttu-id="57357-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="57357-148">Close the page.</span></span>
7. <span data-ttu-id="57357-149">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="57357-149">Close the page.</span></span>

## <a name="use-the-catalog"></a><span data-ttu-id="57357-150">Utiliser le catalogue</span><span class="sxs-lookup"><span data-stu-id="57357-150">Use the catalog</span></span>
1. <span data-ttu-id="57357-151">Allez dans Approvisionnement > Demandes d'achat > Toutes les demandes d'achat.</span><span class="sxs-lookup"><span data-stu-id="57357-151">Go to Procurement and sourcing > Purchase requisitions > All purchase requisitions.</span></span>
2. <span data-ttu-id="57357-152">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="57357-152">Click New.</span></span>
3. <span data-ttu-id="57357-153">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="57357-153">In the Name field, type a value.</span></span>
4. <span data-ttu-id="57357-154">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57357-154">Click OK.</span></span>
5. <span data-ttu-id="57357-155">Cliquez sur Ajouter des produits.</span><span class="sxs-lookup"><span data-stu-id="57357-155">Click Add products.</span></span>
6. <span data-ttu-id="57357-156">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="57357-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="57357-157">Vous pouvez utiliser la hiérarchie de catégorie du côté gauche ou le filtre en haut de la liste pour filtrer les produits.</span><span class="sxs-lookup"><span data-stu-id="57357-157">You can use the category hierarchy on the left or the filter at the top of the list to filter the products.</span></span>  
7. <span data-ttu-id="57357-158">Cliquez sur Ajouter aux lignes.</span><span class="sxs-lookup"><span data-stu-id="57357-158">Click Add to lines.</span></span>
8. <span data-ttu-id="57357-159">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="57357-159">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="57357-160">Cliquez sur Ajouter aux lignes.</span><span class="sxs-lookup"><span data-stu-id="57357-160">Click Add to lines.</span></span>
10. <span data-ttu-id="57357-161">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57357-161">Click OK.</span></span>


