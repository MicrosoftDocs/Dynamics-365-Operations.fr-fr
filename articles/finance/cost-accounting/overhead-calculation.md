---
title: Calcul des frais généraux
description: Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 923e6e38a664e17ec3349d839c4b77ec903c5dc2
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976473"
---
# <a name="overhead-calculation"></a><span data-ttu-id="ba93c-103">Calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="ba93c-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ba93c-104">Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="ba93c-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="ba93c-105">Définition des termes</span><span class="sxs-lookup"><span data-stu-id="ba93c-105">Term definition</span></span>
---------------

<span data-ttu-id="ba93c-106">Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique.</span><span class="sxs-lookup"><span data-stu-id="ba93c-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="ba93c-107">Les frais généraux permettent essentiellement l’identification des activités rémunératrices.</span><span class="sxs-lookup"><span data-stu-id="ba93c-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="ba93c-108">Voici quelques exemples de frais généraux :</span><span class="sxs-lookup"><span data-stu-id="ba93c-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="ba93c-109">Loyer</span><span class="sxs-lookup"><span data-stu-id="ba93c-109">Rent</span></span>
-   <span data-ttu-id="ba93c-110">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-110">Electricity</span></span>
-   <span data-ttu-id="ba93c-111">Salaires administratifs</span><span class="sxs-lookup"><span data-stu-id="ba93c-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="ba93c-112">Vue d’ensemble du calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="ba93c-112">Overhead calculation overview</span></span>
<span data-ttu-id="ba93c-113">Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l’ordre correct.</span><span class="sxs-lookup"><span data-stu-id="ba93c-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="ba93c-114">Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées.</span><span class="sxs-lookup"><span data-stu-id="ba93c-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="ba93c-115">Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions.</span><span class="sxs-lookup"><span data-stu-id="ba93c-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="ba93c-116">Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable.</span><span class="sxs-lookup"><span data-stu-id="ba93c-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="ba93c-117">Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="ba93c-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="ba93c-118">L’ID de version unique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ba93c-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="ba93c-119">Type de version</span><span class="sxs-lookup"><span data-stu-id="ba93c-119">Version type</span></span>
-   <span data-ttu-id="ba93c-120">Date et heure</span><span class="sxs-lookup"><span data-stu-id="ba93c-120">Date and time</span></span>
-   <span data-ttu-id="ba93c-121">Comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="ba93c-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="ba93c-122">Exercice</span><span class="sxs-lookup"><span data-stu-id="ba93c-122">Fiscal year</span></span>
-   <span data-ttu-id="ba93c-123">Période fiscale</span><span class="sxs-lookup"><span data-stu-id="ba93c-123">Fiscal period</span></span>

<span data-ttu-id="ba93c-124">Le calcul des frais généraux est effectué indépendamment de la version.</span><span class="sxs-lookup"><span data-stu-id="ba93c-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="ba93c-125">Par conséquent, vous pouvez calculer la version de budget avant la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="ba93c-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="ba93c-126">Le calcul des frais généraux comporte quatre étapes, comme le montre l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="ba93c-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="ba93c-127">Dans chaque étape, un en-tête de journal avec des entrées de journal est créé.</span><span class="sxs-lookup"><span data-stu-id="ba93c-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="ba93c-128">Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul.</span><span class="sxs-lookup"><span data-stu-id="ba93c-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="ba93c-129">Les stratégies et les règles s’appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie.</span><span class="sxs-lookup"><span data-stu-id="ba93c-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="ba93c-130">Par conséquent, vous disposez toujours d’une traçabilité complète.</span><span class="sxs-lookup"><span data-stu-id="ba93c-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="ba93c-131">[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="ba93c-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="ba93c-132">Calculer et affecter les frais généraux Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="ba93c-133">Dans la comptabilité financière, certaines coûts, tels que l’électricité, sont enregistrés comme montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="ba93c-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="ba93c-134">Par conséquent, l’analyse détaillée n’est pas fournie pour le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="ba93c-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="ba93c-135">Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l’organisation, les coûts doivent suivre les unités organisationnelles.</span><span class="sxs-lookup"><span data-stu-id="ba93c-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="ba93c-136">Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste.</span><span class="sxs-lookup"><span data-stu-id="ba93c-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="ba93c-137">Dans la comptabilité, le coût de l’électricité peut être validé comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="ba93c-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ba93c-138">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ba93c-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-139">Centre de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-140">Compte principal</span><span class="sxs-lookup"><span data-stu-id="ba93c-140">Main account</span></span></th>
<th><span data-ttu-id="ba93c-141">Montant en devise comptable</span><span class="sxs-lookup"><span data-stu-id="ba93c-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-142">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="ba93c-143">CC099</span><span class="sxs-lookup"><span data-stu-id="ba93c-143">CC099</span></span></td>
<td><span data-ttu-id="ba93c-144">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ba93c-144">Default cost center</span></span></td>
<td><span data-ttu-id="ba93c-145">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-145">10001</span></span></td>
<td><span data-ttu-id="ba93c-146">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-146">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="ba93c-148">Étape 1 : Traiter le calcul du comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="ba93c-149">Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="ba93c-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="ba93c-150">Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.</span><span class="sxs-lookup"><span data-stu-id="ba93c-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="ba93c-151">Définir la règle de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-151">Define the cost behavior rule</span></span>

<span data-ttu-id="ba93c-152">Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation.</span><span class="sxs-lookup"><span data-stu-id="ba93c-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="ba93c-153">Les factures d’électricité correspondent souvent à cette définition.</span><span class="sxs-lookup"><span data-stu-id="ba93c-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="ba93c-154">Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH).</span><span class="sxs-lookup"><span data-stu-id="ba93c-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="ba93c-155">Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :</span><span class="sxs-lookup"><span data-stu-id="ba93c-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="ba93c-156">Montant fixe 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="ba93c-157">0 &lt;= 1 000,00 = Fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="ba93c-158">1 000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="ba93c-159">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ba93c-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ba93c-160">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ba93c-160">Journal</span></span></th>
<th><span data-ttu-id="ba93c-161">Type de journal</span><span class="sxs-lookup"><span data-stu-id="ba93c-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ba93c-162">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="ba93c-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ba93c-163">Version</span><span class="sxs-lookup"><span data-stu-id="ba93c-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-164">00001</span><span class="sxs-lookup"><span data-stu-id="ba93c-164">00001</span></span></td>
<td><span data-ttu-id="ba93c-165">Journal de calcul de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="ba93c-166">Exercice</span><span class="sxs-lookup"><span data-stu-id="ba93c-166">Fiscal</span></span></td>
<td><span data-ttu-id="ba93c-167">2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-167">2017</span></span></td>
<td><span data-ttu-id="ba93c-168">Période 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-168">Period 1</span></span></td>
<td><span data-ttu-id="ba93c-169">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ba93c-170">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="ba93c-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ba93c-171">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ba93c-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-172">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-173">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-173">Cost element</span></span></th>
<th><span data-ttu-id="ba93c-174">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-174">Cost behavior</span></span></th>
<th><span data-ttu-id="ba93c-175">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-176">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="ba93c-177">CC099</span><span class="sxs-lookup"><span data-stu-id="ba93c-177">CC099</span></span></td>
<td><span data-ttu-id="ba93c-178">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ba93c-178">Default cost center</span></span></td>
<td><span data-ttu-id="ba93c-179">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-179">10001</span></span></td>
<td><span data-ttu-id="ba93c-180">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-180">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-181">Non classifié</span><span class="sxs-lookup"><span data-stu-id="ba93c-181">Unclassified</span></span></td>
<td><span data-ttu-id="ba93c-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ba93c-183">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-184">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-185">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-185">Cost element</span></span></th>
<th><span data-ttu-id="ba93c-186">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-186">Cost behavior</span></span></th>
<th><span data-ttu-id="ba93c-187">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-187">Amount</span></span></th>
<th><span data-ttu-id="ba93c-188">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ba93c-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-189">CC099</span><span class="sxs-lookup"><span data-stu-id="ba93c-189">CC099</span></span></td>
<td><span data-ttu-id="ba93c-190">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ba93c-190">Default cost center</span></span></td>
<td><span data-ttu-id="ba93c-191">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-191">10001</span></span></td>
<td><span data-ttu-id="ba93c-192">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-192">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-193">Non classifié</span><span class="sxs-lookup"><span data-stu-id="ba93c-193">Unclassified</span></span></td>
<td><span data-ttu-id="ba93c-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-194">10,000.00</span></span></td>
<td><span data-ttu-id="ba93c-195">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-196">CC099</span><span class="sxs-lookup"><span data-stu-id="ba93c-196">CC099</span></span></td>
<td><span data-ttu-id="ba93c-197">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ba93c-197">Default cost center</span></span></td>
<td><span data-ttu-id="ba93c-198">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-198">10001</span></span></td>
<td><span data-ttu-id="ba93c-199">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-199">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-200">Non classifié</span><span class="sxs-lookup"><span data-stu-id="ba93c-200">Unclassified</span></span></td>
<td><span data-ttu-id="ba93c-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-201">-10,000.00</span></span></td>
<td><span data-ttu-id="ba93c-202">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-203">CC099</span><span class="sxs-lookup"><span data-stu-id="ba93c-203">CC099</span></span></td>
<td><span data-ttu-id="ba93c-204">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ba93c-204">Default cost center</span></span></td>
<td><span data-ttu-id="ba93c-205">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-205">10001</span></span></td>
<td><span data-ttu-id="ba93c-206">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-206">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-207">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-207">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-208">1,000.00</span></span></td>
<td><span data-ttu-id="ba93c-209">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-210">CC099</span><span class="sxs-lookup"><span data-stu-id="ba93c-210">CC099</span></span></td>
<td><span data-ttu-id="ba93c-211">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ba93c-211">Default cost center</span></span></td>
<td><span data-ttu-id="ba93c-212">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-212">10001</span></span></td>
<td><span data-ttu-id="ba93c-213">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-213">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-214">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-214">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-215">9 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-215">9,000.00</span></span></td>
<td><span data-ttu-id="ba93c-216">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-217">Pour plus d’informations, voir [Créer et affecter une stratégie de comportement de coûts à une unité de contrôle des coûts](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="ba93c-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="ba93c-218">Étape 2 : Traiter le calcul de distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="ba93c-219">La distribution des coûts est utilisée pour redistribuer le coût d’un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée.</span><span class="sxs-lookup"><span data-stu-id="ba93c-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="ba93c-220">La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l’élément de coût principal du coût d’origine.</span><span class="sxs-lookup"><span data-stu-id="ba93c-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="ba93c-221">Définir la règle de distribution de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-221">Define the cost distribution rule</span></span>

