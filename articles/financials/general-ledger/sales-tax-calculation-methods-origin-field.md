---
title: "Méthodes de calcul de la taxe dans le champ Origine"
description: "Cet article décrit les options du champ Origine dans la page de codes taxe et la manière dont la taxe est calculée selon l'option sélectionnée pour un code taxe."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4c1e1a588e07b9f60880dcf1c34139c5c1ceba35
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="sales-tax-calculation-methods-in-the-origin-field"></a><span data-ttu-id="0de4b-103">Méthodes de calcul de la taxe dans le champ Origine</span><span class="sxs-lookup"><span data-stu-id="0de4b-103">Sales tax calculation methods in the Origin field</span></span>

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [retail name](../includes/retail-name.md)]

<span data-ttu-id="0de4b-104">Cet article décrit les options du champ Origine dans la page de codes taxe et la manière dont la taxe est calculée selon l'option sélectionnée pour un code taxe.</span><span class="sxs-lookup"><span data-stu-id="0de4b-104">This article explains the options in the Origin field on the sales tax codes page and how sales tax is calculated based on the selected option for a sales tax code.</span></span>

<span data-ttu-id="0de4b-105">Pour chaque code taxe créé dans la page Codes taxe, vous devez sélectionner la méthode de calcul à appliquer au montant de base de la taxe dans le champ Origine.</span><span class="sxs-lookup"><span data-stu-id="0de4b-105">For each sales tax code that you create in the Sales tax codes page, you must select the method of calculation to apply to the tax base amount in the Origin field.</span></span>

## <a name="percentage-of-net-amount"></a><span data-ttu-id="0de4b-106">Pourcentage du montant HT</span><span class="sxs-lookup"><span data-stu-id="0de4b-106">Percentage of net amount</span></span>
<span data-ttu-id="0de4b-107">La méthode de calcul Pourcentage du montant HT est la valeur par défaut dans le champ Origine.</span><span class="sxs-lookup"><span data-stu-id="0de4b-107">The Percentage of net amount calculation method is the default value in the Origin field.</span></span> <span data-ttu-id="0de4b-108">La taxe est calculée comme un pourcentage du montant d'achat ou de vente (hors taxe).</span><span class="sxs-lookup"><span data-stu-id="0de4b-108">The sales tax is calculated as a percentage of the purchase or sales amount, excluding any other sales taxes.</span></span>
### <a name="example"></a><span data-ttu-id="0de4b-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="0de4b-109">Example</span></span>

<span data-ttu-id="0de4b-110">Le taux de taxe est de 25 %.</span><span class="sxs-lookup"><span data-stu-id="0de4b-110">The tax rate is 25%.</span></span> <span data-ttu-id="0de4b-111">La ligne de facture affiche une quantité de 10 articles à 1 € pièce et le client peut prétendre à 10 % de remise ligne.</span><span class="sxs-lookup"><span data-stu-id="0de4b-111">The invoice line shows a quantity of 10 items at 1.00 each, and the customer is allowed a 10% line discount.</span></span> <span data-ttu-id="0de4b-112">Montant HT : (10 x 1,00) - 10 % = 9,00 Taxe : 9,00 x 25 % = 2,25 Montant total : 9,00 + 2,25 = 11,25</span><span class="sxs-lookup"><span data-stu-id="0de4b-112">Net amount: (10 x 1.00) -10% = 9.00 Sales tax: 9.00 x 25% = 2.25 Total amount: 9.00 + 2.25 = 11.25</span></span>

## <a name="percentage-of-gross-amount"></a><span data-ttu-id="0de4b-113"> Pourcentage du montant brut</span><span class="sxs-lookup"><span data-stu-id="0de4b-113">Percentage of gross amount</span></span>
<span data-ttu-id="0de4b-114">Si vous sélectionnez la méthode Pourcentage du montant brut, la taxe est calculée comme un pourcentage du chiffre d'affaires brut.</span><span class="sxs-lookup"><span data-stu-id="0de4b-114">If you select the Percentage of gross amount method, the sales tax is calculated as a percentage of the gross sales amount.</span></span> <span data-ttu-id="0de4b-115">Le montant brut est le montant HT de la ligne plus l'ensemble des taxes et frais pour la ligne à l'exception de la taxe indiquant Origine = Pourcentage du montant brut.</span><span class="sxs-lookup"><span data-stu-id="0de4b-115">The gross amount is the line net amount plus all taxes and fees for the line except the one tax with Origin = Percentage of gross amount.</span></span>
### <a name="example"></a><span data-ttu-id="0de4b-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="0de4b-116">Example</span></span>

