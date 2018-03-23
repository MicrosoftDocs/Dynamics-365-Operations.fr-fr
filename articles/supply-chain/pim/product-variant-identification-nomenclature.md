---
title: "Nomenclature de numéros et de noms de variante de produit"
description: "Cette rubrique décrit la procédure de paramétrage d'une nomenclature de numéros de produit pour remplacer le format [Numéro du produit générique - Configuration - Taille - Couleur - Style] fixe."
author: roxanadiaconu
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 6a620f2a0105d578d419d3aac816c7d78fbf3e46
ms.contentlocale: fr-fr
ms.lasthandoff: 03/07/2018

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="264de-103">Nomenclature de numéros et de noms de variante de produit</span><span class="sxs-lookup"><span data-stu-id="264de-103">Nomenclature of product variant numbers and names</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="264de-104">Cette rubrique décrit la procédure de paramétrage d'une nomenclature de numéros de produit pour remplacer le format [Numéro du produit générique - Configuration - Taille - Couleur - Style] fixe.</span><span class="sxs-lookup"><span data-stu-id="264de-104">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="264de-105">La nouvelle nomenclature a un format ciblé qui inclut le numéro du produit générique, les dimensions du produit actif et les séparateurs de texte de votre choix.</span><span class="sxs-lookup"><span data-stu-id="264de-105">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="264de-106">Vous pouvez également créer une nomenclature pour les noms de produit.</span><span class="sxs-lookup"><span data-stu-id="264de-106">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="264de-107">Enfin, vous pouvez créer une nomenclature afin d'identifier les configurations créées par le configurateur de produit basé sur les contraintes.</span><span class="sxs-lookup"><span data-stu-id="264de-107">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="264de-108">Ces nomenclatures peuvent contenir des attributs de votre choix.</span><span class="sxs-lookup"><span data-stu-id="264de-108">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="264de-109">Les nouvelles nomenclatures des numéros et des noms de variante de produit vous permettent d'inclure des segments dans les identificateurs des variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="264de-109">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="264de-110">Ces segments peuvent inclure le numéro et le nom du produit générique, les ID et noms de dimension de produit, les souches de numéros, les constantes de texte et les attributs.</span><span class="sxs-lookup"><span data-stu-id="264de-110">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="264de-111">Cette fonctionnalité vous permet de rechercher rapidement une variante de produit spécifique lorsque vous créez une commande client ou fournisseur.</span><span class="sxs-lookup"><span data-stu-id="264de-111">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="264de-112">Vous créez des nomenclatures pour les numéros et les noms de variante de produit à l'aide de la page **Nomenclature de produit**.</span><span class="sxs-lookup"><span data-stu-id="264de-112">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="264de-113">Pour ouvrir cette page, cliquez sur **Gestion des informations sur les produits** &gt; **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="264de-113">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="264de-114">Nomenclature de variantes de produit prédéfinies</span><span class="sxs-lookup"><span data-stu-id="264de-114">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="264de-115">Les variantes de produit sont générées pour les produits génériques selon l'une des trois technologies de configuration suivantes :</span><span class="sxs-lookup"><span data-stu-id="264de-115">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="264de-116">Variantes prédéfinies</span><span class="sxs-lookup"><span data-stu-id="264de-116">Predefined variants</span></span>
-   <span data-ttu-id="264de-117">Basé sur les contraintes</span><span class="sxs-lookup"><span data-stu-id="264de-117">Constraint-based</span></span>
-   <span data-ttu-id="264de-118">Basé sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="264de-118">Dimension-based</span></span>