<span data-ttu-id="ba93c-222">Dans la comptabilité financière, les coûts d’électricité sont souvent enregistrés comme un montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="ba93c-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="ba93c-223">Dans le Contrôle de gestion, cette approche n’est pas assez détaillée.</span><span class="sxs-lookup"><span data-stu-id="ba93c-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="ba93c-224">Le coût variable doit être attribué aux différents objets de coûts sur une base juste.</span><span class="sxs-lookup"><span data-stu-id="ba93c-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="ba93c-225">La base de répartition la plus logique est la consommation de l’électricité (KWH).</span><span class="sxs-lookup"><span data-stu-id="ba93c-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="ba93c-226">Un membre de dimension statistique nommé Électricité est créé, et la consommation d’électricité est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="ba93c-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="ba93c-227">Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="ba93c-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-228">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-228">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="ba93c-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-230">CC001</span><span class="sxs-lookup"><span data-stu-id="ba93c-230">CC001</span></span></td>
<td><span data-ttu-id="ba93c-231">RH</span><span class="sxs-lookup"><span data-stu-id="ba93c-231">HR</span></span></td>
<td><span data-ttu-id="ba93c-232">1 000</span><span class="sxs-lookup"><span data-stu-id="ba93c-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-233">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-233">CC002</span></span></td>
<td><span data-ttu-id="ba93c-234">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-234">Finance</span></span></td>
<td><span data-ttu-id="ba93c-235">6 000</span><span class="sxs-lookup"><span data-stu-id="ba93c-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-236">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-236">CC003</span></span></td>
<td><span data-ttu-id="ba93c-237">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-237">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-238">0</span><span class="sxs-lookup"><span data-stu-id="ba93c-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-239">Le tableau suivant illustre le résultat lorsque la consommation d’électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="ba93c-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-240">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-240">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-241">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ba93c-241">Magnitude</span></span></th>
<th><span data-ttu-id="ba93c-242">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ba93c-242">Allocation factor</span></span></th>
<th><span data-ttu-id="ba93c-243">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-244">CC001</span><span class="sxs-lookup"><span data-stu-id="ba93c-244">CC001</span></span></td>
<td><span data-ttu-id="ba93c-245">RH</span><span class="sxs-lookup"><span data-stu-id="ba93c-245">HR</span></span></td>
<td><span data-ttu-id="ba93c-246">1 000</span><span class="sxs-lookup"><span data-stu-id="ba93c-246">1,000</span></span></td>
<td><span data-ttu-id="ba93c-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ba93c-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ba93c-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-249">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-249">CC002</span></span></td>
<td><span data-ttu-id="ba93c-250">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-250">Finance</span></span></td>
<td><span data-ttu-id="ba93c-251">6 000</span><span class="sxs-lookup"><span data-stu-id="ba93c-251">6,000</span></span></td>
<td><span data-ttu-id="ba93c-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ba93c-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ba93c-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-254">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-254">CC003</span></span></td>
<td><span data-ttu-id="ba93c-255">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-255">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-256">0</span><span class="sxs-lookup"><span data-stu-id="ba93c-256">0</span></span></td>
<td><span data-ttu-id="ba93c-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ba93c-258">0,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-259">Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l’électricité.</span><span class="sxs-lookup"><span data-stu-id="ba93c-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="ba93c-260">Vous pouvez obtenir ce résultat à l’aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d’électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="ba93c-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-261">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-261">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-262">Formule</span><span class="sxs-lookup"><span data-stu-id="ba93c-262">Formula</span></span></th>
<th><span data-ttu-id="ba93c-263">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ba93c-263">Magnitude</span></span></th>
<th><span data-ttu-id="ba93c-264">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ba93c-264">Allocation factor</span></span></th>
<th><span data-ttu-id="ba93c-265">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-266">CC001</span><span class="sxs-lookup"><span data-stu-id="ba93c-266">CC001</span></span></td>
<td><span data-ttu-id="ba93c-267">RH</span><span class="sxs-lookup"><span data-stu-id="ba93c-267">HR</span></span></td>
<td><span data-ttu-id="ba93c-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ba93c-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ba93c-269">1</span><span class="sxs-lookup"><span data-stu-id="ba93c-269">1</span></span></td>
<td><span data-ttu-id="ba93c-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ba93c-271">500,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-272">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-272">CC002</span></span></td>
<td><span data-ttu-id="ba93c-273">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-273">Finance</span></span></td>
<td><span data-ttu-id="ba93c-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ba93c-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ba93c-275">1</span><span class="sxs-lookup"><span data-stu-id="ba93c-275">1</span></span></td>
<td><span data-ttu-id="ba93c-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ba93c-277">500,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-278">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-278">CC003</span></span></td>
<td><span data-ttu-id="ba93c-279">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-279">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ba93c-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ba93c-281">0</span><span class="sxs-lookup"><span data-stu-id="ba93c-281">0</span></span></td>
<td><span data-ttu-id="ba93c-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ba93c-283">0,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ba93c-284">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ba93c-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ba93c-285">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ba93c-285">Journal</span></span></th>
<th><span data-ttu-id="ba93c-286">Type de journal</span><span class="sxs-lookup"><span data-stu-id="ba93c-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ba93c-287">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="ba93c-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ba93c-288">Version</span><span class="sxs-lookup"><span data-stu-id="ba93c-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-289">00002</span><span class="sxs-lookup"><span data-stu-id="ba93c-289">00002</span></span></td>
<td><span data-ttu-id="ba93c-290">Journal de calcul de la distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="ba93c-291">Exercice</span><span class="sxs-lookup"><span data-stu-id="ba93c-291">Fiscal</span></span></td>
<td><span data-ttu-id="ba93c-292">2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-292">2017</span></span></td>
<td><span data-ttu-id="ba93c-293">Période 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-293">Period 1</span></span></td>
<td><span data-ttu-id="ba93c-294">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ba93c-295">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="ba93c-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ba93c-296">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ba93c-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-297">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-298">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-298">Cost element</span></span></th>
<th><span data-ttu-id="ba93c-299">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-299">Cost behavior</span></span></th>
<th><span data-ttu-id="ba93c-300">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-301">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-302">CC099</span><span class="sxs-lookup"><span data-stu-id="ba93c-302">CC099</span></span></td>
<td><span data-ttu-id="ba93c-303">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ba93c-303">Default cost center</span></span></td>
<td><span data-ttu-id="ba93c-304">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-304">10001</span></span></td>
<td><span data-ttu-id="ba93c-305">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-305">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-306">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-306">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-308">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-309">CC099</span><span class="sxs-lookup"><span data-stu-id="ba93c-309">CC099</span></span></td>
<td><span data-ttu-id="ba93c-310">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ba93c-310">Default cost center</span></span></td>
<td><span data-ttu-id="ba93c-311">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-311">10001</span></span></td>
<td><span data-ttu-id="ba93c-312">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-312">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-313">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-313">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-314">9 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ba93c-315">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-316">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-317">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-317">Cost element</span></span></th>
<th><span data-ttu-id="ba93c-318">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-318">Cost behavior</span></span></th>
<th><span data-ttu-id="ba93c-319">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-319">Amount</span></span></th>
<th><span data-ttu-id="ba93c-320">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ba93c-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-321">CC099</span><span class="sxs-lookup"><span data-stu-id="ba93c-321">CC099</span></span></td>
<td><span data-ttu-id="ba93c-322">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ba93c-322">Default cost center</span></span></td>
<td><span data-ttu-id="ba93c-323">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-323">10001</span></span></td>
<td><span data-ttu-id="ba93c-324">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-324">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-325">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-325">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-326">-1,000.00</span></span></td>
<td><span data-ttu-id="ba93c-327">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-328">CC001</span><span class="sxs-lookup"><span data-stu-id="ba93c-328">CC001</span></span></td>
<td><span data-ttu-id="ba93c-329">RH</span><span class="sxs-lookup"><span data-stu-id="ba93c-329">HR</span></span></td>
<td><span data-ttu-id="ba93c-330">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-330">10001</span></span></td>
<td><span data-ttu-id="ba93c-331">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-331">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-332">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-332">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-333">500,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-333">500.00</span></span></td>
<td><span data-ttu-id="ba93c-334">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-335">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-335">CC002</span></span></td>
<td><span data-ttu-id="ba93c-336">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-336">Finance</span></span></td>
<td><span data-ttu-id="ba93c-337">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-337">10001</span></span></td>
<td><span data-ttu-id="ba93c-338">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-338">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-339">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-339">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-340">500,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-340">500.00</span></span></td>
<td><span data-ttu-id="ba93c-341">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-342">CC099</span><span class="sxs-lookup"><span data-stu-id="ba93c-342">CC099</span></span></td>
<td><span data-ttu-id="ba93c-343">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ba93c-343">Default cost center</span></span></td>
<td><span data-ttu-id="ba93c-344">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-344">10001</span></span></td>
<td><span data-ttu-id="ba93c-345">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-345">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-346">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-346">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-347">-9,000.00</span></span></td>
<td><span data-ttu-id="ba93c-348">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-349">CC001</span><span class="sxs-lookup"><span data-stu-id="ba93c-349">CC001</span></span></td>
<td><span data-ttu-id="ba93c-350">RH</span><span class="sxs-lookup"><span data-stu-id="ba93c-350">HR</span></span></td>
<td><span data-ttu-id="ba93c-351">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-351">10001</span></span></td>
<td><span data-ttu-id="ba93c-352">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-352">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-353">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-353">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ba93c-354">1,285.71</span></span></td>
<td><span data-ttu-id="ba93c-355">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-356">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-356">CC002</span></span></td>
<td><span data-ttu-id="ba93c-357">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-357">Finance</span></span></td>
<td><span data-ttu-id="ba93c-358">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-358">10001</span></span></td>
<td><span data-ttu-id="ba93c-359">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-359">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-360">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-360">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ba93c-361">7,714.29</span></span></td>
<td><span data-ttu-id="ba93c-362">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-363">Pour plus d’informations, voir [Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="ba93c-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="ba93c-364">Étape 3 : Traitement du calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="ba93c-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="ba93c-365">Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût.</span><span class="sxs-lookup"><span data-stu-id="ba93c-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="ba93c-366">Les frais sont basés sur un taux de coût prédéterminé et l’ampleur de la base d’affectation de répartition.</span><span class="sxs-lookup"><span data-stu-id="ba93c-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="ba93c-367">Définition du taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="ba93c-367">Define the overhead rate</span></span>