<span data-ttu-id="0de4b-117">L'administration fiscale impose des droits de douanes spéciaux sur un article.</span><span class="sxs-lookup"><span data-stu-id="0de4b-117">The tax authority has imposed special duties on an item.</span></span> <span data-ttu-id="0de4b-118">Le montant des droits de douanes est ajouté au montant HT avant le calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="0de4b-118">The duty amounts are added to the net amount before sales tax is calculated.</span></span> <span data-ttu-id="0de4b-119">Prenons les codes taxe suivants :</span><span class="sxs-lookup"><span data-stu-id="0de4b-119">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="0de4b-120">DROITS DE DOUANE 1 = 10 %, à l'aide de la méthode de calcul Pourcentage du montant HT</span><span class="sxs-lookup"><span data-stu-id="0de4b-120">DUTY 1 = 10%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="0de4b-121">DROITS DE DOUANE 2 = 20 %, à l'aide de la méthode de calcul Pourcentage du montant HT</span><span class="sxs-lookup"><span data-stu-id="0de4b-121">DUTY 2 = 20%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="0de4b-122">TAXE = 25 %, à l'aide de la méthode de calcul Pourcentage du montant brut</span><span class="sxs-lookup"><span data-stu-id="0de4b-122">SALESTAX = 25%, using the Percentage of gross amount calculation method</span></span>

<span data-ttu-id="0de4b-123">Si le montant HT = 10,00, alors les DROITS DE DOUANE 1 = 1,00 (10,00 x 10 %) et les DROITS DE DOUANE 2 = 2,00 (10,00 x 20 %).</span><span class="sxs-lookup"><span data-stu-id="0de4b-123">If the net amount is 10.00, then DUTY 1 is 1.00 (10.00 x 10%) and DUTY 2 = 2.00 (10.00 x 20%).</span></span> <span data-ttu-id="0de4b-124">Les montants sont les suivants : Montant brut = Montant HT + montant DROITS DE DOUANE 1 + montant DROITS DE DOUANE 2 (10,00 + 1,00 + 2,00) = 13,00 TAXE = 13,00 x 25 % = 3,25 Total DROITS DE DOUANE et TAXE = 1,00 + 2,00 + 3,25 = 6,25 Montant total = 10,00 + 6,25 = 16,25</span><span class="sxs-lookup"><span data-stu-id="0de4b-124">The amounts would be as follows: Gross amount: Net amount + DUTY 1 amount + DUTY 2 amount (10.00 + 1.00 + 2.00) = 13.00 SALESTAX = 13.00 x 25% = 3.25 Total DUTIES and SALESTAX: 1.00 + 2.00 + 3.25 = 6.25 Total amount: 10.00 + 6.25 = 16.25</span></span>

| <span data-ttu-id="0de4b-125">**Remarque**</span><span class="sxs-lookup"><span data-stu-id="0de4b-125">**Note**</span></span>                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0de4b-126">Un seul code taxe avec Origine = Pourcentage du montant brut peut être utilisé pour une transaction.</span><span class="sxs-lookup"><span data-stu-id="0de4b-126">Only one tax code with Origin = Percentage of gross amount can be used for a transaction.</span></span> <span data-ttu-id="0de4b-127">Si plusieurs codes taxe sont déterminés pour une transaction, une erreur s'affiche pour indiquer que la taxe ne peut pas être calculée.</span><span class="sxs-lookup"><span data-stu-id="0de4b-127">If more than one such tax code is determined for a transaction an error will be displayed that sales tax cannot be calculated.</span></span> |


<a name="percentage-of-sales-tax"></a><span data-ttu-id="0de4b-128">Pourcentage de taxe</span><span class="sxs-lookup"><span data-stu-id="0de4b-128">Percentage of sales tax</span></span>
-----------------------

