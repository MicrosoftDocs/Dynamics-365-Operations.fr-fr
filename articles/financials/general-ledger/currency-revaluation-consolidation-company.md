---
title: "Réévaluer une devise dans une société de consolidation"
description: "Cette rubrique décrit la procédure de réévaluation de la devise dans une société de consolidation."
author: ShylaThompson
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ad0083018d2734cb1e36cbf5f94105376c57cdf9
ms.openlocfilehash: 76290564037ab6f5c7a1cd4508a819bd603e8148
ms.contentlocale: fr-fr
ms.lasthandoff: 10/02/2018

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="8732e-103">Réévaluer une devise dans une société de consolidation</span><span class="sxs-lookup"><span data-stu-id="8732e-103">Currency revaluation in a consolidation company</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8732e-104">Lorsque vous consolidez des données d'une devise comptable vers une autre, vous devez toujours exécuter la réévaluation de devise en cas de changement dans les taux de change, de sorte que les soldes de compte soient correctement réévalués.</span><span class="sxs-lookup"><span data-stu-id="8732e-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="8732e-105">Lorsque vous consolidez initialement des données, utilisez l'onglet **Conversion de devises** pour sélectionner les taux de change initiaux pour la traduction lors du processus de consolidation.</span><span class="sxs-lookup"><span data-stu-id="8732e-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="8732e-106">Une fois qu'un nouveau taux de change est entré (par exemple, le mois prochain), vous devez réévaluer les soldes de compte.</span><span class="sxs-lookup"><span data-stu-id="8732e-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="8732e-107">Les profits non réalisés ou les pertes sont alors mis à jour, selon le nouveau taux de change et la date.</span><span class="sxs-lookup"><span data-stu-id="8732e-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="8732e-108">L'exemple suivant illustre les écritures comptables créées lors du processus.</span><span class="sxs-lookup"><span data-stu-id="8732e-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="8732e-109">Paramétrage de la société</span><span class="sxs-lookup"><span data-stu-id="8732e-109">Company setup</span></span>
-   <span data-ttu-id="8732e-110">**Source/société d'exploitation (USMF)**  : Les dollars US (USD) sont utilisés comme devise comptable et devise de reporting.</span><span class="sxs-lookup"><span data-stu-id="8732e-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="8732e-111">**Société consolidée (CON)** : Les Euros (EUR) sont utilisés comme devise comptable et devise de reporting.</span><span class="sxs-lookup"><span data-stu-id="8732e-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="8732e-112">**Profit réalisé** : Compte général 801500</span><span class="sxs-lookup"><span data-stu-id="8732e-112">**Realized gain**– Ledger account 801500</span></span>
    -   <span data-ttu-id="8732e-113">**Perte réalisée** : Compte général 801600</span><span class="sxs-lookup"><span data-stu-id="8732e-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="8732e-114">**Profit non réalisé** : Compte général 801600</span><span class="sxs-lookup"><span data-stu-id="8732e-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="8732e-115">**Perte non réalisée** : Compte général 801400</span><span class="sxs-lookup"><span data-stu-id="8732e-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="8732e-116">Transactions d'origine</span><span class="sxs-lookup"><span data-stu-id="8732e-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="8732e-117">Transactions de rentrée de fonds dans USMF</span><span class="sxs-lookup"><span data-stu-id="8732e-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="8732e-118">Date</span><span class="sxs-lookup"><span data-stu-id="8732e-118">Date</span></span>       | <span data-ttu-id="8732e-119">Compte général</span><span class="sxs-lookup"><span data-stu-id="8732e-119">Ledger account</span></span>               | <span data-ttu-id="8732e-120">Devise</span><span class="sxs-lookup"><span data-stu-id="8732e-120">Currency</span></span> | <span data-ttu-id="8732e-121">Montant</span><span class="sxs-lookup"><span data-stu-id="8732e-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="8732e-122">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="8732e-122">10/11/2015</span></span> | <span data-ttu-id="8732e-123">110110 – Disponibilités</span><span class="sxs-lookup"><span data-stu-id="8732e-123">110110 – Cash</span></span>                | <span data-ttu-id="8732e-124">USD</span><span class="sxs-lookup"><span data-stu-id="8732e-124">USD</span></span>      | <span data-ttu-id="8732e-125">500</span><span class="sxs-lookup"><span data-stu-id="8732e-125">500</span></span>    |
| <span data-ttu-id="8732e-126">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="8732e-126">10/11/2015</span></span> | <span data-ttu-id="8732e-127">130100 – Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="8732e-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="8732e-128">USD</span><span class="sxs-lookup"><span data-stu-id="8732e-128">USD</span></span>      | <span data-ttu-id="8732e-129">-500</span><span class="sxs-lookup"><span data-stu-id="8732e-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="8732e-130">Taux de change</span><span class="sxs-lookup"><span data-stu-id="8732e-130">Exchange rates</span></span>

