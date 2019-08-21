---
title: Taux de taxe en fonction de la Base marginale et du Mode de calcul
description: Cette rubrique décrit comment les valeurs des champs Base marginale et Mode de calcul déterminent les taux de taxe dans les transactions de vente et d'achat.
author: ShylaThompson
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 34e7e3f37d759953b7b4f70fe9eae78154da44d1
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846845"
---
# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a><span data-ttu-id="1b1ce-103">Taux de taxe en fonction de la Base marginale et du Mode de calcul</span><span class="sxs-lookup"><span data-stu-id="1b1ce-103">Sales tax rates based on the Marginal base and Calculation methods</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1b1ce-104">Cette rubrique décrit comment les valeurs des champs Base marginale et Mode de calcul déterminent les taux de taxe dans les transactions de vente et d'achat.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-104">This topic explains how the values in the fields Marginal base and Calculation method determine the tax rate(s) in sales and purchase transactions.</span></span>

<span data-ttu-id="1b1ce-105">La base marginale dans l'organisateur Calcul de la page Codes taxe détermine le montant utilisé pour le choix appropriés du (des) taux de taxe à partir des taux de la page Valeur de code taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-105">The Marginal base on the Calculation FastTab on the Sales tax codes page determines which amount is used to pick the appropriate tax rate(s) from the rates in the Sales tax code values page.</span></span> <span data-ttu-id="1b1ce-106">Le type de montant dans le champ Base marginale, combinée avec la méthode du champ Mode de calcul détermine la logique permettant de rechercher le (les) taux de taxe corrects pour une transaction.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-106">The amount type in the Marginal base field in combination with the method in the Calculation method field determines the logic to find the correct tax rate(s) for a transaction.</span></span> 

<span data-ttu-id="1b1ce-107">Diverses combinaisons de valeurs dans ces champs produisent des calculs de la taxe très différents, comme le montrent les exemples suivants.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-107">Various combinations of values in these fields produce very different sales tax calculations, as shown by the following examples.</span></span> <span data-ttu-id="1b1ce-108">Les exemples utilisent les mêmes valeurs d'intervalle de taxe qui sont paramétrées pour chaque code taxe sur la page Valeurs de codes taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-108">The examples use the same tax interval values, which are set up for each tax code in the Sales tax codes values page.</span></span> <span data-ttu-id="1b1ce-109">Pour ouvrir cette page, cliquez sur Code taxe &gt; Valeurs sur la page Codes taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-109">To open this page, click Sales tax code &gt; Values in the Sales tax codes page.</span></span>

> [!Important]                                                                                                                  
> <span data-ttu-id="1b1ce-110">Si la base marginale sur un ou plusieurs de vos codes taxe est basée sur des montants de ligne ou des unités, la valeur du champ Mode de calcul de la page Paramètres de comptabilité doit être définie à Ligne.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-110">If the Marginal base on one or more of your sales tax codes is based on line amounts or units, the value of the Calculation method field in the General ledger parameters page must be set to Line.</span></span> |

## <a name="net-amount-per-line"></a><span data-ttu-id="1b1ce-111">Montant HT par ligne</span><span class="sxs-lookup"><span data-stu-id="1b1ce-111">Net amount per line</span></span>
<span data-ttu-id="1b1ce-112">Cette option permet de déterminer les taux de taxe sur la base du montant HT des lignes de facture, à l'exclusion de toute autre taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-112">Select this option to determine sales tax rates based on the net amount for the invoice lines, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="1b1ce-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="1b1ce-113">Example</span></span>

<span data-ttu-id="1b1ce-114">Les taux de taxe sont paramétrés dans les intervalles suivants :</span><span class="sxs-lookup"><span data-stu-id="1b1ce-114">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="1b1ce-115">Intervalle de montant</span><span class="sxs-lookup"><span data-stu-id="1b1ce-115">Amount interval</span></span>    | <span data-ttu-id="1b1ce-116">Taux de la taxe</span><span class="sxs-lookup"><span data-stu-id="1b1ce-116">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="1b1ce-117">0 à 50</span><span class="sxs-lookup"><span data-stu-id="1b1ce-117">0 - 50</span></span>             | <span data-ttu-id="1b1ce-118">30 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-118">30%</span></span>      |
| <span data-ttu-id="1b1ce-119">50 à 100</span><span class="sxs-lookup"><span data-stu-id="1b1ce-119">50 - 100</span></span>           | <span data-ttu-id="1b1ce-120">20 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-120">20%</span></span>      |
| <span data-ttu-id="1b1ce-121">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="1b1ce-121">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="1b1ce-122">10 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-122">10%</span></span>      |