<span data-ttu-id="264de-119">Chaque variante de produit dispose d'un numéro et d'un nom, et les nomenclatures d'identification de la variante de produit vous permet de sélectionner les segments qui seront inclus dans chaque numéro ou nom de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="264de-119">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="264de-120">Vous pouvez sélectionner les segments suivants sur la page **Nomenclature de produit** :</span><span class="sxs-lookup"><span data-stu-id="264de-120">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="264de-121">Numéro du produit générique</span><span class="sxs-lookup"><span data-stu-id="264de-121">Product master number</span></span>
-   <span data-ttu-id="264de-122">Nom du produit générique</span><span class="sxs-lookup"><span data-stu-id="264de-122">Product master name</span></span>
-   <span data-ttu-id="264de-123">Valeur de souche de numéros</span><span class="sxs-lookup"><span data-stu-id="264de-123">Number sequence value</span></span>
-   <span data-ttu-id="264de-124">Texte constant</span><span class="sxs-lookup"><span data-stu-id="264de-124">Text constant</span></span>
-   <span data-ttu-id="264de-125">Dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="264de-125">Product dimensions</span></span>
    -   <span data-ttu-id="264de-126">Nom ou ID configuration</span><span class="sxs-lookup"><span data-stu-id="264de-126">Configuration ID or name</span></span>
    -   <span data-ttu-id="264de-127">Nom ou ID couleur</span><span class="sxs-lookup"><span data-stu-id="264de-127">Color ID or name</span></span>
    -   <span data-ttu-id="264de-128">Nom ou ID taille</span><span class="sxs-lookup"><span data-stu-id="264de-128">Size ID or name</span></span>
    -   <span data-ttu-id="264de-129">Nom ou ID style</span><span class="sxs-lookup"><span data-stu-id="264de-129">Style ID or name</span></span>

<span data-ttu-id="264de-130">Une fois que vous définissez une nomenclature de numéros d'identification de variante de produit, vous pouvez l'associer à un groupe de dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="264de-130">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="264de-131">Des numéros de variante de produit sont affectés à tous les produits génériques qui font référence à ce groupe de dimensions de produit en fonction de la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="264de-131">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="264de-132">Toutefois, les nomenclatures de noms de variante de produit ne peuvent pas être associées à des groupes de dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="264de-132">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="264de-133">Vous pouvez également affecter une nomenclature d'identification de variante de produit directement à un produit générique.</span><span class="sxs-lookup"><span data-stu-id="264de-133">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="264de-134">Dans ce cas, des numéros et des noms de variante de produit sont affectés aux variantes de produit qui appartiennent au produit générique en fonction des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="264de-134">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="264de-135">Exemple</span><span class="sxs-lookup"><span data-stu-id="264de-135">Example</span></span>

<span data-ttu-id="264de-136">Un T-shirt (TS1234) est produit dans trois tailles (S, M, L), quatre couleurs (rouge, vert, bleu, jaune) et deux styles (polo, col en V).</span><span class="sxs-lookup"><span data-stu-id="264de-136">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="264de-137">Ainsi, 24 variantes de produit sont possibles (= 3 × 4 x 2).</span><span class="sxs-lookup"><span data-stu-id="264de-137">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="264de-138">Vous créez une nomenclature de numéros de variante de produit qui comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="264de-138">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="264de-139">Numéro du produit générique</span><span class="sxs-lookup"><span data-stu-id="264de-139">Product master number</span></span>
2.  <span data-ttu-id="264de-140">Constante de texte : "-"</span><span class="sxs-lookup"><span data-stu-id="264de-140">Text constant: "-"</span></span>
3.  <span data-ttu-id="264de-141">Couleur</span><span class="sxs-lookup"><span data-stu-id="264de-141">Color</span></span>
4.  <span data-ttu-id="264de-142">Constante de texte : "-"</span><span class="sxs-lookup"><span data-stu-id="264de-142">Text constant: "-"</span></span>
5.  <span data-ttu-id="264de-143">Taille</span><span class="sxs-lookup"><span data-stu-id="264de-143">Size</span></span>
6.  <span data-ttu-id="264de-144">Constante de texte : "-"</span><span class="sxs-lookup"><span data-stu-id="264de-144">Text constant: "-"</span></span>
7.  <span data-ttu-id="264de-145">Style</span><span class="sxs-lookup"><span data-stu-id="264de-145">Style</span></span>

