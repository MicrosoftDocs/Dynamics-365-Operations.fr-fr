---
title: "Réévaluer une devise dans une société de consolidation"
description: "Cette rubrique décrit la procédure de réévaluation de la devise dans une société de consolidation."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2330939ddd7ccf4555cf1eff1e264c51f779c4eb
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="dec8f-103">Réévaluer une devise dans une société de consolidation</span><span class="sxs-lookup"><span data-stu-id="dec8f-103">Currency revaluation in a consolidation company</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="dec8f-104">Lorsque vous consolidez des données d'une devise comptable vers une autre, vous devez toujours exécuter la réévaluation de devise en cas de changement dans les taux de change, de sorte que les soldes de compte soient correctement réévalués.</span><span class="sxs-lookup"><span data-stu-id="dec8f-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="dec8f-105">Lorsque vous consolidez initialement des données, utilisez l'onglet **Conversion de devises** pour sélectionner les taux de change initiaux pour la traduction lors du processus de consolidation.</span><span class="sxs-lookup"><span data-stu-id="dec8f-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="dec8f-106">Une fois qu'un nouveau taux de change est entré (par exemple, le mois prochain), vous devez réévaluer les soldes de compte.</span><span class="sxs-lookup"><span data-stu-id="dec8f-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="dec8f-107">Les profits non réalisés ou les pertes sont alors mis à jour, selon le nouveau taux de change et la date.</span><span class="sxs-lookup"><span data-stu-id="dec8f-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="dec8f-108">L'exemple suivant illustre les écritures comptables créées lors du processus.</span><span class="sxs-lookup"><span data-stu-id="dec8f-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="dec8f-109">Paramétrage de la société</span><span class="sxs-lookup"><span data-stu-id="dec8f-109">Company setup</span></span>
-   <span data-ttu-id="dec8f-110">**Source/société d'exploitation (USMF)**  : Les dollars US (USD) sont utilisés comme devise comptable et devise de reporting.</span><span class="sxs-lookup"><span data-stu-id="dec8f-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="dec8f-111">**Société consolidée (CON)** : Les Euros (EUR) sont utilisés comme devise comptable et devise de reporting.</span><span class="sxs-lookup"><span data-stu-id="dec8f-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="dec8f-112">**Profit réalisé** : Compte général 801500</span><span class="sxs-lookup"><span data-stu-id="dec8f-112">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="dec8f-113">**Perte réalisée** : Compte général 801600</span><span class="sxs-lookup"><span data-stu-id="dec8f-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="dec8f-114">**Profit non réalisé** : Compte général 801600</span><span class="sxs-lookup"><span data-stu-id="dec8f-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="dec8f-115">**Perte non réalisée** : Compte général 801400</span><span class="sxs-lookup"><span data-stu-id="dec8f-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="dec8f-116">Transactions d'origine</span><span class="sxs-lookup"><span data-stu-id="dec8f-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="dec8f-117">Transactions de rentrée de fonds dans USMF</span><span class="sxs-lookup"><span data-stu-id="dec8f-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="dec8f-118">Date</span><span class="sxs-lookup"><span data-stu-id="dec8f-118">Date</span></span>       | <span data-ttu-id="dec8f-119">Compte général</span><span class="sxs-lookup"><span data-stu-id="dec8f-119">Ledger account</span></span>               | <span data-ttu-id="dec8f-120">Devise</span><span class="sxs-lookup"><span data-stu-id="dec8f-120">Currency</span></span> | <span data-ttu-id="dec8f-121">Montant</span><span class="sxs-lookup"><span data-stu-id="dec8f-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="dec8f-122">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="dec8f-122">10/11/2015</span></span> | <span data-ttu-id="dec8f-123">110110 – Disponibilités</span><span class="sxs-lookup"><span data-stu-id="dec8f-123">110110 – Cash</span></span>                | <span data-ttu-id="dec8f-124">USD</span><span class="sxs-lookup"><span data-stu-id="dec8f-124">USD</span></span>      | <span data-ttu-id="dec8f-125">500</span><span class="sxs-lookup"><span data-stu-id="dec8f-125">500</span></span>    |
| <span data-ttu-id="dec8f-126">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="dec8f-126">10/11/2015</span></span> | <span data-ttu-id="dec8f-127">130100 – Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="dec8f-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="dec8f-128">USD</span><span class="sxs-lookup"><span data-stu-id="dec8f-128">USD</span></span>      | <span data-ttu-id="dec8f-129">-500</span><span class="sxs-lookup"><span data-stu-id="dec8f-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="dec8f-130">Taux de change</span><span class="sxs-lookup"><span data-stu-id="dec8f-130">Exchange rates</span></span>

