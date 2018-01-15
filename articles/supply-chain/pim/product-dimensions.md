---
title: Dimensions de produit
description: "Il existe quatre dimensions de produit -  Couleur, Configuration, Taille et Style. Vous combinez des dimensions de produit dans les groupes de dimensions et vous affectez des groupes de dimensions aux produits génériques. Les combinaisons de dimensions de produit déterminent la manière dont les variantes de produit sont définies."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 68f4bfcf62b5e7c65cbe361b510c2769b0e9bebb
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="product-dimensions"></a><span data-ttu-id="9e0b3-105">Dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="9e0b3-105">Product dimensions</span></span>

[!include[banner](../includes/banner.md)]

[!include[Retail name](../includes/retail-name.md)]


<span data-ttu-id="9e0b3-106">Il existe quatre dimensions de produit -  Couleur, Configuration, Taille et Style.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-106">There are four product dimensions -  Color, Configuration, Size and Style.</span></span> <span data-ttu-id="9e0b3-107">Vous combinez des dimensions de produit dans les groupes de dimensions et vous affectez des groupes de dimensions aux produits génériques.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-107">You combine product dimensions in dimension groups and assign dimension groups to product masters.</span></span> <span data-ttu-id="9e0b3-108">Les combinaisons de dimensions de produit déterminent la manière dont les variantes de produit sont définies.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-108">The combinations of product dimensions determine how product variants are defined.</span></span>

<span data-ttu-id="9e0b3-109">Les dimensions de produit sont des caractéristiques qui permettent d'identifier une variante de produit.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-109">Product dimensions are characteristics that serve to identify a product variant.</span></span> <span data-ttu-id="9e0b3-110">Vous pouvez utiliser des combinaisons de dimensions de produit pour définir des variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-110">You can use combinations of product dimensions to define product variants.</span></span> <span data-ttu-id="9e0b3-111">Vous devez définir au moins une dimension de produit pour un produit générique pour créer une variante de produit.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-111">You must define at least one product dimension for a product master in order to create a product variant.</span></span>
<span data-ttu-id="9e0b3-112">Variantes de produit</span><span class="sxs-lookup"><span data-stu-id="9e0b3-112">Product variants</span></span>
----------------

<span data-ttu-id="9e0b3-113">Les variantes de produit sont également appelées des articles.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-113">Product variants are also referred to as items.</span></span> <span data-ttu-id="9e0b3-114">Un article est un produit corporel, ce qui n'est pas le même qu'un service.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-114">An item is a tangible product, which is not the same as a service.</span></span> <span data-ttu-id="9e0b3-115">Il est également possible de définir un produit générique de type Service.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-115">It is also possible to define a product master with the Service type.</span></span> <span data-ttu-id="9e0b3-116">En utilisant le type Service, vous pouvez spécifier des variantes de produit qui incluent les services.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-116">By using the Service type, you can specify product variants that include services.</span></span> <span data-ttu-id="9e0b3-117">Par exemple, vous pouvez spécifier un produit générique pour le travail Conseil et des variantes de produit pour le travail qui est effectué par les consultants supérieurs et les consultants juniors.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-117">For example, you can specify a product master for Consultancy work and product variants for work that is performed by senior consultants and junior consultants.</span></span>

## <a name="product-dimensions"></a><span data-ttu-id="9e0b3-118">Dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="9e0b3-118">Product dimensions</span></span>
<span data-ttu-id="9e0b3-119">Les dimensions de produit suivantes sont disponibles : Configuration, Couleur, Taille et Style.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-119">The following product dimensions are available: Configuration, Color, Size, and Style.</span></span> <span data-ttu-id="9e0b3-120">Une variante de produit peut être générée selon les valeurs de dimension de produit.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-120">A product variant can be generated based on the product dimension values.</span></span>

