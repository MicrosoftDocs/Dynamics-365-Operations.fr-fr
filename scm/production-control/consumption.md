---
title: "Calculer la consommation de matières"
description: "Cet article fournit des informations sur les différentes options relatives au calcul de la consommation de matières."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 88fb31fc425c9fbd2ef96e4497f120da4440af04
ms.contentlocale: fr-fr
ms.lasthandoff: 06/29/2017


---

# <a name="calculate-material-consumption"></a><span data-ttu-id="dbf86-103">Calculer la consommation de matières</span><span class="sxs-lookup"><span data-stu-id="dbf86-103">Calculate material consumption</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="dbf86-104">Cet article fournit des informations sur les différentes options relatives au calcul de la consommation de matières.</span><span class="sxs-lookup"><span data-stu-id="dbf86-104">This article provides information about various options that are related to the calculation of material consumption.</span></span> 

<span data-ttu-id="dbf86-105">Les options suivantes relatives au calcul de la consommation de matières sont disponibles sous les onglets **Paramétrage** et **Consommation de l'étape** sur l'organisateur **Détails de ligne** de la page **Nomenclatures**.</span><span class="sxs-lookup"><span data-stu-id="dbf86-105">The following options that are related to the calculation of material consumption are available on the **Setup** and **Step consumption** tabs on the **Line details** FastTab of the **Bill of materials** page.</span></span>

## <a name="variable-and-constant-consumption"></a><span data-ttu-id="dbf86-106">Consommation variable et constante</span><span class="sxs-lookup"><span data-stu-id="dbf86-106">Variable and constant consumption</span></span>
<span data-ttu-id="dbf86-107">Dans le champ **Type de consommation**, vous pouvez sélectionner si la consommation doit être calculée comme quantité constante ou comme quantité variable.</span><span class="sxs-lookup"><span data-stu-id="dbf86-107">In the **Consumption is** field, you can select whether consumption should be calculated as a constant quantity or a variable quantity.</span></span> <span data-ttu-id="dbf86-108">Sélectionnez **Constante** si une quantité ou un volume fixe est requis pour la production, peu importe la quantité produite.</span><span class="sxs-lookup"><span data-stu-id="dbf86-108">Select **Constant** if a fixed quantity or volume is required for the production, regardless of the quantity that is produced.</span></span> <span data-ttu-id="dbf86-109">Sélectionnez **Variable**, qui est le paramètre par défaut, si la quantité de matières requises dans des produits finis est proportionnelle au nombre de produits finis fabriqués.</span><span class="sxs-lookup"><span data-stu-id="dbf86-109">Select **Variable**, which is the default setting, if the required amount of material in the finished goods is proportional to the number of finished goods that are produced.</span></span>

## <a name="calculating-consumption-from-a-formula"></a><span data-ttu-id="dbf86-110">Calcul de la consommation à partir d'une formule</span><span class="sxs-lookup"><span data-stu-id="dbf86-110">Calculating consumption from a formula</span></span>
<span data-ttu-id="dbf86-111">Dans le champ **Formule**, vous pouvez paramétrer diverses formules pour calculer la consommation de matières.</span><span class="sxs-lookup"><span data-stu-id="dbf86-111">In the **Formula** field, you can set up various formulas for calculating material consumption.</span></span> <span data-ttu-id="dbf86-112">Si vous utilisez la valeur par défaut, **Standard**, la consommation n'est pas calculée à partir d'une formule.</span><span class="sxs-lookup"><span data-stu-id="dbf86-112">If you use the default value, **Standard**, the consumption isn't calculated from a formula.</span></span> <span data-ttu-id="dbf86-113">Les formules suivantes s'associent aux champs **Hauteur**, **Largeur**, **Profondeur**, **Densité** et  **Constante** :</span><span class="sxs-lookup"><span data-stu-id="dbf86-113">The following formulas work together with the **Height**, **Width**, **Depth**, **Density**, and **Constant** fields:</span></span>