<span data-ttu-id="0de4b-129">Lorsque vous sélectionnez Pourcentage de taxe dans le champ Origine, la taxe est calculée comme un pourcentage de la taxe sélectionnée dans le champ Taxe sur taxe.</span><span class="sxs-lookup"><span data-stu-id="0de4b-129">When you select Percentage of sales tax in the Origin field, sales tax is calculated as a percentage of the sales tax that is selected in the Sales tax on sales tax field.</span></span> <span data-ttu-id="0de4b-130">La taxe sélectionnée dans le champ Taxe sur taxe est d'abord calculée.</span><span class="sxs-lookup"><span data-stu-id="0de4b-130">The sales tax that is selected in the Sales tax on sales tax field is calculated first.</span></span> <span data-ttu-id="0de4b-131">La deuxième taxe est ensuite calculée en fonction du montant de la première taxe.</span><span class="sxs-lookup"><span data-stu-id="0de4b-131">The second sales tax is then calculated based on the first sales tax amount.</span></span>
### <a name="example"></a><span data-ttu-id="0de4b-132">Exemple</span><span class="sxs-lookup"><span data-stu-id="0de4b-132">Example</span></span>

<span data-ttu-id="0de4b-133">Prenons les codes taxe suivants :</span><span class="sxs-lookup"><span data-stu-id="0de4b-133">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="0de4b-134">DROITS DE DOUANE 1 = 10 %, à l'aide de la méthode Pourcentage du montant HT</span><span class="sxs-lookup"><span data-stu-id="0de4b-134">DUTY 1 = 10%, using the Percentage of net amount method</span></span>
-   <span data-ttu-id="0de4b-135">DROITS DE DOUANE 2 = 20 %, à l'aide de la méthode Pourcentage de taxe, avec Droits de douane 1 dans le champ Taxe sur taxe</span><span class="sxs-lookup"><span data-stu-id="0de4b-135">DUTY 2 = 20%, using the Percentage of sales tax method, with Duty 1 in the Sales tax on sales tax field</span></span>
-   <span data-ttu-id="0de4b-136">TAXE = 25 %, à l'aide de la méthode Pourcentage du montant brut</span><span class="sxs-lookup"><span data-stu-id="0de4b-136">SALESTAX = 25%, using the Percentage of gross amount method</span></span>

<span data-ttu-id="0de4b-137">Montant HT = 10,00 DROITS DE DOUANE 1 = 10,00 x 10 % = 1,00 DROITS DE DOUANE 2 = 1,00 x 20 % = 0,20 Montant brut = 10,00 + 1,00 + 0,20 = 11,20 TAXE = 11,20 x 25 % = 2,80 Total DROITS DE DOUANE et TAXE = 1,00 + 0,20 + 2,80 = 4,00 Montant total = 10,00 + 4,00 = 14,00</span><span class="sxs-lookup"><span data-stu-id="0de4b-137">Net amount: 10.00 DUTY 1: 10.00 x 10% = 1.00 DUTY 2: 1.00 x 20% = 0.20 Gross amount: 10.00 + 1.00 + 0.20 = 11.20 SALESTAX: 11.20 x 25% = 2.80 Total DUTIES and SALESTAX: 1.00 + 0.20 + 2.80 = 4.00 Total amount: 10.00 + 4.00 = 14.00</span></span>

| <span data-ttu-id="0de4b-138">**Remarque**</span><span class="sxs-lookup"><span data-stu-id="0de4b-138">**Note**</span></span>                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0de4b-139">Les calculs de taxe sur taxe à plusieurs niveaux ne sont pas possibles.</span><span class="sxs-lookup"><span data-stu-id="0de4b-139">Multilevel tax on tax calculations are not possible.</span></span> <span data-ttu-id="0de4b-140">Une taxe ne peut pas être calculée sur la base d'une taxe qui est déjà calculée sur la base d'une autre taxe.</span><span class="sxs-lookup"><span data-stu-id="0de4b-140">A tax cannot be calculated based on a tax which already is calculated based on another tax.</span></span> <span data-ttu-id="0de4b-141">Plusieurs codes de taxe sur taxe à niveau unique peuvent être calculés sur une transaction.</span><span class="sxs-lookup"><span data-stu-id="0de4b-141">Multiple single level tax on tax codes can be calculated on a transaction.</span></span> |

