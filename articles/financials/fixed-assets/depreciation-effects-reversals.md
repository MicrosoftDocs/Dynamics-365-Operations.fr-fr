---
title: Effets d'amortissement avec contrepassations
description: Cet article traite des conséquences potentielles de la contrepassation d'une transaction d'immobilisation.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d624fa998329680d9fa471fa325f6fcfd3920c6a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "320142"
---
# <a name="depreciation-effects-with-reversals"></a><span data-ttu-id="6c164-103">Effets d'amortissement avec contrepassations</span><span class="sxs-lookup"><span data-stu-id="6c164-103">Depreciation effects with reversals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6c164-104">Cet article traite des conséquences potentielles de la contrepassation d'une transaction d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="6c164-104">This article discusses potential implications of reversing a fixed asset transaction.</span></span> 

<span data-ttu-id="6c164-105">Vous pouvez contrepasser des transactions d’immobilisation et les transactions associées à une immobilisation.</span><span class="sxs-lookup"><span data-stu-id="6c164-105">You can reverse fixed asset transactions, and the transactions that are associated with a fixed asset.</span></span> <span data-ttu-id="6c164-106">Vous pouvez également annuler une transaction contrepassée.</span><span class="sxs-lookup"><span data-stu-id="6c164-106">You can also revoke a reversed transaction.</span></span> 

<span data-ttu-id="6c164-107">Vous pouvez contrepasser ou annuler une transaction qui n'était pas la dernière validée dans le registre des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="6c164-107">You can reverse or revoke a transaction that was not the most recent transaction posted to the book for the asset.</span></span> <span data-ttu-id="6c164-108">Vous devez commencer par déterminer si des transactions d'amortissement ont été validées après la transaction en cours de contrepassation.</span><span class="sxs-lookup"><span data-stu-id="6c164-108">You should first determine whether any depreciation transactions were posted after the transaction that you are reversing.</span></span> <span data-ttu-id="6c164-109">Cela est dû au fait que l'amortissement n'est pas recalculé lors de la contrepassation d'une transaction.</span><span class="sxs-lookup"><span data-stu-id="6c164-109">This is because depreciation is not recalculated when you reverse a transaction.</span></span> <span data-ttu-id="6c164-110">Par conséquent, il est souvent surévalué ou sous-évalué après la contrepassation, comme illustré dans les exemples.</span><span class="sxs-lookup"><span data-stu-id="6c164-110">Therefore, depreciation often is overstated or understated after the reversal, as shown in the examples.</span></span> 

<span data-ttu-id="6c164-111">Pour garantir l'exactitude de l'amortissement lors de la contrepassation d'une transaction, ne poursuivez pas la contrepassation si un message indiquant que l'amortissement ne sera pas recalculé s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6c164-111">To make sure that depreciation is correct when you reverse a transaction, do not continue with the reversal if you receive a message that states that depreciation will not be recalculated.</span></span> <span data-ttu-id="6c164-112">Contrepassez d'abord la transaction d'amortissement validée après la transaction que vous tentez de contrepasser, puis poursuivez la contrepassation.</span><span class="sxs-lookup"><span data-stu-id="6c164-112">Instead, first reverse the depreciation transaction that was posted after the transaction you tried to reverse, and then continue with the reversal.</span></span> <span data-ttu-id="6c164-113">Aucun message sur les nouveaux calculs d'amortissement ne s'affiche et vous pouvez poursuivre la contrepassation.</span><span class="sxs-lookup"><span data-stu-id="6c164-113">You will not be warned about depreciation recalculations, and you can continue with the reversal.</span></span> 

<span data-ttu-id="6c164-114">Les exemples suivants indiquent les calculs qui interviennent si vous ignorez le message d'avertissement en ne contrepassant pas préalablement les transactions d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="6c164-114">The following examples show the calculations that occur if you continue beyond the message without first reversing the depreciation transactions.</span></span>

