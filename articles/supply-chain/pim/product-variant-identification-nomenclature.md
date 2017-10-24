---
title: "Nomenclature de numéros et de noms de variante de produit"
description: "Cette rubrique décrit la procédure de paramétrage d'une nomenclature de numéros de produit pour remplacer le format [Numéro du produit générique - Configuration - Taille - Couleur - Style] fixe. La nouvelle nomenclature a un format ciblé qui inclut le numéro du produit générique, les dimensions du produit actif et les séparateurs de texte de votre choix. Vous pouvez également créer une nomenclature pour les noms de produit. Enfin, vous pouvez créer une nomenclature afin d'identifier les configurations créées par le configurateur de produit basé sur les contraintes. Ces nomenclatures peuvent contenir des attributs de votre choix."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 4ebebc1d287908dbe8ac7557c34fc6693c88bfae
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="f11d3-107">Nomenclature de numéros et de noms de variante de produit</span><span class="sxs-lookup"><span data-stu-id="f11d3-107">Nomenclature of product variant numbers and names</span></span>

<span data-ttu-id="f11d3-108">Cette rubrique décrit la procédure de paramétrage d'une nomenclature de numéros de produit pour remplacer le format [Numéro du produit générique - Configuration - Taille - Couleur - Style] fixe.</span><span class="sxs-lookup"><span data-stu-id="f11d3-108">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="f11d3-109">La nouvelle nomenclature a un format ciblé qui inclut le numéro du produit générique, les dimensions du produit actif et les séparateurs de texte de votre choix.</span><span class="sxs-lookup"><span data-stu-id="f11d3-109">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="f11d3-110">Vous pouvez également créer une nomenclature pour les noms de produit.</span><span class="sxs-lookup"><span data-stu-id="f11d3-110">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="f11d3-111">Enfin, vous pouvez créer une nomenclature afin d'identifier les configurations créées par le configurateur de produit basé sur les contraintes.</span><span class="sxs-lookup"><span data-stu-id="f11d3-111">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="f11d3-112">Ces nomenclatures peuvent contenir des attributs de votre choix.</span><span class="sxs-lookup"><span data-stu-id="f11d3-112">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="f11d3-113">Les nouvelles nomenclatures des numéros et des noms de variante de produit vous permettent d'inclure des segments dans les identificateurs des variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="f11d3-113">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="f11d3-114">Ces segments peuvent inclure le numéro et le nom du produit générique, les ID et noms de dimension de produit, les souches de numéros, les constantes de texte et les attributs.</span><span class="sxs-lookup"><span data-stu-id="f11d3-114">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="f11d3-115">Cette fonctionnalité vous permet de rechercher rapidement une variante de produit spécifique lorsque vous créez une commande client ou fournisseur.</span><span class="sxs-lookup"><span data-stu-id="f11d3-115">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="f11d3-116">Vous créez des nomenclatures pour les numéros et les noms de variante de produit à l'aide de la page **Nomenclature de produit**.</span><span class="sxs-lookup"><span data-stu-id="f11d3-116">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="f11d3-117">Pour ouvrir cette page, cliquez sur **Gestion des informations sur les produits** &gt; **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="f11d3-117">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="f11d3-118">Nomenclature de variantes de produit prédéfinies</span><span class="sxs-lookup"><span data-stu-id="f11d3-118">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="f11d3-119">Les variantes de produit sont générées pour les produits génériques selon l'une des trois technologies de configuration suivantes :</span><span class="sxs-lookup"><span data-stu-id="f11d3-119">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="f11d3-120">Variantes prédéfinies</span><span class="sxs-lookup"><span data-stu-id="f11d3-120">Predefined variants</span></span>
-   <span data-ttu-id="f11d3-121">Basé sur les contraintes</span><span class="sxs-lookup"><span data-stu-id="f11d3-121">Constraint-based</span></span>
-   <span data-ttu-id="f11d3-122">Basé sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="f11d3-122">Dimension-based</span></span>