## <a name="amount-per-unit"></a><span data-ttu-id="0de4b-142"> Montant par unité</span><span class="sxs-lookup"><span data-stu-id="0de4b-142">Amount per unit</span></span>
<span data-ttu-id="0de4b-143">Lorsque vous sélectionnez Montant par unité dans le champ Origine, la taxe est calculée comme un montant fixe par unité multiplié par la quantité entrée dans la ligne de document.</span><span class="sxs-lookup"><span data-stu-id="0de4b-143">When you select Amount per unit in the Origin field, sales tax is calculated as a fixed amount per unit multiplied with the quantity entered on the document line.</span></span> <span data-ttu-id="0de4b-144">Une unité doit être sélectionnée dans le champ Unité.</span><span class="sxs-lookup"><span data-stu-id="0de4b-144">A unit has to be selected in the Unit field.</span></span> <span data-ttu-id="0de4b-145">Le montant par unité est spécifié dans la page Valeurs de code taxe.</span><span class="sxs-lookup"><span data-stu-id="0de4b-145">The amount per unit is specified in the Sales tax code values page.</span></span>
### <a name="example"></a><span data-ttu-id="0de4b-146">Exemple</span><span class="sxs-lookup"><span data-stu-id="0de4b-146">Example</span></span>

<span data-ttu-id="0de4b-147">Le code taxe est paramétré comme suit : 1,20 EUR par unité = boîte Sur une ligne de facture client, 25 boîtes d'un article sont vendues La taxe est calculée comme suit = 25 x 1,20 = 30,00</span><span class="sxs-lookup"><span data-stu-id="0de4b-147">Sales tax code is set up as: USD 1.20 per unit = box On a sales invoice line 25 boxes of an item are sold Sales tax is calculated as 25 x 1.20 = 30.00</span></span>

| <span data-ttu-id="0de4b-148">**Remarque**</span><span class="sxs-lookup"><span data-stu-id="0de4b-148">**Note**</span></span>                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0de4b-149">Si la transaction est entrée dans une unité autre que l'unité spécifiée sur le code taxe, elle est automatiquement convertie en fonction des conversions d'unités paramétrées dans la page Conversion d'unités.</span><span class="sxs-lookup"><span data-stu-id="0de4b-149">If the transaction is entered in different unit than the unit specified on the sales tax code, it is converted automatically based on the unit conversions that are set up in the Unit conversions page.</span></span> |

###  <a name="amount-per-unit-additional-option"></a><span data-ttu-id="0de4b-150"> Montant par unité, option supplémentaire</span><span class="sxs-lookup"><span data-stu-id="0de4b-150">Amount per unit, additional option</span></span>

<span data-ttu-id="0de4b-151">Sous l'onglet Calcul, vous pouvez choisir si une taxe calculée Montant par unité est calculée avant d'autres codes taxe et ajoutée au montant HT avant que d'autres codes taxe avec Origine = Pourcentage du montant HT soient calculés.</span><span class="sxs-lookup"><span data-stu-id="0de4b-151">On the Calculation tab, you can select whether an amount per unit calculated tax is calculated before other tax codes and added to the net amount before other tax codes with Origin = Percentage of net amount are calculated.</span></span>

### <a name="examples"></a><span data-ttu-id="0de4b-152">Exemples</span><span class="sxs-lookup"><span data-stu-id="0de4b-152">Examples</span></span>

<span data-ttu-id="0de4b-153">Supposons que nous calculions 2 codes taxe sur une transaction :</span><span class="sxs-lookup"><span data-stu-id="0de4b-153">Assume we calculate 2 tax codes on a transaction:</span></span>

-   <span data-ttu-id="0de4b-154">DROITS DE DOUANE : Origine = Montant par unité et une taxe, la valeur est définie sur 5,00 par unité = pcs</span><span class="sxs-lookup"><span data-stu-id="0de4b-154">DUTY: Origin = Amount per unit and a sales tax, the value is set to 5.00 per unit = pcs</span></span>
-   <span data-ttu-id="0de4b-155">TAXE : Origine = comme indiqué dans les exemples ci-dessous, la valeur est définie sur 25 %</span><span class="sxs-lookup"><span data-stu-id="0de4b-155">SALESTAX: Origin = as shown in the examples below, the value is set to 25%</span></span>

<span data-ttu-id="0de4b-156">Nous vendons 1 article à un prix unitaire de 10,00</span><span class="sxs-lookup"><span data-stu-id="0de4b-156">We sell 1 piece of an item at a unit price of 10.00</span></span>
#### <a name="example-1"></a><span data-ttu-id="0de4b-157">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="0de4b-157">Example 1</span></span>

