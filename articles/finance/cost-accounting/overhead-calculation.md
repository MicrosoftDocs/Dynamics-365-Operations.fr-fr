---
title: Calcul des frais généraux
description: Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.
author: AndersGirke
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 8dc312e66dc666ac6c23bac6b705ffc7893fd06b
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187995"
---
# <a name="overhead-calculation"></a><span data-ttu-id="e76e7-103">Calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="e76e7-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e76e7-104">Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="e76e7-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

## <a name="term-definition"></a><span data-ttu-id="e76e7-105">Définition des termes</span><span class="sxs-lookup"><span data-stu-id="e76e7-105">Term definition</span></span>

<span data-ttu-id="e76e7-106">Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique.</span><span class="sxs-lookup"><span data-stu-id="e76e7-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="e76e7-107">Les frais généraux permettent essentiellement l’identification des activités rémunératrices.</span><span class="sxs-lookup"><span data-stu-id="e76e7-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="e76e7-108">Voici quelques exemples de frais généraux :</span><span class="sxs-lookup"><span data-stu-id="e76e7-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="e76e7-109">Loyer</span><span class="sxs-lookup"><span data-stu-id="e76e7-109">Rent</span></span>
-   <span data-ttu-id="e76e7-110">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-110">Electricity</span></span>
-   <span data-ttu-id="e76e7-111">Salaires administratifs</span><span class="sxs-lookup"><span data-stu-id="e76e7-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="e76e7-112">Vue d’ensemble du calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="e76e7-112">Overhead calculation overview</span></span>
<span data-ttu-id="e76e7-113">Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l’ordre correct.</span><span class="sxs-lookup"><span data-stu-id="e76e7-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="e76e7-114">Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées.</span><span class="sxs-lookup"><span data-stu-id="e76e7-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="e76e7-115">Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions.</span><span class="sxs-lookup"><span data-stu-id="e76e7-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="e76e7-116">Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable.</span><span class="sxs-lookup"><span data-stu-id="e76e7-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="e76e7-117">Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="e76e7-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="e76e7-118">L’ID de version unique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e76e7-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="e76e7-119">Type de version</span><span class="sxs-lookup"><span data-stu-id="e76e7-119">Version type</span></span>
-   <span data-ttu-id="e76e7-120">Date et heure</span><span class="sxs-lookup"><span data-stu-id="e76e7-120">Date and time</span></span>
-   <span data-ttu-id="e76e7-121">Comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="e76e7-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="e76e7-122">Exercice</span><span class="sxs-lookup"><span data-stu-id="e76e7-122">Fiscal year</span></span>
-   <span data-ttu-id="e76e7-123">Période fiscale</span><span class="sxs-lookup"><span data-stu-id="e76e7-123">Fiscal period</span></span>

<span data-ttu-id="e76e7-124">Le calcul des frais généraux est effectué indépendamment de la version.</span><span class="sxs-lookup"><span data-stu-id="e76e7-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="e76e7-125">Par conséquent, vous pouvez calculer la version de budget avant la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="e76e7-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="e76e7-126">Le calcul des frais généraux comporte quatre étapes, comme le montre l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="e76e7-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="e76e7-127">Dans chaque étape, un en-tête de journal avec des entrées de journal est créé.</span><span class="sxs-lookup"><span data-stu-id="e76e7-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="e76e7-128">Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul.</span><span class="sxs-lookup"><span data-stu-id="e76e7-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="e76e7-129">Les stratégies et les règles s’appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie.</span><span class="sxs-lookup"><span data-stu-id="e76e7-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="e76e7-130">Par conséquent, vous disposez toujours d’une traçabilité complète.</span><span class="sxs-lookup"><span data-stu-id="e76e7-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="e76e7-131">[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="e76e7-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="e76e7-132">Calculer et affecter les frais généraux Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="e76e7-133">Dans la comptabilité financière, certaines coûts, tels que l’électricité, sont enregistrés comme montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="e76e7-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="e76e7-134">Par conséquent, l’analyse détaillée n’est pas fournie pour le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="e76e7-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="e76e7-135">Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l’organisation, les coûts doivent suivre les unités organisationnelles.</span><span class="sxs-lookup"><span data-stu-id="e76e7-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="e76e7-136">Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste.</span><span class="sxs-lookup"><span data-stu-id="e76e7-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="e76e7-137">Dans la comptabilité, le coût de l’électricité peut être validé comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="e76e7-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e76e7-138">Date comptable</span><span class="sxs-lookup"><span data-stu-id="e76e7-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-139">Centre de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-140">Compte principal</span><span class="sxs-lookup"><span data-stu-id="e76e7-140">Main account</span></span></th>
<th><span data-ttu-id="e76e7-141">Montant en devise comptable</span><span class="sxs-lookup"><span data-stu-id="e76e7-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-142">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="e76e7-143">CC099</span><span class="sxs-lookup"><span data-stu-id="e76e7-143">CC099</span></span></td>
<td><span data-ttu-id="e76e7-144">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="e76e7-144">Default cost center</span></span></td>
<td><span data-ttu-id="e76e7-145">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-145">10001</span></span></td>
<td><span data-ttu-id="e76e7-146">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-146">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="e76e7-148">Étape 1 : Traiter le calcul du comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="e76e7-149">Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="e76e7-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="e76e7-150">Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.</span><span class="sxs-lookup"><span data-stu-id="e76e7-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="e76e7-151">Définir la règle de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-151">Define the cost behavior rule</span></span>

<span data-ttu-id="e76e7-152">Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation.</span><span class="sxs-lookup"><span data-stu-id="e76e7-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="e76e7-153">Les factures d’électricité correspondent souvent à cette définition.</span><span class="sxs-lookup"><span data-stu-id="e76e7-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="e76e7-154">Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH).</span><span class="sxs-lookup"><span data-stu-id="e76e7-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="e76e7-155">Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :</span><span class="sxs-lookup"><span data-stu-id="e76e7-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="e76e7-156">Montant fixe 1 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="e76e7-157">0 &lt;= 1 000,00 = Fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="e76e7-158">1 000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="e76e7-159">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="e76e7-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e76e7-160">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="e76e7-160">Journal</span></span></th>
<th><span data-ttu-id="e76e7-161">Type de journal</span><span class="sxs-lookup"><span data-stu-id="e76e7-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="e76e7-162">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="e76e7-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="e76e7-163">Version</span><span class="sxs-lookup"><span data-stu-id="e76e7-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-164">00001</span><span class="sxs-lookup"><span data-stu-id="e76e7-164">00001</span></span></td>
<td><span data-ttu-id="e76e7-165">Journal de calcul de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="e76e7-166">Exercice</span><span class="sxs-lookup"><span data-stu-id="e76e7-166">Fiscal</span></span></td>
<td><span data-ttu-id="e76e7-167">2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-167">2017</span></span></td>
<td><span data-ttu-id="e76e7-168">Période 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-168">Period 1</span></span></td>
<td><span data-ttu-id="e76e7-169">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="e76e7-170">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="e76e7-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e76e7-171">Date comptable</span><span class="sxs-lookup"><span data-stu-id="e76e7-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-172">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-173">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-173">Cost element</span></span></th>
<th><span data-ttu-id="e76e7-174">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-174">Cost behavior</span></span></th>
<th><span data-ttu-id="e76e7-175">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-176">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="e76e7-177">CC099</span><span class="sxs-lookup"><span data-stu-id="e76e7-177">CC099</span></span></td>
<td><span data-ttu-id="e76e7-178">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="e76e7-178">Default cost center</span></span></td>
<td><span data-ttu-id="e76e7-179">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-179">10001</span></span></td>
<td><span data-ttu-id="e76e7-180">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-180">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-181">Non classifié</span><span class="sxs-lookup"><span data-stu-id="e76e7-181">Unclassified</span></span></td>
<td><span data-ttu-id="e76e7-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="e76e7-183">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-184">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-185">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-185">Cost element</span></span></th>
<th><span data-ttu-id="e76e7-186">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-186">Cost behavior</span></span></th>
<th><span data-ttu-id="e76e7-187">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-187">Amount</span></span></th>
<th><span data-ttu-id="e76e7-188">Date comptable</span><span class="sxs-lookup"><span data-stu-id="e76e7-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-189">CC099</span><span class="sxs-lookup"><span data-stu-id="e76e7-189">CC099</span></span></td>
<td><span data-ttu-id="e76e7-190">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="e76e7-190">Default cost center</span></span></td>
<td><span data-ttu-id="e76e7-191">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-191">10001</span></span></td>
<td><span data-ttu-id="e76e7-192">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-192">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-193">Non classifié</span><span class="sxs-lookup"><span data-stu-id="e76e7-193">Unclassified</span></span></td>
<td><span data-ttu-id="e76e7-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-194">10,000.00</span></span></td>
<td><span data-ttu-id="e76e7-195">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-196">CC099</span><span class="sxs-lookup"><span data-stu-id="e76e7-196">CC099</span></span></td>
<td><span data-ttu-id="e76e7-197">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="e76e7-197">Default cost center</span></span></td>
<td><span data-ttu-id="e76e7-198">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-198">10001</span></span></td>
<td><span data-ttu-id="e76e7-199">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-199">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-200">Non classifié</span><span class="sxs-lookup"><span data-stu-id="e76e7-200">Unclassified</span></span></td>
<td><span data-ttu-id="e76e7-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-201">-10,000.00</span></span></td>
<td><span data-ttu-id="e76e7-202">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-203">CC099</span><span class="sxs-lookup"><span data-stu-id="e76e7-203">CC099</span></span></td>
<td><span data-ttu-id="e76e7-204">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="e76e7-204">Default cost center</span></span></td>
<td><span data-ttu-id="e76e7-205">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-205">10001</span></span></td>
<td><span data-ttu-id="e76e7-206">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-206">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-207">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-207">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-208">1,000.00</span></span></td>
<td><span data-ttu-id="e76e7-209">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-210">CC099</span><span class="sxs-lookup"><span data-stu-id="e76e7-210">CC099</span></span></td>
<td><span data-ttu-id="e76e7-211">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="e76e7-211">Default cost center</span></span></td>
<td><span data-ttu-id="e76e7-212">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-212">10001</span></span></td>
<td><span data-ttu-id="e76e7-213">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-213">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-214">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-214">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-215">9 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-215">9,000.00</span></span></td>
<td><span data-ttu-id="e76e7-216">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-217">Pour plus d’informations, voir [Créer et affecter une stratégie de comportement de coûts à une unité de contrôle des coûts](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="e76e7-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="e76e7-218">Étape 2 : Traiter le calcul de distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="e76e7-219">La distribution des coûts est utilisée pour redistribuer le coût d’un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée.</span><span class="sxs-lookup"><span data-stu-id="e76e7-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="e76e7-220">La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l’élément de coût principal du coût d’origine.</span><span class="sxs-lookup"><span data-stu-id="e76e7-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="e76e7-221">Définir la règle de distribution de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-221">Define the cost distribution rule</span></span>