<span data-ttu-id="f11d3-123">Chaque variante de produit dispose d'un numéro et d'un nom, et les nomenclatures d'identification de la variante de produit vous permet de sélectionner les segments qui seront inclus dans chaque numéro ou nom de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="f11d3-123">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="f11d3-124">Vous pouvez sélectionner les segments suivants sur la page **Nomenclature de produit** :</span><span class="sxs-lookup"><span data-stu-id="f11d3-124">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="f11d3-125">Numéro du produit générique</span><span class="sxs-lookup"><span data-stu-id="f11d3-125">Product master number</span></span>
-   <span data-ttu-id="f11d3-126">Nom du produit générique</span><span class="sxs-lookup"><span data-stu-id="f11d3-126">Product master name</span></span>
-   <span data-ttu-id="f11d3-127">Valeur de souche de numéros</span><span class="sxs-lookup"><span data-stu-id="f11d3-127">Number sequence value</span></span>
-   <span data-ttu-id="f11d3-128">Texte constant</span><span class="sxs-lookup"><span data-stu-id="f11d3-128">Text constant</span></span>
-   <span data-ttu-id="f11d3-129">Dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="f11d3-129">Product dimensions</span></span>
    -   <span data-ttu-id="f11d3-130">Nom ou ID configuration</span><span class="sxs-lookup"><span data-stu-id="f11d3-130">Configuration ID or name</span></span>
    -   <span data-ttu-id="f11d3-131">Nom ou ID couleur</span><span class="sxs-lookup"><span data-stu-id="f11d3-131">Color ID or name</span></span>
    -   <span data-ttu-id="f11d3-132">Nom ou ID taille</span><span class="sxs-lookup"><span data-stu-id="f11d3-132">Size ID or name</span></span>
    -   <span data-ttu-id="f11d3-133">Nom ou ID style</span><span class="sxs-lookup"><span data-stu-id="f11d3-133">Style ID or name</span></span>

<span data-ttu-id="f11d3-134">Une fois que vous définissez une nomenclature de numéros d'identification de variante de produit, vous pouvez l'associer à un groupe de dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="f11d3-134">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="f11d3-135">Des numéros de variante de produit sont affectés à tous les produits génériques qui font référence à ce groupe de dimensions de produit en fonction de la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="f11d3-135">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="f11d3-136">Toutefois, les nomenclatures de noms de variante de produit ne peuvent pas être associées à des groupes de dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="f11d3-136">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="f11d3-137">Vous pouvez également affecter une nomenclature d'identification de variante de produit directement à un produit générique.</span><span class="sxs-lookup"><span data-stu-id="f11d3-137">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="f11d3-138">Dans ce cas, des numéros et des noms de variante de produit sont affectés aux variantes de produit qui appartiennent au produit générique en fonction des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="f11d3-138">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="f11d3-139">Exemple</span><span class="sxs-lookup"><span data-stu-id="f11d3-139">Example</span></span>

<span data-ttu-id="f11d3-140">Un T-shirt (TS1234) est produit dans trois tailles (S, M, L), quatre couleurs (rouge, vert, bleu, jaune) et deux styles (polo, col en V).</span><span class="sxs-lookup"><span data-stu-id="f11d3-140">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="f11d3-141">Ainsi, 24 variantes de produit sont possibles (= 3 × 4 x 2).</span><span class="sxs-lookup"><span data-stu-id="f11d3-141">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="f11d3-142">Vous créez une nomenclature de numéros de variante de produit qui comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="f11d3-142">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="f11d3-143">Numéro du produit générique</span><span class="sxs-lookup"><span data-stu-id="f11d3-143">Product master number</span></span>
2.  <span data-ttu-id="f11d3-144">Constante de texte : "-"</span><span class="sxs-lookup"><span data-stu-id="f11d3-144">Text constant: "-"</span></span>
3.  <span data-ttu-id="f11d3-145">Couleur</span><span class="sxs-lookup"><span data-stu-id="f11d3-145">Color</span></span>
4.  <span data-ttu-id="f11d3-146">Constante de texte : "-"</span><span class="sxs-lookup"><span data-stu-id="f11d3-146">Text constant: "-"</span></span>
5.  <span data-ttu-id="f11d3-147">Taille</span><span class="sxs-lookup"><span data-stu-id="f11d3-147">Size</span></span>
6.  <span data-ttu-id="f11d3-148">Constante de texte : "-"</span><span class="sxs-lookup"><span data-stu-id="f11d3-148">Text constant: "-"</span></span>
7.  <span data-ttu-id="f11d3-149">Style</span><span class="sxs-lookup"><span data-stu-id="f11d3-149">Style</span></span>

