---
title: "Réévaluation de devise dans une société de consolidation"
description: 
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 643af8d771685fe8fd652b353d41f2679e0bef8b
ms.contentlocale: fr-fr
ms.lasthandoff: 07/18/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="cfdca-102">Réévaluation de devise dans une société de consolidation</span><span class="sxs-lookup"><span data-stu-id="cfdca-102">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="cfdca-103">Lorsque vous consolidez des données d'une devise comptable vers une autre, vous devez toujours exécuter la réévaluation de devise en cas de changement dans les taux de change, de sorte que les soldes de compte soient correctement réévalués.</span><span class="sxs-lookup"><span data-stu-id="cfdca-103">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="cfdca-104">Lorsque vous consolidez initialement des données, utilisez l'onglet **Conversion de devises** pour sélectionner les taux de change initiaux pour la traduction lors du processus de consolidation.</span><span class="sxs-lookup"><span data-stu-id="cfdca-104">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="cfdca-105">Une fois qu'un nouveau taux de change est entré (par exemple, le mois prochain), vous devez réévaluer les soldes de compte.</span><span class="sxs-lookup"><span data-stu-id="cfdca-105">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="cfdca-106">Les profits non réalisés ou les pertes sont alors mis à jour, selon le nouveau taux de change et la date.</span><span class="sxs-lookup"><span data-stu-id="cfdca-106">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="cfdca-107">L'exemple suivant illustre les écritures comptables créées lors du processus.</span><span class="sxs-lookup"><span data-stu-id="cfdca-107">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="cfdca-108">Paramétrage de la société</span><span class="sxs-lookup"><span data-stu-id="cfdca-108">Company setup</span></span>
-   <span data-ttu-id="cfdca-109">**Source/société d'exploitation (USMF)**  : Les dollars US (USD) sont utilisés comme devise comptable et devise de reporting.</span><span class="sxs-lookup"><span data-stu-id="cfdca-109">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="cfdca-110">**Société consolidée (CON)** : Les Euros (EUR) sont utilisés comme devise comptable et devise de reporting.</span><span class="sxs-lookup"><span data-stu-id="cfdca-110">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="cfdca-111">**Profit réalisé** : Compte général 801500</span><span class="sxs-lookup"><span data-stu-id="cfdca-111">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="cfdca-112">**Perte réalisée** : Compte général 801600</span><span class="sxs-lookup"><span data-stu-id="cfdca-112">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="cfdca-113">**Profit non réalisé** : Compte général 801600</span><span class="sxs-lookup"><span data-stu-id="cfdca-113">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="cfdca-114">**Perte non réalisée** : Compte général 801400</span><span class="sxs-lookup"><span data-stu-id="cfdca-114">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="cfdca-115">Transactions d'origine</span><span class="sxs-lookup"><span data-stu-id="cfdca-115">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="cfdca-116">Transactions de rentrée de fonds dans USMF</span><span class="sxs-lookup"><span data-stu-id="cfdca-116">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="cfdca-117">Date</span><span class="sxs-lookup"><span data-stu-id="cfdca-117">Date</span></span>       | <span data-ttu-id="cfdca-118">Compte général</span><span class="sxs-lookup"><span data-stu-id="cfdca-118">Ledger account</span></span>               | <span data-ttu-id="cfdca-119">Devise</span><span class="sxs-lookup"><span data-stu-id="cfdca-119">Currency</span></span> | <span data-ttu-id="cfdca-120">Montant</span><span class="sxs-lookup"><span data-stu-id="cfdca-120">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="cfdca-121">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="cfdca-121">10/11/2015</span></span> | <span data-ttu-id="cfdca-122">110110 – Disponibilités</span><span class="sxs-lookup"><span data-stu-id="cfdca-122">110110 – Cash</span></span>                | <span data-ttu-id="cfdca-123">USD</span><span class="sxs-lookup"><span data-stu-id="cfdca-123">USD</span></span>      | <span data-ttu-id="cfdca-124">500</span><span class="sxs-lookup"><span data-stu-id="cfdca-124">500</span></span>    |
| <span data-ttu-id="cfdca-125">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="cfdca-125">10/11/2015</span></span> | <span data-ttu-id="cfdca-126">130100 – Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="cfdca-126">130100 – Accounts Receivable</span></span> | <span data-ttu-id="cfdca-127">USD</span><span class="sxs-lookup"><span data-stu-id="cfdca-127">USD</span></span>      | <span data-ttu-id="cfdca-128">-500</span><span class="sxs-lookup"><span data-stu-id="cfdca-128">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="cfdca-129">Taux de change</span><span class="sxs-lookup"><span data-stu-id="cfdca-129">Exchange rates</span></span>
| <span data-ttu-id="cfdca-130">Devise de départ</span><span class="sxs-lookup"><span data-stu-id="cfdca-130">From currency</span></span> | <span data-ttu-id="cfdca-131">Devise d'arrivée</span><span class="sxs-lookup"><span data-stu-id="cfdca-131">To currency</span></span> | <span data-ttu-id="cfdca-132">Date de début</span><span class="sxs-lookup"><span data-stu-id="cfdca-132">Start date</span></span> | <span data-ttu-id="cfdca-133">Taux de change</span><span class="sxs-lookup"><span data-stu-id="cfdca-133">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="cfdca-134">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-134">EUR</span></span>           | <span data-ttu-id="cfdca-135">USD</span><span class="sxs-lookup"><span data-stu-id="cfdca-135">USD</span></span>         | <span data-ttu-id="cfdca-136">10/1/2015</span><span class="sxs-lookup"><span data-stu-id="cfdca-136">10/1/2015</span></span>  | <span data-ttu-id="cfdca-137">200</span><span class="sxs-lookup"><span data-stu-id="cfdca-137">200</span></span>           |
| <span data-ttu-id="cfdca-138">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-138">EUR</span></span>           | <span data-ttu-id="cfdca-139">USD</span><span class="sxs-lookup"><span data-stu-id="cfdca-139">USD</span></span>         | <span data-ttu-id="cfdca-140">11/1/2015</span><span class="sxs-lookup"><span data-stu-id="cfdca-140">11/1/2015</span></span>  | <span data-ttu-id="cfdca-141">150</span><span class="sxs-lookup"><span data-stu-id="cfdca-141">150</span></span>           |
| <span data-ttu-id="cfdca-142">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-142">EUR</span></span>           | <span data-ttu-id="cfdca-143">USD</span><span class="sxs-lookup"><span data-stu-id="cfdca-143">USD</span></span>         | <span data-ttu-id="cfdca-144">12/1/2012</span><span class="sxs-lookup"><span data-stu-id="cfdca-144">12/1/2012</span></span>  | <span data-ttu-id="cfdca-145">100</span><span class="sxs-lookup"><span data-stu-id="cfdca-145">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="cfdca-146">Effectuer la consolidation pour octobre 2015</span><span class="sxs-lookup"><span data-stu-id="cfdca-146">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="cfdca-147">Soldes dans la société de consolidation</span><span class="sxs-lookup"><span data-stu-id="cfdca-147">Balances in the consolidation company</span></span>