> [!NOTE]                                                                                                             
> <span data-ttu-id="1b1ce-123">La limite supérieure 0 (zéro) dans le dernier intervalle signifie que tous les montants supérieurs à 100 sont inclus dans l'intervalle.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-123">The upper limit of zero (0) in the last interval means that all amounts that exceed 100 are included in the interval.</span></span>

<span data-ttu-id="1b1ce-124">Base marginale : **Montant HT par ligne**</span><span class="sxs-lookup"><span data-stu-id="1b1ce-124">Marginal base: **Net amount per line**</span></span> 

<span data-ttu-id="1b1ce-125">Mode de calcul : **Intervalle**</span><span class="sxs-lookup"><span data-stu-id="1b1ce-125">Calculation method: **Interval**</span></span> 

<span data-ttu-id="1b1ce-126">Vous achetez 8 lampes à 25,00 pièce.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-126">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="1b1ce-127">Le montant HT de la ligne de facture est de 200 euros.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-127">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="1b1ce-128">La taxe est calculée comme suit :</span><span class="sxs-lookup"><span data-stu-id="1b1ce-128">The tax is calculated as follows:</span></span> 

<span data-ttu-id="1b1ce-129">Taxe totale = 50 x 30 % + 50 x 20 % + 100 x 10 % = 15 + 10 + 10 = 35,00 euros</span><span class="sxs-lookup"><span data-stu-id="1b1ce-129">Total sales tax = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35.00</span></span> 

<span data-ttu-id="1b1ce-130">Montant total de la facture = 200,00 + 35,00 = 235,00 euros</span><span class="sxs-lookup"><span data-stu-id="1b1ce-130">Total invoice amount = 200.00 + 35.00 = 235.00</span></span> 

<span data-ttu-id="1b1ce-131">**Variante**</span><span class="sxs-lookup"><span data-stu-id="1b1ce-131">**Variation**</span></span> 

<span data-ttu-id="1b1ce-132">Si la facture dispose de deux lignes de 4 articles chacune, le montant HT par ligne est de 100,00 euros, et la taxe est calculée comme suit :</span><span class="sxs-lookup"><span data-stu-id="1b1ce-132">If the invoice has two lines with four items on each line, the net amount on each line is 100.00 and the sales tax is calculated as follows:</span></span> 

<span data-ttu-id="1b1ce-133">Ligne de taxe 1 = 50 x 30 % + 50 x 20 % = 15 + 10 = 25,00 euros</span><span class="sxs-lookup"><span data-stu-id="1b1ce-133">Sales tax line 1 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="1b1ce-134">Ligne de taxe 2 = 50 x 30 % + 50 x 20 % = 15 + 10 = 25,00 euros</span><span class="sxs-lookup"><span data-stu-id="1b1ce-134">Sales tax line 2 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="1b1ce-135">Taxe totale = 25,00 + 25,00 = 50,00</span><span class="sxs-lookup"><span data-stu-id="1b1ce-135">Total sales tax = 25.00 + 25.00 = 50.00</span></span> 

<span data-ttu-id="1b1ce-136">Montant total de la facture = 200,00 + 50,00 = 250,00 euros</span><span class="sxs-lookup"><span data-stu-id="1b1ce-136">Total invoice amount = 200.00 + 50.00 = 250.00</span></span>

## <a name="net-amount-per-unit"></a><span data-ttu-id="1b1ce-137">Montant HT par unité</span><span class="sxs-lookup"><span data-stu-id="1b1ce-137">Net amount per unit</span></span>
<span data-ttu-id="1b1ce-138">Cette option permet de déterminer les taux de taxe en fonction de la valeur de chaque unité, à l'exclusion de toute autre taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-138">Select this option to determine sales tax rates based on the value of each unit, excluding any other taxes.</span></span> <span data-ttu-id="1b1ce-139">Lorsqu'une base marginale basée sur les unités est sélectionnée, alors une unité doit également être spécifiée pour le code taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-139">When a unit based Marginal base is selected then also a Unit has to be specified for the Sales tax code.</span></span>