<span data-ttu-id="f11d3-150">Dans ce cas, le numéro de variante de produit pour un T-shirt polo rouge de taille S sera TS1234-Red-Small-Polo.</span><span class="sxs-lookup"><span data-stu-id="f11d3-150">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraintbased-configurations"></a><span data-ttu-id="f11d3-151">Nomenclature des configurations basées sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="f11d3-151">Nomenclature of constraintbased configurations</span></span>
<span data-ttu-id="f11d3-152">Pour les configurations basées sur les contraintes, vous pouvez créer une nomenclature dédiée pour la dimension de produit de configuration.</span><span class="sxs-lookup"><span data-stu-id="f11d3-152">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="f11d3-153">Vous pouvez sélectionner les segments suivants sur la page **Nomenclature de produit** :</span><span class="sxs-lookup"><span data-stu-id="f11d3-153">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="f11d3-154">Valeur de souche de numéros</span><span class="sxs-lookup"><span data-stu-id="f11d3-154">Number sequence value</span></span>
-   <span data-ttu-id="f11d3-155">Texte constant</span><span class="sxs-lookup"><span data-stu-id="f11d3-155">Text constant</span></span>
-   <span data-ttu-id="f11d3-156">Valeur d'attribut</span><span class="sxs-lookup"><span data-stu-id="f11d3-156">Attribute value</span></span>

<span data-ttu-id="f11d3-157">Chaque composant d'un modèle de configuration de produit peut avoir sa propre nomenclature de configuration.</span><span class="sxs-lookup"><span data-stu-id="f11d3-157">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="f11d3-158">Seuls les attributs appartenant au composant peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="f11d3-158">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="f11d3-159">Les attributs des sous-composants ou des exigences client ne peuvent pas être utilisés.</span><span class="sxs-lookup"><span data-stu-id="f11d3-159">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="f11d3-160">Exemple</span><span class="sxs-lookup"><span data-stu-id="f11d3-160">Example</span></span>

<span data-ttu-id="f11d3-161">Un modèle de configuration de produit dispose d'un composant racine avec deux attributs :</span><span class="sxs-lookup"><span data-stu-id="f11d3-161">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="f11d3-162">Matières (plastique, bois, acier)</span><span class="sxs-lookup"><span data-stu-id="f11d3-162">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="f11d3-163">Longueur (10... 100)</span><span class="sxs-lookup"><span data-stu-id="f11d3-163">Length (10...100)</span></span>

<span data-ttu-id="f11d3-164">Vous créez une nomenclature de configuration qui comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="f11d3-164">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="f11d3-165">Valeur d'attribut : Matières</span><span class="sxs-lookup"><span data-stu-id="f11d3-165">Attribute value: Material</span></span>
2.  <span data-ttu-id="f11d3-166">Constante de texte : "AAA"</span><span class="sxs-lookup"><span data-stu-id="f11d3-166">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="f11d3-167">Valeur d'attribut : Longueur</span><span class="sxs-lookup"><span data-stu-id="f11d3-167">Attribute value: Length</span></span>

<span data-ttu-id="f11d3-168">Dans ce cas, l'ID de configuration des matières en bois avec une longueur de 78 est WoodAAA78.</span><span class="sxs-lookup"><span data-stu-id="f11d3-168">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimensionbased-configurations"></a><span data-ttu-id="f11d3-169">Nomenclature des configurations basées sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="f11d3-169">Nomenclature of dimensionbased configurations</span></span>
<span data-ttu-id="f11d3-170">Pour les configurations basées sur les dimensions, vous pouvez créer une nomenclature dédiée pour la dimension de produit de configuration.</span><span class="sxs-lookup"><span data-stu-id="f11d3-170">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="f11d3-171">Vous pouvez sélectionner les segments suivants sur la page **Nomenclature de produit** :</span><span class="sxs-lookup"><span data-stu-id="f11d3-171">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="f11d3-172">Valeur de souche de numéros</span><span class="sxs-lookup"><span data-stu-id="f11d3-172">Number sequence value</span></span>
-   <span data-ttu-id="f11d3-173">Texte constant</span><span class="sxs-lookup"><span data-stu-id="f11d3-173">Text constant</span></span>
-   <span data-ttu-id="f11d3-174">Article de groupe de configuration</span><span class="sxs-lookup"><span data-stu-id="f11d3-174">Configuration group item</span></span>