| <span data-ttu-id="cfdca-148">Compte général</span><span class="sxs-lookup"><span data-stu-id="cfdca-148">Ledger account</span></span> | <span data-ttu-id="cfdca-149">Devise</span><span class="sxs-lookup"><span data-stu-id="cfdca-149">Currency</span></span> | <span data-ttu-id="cfdca-150">Montant</span><span class="sxs-lookup"><span data-stu-id="cfdca-150">Amount</span></span> | <span data-ttu-id="cfdca-151">Calcul</span><span class="sxs-lookup"><span data-stu-id="cfdca-151">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="cfdca-152">110110</span><span class="sxs-lookup"><span data-stu-id="cfdca-152">110110</span></span>         | <span data-ttu-id="cfdca-153">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-153">EUR</span></span>      | <span data-ttu-id="cfdca-154">250</span><span class="sxs-lookup"><span data-stu-id="cfdca-154">250</span></span>    | <span data-ttu-id="cfdca-155">500 USD × 50 %</span><span class="sxs-lookup"><span data-stu-id="cfdca-155">500 USD × 50%</span></span>  |
| <span data-ttu-id="cfdca-156">130100</span><span class="sxs-lookup"><span data-stu-id="cfdca-156">130100</span></span>         | <span data-ttu-id="cfdca-157">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-157">EUR</span></span>      | <span data-ttu-id="cfdca-158">-250</span><span class="sxs-lookup"><span data-stu-id="cfdca-158">-250</span></span>   | <span data-ttu-id="cfdca-159">-500 USD × 50 %</span><span class="sxs-lookup"><span data-stu-id="cfdca-159">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="cfdca-160">Effectuer la réévaluation de devise des comptes à partir du 1er octobre 2015, jusqu'au 30 novembre 2015</span><span class="sxs-lookup"><span data-stu-id="cfdca-160">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="cfdca-161">Soldes dans la société de consolidation</span><span class="sxs-lookup"><span data-stu-id="cfdca-161">Balances in the consolidation company</span></span>