<span data-ttu-id="0de4b-158">TAXE : Origine = Méthode Pourcentage du montant brut L'option Calculer avant la taxe n'a aucun effet, car la TAXE est calculée comme un pourcentage du montant brut.</span><span class="sxs-lookup"><span data-stu-id="0de4b-158">SALESTAX: Origin = Percentage of gross amount method The Calculate before sales tax option has no effect, because SALESTAX is calculated as a percentage of the gross amount.</span></span> <span data-ttu-id="0de4b-159">DROITS DE DOUANE = 1 x 5,00 = 5,00 Montant brut = 10,00 + 5,00 = 15,00 TAXE = 15,00 x 25 % = 3,75 Taxe totale = 5,00 + 3,75 = 8,75 Montant total = 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="0de4b-159">DUTY: 1 x 5.00 = 5.00 Gross amount: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-2"></a><span data-ttu-id="0de4b-160">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="0de4b-160">Example 2</span></span>

<span data-ttu-id="0de4b-161">TAXE : Origine = Pourcentage du montant HT L'option Calculer avant la taxe n'est pas sélectionnée pour le calcul des DROITS DE DOUANE.</span><span class="sxs-lookup"><span data-stu-id="0de4b-161">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is not selected for the DUTY calculation.</span></span> <span data-ttu-id="0de4b-162">Montant HT = 10,00 DROITS DE DOUANE = 1 x 5,00 = 5,00 TAXE = 10,00 x 25 % = 2,50 Taxe totale = 5,00 + 2,50 = 7,50 Montant total = 10,00 + 7,50 = 17,50</span><span class="sxs-lookup"><span data-stu-id="0de4b-162">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: 10.00 x 25% = 2.50 Total sales tax: 5.00 + 2.50 = 7.50 Total amount: 10.00 + 7.50 = 17.50</span></span>

#### <a name="example-3"></a><span data-ttu-id="0de4b-163">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="0de4b-163">Example 3</span></span>

<span data-ttu-id="0de4b-164">TAXE : Origine = Pourcentage du montant HT L'option Calculer avant la taxe est sélectionnée pour le calcul des DROITS DE DOUANE.</span><span class="sxs-lookup"><span data-stu-id="0de4b-164">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is selected for the DUTY calculation.</span></span> <span data-ttu-id="0de4b-165">Montant HT = 10,00 DROITS DE DOUANE = 1 x 5,00 = 5,00 TAXE = (10,00 + 5,00) x 25 % = 3,75 Taxe totale = 5,00 + 3,75 = 8,75 Montant total = 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="0de4b-165">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: (10.00 + 5.00) x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-4"></a><span data-ttu-id="0de4b-166">Exemple 4</span><span class="sxs-lookup"><span data-stu-id="0de4b-166">Example 4</span></span>

<span data-ttu-id="0de4b-167">Les résultats des exemples 1 et 3 sont les mêmes car il n'impliquent pas plusieurs droits de douanes.</span><span class="sxs-lookup"><span data-stu-id="0de4b-167">The result of Example 3 and Example 1 is the same, because there is only one duty.</span></span> <span data-ttu-id="0de4b-168">Supposez que vous ayez deux DROITS DE DOUANE et un seul est inclus dans le montant HT pour le calcul de la taxe : DROITS DE DOUANE 1 = 5,00, à l'aide de la méthode Montant par unité, et l'option Calculer avant la taxe est sélectionnée DROITS DE DOUANE 2 = 2,50, à l'aide de la méthode Montant par unité, et l'option Calculer avant la taxe n'est pas sélectionnée Taxe = 25 %, à l'aide de la méthode Pourcentage du montant HT Montant HT = 10,00 DROITS DE DOUANE 1 = 1 x 5,00 = 5,00 DROITS DE DOUANE 2 = 1 x 2,50 = 2,50 Montant HT soumis à la taxe = 10,00 + 5,00 = 15,00 TAXE = 15,00 x 25 % = 3,75 Taxes totales, droits de douanes inclus = 5,00 + 2,50 + 3,75 = 11,25 Montant total = 10,00 + 11,25 = 21,25 La TAXE de 25 % est calculée pour la somme du montant HT (10,00) + DROITS DE DOUANE 1 (5,00) = 15,00.</span><span class="sxs-lookup"><span data-stu-id="0de4b-168">Assume that you have two DUTIES, and only one of them is included in the net amount for the sales tax calculation: DUTY 1: 5.00, using the Amount per unit method, and the Calculate before sales tax option is selected DUTY 2: 2.50, using the Amount per unit method, and the Calculate before sales tax option is not selected Sales tax: 25%, using the Percentage of net amount method Net amount: 10.00 DUTY 1: 1 x 5.00 = 5.00 DUTY 2: 1 x 2.50 = 2.50 Net amount subject to sales tax: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales taxes, including duties: 5.00 + 2.50 + 3.75 = 11.25 Total amount: 10.00 + 11.25 = 21.25 The 25% SALESTAX is calculated for the sum of the net amount (10.00) + DUTY 1 (5.00) = 15.00.</span></span> <span data-ttu-id="0de4b-169">Les DROITS DE DOUANE 2 sont ajoutés au montant de la taxe après le calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="0de4b-169">DUTY 2 is added to the tax amount after the sales tax is calculated.</span></span>