| <span data-ttu-id="dec8f-131">Devise de départ</span><span class="sxs-lookup"><span data-stu-id="dec8f-131">From currency</span></span> | <span data-ttu-id="dec8f-132">Devise d'arrivée</span><span class="sxs-lookup"><span data-stu-id="dec8f-132">To currency</span></span> | <span data-ttu-id="dec8f-133">Date de début</span><span class="sxs-lookup"><span data-stu-id="dec8f-133">Start date</span></span> | <span data-ttu-id="dec8f-134">Taux de change</span><span class="sxs-lookup"><span data-stu-id="dec8f-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="dec8f-135">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-135">EUR</span></span>           | <span data-ttu-id="dec8f-136">USD</span><span class="sxs-lookup"><span data-stu-id="dec8f-136">USD</span></span>         | <span data-ttu-id="dec8f-137">10/1/2015</span><span class="sxs-lookup"><span data-stu-id="dec8f-137">10/1/2015</span></span>  | <span data-ttu-id="dec8f-138">200</span><span class="sxs-lookup"><span data-stu-id="dec8f-138">200</span></span>           |
| <span data-ttu-id="dec8f-139">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-139">EUR</span></span>           | <span data-ttu-id="dec8f-140">USD</span><span class="sxs-lookup"><span data-stu-id="dec8f-140">USD</span></span>         | <span data-ttu-id="dec8f-141">11/1/2015</span><span class="sxs-lookup"><span data-stu-id="dec8f-141">11/1/2015</span></span>  | <span data-ttu-id="dec8f-142">150</span><span class="sxs-lookup"><span data-stu-id="dec8f-142">150</span></span>           |
| <span data-ttu-id="dec8f-143">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-143">EUR</span></span>           | <span data-ttu-id="dec8f-144">USD</span><span class="sxs-lookup"><span data-stu-id="dec8f-144">USD</span></span>         | <span data-ttu-id="dec8f-145">12/1/2012</span><span class="sxs-lookup"><span data-stu-id="dec8f-145">12/1/2012</span></span>  | <span data-ttu-id="dec8f-146">100</span><span class="sxs-lookup"><span data-stu-id="dec8f-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="dec8f-147">Effectuer la consolidation pour octobre 2015</span><span class="sxs-lookup"><span data-stu-id="dec8f-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="dec8f-148">Soldes dans la société de consolidation</span><span class="sxs-lookup"><span data-stu-id="dec8f-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="dec8f-149">Compte général</span><span class="sxs-lookup"><span data-stu-id="dec8f-149">Ledger account</span></span> | <span data-ttu-id="dec8f-150">Devise</span><span class="sxs-lookup"><span data-stu-id="dec8f-150">Currency</span></span> | <span data-ttu-id="dec8f-151">Montant</span><span class="sxs-lookup"><span data-stu-id="dec8f-151">Amount</span></span> | <span data-ttu-id="dec8f-152">Calcul</span><span class="sxs-lookup"><span data-stu-id="dec8f-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="dec8f-153">110110</span><span class="sxs-lookup"><span data-stu-id="dec8f-153">110110</span></span>         | <span data-ttu-id="dec8f-154">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-154">EUR</span></span>      | <span data-ttu-id="dec8f-155">250</span><span class="sxs-lookup"><span data-stu-id="dec8f-155">250</span></span>    | <span data-ttu-id="dec8f-156">500 USD × 50 %</span><span class="sxs-lookup"><span data-stu-id="dec8f-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="dec8f-157">130100</span><span class="sxs-lookup"><span data-stu-id="dec8f-157">130100</span></span>         | <span data-ttu-id="dec8f-158">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-158">EUR</span></span>      | <span data-ttu-id="dec8f-159">-250</span><span class="sxs-lookup"><span data-stu-id="dec8f-159">-250</span></span>   | <span data-ttu-id="dec8f-160">-500 USD × 50 %</span><span class="sxs-lookup"><span data-stu-id="dec8f-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="dec8f-161">Effectuer la réévaluation de devise des comptes à partir du 1er octobre 2015, jusqu'au 30 novembre 2015</span><span class="sxs-lookup"><span data-stu-id="dec8f-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="dec8f-162">Soldes dans la société de consolidation</span><span class="sxs-lookup"><span data-stu-id="dec8f-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="dec8f-163">Compte général</span><span class="sxs-lookup"><span data-stu-id="dec8f-163">Ledger account</span></span> | <span data-ttu-id="dec8f-164">Devise</span><span class="sxs-lookup"><span data-stu-id="dec8f-164">Currency</span></span> | <span data-ttu-id="dec8f-165">Montant</span><span class="sxs-lookup"><span data-stu-id="dec8f-165">Amount</span></span>  | <span data-ttu-id="dec8f-166">Calcul</span><span class="sxs-lookup"><span data-stu-id="dec8f-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="dec8f-167">110110</span><span class="sxs-lookup"><span data-stu-id="dec8f-167">110110</span></span>         | <span data-ttu-id="dec8f-168">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-168">EUR</span></span>      | <span data-ttu-id="dec8f-169">333,33</span><span class="sxs-lookup"><span data-stu-id="dec8f-169">333.33</span></span>  | <span data-ttu-id="dec8f-170">Montant d'origine de 500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="dec8f-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="dec8f-171">130100</span><span class="sxs-lookup"><span data-stu-id="dec8f-171">130100</span></span>         | <span data-ttu-id="dec8f-172">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-172">EUR</span></span>      | <span data-ttu-id="dec8f-173">-333,33</span><span class="sxs-lookup"><span data-stu-id="dec8f-173">-333.33</span></span> | <span data-ttu-id="dec8f-174">Montant d'origine de -500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="dec8f-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="dec8f-175">801400</span><span class="sxs-lookup"><span data-stu-id="dec8f-175">801400</span></span>         | <span data-ttu-id="dec8f-176">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-176">EUR</span></span>      | <span data-ttu-id="dec8f-177">83,33</span><span class="sxs-lookup"><span data-stu-id="dec8f-177">83.33</span></span>   | <span data-ttu-id="dec8f-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="dec8f-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="dec8f-179">801600</span><span class="sxs-lookup"><span data-stu-id="dec8f-179">801600</span></span>         | <span data-ttu-id="dec8f-180">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-180">EUR</span></span>      | <span data-ttu-id="dec8f-181">-83,33</span><span class="sxs-lookup"><span data-stu-id="dec8f-181">-83.33</span></span>  | <span data-ttu-id="dec8f-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="dec8f-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="dec8f-183">Vous verrez des transactions supplémentaires pour les montants de devise de déclaration.</span><span class="sxs-lookup"><span data-stu-id="dec8f-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="dec8f-184">Effectuer la réévaluation de devise des comptes à partir du 1er octobre 2015, jusqu'au 31 décembre 2015</span><span class="sxs-lookup"><span data-stu-id="dec8f-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="dec8f-185">Soldes dans la société de consolidation</span><span class="sxs-lookup"><span data-stu-id="dec8f-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="dec8f-186">Compte général</span><span class="sxs-lookup"><span data-stu-id="dec8f-186">Ledger account</span></span> | <span data-ttu-id="dec8f-187">Devise</span><span class="sxs-lookup"><span data-stu-id="dec8f-187">Currency</span></span> | <span data-ttu-id="dec8f-188">Montant</span><span class="sxs-lookup"><span data-stu-id="dec8f-188">Amount</span></span>  | <span data-ttu-id="dec8f-189">Calcul</span><span class="sxs-lookup"><span data-stu-id="dec8f-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="dec8f-190">110110</span><span class="sxs-lookup"><span data-stu-id="dec8f-190">110110</span></span>         | <span data-ttu-id="dec8f-191">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-191">EUR</span></span>      | <span data-ttu-id="dec8f-192">500,00</span><span class="sxs-lookup"><span data-stu-id="dec8f-192">500.00</span></span>  | <span data-ttu-id="dec8f-193">Montant d'origine de 500 × 1</span><span class="sxs-lookup"><span data-stu-id="dec8f-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="dec8f-194">130100</span><span class="sxs-lookup"><span data-stu-id="dec8f-194">130100</span></span>         | <span data-ttu-id="dec8f-195">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-195">EUR</span></span>      | <span data-ttu-id="dec8f-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="dec8f-196">-500.00</span></span> | <span data-ttu-id="dec8f-197">Montant d'origine de -500 × 1</span><span class="sxs-lookup"><span data-stu-id="dec8f-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="dec8f-198">801400</span><span class="sxs-lookup"><span data-stu-id="dec8f-198">801400</span></span>         | <span data-ttu-id="dec8f-199">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-199">EUR</span></span>      | <span data-ttu-id="dec8f-200">250</span><span class="sxs-lookup"><span data-stu-id="dec8f-200">250</span></span>     | <span data-ttu-id="dec8f-201">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="dec8f-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="dec8f-202">801600</span><span class="sxs-lookup"><span data-stu-id="dec8f-202">801600</span></span>         | <span data-ttu-id="dec8f-203">EUR</span><span class="sxs-lookup"><span data-stu-id="dec8f-203">EUR</span></span>      | <span data-ttu-id="dec8f-204">-250</span><span class="sxs-lookup"><span data-stu-id="dec8f-204">-250</span></span>    | <span data-ttu-id="dec8f-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="dec8f-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






