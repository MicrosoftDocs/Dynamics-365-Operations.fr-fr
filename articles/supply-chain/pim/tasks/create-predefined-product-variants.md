--- 
title: "Créer des variantes de produits prédéfinies"
description: "Cette procédure décrit la création des variantes de produit pour un produit générique à l'aide des combinaisons de dimensions de produit."
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c49d25004b19084276404cf887188e89200afa32
ms.contentlocale: fr-fr
ms.lasthandoff: 11/08/2017

---
# <a name="create-predefined-product-variants"></a><span data-ttu-id="e9d68-103">Créer des variantes de produits prédéfinies</span><span class="sxs-lookup"><span data-stu-id="e9d68-103">Create predefined product variants</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e9d68-104">Cette procédure décrit la création des variantes de produit pour un produit générique à l'aide des combinaisons de dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="e9d68-104">This procedure walks through creating product variants for a product master using the combinations of product dimensions.</span></span> <span data-ttu-id="e9d68-105">La société fictive de démonstration utilisée pour créer cette procédure est USMF.</span><span class="sxs-lookup"><span data-stu-id="e9d68-105">The demo company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-master"></a><span data-ttu-id="e9d68-106">Créer un produit générique</span><span class="sxs-lookup"><span data-stu-id="e9d68-106">Create a product master</span></span>
1. <span data-ttu-id="e9d68-107">Accédez à Gestion des informations sur les produits > Produits > Produits génériques.</span><span class="sxs-lookup"><span data-stu-id="e9d68-107">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="e9d68-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e9d68-108">Click New.</span></span>
3. <span data-ttu-id="e9d68-109">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e9d68-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="e9d68-110">La saisie manuelle d'un numéro de produit est obligatoire uniquement si aucune souche de numéros n'a été paramétrée pour le champ du numéro de produit.</span><span class="sxs-lookup"><span data-stu-id="e9d68-110">Entering a product number manually is only required if no number sequence has been set for the product number field.</span></span> <span data-ttu-id="e9d68-111">Autrement dit, ignorez l'étape si la souche de numéros a été définie pour le champ.</span><span class="sxs-lookup"><span data-stu-id="e9d68-111">In other words, skip the step if number sequence has been set for the field.</span></span>  
4. <span data-ttu-id="e9d68-112">Dans le champ Nom du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e9d68-112">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="e9d68-113">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="e9d68-113">In the Product dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e9d68-114">Sélectionnez le groupe de dimensions de produit SizeCol (taille et couleur).</span><span class="sxs-lookup"><span data-stu-id="e9d68-114">Select the product dimension group SizeCol (Size and Color).</span></span>  
6. <span data-ttu-id="e9d68-115">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e9d68-115">Click OK.</span></span>

## <a name="add-product-dimensions"></a><span data-ttu-id="e9d68-116">Ajouter des dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="e9d68-116">Add product dimensions</span></span>
1. <span data-ttu-id="e9d68-117">Cliquez sur Dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="e9d68-117">Click Product dimensions.</span></span>
    * <span data-ttu-id="e9d68-118">Cet exemple décrit la manière d'entrer manuellement les dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="e9d68-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="e9d68-119">Vous pouvez également choisir de sélectionner un groupe de tailles, de couleurs ou de styles incluant les valeurs de dimension de produit à utiliser.</span><span class="sxs-lookup"><span data-stu-id="e9d68-119">You can also choose to select a size, color or style group that includes the product dimension values you want to use.</span></span>  
2. <span data-ttu-id="e9d68-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e9d68-120">Click New.</span></span>
3. <span data-ttu-id="e9d68-121">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e9d68-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="e9d68-122">Saisissez ou sélectionnez une valeur dans le champ Taille.</span><span class="sxs-lookup"><span data-stu-id="e9d68-122">In the Size field, enter or select a value.</span></span>
5. <span data-ttu-id="e9d68-123">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e9d68-123">In the Name field, type a value.</span></span>
6. <span data-ttu-id="e9d68-124">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e9d68-124">Click New.</span></span>
7. <span data-ttu-id="e9d68-125">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e9d68-125">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="e9d68-126">Saisissez ou sélectionnez une valeur dans le champ Taille.</span><span class="sxs-lookup"><span data-stu-id="e9d68-126">In the Size field, enter or select a value.</span></span>
9. <span data-ttu-id="e9d68-127">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e9d68-127">In the Name field, type a value.</span></span>
10. <span data-ttu-id="e9d68-128">Cliquez sur l'onglet Couleurs.</span><span class="sxs-lookup"><span data-stu-id="e9d68-128">Click the Colors tab.</span></span>
11. <span data-ttu-id="e9d68-129">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e9d68-129">Click New.</span></span>
12. <span data-ttu-id="e9d68-130">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e9d68-130">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="e9d68-131">Dans le champ Couleur, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e9d68-131">In the Color field, enter or select a value.</span></span>
14. <span data-ttu-id="e9d68-132">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e9d68-132">In the Name field, type a value.</span></span>
15. <span data-ttu-id="e9d68-133">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e9d68-133">Click New.</span></span>
16. <span data-ttu-id="e9d68-134">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e9d68-134">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="e9d68-135">Dans le champ Couleur, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e9d68-135">In the Color field, enter or select a value.</span></span>
18. <span data-ttu-id="e9d68-136">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e9d68-136">In the Name field, type a value.</span></span>
19. <span data-ttu-id="e9d68-137">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e9d68-137">Click Save.</span></span>
20. <span data-ttu-id="e9d68-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e9d68-138">Close the page.</span></span>

## <a name="generate-product-variants"></a><span data-ttu-id="e9d68-139">Générer des variantes de produits</span><span class="sxs-lookup"><span data-stu-id="e9d68-139">Generate product variants</span></span>
1. <span data-ttu-id="e9d68-140">Cliquez sur Variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="e9d68-140">Click Product variants.</span></span>
2. <span data-ttu-id="e9d68-141">Cliquez sur Suggestions de variante.</span><span class="sxs-lookup"><span data-stu-id="e9d68-141">Click Variant suggestions.</span></span>
3. <span data-ttu-id="e9d68-142">Cliquez sur Sélectionner tout.</span><span class="sxs-lookup"><span data-stu-id="e9d68-142">Click Select all.</span></span>
    * <span data-ttu-id="e9d68-143">Dans cet exemple, toutes les variantes possibles sont sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="e9d68-143">In this example, all possible variants are selected.</span></span> <span data-ttu-id="e9d68-144">Si un seul sous-ensemble des combinaisons possibles de dimension de produit sera utilisé pour créer des variantes, vous pouvez sélectionner les entrées individuelles.</span><span class="sxs-lookup"><span data-stu-id="e9d68-144">If only a subset of the possible product dimension combinations will be used to create variants, you can select the individual entries.</span></span>  
4. <span data-ttu-id="e9d68-145">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="e9d68-145">Click Create.</span></span>
    * <span data-ttu-id="e9d68-146">Vous pouvez générer des descriptions pour toutes les variantes selon la combinaison des valeurs de dimension de produit.</span><span class="sxs-lookup"><span data-stu-id="e9d68-146">You can generate descriptions for all your variants based on the combination of product dimension values.</span></span> <span data-ttu-id="e9d68-147">La description est facultative.</span><span class="sxs-lookup"><span data-stu-id="e9d68-147">The descriptions are optional.</span></span>  
5. <span data-ttu-id="e9d68-148">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e9d68-148">Click Save.</span></span>