## <a name="calculated-percentage-of-net-amount"></a><span data-ttu-id="0de4b-170"> Pourcentage calculé du montant HT</span><span class="sxs-lookup"><span data-stu-id="0de4b-170">Calculated percentage of net amount</span></span>
<span data-ttu-id="0de4b-171">Le pourcentage calculé du montant HT gère le calcul de la taxe différemment selon la définition du paramètre Montants, taxe incluse pour le document ou le journal.</span><span class="sxs-lookup"><span data-stu-id="0de4b-171">The Calculated percentage of net amount handles tax calculation differently depending on the setting of the Amounts include sales tax parameter for the document or journal.</span></span>
### <a name="example-1"></a><span data-ttu-id="0de4b-172">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="0de4b-172">Example 1</span></span>

<span data-ttu-id="0de4b-173">Le document ou journal est défini sur Montants, taxe incluse = Oui Montant de la ligne de transaction = 10,00 Taux de taxe = Taxe de 25 % Montant de la ligne de transaction x taux de taxe (10,00 x 25 %) = 2,50 Montant de base de la taxe (montant d'origine) = Montant de la ligne de transaction - Taxe (10,00 - 2,50) = 7,50</span><span class="sxs-lookup"><span data-stu-id="0de4b-173">Document / journal is set to Amounts include sales tax = Yes Transaction line amount: 10.00 Tax rate: 25% Sales tax: Transaction line amount x tax rate (10.00 x 25%) = 2.50 Tax base amount (origin amount): Transaction line amount - Sales tax (10.00 - 2.50) = 7.50</span></span>

### <a name="example-2"></a><span data-ttu-id="0de4b-174">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="0de4b-174">Example 2</span></span>

<span data-ttu-id="0de4b-175">Le document ou journal est défini sur Montants, taxe incluse = Non Montant de la ligne de transaction = 10,00 Taux de taxe = Taxe de 25 % (Montant de la ligne de transaction x taux de taxe) / (100 - taux de taxe) (10,00 x 25 %) / (100 % - 25 %) = 3,33 Montant de base de la taxe (montant d'origine) = Montant de la ligne de transaction = 10,00</span><span class="sxs-lookup"><span data-stu-id="0de4b-175">Document / journal is set to Amounts include sales tax = No Transaction line amount: 10.00 Tax rate: 25% Sales tax: (Transaction line amount x tax rate) / (100 - tax rate) (10.00 x 25%) / (100% - 25%) = 3.33 Tax base amount (origin amount): Transaction line amount = 10.00</span></span>



<a name="see-also"></a><span data-ttu-id="0de4b-176">Voir également :</span><span class="sxs-lookup"><span data-stu-id="0de4b-176">See also</span></span>
--------

[<span data-ttu-id="0de4b-177">Détermination des taux de taxe en fonction des champs Base marginale et Mode de calcul</span><span class="sxs-lookup"><span data-stu-id="0de4b-177">Determining sale tax rates based on the Marginal base and Calculation method fields</span></span>](marginal-base-field.md)

[<span data-ttu-id="0de4b-178">Options de calcul Montant entier et Intervalle pour les codes taxe</span><span class="sxs-lookup"><span data-stu-id="0de4b-178">Whole amount and Interval calculation options for sales tax codes</span></span>](whole-amount-interval-options-sales-tax-codes.md)




