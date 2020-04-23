---
title: Conversion d'unité de mesure selon la variante de produit
description: Cette rubrique explique comment les conversions d'unités de mesure peuvent être paramétrées selon les variantes de produit.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: e50be7fa6fa686a90b2dd5c5200c881e4629f019
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204491"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="6f627-103">Conversion d'unité de mesure selon la variante de produit</span><span class="sxs-lookup"><span data-stu-id="6f627-103">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6f627-104">Cette rubrique explique comment les conversions d'unités de mesure peuvent être paramétrées selon les variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="6f627-104">This topic explains how unit of measure conversions can be set up on product variants.</span></span> <span data-ttu-id="6f627-105">Elle inclut un exemple de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="6f627-105">It includes an example of the setup.</span></span>

<span data-ttu-id="6f627-106">Cette fonctionnalité permet aux sociétés de définir différentes conversions d'unités entre les variantes du même produit.</span><span class="sxs-lookup"><span data-stu-id="6f627-106">This feature makes it possible for companies to define different unit conversion between the variants of the same product.</span></span> <span data-ttu-id="6f627-107">L'exemple ci-dessous est utilisé dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="6f627-107">The following example is used in this topic.</span></span> <span data-ttu-id="6f627-108">Une société vend des t-shirts dans les tailles S, M, L et XL.</span><span class="sxs-lookup"><span data-stu-id="6f627-108">A company sells T-shirts in sizes Small, Medium, Large, and Extra-Large.</span></span> <span data-ttu-id="6f627-109">Le T-shirt est défini comme produit, et les différentes tailles sont définies en tant que variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="6f627-109">The T-shirt is defined as a product, and the different sizes are defined as variants of the product.</span></span> <span data-ttu-id="6f627-110">Les t-shirts sont emballés dans des boîtes et il peut y avoir cinq t-shirts dans une boîte, à l'exception de la taille XL où il n'y a d'espace pour quatre t-shirts.</span><span class="sxs-lookup"><span data-stu-id="6f627-110">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-Large size where there is only space for four T-shirts.</span></span> <span data-ttu-id="6f627-111">La société souhaite suivre les différentes variantes de t-shirts dans l'unité **Pièces** mais vend les t-shirts dans l'unité **Boîtes**.</span><span class="sxs-lookup"><span data-stu-id="6f627-111">The company wants to track the different variants of the T-shirts in the unit **Pieces** but is selling the T-shirts in the unit **Boxes**.</span></span> <span data-ttu-id="6f627-112">La conversion entre l'unité de stock et l'unité de vente est de 1 boîte = 5 pièces, sauf la variante XL, où la conversion est 1 boîte = 4 pièces.</span><span class="sxs-lookup"><span data-stu-id="6f627-112">The conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces, except for the variant Extra-Large, where the conversion is 1 Box = 4 Pieces.</span></span>

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="6f627-113">Paramétrage d'un produit pour la conversion d'unités par variante</span><span class="sxs-lookup"><span data-stu-id="6f627-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="6f627-114">Les variantes de produit peuvent être créées uniquement pour les produits du **sous-type Produit** : **Produit générique**.</span><span class="sxs-lookup"><span data-stu-id="6f627-114">Product variants can only be created for products of **Product subtype**: **Product master**.</span></span> <span data-ttu-id="6f627-115">Pour plus d'informations, voir [Création d'un produit générique](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="6f627-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span>

<span data-ttu-id="6f627-116">La fonctionnalité n'est pas activée pour les produits paramétrés pour les processus en poids variable.</span><span class="sxs-lookup"><span data-stu-id="6f627-116">The feature is not enabled for products that are set up for Catch Weight processes.</span></span> 

<span data-ttu-id="6f627-117">Lorsque le produit générique avec des variantes de produits lancés est créé, des conversions d'unités par variantes peuvent être paramétrées.</span><span class="sxs-lookup"><span data-stu-id="6f627-117">When the product master with released products variants is created, unit conversions per variants can be set up.</span></span> <span data-ttu-id="6f627-118">Vous pouvez trouver l'option de menu pour ouvrir la page de conversion d'unités dans le contexte d'un produit ou d'une variante de produit dans les pages suivantes.</span><span class="sxs-lookup"><span data-stu-id="6f627-118">You can find the menu item for opening the unit conversion page in context of a product or a product variant on the following pages.</span></span>