| <span data-ttu-id="8732e-131">Devise de départ</span><span class="sxs-lookup"><span data-stu-id="8732e-131">From currency</span></span> | <span data-ttu-id="8732e-132">Devise d'arrivée</span><span class="sxs-lookup"><span data-stu-id="8732e-132">To currency</span></span> | <span data-ttu-id="8732e-133">Date de début</span><span class="sxs-lookup"><span data-stu-id="8732e-133">Start date</span></span> | <span data-ttu-id="8732e-134">Taux de change</span><span class="sxs-lookup"><span data-stu-id="8732e-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="8732e-135">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-135">EUR</span></span>           | <span data-ttu-id="8732e-136">USD</span><span class="sxs-lookup"><span data-stu-id="8732e-136">USD</span></span>         | <span data-ttu-id="8732e-137">10/1/2015</span><span class="sxs-lookup"><span data-stu-id="8732e-137">10/1/2015</span></span>  | <span data-ttu-id="8732e-138">200</span><span class="sxs-lookup"><span data-stu-id="8732e-138">200</span></span>           |
| <span data-ttu-id="8732e-139">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-139">EUR</span></span>           | <span data-ttu-id="8732e-140">USD</span><span class="sxs-lookup"><span data-stu-id="8732e-140">USD</span></span>         | <span data-ttu-id="8732e-141">11/1/2015</span><span class="sxs-lookup"><span data-stu-id="8732e-141">11/1/2015</span></span>  | <span data-ttu-id="8732e-142">150</span><span class="sxs-lookup"><span data-stu-id="8732e-142">150</span></span>           |
| <span data-ttu-id="8732e-143">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-143">EUR</span></span>           | <span data-ttu-id="8732e-144">USD</span><span class="sxs-lookup"><span data-stu-id="8732e-144">USD</span></span>         | <span data-ttu-id="8732e-145">12/1/2012</span><span class="sxs-lookup"><span data-stu-id="8732e-145">12/1/2012</span></span>  | <span data-ttu-id="8732e-146">100</span><span class="sxs-lookup"><span data-stu-id="8732e-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="8732e-147">Effectuer la consolidation pour octobre 2015</span><span class="sxs-lookup"><span data-stu-id="8732e-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="8732e-148">Soldes dans la société de consolidation</span><span class="sxs-lookup"><span data-stu-id="8732e-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="8732e-149">Compte général</span><span class="sxs-lookup"><span data-stu-id="8732e-149">Ledger account</span></span> | <span data-ttu-id="8732e-150">Devise</span><span class="sxs-lookup"><span data-stu-id="8732e-150">Currency</span></span> | <span data-ttu-id="8732e-151">Montant</span><span class="sxs-lookup"><span data-stu-id="8732e-151">Amount</span></span> | <span data-ttu-id="8732e-152">Calcul</span><span class="sxs-lookup"><span data-stu-id="8732e-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="8732e-153">110110</span><span class="sxs-lookup"><span data-stu-id="8732e-153">110110</span></span>         | <span data-ttu-id="8732e-154">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-154">EUR</span></span>      | <span data-ttu-id="8732e-155">250</span><span class="sxs-lookup"><span data-stu-id="8732e-155">250</span></span>    | <span data-ttu-id="8732e-156">500 USD × 50 %</span><span class="sxs-lookup"><span data-stu-id="8732e-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="8732e-157">130100</span><span class="sxs-lookup"><span data-stu-id="8732e-157">130100</span></span>         | <span data-ttu-id="8732e-158">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-158">EUR</span></span>      | <span data-ttu-id="8732e-159">-250</span><span class="sxs-lookup"><span data-stu-id="8732e-159">-250</span></span>   | <span data-ttu-id="8732e-160">-500 USD × 50 %</span><span class="sxs-lookup"><span data-stu-id="8732e-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="8732e-161">Effectuer la réévaluation de devise des comptes à partir du 1er octobre 2015, jusqu'au 30 novembre 2015</span><span class="sxs-lookup"><span data-stu-id="8732e-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="8732e-162">Soldes dans la société de consolidation</span><span class="sxs-lookup"><span data-stu-id="8732e-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="8732e-163">Compte général</span><span class="sxs-lookup"><span data-stu-id="8732e-163">Ledger account</span></span> | <span data-ttu-id="8732e-164">Devise</span><span class="sxs-lookup"><span data-stu-id="8732e-164">Currency</span></span> | <span data-ttu-id="8732e-165">Montant</span><span class="sxs-lookup"><span data-stu-id="8732e-165">Amount</span></span>  | <span data-ttu-id="8732e-166">Calcul</span><span class="sxs-lookup"><span data-stu-id="8732e-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="8732e-167">110110</span><span class="sxs-lookup"><span data-stu-id="8732e-167">110110</span></span>         | <span data-ttu-id="8732e-168">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-168">EUR</span></span>      | <span data-ttu-id="8732e-169">333,33</span><span class="sxs-lookup"><span data-stu-id="8732e-169">333.33</span></span>  | <span data-ttu-id="8732e-170">Montant d'origine de 500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="8732e-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="8732e-171">130100</span><span class="sxs-lookup"><span data-stu-id="8732e-171">130100</span></span>         | <span data-ttu-id="8732e-172">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-172">EUR</span></span>      | <span data-ttu-id="8732e-173">-333,33</span><span class="sxs-lookup"><span data-stu-id="8732e-173">-333.33</span></span> | <span data-ttu-id="8732e-174">Montant d'origine de -500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="8732e-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="8732e-175">801400</span><span class="sxs-lookup"><span data-stu-id="8732e-175">801400</span></span>         | <span data-ttu-id="8732e-176">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-176">EUR</span></span>      | <span data-ttu-id="8732e-177">83,33</span><span class="sxs-lookup"><span data-stu-id="8732e-177">83.33</span></span>   | <span data-ttu-id="8732e-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="8732e-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="8732e-179">801600</span><span class="sxs-lookup"><span data-stu-id="8732e-179">801600</span></span>         | <span data-ttu-id="8732e-180">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-180">EUR</span></span>      | <span data-ttu-id="8732e-181">-83,33</span><span class="sxs-lookup"><span data-stu-id="8732e-181">-83.33</span></span>  | <span data-ttu-id="8732e-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="8732e-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="8732e-183">Vous verrez des transactions supplémentaires pour les montants de devise de déclaration.</span><span class="sxs-lookup"><span data-stu-id="8732e-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="8732e-184">Effectuer la réévaluation de devise des comptes à partir du 1er octobre 2015, jusqu'au 31 décembre 2015</span><span class="sxs-lookup"><span data-stu-id="8732e-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="8732e-185">Soldes dans la société de consolidation</span><span class="sxs-lookup"><span data-stu-id="8732e-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="8732e-186">Compte général</span><span class="sxs-lookup"><span data-stu-id="8732e-186">Ledger account</span></span> | <span data-ttu-id="8732e-187">Devise</span><span class="sxs-lookup"><span data-stu-id="8732e-187">Currency</span></span> | <span data-ttu-id="8732e-188">Montant</span><span class="sxs-lookup"><span data-stu-id="8732e-188">Amount</span></span>  | <span data-ttu-id="8732e-189">Calcul</span><span class="sxs-lookup"><span data-stu-id="8732e-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="8732e-190">110110</span><span class="sxs-lookup"><span data-stu-id="8732e-190">110110</span></span>         | <span data-ttu-id="8732e-191">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-191">EUR</span></span>      | <span data-ttu-id="8732e-192">500,00</span><span class="sxs-lookup"><span data-stu-id="8732e-192">500.00</span></span>  | <span data-ttu-id="8732e-193">Montant d'origine de 500 × 1</span><span class="sxs-lookup"><span data-stu-id="8732e-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="8732e-194">130100</span><span class="sxs-lookup"><span data-stu-id="8732e-194">130100</span></span>         | <span data-ttu-id="8732e-195">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-195">EUR</span></span>      | <span data-ttu-id="8732e-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="8732e-196">-500.00</span></span> | <span data-ttu-id="8732e-197">Montant d'origine de -500 × 1</span><span class="sxs-lookup"><span data-stu-id="8732e-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="8732e-198">801400</span><span class="sxs-lookup"><span data-stu-id="8732e-198">801400</span></span>         | <span data-ttu-id="8732e-199">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-199">EUR</span></span>      | <span data-ttu-id="8732e-200">250</span><span class="sxs-lookup"><span data-stu-id="8732e-200">250</span></span>     | <span data-ttu-id="8732e-201">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="8732e-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="8732e-202">801600</span><span class="sxs-lookup"><span data-stu-id="8732e-202">801600</span></span>         | <span data-ttu-id="8732e-203">EUR</span><span class="sxs-lookup"><span data-stu-id="8732e-203">EUR</span></span>      | <span data-ttu-id="8732e-204">-250</span><span class="sxs-lookup"><span data-stu-id="8732e-204">-250</span></span>    | <span data-ttu-id="8732e-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="8732e-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