<span data-ttu-id="f11d3-175">Vous pouvez définir une nomenclature de configuration pour une nomenclature.</span><span class="sxs-lookup"><span data-stu-id="f11d3-175">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="f11d3-176">Exemple</span><span class="sxs-lookup"><span data-stu-id="f11d3-176">Example</span></span>

<span data-ttu-id="f11d3-177">Une nomenclature comporte quatre lignes de nomenclature qui sont divisées en deux groupes de configuration :</span><span class="sxs-lookup"><span data-stu-id="f11d3-177">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="f11d3-178">Ligne de nomenclature : Meuble standard, M0007</span><span class="sxs-lookup"><span data-stu-id="f11d3-178">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="f11d3-179">Groupe de configurations : Meuble</span><span class="sxs-lookup"><span data-stu-id="f11d3-179">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="f11d3-180">Ligne de nomenclature : M0008, Meuble haut de gamme</span><span class="sxs-lookup"><span data-stu-id="f11d3-180">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="f11d3-181">Groupe de configurations : Meuble</span><span class="sxs-lookup"><span data-stu-id="f11d3-181">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="f11d3-182">Ligne de nomenclature : M0021, tissu de grille avant</span><span class="sxs-lookup"><span data-stu-id="f11d3-182">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="f11d3-183">Groupe de configurations : Grille avant</span><span class="sxs-lookup"><span data-stu-id="f11d3-183">Configuration group: Front grill</span></span>
-   <span data-ttu-id="f11d3-184">Ligne de nomenclature : M0022, métal de grille avant</span><span class="sxs-lookup"><span data-stu-id="f11d3-184">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="f11d3-185">Groupe de configurations : Grille avant</span><span class="sxs-lookup"><span data-stu-id="f11d3-185">Configuration group: Front grill</span></span>

<span data-ttu-id="f11d3-186">Vous créez une nomenclature de configuration qui comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="f11d3-186">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="f11d3-187">Groupe de configurations : Meuble</span><span class="sxs-lookup"><span data-stu-id="f11d3-187">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="f11d3-188">Constante de texte : "&"</span><span class="sxs-lookup"><span data-stu-id="f11d3-188">Text constant: "&"</span></span>
3.  <span data-ttu-id="f11d3-189">Groupe de configurations : Grille avant</span><span class="sxs-lookup"><span data-stu-id="f11d3-189">Configuration group: Front grill</span></span>

<span data-ttu-id="f11d3-190">Dans ce cas, l'ID de configuration d'un meuble standard avec grille avant en tissu est M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="f11d3-190">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="f11d3-191">Nomenclature d'une combinaison de variantes de produit et de configurations</span><span class="sxs-lookup"><span data-stu-id="f11d3-191">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="f11d3-192">Lorsque vous utilisez la technologie de configuration basée sur les contraintes ou basée sur les dimensions pour configurer des variantes de produit pour un produit générique, les numéros des variantes de produit peuvent inclure la nomenclature de la dimension de configuration.</span><span class="sxs-lookup"><span data-stu-id="f11d3-192">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="f11d3-193">Pour configurer les variantes, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f11d3-193">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="f11d3-194">Sur la page **Nomenclature de produit**, définissez une nomenclature de numéros de variante de produit qui contient la dimension de configuration.</span><span class="sxs-lookup"><span data-stu-id="f11d3-194">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="f11d3-195">Affectez la nomenclature à un groupe de dimensions de produit qui inclut la dimension de configuration.</span><span class="sxs-lookup"><span data-stu-id="f11d3-195">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="f11d3-196">Définissez une nomenclature de configuration pour les composants ou les nomenclatures qui seront utilisées pour configurer les variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="f11d3-196">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="f11d3-197">Vous pouvez également créer des nomenclatures pour les noms de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="f11d3-197">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="f11d3-198">Les noms de variante de produit peuvent être configurés pour inclure l'ID ou le nom de configuration.</span><span class="sxs-lookup"><span data-stu-id="f11d3-198">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="f11d3-199">Exemple de configurations basées sur des contraintes</span><span class="sxs-lookup"><span data-stu-id="f11d3-199">Example for constraint-based configurations</span></span>