<span data-ttu-id="264de-146">Dans ce cas, le numéro de variante de produit pour un T-shirt polo rouge de taille S sera TS1234-Red-Small-Polo.</span><span class="sxs-lookup"><span data-stu-id="264de-146">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraint-based-configurations"></a><span data-ttu-id="264de-147">Nomenclature des configurations basées sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="264de-147">Nomenclature of constraint-based configurations</span></span>
<span data-ttu-id="264de-148">Pour les configurations basées sur les contraintes, vous pouvez créer une nomenclature dédiée pour la dimension de produit de configuration.</span><span class="sxs-lookup"><span data-stu-id="264de-148">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="264de-149">Vous pouvez sélectionner les segments suivants sur la page **Nomenclature de produit** :</span><span class="sxs-lookup"><span data-stu-id="264de-149">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="264de-150">Valeur de souche de numéros</span><span class="sxs-lookup"><span data-stu-id="264de-150">Number sequence value</span></span>
-   <span data-ttu-id="264de-151">Texte constant</span><span class="sxs-lookup"><span data-stu-id="264de-151">Text constant</span></span>
-   <span data-ttu-id="264de-152">Valeur d'attribut</span><span class="sxs-lookup"><span data-stu-id="264de-152">Attribute value</span></span>

<span data-ttu-id="264de-153">Chaque composant d'un modèle de configuration de produit peut avoir sa propre nomenclature de configuration.</span><span class="sxs-lookup"><span data-stu-id="264de-153">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="264de-154">Seuls les attributs appartenant au composant peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="264de-154">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="264de-155">Les attributs des sous-composants ou des exigences client ne peuvent pas être utilisés.</span><span class="sxs-lookup"><span data-stu-id="264de-155">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="264de-156">Exemple</span><span class="sxs-lookup"><span data-stu-id="264de-156">Example</span></span>

<span data-ttu-id="264de-157">Un modèle de configuration de produit dispose d'un composant racine avec deux attributs :</span><span class="sxs-lookup"><span data-stu-id="264de-157">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="264de-158">Matières (plastique, bois, acier)</span><span class="sxs-lookup"><span data-stu-id="264de-158">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="264de-159">Longueur (10... 100)</span><span class="sxs-lookup"><span data-stu-id="264de-159">Length (10...100)</span></span>

<span data-ttu-id="264de-160">Vous créez une nomenclature de configuration qui comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="264de-160">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="264de-161">Valeur d'attribut : Matières</span><span class="sxs-lookup"><span data-stu-id="264de-161">Attribute value: Material</span></span>
2.  <span data-ttu-id="264de-162">Constante de texte : "AAA"</span><span class="sxs-lookup"><span data-stu-id="264de-162">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="264de-163">Valeur d'attribut : Longueur</span><span class="sxs-lookup"><span data-stu-id="264de-163">Attribute value: Length</span></span>

<span data-ttu-id="264de-164">Dans ce cas, l'ID de configuration des matières en bois avec une longueur de 78 est WoodAAA78.</span><span class="sxs-lookup"><span data-stu-id="264de-164">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimension-based-configurations"></a><span data-ttu-id="264de-165">Nomenclature des configurations basées sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="264de-165">Nomenclature of dimension-based configurations</span></span>
<span data-ttu-id="264de-166">Pour les configurations basées sur les dimensions, vous pouvez créer une nomenclature dédiée pour la dimension de produit de configuration.</span><span class="sxs-lookup"><span data-stu-id="264de-166">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="264de-167">Vous pouvez sélectionner les segments suivants sur la page **Nomenclature de produit** :</span><span class="sxs-lookup"><span data-stu-id="264de-167">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="264de-168">Valeur de souche de numéros</span><span class="sxs-lookup"><span data-stu-id="264de-168">Number sequence value</span></span>
-   <span data-ttu-id="264de-169">Texte constant</span><span class="sxs-lookup"><span data-stu-id="264de-169">Text constant</span></span>
-   <span data-ttu-id="264de-170">Article de groupe de configuration</span><span class="sxs-lookup"><span data-stu-id="264de-170">Configuration group item</span></span>