## <a name="example-1-depreciation-is-overstated"></a><span data-ttu-id="6c164-115">Exemple 1 : l'amortissement est surévalué</span><span class="sxs-lookup"><span data-stu-id="6c164-115">Example 1: Depreciation is overstated</span></span>
<span data-ttu-id="6c164-116">Une immobilisation est paramétrée avec une durée de vie utile de 5 ans et un amortissement linéaire (60 périodes d'amortissement).</span><span class="sxs-lookup"><span data-stu-id="6c164-116">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="6c164-117">Dans cet exemple, l'amortissement est surévalué.</span><span class="sxs-lookup"><span data-stu-id="6c164-117">In this example, depreciation is overstated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="6c164-118">Historique de la transaction d'immobilisation</span><span class="sxs-lookup"><span data-stu-id="6c164-118">Asset transaction history</span></span>

| <span data-ttu-id="6c164-119">Date</span><span class="sxs-lookup"><span data-stu-id="6c164-119">Date</span></span>       | <span data-ttu-id="6c164-120">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="6c164-120">Transaction type</span></span>                                                          | <span data-ttu-id="6c164-121">Montant</span><span class="sxs-lookup"><span data-stu-id="6c164-121">Amount</span></span>                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| <span data-ttu-id="6c164-122">1er janvier</span><span class="sxs-lookup"><span data-stu-id="6c164-122">January 1</span></span>  | <span data-ttu-id="6c164-123">Acquisition</span><span class="sxs-lookup"><span data-stu-id="6c164-123">Acquisition</span></span>                                                               | <span data-ttu-id="6c164-124">59 000,00</span><span class="sxs-lookup"><span data-stu-id="6c164-124">59,000.00</span></span>                                 |
| <span data-ttu-id="6c164-125">1er janvier</span><span class="sxs-lookup"><span data-stu-id="6c164-125">January 1</span></span>  | <span data-ttu-id="6c164-126">Ajustement d'acquisition</span><span class="sxs-lookup"><span data-stu-id="6c164-126">Acquisition adjustment</span></span>                                                    | <span data-ttu-id="6c164-127">1 000,00</span><span class="sxs-lookup"><span data-stu-id="6c164-127">1,000.00</span></span>                                  |
| <span data-ttu-id="6c164-128">31 janvier</span><span class="sxs-lookup"><span data-stu-id="6c164-128">January 31</span></span> | <span data-ttu-id="6c164-129">Amortissement (créé à l'aide d'une proposition pour une période d'amortissement)</span><span class="sxs-lookup"><span data-stu-id="6c164-129">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="6c164-130">1 000,00Calcul : valeur comptable (59 000 + 1 000) / nombre de périodes d'amortissement restantes (60)</span><span class="sxs-lookup"><span data-stu-id="6c164-130">1,000.00Calculation: Book value (59,000 + 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="6c164-131">Action de contrepassation</span><span class="sxs-lookup"><span data-stu-id="6c164-131">Reversal action</span></span>

| <span data-ttu-id="6c164-132">Date</span><span class="sxs-lookup"><span data-stu-id="6c164-132">Date</span></span>      | <span data-ttu-id="6c164-133">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="6c164-133">Transaction type</span></span>                | <span data-ttu-id="6c164-134">Montant</span><span class="sxs-lookup"><span data-stu-id="6c164-134">Amount</span></span>    |
|-----------|---------------------------------|-----------|
| <span data-ttu-id="6c164-135">1er janvier</span><span class="sxs-lookup"><span data-stu-id="6c164-135">January 1</span></span> | <span data-ttu-id="6c164-136">Contrepassation d'ajustement d'acquisition</span><span class="sxs-lookup"><span data-stu-id="6c164-136">Acquisition adjustment reversal</span></span> | <span data-ttu-id="6c164-137">–1 000,00</span><span class="sxs-lookup"><span data-stu-id="6c164-137">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="6c164-138">Effet d'amortissement</span><span class="sxs-lookup"><span data-stu-id="6c164-138">Depreciation effect</span></span>

| <span data-ttu-id="6c164-139">Date</span><span class="sxs-lookup"><span data-stu-id="6c164-139">Date</span></span>        | <span data-ttu-id="6c164-140">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="6c164-140">Transaction type</span></span>        | <span data-ttu-id="6c164-141">Montant</span><span class="sxs-lookup"><span data-stu-id="6c164-141">Amount</span></span>                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| <span data-ttu-id="6c164-142">28 février</span><span class="sxs-lookup"><span data-stu-id="6c164-142">February 28</span></span> | <span data-ttu-id="6c164-143">Amortissement (proposition)</span><span class="sxs-lookup"><span data-stu-id="6c164-143">Depreciation (proposal)</span></span> | <span data-ttu-id="6c164-144">983,05Calcul : valeur comptable (59 000 - 1 000 amortissements) / nombre de périodes d'amortissement restantes (59)</span><span class="sxs-lookup"><span data-stu-id="6c164-144">983.05Calculation: Book value (59,000 - 1,000 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="6c164-145">L'amortissement est surévalué de 16,95 (1 000 - 983,05).</span><span class="sxs-lookup"><span data-stu-id="6c164-145">Depreciation is overstated by 16.95 (1,000 - 983.05).</span></span>

## <a name="example-2-depreciation-is-understated"></a><span data-ttu-id="6c164-146">Exemple 2 : l'amortissement est sous-évalué</span><span class="sxs-lookup"><span data-stu-id="6c164-146">Example 2: Depreciation is understated</span></span>
<span data-ttu-id="6c164-147">Une immobilisation est paramétrée avec une durée de vie utile de 5 ans et un amortissement linéaire (60 périodes d'amortissement).</span><span class="sxs-lookup"><span data-stu-id="6c164-147">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="6c164-148">Dans cet exemple, l'amortissement est sous-évalué.</span><span class="sxs-lookup"><span data-stu-id="6c164-148">In this example, depreciation is understated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="6c164-149">Historique de la transaction d'immobilisation</span><span class="sxs-lookup"><span data-stu-id="6c164-149">Asset transaction history</span></span>

| <span data-ttu-id="6c164-150">Date</span><span class="sxs-lookup"><span data-stu-id="6c164-150">Date</span></span>       | <span data-ttu-id="6c164-151">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="6c164-151">Transaction type</span></span>                                                          | <span data-ttu-id="6c164-152">Montant</span><span class="sxs-lookup"><span data-stu-id="6c164-152">Amount</span></span>                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="6c164-153">1er janvier</span><span class="sxs-lookup"><span data-stu-id="6c164-153">January 1</span></span>  | <span data-ttu-id="6c164-154">Acquisition</span><span class="sxs-lookup"><span data-stu-id="6c164-154">Acquisition</span></span>                                                               | <span data-ttu-id="6c164-155">59 000,00</span><span class="sxs-lookup"><span data-stu-id="6c164-155">59,000.00</span></span>                                   |
| <span data-ttu-id="6c164-156">1er janvier</span><span class="sxs-lookup"><span data-stu-id="6c164-156">January 1</span></span>  | <span data-ttu-id="6c164-157">Diminution</span><span class="sxs-lookup"><span data-stu-id="6c164-157">Write-down adjustment</span></span>                                                     | <span data-ttu-id="6c164-158">1 000,00</span><span class="sxs-lookup"><span data-stu-id="6c164-158">1,000.00</span></span>                                    |
| <span data-ttu-id="6c164-159">31 janvier</span><span class="sxs-lookup"><span data-stu-id="6c164-159">January 31</span></span> | <span data-ttu-id="6c164-160">Amortissement (créé à l'aide d'une proposition pour une période d'amortissement)</span><span class="sxs-lookup"><span data-stu-id="6c164-160">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="6c164-161">966,67Calcul : valeur comptable (59 000 - 1 000) / nombre de périodes d'amortissement restantes (60)</span><span class="sxs-lookup"><span data-stu-id="6c164-161">966.67Calculation: Book value (59,000 - 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="6c164-162">Action de contrepassation</span><span class="sxs-lookup"><span data-stu-id="6c164-162">Reversal action</span></span>

| <span data-ttu-id="6c164-163">Date</span><span class="sxs-lookup"><span data-stu-id="6c164-163">Date</span></span>      | <span data-ttu-id="6c164-164">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="6c164-164">Transaction type</span></span>               | <span data-ttu-id="6c164-165">Montant</span><span class="sxs-lookup"><span data-stu-id="6c164-165">Amount</span></span>    |
|-----------|--------------------------------|-----------|
| <span data-ttu-id="6c164-166">1er janvier</span><span class="sxs-lookup"><span data-stu-id="6c164-166">January 1</span></span> | <span data-ttu-id="6c164-167">Contrepassation de diminutions</span><span class="sxs-lookup"><span data-stu-id="6c164-167">Write-down adjustment reversal</span></span> | <span data-ttu-id="6c164-168">–1 000,00</span><span class="sxs-lookup"><span data-stu-id="6c164-168">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="6c164-169">Effet d'amortissement</span><span class="sxs-lookup"><span data-stu-id="6c164-169">Depreciation effect</span></span>

| <span data-ttu-id="6c164-170">Date</span><span class="sxs-lookup"><span data-stu-id="6c164-170">Date</span></span>        | <span data-ttu-id="6c164-171">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="6c164-171">Transaction type</span></span>        | <span data-ttu-id="6c164-172">Montant</span><span class="sxs-lookup"><span data-stu-id="6c164-172">Amount</span></span>                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| <span data-ttu-id="6c164-173">28 février</span><span class="sxs-lookup"><span data-stu-id="6c164-173">February 28</span></span> | <span data-ttu-id="6c164-174">Amortissement (proposition)</span><span class="sxs-lookup"><span data-stu-id="6c164-174">Depreciation (proposal)</span></span> | <span data-ttu-id="6c164-175">983,62Calcul : valeur comptable (59 000 - 966,67 amortissements) / nombre de périodes d'amortissement restantes (59)</span><span class="sxs-lookup"><span data-stu-id="6c164-175">983.62Calculation: Book value (59,000 - 966.67 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="6c164-176">L'amortissement est sous-évalué de 16,95 (983,62 - 966,67).</span><span class="sxs-lookup"><span data-stu-id="6c164-176">Depreciation is understated by 16.95 (983.62 - 966.67).</span></span>



<a name="additional-resources"></a><span data-ttu-id="6c164-177">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6c164-177">Additional resources</span></span>
--------

[<span data-ttu-id="6c164-178">Amortissement des immobilisations</span><span class="sxs-lookup"><span data-stu-id="6c164-178">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)