| <span data-ttu-id="cfdca-162">Compte général</span><span class="sxs-lookup"><span data-stu-id="cfdca-162">Ledger account</span></span> | <span data-ttu-id="cfdca-163">Devise</span><span class="sxs-lookup"><span data-stu-id="cfdca-163">Currency</span></span> | <span data-ttu-id="cfdca-164">Montant</span><span class="sxs-lookup"><span data-stu-id="cfdca-164">Amount</span></span>  | <span data-ttu-id="cfdca-165">Calcul</span><span class="sxs-lookup"><span data-stu-id="cfdca-165">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="cfdca-166">110110</span><span class="sxs-lookup"><span data-stu-id="cfdca-166">110110</span></span>         | <span data-ttu-id="cfdca-167">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-167">EUR</span></span>      | <span data-ttu-id="cfdca-168">333,33</span><span class="sxs-lookup"><span data-stu-id="cfdca-168">333.33</span></span>  | <span data-ttu-id="cfdca-169">Montant d'origine de 500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="cfdca-169">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="cfdca-170">130100</span><span class="sxs-lookup"><span data-stu-id="cfdca-170">130100</span></span>         | <span data-ttu-id="cfdca-171">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-171">EUR</span></span>      | <span data-ttu-id="cfdca-172">-333,33</span><span class="sxs-lookup"><span data-stu-id="cfdca-172">-333.33</span></span> | <span data-ttu-id="cfdca-173">Montant d'origine de -500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="cfdca-173">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="cfdca-174">801400</span><span class="sxs-lookup"><span data-stu-id="cfdca-174">801400</span></span>         | <span data-ttu-id="cfdca-175">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-175">EUR</span></span>      | <span data-ttu-id="cfdca-176">83,33</span><span class="sxs-lookup"><span data-stu-id="cfdca-176">83.33</span></span>   | <span data-ttu-id="cfdca-177">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="cfdca-177">333.33 – 250</span></span>                       |
| <span data-ttu-id="cfdca-178">801600</span><span class="sxs-lookup"><span data-stu-id="cfdca-178">801600</span></span>         | <span data-ttu-id="cfdca-179">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-179">EUR</span></span>      | <span data-ttu-id="cfdca-180">-83,33</span><span class="sxs-lookup"><span data-stu-id="cfdca-180">-83.33</span></span>  | <span data-ttu-id="cfdca-181">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="cfdca-181">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="cfdca-182">Vous verrez des transactions supplémentaires pour les montants de devise de déclaration.</span><span class="sxs-lookup"><span data-stu-id="cfdca-182">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="cfdca-183">Effectuer la réévaluation de devise des comptes à partir du 1er octobre 2015, jusqu'au 31 décembre 2015</span><span class="sxs-lookup"><span data-stu-id="cfdca-183">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="cfdca-184">Soldes dans la société de consolidation</span><span class="sxs-lookup"><span data-stu-id="cfdca-184">Balances in the consolidation company</span></span>

| <span data-ttu-id="cfdca-185">Compte général</span><span class="sxs-lookup"><span data-stu-id="cfdca-185">Ledger account</span></span> | <span data-ttu-id="cfdca-186">Devise</span><span class="sxs-lookup"><span data-stu-id="cfdca-186">Currency</span></span> | <span data-ttu-id="cfdca-187">Montant</span><span class="sxs-lookup"><span data-stu-id="cfdca-187">Amount</span></span>  | <span data-ttu-id="cfdca-188">Calcul</span><span class="sxs-lookup"><span data-stu-id="cfdca-188">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="cfdca-189">110110</span><span class="sxs-lookup"><span data-stu-id="cfdca-189">110110</span></span>         | <span data-ttu-id="cfdca-190">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-190">EUR</span></span>      | <span data-ttu-id="cfdca-191">500,00</span><span class="sxs-lookup"><span data-stu-id="cfdca-191">500.00</span></span>  | <span data-ttu-id="cfdca-192">Montant d'origine de 500 × 1</span><span class="sxs-lookup"><span data-stu-id="cfdca-192">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="cfdca-193">130100</span><span class="sxs-lookup"><span data-stu-id="cfdca-193">130100</span></span>         | <span data-ttu-id="cfdca-194">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-194">EUR</span></span>      | <span data-ttu-id="cfdca-195">-500,00</span><span class="sxs-lookup"><span data-stu-id="cfdca-195">-500.00</span></span> | <span data-ttu-id="cfdca-196">Montant d'origine de -500 × 1</span><span class="sxs-lookup"><span data-stu-id="cfdca-196">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="cfdca-197">801400</span><span class="sxs-lookup"><span data-stu-id="cfdca-197">801400</span></span>         | <span data-ttu-id="cfdca-198">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-198">EUR</span></span>      | <span data-ttu-id="cfdca-199">250</span><span class="sxs-lookup"><span data-stu-id="cfdca-199">250</span></span>     | <span data-ttu-id="cfdca-200">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="cfdca-200">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="cfdca-201">801600</span><span class="sxs-lookup"><span data-stu-id="cfdca-201">801600</span></span>         | <span data-ttu-id="cfdca-202">EUR</span><span class="sxs-lookup"><span data-stu-id="cfdca-202">EUR</span></span>      | <span data-ttu-id="cfdca-203">-250</span><span class="sxs-lookup"><span data-stu-id="cfdca-203">-250</span></span>    | <span data-ttu-id="cfdca-204">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="cfdca-204">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