<span data-ttu-id="ba93c-368">L’objet de coût CC001 HR contribue à un ensemble de projets internes.</span><span class="sxs-lookup"><span data-stu-id="ba93c-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="ba93c-369">Un membre de dimension statistique nommé Projets HR est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ba93c-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-370">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-370">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-371">Heures</span><span class="sxs-lookup"><span data-stu-id="ba93c-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-372">Proj 1</span></span></td>
<td><span data-ttu-id="ba93c-373">Projet 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-373">Project 1</span></span></td>
<td><span data-ttu-id="ba93c-374">3</span><span class="sxs-lookup"><span data-stu-id="ba93c-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-375">Proj 2</span></span></td>
<td><span data-ttu-id="ba93c-376">Projet 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-376">Project 2</span></span></td>
<td><span data-ttu-id="ba93c-377">1</span><span class="sxs-lookup"><span data-stu-id="ba93c-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-378">Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.</span><span class="sxs-lookup"><span data-stu-id="ba93c-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-379">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-379">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-380">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-380">Cost element</span></span></th>
<th><span data-ttu-id="ba93c-381">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-381">Cost behavior</span></span></th>
<th><span data-ttu-id="ba93c-382">Unités</span><span class="sxs-lookup"><span data-stu-id="ba93c-382">Units</span></span></th>
<th><span data-ttu-id="ba93c-383">Taux</span><span class="sxs-lookup"><span data-stu-id="ba93c-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-384">CC001</span><span class="sxs-lookup"><span data-stu-id="ba93c-384">CC001</span></span></td>
<td><span data-ttu-id="ba93c-385">RH</span><span class="sxs-lookup"><span data-stu-id="ba93c-385">HR</span></span></td>
<td><span data-ttu-id="ba93c-386">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-386">10001</span></span></td>
<td><span data-ttu-id="ba93c-387">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-387">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-388">1</span><span class="sxs-lookup"><span data-stu-id="ba93c-388">1</span></span></td>
<td><span data-ttu-id="ba93c-389">10</span><span class="sxs-lookup"><span data-stu-id="ba93c-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-390">Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="ba93c-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-391">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-391">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-392">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ba93c-392">Magnitude</span></span></th>
<th><span data-ttu-id="ba93c-393">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-393">Cost element</span></span></th>
<th><span data-ttu-id="ba93c-394">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ba93c-394">Allocation factor</span></span></th>
<th><span data-ttu-id="ba93c-395">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-396">Proj 1</span></span></td>
<td><span data-ttu-id="ba93c-397">Projet 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-397">Project 1</span></span></td>
<td><span data-ttu-id="ba93c-398">3</span><span class="sxs-lookup"><span data-stu-id="ba93c-398">3</span></span></td>
<td><span data-ttu-id="ba93c-399">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-399">10001</span></span></td>
<td><span data-ttu-id="ba93c-400">(3 ÷ 1) × 10m00</span><span class="sxs-lookup"><span data-stu-id="ba93c-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ba93c-401">30,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-402">Proj 2</span></span></td>
<td><span data-ttu-id="ba93c-403">Projet 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-403">Project 2</span></span></td>
<td><span data-ttu-id="ba93c-404">1</span><span class="sxs-lookup"><span data-stu-id="ba93c-404">1</span></span></td>
<td><span data-ttu-id="ba93c-405">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-405">10001</span></span></td>
<td><span data-ttu-id="ba93c-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ba93c-407">10,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ba93c-408">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ba93c-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ba93c-409">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ba93c-409">Journal</span></span></th>
<th><span data-ttu-id="ba93c-410">Type de journal</span><span class="sxs-lookup"><span data-stu-id="ba93c-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ba93c-411">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="ba93c-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ba93c-412">Version</span><span class="sxs-lookup"><span data-stu-id="ba93c-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-413">00003</span><span class="sxs-lookup"><span data-stu-id="ba93c-413">00003</span></span></td>
<td><span data-ttu-id="ba93c-414">Journal de calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="ba93c-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="ba93c-415">Exercice</span><span class="sxs-lookup"><span data-stu-id="ba93c-415">Fiscal</span></span></td>
<td><span data-ttu-id="ba93c-416">2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-416">2017</span></span></td>
<td><span data-ttu-id="ba93c-417">Période 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-417">Period 1</span></span></td>
<td><span data-ttu-id="ba93c-418">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="ba93c-419">Entrées du journal (pour le calcul du taux de frais généraux)</span><span class="sxs-lookup"><span data-stu-id="ba93c-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ba93c-420">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ba93c-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-421">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-421">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-422">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ba93c-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-423">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-424">Proj 1</span></span></td>
<td><span data-ttu-id="ba93c-425">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ba93c-426">3,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-427">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-428">Proj 2</span></span></td>
<td><span data-ttu-id="ba93c-429">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ba93c-430">1,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ba93c-431">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-432">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-433">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-433">Cost element</span></span></th>
<th><span data-ttu-id="ba93c-434">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-434">Cost behavior</span></span></th>
<th><span data-ttu-id="ba93c-435">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-435">Amount</span></span></th>
<th><span data-ttu-id="ba93c-436">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ba93c-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="ba93c-437">CC0001</span></span></td>
<td><span data-ttu-id="ba93c-438">RH</span><span class="sxs-lookup"><span data-stu-id="ba93c-438">HR</span></span></td>
<td><span data-ttu-id="ba93c-439">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-439">10001</span></span></td>
<td><span data-ttu-id="ba93c-440">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-440">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-441">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-441">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-442">-30.00</span></span></td>
<td><span data-ttu-id="ba93c-443">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-444">Proj 1</span></span></td>
<td><span data-ttu-id="ba93c-445">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ba93c-446">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-446">10001</span></span></td>
<td><span data-ttu-id="ba93c-447">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-447">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-448">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-448">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-449">30,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-449">30.00</span></span></td>
<td><span data-ttu-id="ba93c-450">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-451">CC001</span><span class="sxs-lookup"><span data-stu-id="ba93c-451">CC001</span></span></td>
<td><span data-ttu-id="ba93c-452">RH</span><span class="sxs-lookup"><span data-stu-id="ba93c-452">HR</span></span></td>
<td><span data-ttu-id="ba93c-453">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-453">10001</span></span></td>
<td><span data-ttu-id="ba93c-454">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-454">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-455">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-455">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-456">-10.00</span></span></td>
<td><span data-ttu-id="ba93c-457">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-458">Proj 2</span></span></td>
<td><span data-ttu-id="ba93c-459">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ba93c-460">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-460">10001</span></span></td>
<td><span data-ttu-id="ba93c-461">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-461">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-462">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-462">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-463">10.00</span><span class="sxs-lookup"><span data-stu-id="ba93c-463">10.00</span></span></td>
<td><span data-ttu-id="ba93c-464">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-465">Pour plus d’informations, voir [Exécuter le calcul des frais généraux](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="ba93c-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="ba93c-466">Étape 4 : Traiter le calcul de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="ba93c-467">La répartition est utilisée pour affecter le solde d’un objet de coût à d’autres objets de coût en appliquant une base de répartition.</span><span class="sxs-lookup"><span data-stu-id="ba93c-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="ba93c-468">Finance prend en charge la méthode de répartition réciproque.</span><span class="sxs-lookup"><span data-stu-id="ba93c-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="ba93c-469">Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés.</span><span class="sxs-lookup"><span data-stu-id="ba93c-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="ba93c-470">Le système détermine automatiquement l’ordre correct selon lequel exécuter les répartitions.</span><span class="sxs-lookup"><span data-stu-id="ba93c-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="ba93c-471">Le solde d’un objet de coût est réparti par une seule base de répartition.</span><span class="sxs-lookup"><span data-stu-id="ba93c-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="ba93c-472">Les répartitions entre plusieurs dimensions d’objets de coût et leurs membres respectifs sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="ba93c-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="ba93c-473">L’ordre de répartition est contrôlé par l’unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="ba93c-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="ba93c-474">[![Méthode réciproque](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="ba93c-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="ba93c-475">Définir la répartition de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-475">Define the cost allocation</span></span>