<span data-ttu-id="f11d3-200">Pour cet exemple, vous pouvez utiliser une nomenclature de numéros de variante de produit qui comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="f11d3-200">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="f11d3-201">Numéro du produit générique</span><span class="sxs-lookup"><span data-stu-id="f11d3-201">Product master number</span></span>
2.  <span data-ttu-id="f11d3-202">Constante de texte : "\_"</span><span class="sxs-lookup"><span data-stu-id="f11d3-202">Text constant "\_"</span></span>
3.  <span data-ttu-id="f11d3-203">Configuration</span><span class="sxs-lookup"><span data-stu-id="f11d3-203">Configuration</span></span>

<span data-ttu-id="f11d3-204">La nomenclature de configuration comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="f11d3-204">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="f11d3-205">Valeur d'attribut : Matières</span><span class="sxs-lookup"><span data-stu-id="f11d3-205">Attribute value: Material</span></span>
2.  <span data-ttu-id="f11d3-206">Constante de texte : "AAA"</span><span class="sxs-lookup"><span data-stu-id="f11d3-206">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="f11d3-207">Valeur d'attribut : Longueur</span><span class="sxs-lookup"><span data-stu-id="f11d3-207">Attribute value: Length</span></span>

<span data-ttu-id="f11d3-208">Entrez les valeurs suivantes pour les segments :</span><span class="sxs-lookup"><span data-stu-id="f11d3-208">You enter the following values for segments:</span></span>

-   <span data-ttu-id="f11d3-209">Numéro du produit générique = **M0099**</span><span class="sxs-lookup"><span data-stu-id="f11d3-209">Product master number = **M0099**</span></span>
-   <span data-ttu-id="f11d3-210">Matières = **Plastique**</span><span class="sxs-lookup"><span data-stu-id="f11d3-210">Material = **Plastic**</span></span>
-   <span data-ttu-id="f11d3-211">Longueur = **12**</span><span class="sxs-lookup"><span data-stu-id="f11d3-211">Length = **12**</span></span>

<span data-ttu-id="f11d3-212">Dans ce cas, le numéro de variante de produit est M0099\_PlasticAAA12.</span><span class="sxs-lookup"><span data-stu-id="f11d3-212">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="f11d3-213">Exemple de configurations basées sur des dimensions</span><span class="sxs-lookup"><span data-stu-id="f11d3-213">Example for dimension-based configurations</span></span>

<span data-ttu-id="f11d3-214">Pour cet exemple, vous pouvez utiliser une nomenclature de numéros de variante de produit qui comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="f11d3-214">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="f11d3-215">Numéro du produit générique</span><span class="sxs-lookup"><span data-stu-id="f11d3-215">Product master number</span></span>
2.  <span data-ttu-id="f11d3-216">Constante de texte : "//"</span><span class="sxs-lookup"><span data-stu-id="f11d3-216">Text constant "//"</span></span>
3.  <span data-ttu-id="f11d3-217">Configuration</span><span class="sxs-lookup"><span data-stu-id="f11d3-217">Configuration</span></span>

<span data-ttu-id="f11d3-218">La nomenclature de configuration comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="f11d3-218">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="f11d3-219">Groupe de configurations : Meuble</span><span class="sxs-lookup"><span data-stu-id="f11d3-219">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="f11d3-220">Constante de texte : "&"</span><span class="sxs-lookup"><span data-stu-id="f11d3-220">Text constant: "&"</span></span>
3.  <span data-ttu-id="f11d3-221">Groupe de configurations : Grille avant</span><span class="sxs-lookup"><span data-stu-id="f11d3-221">Configuration group: Front grill</span></span>

<span data-ttu-id="f11d3-222">Entrez les valeurs suivantes pour les segments :</span><span class="sxs-lookup"><span data-stu-id="f11d3-222">You enter the following values for segments:</span></span>

-   <span data-ttu-id="f11d3-223">Numéro du produit générique = **D0123**</span><span class="sxs-lookup"><span data-stu-id="f11d3-223">Product master number = **D0123**</span></span>
-   <span data-ttu-id="f11d3-224">Meuble = **M0008**</span><span class="sxs-lookup"><span data-stu-id="f11d3-224">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="f11d3-225">Grille avant = **M0022**</span><span class="sxs-lookup"><span data-stu-id="f11d3-225">Front grill = **M0022**</span></span>