<span data-ttu-id="9e0b3-121">Les valeurs de dimensions de produit telles que la taille, la couleur et le style peuvent être créées dans les pages **Taille**, **Couleur** et **Style**, qui sont accessibles à partir des emplacements suivants : **Gestion des informations sur les produits** &gt; **Paramétrage** &gt; **Groupes de dimensions et de variantes** &gt; **Tailles/Couleurs/Styles**.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-121">Product dimensions values such as Size, Color and Style can be created on the **Size**, **Color** and **Style** pages, which can be accessed from the following locations: **Product information management** &gt; **Setup** &gt; **Dimension and variant Groups** &gt; **Sizes/Colors/Styles**.</span></span> <span data-ttu-id="9e0b3-122">Les valeurs de dimension de produit pour la dimension Configuration sont généralement créées à l'aide du configurateur de produits ou du configurateur basé sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-122">Product dimension values for the Configuration dimension are typically created using either the Product configurator or the Dimension-based configurator.</span></span> <span data-ttu-id="9e0b3-123">Les dimensions de produit peuvent également être créées et tenues à jour dans la page **Dimensions de produit**, qui est accessible depuis les emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="9e0b3-123">Product dimensions can also be created and maintained on the **Product dimensions** page, which can be accessed from the following locations:</span></span>
-   <span data-ttu-id="9e0b3-124">Cliquez sur **Gestion des informations sur les produits** &gt; **Produits** &gt; **Produits génériques**.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-124">Click **Product information management** &gt; **Products** &gt; **Product masters**.</span></span> <span data-ttu-id="9e0b3-125">Dans le volet **Actions**, cliquez sur **Dimensions de produit**.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-125">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="9e0b3-126">Cliquez sur **Gestion des informations sur les produits** &gt; **Produits** &gt; **Tous les produits et produits génériques**.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-126">Click **Product information management** &gt; **Products** &gt; **All products and product masters**.</span></span> <span data-ttu-id="9e0b3-127">Sélectionnez un produit générique.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-127">Select a product master.</span></span> <span data-ttu-id="9e0b3-128">Dans le volet **Actions**, cliquez sur **Dimensions de produit**.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-128">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="9e0b3-129">Cliquez sur **Gestion des informations sur les produits** &gt; **Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-129">Click **Product information management** &gt; **Released products**.</span></span> <span data-ttu-id="9e0b3-130">Sélectionnez un produit générique.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-130">Select a product master.</span></span> <span data-ttu-id="9e0b3-131">Dans le volet **Actions**, cliquez sur **Produit**.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-131">On the **Action Pane**, click **Product**.</span></span> <span data-ttu-id="9e0b3-132">Dans le groupe **Produit générique**, cliquez sur **Dimensions de produit**.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-132">In the **Product master** group, click **Product dimensions**.</span></span>

<span data-ttu-id="9e0b3-133">Le nombre de variantes que vous pouvez créer pour un article est limité par le nombre de combinaisons possibles de dimension de produit.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-133">The number of variants that you can create for an item is limited by the number of possible product dimension combinations.</span></span>
| <span data-ttu-id="9e0b3-134">**Conseil**</span><span class="sxs-lookup"><span data-stu-id="9e0b3-134">**Tip**</span></span>                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9e0b3-135">Lorsque vous utilisez un produit sur, par exemple, une ligne de commande, vous sélectionnez les dimensions de produit pour identifier la variante de produit avec laquelle vous souhaitez travailler.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-135">When you use a product on, for example, an order line, you select the product dimensions to identify the product variant that you want to work with.</span></span> |