-   <span data-ttu-id="dbf86-114">Hauteur \* Constante</span><span class="sxs-lookup"><span data-stu-id="dbf86-114">Height \* Constant</span></span>
-   <span data-ttu-id="dbf86-115">Hauteur \* Largeur \* Constante</span><span class="sxs-lookup"><span data-stu-id="dbf86-115">Height \* Width \* Constant</span></span>
-   <span data-ttu-id="dbf86-116">Hauteur \* Largeur \* Profondeur \* Constante</span><span class="sxs-lookup"><span data-stu-id="dbf86-116">Height \* Width \* Depth \* Constant</span></span>
-   <span data-ttu-id="dbf86-117">(Hauteur \* Largeur \* Profondeur / Densité) \* Constante</span><span class="sxs-lookup"><span data-stu-id="dbf86-117">(Height \* Width \* Depth / Density) \* Constant</span></span>

## <a name="rounding-up-and-multiples"></a><span data-ttu-id="dbf86-118">Arrondi et multiples</span><span class="sxs-lookup"><span data-stu-id="dbf86-118">Rounding up and multiples</span></span>
<span data-ttu-id="dbf86-119">Associés, les champs **Arrondi** et **Multiples** permettent d'arrondir la valeur de consommation des matières.</span><span class="sxs-lookup"><span data-stu-id="dbf86-119">Together, the **Rounding up** and **Multiples** fields let you round up the material consumption value.</span></span> <span data-ttu-id="dbf86-120">Par exemple, vous pouvez arrondir la valeur en fonction de l'unité de manutention dans laquelle la matière première est prélevée pour la production.</span><span class="sxs-lookup"><span data-stu-id="dbf86-120">For example, you can round up the value according to the handling unit in which the raw material is picked for production.</span></span> <span data-ttu-id="dbf86-121">Les options suivantes sont disponibles dans le champ **Arrondi** : **Quantité****Mesure** et **Consommation**.</span><span class="sxs-lookup"><span data-stu-id="dbf86-121">The following options are available in the **Rounding up** field: **Quantity**, **Measurement**, and **Consumption**.</span></span>

### <a name="quantity"></a><span data-ttu-id="dbf86-122">Quantité</span><span class="sxs-lookup"><span data-stu-id="dbf86-122">Quantity</span></span>

<span data-ttu-id="dbf86-123">Si vous sélectionnez **Quantité** comme mécanisme d'arrondi, la quantité doit être un multiple de la quantité spécifiée.</span><span class="sxs-lookup"><span data-stu-id="dbf86-123">If you select **Quantity** as the rounding-up mechanism, the quantity must be a multiple of the specified quantity.</span></span> <span data-ttu-id="dbf86-124">Par exemple, si des nombres entiers sont requis, sélectionnez **1** dans le champ **Multiples**.</span><span class="sxs-lookup"><span data-stu-id="dbf86-124">For example, if whole numbers are required, select **1** in the **Multiples** field.</span></span> <span data-ttu-id="dbf86-125">Les numéros sont ensuite arrondis jusqu'à une quantité divisible par 1.</span><span class="sxs-lookup"><span data-stu-id="dbf86-125">Numbers are then rounded up to a quantity that is divisible by 1.</span></span>

### <a name="measurement"></a><span data-ttu-id="dbf86-126">Mesure</span><span class="sxs-lookup"><span data-stu-id="dbf86-126">Measurement</span></span>