### <a name="example"></a><span data-ttu-id="1b1ce-140">Exemple</span><span class="sxs-lookup"><span data-stu-id="1b1ce-140">Example</span></span>

<span data-ttu-id="1b1ce-141">Les taux de taxe sont paramétrés dans les intervalles suivants :</span><span class="sxs-lookup"><span data-stu-id="1b1ce-141">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="1b1ce-142">Montant</span><span class="sxs-lookup"><span data-stu-id="1b1ce-142">Amount</span></span>             | <span data-ttu-id="1b1ce-143">Taux de la taxe</span><span class="sxs-lookup"><span data-stu-id="1b1ce-143">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="1b1ce-144">0 à 50</span><span class="sxs-lookup"><span data-stu-id="1b1ce-144">0 - 50</span></span>             | <span data-ttu-id="1b1ce-145">30 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-145">30%</span></span>      |
| <span data-ttu-id="1b1ce-146">50 à 100</span><span class="sxs-lookup"><span data-stu-id="1b1ce-146">50 - 100</span></span>           | <span data-ttu-id="1b1ce-147">20 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-147">20%</span></span>      |
| <span data-ttu-id="1b1ce-148">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="1b1ce-148">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="1b1ce-149">10 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-149">10%</span></span>      |

<span data-ttu-id="1b1ce-150">Base marginale : **Montant HT par unité**</span><span class="sxs-lookup"><span data-stu-id="1b1ce-150">Marginal base: **Net amount per unit**</span></span> 

<span data-ttu-id="1b1ce-151">Mode de calcul : **Montant entier**</span><span class="sxs-lookup"><span data-stu-id="1b1ce-151">Calculation method: **Whole amount**</span></span> 

<span data-ttu-id="1b1ce-152">Vous achetez 8 lampes à 25,00 pièce.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-152">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="1b1ce-153">Le montant HT de la ligne de facture est de 200 euros.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-153">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="1b1ce-154">La taxe est calculée comme suit : Taxe par unité = 25,00 = 30 % x 7,50 Taxe totale = 7,50 x 8 unités = 60,00 Montant total facturé = 200,00 + 60,00 = 260,00</span><span class="sxs-lookup"><span data-stu-id="1b1ce-154">The tax is calculated as follows: Sales tax per unit = 25.00 x 30% = 7.50 Total sales tax = 7.50 x 8 units = 60.00 Total invoice amount = 200.00 + 60.00 = 260.00</span></span>

## <a name="net-amount-of-invoice-balance"></a><span data-ttu-id="1b1ce-155">Montant HT du solde de la facture</span><span class="sxs-lookup"><span data-stu-id="1b1ce-155">Net amount of invoice balance</span></span>

<span data-ttu-id="1b1ce-156">Cette option permet de déterminer les taux de taxe en fonction de la valeur totale de la facture, à l'exclusion de toute autre taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-156">Select this option to determine sales tax rates based on the total value for the invoice, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="1b1ce-157">Exemple</span><span class="sxs-lookup"><span data-stu-id="1b1ce-157">Example</span></span>

<span data-ttu-id="1b1ce-158">Les taux de taxe sont paramétrés dans les intervalles suivants :</span><span class="sxs-lookup"><span data-stu-id="1b1ce-158">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="1b1ce-159">Montant</span><span class="sxs-lookup"><span data-stu-id="1b1ce-159">Amount</span></span>            | <span data-ttu-id="1b1ce-160">Taux de la taxe</span><span class="sxs-lookup"><span data-stu-id="1b1ce-160">Tax rate</span></span> |
|-------------------|----------|
| <span data-ttu-id="1b1ce-161">0 à 50</span><span class="sxs-lookup"><span data-stu-id="1b1ce-161">0 - 50</span></span>            | <span data-ttu-id="1b1ce-162">30 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-162">30%</span></span>      |
| <span data-ttu-id="1b1ce-163">50 à 100</span><span class="sxs-lookup"><span data-stu-id="1b1ce-163">50 - 100</span></span>          | <span data-ttu-id="1b1ce-164">20 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-164">20%</span></span>      |
| <span data-ttu-id="1b1ce-165">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="1b1ce-165">100 -0 (&gt; 100)</span></span> | <span data-ttu-id="1b1ce-166">10 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-166">10%</span></span>      |