## <a name="example"></a><span data-ttu-id="9e0b3-136">Exemple</span><span class="sxs-lookup"><span data-stu-id="9e0b3-136">Example</span></span>
<span data-ttu-id="9e0b3-137">Une entreprise vend des jeans.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-137">A company sells denim jeans.</span></span> <span data-ttu-id="9e0b3-138">Les articles, des jeans, utilisent les dimensions de produit Couleur et Taille.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-138">The item, Jeans, uses the Color and Size product dimensions.</span></span> <span data-ttu-id="9e0b3-139">Ils sont vendus en trois couleurs et en six tailles différentes.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-139">The jeans are sold in three different colors and six different sizes.</span></span> <span data-ttu-id="9e0b3-140">Couleurs : bleu, noir, marron. Tailles : XS, S, M, L, XL, XXL. Toutes les tailles ne sont pas disponibles dans les trois couleurs.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-140">Colors: Blue, Black, Brown Sizes: XS, S, M, L, XL, XXL Not all sizes are available in all the three colors.</span></span> <span data-ttu-id="9e0b3-141">Si toutes les combinaisons étaient disponibles, il y aurait 18 types différents de jeans.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-141">If all combinations were available, it would create 18 different types of jeans.</span></span> <span data-ttu-id="9e0b3-142">Dans cet exemple, seules les neuf combinaisons de variantes de produit suivantes sont produites.</span><span class="sxs-lookup"><span data-stu-id="9e0b3-142">In this example, only the following nine product variant combinations are produced.</span></span>

| <span data-ttu-id="9e0b3-143">Couleur</span><span class="sxs-lookup"><span data-stu-id="9e0b3-143">Color</span></span> | <span data-ttu-id="9e0b3-144">Taille</span><span class="sxs-lookup"><span data-stu-id="9e0b3-144">Size</span></span> |
|-------|------|
| <span data-ttu-id="9e0b3-145">Bleu</span><span class="sxs-lookup"><span data-stu-id="9e0b3-145">Blue</span></span>  | <span data-ttu-id="9e0b3-146">XS</span><span class="sxs-lookup"><span data-stu-id="9e0b3-146">XS</span></span>   |
| <span data-ttu-id="9e0b3-147">Bleu</span><span class="sxs-lookup"><span data-stu-id="9e0b3-147">Blue</span></span>  | <span data-ttu-id="9e0b3-148">Sa</span><span class="sxs-lookup"><span data-stu-id="9e0b3-148">S</span></span>    |
| <span data-ttu-id="9e0b3-149">Bleu</span><span class="sxs-lookup"><span data-stu-id="9e0b3-149">Blue</span></span>  | <span data-ttu-id="9e0b3-150">F</span><span class="sxs-lookup"><span data-stu-id="9e0b3-150">M</span></span>    |
| <span data-ttu-id="9e0b3-151">Noir</span><span class="sxs-lookup"><span data-stu-id="9e0b3-151">Black</span></span> | <span data-ttu-id="9e0b3-152">F</span><span class="sxs-lookup"><span data-stu-id="9e0b3-152">M</span></span>    |
| <span data-ttu-id="9e0b3-153">Noir</span><span class="sxs-lookup"><span data-stu-id="9e0b3-153">Black</span></span> | <span data-ttu-id="9e0b3-154">R</span><span class="sxs-lookup"><span data-stu-id="9e0b3-154">L</span></span>    |
| <span data-ttu-id="9e0b3-155">Noir</span><span class="sxs-lookup"><span data-stu-id="9e0b3-155">Black</span></span> | <span data-ttu-id="9e0b3-156">XL</span><span class="sxs-lookup"><span data-stu-id="9e0b3-156">XL</span></span>   |
| <span data-ttu-id="9e0b3-157">Marron</span><span class="sxs-lookup"><span data-stu-id="9e0b3-157">Brown</span></span> | <span data-ttu-id="9e0b3-158">R</span><span class="sxs-lookup"><span data-stu-id="9e0b3-158">L</span></span>    |
| <span data-ttu-id="9e0b3-159">Marron</span><span class="sxs-lookup"><span data-stu-id="9e0b3-159">Brown</span></span> | <span data-ttu-id="9e0b3-160">XL</span><span class="sxs-lookup"><span data-stu-id="9e0b3-160">XL</span></span>   |
| <span data-ttu-id="9e0b3-161">Marron</span><span class="sxs-lookup"><span data-stu-id="9e0b3-161">Brown</span></span> | <span data-ttu-id="9e0b3-162">XXL</span><span class="sxs-lookup"><span data-stu-id="9e0b3-162">XXL</span></span>  |