<span data-ttu-id="264de-171">Vous pouvez définir une nomenclature de configuration pour une nomenclature.</span><span class="sxs-lookup"><span data-stu-id="264de-171">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="264de-172">Exemple</span><span class="sxs-lookup"><span data-stu-id="264de-172">Example</span></span>

<span data-ttu-id="264de-173">Une nomenclature comporte quatre lignes de nomenclature qui sont divisées en deux groupes de configuration :</span><span class="sxs-lookup"><span data-stu-id="264de-173">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="264de-174">Ligne de nomenclature : Meuble standard, M0007</span><span class="sxs-lookup"><span data-stu-id="264de-174">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="264de-175">Groupe de configurations : Meuble</span><span class="sxs-lookup"><span data-stu-id="264de-175">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="264de-176">Ligne de nomenclature : M0008, Meuble haut de gamme</span><span class="sxs-lookup"><span data-stu-id="264de-176">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="264de-177">Groupe de configurations : Meuble</span><span class="sxs-lookup"><span data-stu-id="264de-177">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="264de-178">Ligne de nomenclature : M0021, tissu de grille avant</span><span class="sxs-lookup"><span data-stu-id="264de-178">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="264de-179">Groupe de configurations : Grille avant</span><span class="sxs-lookup"><span data-stu-id="264de-179">Configuration group: Front grill</span></span>
-   <span data-ttu-id="264de-180">Ligne de nomenclature : M0022, métal de grille avant</span><span class="sxs-lookup"><span data-stu-id="264de-180">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="264de-181">Groupe de configurations : Grille avant</span><span class="sxs-lookup"><span data-stu-id="264de-181">Configuration group: Front grill</span></span>

<span data-ttu-id="264de-182">Vous créez une nomenclature de configuration qui comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="264de-182">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="264de-183">Groupe de configurations : Meuble</span><span class="sxs-lookup"><span data-stu-id="264de-183">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="264de-184">Constante de texte : "&"</span><span class="sxs-lookup"><span data-stu-id="264de-184">Text constant: "&"</span></span>
3.  <span data-ttu-id="264de-185">Groupe de configurations : Grille avant</span><span class="sxs-lookup"><span data-stu-id="264de-185">Configuration group: Front grill</span></span>

<span data-ttu-id="264de-186">Dans ce cas, l'ID de configuration d'un meuble standard avec grille avant en tissu est M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="264de-186">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="264de-187">Nomenclature d'une combinaison de variantes de produit et de configurations</span><span class="sxs-lookup"><span data-stu-id="264de-187">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="264de-188">Lorsque vous utilisez la technologie de configuration basée sur les contraintes ou basée sur les dimensions pour configurer des variantes de produit pour un produit générique, les numéros des variantes de produit peuvent inclure la nomenclature de la dimension de configuration.</span><span class="sxs-lookup"><span data-stu-id="264de-188">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="264de-189">Pour configurer les variantes, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="264de-189">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="264de-190">Sur la page **Nomenclature de produit**, définissez une nomenclature de numéros de variante de produit qui contient la dimension de configuration.</span><span class="sxs-lookup"><span data-stu-id="264de-190">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="264de-191">Affectez la nomenclature à un groupe de dimensions de produit qui inclut la dimension de configuration.</span><span class="sxs-lookup"><span data-stu-id="264de-191">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="264de-192">Définissez une nomenclature de configuration pour les composants ou les nomenclatures qui seront utilisées pour configurer les variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="264de-192">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="264de-193">Vous pouvez également créer des nomenclatures pour les noms de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="264de-193">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="264de-194">Les noms de variante de produit peuvent être configurés pour inclure l'ID ou le nom de configuration.</span><span class="sxs-lookup"><span data-stu-id="264de-194">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="264de-195">Exemple de configurations basées sur des contraintes</span><span class="sxs-lookup"><span data-stu-id="264de-195">Example for constraint-based configurations</span></span>