<span data-ttu-id="dbf86-127">En général, vous sélectionnez **Mesure** comme mécanisme d'arrondi lorsque la matière première a des dimensions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="dbf86-127">Typically, you select **Measurement** as the rounding-up mechanism when the raw material comes in specific dimensions.</span></span> <span data-ttu-id="dbf86-128">Par exemple, un tube métallique de 2 mètres est requis pour fabriquer un produit fini, et le tube en métal est disponible en longueur de 4,5 mètres.</span><span class="sxs-lookup"><span data-stu-id="dbf86-128">For example, a piece of 2-meter metal tube is required for a finished good, and the metal tube is stored in 4.5-meter lengths.</span></span> <span data-ttu-id="dbf86-129">Dans ce cas, le mécanisme d'arrondi **Mesure** peut être utilisé pour calculer le nombre de tubes métalliques nécessaires pour fabriquer une quantité spécifique de produits finis.</span><span class="sxs-lookup"><span data-stu-id="dbf86-129">In this case, the **Measurement** rounding-up mechanism can be used to calculate how many metal tubes are required to produce a specific number of pieces of the finished good.</span></span> <span data-ttu-id="dbf86-130">Pour cet exemple, le champ **Formule** est défini sur **Hauteur \* Constante**.</span><span class="sxs-lookup"><span data-stu-id="dbf86-130">For this example, the **Formula** field is set to **Height \* Constant**.</span></span> <span data-ttu-id="dbf86-131">Le champ **Hauteur** est défini sur **2** pour indiquer la longueur du tube requise pour obtenir le produit fini.</span><span class="sxs-lookup"><span data-stu-id="dbf86-131">The **Height** field is set to **2** to indicate the length of the tube that is required for the finished good.</span></span> <span data-ttu-id="dbf86-132">Le champ **Multiple** est défini sur **4,5** pour indiquer que le tube est disponible dans une longueur de 4,5 mètres.</span><span class="sxs-lookup"><span data-stu-id="dbf86-132">The **Multiple** field is set to **4.5** to indicate that the tube is picked in lengths of 4.5 meters.</span></span> <span data-ttu-id="dbf86-133">Voici le calcul :</span><span class="sxs-lookup"><span data-stu-id="dbf86-133">Here is the calculation:</span></span>

1.  <span data-ttu-id="dbf86-134">Nombre de multiples nécessaires pour 10 pièces de produits finis : 10 ÷ 2 = 5 pièces</span><span class="sxs-lookup"><span data-stu-id="dbf86-134">Number of multiples that are required for 10 pieces of the finished good: 10 ÷ 2 = 5 pieces</span></span>
2.  <span data-ttu-id="dbf86-135">Consommation totale : 4,5 × 5 = 22,5 mètres de tube métallique</span><span class="sxs-lookup"><span data-stu-id="dbf86-135">Total consumption:  4.5 × 5 = 22.5 meters of metal tube</span></span>

<span data-ttu-id="dbf86-136">On suppose que 0,5 mètre de tube est mis au rebut pour chaque lot de 5 pièces de tube consommées.</span><span class="sxs-lookup"><span data-stu-id="dbf86-136">It's assumed that 0.5 meter of tube is scrapped for every five pieces of tube that are consumed.</span></span>

### <a name="consumption"></a><span data-ttu-id="dbf86-137">Consommation</span><span class="sxs-lookup"><span data-stu-id="dbf86-137">Consumption</span></span>

<span data-ttu-id="dbf86-138">En général, vous sélectionnez**Consommation** comme mécanisme d'arrondi lorsque la matière première doit être prélevée selon des quantités d'une unité de manutention spécifique du produit.</span><span class="sxs-lookup"><span data-stu-id="dbf86-138">Typically, you select **Consumption** as the rounding-up mechanism when raw material must be picked in whole quantities of a specific handling unit of the product.</span></span> <span data-ttu-id="dbf86-139">Par exemple, 2 litres de peinture sont utilisés pour produire une pièce de produit fini, et la peinture est prélevée par boîtes de 25 l.</span><span class="sxs-lookup"><span data-stu-id="dbf86-139">For example, 2 quarts of paint are used to produce one piece of a finished good, and the paint is picked in 25-quart cans.</span></span> <span data-ttu-id="dbf86-140">Dans ce cas, le mécanisme d'arrondi **Consommation** peut être utilisé pour arrondir la consommation de la totalité des boîtes de 25 l.</span><span class="sxs-lookup"><span data-stu-id="dbf86-140">In this case, the **Consumption** rounding-up mechanism can be used to round up consumption to whole numbers of 25-quart cans.</span></span> <span data-ttu-id="dbf86-141">Voici le calcul de la quantité de peinture requise si 180 pièces de produits finis doivent être fabriquées :</span><span class="sxs-lookup"><span data-stu-id="dbf86-141">Here is the calculation for the amount of paint that is required if 180 pieces of the finished good must be produced:</span></span>