<span data-ttu-id="1b1ce-167">Base marginale : **Montant HT du solde de la facture**</span><span class="sxs-lookup"><span data-stu-id="1b1ce-167">Marginal base: **Net amount of invoice balance**</span></span> 

<span data-ttu-id="1b1ce-168">Mode de calcul : **Intervalle** Une facture client a 2 lignes avec 4 lampes sur chaque ligne, à 25,00 chacune.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-168">Calculation method: **Interval** A sales invoice has 2 lines with 4 lamps on each lines for 25.00 each.</span></span> <span data-ttu-id="1b1ce-169">Le montant HT du solde de facture est 4 x 25,00 + 4 x 25,00 = 200,00.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-169">The net amount of invoice balance is 4 x 25.00 + 4 x 25.00 = 200.00.</span></span> <span data-ttu-id="1b1ce-170">La taxe est calculée comme suit : Taxe totale = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Montant total facturé = 200,00 + 35,00 = 235,00</span><span class="sxs-lookup"><span data-stu-id="1b1ce-170">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 100 x 0.10 = 15 + 10 + 10 = 35.00 Total invoice amount = 200.00 + 35.00 = 235.00</span></span>

## <a name="gross-amount-per-line"></a><span data-ttu-id="1b1ce-171">Montant brut par ligne</span><span class="sxs-lookup"><span data-stu-id="1b1ce-171">Gross amount per line</span></span>

<span data-ttu-id="1b1ce-172">Cette option permet de déterminer les taux de taxe en fonction de la valeur de la ligne, en incluant toute autre taxe pour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-172">Select this option to determine sales tax rates based on the value of the line including all other taxes for that line.</span></span>

> [!NOTE]
> <span data-ttu-id="1b1ce-173">Dans un groupe de taxe, vous ne pouvez avoir qu'un seul code taxe avec cette sélection dans le champ Base marginale.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-173">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="1b1ce-174">Exemple</span><span class="sxs-lookup"><span data-stu-id="1b1ce-174">Example</span></span>

<span data-ttu-id="1b1ce-175">Les taux de taxe sont paramétrés dans les intervalles suivants :</span><span class="sxs-lookup"><span data-stu-id="1b1ce-175">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="1b1ce-176">Montant</span><span class="sxs-lookup"><span data-stu-id="1b1ce-176">Amount</span></span>             | <span data-ttu-id="1b1ce-177">Taux de la taxe</span><span class="sxs-lookup"><span data-stu-id="1b1ce-177">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="1b1ce-178">0 à 50</span><span class="sxs-lookup"><span data-stu-id="1b1ce-178">0 - 50</span></span>             | <span data-ttu-id="1b1ce-179">30 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-179">30%</span></span>      |
| <span data-ttu-id="1b1ce-180">50 à 100</span><span class="sxs-lookup"><span data-stu-id="1b1ce-180">50 - 100</span></span>           | <span data-ttu-id="1b1ce-181">20 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-181">20%</span></span>      |
| <span data-ttu-id="1b1ce-182">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="1b1ce-182">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="1b1ce-183">10 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-183">10%</span></span>      |

<span data-ttu-id="1b1ce-184">Base marginale : **Montant brut par ligne** Mode de calcul : **Intervalle** En outre, il existe un autre code taxe calculé pour un droit de douane spécial de 5,00 sur chaque lampe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-184">Marginal base: **Gross amount per line** Calculation method: **Interval** Additionally there is another tax code calculated for a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="1b1ce-185">Le droit est ajouté au montant HT avant le calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-185">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="1b1ce-186">Vous achetez 8 lampes à 25,00 pièce.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-186">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="1b1ce-187">Le montant HT de la ligne de facture est de 200 euros.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-187">The net amount for the invoice line is 200.00.</span></span> <span data-ttu-id="1b1ce-188">Le montant brut de la ligne de facture est 8 x 25,00 + 8 x 5,00 = 240,00.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-188">The gross amount for the invoice line is 8 x 25.00 + 8 x 5.00 = 240.00.</span></span> <span data-ttu-id="1b1ce-189">La taxe est calculée comme suit : Taxe totale = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 20 + 14 = 39,00 Total des droits de douane = 5,00 x 8 = 40,00 Montant total facturé = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="1b1ce-189">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 20 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="1b1ce-190">**Variante**</span><span class="sxs-lookup"><span data-stu-id="1b1ce-190">**Variation**</span></span> 