<span data-ttu-id="ba93c-476">Voici un exemple simple expliquant comment suivre le flux du coût.</span><span class="sxs-lookup"><span data-stu-id="ba93c-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="ba93c-477">L’objet de coût CC001 HR contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="ba93c-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="ba93c-478">Un membre de dimension statistique nommé Services HR est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ba93c-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-479">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-479">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-480">Services HR</span><span class="sxs-lookup"><span data-stu-id="ba93c-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-481">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-481">CC002</span></span></td>
<td><span data-ttu-id="ba93c-482">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-482">Finance</span></span></td>
<td><span data-ttu-id="ba93c-483">35</span><span class="sxs-lookup"><span data-stu-id="ba93c-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-484">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-484">CC003</span></span></td>
<td><span data-ttu-id="ba93c-485">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-485">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-486">55</span><span class="sxs-lookup"><span data-stu-id="ba93c-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-487">CC004</span><span class="sxs-lookup"><span data-stu-id="ba93c-487">CC004</span></span></td>
<td><span data-ttu-id="ba93c-488">Emballage</span><span class="sxs-lookup"><span data-stu-id="ba93c-488">Packaging</span></span></td>
<td><span data-ttu-id="ba93c-489">10</span><span class="sxs-lookup"><span data-stu-id="ba93c-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-490">L’objet de coût CC002 Finance contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="ba93c-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="ba93c-491">Un membre de dimension statistique nommé Services Finance est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ba93c-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-492">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-492">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-493">Services Finance</span><span class="sxs-lookup"><span data-stu-id="ba93c-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-494">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-494">CC003</span></span></td>
<td><span data-ttu-id="ba93c-495">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-495">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-496">65</span><span class="sxs-lookup"><span data-stu-id="ba93c-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-497">CC004</span><span class="sxs-lookup"><span data-stu-id="ba93c-497">CC004</span></span></td>
<td><span data-ttu-id="ba93c-498">Emballage</span><span class="sxs-lookup"><span data-stu-id="ba93c-498">Packaging</span></span></td>
<td><span data-ttu-id="ba93c-499">35</span><span class="sxs-lookup"><span data-stu-id="ba93c-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-500">L’objet de coût CC003 Assemblage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="ba93c-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="ba93c-501">Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ba93c-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-502">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-502">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-503">Services Assemblage (heures)</span><span class="sxs-lookup"><span data-stu-id="ba93c-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-504">Prod 1</span></span></td>
<td><span data-ttu-id="ba93c-505">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-505">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-506">60</span><span class="sxs-lookup"><span data-stu-id="ba93c-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-507">Prod 2</span></span></td>
<td><span data-ttu-id="ba93c-508">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-508">Product 2</span></span></td>
<td><span data-ttu-id="ba93c-509">20</span><span class="sxs-lookup"><span data-stu-id="ba93c-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-510">L’objet de coût CC004 Emballage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="ba93c-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="ba93c-511">Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ba93c-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-512">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-512">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-513">Services Emballage (heures)</span><span class="sxs-lookup"><span data-stu-id="ba93c-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-514">Prod 1</span></span></td>
<td><span data-ttu-id="ba93c-515">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-515">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-516">80</span><span class="sxs-lookup"><span data-stu-id="ba93c-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-517">Prod 2</span></span></td>
<td><span data-ttu-id="ba93c-518">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-518">Product 2</span></span></td>
<td><span data-ttu-id="ba93c-519">15</span><span class="sxs-lookup"><span data-stu-id="ba93c-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ba93c-520">Les mesures statistiques telles que les heures de production qu’un produit consomme peuvent être dérivées des données sources.</span><span class="sxs-lookup"><span data-stu-id="ba93c-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="ba93c-521">Pour plus d’informations, voir [Modèle de fournisseur de mesures statistiques](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="ba93c-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="ba93c-522">Le tableau suivant présente le résultat lorsque les services RH sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="ba93c-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-523">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-523">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-524">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ba93c-524">Magnitude</span></span></th>
<th><span data-ttu-id="ba93c-525">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ba93c-525">Allocation factor</span></span></th>
<th><span data-ttu-id="ba93c-526">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-526">Amount</span></span></th>
<th><span data-ttu-id="ba93c-527">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-528">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-528">CC002</span></span></td>
<td><span data-ttu-id="ba93c-529">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-529">Finance</span></span></td>
<td><span data-ttu-id="ba93c-530">35</span><span class="sxs-lookup"><span data-stu-id="ba93c-530">35</span></span></td>
<td><span data-ttu-id="ba93c-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ba93c-532">175.00</span><span class="sxs-lookup"><span data-stu-id="ba93c-532">175.00</span></span></td>
<td><span data-ttu-id="ba93c-533">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-534">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-534">CC003</span></span></td>
<td><span data-ttu-id="ba93c-535">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-535">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-536">55</span><span class="sxs-lookup"><span data-stu-id="ba93c-536">55</span></span></td>
<td><span data-ttu-id="ba93c-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ba93c-538">275.00</span><span class="sxs-lookup"><span data-stu-id="ba93c-538">275.00</span></span></td>
<td><span data-ttu-id="ba93c-539">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-540">CC004</span><span class="sxs-lookup"><span data-stu-id="ba93c-540">CC004</span></span></td>
<td><span data-ttu-id="ba93c-541">Emballage</span><span class="sxs-lookup"><span data-stu-id="ba93c-541">Packaging</span></span></td>
<td><span data-ttu-id="ba93c-542">10</span><span class="sxs-lookup"><span data-stu-id="ba93c-542">10</span></span></td>
<td><span data-ttu-id="ba93c-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ba93c-544">50,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-544">50.00</span></span></td>
<td><span data-ttu-id="ba93c-545">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-546">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-546">CC002</span></span></td>
<td><span data-ttu-id="ba93c-547">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-547">Finance</span></span></td>
<td><span data-ttu-id="ba93c-548">35</span><span class="sxs-lookup"><span data-stu-id="ba93c-548">35</span></span></td>
<td><span data-ttu-id="ba93c-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="ba93c-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ba93c-550">436.00</span><span class="sxs-lookup"><span data-stu-id="ba93c-550">436.00</span></span></td>
<td><span data-ttu-id="ba93c-551">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-552">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-552">CC003</span></span></td>
<td><span data-ttu-id="ba93c-553">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-553">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-554">55</span><span class="sxs-lookup"><span data-stu-id="ba93c-554">55</span></span></td>
<td><span data-ttu-id="ba93c-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="ba93c-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ba93c-556">685.14</span><span class="sxs-lookup"><span data-stu-id="ba93c-556">685.14</span></span></td>
<td><span data-ttu-id="ba93c-557">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-558">CC004</span><span class="sxs-lookup"><span data-stu-id="ba93c-558">CC004</span></span></td>
<td><span data-ttu-id="ba93c-559">Emballage</span><span class="sxs-lookup"><span data-stu-id="ba93c-559">Packaging</span></span></td>
<td><span data-ttu-id="ba93c-560">10</span><span class="sxs-lookup"><span data-stu-id="ba93c-560">10</span></span></td>
<td><span data-ttu-id="ba93c-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="ba93c-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ba93c-562">124.57</span><span class="sxs-lookup"><span data-stu-id="ba93c-562">124.57</span></span></td>
<td><span data-ttu-id="ba93c-563">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-564">Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="ba93c-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-565">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-565">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-566">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ba93c-566">Magnitude</span></span></th>
<th><span data-ttu-id="ba93c-567">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ba93c-567">Allocation factor</span></span></th>
<th><span data-ttu-id="ba93c-568">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-568">Amount</span></span></th>
<th><span data-ttu-id="ba93c-569">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-570">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-570">CC003</span></span></td>
<td><span data-ttu-id="ba93c-571">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-571">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-572">65</span><span class="sxs-lookup"><span data-stu-id="ba93c-572">65</span></span></td>
<td><span data-ttu-id="ba93c-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="ba93c-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ba93c-574">438.75</span><span class="sxs-lookup"><span data-stu-id="ba93c-574">438.75</span></span></td>
<td><span data-ttu-id="ba93c-575">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-576">CC004</span><span class="sxs-lookup"><span data-stu-id="ba93c-576">CC004</span></span></td>
<td><span data-ttu-id="ba93c-577">Emballage</span><span class="sxs-lookup"><span data-stu-id="ba93c-577">Packaging</span></span></td>
<td><span data-ttu-id="ba93c-578">35</span><span class="sxs-lookup"><span data-stu-id="ba93c-578">35</span></span></td>
<td><span data-ttu-id="ba93c-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="ba93c-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ba93c-580">236.25</span><span class="sxs-lookup"><span data-stu-id="ba93c-580">236.25</span></span></td>
<td><span data-ttu-id="ba93c-581">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-582">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-582">CC003</span></span></td>
<td><span data-ttu-id="ba93c-583">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-583">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-584">65</span><span class="sxs-lookup"><span data-stu-id="ba93c-584">65</span></span></td>
<td><span data-ttu-id="ba93c-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="ba93c-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ba93c-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ba93c-586">5,297.69</span></span></td>
<td><span data-ttu-id="ba93c-587">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-588">CC004</span><span class="sxs-lookup"><span data-stu-id="ba93c-588">CC004</span></span></td>
<td><span data-ttu-id="ba93c-589">Emballage</span><span class="sxs-lookup"><span data-stu-id="ba93c-589">Packaging</span></span></td>
<td><span data-ttu-id="ba93c-590">35</span><span class="sxs-lookup"><span data-stu-id="ba93c-590">35</span></span></td>
<td><span data-ttu-id="ba93c-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="ba93c-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ba93c-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ba93c-592">2,852.60</span></span></td>
<td><span data-ttu-id="ba93c-593">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-594">Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="ba93c-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-595">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-595">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-596">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ba93c-596">Magnitude</span></span></th>
<th><span data-ttu-id="ba93c-597">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ba93c-597">Allocation factor</span></span></th>
<th><span data-ttu-id="ba93c-598">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-598">Amount</span></span></th>
<th><span data-ttu-id="ba93c-599">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-600">Prod 1</span></span></td>
<td><span data-ttu-id="ba93c-601">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-601">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-602">60</span><span class="sxs-lookup"><span data-stu-id="ba93c-602">60</span></span></td>
<td><span data-ttu-id="ba93c-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="ba93c-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ba93c-604">535.31</span><span class="sxs-lookup"><span data-stu-id="ba93c-604">535.31</span></span></td>
<td><span data-ttu-id="ba93c-605">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-606">Prod 2</span></span></td>
<td><span data-ttu-id="ba93c-607">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-607">Product 2</span></span></td>
<td><span data-ttu-id="ba93c-608">20</span><span class="sxs-lookup"><span data-stu-id="ba93c-608">20</span></span></td>
<td><span data-ttu-id="ba93c-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="ba93c-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ba93c-610">178.44</span><span class="sxs-lookup"><span data-stu-id="ba93c-610">178.44</span></span></td>
<td><span data-ttu-id="ba93c-611">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-612">Prod 1</span></span></td>
<td><span data-ttu-id="ba93c-613">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-613">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-614">60</span><span class="sxs-lookup"><span data-stu-id="ba93c-614">60</span></span></td>
<td><span data-ttu-id="ba93c-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="ba93c-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ba93c-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ba93c-616">4,487.12</span></span></td>
<td><span data-ttu-id="ba93c-617">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-618">Prod 2</span></span></td>
<td><span data-ttu-id="ba93c-619">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-619">Product 2</span></span></td>
<td><span data-ttu-id="ba93c-620">20</span><span class="sxs-lookup"><span data-stu-id="ba93c-620">20</span></span></td>
<td><span data-ttu-id="ba93c-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="ba93c-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ba93c-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ba93c-622">1,495.71</span></span></td>
<td><span data-ttu-id="ba93c-623">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba93c-624">Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="ba93c-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-625">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-625">Cost object</span></span></th>
<th><span data-ttu-id="ba93c-626">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ba93c-626">Magnitude</span></span></th>
<th><span data-ttu-id="ba93c-627">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ba93c-627">Allocation factor</span></span></th>
<th><span data-ttu-id="ba93c-628">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-628">Amount</span></span></th>
<th><span data-ttu-id="ba93c-629">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-630">Prod 1</span></span></td>
<td><span data-ttu-id="ba93c-631">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-631">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-632">80</span><span class="sxs-lookup"><span data-stu-id="ba93c-632">80</span></span></td>
<td><span data-ttu-id="ba93c-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="ba93c-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ba93c-634">241.05</span><span class="sxs-lookup"><span data-stu-id="ba93c-634">241.05</span></span></td>
<td><span data-ttu-id="ba93c-635">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-636">Prod 2</span></span></td>
<td><span data-ttu-id="ba93c-637">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-637">Product 2</span></span></td>
<td><span data-ttu-id="ba93c-638">15</span><span class="sxs-lookup"><span data-stu-id="ba93c-638">15</span></span></td>
<td><span data-ttu-id="ba93c-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="ba93c-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ba93c-640">45.20</span><span class="sxs-lookup"><span data-stu-id="ba93c-640">45.20</span></span></td>
<td><span data-ttu-id="ba93c-641">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-642">Prod 1</span></span></td>
<td><span data-ttu-id="ba93c-643">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-643">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-644">80</span><span class="sxs-lookup"><span data-stu-id="ba93c-644">80</span></span></td>
<td><span data-ttu-id="ba93c-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="ba93c-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ba93c-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ba93c-646">2,507.09</span></span></td>
<td><span data-ttu-id="ba93c-647">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-648">Prod 2</span></span></td>
<td><span data-ttu-id="ba93c-649">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-649">Product 2</span></span></td>
<td><span data-ttu-id="ba93c-650">15</span><span class="sxs-lookup"><span data-stu-id="ba93c-650">15</span></span></td>
<td><span data-ttu-id="ba93c-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="ba93c-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ba93c-652">470.08</span><span class="sxs-lookup"><span data-stu-id="ba93c-652">470.08</span></span></td>
<td><span data-ttu-id="ba93c-653">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ba93c-654">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="ba93c-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ba93c-655">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ba93c-655">Journal</span></span></th>
<th><span data-ttu-id="ba93c-656">Type de journal</span><span class="sxs-lookup"><span data-stu-id="ba93c-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ba93c-657">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="ba93c-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ba93c-658">Version</span><span class="sxs-lookup"><span data-stu-id="ba93c-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-659">00004</span><span class="sxs-lookup"><span data-stu-id="ba93c-659">00004</span></span></td>
<td><span data-ttu-id="ba93c-660">Journal de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="ba93c-661">Exercice</span><span class="sxs-lookup"><span data-stu-id="ba93c-661">Fiscal</span></span></td>
<td><span data-ttu-id="ba93c-662">2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-662">2017</span></span></td>
<td><span data-ttu-id="ba93c-663">Période 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-663">Period 1</span></span></td>
<td><span data-ttu-id="ba93c-664">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="ba93c-665">Lignes de journal</span><span class="sxs-lookup"><span data-stu-id="ba93c-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ba93c-666">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ba93c-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-667">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-668">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-668">Cost element</span></span></th>
<th><span data-ttu-id="ba93c-669">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-669">Cost behavior</span></span></th>
<th><span data-ttu-id="ba93c-670">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-671">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-672">CC001</span><span class="sxs-lookup"><span data-stu-id="ba93c-672">CC001</span></span></td>
<td><span data-ttu-id="ba93c-673">RH</span><span class="sxs-lookup"><span data-stu-id="ba93c-673">HR</span></span></td>
<td><span data-ttu-id="ba93c-674">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-674">10001</span></span></td>
<td><span data-ttu-id="ba93c-675">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-675">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-676">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-676">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-677">500,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-678">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-679">CC001</span><span class="sxs-lookup"><span data-stu-id="ba93c-679">CC001</span></span></td>
<td><span data-ttu-id="ba93c-680">RH</span><span class="sxs-lookup"><span data-stu-id="ba93c-680">HR</span></span></td>
<td><span data-ttu-id="ba93c-681">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-681">10001</span></span></td>
<td><span data-ttu-id="ba93c-682">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-682">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-683">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-683">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="ba93c-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-685">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-686">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-686">CC002</span></span></td>
<td><span data-ttu-id="ba93c-687">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-687">Finance</span></span></td>
<td><span data-ttu-id="ba93c-688">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-688">10001</span></span></td>
<td><span data-ttu-id="ba93c-689">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-689">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-690">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-690">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-691">675.00</span><span class="sxs-lookup"><span data-stu-id="ba93c-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-692">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-693">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-693">CC002</span></span></td>
<td><span data-ttu-id="ba93c-694">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-694">Finance</span></span></td>
<td><span data-ttu-id="ba93c-695">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-695">10001</span></span></td>
<td><span data-ttu-id="ba93c-696">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-696">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-697">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-697">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="ba93c-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-699">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-700">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-700">CC003</span></span></td>
<td><span data-ttu-id="ba93c-701">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-701">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-702">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-702">10001</span></span></td>
<td><span data-ttu-id="ba93c-703">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-703">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-704">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-704">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-705">713.75</span><span class="sxs-lookup"><span data-stu-id="ba93c-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-706">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-707">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-707">CC003</span></span></td>
<td><span data-ttu-id="ba93c-708">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-708">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-709">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-709">10001</span></span></td>
<td><span data-ttu-id="ba93c-710">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-710">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-711">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-711">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="ba93c-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-713">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-714">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-714">CC003</span></span></td>
<td><span data-ttu-id="ba93c-715">Emballage</span><span class="sxs-lookup"><span data-stu-id="ba93c-715">Packaging</span></span></td>
<td><span data-ttu-id="ba93c-716">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-716">10001</span></span></td>
<td><span data-ttu-id="ba93c-717">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-717">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-718">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-718">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-719">286.25</span><span class="sxs-lookup"><span data-stu-id="ba93c-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-720">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-721">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-721">CC003</span></span></td>
<td><span data-ttu-id="ba93c-722">Emballage</span><span class="sxs-lookup"><span data-stu-id="ba93c-722">Packaging</span></span></td>
<td><span data-ttu-id="ba93c-723">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-723">10001</span></span></td>
<td><span data-ttu-id="ba93c-724">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-724">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-725">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-725">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="ba93c-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-727">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-728">Prod 1</span></span></td>
<td><span data-ttu-id="ba93c-729">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-729">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-730">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-730">10001</span></span></td>
<td><span data-ttu-id="ba93c-731">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-731">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-732">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-732">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-733">776.36</span><span class="sxs-lookup"><span data-stu-id="ba93c-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-734">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-735">Prod 1</span></span></td>
<td><span data-ttu-id="ba93c-736">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-736">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-737">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-737">10001</span></span></td>
<td><span data-ttu-id="ba93c-738">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-738">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-739">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-739">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ba93c-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-741">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-742">Prod 2</span></span></td>
<td><span data-ttu-id="ba93c-743">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-743">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-744">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-744">10001</span></span></td>
<td><span data-ttu-id="ba93c-745">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-745">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-746">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-746">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-747">223.64</span><span class="sxs-lookup"><span data-stu-id="ba93c-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-748">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="ba93c-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-749">Prod 2</span></span></td>
<td><span data-ttu-id="ba93c-750">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-750">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-751">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-751">10001</span></span></td>
<td><span data-ttu-id="ba93c-752">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-752">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-753">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-753">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ba93c-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ba93c-755">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ba93c-756">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ba93c-757">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-757">Cost element</span></span></th>
<th><span data-ttu-id="ba93c-758">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ba93c-758">Cost behavior</span></span></th>
<th><span data-ttu-id="ba93c-759">Montant</span><span class="sxs-lookup"><span data-stu-id="ba93c-759">Amount</span></span></th>
<th><span data-ttu-id="ba93c-760">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ba93c-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ba93c-761">CC001</span><span class="sxs-lookup"><span data-stu-id="ba93c-761">CC001</span></span></td>
<td><span data-ttu-id="ba93c-762">RH</span><span class="sxs-lookup"><span data-stu-id="ba93c-762">HR</span></span></td>
<td><span data-ttu-id="ba93c-763">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-763">10001</span></span></td>
<td><span data-ttu-id="ba93c-764">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-764">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-765">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-765">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-766">-500.00</span></span></td>
<td><span data-ttu-id="ba93c-767">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-768">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-768">CC002</span></span></td>
<td><span data-ttu-id="ba93c-769">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-769">Finance</span></span></td>
<td><span data-ttu-id="ba93c-770">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-770">10001</span></span></td>
<td><span data-ttu-id="ba93c-771">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-771">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-772">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-772">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-773">175.00</span><span class="sxs-lookup"><span data-stu-id="ba93c-773">175.00</span></span></td>
<td><span data-ttu-id="ba93c-774">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-775">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-775">CC003</span></span></td>
<td><span data-ttu-id="ba93c-776">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-776">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-777">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-777">10001</span></span></td>
<td><span data-ttu-id="ba93c-778">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-778">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-779">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-779">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-780">275.00</span><span class="sxs-lookup"><span data-stu-id="ba93c-780">275.00</span></span></td>
<td><span data-ttu-id="ba93c-781">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-782">CC004</span><span class="sxs-lookup"><span data-stu-id="ba93c-782">CC004</span></span></td>
<td><span data-ttu-id="ba93c-783">Emballage</span><span class="sxs-lookup"><span data-stu-id="ba93c-783">Packaging</span></span></td>
<td><span data-ttu-id="ba93c-784">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-784">10001</span></span></td>
<td><span data-ttu-id="ba93c-785">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-785">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-786">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-786">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-787">50,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-787">50,00</span></span></td>
<td><span data-ttu-id="ba93c-788">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-789">CC001</span><span class="sxs-lookup"><span data-stu-id="ba93c-789">CC001</span></span></td>
<td><span data-ttu-id="ba93c-790">RH</span><span class="sxs-lookup"><span data-stu-id="ba93c-790">HR</span></span></td>
<td><span data-ttu-id="ba93c-791">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-791">10001</span></span></td>
<td><span data-ttu-id="ba93c-792">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-792">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-793">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-793">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="ba93c-794">-1,245.71</span></span></td>
<td><span data-ttu-id="ba93c-795">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-796">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-796">CC002</span></span></td>
<td><span data-ttu-id="ba93c-797">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-797">Finance</span></span></td>
<td><span data-ttu-id="ba93c-798">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-798">10001</span></span></td>
<td><span data-ttu-id="ba93c-799">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-799">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-800">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-800">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-801">436.00</span><span class="sxs-lookup"><span data-stu-id="ba93c-801">436.00</span></span></td>
<td><span data-ttu-id="ba93c-802">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-803">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-803">CC003</span></span></td>
<td><span data-ttu-id="ba93c-804">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-804">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-805">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-805">10001</span></span></td>
<td><span data-ttu-id="ba93c-806">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-806">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-807">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-807">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-808">685.14</span><span class="sxs-lookup"><span data-stu-id="ba93c-808">685.14</span></span></td>
<td><span data-ttu-id="ba93c-809">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-810">CC004</span><span class="sxs-lookup"><span data-stu-id="ba93c-810">CC004</span></span></td>
<td><span data-ttu-id="ba93c-811">Emballage</span><span class="sxs-lookup"><span data-stu-id="ba93c-811">Packaging</span></span></td>
<td><span data-ttu-id="ba93c-812">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-812">10001</span></span></td>
<td><span data-ttu-id="ba93c-813">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-813">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-814">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-814">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-815">124.57</span><span class="sxs-lookup"><span data-stu-id="ba93c-815">124.57</span></span></td>
<td><span data-ttu-id="ba93c-816">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-817">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-817">CC002</span></span></td>
<td><span data-ttu-id="ba93c-818">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-818">Finance</span></span></td>
<td><span data-ttu-id="ba93c-819">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-819">10001</span></span></td>
<td><span data-ttu-id="ba93c-820">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-820">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-821">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-821">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-822">-675.00</span></span></td>
<td><span data-ttu-id="ba93c-823">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-824">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-824">CC003</span></span></td>
<td><span data-ttu-id="ba93c-825">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-825">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-826">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-826">10001</span></span></td>
<td><span data-ttu-id="ba93c-827">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-827">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-828">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-828">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-829">438.75</span><span class="sxs-lookup"><span data-stu-id="ba93c-829">438.75</span></span></td>
<td><span data-ttu-id="ba93c-830">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-831">CC004</span><span class="sxs-lookup"><span data-stu-id="ba93c-831">CC004</span></span></td>
<td><span data-ttu-id="ba93c-832">Emballage</span><span class="sxs-lookup"><span data-stu-id="ba93c-832">Packaging</span></span></td>
<td><span data-ttu-id="ba93c-833">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-833">10001</span></span></td>
<td><span data-ttu-id="ba93c-834">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-834">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-835">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-835">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-836">236.25</span><span class="sxs-lookup"><span data-stu-id="ba93c-836">236.25</span></span></td>
<td><span data-ttu-id="ba93c-837">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-838">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-838">CC002</span></span></td>
<td><span data-ttu-id="ba93c-839">Finances</span><span class="sxs-lookup"><span data-stu-id="ba93c-839">Finance</span></span></td>
<td><span data-ttu-id="ba93c-840">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-840">10001</span></span></td>
<td><span data-ttu-id="ba93c-841">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-841">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-842">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-842">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="ba93c-843">-8,150.29</span></span></td>
<td><span data-ttu-id="ba93c-844">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-845">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-845">CC003</span></span></td>
<td><span data-ttu-id="ba93c-846">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-846">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-847">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-847">10001</span></span></td>
<td><span data-ttu-id="ba93c-848">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-848">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-849">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-849">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ba93c-850">5,297.69</span></span></td>
<td><span data-ttu-id="ba93c-851">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-852">CC004</span><span class="sxs-lookup"><span data-stu-id="ba93c-852">CC004</span></span></td>
<td><span data-ttu-id="ba93c-853">Emballage</span><span class="sxs-lookup"><span data-stu-id="ba93c-853">Packaging</span></span></td>
<td><span data-ttu-id="ba93c-854">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-854">10001</span></span></td>
<td><span data-ttu-id="ba93c-855">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-855">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-856">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-856">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ba93c-857">2,852.60</span></span></td>
<td><span data-ttu-id="ba93c-858">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-859">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-859">CC003</span></span></td>
<td><span data-ttu-id="ba93c-860">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-860">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-861">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-861">10001</span></span></td>
<td><span data-ttu-id="ba93c-862">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-862">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-863">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-863">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="ba93c-864">-713.75</span></span></td>
<td><span data-ttu-id="ba93c-865">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-866">Prod 1</span></span></td>
<td><span data-ttu-id="ba93c-867">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-867">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-868">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-868">10001</span></span></td>
<td><span data-ttu-id="ba93c-869">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-869">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-870">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-870">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-871">535.31</span><span class="sxs-lookup"><span data-stu-id="ba93c-871">535.31</span></span></td>
<td><span data-ttu-id="ba93c-872">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-873">Prod 2</span></span></td>
<td><span data-ttu-id="ba93c-874">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-874">Product 2</span></span></td>
<td><span data-ttu-id="ba93c-875">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-875">10001</span></span></td>
<td><span data-ttu-id="ba93c-876">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-876">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-877">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-877">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-878">178.44</span><span class="sxs-lookup"><span data-stu-id="ba93c-878">178.44</span></span></td>
<td><span data-ttu-id="ba93c-879">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-880">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-880">CC003</span></span></td>
<td><span data-ttu-id="ba93c-881">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-881">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-882">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-882">10001</span></span></td>
<td><span data-ttu-id="ba93c-883">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-883">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-884">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-884">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="ba93c-885">-5,982.83</span></span></td>
<td><span data-ttu-id="ba93c-886">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-887">Prod 1</span></span></td>
<td><span data-ttu-id="ba93c-888">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-888">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-889">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-889">10001</span></span></td>
<td><span data-ttu-id="ba93c-890">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-890">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-891">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-891">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ba93c-892">4,487.12</span></span></td>
<td><span data-ttu-id="ba93c-893">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-894">Prod 2</span></span></td>
<td><span data-ttu-id="ba93c-895">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-895">Product 2</span></span></td>
<td><span data-ttu-id="ba93c-896">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-896">10001</span></span></td>
<td><span data-ttu-id="ba93c-897">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-897">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-898">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-898">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ba93c-899">1,495.71</span></span></td>
<td><span data-ttu-id="ba93c-900">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-901">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-901">CC003</span></span></td>
<td><span data-ttu-id="ba93c-902">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-902">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-903">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-903">10001</span></span></td>
<td><span data-ttu-id="ba93c-904">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-904">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-905">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-905">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="ba93c-906">-286.25</span></span></td>
<td><span data-ttu-id="ba93c-907">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-908">Prod 1</span></span></td>
<td><span data-ttu-id="ba93c-909">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-909">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-910">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-910">10001</span></span></td>
<td><span data-ttu-id="ba93c-911">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-911">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-912">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-912">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-913">241.05</span><span class="sxs-lookup"><span data-stu-id="ba93c-913">241.05</span></span></td>
<td><span data-ttu-id="ba93c-914">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-915">Prod 2</span></span></td>
<td><span data-ttu-id="ba93c-916">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-916">Product 2</span></span></td>
<td><span data-ttu-id="ba93c-917">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-917">10001</span></span></td>
<td><span data-ttu-id="ba93c-918">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-918">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-919">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-919">Fixed cost</span></span></td>
<td><span data-ttu-id="ba93c-920">45.20</span><span class="sxs-lookup"><span data-stu-id="ba93c-920">45.20</span></span></td>
<td><span data-ttu-id="ba93c-921">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-922">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-922">CC003</span></span></td>
<td><span data-ttu-id="ba93c-923">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ba93c-923">Assembly</span></span></td>
<td><span data-ttu-id="ba93c-924">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-924">10001</span></span></td>
<td><span data-ttu-id="ba93c-925">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-925">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-926">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-926">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="ba93c-927">-2,977.17</span></span></td>
<td><span data-ttu-id="ba93c-928">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-929">Prod 1</span></span></td>
<td><span data-ttu-id="ba93c-930">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-930">Product 1</span></span></td>
<td><span data-ttu-id="ba93c-931">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-931">10001</span></span></td>
<td><span data-ttu-id="ba93c-932">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-932">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-933">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-933">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ba93c-934">2,507.09</span></span></td>
<td><span data-ttu-id="ba93c-935">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ba93c-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-936">Prod 2</span></span></td>
<td><span data-ttu-id="ba93c-937">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-937">Product 2</span></span></td>
<td><span data-ttu-id="ba93c-938">10001</span><span class="sxs-lookup"><span data-stu-id="ba93c-938">10001</span></span></td>
<td><span data-ttu-id="ba93c-939">Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-939">Electricity</span></span></td>
<td><span data-ttu-id="ba93c-940">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-940">Variable cost</span></span></td>
<td><span data-ttu-id="ba93c-941">470.08</span><span class="sxs-lookup"><span data-stu-id="ba93c-941">470.08</span></span></td>
<td><span data-ttu-id="ba93c-942">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ba93c-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="ba93c-943">Conclusion</span><span class="sxs-lookup"><span data-stu-id="ba93c-943">Conclusion</span></span>
<span data-ttu-id="ba93c-944">Dans la comptabilité financière, un coût de 10 000,00 pour l’électricité est imputé sur un ID de centre de coût fictif.</span><span class="sxs-lookup"><span data-stu-id="ba93c-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="ba93c-945">Par conséquent, les comptables sauront que ce coût doit être affecté.</span><span class="sxs-lookup"><span data-stu-id="ba93c-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="ba93c-946">Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l’organisation, selon les stratégies et les règles qui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="ba93c-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="ba93c-947">Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="ba93c-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="ba93c-948">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="ba93c-949">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ba93c-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="ba93c-950">Total</span><span class="sxs-lookup"><span data-stu-id="ba93c-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ba93c-951">CC099</span><span class="sxs-lookup"><span data-stu-id="ba93c-951">CC099</span></span></th>
<th><span data-ttu-id="ba93c-952">CC001</span><span class="sxs-lookup"><span data-stu-id="ba93c-952">CC001</span></span></th>
<th><span data-ttu-id="ba93c-953">CC002</span><span class="sxs-lookup"><span data-stu-id="ba93c-953">CC002</span></span></th>
<th><span data-ttu-id="ba93c-954">CC003</span><span class="sxs-lookup"><span data-stu-id="ba93c-954">CC003</span></span></th>
<th><span data-ttu-id="ba93c-955">CC004</span><span class="sxs-lookup"><span data-stu-id="ba93c-955">CC004</span></span></th>
<th><span data-ttu-id="ba93c-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-956">Proj 1</span></span></th>
<th><span data-ttu-id="ba93c-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-957">Proj 2</span></span></th>
<th><span data-ttu-id="ba93c-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ba93c-958">Prod 1</span></span></th>
<th><span data-ttu-id="ba93c-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ba93c-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="ba93c-960">10001 Électricité</span><span class="sxs-lookup"><span data-stu-id="ba93c-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ba93c-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ba93c-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ba93c-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ba93c-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="ba93c-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="ba93c-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="ba93c-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="ba93c-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ba93c-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="ba93c-970">Non classifié</span><span class="sxs-lookup"><span data-stu-id="ba93c-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-971">0,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-971">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="ba93c-972">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ba93c-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-973">0,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-974">0,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-975">0,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-976">0,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-977">0,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-978">776.36</span><span class="sxs-lookup"><span data-stu-id="ba93c-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-979">223.64</span><span class="sxs-lookup"><span data-stu-id="ba93c-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-980"><strong>1 000,00</strong></span><span class="sxs-lookup"><span data-stu-id="ba93c-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="ba93c-981">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ba93c-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-982">000</span><span class="sxs-lookup"><span data-stu-id="ba93c-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-983">0,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-984">0,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-985">0,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-986">0,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-987">30,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-988">10,00</span><span class="sxs-lookup"><span data-stu-id="ba93c-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ba93c-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ba93c-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ba93c-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ba93c-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ba93c-992">Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût.</span><span class="sxs-lookup"><span data-stu-id="ba93c-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="ba93c-993">Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="ba93c-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="ba93c-994">Autrement dit, les objets de coût de plus bas niveau supportent le coût.</span><span class="sxs-lookup"><span data-stu-id="ba93c-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="ba93c-995">Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts.</span><span class="sxs-lookup"><span data-stu-id="ba93c-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="ba93c-996">Pour plus d’informations, voir [Stratégie de repositionnement des coûts et calcul des frais généraux](cost-rollup.md)..</span><span class="sxs-lookup"><span data-stu-id="ba93c-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