<span data-ttu-id="264de-196">Pour cet exemple, vous pouvez utiliser une nomenclature de numéros de variante de produit qui comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="264de-196">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="264de-197">Numéro du produit générique</span><span class="sxs-lookup"><span data-stu-id="264de-197">Product master number</span></span>
2.  <span data-ttu-id="264de-198">Constante de texte : "\_"</span><span class="sxs-lookup"><span data-stu-id="264de-198">Text constant "\_"</span></span>
3.  <span data-ttu-id="264de-199">Configuration</span><span class="sxs-lookup"><span data-stu-id="264de-199">Configuration</span></span>

<span data-ttu-id="264de-200">La nomenclature de configuration comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="264de-200">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="264de-201">Valeur d'attribut : Matières</span><span class="sxs-lookup"><span data-stu-id="264de-201">Attribute value: Material</span></span>
2.  <span data-ttu-id="264de-202">Constante de texte : "AAA"</span><span class="sxs-lookup"><span data-stu-id="264de-202">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="264de-203">Valeur d'attribut : Longueur</span><span class="sxs-lookup"><span data-stu-id="264de-203">Attribute value: Length</span></span>

<span data-ttu-id="264de-204">Entrez les valeurs suivantes pour les segments :</span><span class="sxs-lookup"><span data-stu-id="264de-204">You enter the following values for segments:</span></span>

-   <span data-ttu-id="264de-205">Numéro du produit générique = **M0099**</span><span class="sxs-lookup"><span data-stu-id="264de-205">Product master number = **M0099**</span></span>
-   <span data-ttu-id="264de-206">Matières = **Plastique**</span><span class="sxs-lookup"><span data-stu-id="264de-206">Material = **Plastic**</span></span>
-   <span data-ttu-id="264de-207">Longueur = **12**</span><span class="sxs-lookup"><span data-stu-id="264de-207">Length = **12**</span></span>

<span data-ttu-id="264de-208">Dans ce cas, le numéro de variante de produit est M0099\_PlasticAAA12.</span><span class="sxs-lookup"><span data-stu-id="264de-208">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="264de-209">Exemple de configurations basées sur des dimensions</span><span class="sxs-lookup"><span data-stu-id="264de-209">Example for dimension-based configurations</span></span>

<span data-ttu-id="264de-210">Pour cet exemple, vous pouvez utiliser une nomenclature de numéros de variante de produit qui comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="264de-210">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="264de-211">Numéro du produit générique</span><span class="sxs-lookup"><span data-stu-id="264de-211">Product master number</span></span>
2.  <span data-ttu-id="264de-212">Constante de texte : "//"</span><span class="sxs-lookup"><span data-stu-id="264de-212">Text constant "//"</span></span>
3.  <span data-ttu-id="264de-213">Configuration</span><span class="sxs-lookup"><span data-stu-id="264de-213">Configuration</span></span>

<span data-ttu-id="264de-214">La nomenclature de configuration comporte les segments suivants :</span><span class="sxs-lookup"><span data-stu-id="264de-214">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="264de-215">Groupe de configurations : Meuble</span><span class="sxs-lookup"><span data-stu-id="264de-215">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="264de-216">Constante de texte : "&"</span><span class="sxs-lookup"><span data-stu-id="264de-216">Text constant: "&"</span></span>
3.  <span data-ttu-id="264de-217">Groupe de configurations : Grille avant</span><span class="sxs-lookup"><span data-stu-id="264de-217">Configuration group: Front grill</span></span>

<span data-ttu-id="264de-218">Entrez les valeurs suivantes pour les segments :</span><span class="sxs-lookup"><span data-stu-id="264de-218">You enter the following values for segments:</span></span>

-   <span data-ttu-id="264de-219">Numéro du produit générique = **D0123**</span><span class="sxs-lookup"><span data-stu-id="264de-219">Product master number = **D0123**</span></span>
-   <span data-ttu-id="264de-220">Meuble = **M0008**</span><span class="sxs-lookup"><span data-stu-id="264de-220">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="264de-221">Grille avant = **M0022**</span><span class="sxs-lookup"><span data-stu-id="264de-221">Front grill = **M0022**</span></span>