1.  <span data-ttu-id="dbf86-142">Peinture requise, hormis mise au rebut : 180 × 2 = 360 litres</span><span class="sxs-lookup"><span data-stu-id="dbf86-142">Paint that is required, excluding scrap: 180 × 2 = 360 quarts</span></span>
2.  <span data-ttu-id="dbf86-143">Nombre de boîtes : 360 ÷ 25 = 14,4, qui est arrondi à 15</span><span class="sxs-lookup"><span data-stu-id="dbf86-143">Number of cans: 360 ÷ 25 = 14.4, which is rounded up to 15</span></span>
3.  <span data-ttu-id="dbf86-144">Peinture requise, mise au rebut incluse : 15 × 25 = 375 litres</span><span class="sxs-lookup"><span data-stu-id="dbf86-144">Paint that is required, including scrap: 15 × 25 = 375 quarts</span></span>

## <a name="step-consumption"></a><span data-ttu-id="dbf86-145">Consommation de l'étape</span><span class="sxs-lookup"><span data-stu-id="dbf86-145">Step consumption</span></span>
<span data-ttu-id="dbf86-146">L'option Consommation de l'étape est utilisée pour calculer la consommation constante selon des intervalles de quantité.</span><span class="sxs-lookup"><span data-stu-id="dbf86-146">Step consumption is used to calculate constant consumption in quantity intervals.</span></span> <span data-ttu-id="dbf86-147">Si vous sélectionnez **Consommation de l'étape** dans le champ **Formule** sous l'onglet **Paramétrage**, vous pouvez ajouter des informations sur les étapes sous l'onglet **Consommation de l'étape**.</span><span class="sxs-lookup"><span data-stu-id="dbf86-147">If you select **Step consumption** in the **Formula** field on the **Setup** tab, you can add information about the steps on the **Step consumption** tab.</span></span> <span data-ttu-id="dbf86-148">La quantité consommée fixe peut être paramétrée selon des intervalles de quantité produite.</span><span class="sxs-lookup"><span data-stu-id="dbf86-148">The fixed consumed quantity can be set up in intervals of the produced quantity.</span></span> <span data-ttu-id="dbf86-149">Par exemple, la consommation de l'étape est paramétrée comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="dbf86-149">For example, step consumption is set up as shown in the following table.</span></span>

| <span data-ttu-id="dbf86-150">Série de départ</span><span class="sxs-lookup"><span data-stu-id="dbf86-150">From series</span></span> | <span data-ttu-id="dbf86-151">Quantité</span><span class="sxs-lookup"><span data-stu-id="dbf86-151">Quantity</span></span> |
|-------------|----------|
| <span data-ttu-id="dbf86-152">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf86-152">0.00</span></span>        | <span data-ttu-id="dbf86-153">10,0000</span><span class="sxs-lookup"><span data-stu-id="dbf86-153">10.0000</span></span>  |
| <span data-ttu-id="dbf86-154">100,00</span><span class="sxs-lookup"><span data-stu-id="dbf86-154">100.00</span></span>      | <span data-ttu-id="dbf86-155">20,0000</span><span class="sxs-lookup"><span data-stu-id="dbf86-155">20.0000</span></span>  |
| <span data-ttu-id="dbf86-156">200,00</span><span class="sxs-lookup"><span data-stu-id="dbf86-156">200.00</span></span>      | <span data-ttu-id="dbf86-157">40,0000</span><span class="sxs-lookup"><span data-stu-id="dbf86-157">40.0000</span></span>  |

<span data-ttu-id="dbf86-158">La quantité de la nomenclature est de 1, et la quantité de la production est de 110.</span><span class="sxs-lookup"><span data-stu-id="dbf86-158">The bill of materials (BOM) quantity is 1, and the production quantity is 110.</span></span> <span data-ttu-id="dbf86-159">La formule de la consommation est Série de départ (Quantité) = Consommation.</span><span class="sxs-lookup"><span data-stu-id="dbf86-159">The formula for the consumption is From series (Quantity) = Consumption.</span></span> <span data-ttu-id="dbf86-160">Étant donné que la quantité de production est de 110, elle passe dans la « Série de départ 100 ».</span><span class="sxs-lookup"><span data-stu-id="dbf86-160">Because the production quantity is 110, it falls into the "From 100 series."</span></span> <span data-ttu-id="dbf86-161">Par conséquent, la quantité est 20.</span><span class="sxs-lookup"><span data-stu-id="dbf86-161">Therefore, the quantity is 20.</span></span>