<span data-ttu-id="e76e7-222">Dans la comptabilité financière, les coûts d’électricité sont souvent enregistrés comme un montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="e76e7-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="e76e7-223">Dans le Contrôle de gestion, cette approche n’est pas assez détaillée.</span><span class="sxs-lookup"><span data-stu-id="e76e7-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="e76e7-224">Le coût variable doit être attribué aux différents objets de coûts sur une base juste.</span><span class="sxs-lookup"><span data-stu-id="e76e7-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="e76e7-225">La base de répartition la plus logique est la consommation de l’électricité (KWH).</span><span class="sxs-lookup"><span data-stu-id="e76e7-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="e76e7-226">Un membre de dimension statistique nommé Électricité est créé, et la consommation d’électricité est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="e76e7-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="e76e7-227">Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="e76e7-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-228">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-228">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="e76e7-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-230">CC001</span><span class="sxs-lookup"><span data-stu-id="e76e7-230">CC001</span></span></td>
<td><span data-ttu-id="e76e7-231">RH</span><span class="sxs-lookup"><span data-stu-id="e76e7-231">HR</span></span></td>
<td><span data-ttu-id="e76e7-232">1 000</span><span class="sxs-lookup"><span data-stu-id="e76e7-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-233">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-233">CC002</span></span></td>
<td><span data-ttu-id="e76e7-234">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-234">Finance</span></span></td>
<td><span data-ttu-id="e76e7-235">6 000</span><span class="sxs-lookup"><span data-stu-id="e76e7-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-236">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-236">CC003</span></span></td>
<td><span data-ttu-id="e76e7-237">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-237">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-238">0</span><span class="sxs-lookup"><span data-stu-id="e76e7-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-239">Le tableau suivant illustre le résultat lorsque la consommation d’électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="e76e7-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-240">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-240">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-241">Ampleur</span><span class="sxs-lookup"><span data-stu-id="e76e7-241">Magnitude</span></span></th>
<th><span data-ttu-id="e76e7-242">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="e76e7-242">Allocation factor</span></span></th>
<th><span data-ttu-id="e76e7-243">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-244">CC001</span><span class="sxs-lookup"><span data-stu-id="e76e7-244">CC001</span></span></td>
<td><span data-ttu-id="e76e7-245">RH</span><span class="sxs-lookup"><span data-stu-id="e76e7-245">HR</span></span></td>
<td><span data-ttu-id="e76e7-246">1 000</span><span class="sxs-lookup"><span data-stu-id="e76e7-246">1,000</span></span></td>
<td><span data-ttu-id="e76e7-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="e76e7-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="e76e7-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-249">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-249">CC002</span></span></td>
<td><span data-ttu-id="e76e7-250">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-250">Finance</span></span></td>
<td><span data-ttu-id="e76e7-251">6 000</span><span class="sxs-lookup"><span data-stu-id="e76e7-251">6,000</span></span></td>
<td><span data-ttu-id="e76e7-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="e76e7-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="e76e7-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-254">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-254">CC003</span></span></td>
<td><span data-ttu-id="e76e7-255">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-255">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-256">0</span><span class="sxs-lookup"><span data-stu-id="e76e7-256">0</span></span></td>
<td><span data-ttu-id="e76e7-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="e76e7-258">0,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-259">Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l’électricité.</span><span class="sxs-lookup"><span data-stu-id="e76e7-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="e76e7-260">Vous pouvez obtenir ce résultat à l’aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d’électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="e76e7-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-261">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-261">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-262">Formule</span><span class="sxs-lookup"><span data-stu-id="e76e7-262">Formula</span></span></th>
<th><span data-ttu-id="e76e7-263">Ampleur</span><span class="sxs-lookup"><span data-stu-id="e76e7-263">Magnitude</span></span></th>
<th><span data-ttu-id="e76e7-264">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="e76e7-264">Allocation factor</span></span></th>
<th><span data-ttu-id="e76e7-265">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-266">CC001</span><span class="sxs-lookup"><span data-stu-id="e76e7-266">CC001</span></span></td>
<td><span data-ttu-id="e76e7-267">RH</span><span class="sxs-lookup"><span data-stu-id="e76e7-267">HR</span></span></td>
<td><span data-ttu-id="e76e7-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="e76e7-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="e76e7-269">1</span><span class="sxs-lookup"><span data-stu-id="e76e7-269">1</span></span></td>
<td><span data-ttu-id="e76e7-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="e76e7-271">500,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-272">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-272">CC002</span></span></td>
<td><span data-ttu-id="e76e7-273">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-273">Finance</span></span></td>
<td><span data-ttu-id="e76e7-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="e76e7-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="e76e7-275">1</span><span class="sxs-lookup"><span data-stu-id="e76e7-275">1</span></span></td>
<td><span data-ttu-id="e76e7-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="e76e7-277">500,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-278">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-278">CC003</span></span></td>
<td><span data-ttu-id="e76e7-279">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-279">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="e76e7-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="e76e7-281">0</span><span class="sxs-lookup"><span data-stu-id="e76e7-281">0</span></span></td>
<td><span data-ttu-id="e76e7-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="e76e7-283">0,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="e76e7-284">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="e76e7-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e76e7-285">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="e76e7-285">Journal</span></span></th>
<th><span data-ttu-id="e76e7-286">Type de journal</span><span class="sxs-lookup"><span data-stu-id="e76e7-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="e76e7-287">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="e76e7-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="e76e7-288">Version</span><span class="sxs-lookup"><span data-stu-id="e76e7-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-289">00002</span><span class="sxs-lookup"><span data-stu-id="e76e7-289">00002</span></span></td>
<td><span data-ttu-id="e76e7-290">Journal de calcul de la distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="e76e7-291">Exercice</span><span class="sxs-lookup"><span data-stu-id="e76e7-291">Fiscal</span></span></td>
<td><span data-ttu-id="e76e7-292">2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-292">2017</span></span></td>
<td><span data-ttu-id="e76e7-293">Période 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-293">Period 1</span></span></td>
<td><span data-ttu-id="e76e7-294">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="e76e7-295">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="e76e7-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e76e7-296">Date comptable</span><span class="sxs-lookup"><span data-stu-id="e76e7-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-297">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-298">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-298">Cost element</span></span></th>
<th><span data-ttu-id="e76e7-299">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-299">Cost behavior</span></span></th>
<th><span data-ttu-id="e76e7-300">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-301">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-302">CC099</span><span class="sxs-lookup"><span data-stu-id="e76e7-302">CC099</span></span></td>
<td><span data-ttu-id="e76e7-303">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="e76e7-303">Default cost center</span></span></td>
<td><span data-ttu-id="e76e7-304">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-304">10001</span></span></td>
<td><span data-ttu-id="e76e7-305">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-305">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-306">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-306">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-308">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-309">CC099</span><span class="sxs-lookup"><span data-stu-id="e76e7-309">CC099</span></span></td>
<td><span data-ttu-id="e76e7-310">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="e76e7-310">Default cost center</span></span></td>
<td><span data-ttu-id="e76e7-311">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-311">10001</span></span></td>
<td><span data-ttu-id="e76e7-312">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-312">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-313">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-313">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-314">9 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="e76e7-315">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-316">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-317">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-317">Cost element</span></span></th>
<th><span data-ttu-id="e76e7-318">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-318">Cost behavior</span></span></th>
<th><span data-ttu-id="e76e7-319">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-319">Amount</span></span></th>
<th><span data-ttu-id="e76e7-320">Date comptable</span><span class="sxs-lookup"><span data-stu-id="e76e7-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-321">CC099</span><span class="sxs-lookup"><span data-stu-id="e76e7-321">CC099</span></span></td>
<td><span data-ttu-id="e76e7-322">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="e76e7-322">Default cost center</span></span></td>
<td><span data-ttu-id="e76e7-323">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-323">10001</span></span></td>
<td><span data-ttu-id="e76e7-324">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-324">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-325">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-325">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-326">-1,000.00</span></span></td>
<td><span data-ttu-id="e76e7-327">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-328">CC001</span><span class="sxs-lookup"><span data-stu-id="e76e7-328">CC001</span></span></td>
<td><span data-ttu-id="e76e7-329">RH</span><span class="sxs-lookup"><span data-stu-id="e76e7-329">HR</span></span></td>
<td><span data-ttu-id="e76e7-330">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-330">10001</span></span></td>
<td><span data-ttu-id="e76e7-331">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-331">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-332">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-332">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-333">500,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-333">500.00</span></span></td>
<td><span data-ttu-id="e76e7-334">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-335">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-335">CC002</span></span></td>
<td><span data-ttu-id="e76e7-336">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-336">Finance</span></span></td>
<td><span data-ttu-id="e76e7-337">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-337">10001</span></span></td>
<td><span data-ttu-id="e76e7-338">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-338">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-339">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-339">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-340">500,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-340">500.00</span></span></td>
<td><span data-ttu-id="e76e7-341">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-342">CC099</span><span class="sxs-lookup"><span data-stu-id="e76e7-342">CC099</span></span></td>
<td><span data-ttu-id="e76e7-343">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="e76e7-343">Default cost center</span></span></td>
<td><span data-ttu-id="e76e7-344">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-344">10001</span></span></td>
<td><span data-ttu-id="e76e7-345">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-345">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-346">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-346">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-347">-9,000.00</span></span></td>
<td><span data-ttu-id="e76e7-348">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-349">CC001</span><span class="sxs-lookup"><span data-stu-id="e76e7-349">CC001</span></span></td>
<td><span data-ttu-id="e76e7-350">RH</span><span class="sxs-lookup"><span data-stu-id="e76e7-350">HR</span></span></td>
<td><span data-ttu-id="e76e7-351">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-351">10001</span></span></td>
<td><span data-ttu-id="e76e7-352">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-352">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-353">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-353">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="e76e7-354">1,285.71</span></span></td>
<td><span data-ttu-id="e76e7-355">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-356">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-356">CC002</span></span></td>
<td><span data-ttu-id="e76e7-357">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-357">Finance</span></span></td>
<td><span data-ttu-id="e76e7-358">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-358">10001</span></span></td>
<td><span data-ttu-id="e76e7-359">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-359">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-360">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-360">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="e76e7-361">7,714.29</span></span></td>
<td><span data-ttu-id="e76e7-362">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-363">Pour plus d’informations, voir [Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="e76e7-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="e76e7-364">Étape 3 : Traitement du calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="e76e7-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="e76e7-365">Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût.</span><span class="sxs-lookup"><span data-stu-id="e76e7-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="e76e7-366">Les frais sont basés sur un taux de coût prédéterminé et l’ampleur de la base d’affectation de répartition.</span><span class="sxs-lookup"><span data-stu-id="e76e7-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="e76e7-367">Définition du taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="e76e7-367">Define the overhead rate</span></span>