<span data-ttu-id="1b1ce-191">Si la facture est créée à l'aide de deux lignes de facture de 4 articles chacune, le montant HT par ligne de facture est EUR 100.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-191">If the invoice is created by using 2 invoice lines with 4 items on each line, the net amount per invoice line is 100.00.</span></span> <span data-ttu-id="1b1ce-192">Le montant brut (y compris le droit de douane de 4 x 5,00) par ligne de facture est 120,00, et la taxe est créée comme suit : Ligne de facture de taxe 1 = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Ligne de facture de taxe 2 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Taxe totale = 27,00 + 27,00 = 54,00 Total des droits de douane = 5,00 x 8 = 40,00 Montant total facturé = 200,00 + 54,00 + 40,00 = 294,00</span><span class="sxs-lookup"><span data-stu-id="1b1ce-192">The gross amount (including the duty of 4 x 5.00) per invoice line would be 120.00, and the sales tax is created as follows: Sales tax invoice line 1 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Sales tax invoice line 2 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Total sales tax = 27.00 + 27.00 = 54.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 54.00 + 40.00 = 294.00</span></span>

## <a name="gross-amount-per-unit"></a><span data-ttu-id="1b1ce-193">Montant brut par unité</span><span class="sxs-lookup"><span data-stu-id="1b1ce-193">Gross amount per unit</span></span>

<span data-ttu-id="1b1ce-194">Cette option permet de déterminer les taux de taxe en fonction de la valeur de l'unité, en incluant toute autre taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-194">Select this option to determine sales tax rates based on the value of the unit including any other taxes.</span></span>

> [!NOTE]
> <span data-ttu-id="1b1ce-195">Dans un groupe de taxe, vous ne pouvez avoir qu'un seul code taxe avec cette sélection dans le champ Base marginale.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-195">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="1b1ce-196">Exemple</span><span class="sxs-lookup"><span data-stu-id="1b1ce-196">Example</span></span>

<span data-ttu-id="1b1ce-197">Les taux de taxe sont paramétrés dans les intervalles suivants :</span><span class="sxs-lookup"><span data-stu-id="1b1ce-197">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="1b1ce-198">Montant</span><span class="sxs-lookup"><span data-stu-id="1b1ce-198">Amount</span></span>             | <span data-ttu-id="1b1ce-199">Taux de la taxe</span><span class="sxs-lookup"><span data-stu-id="1b1ce-199">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="1b1ce-200">0 à 50</span><span class="sxs-lookup"><span data-stu-id="1b1ce-200">0 - 50</span></span>             | <span data-ttu-id="1b1ce-201">30 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-201">30%</span></span>      |
| <span data-ttu-id="1b1ce-202">50 à 100</span><span class="sxs-lookup"><span data-stu-id="1b1ce-202">50 - 100</span></span>           | <span data-ttu-id="1b1ce-203">20 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-203">20%</span></span>      |
| <span data-ttu-id="1b1ce-204">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="1b1ce-204">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="1b1ce-205">10 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-205">10%</span></span>      |

<span data-ttu-id="1b1ce-206">Base marginale : **Montant brut par unité** Il existe un droit de douane spécial de 5,00 sur chaque lampe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-206">Marginal base: **Gross amount per unit** There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="1b1ce-207">Le droit est ajouté au montant HT avant le calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-207">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="1b1ce-208">Vous achetez 8 lampes à 25,00 pièce.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-208">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="1b1ce-209">Le montant brut par unité est 30,00.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-209">The gross amount per unit is 30.00.</span></span> <span data-ttu-id="1b1ce-210">La taxe est calculée comme suit : Taxe par unité = 30 x 30 % = 9,00 Taxe totale = 9,00 x 8 = 72,00 Total des droits de douane = 5,00 x 8 = 40,00 Montant total facturé = 200,00 + 72,00 + 40,00 = 312,00</span><span class="sxs-lookup"><span data-stu-id="1b1ce-210">The tax is calculated as follows: Sales tax per unit = 30 x 30% = 9.00 Total sales tax = 9.00 x 8 = 72.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 72.00 + 40.00 = 312.00</span></span>