<span data-ttu-id="264de-222">Dans ce cas, le numéro de variante de produit est D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="264de-222">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="264de-223">Conflits de numérotation</span><span class="sxs-lookup"><span data-stu-id="264de-223">Numbering conflicts</span></span>
<span data-ttu-id="264de-224">Dans certains cas, une nomenclature de numéros de variante de produit que vous paramétrez peut ne pas produire des numéros de variante de produit uniques.</span><span class="sxs-lookup"><span data-stu-id="264de-224">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="264de-225">Par exemple, les numéros de variante de produit ne sont pas uniques si une dimension de produit active n'est pas incluse dans la nomenclature d'un produit générique qui utilise la technologie de configuration de variante prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="264de-225">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="264de-226">La façon dont vous gérez les conflits varie selon la technologie de configuration.</span><span class="sxs-lookup"><span data-stu-id="264de-226">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="264de-227">Variantes prédéfinies</span><span class="sxs-lookup"><span data-stu-id="264de-227">Predefined variants</span></span>

<span data-ttu-id="264de-228">Une erreur se produit si vous essayez de créer manuellement ou de générer automatiquement des variantes de produit, et plusieurs variantes de produit se terminent avec le même numéro de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="264de-228">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="264de-229">Pour éviter ce scénario, vous devez utiliser toutes les dimensions de produit actives dans le groupe de dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="264de-229">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="264de-230">Sinon, incluez une souche de numéros pour garantir que les numéros de variante de produit sont uniques.</span><span class="sxs-lookup"><span data-stu-id="264de-230">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="264de-231">Configurations basées sur les contraintes</span><span class="sxs-lookup"><span data-stu-id="264de-231">Constraint-based configurations</span></span>

<span data-ttu-id="264de-232">Selon la nomenclature, le système peut tenter d'affecter un numéro de variante de produit non unique à une configuration.</span><span class="sxs-lookup"><span data-stu-id="264de-232">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="264de-233">Dans ce cas, le système utilise la souche de numéros de la dimension de configuration comme numéro de variante de produit à la place. Vous recevrez alors un avertissement.</span><span class="sxs-lookup"><span data-stu-id="264de-233">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="264de-234">Pour éviter ce scénario, vous devez inclure assez d'attributs dans la nomenclature pour garantir que les numéros de variable de produit sont uniques.</span><span class="sxs-lookup"><span data-stu-id="264de-234">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="264de-235">Vous devez également vous assurer que l'option **Réutilisation** est activée pour le composant.</span><span class="sxs-lookup"><span data-stu-id="264de-235">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="264de-236">Configurations basées sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="264de-236">Dimension-based configurations</span></span>

<span data-ttu-id="264de-237">Au cours d'une étape du processus de configuration, le système suggère une valeur de configuration selon la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="264de-237">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="264de-238">À cette étape, vous pouvez modifier manuellement la valeur de la configuration.</span><span class="sxs-lookup"><span data-stu-id="264de-238">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="264de-239">Lorsque vous enregistrez la configuration, le système vérifie que la valeur de configuration est unique.</span><span class="sxs-lookup"><span data-stu-id="264de-239">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="264de-240">Si la valeur entrée n'est pas unique, vous recevez un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="264de-240">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="264de-241">Pour enregistrer la configuration, vous devez entrer une valeur de configuration unique.</span><span class="sxs-lookup"><span data-stu-id="264de-241">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="see-also"></a><span data-ttu-id="264de-242">Voir également :</span><span class="sxs-lookup"><span data-stu-id="264de-242">See also</span></span>
--------

[<span data-ttu-id="264de-243">Créer une nomenclature de numéros de produit pour des variantes de produit prédéfinies</span><span class="sxs-lookup"><span data-stu-id="264de-243">Create a product number nomenclature for predefined product variants</span></span>](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[<span data-ttu-id="264de-244">Créer une nomenclature de numéros de produit pour des variantes de produit configurées</span><span class="sxs-lookup"><span data-stu-id="264de-244">Create a product number nomenclature for configured product variants</span></span>](tasks/create-product-number-nomenclature-product-variants_2016_11.md)