-   <span data-ttu-id="6f627-119">Page **Détails de produit**</span><span class="sxs-lookup"><span data-stu-id="6f627-119">**Product details** page</span></span>
-   <span data-ttu-id="6f627-120">Page **Détails des produits lancés**</span><span class="sxs-lookup"><span data-stu-id="6f627-120">**Released products details** page</span></span>
-   <span data-ttu-id="6f627-121">Page **Variantes de produits lancés**</span><span class="sxs-lookup"><span data-stu-id="6f627-121">**Released product variants** page</span></span>

<span data-ttu-id="6f627-122">Lorsque vous ouvrez la page **Conversion d'unités** dans le contexte d'une variante de produit générique ou de produit lancé, vous pouvez choisir si vous voulez paramétrer la conversion d'unités pour le produit ou pour une variante de produit.</span><span class="sxs-lookup"><span data-stu-id="6f627-122">When you open the **Unit conversion** page in context of a product master or released product variant, you can select if you want to set up the unit conversion for the product or for a product variant.</span></span> <span data-ttu-id="6f627-123">Pour cela, sélectionnez **Variante de produit** ou **Produit** dans le champ **Créer la conversion pour**.</span><span class="sxs-lookup"><span data-stu-id="6f627-123">You do that by selecting either **Product variant** or **Product** in the **Create conversion for** field.</span></span>

### <a name="product-variant"></a><span data-ttu-id="6f627-124">Variante de produit</span><span class="sxs-lookup"><span data-stu-id="6f627-124">Product variant</span></span>

<span data-ttu-id="6f627-125">Si vous sélectionnez **Variante de produit**, vous pouvez sélectionner pour quelle variante vous souhaitez paramétrer la conversion d'unités dans le champ **Variante de produit**.</span><span class="sxs-lookup"><span data-stu-id="6f627-125">If you select **Product variant,** then you can select for which variant you want to set up the unit conversion in the **Product variant** field.</span></span>

### <a name="product"></a><span data-ttu-id="6f627-126">Produit</span><span class="sxs-lookup"><span data-stu-id="6f627-126">Product</span></span>

<span data-ttu-id="6f627-127">Si vous sélectionnez **Produit**, vous pouvez paramétrer une conversion d'unités pour le produit générique.</span><span class="sxs-lookup"><span data-stu-id="6f627-127">If you select **Product**, then you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="6f627-128">Cette conversion d'unité s'appliquera pour toutes les variantes de produit sans conversion d'unité définie.</span><span class="sxs-lookup"><span data-stu-id="6f627-128">This unit conversion will apply for all product variants with no defined unit conversion.</span></span>

### <a name="example"></a><span data-ttu-id="6f627-129">Exemple</span><span class="sxs-lookup"><span data-stu-id="6f627-129">Example</span></span>

<span data-ttu-id="6f627-130">Un produit générique, **T-shirt**, a quatre variantes de produits lancés : S, M, L et XL.</span><span class="sxs-lookup"><span data-stu-id="6f627-130">A product master, **T-Shirt**, has four released products variants Small, Medium, Large, and X-Large.</span></span> <span data-ttu-id="6f627-131">Les t-shirts sont emballés dans des boîtes et il peut y avoir cinq t-shirts dans une boîte, à l'exception de la taille XL où il n'y a d'espace pour quatre t-shirts.</span><span class="sxs-lookup"><span data-stu-id="6f627-131">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-large size where there is only space for four T-shirts.</span></span>

<span data-ttu-id="6f627-132">Premièrement, ouvrez la page **Conversion d'unité** de la page de détails de produit lancé pour **T-shirt.**</span><span class="sxs-lookup"><span data-stu-id="6f627-132">First, open the **Unit conversion** page from the Release product details page for **T-shirt.**</span></span>

<span data-ttu-id="6f627-133">Dans la page **Conversion d'unité**, paramétrez la conversion d'unité pour la variante de produit lancé XL.</span><span class="sxs-lookup"><span data-stu-id="6f627-133">On the **Unit conversion** page, set up the unit conversion for the release product variant X-Large.</span></span>