## <a name="invoice-total-incl-other-sales-tax-amounts"></a><span data-ttu-id="1b1ce-211">Facture totale, autres taxe incluses</span><span class="sxs-lookup"><span data-stu-id="1b1ce-211">Invoice total incl. other sales tax amounts</span></span>

<span data-ttu-id="1b1ce-212">Cette option permet de déterminer les taux de taxe en fonction de la valeur totale de la facture, en incluant toute autre taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-212">Select this option to determine sales tax rates based on the total value for the invoice including any other taxes.</span></span>
> [!NOTE]
> <span data-ttu-id="1b1ce-213">Dans un groupe de taxe, vous ne pouvez avoir qu'un seul code taxe avec cette sélection dans le champ Base marginale</span><span class="sxs-lookup"><span data-stu-id="1b1ce-213">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field</span></span>

### <a name="example"></a><span data-ttu-id="1b1ce-214">Exemple</span><span class="sxs-lookup"><span data-stu-id="1b1ce-214">Example</span></span>

<span data-ttu-id="1b1ce-215">Les taux de taxe sont paramétrés dans les intervalles suivants :</span><span class="sxs-lookup"><span data-stu-id="1b1ce-215">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="1b1ce-216">Montant</span><span class="sxs-lookup"><span data-stu-id="1b1ce-216">Amount</span></span>             | <span data-ttu-id="1b1ce-217">Taux de la taxe</span><span class="sxs-lookup"><span data-stu-id="1b1ce-217">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="1b1ce-218">0 à 50</span><span class="sxs-lookup"><span data-stu-id="1b1ce-218">0 - 50</span></span>             | <span data-ttu-id="1b1ce-219">30 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-219">30%</span></span>      |
| <span data-ttu-id="1b1ce-220">50 à 100</span><span class="sxs-lookup"><span data-stu-id="1b1ce-220">50 - 100</span></span>           | <span data-ttu-id="1b1ce-221">20 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-221">20%</span></span>      |
| <span data-ttu-id="1b1ce-222">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="1b1ce-222">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="1b1ce-223">10 %</span><span class="sxs-lookup"><span data-stu-id="1b1ce-223">10%</span></span>      |

<span data-ttu-id="1b1ce-224">Base marginale : **Facture totale, autres taxe incluses** Mode de calcul : **Intervalle** </span><span class="sxs-lookup"><span data-stu-id="1b1ce-224">Marginal base: **Invoice total incl. other sales tax amounts** Calculation method: **Interval** </span></span>  
<span data-ttu-id="1b1ce-225">Il y a un droit de douane spécial de 5,00 euros sur chaque lampe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-225">There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="1b1ce-226">Le droit est ajouté au montant HT avant le calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-226">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="1b1ce-227">Vous achetez 8 lampes à 25,00 pièce.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-227">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="1b1ce-228">Le montant HT de la facture est 200,00.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-228">The net amount for the invoice is 200.00.</span></span> <span data-ttu-id="1b1ce-229">Le montant TTC de la facture est 200,00 + (8 x 5,00) = 240,00.</span><span class="sxs-lookup"><span data-stu-id="1b1ce-229">The gross amount for the invoice is 200.00 + (8 x 5.00) = 240.00.</span></span> <span data-ttu-id="1b1ce-230">La taxe est calculée comme suit : Taxe totale = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 Total des droits de douane = 5,00 x 8 = 40,00 Montant total facturé = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="1b1ce-230">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 10 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="1b1ce-231">Pour plus d'informations, voir [Options de calcul de montant total et d'intervalle pour les codes taxe](whole-amount-interval-options-sales-tax-codes.md) et [Méthodes de calcul de la taxe dans le champ Origine](sales-tax-calculation-methods-origin-field.md).</span><span class="sxs-lookup"><span data-stu-id="1b1ce-231">For more information, see [Whole amount and Interval calculation options for sales tax codes](whole-amount-interval-options-sales-tax-codes.md) and [Sales tax calculation methods in the Origin field](sales-tax-calculation-methods-origin-field.md).</span></span>