<span data-ttu-id="e76e7-368">L’objet de coût CC001 HR contribue à un ensemble de projets internes.</span><span class="sxs-lookup"><span data-stu-id="e76e7-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="e76e7-369">Un membre de dimension statistique nommé Projets HR est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="e76e7-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-370">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-370">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-371">Heures</span><span class="sxs-lookup"><span data-stu-id="e76e7-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-372">Proj 1</span></span></td>
<td><span data-ttu-id="e76e7-373">Projet 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-373">Project 1</span></span></td>
<td><span data-ttu-id="e76e7-374">3</span><span class="sxs-lookup"><span data-stu-id="e76e7-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-375">Proj 2</span></span></td>
<td><span data-ttu-id="e76e7-376">Projet 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-376">Project 2</span></span></td>
<td><span data-ttu-id="e76e7-377">1</span><span class="sxs-lookup"><span data-stu-id="e76e7-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-378">Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.</span><span class="sxs-lookup"><span data-stu-id="e76e7-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-379">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-379">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-380">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-380">Cost element</span></span></th>
<th><span data-ttu-id="e76e7-381">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-381">Cost behavior</span></span></th>
<th><span data-ttu-id="e76e7-382">Unités</span><span class="sxs-lookup"><span data-stu-id="e76e7-382">Units</span></span></th>
<th><span data-ttu-id="e76e7-383">Taux</span><span class="sxs-lookup"><span data-stu-id="e76e7-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-384">CC001</span><span class="sxs-lookup"><span data-stu-id="e76e7-384">CC001</span></span></td>
<td><span data-ttu-id="e76e7-385">RH</span><span class="sxs-lookup"><span data-stu-id="e76e7-385">HR</span></span></td>
<td><span data-ttu-id="e76e7-386">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-386">10001</span></span></td>
<td><span data-ttu-id="e76e7-387">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-387">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-388">1</span><span class="sxs-lookup"><span data-stu-id="e76e7-388">1</span></span></td>
<td><span data-ttu-id="e76e7-389">10</span><span class="sxs-lookup"><span data-stu-id="e76e7-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-390">Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="e76e7-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-391">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-391">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-392">Ampleur</span><span class="sxs-lookup"><span data-stu-id="e76e7-392">Magnitude</span></span></th>
<th><span data-ttu-id="e76e7-393">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-393">Cost element</span></span></th>
<th><span data-ttu-id="e76e7-394">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="e76e7-394">Allocation factor</span></span></th>
<th><span data-ttu-id="e76e7-395">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-396">Proj 1</span></span></td>
<td><span data-ttu-id="e76e7-397">Projet 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-397">Project 1</span></span></td>
<td><span data-ttu-id="e76e7-398">3</span><span class="sxs-lookup"><span data-stu-id="e76e7-398">3</span></span></td>
<td><span data-ttu-id="e76e7-399">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-399">10001</span></span></td>
<td><span data-ttu-id="e76e7-400">(3 ÷ 1) × 10m00</span><span class="sxs-lookup"><span data-stu-id="e76e7-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="e76e7-401">30,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-402">Proj 2</span></span></td>
<td><span data-ttu-id="e76e7-403">Projet 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-403">Project 2</span></span></td>
<td><span data-ttu-id="e76e7-404">1</span><span class="sxs-lookup"><span data-stu-id="e76e7-404">1</span></span></td>
<td><span data-ttu-id="e76e7-405">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-405">10001</span></span></td>
<td><span data-ttu-id="e76e7-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="e76e7-407">10,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="e76e7-408">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="e76e7-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e76e7-409">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="e76e7-409">Journal</span></span></th>
<th><span data-ttu-id="e76e7-410">Type de journal</span><span class="sxs-lookup"><span data-stu-id="e76e7-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="e76e7-411">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="e76e7-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="e76e7-412">Version</span><span class="sxs-lookup"><span data-stu-id="e76e7-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-413">00003</span><span class="sxs-lookup"><span data-stu-id="e76e7-413">00003</span></span></td>
<td><span data-ttu-id="e76e7-414">Journal de calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="e76e7-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="e76e7-415">Exercice</span><span class="sxs-lookup"><span data-stu-id="e76e7-415">Fiscal</span></span></td>
<td><span data-ttu-id="e76e7-416">2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-416">2017</span></span></td>
<td><span data-ttu-id="e76e7-417">Période 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-417">Period 1</span></span></td>
<td><span data-ttu-id="e76e7-418">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="e76e7-419">Entrées du journal (pour le calcul du taux de frais généraux)</span><span class="sxs-lookup"><span data-stu-id="e76e7-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e76e7-420">Date comptable</span><span class="sxs-lookup"><span data-stu-id="e76e7-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-421">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-421">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-422">Ampleur</span><span class="sxs-lookup"><span data-stu-id="e76e7-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-423">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-424">Proj 1</span></span></td>
<td><span data-ttu-id="e76e7-425">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="e76e7-426">3,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-427">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-428">Proj 2</span></span></td>
<td><span data-ttu-id="e76e7-429">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="e76e7-430">1,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="e76e7-431">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-432">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-433">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-433">Cost element</span></span></th>
<th><span data-ttu-id="e76e7-434">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-434">Cost behavior</span></span></th>
<th><span data-ttu-id="e76e7-435">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-435">Amount</span></span></th>
<th><span data-ttu-id="e76e7-436">Date comptable</span><span class="sxs-lookup"><span data-stu-id="e76e7-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="e76e7-437">CC0001</span></span></td>
<td><span data-ttu-id="e76e7-438">RH</span><span class="sxs-lookup"><span data-stu-id="e76e7-438">HR</span></span></td>
<td><span data-ttu-id="e76e7-439">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-439">10001</span></span></td>
<td><span data-ttu-id="e76e7-440">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-440">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-441">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-441">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-442">-30.00</span></span></td>
<td><span data-ttu-id="e76e7-443">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-444">Proj 1</span></span></td>
<td><span data-ttu-id="e76e7-445">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="e76e7-446">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-446">10001</span></span></td>
<td><span data-ttu-id="e76e7-447">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-447">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-448">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-448">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-449">30,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-449">30.00</span></span></td>
<td><span data-ttu-id="e76e7-450">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-451">CC001</span><span class="sxs-lookup"><span data-stu-id="e76e7-451">CC001</span></span></td>
<td><span data-ttu-id="e76e7-452">RH</span><span class="sxs-lookup"><span data-stu-id="e76e7-452">HR</span></span></td>
<td><span data-ttu-id="e76e7-453">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-453">10001</span></span></td>
<td><span data-ttu-id="e76e7-454">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-454">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-455">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-455">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-456">-10.00</span></span></td>
<td><span data-ttu-id="e76e7-457">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-458">Proj 2</span></span></td>
<td><span data-ttu-id="e76e7-459">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="e76e7-460">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-460">10001</span></span></td>
<td><span data-ttu-id="e76e7-461">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-461">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-462">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-462">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-463">10.00</span><span class="sxs-lookup"><span data-stu-id="e76e7-463">10.00</span></span></td>
<td><span data-ttu-id="e76e7-464">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-465">Pour plus d’informations, voir [Exécuter le calcul des frais généraux](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="e76e7-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="e76e7-466">Étape 4 : Traiter le calcul de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="e76e7-467">La répartition est utilisée pour affecter le solde d’un objet de coût à d’autres objets de coût en appliquant une base de répartition.</span><span class="sxs-lookup"><span data-stu-id="e76e7-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="e76e7-468">Finance prend en charge la méthode de répartition réciproque.</span><span class="sxs-lookup"><span data-stu-id="e76e7-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="e76e7-469">Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés.</span><span class="sxs-lookup"><span data-stu-id="e76e7-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="e76e7-470">Le système détermine automatiquement l’ordre correct selon lequel exécuter les répartitions.</span><span class="sxs-lookup"><span data-stu-id="e76e7-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="e76e7-471">Le solde d’un objet de coût est réparti par une seule base de répartition.</span><span class="sxs-lookup"><span data-stu-id="e76e7-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="e76e7-472">Les répartitions entre plusieurs dimensions d’objets de coût et leurs membres respectifs sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="e76e7-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="e76e7-473">L’ordre de répartition est contrôlé par l’unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="e76e7-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="e76e7-474">[![Méthode réciproque](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="e76e7-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="e76e7-475">Définir la répartition de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-475">Define the cost allocation</span></span>