<span data-ttu-id="f11d3-226">Dans ce cas, le numéro de variante de produit est D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="f11d3-226">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="f11d3-227">Conflits de numérotation</span><span class="sxs-lookup"><span data-stu-id="f11d3-227">Numbering conflicts</span></span>
<span data-ttu-id="f11d3-228">Dans certains cas, une nomenclature de numéros de variante de produit que vous paramétrez peut ne pas produire des numéros de variante de produit uniques.</span><span class="sxs-lookup"><span data-stu-id="f11d3-228">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="f11d3-229">Par exemple, les numéros de variante de produit ne sont pas uniques si une dimension de produit active n'est pas incluse dans la nomenclature d'un produit générique qui utilise la technologie de configuration de variante prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="f11d3-229">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="f11d3-230">La façon dont vous gérez les conflits varie selon la technologie de configuration.</span><span class="sxs-lookup"><span data-stu-id="f11d3-230">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="f11d3-231">Variantes prédéfinies</span><span class="sxs-lookup"><span data-stu-id="f11d3-231">Predefined variants</span></span>

<span data-ttu-id="f11d3-232">Une erreur se produit si vous essayez de créer manuellement ou de générer automatiquement des variantes de produit, et plusieurs variantes de produit se terminent avec le même numéro de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="f11d3-232">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="f11d3-233">Pour éviter ce scénario, vous devez utiliser toutes les dimensions de produit actives dans le groupe de dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="f11d3-233">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="f11d3-234">Sinon, incluez une souche de numéros pour garantir que les numéros de variante de produit sont uniques.</span><span class="sxs-lookup"><span data-stu-id="f11d3-234">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="f11d3-235">Configurations basées sur les contraintes</span><span class="sxs-lookup"><span data-stu-id="f11d3-235">Constraint-based configurations</span></span>

<span data-ttu-id="f11d3-236">Selon la nomenclature, le système peut tenter d'affecter un numéro de variante de produit non unique à une configuration.</span><span class="sxs-lookup"><span data-stu-id="f11d3-236">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="f11d3-237">Dans ce cas, le système utilise la souche de numéros de la dimension de configuration comme numéro de variante de produit à la place. Vous recevrez alors un avertissement.</span><span class="sxs-lookup"><span data-stu-id="f11d3-237">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="f11d3-238">Pour éviter ce scénario, vous devez inclure assez d'attributs dans la nomenclature pour garantir que les numéros de variable de produit sont uniques.</span><span class="sxs-lookup"><span data-stu-id="f11d3-238">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="f11d3-239">Vous devez également vous assurer que l'option **Réutilisation** est activée pour le composant.</span><span class="sxs-lookup"><span data-stu-id="f11d3-239">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="f11d3-240">Configurations basées sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="f11d3-240">Dimension-based configurations</span></span>

<span data-ttu-id="f11d3-241">Au cours d'une étape du processus de configuration, le système suggère une valeur de configuration selon la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="f11d3-241">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="f11d3-242">À cette étape, vous pouvez modifier manuellement la valeur de la configuration.</span><span class="sxs-lookup"><span data-stu-id="f11d3-242">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="f11d3-243">Lorsque vous enregistrez la configuration, le système vérifie que la valeur de configuration est unique.</span><span class="sxs-lookup"><span data-stu-id="f11d3-243">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="f11d3-244">Si la valeur entrée n'est pas unique, vous recevez un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="f11d3-244">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="f11d3-245">Pour enregistrer la configuration, vous devez entrer une valeur de configuration unique.</span><span class="sxs-lookup"><span data-stu-id="f11d3-245">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="see-also"></a><span data-ttu-id="f11d3-246">Voir également :</span><span class="sxs-lookup"><span data-stu-id="f11d3-246">See also</span></span>
--------

[<span data-ttu-id="f11d3-247">Créer une nomenclature de numéros de produit pour des variantes de produit prédéfinies</span><span class="sxs-lookup"><span data-stu-id="f11d3-247">Create a product number nomenclature for predefined product variants</span></span>](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[<span data-ttu-id="f11d3-248">Créer une nomenclature de numéros de produit pour des variantes de produit configurées</span><span class="sxs-lookup"><span data-stu-id="f11d3-248">Create a product number nomenclature for configured product variants</span></span>](tasks/create-product-number-nomenclature-product-variants_2016_11.md)