| <span data-ttu-id="6f627-134">**Champ**</span><span class="sxs-lookup"><span data-stu-id="6f627-134">**Field**</span></span>             | <span data-ttu-id="6f627-135">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="6f627-135">**Setting**</span></span>             |
|-----------------------|-------------------------|
| <span data-ttu-id="6f627-136">Créer une conversion pour</span><span class="sxs-lookup"><span data-stu-id="6f627-136">Create conversion for</span></span> | <span data-ttu-id="6f627-137">Variante de produit</span><span class="sxs-lookup"><span data-stu-id="6f627-137">Product variant</span></span>         |
| <span data-ttu-id="6f627-138">Variante de produit</span><span class="sxs-lookup"><span data-stu-id="6f627-138">Product variant</span></span>       | <span data-ttu-id="6f627-139">T-shirt : : XL : :</span><span class="sxs-lookup"><span data-stu-id="6f627-139">T-Shirt : : X-Large : :</span></span> |
| <span data-ttu-id="6f627-140">Unité - De</span><span class="sxs-lookup"><span data-stu-id="6f627-140">From unit</span></span>             | <span data-ttu-id="6f627-141">Boîtes</span><span class="sxs-lookup"><span data-stu-id="6f627-141">Boxes</span></span>                   |
| <span data-ttu-id="6f627-142">Facteur</span><span class="sxs-lookup"><span data-stu-id="6f627-142">Factor</span></span>                | <span data-ttu-id="6f627-143">4</span><span class="sxs-lookup"><span data-stu-id="6f627-143">4</span></span>                       |
| <span data-ttu-id="6f627-144">À l'unité</span><span class="sxs-lookup"><span data-stu-id="6f627-144">To Unit</span></span>               | <span data-ttu-id="6f627-145">Pièces</span><span class="sxs-lookup"><span data-stu-id="6f627-145">Pieces</span></span>                  |

<span data-ttu-id="6f627-146">Les variantes de produit lancé S, M et L ont la même conversion d'unité entre l'unité Boîte et Pièces, ce qui signifie que vous pouvez définir une conversion d'unité pour ces variantes de produit dans le produit générique.</span><span class="sxs-lookup"><span data-stu-id="6f627-146">The Released product variants Small, Medium, and Large have the same unit conversion between the unit Box and Pieces, which means that you can define the unit conversion for these product variants on the product master.</span></span>

| <span data-ttu-id="6f627-147">**Champ**</span><span class="sxs-lookup"><span data-stu-id="6f627-147">**Field**</span></span>             | <span data-ttu-id="6f627-148">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="6f627-148">**Setting**</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="6f627-149">Créer une conversion pour</span><span class="sxs-lookup"><span data-stu-id="6f627-149">Create conversion for</span></span> | <span data-ttu-id="6f627-150">Produit</span><span class="sxs-lookup"><span data-stu-id="6f627-150">Product</span></span>     |
| <span data-ttu-id="6f627-151">Produit</span><span class="sxs-lookup"><span data-stu-id="6f627-151">Product</span></span>               | <span data-ttu-id="6f627-152">T-shirt</span><span class="sxs-lookup"><span data-stu-id="6f627-152">T-Shirt</span></span>     |
| <span data-ttu-id="6f627-153">Unité - De</span><span class="sxs-lookup"><span data-stu-id="6f627-153">From unit</span></span>             | <span data-ttu-id="6f627-154">Boîtes</span><span class="sxs-lookup"><span data-stu-id="6f627-154">Boxes</span></span>       |
| <span data-ttu-id="6f627-155">Facteur</span><span class="sxs-lookup"><span data-stu-id="6f627-155">Factor</span></span>                | <span data-ttu-id="6f627-156">5</span><span class="sxs-lookup"><span data-stu-id="6f627-156">5</span></span>           |
| <span data-ttu-id="6f627-157">À l'unité</span><span class="sxs-lookup"><span data-stu-id="6f627-157">To Unit</span></span>               | <span data-ttu-id="6f627-158">Pièces</span><span class="sxs-lookup"><span data-stu-id="6f627-158">Pieces</span></span>      |

### <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="6f627-159">Utilisation d'Excel pour mettre à jour les conversions d'unité</span><span class="sxs-lookup"><span data-stu-id="6f627-159">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="6f627-160">Si un produit a plusieurs variantes de produit différentes avec des conversions d'unités distinctes, il est conseillé d'exporter les conversions d'unités de la page **Conversion d'unité** dans une feuille de calcul Excel, de mettre à jour les conversions, puis de les publier dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6f627-160">If a product has many product variants with different unit conversions, it's a good idea to export the unit conversions from the **Unit conversion** page to an Excel spreadsheet, update the conversions, and then publish them back to Supply Chain Mangement.</span></span>

<span data-ttu-id="6f627-161">L'option permettant d'exporter vers Excel et de republier les modifications dans Supply Chain Management est activée dans l'option de menu **Ouvrir dans Microsoft office** sur le volet Actions de la page **Conversion d'unité**.</span><span class="sxs-lookup"><span data-stu-id="6f627-161">The option to export to Excel and publish the edits back to Supply Chain Mangement is enabled from the **Open in Microsoft office** menu item on the Action Pane on the **Unit conversion** page.</span></span>