<span data-ttu-id="e76e7-476">Voici un exemple simple expliquant comment suivre le flux du coût.</span><span class="sxs-lookup"><span data-stu-id="e76e7-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="e76e7-477">L’objet de coût CC001 HR contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="e76e7-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="e76e7-478">Un membre de dimension statistique nommé Services HR est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="e76e7-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-479">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-479">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-480">Services HR</span><span class="sxs-lookup"><span data-stu-id="e76e7-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-481">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-481">CC002</span></span></td>
<td><span data-ttu-id="e76e7-482">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-482">Finance</span></span></td>
<td><span data-ttu-id="e76e7-483">35</span><span class="sxs-lookup"><span data-stu-id="e76e7-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-484">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-484">CC003</span></span></td>
<td><span data-ttu-id="e76e7-485">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-485">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-486">55</span><span class="sxs-lookup"><span data-stu-id="e76e7-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-487">CC004</span><span class="sxs-lookup"><span data-stu-id="e76e7-487">CC004</span></span></td>
<td><span data-ttu-id="e76e7-488">Emballage</span><span class="sxs-lookup"><span data-stu-id="e76e7-488">Packaging</span></span></td>
<td><span data-ttu-id="e76e7-489">10</span><span class="sxs-lookup"><span data-stu-id="e76e7-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-490">L’objet de coût CC002 Finance contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="e76e7-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="e76e7-491">Un membre de dimension statistique nommé Services Finance est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="e76e7-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-492">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-492">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-493">Services Finance</span><span class="sxs-lookup"><span data-stu-id="e76e7-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-494">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-494">CC003</span></span></td>
<td><span data-ttu-id="e76e7-495">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-495">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-496">65</span><span class="sxs-lookup"><span data-stu-id="e76e7-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-497">CC004</span><span class="sxs-lookup"><span data-stu-id="e76e7-497">CC004</span></span></td>
<td><span data-ttu-id="e76e7-498">Emballage</span><span class="sxs-lookup"><span data-stu-id="e76e7-498">Packaging</span></span></td>
<td><span data-ttu-id="e76e7-499">35</span><span class="sxs-lookup"><span data-stu-id="e76e7-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-500">L’objet de coût CC003 Assemblage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="e76e7-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="e76e7-501">Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="e76e7-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-502">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-502">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-503">Services Assemblage (heures)</span><span class="sxs-lookup"><span data-stu-id="e76e7-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-504">Prod 1</span></span></td>
<td><span data-ttu-id="e76e7-505">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-505">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-506">60</span><span class="sxs-lookup"><span data-stu-id="e76e7-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-507">Prod 2</span></span></td>
<td><span data-ttu-id="e76e7-508">Produit 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-508">Product 2</span></span></td>
<td><span data-ttu-id="e76e7-509">20</span><span class="sxs-lookup"><span data-stu-id="e76e7-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-510">L’objet de coût CC004 Emballage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="e76e7-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="e76e7-511">Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="e76e7-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-512">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-512">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-513">Services Emballage (heures)</span><span class="sxs-lookup"><span data-stu-id="e76e7-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-514">Prod 1</span></span></td>
<td><span data-ttu-id="e76e7-515">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-515">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-516">80</span><span class="sxs-lookup"><span data-stu-id="e76e7-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-517">Prod 2</span></span></td>
<td><span data-ttu-id="e76e7-518">Produit 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-518">Product 2</span></span></td>
<td><span data-ttu-id="e76e7-519">15</span><span class="sxs-lookup"><span data-stu-id="e76e7-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="e76e7-520">Les mesures statistiques telles que les heures de production qu’un produit consomme peuvent être dérivées des données sources.</span><span class="sxs-lookup"><span data-stu-id="e76e7-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="e76e7-521">Pour plus d’informations, voir [Modèle de fournisseur de mesures statistiques](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="e76e7-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="e76e7-522">Le tableau suivant présente le résultat lorsque les services RH sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="e76e7-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-523">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-523">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-524">Ampleur</span><span class="sxs-lookup"><span data-stu-id="e76e7-524">Magnitude</span></span></th>
<th><span data-ttu-id="e76e7-525">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="e76e7-525">Allocation factor</span></span></th>
<th><span data-ttu-id="e76e7-526">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-526">Amount</span></span></th>
<th><span data-ttu-id="e76e7-527">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-528">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-528">CC002</span></span></td>
<td><span data-ttu-id="e76e7-529">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-529">Finance</span></span></td>
<td><span data-ttu-id="e76e7-530">35</span><span class="sxs-lookup"><span data-stu-id="e76e7-530">35</span></span></td>
<td><span data-ttu-id="e76e7-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="e76e7-532">175.00</span><span class="sxs-lookup"><span data-stu-id="e76e7-532">175.00</span></span></td>
<td><span data-ttu-id="e76e7-533">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-534">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-534">CC003</span></span></td>
<td><span data-ttu-id="e76e7-535">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-535">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-536">55</span><span class="sxs-lookup"><span data-stu-id="e76e7-536">55</span></span></td>
<td><span data-ttu-id="e76e7-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="e76e7-538">275.00</span><span class="sxs-lookup"><span data-stu-id="e76e7-538">275.00</span></span></td>
<td><span data-ttu-id="e76e7-539">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-540">CC004</span><span class="sxs-lookup"><span data-stu-id="e76e7-540">CC004</span></span></td>
<td><span data-ttu-id="e76e7-541">Emballage</span><span class="sxs-lookup"><span data-stu-id="e76e7-541">Packaging</span></span></td>
<td><span data-ttu-id="e76e7-542">10</span><span class="sxs-lookup"><span data-stu-id="e76e7-542">10</span></span></td>
<td><span data-ttu-id="e76e7-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="e76e7-544">50,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-544">50.00</span></span></td>
<td><span data-ttu-id="e76e7-545">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-546">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-546">CC002</span></span></td>
<td><span data-ttu-id="e76e7-547">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-547">Finance</span></span></td>
<td><span data-ttu-id="e76e7-548">35</span><span class="sxs-lookup"><span data-stu-id="e76e7-548">35</span></span></td>
<td><span data-ttu-id="e76e7-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="e76e7-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="e76e7-550">436.00</span><span class="sxs-lookup"><span data-stu-id="e76e7-550">436.00</span></span></td>
<td><span data-ttu-id="e76e7-551">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-552">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-552">CC003</span></span></td>
<td><span data-ttu-id="e76e7-553">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-553">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-554">55</span><span class="sxs-lookup"><span data-stu-id="e76e7-554">55</span></span></td>
<td><span data-ttu-id="e76e7-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="e76e7-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="e76e7-556">685.14</span><span class="sxs-lookup"><span data-stu-id="e76e7-556">685.14</span></span></td>
<td><span data-ttu-id="e76e7-557">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-558">CC004</span><span class="sxs-lookup"><span data-stu-id="e76e7-558">CC004</span></span></td>
<td><span data-ttu-id="e76e7-559">Emballage</span><span class="sxs-lookup"><span data-stu-id="e76e7-559">Packaging</span></span></td>
<td><span data-ttu-id="e76e7-560">10</span><span class="sxs-lookup"><span data-stu-id="e76e7-560">10</span></span></td>
<td><span data-ttu-id="e76e7-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="e76e7-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="e76e7-562">124.57</span><span class="sxs-lookup"><span data-stu-id="e76e7-562">124.57</span></span></td>
<td><span data-ttu-id="e76e7-563">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-564">Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="e76e7-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-565">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-565">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-566">Ampleur</span><span class="sxs-lookup"><span data-stu-id="e76e7-566">Magnitude</span></span></th>
<th><span data-ttu-id="e76e7-567">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="e76e7-567">Allocation factor</span></span></th>
<th><span data-ttu-id="e76e7-568">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-568">Amount</span></span></th>
<th><span data-ttu-id="e76e7-569">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-570">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-570">CC003</span></span></td>
<td><span data-ttu-id="e76e7-571">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-571">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-572">65</span><span class="sxs-lookup"><span data-stu-id="e76e7-572">65</span></span></td>
<td><span data-ttu-id="e76e7-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="e76e7-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="e76e7-574">438.75</span><span class="sxs-lookup"><span data-stu-id="e76e7-574">438.75</span></span></td>
<td><span data-ttu-id="e76e7-575">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-576">CC004</span><span class="sxs-lookup"><span data-stu-id="e76e7-576">CC004</span></span></td>
<td><span data-ttu-id="e76e7-577">Emballage</span><span class="sxs-lookup"><span data-stu-id="e76e7-577">Packaging</span></span></td>
<td><span data-ttu-id="e76e7-578">35</span><span class="sxs-lookup"><span data-stu-id="e76e7-578">35</span></span></td>
<td><span data-ttu-id="e76e7-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="e76e7-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="e76e7-580">236.25</span><span class="sxs-lookup"><span data-stu-id="e76e7-580">236.25</span></span></td>
<td><span data-ttu-id="e76e7-581">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-582">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-582">CC003</span></span></td>
<td><span data-ttu-id="e76e7-583">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-583">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-584">65</span><span class="sxs-lookup"><span data-stu-id="e76e7-584">65</span></span></td>
<td><span data-ttu-id="e76e7-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="e76e7-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="e76e7-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="e76e7-586">5,297.69</span></span></td>
<td><span data-ttu-id="e76e7-587">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-588">CC004</span><span class="sxs-lookup"><span data-stu-id="e76e7-588">CC004</span></span></td>
<td><span data-ttu-id="e76e7-589">Emballage</span><span class="sxs-lookup"><span data-stu-id="e76e7-589">Packaging</span></span></td>
<td><span data-ttu-id="e76e7-590">35</span><span class="sxs-lookup"><span data-stu-id="e76e7-590">35</span></span></td>
<td><span data-ttu-id="e76e7-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="e76e7-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="e76e7-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="e76e7-592">2,852.60</span></span></td>
<td><span data-ttu-id="e76e7-593">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-594">Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="e76e7-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-595">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-595">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-596">Ampleur</span><span class="sxs-lookup"><span data-stu-id="e76e7-596">Magnitude</span></span></th>
<th><span data-ttu-id="e76e7-597">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="e76e7-597">Allocation factor</span></span></th>
<th><span data-ttu-id="e76e7-598">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-598">Amount</span></span></th>
<th><span data-ttu-id="e76e7-599">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-600">Prod 1</span></span></td>
<td><span data-ttu-id="e76e7-601">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-601">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-602">60</span><span class="sxs-lookup"><span data-stu-id="e76e7-602">60</span></span></td>
<td><span data-ttu-id="e76e7-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="e76e7-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="e76e7-604">535.31</span><span class="sxs-lookup"><span data-stu-id="e76e7-604">535.31</span></span></td>
<td><span data-ttu-id="e76e7-605">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-606">Prod 2</span></span></td>
<td><span data-ttu-id="e76e7-607">Produit 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-607">Product 2</span></span></td>
<td><span data-ttu-id="e76e7-608">20</span><span class="sxs-lookup"><span data-stu-id="e76e7-608">20</span></span></td>
<td><span data-ttu-id="e76e7-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="e76e7-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="e76e7-610">178.44</span><span class="sxs-lookup"><span data-stu-id="e76e7-610">178.44</span></span></td>
<td><span data-ttu-id="e76e7-611">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-612">Prod 1</span></span></td>
<td><span data-ttu-id="e76e7-613">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-613">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-614">60</span><span class="sxs-lookup"><span data-stu-id="e76e7-614">60</span></span></td>
<td><span data-ttu-id="e76e7-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="e76e7-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="e76e7-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="e76e7-616">4,487.12</span></span></td>
<td><span data-ttu-id="e76e7-617">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-618">Prod 2</span></span></td>
<td><span data-ttu-id="e76e7-619">Produit 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-619">Product 2</span></span></td>
<td><span data-ttu-id="e76e7-620">20</span><span class="sxs-lookup"><span data-stu-id="e76e7-620">20</span></span></td>
<td><span data-ttu-id="e76e7-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="e76e7-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="e76e7-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="e76e7-622">1,495.71</span></span></td>
<td><span data-ttu-id="e76e7-623">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e76e7-624">Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="e76e7-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-625">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-625">Cost object</span></span></th>
<th><span data-ttu-id="e76e7-626">Ampleur</span><span class="sxs-lookup"><span data-stu-id="e76e7-626">Magnitude</span></span></th>
<th><span data-ttu-id="e76e7-627">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="e76e7-627">Allocation factor</span></span></th>
<th><span data-ttu-id="e76e7-628">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-628">Amount</span></span></th>
<th><span data-ttu-id="e76e7-629">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-630">Prod 1</span></span></td>
<td><span data-ttu-id="e76e7-631">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-631">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-632">80</span><span class="sxs-lookup"><span data-stu-id="e76e7-632">80</span></span></td>
<td><span data-ttu-id="e76e7-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="e76e7-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="e76e7-634">241.05</span><span class="sxs-lookup"><span data-stu-id="e76e7-634">241.05</span></span></td>
<td><span data-ttu-id="e76e7-635">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-636">Prod 2</span></span></td>
<td><span data-ttu-id="e76e7-637">Produit 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-637">Product 2</span></span></td>
<td><span data-ttu-id="e76e7-638">15</span><span class="sxs-lookup"><span data-stu-id="e76e7-638">15</span></span></td>
<td><span data-ttu-id="e76e7-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="e76e7-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="e76e7-640">45.20</span><span class="sxs-lookup"><span data-stu-id="e76e7-640">45.20</span></span></td>
<td><span data-ttu-id="e76e7-641">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-642">Prod 1</span></span></td>
<td><span data-ttu-id="e76e7-643">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-643">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-644">80</span><span class="sxs-lookup"><span data-stu-id="e76e7-644">80</span></span></td>
<td><span data-ttu-id="e76e7-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="e76e7-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="e76e7-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="e76e7-646">2,507.09</span></span></td>
<td><span data-ttu-id="e76e7-647">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-648">Prod 2</span></span></td>
<td><span data-ttu-id="e76e7-649">Produit 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-649">Product 2</span></span></td>
<td><span data-ttu-id="e76e7-650">15</span><span class="sxs-lookup"><span data-stu-id="e76e7-650">15</span></span></td>
<td><span data-ttu-id="e76e7-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="e76e7-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="e76e7-652">470.08</span><span class="sxs-lookup"><span data-stu-id="e76e7-652">470.08</span></span></td>
<td><span data-ttu-id="e76e7-653">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="e76e7-654">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="e76e7-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e76e7-655">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="e76e7-655">Journal</span></span></th>
<th><span data-ttu-id="e76e7-656">Type de journal</span><span class="sxs-lookup"><span data-stu-id="e76e7-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="e76e7-657">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="e76e7-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="e76e7-658">Version</span><span class="sxs-lookup"><span data-stu-id="e76e7-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-659">00004</span><span class="sxs-lookup"><span data-stu-id="e76e7-659">00004</span></span></td>
<td><span data-ttu-id="e76e7-660">Journal de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="e76e7-661">Exercice</span><span class="sxs-lookup"><span data-stu-id="e76e7-661">Fiscal</span></span></td>
<td><span data-ttu-id="e76e7-662">2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-662">2017</span></span></td>
<td><span data-ttu-id="e76e7-663">Période 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-663">Period 1</span></span></td>
<td><span data-ttu-id="e76e7-664">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="e76e7-665">Lignes de journal</span><span class="sxs-lookup"><span data-stu-id="e76e7-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e76e7-666">Date comptable</span><span class="sxs-lookup"><span data-stu-id="e76e7-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-667">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-668">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-668">Cost element</span></span></th>
<th><span data-ttu-id="e76e7-669">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-669">Cost behavior</span></span></th>
<th><span data-ttu-id="e76e7-670">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-671">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-672">CC001</span><span class="sxs-lookup"><span data-stu-id="e76e7-672">CC001</span></span></td>
<td><span data-ttu-id="e76e7-673">RH</span><span class="sxs-lookup"><span data-stu-id="e76e7-673">HR</span></span></td>
<td><span data-ttu-id="e76e7-674">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-674">10001</span></span></td>
<td><span data-ttu-id="e76e7-675">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-675">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-676">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-676">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-677">500,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-678">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-679">CC001</span><span class="sxs-lookup"><span data-stu-id="e76e7-679">CC001</span></span></td>
<td><span data-ttu-id="e76e7-680">RH</span><span class="sxs-lookup"><span data-stu-id="e76e7-680">HR</span></span></td>
<td><span data-ttu-id="e76e7-681">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-681">10001</span></span></td>
<td><span data-ttu-id="e76e7-682">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-682">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-683">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-683">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="e76e7-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-685">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-686">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-686">CC002</span></span></td>
<td><span data-ttu-id="e76e7-687">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-687">Finance</span></span></td>
<td><span data-ttu-id="e76e7-688">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-688">10001</span></span></td>
<td><span data-ttu-id="e76e7-689">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-689">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-690">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-690">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-691">675.00</span><span class="sxs-lookup"><span data-stu-id="e76e7-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-692">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-693">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-693">CC002</span></span></td>
<td><span data-ttu-id="e76e7-694">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-694">Finance</span></span></td>
<td><span data-ttu-id="e76e7-695">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-695">10001</span></span></td>
<td><span data-ttu-id="e76e7-696">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-696">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-697">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-697">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="e76e7-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-699">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-700">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-700">CC003</span></span></td>
<td><span data-ttu-id="e76e7-701">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-701">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-702">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-702">10001</span></span></td>
<td><span data-ttu-id="e76e7-703">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-703">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-704">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-704">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-705">713.75</span><span class="sxs-lookup"><span data-stu-id="e76e7-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-706">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-707">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-707">CC003</span></span></td>
<td><span data-ttu-id="e76e7-708">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-708">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-709">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-709">10001</span></span></td>
<td><span data-ttu-id="e76e7-710">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-710">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-711">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-711">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="e76e7-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-713">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-714">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-714">CC003</span></span></td>
<td><span data-ttu-id="e76e7-715">Emballage</span><span class="sxs-lookup"><span data-stu-id="e76e7-715">Packaging</span></span></td>
<td><span data-ttu-id="e76e7-716">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-716">10001</span></span></td>
<td><span data-ttu-id="e76e7-717">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-717">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-718">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-718">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-719">286.25</span><span class="sxs-lookup"><span data-stu-id="e76e7-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-720">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-721">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-721">CC003</span></span></td>
<td><span data-ttu-id="e76e7-722">Emballage</span><span class="sxs-lookup"><span data-stu-id="e76e7-722">Packaging</span></span></td>
<td><span data-ttu-id="e76e7-723">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-723">10001</span></span></td>
<td><span data-ttu-id="e76e7-724">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-724">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-725">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-725">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="e76e7-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-727">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-728">Prod 1</span></span></td>
<td><span data-ttu-id="e76e7-729">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-729">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-730">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-730">10001</span></span></td>
<td><span data-ttu-id="e76e7-731">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-731">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-732">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-732">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-733">776.36</span><span class="sxs-lookup"><span data-stu-id="e76e7-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-734">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-735">Prod 1</span></span></td>
<td><span data-ttu-id="e76e7-736">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-736">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-737">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-737">10001</span></span></td>
<td><span data-ttu-id="e76e7-738">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-738">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-739">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-739">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="e76e7-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-741">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-742">Prod 2</span></span></td>
<td><span data-ttu-id="e76e7-743">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-743">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-744">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-744">10001</span></span></td>
<td><span data-ttu-id="e76e7-745">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-745">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-746">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-746">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-747">223.64</span><span class="sxs-lookup"><span data-stu-id="e76e7-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-748">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="e76e7-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-749">Prod 2</span></span></td>
<td><span data-ttu-id="e76e7-750">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-750">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-751">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-751">10001</span></span></td>
<td><span data-ttu-id="e76e7-752">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-752">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-753">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-753">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="e76e7-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="e76e7-755">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="e76e7-756">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="e76e7-757">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-757">Cost element</span></span></th>
<th><span data-ttu-id="e76e7-758">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="e76e7-758">Cost behavior</span></span></th>
<th><span data-ttu-id="e76e7-759">Montant</span><span class="sxs-lookup"><span data-stu-id="e76e7-759">Amount</span></span></th>
<th><span data-ttu-id="e76e7-760">Date comptable</span><span class="sxs-lookup"><span data-stu-id="e76e7-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e76e7-761">CC001</span><span class="sxs-lookup"><span data-stu-id="e76e7-761">CC001</span></span></td>
<td><span data-ttu-id="e76e7-762">RH</span><span class="sxs-lookup"><span data-stu-id="e76e7-762">HR</span></span></td>
<td><span data-ttu-id="e76e7-763">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-763">10001</span></span></td>
<td><span data-ttu-id="e76e7-764">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-764">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-765">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-765">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-766">-500.00</span></span></td>
<td><span data-ttu-id="e76e7-767">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-768">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-768">CC002</span></span></td>
<td><span data-ttu-id="e76e7-769">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-769">Finance</span></span></td>
<td><span data-ttu-id="e76e7-770">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-770">10001</span></span></td>
<td><span data-ttu-id="e76e7-771">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-771">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-772">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-772">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-773">175.00</span><span class="sxs-lookup"><span data-stu-id="e76e7-773">175.00</span></span></td>
<td><span data-ttu-id="e76e7-774">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-775">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-775">CC003</span></span></td>
<td><span data-ttu-id="e76e7-776">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-776">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-777">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-777">10001</span></span></td>
<td><span data-ttu-id="e76e7-778">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-778">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-779">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-779">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-780">275.00</span><span class="sxs-lookup"><span data-stu-id="e76e7-780">275.00</span></span></td>
<td><span data-ttu-id="e76e7-781">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-782">CC004</span><span class="sxs-lookup"><span data-stu-id="e76e7-782">CC004</span></span></td>
<td><span data-ttu-id="e76e7-783">Emballage</span><span class="sxs-lookup"><span data-stu-id="e76e7-783">Packaging</span></span></td>
<td><span data-ttu-id="e76e7-784">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-784">10001</span></span></td>
<td><span data-ttu-id="e76e7-785">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-785">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-786">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-786">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-787">50,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-787">50,00</span></span></td>
<td><span data-ttu-id="e76e7-788">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-789">CC001</span><span class="sxs-lookup"><span data-stu-id="e76e7-789">CC001</span></span></td>
<td><span data-ttu-id="e76e7-790">RH</span><span class="sxs-lookup"><span data-stu-id="e76e7-790">HR</span></span></td>
<td><span data-ttu-id="e76e7-791">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-791">10001</span></span></td>
<td><span data-ttu-id="e76e7-792">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-792">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-793">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-793">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="e76e7-794">-1,245.71</span></span></td>
<td><span data-ttu-id="e76e7-795">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-796">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-796">CC002</span></span></td>
<td><span data-ttu-id="e76e7-797">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-797">Finance</span></span></td>
<td><span data-ttu-id="e76e7-798">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-798">10001</span></span></td>
<td><span data-ttu-id="e76e7-799">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-799">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-800">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-800">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-801">436.00</span><span class="sxs-lookup"><span data-stu-id="e76e7-801">436.00</span></span></td>
<td><span data-ttu-id="e76e7-802">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-803">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-803">CC003</span></span></td>
<td><span data-ttu-id="e76e7-804">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-804">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-805">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-805">10001</span></span></td>
<td><span data-ttu-id="e76e7-806">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-806">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-807">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-807">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-808">685.14</span><span class="sxs-lookup"><span data-stu-id="e76e7-808">685.14</span></span></td>
<td><span data-ttu-id="e76e7-809">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-810">CC004</span><span class="sxs-lookup"><span data-stu-id="e76e7-810">CC004</span></span></td>
<td><span data-ttu-id="e76e7-811">Emballage</span><span class="sxs-lookup"><span data-stu-id="e76e7-811">Packaging</span></span></td>
<td><span data-ttu-id="e76e7-812">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-812">10001</span></span></td>
<td><span data-ttu-id="e76e7-813">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-813">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-814">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-814">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-815">124.57</span><span class="sxs-lookup"><span data-stu-id="e76e7-815">124.57</span></span></td>
<td><span data-ttu-id="e76e7-816">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-817">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-817">CC002</span></span></td>
<td><span data-ttu-id="e76e7-818">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-818">Finance</span></span></td>
<td><span data-ttu-id="e76e7-819">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-819">10001</span></span></td>
<td><span data-ttu-id="e76e7-820">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-820">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-821">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-821">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-822">-675.00</span></span></td>
<td><span data-ttu-id="e76e7-823">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-824">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-824">CC003</span></span></td>
<td><span data-ttu-id="e76e7-825">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-825">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-826">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-826">10001</span></span></td>
<td><span data-ttu-id="e76e7-827">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-827">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-828">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-828">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-829">438.75</span><span class="sxs-lookup"><span data-stu-id="e76e7-829">438.75</span></span></td>
<td><span data-ttu-id="e76e7-830">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-831">CC004</span><span class="sxs-lookup"><span data-stu-id="e76e7-831">CC004</span></span></td>
<td><span data-ttu-id="e76e7-832">Emballage</span><span class="sxs-lookup"><span data-stu-id="e76e7-832">Packaging</span></span></td>
<td><span data-ttu-id="e76e7-833">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-833">10001</span></span></td>
<td><span data-ttu-id="e76e7-834">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-834">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-835">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-835">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-836">236.25</span><span class="sxs-lookup"><span data-stu-id="e76e7-836">236.25</span></span></td>
<td><span data-ttu-id="e76e7-837">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-838">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-838">CC002</span></span></td>
<td><span data-ttu-id="e76e7-839">Finances</span><span class="sxs-lookup"><span data-stu-id="e76e7-839">Finance</span></span></td>
<td><span data-ttu-id="e76e7-840">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-840">10001</span></span></td>
<td><span data-ttu-id="e76e7-841">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-841">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-842">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-842">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="e76e7-843">-8,150.29</span></span></td>
<td><span data-ttu-id="e76e7-844">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-845">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-845">CC003</span></span></td>
<td><span data-ttu-id="e76e7-846">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-846">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-847">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-847">10001</span></span></td>
<td><span data-ttu-id="e76e7-848">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-848">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-849">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-849">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="e76e7-850">5,297.69</span></span></td>
<td><span data-ttu-id="e76e7-851">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-852">CC004</span><span class="sxs-lookup"><span data-stu-id="e76e7-852">CC004</span></span></td>
<td><span data-ttu-id="e76e7-853">Emballage</span><span class="sxs-lookup"><span data-stu-id="e76e7-853">Packaging</span></span></td>
<td><span data-ttu-id="e76e7-854">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-854">10001</span></span></td>
<td><span data-ttu-id="e76e7-855">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-855">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-856">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-856">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="e76e7-857">2,852.60</span></span></td>
<td><span data-ttu-id="e76e7-858">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-859">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-859">CC003</span></span></td>
<td><span data-ttu-id="e76e7-860">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-860">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-861">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-861">10001</span></span></td>
<td><span data-ttu-id="e76e7-862">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-862">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-863">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-863">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="e76e7-864">-713.75</span></span></td>
<td><span data-ttu-id="e76e7-865">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-866">Prod 1</span></span></td>
<td><span data-ttu-id="e76e7-867">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-867">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-868">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-868">10001</span></span></td>
<td><span data-ttu-id="e76e7-869">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-869">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-870">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-870">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-871">535.31</span><span class="sxs-lookup"><span data-stu-id="e76e7-871">535.31</span></span></td>
<td><span data-ttu-id="e76e7-872">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-873">Prod 2</span></span></td>
<td><span data-ttu-id="e76e7-874">Produit 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-874">Product 2</span></span></td>
<td><span data-ttu-id="e76e7-875">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-875">10001</span></span></td>
<td><span data-ttu-id="e76e7-876">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-876">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-877">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-877">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-878">178.44</span><span class="sxs-lookup"><span data-stu-id="e76e7-878">178.44</span></span></td>
<td><span data-ttu-id="e76e7-879">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-880">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-880">CC003</span></span></td>
<td><span data-ttu-id="e76e7-881">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-881">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-882">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-882">10001</span></span></td>
<td><span data-ttu-id="e76e7-883">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-883">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-884">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-884">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="e76e7-885">-5,982.83</span></span></td>
<td><span data-ttu-id="e76e7-886">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-887">Prod 1</span></span></td>
<td><span data-ttu-id="e76e7-888">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-888">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-889">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-889">10001</span></span></td>
<td><span data-ttu-id="e76e7-890">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-890">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-891">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-891">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="e76e7-892">4,487.12</span></span></td>
<td><span data-ttu-id="e76e7-893">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-894">Prod 2</span></span></td>
<td><span data-ttu-id="e76e7-895">Produit 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-895">Product 2</span></span></td>
<td><span data-ttu-id="e76e7-896">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-896">10001</span></span></td>
<td><span data-ttu-id="e76e7-897">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-897">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-898">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-898">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="e76e7-899">1,495.71</span></span></td>
<td><span data-ttu-id="e76e7-900">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-901">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-901">CC003</span></span></td>
<td><span data-ttu-id="e76e7-902">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-902">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-903">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-903">10001</span></span></td>
<td><span data-ttu-id="e76e7-904">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-904">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-905">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-905">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="e76e7-906">-286.25</span></span></td>
<td><span data-ttu-id="e76e7-907">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-908">Prod 1</span></span></td>
<td><span data-ttu-id="e76e7-909">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-909">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-910">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-910">10001</span></span></td>
<td><span data-ttu-id="e76e7-911">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-911">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-912">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-912">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-913">241.05</span><span class="sxs-lookup"><span data-stu-id="e76e7-913">241.05</span></span></td>
<td><span data-ttu-id="e76e7-914">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-915">Prod 2</span></span></td>
<td><span data-ttu-id="e76e7-916">Produit 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-916">Product 2</span></span></td>
<td><span data-ttu-id="e76e7-917">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-917">10001</span></span></td>
<td><span data-ttu-id="e76e7-918">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-918">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-919">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-919">Fixed cost</span></span></td>
<td><span data-ttu-id="e76e7-920">45.20</span><span class="sxs-lookup"><span data-stu-id="e76e7-920">45.20</span></span></td>
<td><span data-ttu-id="e76e7-921">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-922">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-922">CC003</span></span></td>
<td><span data-ttu-id="e76e7-923">Assemblage</span><span class="sxs-lookup"><span data-stu-id="e76e7-923">Assembly</span></span></td>
<td><span data-ttu-id="e76e7-924">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-924">10001</span></span></td>
<td><span data-ttu-id="e76e7-925">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-925">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-926">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-926">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="e76e7-927">-2,977.17</span></span></td>
<td><span data-ttu-id="e76e7-928">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-929">Prod 1</span></span></td>
<td><span data-ttu-id="e76e7-930">Produit 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-930">Product 1</span></span></td>
<td><span data-ttu-id="e76e7-931">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-931">10001</span></span></td>
<td><span data-ttu-id="e76e7-932">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-932">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-933">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-933">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="e76e7-934">2,507.09</span></span></td>
<td><span data-ttu-id="e76e7-935">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e76e7-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-936">Prod 2</span></span></td>
<td><span data-ttu-id="e76e7-937">Produit 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-937">Product 2</span></span></td>
<td><span data-ttu-id="e76e7-938">10001</span><span class="sxs-lookup"><span data-stu-id="e76e7-938">10001</span></span></td>
<td><span data-ttu-id="e76e7-939">Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-939">Electricity</span></span></td>
<td><span data-ttu-id="e76e7-940">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-940">Variable cost</span></span></td>
<td><span data-ttu-id="e76e7-941">470.08</span><span class="sxs-lookup"><span data-stu-id="e76e7-941">470.08</span></span></td>
<td><span data-ttu-id="e76e7-942">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="e76e7-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="e76e7-943">Conclusion</span><span class="sxs-lookup"><span data-stu-id="e76e7-943">Conclusion</span></span>
<span data-ttu-id="e76e7-944">Dans la comptabilité financière, un coût de 10 000,00 pour l’électricité est imputé sur un ID de centre de coût fictif.</span><span class="sxs-lookup"><span data-stu-id="e76e7-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="e76e7-945">Par conséquent, les comptables sauront que ce coût doit être affecté.</span><span class="sxs-lookup"><span data-stu-id="e76e7-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="e76e7-946">Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l’organisation, selon les stratégies et les règles qui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="e76e7-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="e76e7-947">Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="e76e7-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="e76e7-948">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="e76e7-949">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="e76e7-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="e76e7-950">Total</span><span class="sxs-lookup"><span data-stu-id="e76e7-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="e76e7-951">CC099</span><span class="sxs-lookup"><span data-stu-id="e76e7-951">CC099</span></span></th>
<th><span data-ttu-id="e76e7-952">CC001</span><span class="sxs-lookup"><span data-stu-id="e76e7-952">CC001</span></span></th>
<th><span data-ttu-id="e76e7-953">CC002</span><span class="sxs-lookup"><span data-stu-id="e76e7-953">CC002</span></span></th>
<th><span data-ttu-id="e76e7-954">CC003</span><span class="sxs-lookup"><span data-stu-id="e76e7-954">CC003</span></span></th>
<th><span data-ttu-id="e76e7-955">CC004</span><span class="sxs-lookup"><span data-stu-id="e76e7-955">CC004</span></span></th>
<th><span data-ttu-id="e76e7-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-956">Proj 1</span></span></th>
<th><span data-ttu-id="e76e7-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-957">Proj 2</span></span></th>
<th><span data-ttu-id="e76e7-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="e76e7-958">Prod 1</span></span></th>
<th><span data-ttu-id="e76e7-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="e76e7-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="e76e7-960">10001 Électricité</span><span class="sxs-lookup"><span data-stu-id="e76e7-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="e76e7-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="e76e7-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="e76e7-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="e76e7-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="e76e7-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="e76e7-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="e76e7-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="e76e7-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="e76e7-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="e76e7-970">Non classifié</span><span class="sxs-lookup"><span data-stu-id="e76e7-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-971">0,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="e76e7-972">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="e76e7-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-973">0,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-974">0,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-975">0,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-976">0,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-977">0,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-978">776.36</span><span class="sxs-lookup"><span data-stu-id="e76e7-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-979">223.64</span><span class="sxs-lookup"><span data-stu-id="e76e7-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-980"><strong>1 000,00</strong></span><span class="sxs-lookup"><span data-stu-id="e76e7-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="e76e7-981">Coût variable</span><span class="sxs-lookup"><span data-stu-id="e76e7-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-982">000</span><span class="sxs-lookup"><span data-stu-id="e76e7-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-983">0,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-984">0,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-985">0,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-986">0,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-987">30,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-988">10,00</span><span class="sxs-lookup"><span data-stu-id="e76e7-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="e76e7-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="e76e7-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="e76e7-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="e76e7-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="e76e7-992">Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût.</span><span class="sxs-lookup"><span data-stu-id="e76e7-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="e76e7-993">Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="e76e7-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="e76e7-994">Autrement dit, les objets de coût de plus bas niveau supportent le coût.</span><span class="sxs-lookup"><span data-stu-id="e76e7-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="e76e7-995">Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts.</span><span class="sxs-lookup"><span data-stu-id="e76e7-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="e76e7-996">Pour plus d’informations, voir [Stratégie de repositionnement des coûts et calcul des frais généraux](cost-rollup.md)..</span><span class="sxs-lookup"><span data-stu-id="e76e7-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]