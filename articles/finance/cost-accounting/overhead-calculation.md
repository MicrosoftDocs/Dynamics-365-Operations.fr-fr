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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443282"
---
# <a name="overhead-calculation"></a><span data-ttu-id="bd747-103">Calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="bd747-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd747-104">Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="bd747-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="bd747-105">Définition des termes</span><span class="sxs-lookup"><span data-stu-id="bd747-105">Term definition</span></span>
---------------

<span data-ttu-id="bd747-106">Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique.</span><span class="sxs-lookup"><span data-stu-id="bd747-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="bd747-107">Les frais généraux permettent essentiellement l’identification des activités rémunératrices.</span><span class="sxs-lookup"><span data-stu-id="bd747-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="bd747-108">Voici quelques exemples de frais généraux :</span><span class="sxs-lookup"><span data-stu-id="bd747-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="bd747-109">Loyer</span><span class="sxs-lookup"><span data-stu-id="bd747-109">Rent</span></span>
-   <span data-ttu-id="bd747-110">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-110">Electricity</span></span>
-   <span data-ttu-id="bd747-111">Salaires administratifs</span><span class="sxs-lookup"><span data-stu-id="bd747-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="bd747-112">Vue d’ensemble du calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="bd747-112">Overhead calculation overview</span></span>
<span data-ttu-id="bd747-113">Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l’ordre correct.</span><span class="sxs-lookup"><span data-stu-id="bd747-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="bd747-114">Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées.</span><span class="sxs-lookup"><span data-stu-id="bd747-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="bd747-115">Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions.</span><span class="sxs-lookup"><span data-stu-id="bd747-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="bd747-116">Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable.</span><span class="sxs-lookup"><span data-stu-id="bd747-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="bd747-117">Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="bd747-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="bd747-118">L’ID de version unique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="bd747-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="bd747-119">Type de version</span><span class="sxs-lookup"><span data-stu-id="bd747-119">Version type</span></span>
-   <span data-ttu-id="bd747-120">Date et heure</span><span class="sxs-lookup"><span data-stu-id="bd747-120">Date and time</span></span>
-   <span data-ttu-id="bd747-121">Comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="bd747-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="bd747-122">Exercice</span><span class="sxs-lookup"><span data-stu-id="bd747-122">Fiscal year</span></span>
-   <span data-ttu-id="bd747-123">Période fiscale</span><span class="sxs-lookup"><span data-stu-id="bd747-123">Fiscal period</span></span>

<span data-ttu-id="bd747-124">Le calcul des frais généraux est effectué indépendamment de la version.</span><span class="sxs-lookup"><span data-stu-id="bd747-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="bd747-125">Par conséquent, vous pouvez calculer la version de budget avant la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="bd747-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="bd747-126">Le calcul des frais généraux comporte quatre étapes, comme le montre l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="bd747-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="bd747-127">Dans chaque étape, un en-tête de journal avec des entrées de journal est créé.</span><span class="sxs-lookup"><span data-stu-id="bd747-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="bd747-128">Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul.</span><span class="sxs-lookup"><span data-stu-id="bd747-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="bd747-129">Les stratégies et les règles s’appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie.</span><span class="sxs-lookup"><span data-stu-id="bd747-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="bd747-130">Par conséquent, vous disposez toujours d’une traçabilité complète.</span><span class="sxs-lookup"><span data-stu-id="bd747-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="bd747-131">[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="bd747-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="bd747-132">Calculer et affecter les frais généraux Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="bd747-133">Dans la comptabilité financière, certaines coûts, tels que l’électricité, sont enregistrés comme montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="bd747-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="bd747-134">Par conséquent, l’analyse détaillée n’est pas fournie pour le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="bd747-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="bd747-135">Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l’organisation, les coûts doivent suivre les unités organisationnelles.</span><span class="sxs-lookup"><span data-stu-id="bd747-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="bd747-136">Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste.</span><span class="sxs-lookup"><span data-stu-id="bd747-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="bd747-137">Dans la comptabilité, le coût de l’électricité peut être validé comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="bd747-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bd747-138">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bd747-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-139">Centre de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-140">Compte principal</span><span class="sxs-lookup"><span data-stu-id="bd747-140">Main account</span></span></th>
<th><span data-ttu-id="bd747-141">Montant en devise comptable</span><span class="sxs-lookup"><span data-stu-id="bd747-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-142">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="bd747-143">CC099</span><span class="sxs-lookup"><span data-stu-id="bd747-143">CC099</span></span></td>
<td><span data-ttu-id="bd747-144">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bd747-144">Default cost center</span></span></td>
<td><span data-ttu-id="bd747-145">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-145">10001</span></span></td>
<td><span data-ttu-id="bd747-146">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-146">Electricity</span></span></td>
<td><span data-ttu-id="bd747-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="bd747-148">Étape 1 : Traiter le calcul du comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="bd747-149">Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="bd747-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="bd747-150">Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.</span><span class="sxs-lookup"><span data-stu-id="bd747-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="bd747-151">Définir la règle de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-151">Define the cost behavior rule</span></span>

<span data-ttu-id="bd747-152">Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation.</span><span class="sxs-lookup"><span data-stu-id="bd747-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="bd747-153">Les factures d’électricité correspondent souvent à cette définition.</span><span class="sxs-lookup"><span data-stu-id="bd747-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="bd747-154">Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH).</span><span class="sxs-lookup"><span data-stu-id="bd747-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="bd747-155">Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :</span><span class="sxs-lookup"><span data-stu-id="bd747-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="bd747-156">Montant fixe 1 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="bd747-157">0 &lt;= 1 000,00 = Fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="bd747-158">1 000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="bd747-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="bd747-159">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bd747-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bd747-160">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bd747-160">Journal</span></span></th>
<th><span data-ttu-id="bd747-161">Type de journal</span><span class="sxs-lookup"><span data-stu-id="bd747-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="bd747-162">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="bd747-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="bd747-163">Version</span><span class="sxs-lookup"><span data-stu-id="bd747-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-164">00001</span><span class="sxs-lookup"><span data-stu-id="bd747-164">00001</span></span></td>
<td><span data-ttu-id="bd747-165">Journal de calcul de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="bd747-166">Exercice</span><span class="sxs-lookup"><span data-stu-id="bd747-166">Fiscal</span></span></td>
<td><span data-ttu-id="bd747-167">2017</span><span class="sxs-lookup"><span data-stu-id="bd747-167">2017</span></span></td>
<td><span data-ttu-id="bd747-168">Période 1</span><span class="sxs-lookup"><span data-stu-id="bd747-168">Period 1</span></span></td>
<td><span data-ttu-id="bd747-169">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="bd747-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="bd747-170">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="bd747-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bd747-171">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bd747-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-172">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-173">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-173">Cost element</span></span></th>
<th><span data-ttu-id="bd747-174">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-174">Cost behavior</span></span></th>
<th><span data-ttu-id="bd747-175">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-176">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="bd747-177">CC099</span><span class="sxs-lookup"><span data-stu-id="bd747-177">CC099</span></span></td>
<td><span data-ttu-id="bd747-178">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bd747-178">Default cost center</span></span></td>
<td><span data-ttu-id="bd747-179">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-179">10001</span></span></td>
<td><span data-ttu-id="bd747-180">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-180">Electricity</span></span></td>
<td><span data-ttu-id="bd747-181">Non classifié</span><span class="sxs-lookup"><span data-stu-id="bd747-181">Unclassified</span></span></td>
<td><span data-ttu-id="bd747-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="bd747-183">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-184">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-185">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-185">Cost element</span></span></th>
<th><span data-ttu-id="bd747-186">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-186">Cost behavior</span></span></th>
<th><span data-ttu-id="bd747-187">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-187">Amount</span></span></th>
<th><span data-ttu-id="bd747-188">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bd747-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-189">CC099</span><span class="sxs-lookup"><span data-stu-id="bd747-189">CC099</span></span></td>
<td><span data-ttu-id="bd747-190">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bd747-190">Default cost center</span></span></td>
<td><span data-ttu-id="bd747-191">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-191">10001</span></span></td>
<td><span data-ttu-id="bd747-192">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-192">Electricity</span></span></td>
<td><span data-ttu-id="bd747-193">Non classifié</span><span class="sxs-lookup"><span data-stu-id="bd747-193">Unclassified</span></span></td>
<td><span data-ttu-id="bd747-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-194">10,000.00</span></span></td>
<td><span data-ttu-id="bd747-195">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-196">CC099</span><span class="sxs-lookup"><span data-stu-id="bd747-196">CC099</span></span></td>
<td><span data-ttu-id="bd747-197">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bd747-197">Default cost center</span></span></td>
<td><span data-ttu-id="bd747-198">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-198">10001</span></span></td>
<td><span data-ttu-id="bd747-199">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-199">Electricity</span></span></td>
<td><span data-ttu-id="bd747-200">Non classifié</span><span class="sxs-lookup"><span data-stu-id="bd747-200">Unclassified</span></span></td>
<td><span data-ttu-id="bd747-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-201">-10,000.00</span></span></td>
<td><span data-ttu-id="bd747-202">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-203">CC099</span><span class="sxs-lookup"><span data-stu-id="bd747-203">CC099</span></span></td>
<td><span data-ttu-id="bd747-204">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bd747-204">Default cost center</span></span></td>
<td><span data-ttu-id="bd747-205">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-205">10001</span></span></td>
<td><span data-ttu-id="bd747-206">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-206">Electricity</span></span></td>
<td><span data-ttu-id="bd747-207">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-207">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-208">1,000.00</span></span></td>
<td><span data-ttu-id="bd747-209">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-210">CC099</span><span class="sxs-lookup"><span data-stu-id="bd747-210">CC099</span></span></td>
<td><span data-ttu-id="bd747-211">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bd747-211">Default cost center</span></span></td>
<td><span data-ttu-id="bd747-212">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-212">10001</span></span></td>
<td><span data-ttu-id="bd747-213">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-213">Electricity</span></span></td>
<td><span data-ttu-id="bd747-214">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-214">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-215">9 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-215">9,000.00</span></span></td>
<td><span data-ttu-id="bd747-216">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-217">Pour plus d’informations, voir [Créer et affecter une stratégie de comportement de coûts à une unité de contrôle des coûts](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="bd747-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="bd747-218">Étape 2 : Traiter le calcul de distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="bd747-219">La distribution des coûts est utilisée pour redistribuer le coût d’un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée.</span><span class="sxs-lookup"><span data-stu-id="bd747-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="bd747-220">La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l’élément de coût principal du coût d’origine.</span><span class="sxs-lookup"><span data-stu-id="bd747-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="bd747-221">Définir la règle de distribution de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-221">Define the cost distribution rule</span></span>

<span data-ttu-id="bd747-222">Dans la comptabilité financière, les coûts d’électricité sont souvent enregistrés comme un montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="bd747-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="bd747-223">Dans le Contrôle de gestion, cette approche n’est pas assez détaillée.</span><span class="sxs-lookup"><span data-stu-id="bd747-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="bd747-224">Le coût variable doit être attribué aux différents objets de coûts sur une base juste.</span><span class="sxs-lookup"><span data-stu-id="bd747-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="bd747-225">La base de répartition la plus logique est la consommation de l’électricité (KWH).</span><span class="sxs-lookup"><span data-stu-id="bd747-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="bd747-226">Un membre de dimension statistique nommé Électricité est créé, et la consommation d’électricité est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="bd747-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="bd747-227">Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="bd747-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-228">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-228">Cost object</span></span></th>
<th><span data-ttu-id="bd747-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="bd747-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-230">CC001</span><span class="sxs-lookup"><span data-stu-id="bd747-230">CC001</span></span></td>
<td><span data-ttu-id="bd747-231">RH</span><span class="sxs-lookup"><span data-stu-id="bd747-231">HR</span></span></td>
<td><span data-ttu-id="bd747-232">1 000</span><span class="sxs-lookup"><span data-stu-id="bd747-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-233">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-233">CC002</span></span></td>
<td><span data-ttu-id="bd747-234">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-234">Finance</span></span></td>
<td><span data-ttu-id="bd747-235">6 000</span><span class="sxs-lookup"><span data-stu-id="bd747-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-236">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-236">CC003</span></span></td>
<td><span data-ttu-id="bd747-237">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-237">Assembly</span></span></td>
<td><span data-ttu-id="bd747-238">0</span><span class="sxs-lookup"><span data-stu-id="bd747-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-239">Le tableau suivant illustre le résultat lorsque la consommation d’électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="bd747-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-240">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-240">Cost object</span></span></th>
<th><span data-ttu-id="bd747-241">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bd747-241">Magnitude</span></span></th>
<th><span data-ttu-id="bd747-242">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bd747-242">Allocation factor</span></span></th>
<th><span data-ttu-id="bd747-243">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-244">CC001</span><span class="sxs-lookup"><span data-stu-id="bd747-244">CC001</span></span></td>
<td><span data-ttu-id="bd747-245">RH</span><span class="sxs-lookup"><span data-stu-id="bd747-245">HR</span></span></td>
<td><span data-ttu-id="bd747-246">1 000</span><span class="sxs-lookup"><span data-stu-id="bd747-246">1,000</span></span></td>
<td><span data-ttu-id="bd747-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="bd747-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="bd747-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-249">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-249">CC002</span></span></td>
<td><span data-ttu-id="bd747-250">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-250">Finance</span></span></td>
<td><span data-ttu-id="bd747-251">6 000</span><span class="sxs-lookup"><span data-stu-id="bd747-251">6,000</span></span></td>
<td><span data-ttu-id="bd747-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="bd747-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="bd747-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-254">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-254">CC003</span></span></td>
<td><span data-ttu-id="bd747-255">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-255">Assembly</span></span></td>
<td><span data-ttu-id="bd747-256">0</span><span class="sxs-lookup"><span data-stu-id="bd747-256">0</span></span></td>
<td><span data-ttu-id="bd747-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="bd747-258">0,00</span><span class="sxs-lookup"><span data-stu-id="bd747-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-259">Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l’électricité.</span><span class="sxs-lookup"><span data-stu-id="bd747-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="bd747-260">Vous pouvez obtenir ce résultat à l’aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d’électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="bd747-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-261">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-261">Cost object</span></span></th>
<th><span data-ttu-id="bd747-262">Formule</span><span class="sxs-lookup"><span data-stu-id="bd747-262">Formula</span></span></th>
<th><span data-ttu-id="bd747-263">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bd747-263">Magnitude</span></span></th>
<th><span data-ttu-id="bd747-264">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bd747-264">Allocation factor</span></span></th>
<th><span data-ttu-id="bd747-265">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-266">CC001</span><span class="sxs-lookup"><span data-stu-id="bd747-266">CC001</span></span></td>
<td><span data-ttu-id="bd747-267">RH</span><span class="sxs-lookup"><span data-stu-id="bd747-267">HR</span></span></td>
<td><span data-ttu-id="bd747-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="bd747-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="bd747-269">1</span><span class="sxs-lookup"><span data-stu-id="bd747-269">1</span></span></td>
<td><span data-ttu-id="bd747-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="bd747-271">500,00</span><span class="sxs-lookup"><span data-stu-id="bd747-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-272">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-272">CC002</span></span></td>
<td><span data-ttu-id="bd747-273">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-273">Finance</span></span></td>
<td><span data-ttu-id="bd747-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="bd747-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="bd747-275">1</span><span class="sxs-lookup"><span data-stu-id="bd747-275">1</span></span></td>
<td><span data-ttu-id="bd747-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="bd747-277">500,00</span><span class="sxs-lookup"><span data-stu-id="bd747-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-278">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-278">CC003</span></span></td>
<td><span data-ttu-id="bd747-279">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-279">Assembly</span></span></td>
<td><span data-ttu-id="bd747-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="bd747-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="bd747-281">0</span><span class="sxs-lookup"><span data-stu-id="bd747-281">0</span></span></td>
<td><span data-ttu-id="bd747-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="bd747-283">0,00</span><span class="sxs-lookup"><span data-stu-id="bd747-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="bd747-284">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bd747-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bd747-285">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bd747-285">Journal</span></span></th>
<th><span data-ttu-id="bd747-286">Type de journal</span><span class="sxs-lookup"><span data-stu-id="bd747-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="bd747-287">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="bd747-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="bd747-288">Version</span><span class="sxs-lookup"><span data-stu-id="bd747-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-289">00002</span><span class="sxs-lookup"><span data-stu-id="bd747-289">00002</span></span></td>
<td><span data-ttu-id="bd747-290">Journal de calcul de la distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="bd747-291">Exercice</span><span class="sxs-lookup"><span data-stu-id="bd747-291">Fiscal</span></span></td>
<td><span data-ttu-id="bd747-292">2017</span><span class="sxs-lookup"><span data-stu-id="bd747-292">2017</span></span></td>
<td><span data-ttu-id="bd747-293">Période 1</span><span class="sxs-lookup"><span data-stu-id="bd747-293">Period 1</span></span></td>
<td><span data-ttu-id="bd747-294">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="bd747-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="bd747-295">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="bd747-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bd747-296">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bd747-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-297">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-298">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-298">Cost element</span></span></th>
<th><span data-ttu-id="bd747-299">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-299">Cost behavior</span></span></th>
<th><span data-ttu-id="bd747-300">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-301">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-302">CC099</span><span class="sxs-lookup"><span data-stu-id="bd747-302">CC099</span></span></td>
<td><span data-ttu-id="bd747-303">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bd747-303">Default cost center</span></span></td>
<td><span data-ttu-id="bd747-304">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-304">10001</span></span></td>
<td><span data-ttu-id="bd747-305">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-305">Electricity</span></span></td>
<td><span data-ttu-id="bd747-306">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-306">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-308">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-309">CC099</span><span class="sxs-lookup"><span data-stu-id="bd747-309">CC099</span></span></td>
<td><span data-ttu-id="bd747-310">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bd747-310">Default cost center</span></span></td>
<td><span data-ttu-id="bd747-311">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-311">10001</span></span></td>
<td><span data-ttu-id="bd747-312">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-312">Electricity</span></span></td>
<td><span data-ttu-id="bd747-313">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-313">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-314">9 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="bd747-315">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-316">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-317">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-317">Cost element</span></span></th>
<th><span data-ttu-id="bd747-318">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-318">Cost behavior</span></span></th>
<th><span data-ttu-id="bd747-319">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-319">Amount</span></span></th>
<th><span data-ttu-id="bd747-320">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bd747-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-321">CC099</span><span class="sxs-lookup"><span data-stu-id="bd747-321">CC099</span></span></td>
<td><span data-ttu-id="bd747-322">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bd747-322">Default cost center</span></span></td>
<td><span data-ttu-id="bd747-323">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-323">10001</span></span></td>
<td><span data-ttu-id="bd747-324">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-324">Electricity</span></span></td>
<td><span data-ttu-id="bd747-325">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-325">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-326">-1,000.00</span></span></td>
<td><span data-ttu-id="bd747-327">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-328">CC001</span><span class="sxs-lookup"><span data-stu-id="bd747-328">CC001</span></span></td>
<td><span data-ttu-id="bd747-329">RH</span><span class="sxs-lookup"><span data-stu-id="bd747-329">HR</span></span></td>
<td><span data-ttu-id="bd747-330">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-330">10001</span></span></td>
<td><span data-ttu-id="bd747-331">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-331">Electricity</span></span></td>
<td><span data-ttu-id="bd747-332">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-332">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-333">500,00</span><span class="sxs-lookup"><span data-stu-id="bd747-333">500.00</span></span></td>
<td><span data-ttu-id="bd747-334">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-335">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-335">CC002</span></span></td>
<td><span data-ttu-id="bd747-336">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-336">Finance</span></span></td>
<td><span data-ttu-id="bd747-337">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-337">10001</span></span></td>
<td><span data-ttu-id="bd747-338">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-338">Electricity</span></span></td>
<td><span data-ttu-id="bd747-339">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-339">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-340">500,00</span><span class="sxs-lookup"><span data-stu-id="bd747-340">500.00</span></span></td>
<td><span data-ttu-id="bd747-341">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-342">CC099</span><span class="sxs-lookup"><span data-stu-id="bd747-342">CC099</span></span></td>
<td><span data-ttu-id="bd747-343">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bd747-343">Default cost center</span></span></td>
<td><span data-ttu-id="bd747-344">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-344">10001</span></span></td>
<td><span data-ttu-id="bd747-345">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-345">Electricity</span></span></td>
<td><span data-ttu-id="bd747-346">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-346">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="bd747-347">-9,000.00</span></span></td>
<td><span data-ttu-id="bd747-348">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-349">CC001</span><span class="sxs-lookup"><span data-stu-id="bd747-349">CC001</span></span></td>
<td><span data-ttu-id="bd747-350">RH</span><span class="sxs-lookup"><span data-stu-id="bd747-350">HR</span></span></td>
<td><span data-ttu-id="bd747-351">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-351">10001</span></span></td>
<td><span data-ttu-id="bd747-352">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-352">Electricity</span></span></td>
<td><span data-ttu-id="bd747-353">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-353">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="bd747-354">1,285.71</span></span></td>
<td><span data-ttu-id="bd747-355">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-356">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-356">CC002</span></span></td>
<td><span data-ttu-id="bd747-357">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-357">Finance</span></span></td>
<td><span data-ttu-id="bd747-358">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-358">10001</span></span></td>
<td><span data-ttu-id="bd747-359">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-359">Electricity</span></span></td>
<td><span data-ttu-id="bd747-360">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-360">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="bd747-361">7,714.29</span></span></td>
<td><span data-ttu-id="bd747-362">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-363">Pour plus d’informations, voir [Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="bd747-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="bd747-364">Étape 3 : Traitement du calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="bd747-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="bd747-365">Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût.</span><span class="sxs-lookup"><span data-stu-id="bd747-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="bd747-366">Les frais sont basés sur un taux de coût prédéterminé et l’ampleur de la base d’affectation de répartition.</span><span class="sxs-lookup"><span data-stu-id="bd747-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="bd747-367">Définition du taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="bd747-367">Define the overhead rate</span></span>

<span data-ttu-id="bd747-368">L’objet de coût CC001 HR contribue à un ensemble de projets internes.</span><span class="sxs-lookup"><span data-stu-id="bd747-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="bd747-369">Un membre de dimension statistique nommé Projets HR est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="bd747-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-370">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-370">Cost object</span></span></th>
<th><span data-ttu-id="bd747-371">Heures</span><span class="sxs-lookup"><span data-stu-id="bd747-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="bd747-372">Proj 1</span></span></td>
<td><span data-ttu-id="bd747-373">Projet 1</span><span class="sxs-lookup"><span data-stu-id="bd747-373">Project 1</span></span></td>
<td><span data-ttu-id="bd747-374">3</span><span class="sxs-lookup"><span data-stu-id="bd747-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="bd747-375">Proj 2</span></span></td>
<td><span data-ttu-id="bd747-376">Projet 2</span><span class="sxs-lookup"><span data-stu-id="bd747-376">Project 2</span></span></td>
<td><span data-ttu-id="bd747-377">1</span><span class="sxs-lookup"><span data-stu-id="bd747-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-378">Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.</span><span class="sxs-lookup"><span data-stu-id="bd747-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-379">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-379">Cost object</span></span></th>
<th><span data-ttu-id="bd747-380">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-380">Cost element</span></span></th>
<th><span data-ttu-id="bd747-381">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-381">Cost behavior</span></span></th>
<th><span data-ttu-id="bd747-382">Unités</span><span class="sxs-lookup"><span data-stu-id="bd747-382">Units</span></span></th>
<th><span data-ttu-id="bd747-383">Taux</span><span class="sxs-lookup"><span data-stu-id="bd747-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-384">CC001</span><span class="sxs-lookup"><span data-stu-id="bd747-384">CC001</span></span></td>
<td><span data-ttu-id="bd747-385">RH</span><span class="sxs-lookup"><span data-stu-id="bd747-385">HR</span></span></td>
<td><span data-ttu-id="bd747-386">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-386">10001</span></span></td>
<td><span data-ttu-id="bd747-387">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-387">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-388">1</span><span class="sxs-lookup"><span data-stu-id="bd747-388">1</span></span></td>
<td><span data-ttu-id="bd747-389">10</span><span class="sxs-lookup"><span data-stu-id="bd747-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-390">Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="bd747-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-391">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-391">Cost object</span></span></th>
<th><span data-ttu-id="bd747-392">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bd747-392">Magnitude</span></span></th>
<th><span data-ttu-id="bd747-393">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-393">Cost element</span></span></th>
<th><span data-ttu-id="bd747-394">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bd747-394">Allocation factor</span></span></th>
<th><span data-ttu-id="bd747-395">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="bd747-396">Proj 1</span></span></td>
<td><span data-ttu-id="bd747-397">Projet 1</span><span class="sxs-lookup"><span data-stu-id="bd747-397">Project 1</span></span></td>
<td><span data-ttu-id="bd747-398">3</span><span class="sxs-lookup"><span data-stu-id="bd747-398">3</span></span></td>
<td><span data-ttu-id="bd747-399">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-399">10001</span></span></td>
<td><span data-ttu-id="bd747-400">(3 ÷ 1) × 10m00</span><span class="sxs-lookup"><span data-stu-id="bd747-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="bd747-401">30,00</span><span class="sxs-lookup"><span data-stu-id="bd747-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="bd747-402">Proj 2</span></span></td>
<td><span data-ttu-id="bd747-403">Projet 2</span><span class="sxs-lookup"><span data-stu-id="bd747-403">Project 2</span></span></td>
<td><span data-ttu-id="bd747-404">1</span><span class="sxs-lookup"><span data-stu-id="bd747-404">1</span></span></td>
<td><span data-ttu-id="bd747-405">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-405">10001</span></span></td>
<td><span data-ttu-id="bd747-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="bd747-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="bd747-407">10,00</span><span class="sxs-lookup"><span data-stu-id="bd747-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="bd747-408">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bd747-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bd747-409">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bd747-409">Journal</span></span></th>
<th><span data-ttu-id="bd747-410">Type de journal</span><span class="sxs-lookup"><span data-stu-id="bd747-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="bd747-411">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="bd747-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="bd747-412">Version</span><span class="sxs-lookup"><span data-stu-id="bd747-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-413">00003</span><span class="sxs-lookup"><span data-stu-id="bd747-413">00003</span></span></td>
<td><span data-ttu-id="bd747-414">Journal de calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="bd747-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="bd747-415">Exercice</span><span class="sxs-lookup"><span data-stu-id="bd747-415">Fiscal</span></span></td>
<td><span data-ttu-id="bd747-416">2017</span><span class="sxs-lookup"><span data-stu-id="bd747-416">2017</span></span></td>
<td><span data-ttu-id="bd747-417">Période 1</span><span class="sxs-lookup"><span data-stu-id="bd747-417">Period 1</span></span></td>
<td><span data-ttu-id="bd747-418">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="bd747-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="bd747-419">Entrées du journal (pour le calcul du taux de frais généraux)</span><span class="sxs-lookup"><span data-stu-id="bd747-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bd747-420">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bd747-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-421">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-421">Cost object</span></span></th>
<th><span data-ttu-id="bd747-422">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bd747-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-423">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="bd747-424">Proj 1</span></span></td>
<td><span data-ttu-id="bd747-425">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="bd747-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="bd747-426">3,00</span><span class="sxs-lookup"><span data-stu-id="bd747-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-427">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="bd747-428">Proj 2</span></span></td>
<td><span data-ttu-id="bd747-429">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="bd747-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="bd747-430">1,00</span><span class="sxs-lookup"><span data-stu-id="bd747-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="bd747-431">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-432">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-433">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-433">Cost element</span></span></th>
<th><span data-ttu-id="bd747-434">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-434">Cost behavior</span></span></th>
<th><span data-ttu-id="bd747-435">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-435">Amount</span></span></th>
<th><span data-ttu-id="bd747-436">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bd747-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="bd747-437">CC0001</span></span></td>
<td><span data-ttu-id="bd747-438">RH</span><span class="sxs-lookup"><span data-stu-id="bd747-438">HR</span></span></td>
<td><span data-ttu-id="bd747-439">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-439">10001</span></span></td>
<td><span data-ttu-id="bd747-440">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-440">Electricity</span></span></td>
<td><span data-ttu-id="bd747-441">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-441">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="bd747-442">-30.00</span></span></td>
<td><span data-ttu-id="bd747-443">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="bd747-444">Proj 1</span></span></td>
<td><span data-ttu-id="bd747-445">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="bd747-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="bd747-446">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-446">10001</span></span></td>
<td><span data-ttu-id="bd747-447">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-447">Electricity</span></span></td>
<td><span data-ttu-id="bd747-448">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-448">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-449">30,00</span><span class="sxs-lookup"><span data-stu-id="bd747-449">30.00</span></span></td>
<td><span data-ttu-id="bd747-450">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-451">CC001</span><span class="sxs-lookup"><span data-stu-id="bd747-451">CC001</span></span></td>
<td><span data-ttu-id="bd747-452">RH</span><span class="sxs-lookup"><span data-stu-id="bd747-452">HR</span></span></td>
<td><span data-ttu-id="bd747-453">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-453">10001</span></span></td>
<td><span data-ttu-id="bd747-454">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-454">Electricity</span></span></td>
<td><span data-ttu-id="bd747-455">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-455">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="bd747-456">-10.00</span></span></td>
<td><span data-ttu-id="bd747-457">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="bd747-458">Proj 2</span></span></td>
<td><span data-ttu-id="bd747-459">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="bd747-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="bd747-460">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-460">10001</span></span></td>
<td><span data-ttu-id="bd747-461">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-461">Electricity</span></span></td>
<td><span data-ttu-id="bd747-462">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-462">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-463">10.00</span><span class="sxs-lookup"><span data-stu-id="bd747-463">10.00</span></span></td>
<td><span data-ttu-id="bd747-464">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-465">Pour plus d’informations, voir [Exécuter le calcul des frais généraux](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="bd747-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="bd747-466">Étape 4 : Traiter le calcul de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="bd747-467">La répartition est utilisée pour affecter le solde d’un objet de coût à d’autres objets de coût en appliquant une base de répartition.</span><span class="sxs-lookup"><span data-stu-id="bd747-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="bd747-468">Finance prend en charge la méthode de répartition réciproque.</span><span class="sxs-lookup"><span data-stu-id="bd747-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="bd747-469">Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés.</span><span class="sxs-lookup"><span data-stu-id="bd747-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="bd747-470">Le système détermine automatiquement l’ordre correct selon lequel exécuter les répartitions.</span><span class="sxs-lookup"><span data-stu-id="bd747-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="bd747-471">Le solde d’un objet de coût est réparti par une seule base de répartition.</span><span class="sxs-lookup"><span data-stu-id="bd747-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="bd747-472">Les répartitions entre plusieurs dimensions d’objets de coût et leurs membres respectifs sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="bd747-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="bd747-473">L’ordre de répartition est contrôlé par l’unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="bd747-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="bd747-474">[![Méthode réciproque](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="bd747-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="bd747-475">Définir la répartition de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-475">Define the cost allocation</span></span>

<span data-ttu-id="bd747-476">Voici un exemple simple expliquant comment suivre le flux du coût.</span><span class="sxs-lookup"><span data-stu-id="bd747-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="bd747-477">L’objet de coût CC001 HR contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="bd747-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="bd747-478">Un membre de dimension statistique nommé Services HR est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="bd747-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-479">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-479">Cost object</span></span></th>
<th><span data-ttu-id="bd747-480">Services HR</span><span class="sxs-lookup"><span data-stu-id="bd747-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-481">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-481">CC002</span></span></td>
<td><span data-ttu-id="bd747-482">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-482">Finance</span></span></td>
<td><span data-ttu-id="bd747-483">35</span><span class="sxs-lookup"><span data-stu-id="bd747-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-484">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-484">CC003</span></span></td>
<td><span data-ttu-id="bd747-485">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-485">Assembly</span></span></td>
<td><span data-ttu-id="bd747-486">55</span><span class="sxs-lookup"><span data-stu-id="bd747-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-487">CC004</span><span class="sxs-lookup"><span data-stu-id="bd747-487">CC004</span></span></td>
<td><span data-ttu-id="bd747-488">Emballage</span><span class="sxs-lookup"><span data-stu-id="bd747-488">Packaging</span></span></td>
<td><span data-ttu-id="bd747-489">10</span><span class="sxs-lookup"><span data-stu-id="bd747-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-490">L’objet de coût CC002 Finance contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="bd747-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="bd747-491">Un membre de dimension statistique nommé Services Finance est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="bd747-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-492">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-492">Cost object</span></span></th>
<th><span data-ttu-id="bd747-493">Services Finance</span><span class="sxs-lookup"><span data-stu-id="bd747-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-494">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-494">CC003</span></span></td>
<td><span data-ttu-id="bd747-495">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-495">Assembly</span></span></td>
<td><span data-ttu-id="bd747-496">65</span><span class="sxs-lookup"><span data-stu-id="bd747-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-497">CC004</span><span class="sxs-lookup"><span data-stu-id="bd747-497">CC004</span></span></td>
<td><span data-ttu-id="bd747-498">Emballage</span><span class="sxs-lookup"><span data-stu-id="bd747-498">Packaging</span></span></td>
<td><span data-ttu-id="bd747-499">35</span><span class="sxs-lookup"><span data-stu-id="bd747-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-500">L’objet de coût CC003 Assemblage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="bd747-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="bd747-501">Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="bd747-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-502">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-502">Cost object</span></span></th>
<th><span data-ttu-id="bd747-503">Services Assemblage (heures)</span><span class="sxs-lookup"><span data-stu-id="bd747-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-504">Prod 1</span></span></td>
<td><span data-ttu-id="bd747-505">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-505">Product 1</span></span></td>
<td><span data-ttu-id="bd747-506">60</span><span class="sxs-lookup"><span data-stu-id="bd747-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-507">Prod 2</span></span></td>
<td><span data-ttu-id="bd747-508">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bd747-508">Product 2</span></span></td>
<td><span data-ttu-id="bd747-509">20</span><span class="sxs-lookup"><span data-stu-id="bd747-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-510">L’objet de coût CC004 Emballage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="bd747-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="bd747-511">Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="bd747-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-512">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-512">Cost object</span></span></th>
<th><span data-ttu-id="bd747-513">Services Emballage (heures)</span><span class="sxs-lookup"><span data-stu-id="bd747-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-514">Prod 1</span></span></td>
<td><span data-ttu-id="bd747-515">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-515">Product 1</span></span></td>
<td><span data-ttu-id="bd747-516">80</span><span class="sxs-lookup"><span data-stu-id="bd747-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-517">Prod 2</span></span></td>
<td><span data-ttu-id="bd747-518">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bd747-518">Product 2</span></span></td>
<td><span data-ttu-id="bd747-519">15</span><span class="sxs-lookup"><span data-stu-id="bd747-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="bd747-520">Les mesures statistiques telles que les heures de production qu’un produit consomme peuvent être dérivées des données sources.</span><span class="sxs-lookup"><span data-stu-id="bd747-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="bd747-521">Pour plus d’informations, voir [Modèle de fournisseur de mesures statistiques](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="bd747-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="bd747-522">Le tableau suivant présente le résultat lorsque les services RH sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="bd747-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-523">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-523">Cost object</span></span></th>
<th><span data-ttu-id="bd747-524">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bd747-524">Magnitude</span></span></th>
<th><span data-ttu-id="bd747-525">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bd747-525">Allocation factor</span></span></th>
<th><span data-ttu-id="bd747-526">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-526">Amount</span></span></th>
<th><span data-ttu-id="bd747-527">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-528">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-528">CC002</span></span></td>
<td><span data-ttu-id="bd747-529">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-529">Finance</span></span></td>
<td><span data-ttu-id="bd747-530">35</span><span class="sxs-lookup"><span data-stu-id="bd747-530">35</span></span></td>
<td><span data-ttu-id="bd747-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="bd747-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="bd747-532">175.00</span><span class="sxs-lookup"><span data-stu-id="bd747-532">175.00</span></span></td>
<td><span data-ttu-id="bd747-533">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-534">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-534">CC003</span></span></td>
<td><span data-ttu-id="bd747-535">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-535">Assembly</span></span></td>
<td><span data-ttu-id="bd747-536">55</span><span class="sxs-lookup"><span data-stu-id="bd747-536">55</span></span></td>
<td><span data-ttu-id="bd747-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="bd747-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="bd747-538">275.00</span><span class="sxs-lookup"><span data-stu-id="bd747-538">275.00</span></span></td>
<td><span data-ttu-id="bd747-539">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-540">CC004</span><span class="sxs-lookup"><span data-stu-id="bd747-540">CC004</span></span></td>
<td><span data-ttu-id="bd747-541">Emballage</span><span class="sxs-lookup"><span data-stu-id="bd747-541">Packaging</span></span></td>
<td><span data-ttu-id="bd747-542">10</span><span class="sxs-lookup"><span data-stu-id="bd747-542">10</span></span></td>
<td><span data-ttu-id="bd747-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="bd747-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="bd747-544">50,00</span><span class="sxs-lookup"><span data-stu-id="bd747-544">50.00</span></span></td>
<td><span data-ttu-id="bd747-545">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-546">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-546">CC002</span></span></td>
<td><span data-ttu-id="bd747-547">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-547">Finance</span></span></td>
<td><span data-ttu-id="bd747-548">35</span><span class="sxs-lookup"><span data-stu-id="bd747-548">35</span></span></td>
<td><span data-ttu-id="bd747-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="bd747-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="bd747-550">436.00</span><span class="sxs-lookup"><span data-stu-id="bd747-550">436.00</span></span></td>
<td><span data-ttu-id="bd747-551">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-552">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-552">CC003</span></span></td>
<td><span data-ttu-id="bd747-553">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-553">Assembly</span></span></td>
<td><span data-ttu-id="bd747-554">55</span><span class="sxs-lookup"><span data-stu-id="bd747-554">55</span></span></td>
<td><span data-ttu-id="bd747-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="bd747-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="bd747-556">685.14</span><span class="sxs-lookup"><span data-stu-id="bd747-556">685.14</span></span></td>
<td><span data-ttu-id="bd747-557">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-558">CC004</span><span class="sxs-lookup"><span data-stu-id="bd747-558">CC004</span></span></td>
<td><span data-ttu-id="bd747-559">Emballage</span><span class="sxs-lookup"><span data-stu-id="bd747-559">Packaging</span></span></td>
<td><span data-ttu-id="bd747-560">10</span><span class="sxs-lookup"><span data-stu-id="bd747-560">10</span></span></td>
<td><span data-ttu-id="bd747-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="bd747-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="bd747-562">124.57</span><span class="sxs-lookup"><span data-stu-id="bd747-562">124.57</span></span></td>
<td><span data-ttu-id="bd747-563">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-564">Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="bd747-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-565">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-565">Cost object</span></span></th>
<th><span data-ttu-id="bd747-566">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bd747-566">Magnitude</span></span></th>
<th><span data-ttu-id="bd747-567">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bd747-567">Allocation factor</span></span></th>
<th><span data-ttu-id="bd747-568">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-568">Amount</span></span></th>
<th><span data-ttu-id="bd747-569">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-570">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-570">CC003</span></span></td>
<td><span data-ttu-id="bd747-571">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-571">Assembly</span></span></td>
<td><span data-ttu-id="bd747-572">65</span><span class="sxs-lookup"><span data-stu-id="bd747-572">65</span></span></td>
<td><span data-ttu-id="bd747-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="bd747-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="bd747-574">438.75</span><span class="sxs-lookup"><span data-stu-id="bd747-574">438.75</span></span></td>
<td><span data-ttu-id="bd747-575">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-576">CC004</span><span class="sxs-lookup"><span data-stu-id="bd747-576">CC004</span></span></td>
<td><span data-ttu-id="bd747-577">Emballage</span><span class="sxs-lookup"><span data-stu-id="bd747-577">Packaging</span></span></td>
<td><span data-ttu-id="bd747-578">35</span><span class="sxs-lookup"><span data-stu-id="bd747-578">35</span></span></td>
<td><span data-ttu-id="bd747-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="bd747-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="bd747-580">236.25</span><span class="sxs-lookup"><span data-stu-id="bd747-580">236.25</span></span></td>
<td><span data-ttu-id="bd747-581">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-582">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-582">CC003</span></span></td>
<td><span data-ttu-id="bd747-583">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-583">Assembly</span></span></td>
<td><span data-ttu-id="bd747-584">65</span><span class="sxs-lookup"><span data-stu-id="bd747-584">65</span></span></td>
<td><span data-ttu-id="bd747-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="bd747-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="bd747-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="bd747-586">5,297.69</span></span></td>
<td><span data-ttu-id="bd747-587">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-588">CC004</span><span class="sxs-lookup"><span data-stu-id="bd747-588">CC004</span></span></td>
<td><span data-ttu-id="bd747-589">Emballage</span><span class="sxs-lookup"><span data-stu-id="bd747-589">Packaging</span></span></td>
<td><span data-ttu-id="bd747-590">35</span><span class="sxs-lookup"><span data-stu-id="bd747-590">35</span></span></td>
<td><span data-ttu-id="bd747-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="bd747-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="bd747-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="bd747-592">2,852.60</span></span></td>
<td><span data-ttu-id="bd747-593">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-594">Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="bd747-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-595">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-595">Cost object</span></span></th>
<th><span data-ttu-id="bd747-596">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bd747-596">Magnitude</span></span></th>
<th><span data-ttu-id="bd747-597">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bd747-597">Allocation factor</span></span></th>
<th><span data-ttu-id="bd747-598">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-598">Amount</span></span></th>
<th><span data-ttu-id="bd747-599">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-600">Prod 1</span></span></td>
<td><span data-ttu-id="bd747-601">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-601">Product 1</span></span></td>
<td><span data-ttu-id="bd747-602">60</span><span class="sxs-lookup"><span data-stu-id="bd747-602">60</span></span></td>
<td><span data-ttu-id="bd747-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="bd747-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="bd747-604">535.31</span><span class="sxs-lookup"><span data-stu-id="bd747-604">535.31</span></span></td>
<td><span data-ttu-id="bd747-605">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-606">Prod 2</span></span></td>
<td><span data-ttu-id="bd747-607">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bd747-607">Product 2</span></span></td>
<td><span data-ttu-id="bd747-608">20</span><span class="sxs-lookup"><span data-stu-id="bd747-608">20</span></span></td>
<td><span data-ttu-id="bd747-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="bd747-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="bd747-610">178.44</span><span class="sxs-lookup"><span data-stu-id="bd747-610">178.44</span></span></td>
<td><span data-ttu-id="bd747-611">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-612">Prod 1</span></span></td>
<td><span data-ttu-id="bd747-613">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-613">Product 1</span></span></td>
<td><span data-ttu-id="bd747-614">60</span><span class="sxs-lookup"><span data-stu-id="bd747-614">60</span></span></td>
<td><span data-ttu-id="bd747-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="bd747-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="bd747-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="bd747-616">4,487.12</span></span></td>
<td><span data-ttu-id="bd747-617">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-618">Prod 2</span></span></td>
<td><span data-ttu-id="bd747-619">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bd747-619">Product 2</span></span></td>
<td><span data-ttu-id="bd747-620">20</span><span class="sxs-lookup"><span data-stu-id="bd747-620">20</span></span></td>
<td><span data-ttu-id="bd747-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="bd747-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="bd747-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="bd747-622">1,495.71</span></span></td>
<td><span data-ttu-id="bd747-623">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bd747-624">Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="bd747-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-625">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-625">Cost object</span></span></th>
<th><span data-ttu-id="bd747-626">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bd747-626">Magnitude</span></span></th>
<th><span data-ttu-id="bd747-627">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bd747-627">Allocation factor</span></span></th>
<th><span data-ttu-id="bd747-628">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-628">Amount</span></span></th>
<th><span data-ttu-id="bd747-629">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-630">Prod 1</span></span></td>
<td><span data-ttu-id="bd747-631">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-631">Product 1</span></span></td>
<td><span data-ttu-id="bd747-632">80</span><span class="sxs-lookup"><span data-stu-id="bd747-632">80</span></span></td>
<td><span data-ttu-id="bd747-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="bd747-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="bd747-634">241.05</span><span class="sxs-lookup"><span data-stu-id="bd747-634">241.05</span></span></td>
<td><span data-ttu-id="bd747-635">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-636">Prod 2</span></span></td>
<td><span data-ttu-id="bd747-637">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bd747-637">Product 2</span></span></td>
<td><span data-ttu-id="bd747-638">15</span><span class="sxs-lookup"><span data-stu-id="bd747-638">15</span></span></td>
<td><span data-ttu-id="bd747-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="bd747-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="bd747-640">45.20</span><span class="sxs-lookup"><span data-stu-id="bd747-640">45.20</span></span></td>
<td><span data-ttu-id="bd747-641">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-642">Prod 1</span></span></td>
<td><span data-ttu-id="bd747-643">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-643">Product 1</span></span></td>
<td><span data-ttu-id="bd747-644">80</span><span class="sxs-lookup"><span data-stu-id="bd747-644">80</span></span></td>
<td><span data-ttu-id="bd747-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="bd747-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="bd747-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="bd747-646">2,507.09</span></span></td>
<td><span data-ttu-id="bd747-647">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-648">Prod 2</span></span></td>
<td><span data-ttu-id="bd747-649">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bd747-649">Product 2</span></span></td>
<td><span data-ttu-id="bd747-650">15</span><span class="sxs-lookup"><span data-stu-id="bd747-650">15</span></span></td>
<td><span data-ttu-id="bd747-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="bd747-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="bd747-652">470.08</span><span class="sxs-lookup"><span data-stu-id="bd747-652">470.08</span></span></td>
<td><span data-ttu-id="bd747-653">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="bd747-654">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="bd747-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bd747-655">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bd747-655">Journal</span></span></th>
<th><span data-ttu-id="bd747-656">Type de journal</span><span class="sxs-lookup"><span data-stu-id="bd747-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="bd747-657">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="bd747-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="bd747-658">Version</span><span class="sxs-lookup"><span data-stu-id="bd747-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-659">00004</span><span class="sxs-lookup"><span data-stu-id="bd747-659">00004</span></span></td>
<td><span data-ttu-id="bd747-660">Journal de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="bd747-661">Exercice</span><span class="sxs-lookup"><span data-stu-id="bd747-661">Fiscal</span></span></td>
<td><span data-ttu-id="bd747-662">2017</span><span class="sxs-lookup"><span data-stu-id="bd747-662">2017</span></span></td>
<td><span data-ttu-id="bd747-663">Période 1</span><span class="sxs-lookup"><span data-stu-id="bd747-663">Period 1</span></span></td>
<td><span data-ttu-id="bd747-664">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="bd747-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="bd747-665">Lignes de journal</span><span class="sxs-lookup"><span data-stu-id="bd747-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bd747-666">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bd747-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-667">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-668">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-668">Cost element</span></span></th>
<th><span data-ttu-id="bd747-669">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-669">Cost behavior</span></span></th>
<th><span data-ttu-id="bd747-670">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-671">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-672">CC001</span><span class="sxs-lookup"><span data-stu-id="bd747-672">CC001</span></span></td>
<td><span data-ttu-id="bd747-673">RH</span><span class="sxs-lookup"><span data-stu-id="bd747-673">HR</span></span></td>
<td><span data-ttu-id="bd747-674">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-674">10001</span></span></td>
<td><span data-ttu-id="bd747-675">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-675">Electricity</span></span></td>
<td><span data-ttu-id="bd747-676">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-676">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-677">500,00</span><span class="sxs-lookup"><span data-stu-id="bd747-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-678">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-679">CC001</span><span class="sxs-lookup"><span data-stu-id="bd747-679">CC001</span></span></td>
<td><span data-ttu-id="bd747-680">RH</span><span class="sxs-lookup"><span data-stu-id="bd747-680">HR</span></span></td>
<td><span data-ttu-id="bd747-681">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-681">10001</span></span></td>
<td><span data-ttu-id="bd747-682">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-682">Electricity</span></span></td>
<td><span data-ttu-id="bd747-683">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-683">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="bd747-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-685">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-686">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-686">CC002</span></span></td>
<td><span data-ttu-id="bd747-687">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-687">Finance</span></span></td>
<td><span data-ttu-id="bd747-688">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-688">10001</span></span></td>
<td><span data-ttu-id="bd747-689">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-689">Electricity</span></span></td>
<td><span data-ttu-id="bd747-690">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-690">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-691">675.00</span><span class="sxs-lookup"><span data-stu-id="bd747-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-692">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-693">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-693">CC002</span></span></td>
<td><span data-ttu-id="bd747-694">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-694">Finance</span></span></td>
<td><span data-ttu-id="bd747-695">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-695">10001</span></span></td>
<td><span data-ttu-id="bd747-696">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-696">Electricity</span></span></td>
<td><span data-ttu-id="bd747-697">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-697">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="bd747-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-699">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-700">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-700">CC003</span></span></td>
<td><span data-ttu-id="bd747-701">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-701">Assembly</span></span></td>
<td><span data-ttu-id="bd747-702">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-702">10001</span></span></td>
<td><span data-ttu-id="bd747-703">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-703">Electricity</span></span></td>
<td><span data-ttu-id="bd747-704">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-704">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-705">713.75</span><span class="sxs-lookup"><span data-stu-id="bd747-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-706">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-707">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-707">CC003</span></span></td>
<td><span data-ttu-id="bd747-708">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-708">Assembly</span></span></td>
<td><span data-ttu-id="bd747-709">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-709">10001</span></span></td>
<td><span data-ttu-id="bd747-710">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-710">Electricity</span></span></td>
<td><span data-ttu-id="bd747-711">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-711">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="bd747-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-713">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-714">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-714">CC003</span></span></td>
<td><span data-ttu-id="bd747-715">Emballage</span><span class="sxs-lookup"><span data-stu-id="bd747-715">Packaging</span></span></td>
<td><span data-ttu-id="bd747-716">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-716">10001</span></span></td>
<td><span data-ttu-id="bd747-717">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-717">Electricity</span></span></td>
<td><span data-ttu-id="bd747-718">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-718">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-719">286.25</span><span class="sxs-lookup"><span data-stu-id="bd747-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-720">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-721">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-721">CC003</span></span></td>
<td><span data-ttu-id="bd747-722">Emballage</span><span class="sxs-lookup"><span data-stu-id="bd747-722">Packaging</span></span></td>
<td><span data-ttu-id="bd747-723">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-723">10001</span></span></td>
<td><span data-ttu-id="bd747-724">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-724">Electricity</span></span></td>
<td><span data-ttu-id="bd747-725">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-725">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="bd747-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-727">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-728">Prod 1</span></span></td>
<td><span data-ttu-id="bd747-729">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-729">Product 1</span></span></td>
<td><span data-ttu-id="bd747-730">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-730">10001</span></span></td>
<td><span data-ttu-id="bd747-731">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-731">Electricity</span></span></td>
<td><span data-ttu-id="bd747-732">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-732">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-733">776.36</span><span class="sxs-lookup"><span data-stu-id="bd747-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-734">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-735">Prod 1</span></span></td>
<td><span data-ttu-id="bd747-736">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-736">Product 1</span></span></td>
<td><span data-ttu-id="bd747-737">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-737">10001</span></span></td>
<td><span data-ttu-id="bd747-738">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-738">Electricity</span></span></td>
<td><span data-ttu-id="bd747-739">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-739">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="bd747-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-741">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-742">Prod 2</span></span></td>
<td><span data-ttu-id="bd747-743">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-743">Product 1</span></span></td>
<td><span data-ttu-id="bd747-744">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-744">10001</span></span></td>
<td><span data-ttu-id="bd747-745">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-745">Electricity</span></span></td>
<td><span data-ttu-id="bd747-746">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-746">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-747">223.64</span><span class="sxs-lookup"><span data-stu-id="bd747-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-748">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="bd747-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-749">Prod 2</span></span></td>
<td><span data-ttu-id="bd747-750">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-750">Product 1</span></span></td>
<td><span data-ttu-id="bd747-751">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-751">10001</span></span></td>
<td><span data-ttu-id="bd747-752">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-752">Electricity</span></span></td>
<td><span data-ttu-id="bd747-753">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-753">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="bd747-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="bd747-755">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bd747-756">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bd747-757">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-757">Cost element</span></span></th>
<th><span data-ttu-id="bd747-758">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bd747-758">Cost behavior</span></span></th>
<th><span data-ttu-id="bd747-759">Montant</span><span class="sxs-lookup"><span data-stu-id="bd747-759">Amount</span></span></th>
<th><span data-ttu-id="bd747-760">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bd747-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bd747-761">CC001</span><span class="sxs-lookup"><span data-stu-id="bd747-761">CC001</span></span></td>
<td><span data-ttu-id="bd747-762">RH</span><span class="sxs-lookup"><span data-stu-id="bd747-762">HR</span></span></td>
<td><span data-ttu-id="bd747-763">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-763">10001</span></span></td>
<td><span data-ttu-id="bd747-764">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-764">Electricity</span></span></td>
<td><span data-ttu-id="bd747-765">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-765">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="bd747-766">-500.00</span></span></td>
<td><span data-ttu-id="bd747-767">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-768">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-768">CC002</span></span></td>
<td><span data-ttu-id="bd747-769">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-769">Finance</span></span></td>
<td><span data-ttu-id="bd747-770">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-770">10001</span></span></td>
<td><span data-ttu-id="bd747-771">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-771">Electricity</span></span></td>
<td><span data-ttu-id="bd747-772">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-772">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-773">175.00</span><span class="sxs-lookup"><span data-stu-id="bd747-773">175.00</span></span></td>
<td><span data-ttu-id="bd747-774">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-775">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-775">CC003</span></span></td>
<td><span data-ttu-id="bd747-776">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-776">Assembly</span></span></td>
<td><span data-ttu-id="bd747-777">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-777">10001</span></span></td>
<td><span data-ttu-id="bd747-778">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-778">Electricity</span></span></td>
<td><span data-ttu-id="bd747-779">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-779">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-780">275.00</span><span class="sxs-lookup"><span data-stu-id="bd747-780">275.00</span></span></td>
<td><span data-ttu-id="bd747-781">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-782">CC004</span><span class="sxs-lookup"><span data-stu-id="bd747-782">CC004</span></span></td>
<td><span data-ttu-id="bd747-783">Emballage</span><span class="sxs-lookup"><span data-stu-id="bd747-783">Packaging</span></span></td>
<td><span data-ttu-id="bd747-784">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-784">10001</span></span></td>
<td><span data-ttu-id="bd747-785">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-785">Electricity</span></span></td>
<td><span data-ttu-id="bd747-786">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-786">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-787">50,00</span><span class="sxs-lookup"><span data-stu-id="bd747-787">50,00</span></span></td>
<td><span data-ttu-id="bd747-788">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-789">CC001</span><span class="sxs-lookup"><span data-stu-id="bd747-789">CC001</span></span></td>
<td><span data-ttu-id="bd747-790">RH</span><span class="sxs-lookup"><span data-stu-id="bd747-790">HR</span></span></td>
<td><span data-ttu-id="bd747-791">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-791">10001</span></span></td>
<td><span data-ttu-id="bd747-792">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-792">Electricity</span></span></td>
<td><span data-ttu-id="bd747-793">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-793">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="bd747-794">-1,245.71</span></span></td>
<td><span data-ttu-id="bd747-795">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-796">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-796">CC002</span></span></td>
<td><span data-ttu-id="bd747-797">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-797">Finance</span></span></td>
<td><span data-ttu-id="bd747-798">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-798">10001</span></span></td>
<td><span data-ttu-id="bd747-799">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-799">Electricity</span></span></td>
<td><span data-ttu-id="bd747-800">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-800">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-801">436.00</span><span class="sxs-lookup"><span data-stu-id="bd747-801">436.00</span></span></td>
<td><span data-ttu-id="bd747-802">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-803">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-803">CC003</span></span></td>
<td><span data-ttu-id="bd747-804">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-804">Assembly</span></span></td>
<td><span data-ttu-id="bd747-805">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-805">10001</span></span></td>
<td><span data-ttu-id="bd747-806">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-806">Electricity</span></span></td>
<td><span data-ttu-id="bd747-807">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-807">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-808">685.14</span><span class="sxs-lookup"><span data-stu-id="bd747-808">685.14</span></span></td>
<td><span data-ttu-id="bd747-809">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-810">CC004</span><span class="sxs-lookup"><span data-stu-id="bd747-810">CC004</span></span></td>
<td><span data-ttu-id="bd747-811">Emballage</span><span class="sxs-lookup"><span data-stu-id="bd747-811">Packaging</span></span></td>
<td><span data-ttu-id="bd747-812">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-812">10001</span></span></td>
<td><span data-ttu-id="bd747-813">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-813">Electricity</span></span></td>
<td><span data-ttu-id="bd747-814">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-814">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-815">124.57</span><span class="sxs-lookup"><span data-stu-id="bd747-815">124.57</span></span></td>
<td><span data-ttu-id="bd747-816">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-817">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-817">CC002</span></span></td>
<td><span data-ttu-id="bd747-818">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-818">Finance</span></span></td>
<td><span data-ttu-id="bd747-819">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-819">10001</span></span></td>
<td><span data-ttu-id="bd747-820">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-820">Electricity</span></span></td>
<td><span data-ttu-id="bd747-821">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-821">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="bd747-822">-675.00</span></span></td>
<td><span data-ttu-id="bd747-823">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-824">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-824">CC003</span></span></td>
<td><span data-ttu-id="bd747-825">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-825">Assembly</span></span></td>
<td><span data-ttu-id="bd747-826">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-826">10001</span></span></td>
<td><span data-ttu-id="bd747-827">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-827">Electricity</span></span></td>
<td><span data-ttu-id="bd747-828">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-828">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-829">438.75</span><span class="sxs-lookup"><span data-stu-id="bd747-829">438.75</span></span></td>
<td><span data-ttu-id="bd747-830">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-831">CC004</span><span class="sxs-lookup"><span data-stu-id="bd747-831">CC004</span></span></td>
<td><span data-ttu-id="bd747-832">Emballage</span><span class="sxs-lookup"><span data-stu-id="bd747-832">Packaging</span></span></td>
<td><span data-ttu-id="bd747-833">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-833">10001</span></span></td>
<td><span data-ttu-id="bd747-834">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-834">Electricity</span></span></td>
<td><span data-ttu-id="bd747-835">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-835">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-836">236.25</span><span class="sxs-lookup"><span data-stu-id="bd747-836">236.25</span></span></td>
<td><span data-ttu-id="bd747-837">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-838">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-838">CC002</span></span></td>
<td><span data-ttu-id="bd747-839">Finances</span><span class="sxs-lookup"><span data-stu-id="bd747-839">Finance</span></span></td>
<td><span data-ttu-id="bd747-840">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-840">10001</span></span></td>
<td><span data-ttu-id="bd747-841">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-841">Electricity</span></span></td>
<td><span data-ttu-id="bd747-842">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-842">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="bd747-843">-8,150.29</span></span></td>
<td><span data-ttu-id="bd747-844">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-845">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-845">CC003</span></span></td>
<td><span data-ttu-id="bd747-846">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-846">Assembly</span></span></td>
<td><span data-ttu-id="bd747-847">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-847">10001</span></span></td>
<td><span data-ttu-id="bd747-848">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-848">Electricity</span></span></td>
<td><span data-ttu-id="bd747-849">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-849">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="bd747-850">5,297.69</span></span></td>
<td><span data-ttu-id="bd747-851">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-852">CC004</span><span class="sxs-lookup"><span data-stu-id="bd747-852">CC004</span></span></td>
<td><span data-ttu-id="bd747-853">Emballage</span><span class="sxs-lookup"><span data-stu-id="bd747-853">Packaging</span></span></td>
<td><span data-ttu-id="bd747-854">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-854">10001</span></span></td>
<td><span data-ttu-id="bd747-855">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-855">Electricity</span></span></td>
<td><span data-ttu-id="bd747-856">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-856">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="bd747-857">2,852.60</span></span></td>
<td><span data-ttu-id="bd747-858">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-859">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-859">CC003</span></span></td>
<td><span data-ttu-id="bd747-860">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-860">Assembly</span></span></td>
<td><span data-ttu-id="bd747-861">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-861">10001</span></span></td>
<td><span data-ttu-id="bd747-862">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-862">Electricity</span></span></td>
<td><span data-ttu-id="bd747-863">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-863">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="bd747-864">-713.75</span></span></td>
<td><span data-ttu-id="bd747-865">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-866">Prod 1</span></span></td>
<td><span data-ttu-id="bd747-867">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-867">Product 1</span></span></td>
<td><span data-ttu-id="bd747-868">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-868">10001</span></span></td>
<td><span data-ttu-id="bd747-869">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-869">Electricity</span></span></td>
<td><span data-ttu-id="bd747-870">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-870">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-871">535.31</span><span class="sxs-lookup"><span data-stu-id="bd747-871">535.31</span></span></td>
<td><span data-ttu-id="bd747-872">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-873">Prod 2</span></span></td>
<td><span data-ttu-id="bd747-874">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bd747-874">Product 2</span></span></td>
<td><span data-ttu-id="bd747-875">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-875">10001</span></span></td>
<td><span data-ttu-id="bd747-876">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-876">Electricity</span></span></td>
<td><span data-ttu-id="bd747-877">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-877">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-878">178.44</span><span class="sxs-lookup"><span data-stu-id="bd747-878">178.44</span></span></td>
<td><span data-ttu-id="bd747-879">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-880">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-880">CC003</span></span></td>
<td><span data-ttu-id="bd747-881">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-881">Assembly</span></span></td>
<td><span data-ttu-id="bd747-882">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-882">10001</span></span></td>
<td><span data-ttu-id="bd747-883">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-883">Electricity</span></span></td>
<td><span data-ttu-id="bd747-884">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-884">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="bd747-885">-5,982.83</span></span></td>
<td><span data-ttu-id="bd747-886">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-887">Prod 1</span></span></td>
<td><span data-ttu-id="bd747-888">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-888">Product 1</span></span></td>
<td><span data-ttu-id="bd747-889">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-889">10001</span></span></td>
<td><span data-ttu-id="bd747-890">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-890">Electricity</span></span></td>
<td><span data-ttu-id="bd747-891">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-891">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="bd747-892">4,487.12</span></span></td>
<td><span data-ttu-id="bd747-893">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-894">Prod 2</span></span></td>
<td><span data-ttu-id="bd747-895">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bd747-895">Product 2</span></span></td>
<td><span data-ttu-id="bd747-896">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-896">10001</span></span></td>
<td><span data-ttu-id="bd747-897">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-897">Electricity</span></span></td>
<td><span data-ttu-id="bd747-898">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-898">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="bd747-899">1,495.71</span></span></td>
<td><span data-ttu-id="bd747-900">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-901">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-901">CC003</span></span></td>
<td><span data-ttu-id="bd747-902">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-902">Assembly</span></span></td>
<td><span data-ttu-id="bd747-903">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-903">10001</span></span></td>
<td><span data-ttu-id="bd747-904">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-904">Electricity</span></span></td>
<td><span data-ttu-id="bd747-905">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-905">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="bd747-906">-286.25</span></span></td>
<td><span data-ttu-id="bd747-907">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-908">Prod 1</span></span></td>
<td><span data-ttu-id="bd747-909">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-909">Product 1</span></span></td>
<td><span data-ttu-id="bd747-910">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-910">10001</span></span></td>
<td><span data-ttu-id="bd747-911">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-911">Electricity</span></span></td>
<td><span data-ttu-id="bd747-912">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-912">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-913">241.05</span><span class="sxs-lookup"><span data-stu-id="bd747-913">241.05</span></span></td>
<td><span data-ttu-id="bd747-914">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-915">Prod 2</span></span></td>
<td><span data-ttu-id="bd747-916">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bd747-916">Product 2</span></span></td>
<td><span data-ttu-id="bd747-917">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-917">10001</span></span></td>
<td><span data-ttu-id="bd747-918">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-918">Electricity</span></span></td>
<td><span data-ttu-id="bd747-919">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-919">Fixed cost</span></span></td>
<td><span data-ttu-id="bd747-920">45.20</span><span class="sxs-lookup"><span data-stu-id="bd747-920">45.20</span></span></td>
<td><span data-ttu-id="bd747-921">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-922">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-922">CC003</span></span></td>
<td><span data-ttu-id="bd747-923">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bd747-923">Assembly</span></span></td>
<td><span data-ttu-id="bd747-924">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-924">10001</span></span></td>
<td><span data-ttu-id="bd747-925">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-925">Electricity</span></span></td>
<td><span data-ttu-id="bd747-926">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-926">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="bd747-927">-2,977.17</span></span></td>
<td><span data-ttu-id="bd747-928">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-929">Prod 1</span></span></td>
<td><span data-ttu-id="bd747-930">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bd747-930">Product 1</span></span></td>
<td><span data-ttu-id="bd747-931">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-931">10001</span></span></td>
<td><span data-ttu-id="bd747-932">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-932">Electricity</span></span></td>
<td><span data-ttu-id="bd747-933">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-933">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="bd747-934">2,507.09</span></span></td>
<td><span data-ttu-id="bd747-935">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bd747-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-936">Prod 2</span></span></td>
<td><span data-ttu-id="bd747-937">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bd747-937">Product 2</span></span></td>
<td><span data-ttu-id="bd747-938">10001</span><span class="sxs-lookup"><span data-stu-id="bd747-938">10001</span></span></td>
<td><span data-ttu-id="bd747-939">Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-939">Electricity</span></span></td>
<td><span data-ttu-id="bd747-940">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-940">Variable cost</span></span></td>
<td><span data-ttu-id="bd747-941">470.08</span><span class="sxs-lookup"><span data-stu-id="bd747-941">470.08</span></span></td>
<td><span data-ttu-id="bd747-942">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bd747-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="bd747-943">Conclusion</span><span class="sxs-lookup"><span data-stu-id="bd747-943">Conclusion</span></span>
<span data-ttu-id="bd747-944">Dans la comptabilité financière, un coût de 10 000,00 pour l’électricité est imputé sur un ID de centre de coût fictif.</span><span class="sxs-lookup"><span data-stu-id="bd747-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="bd747-945">Par conséquent, les comptables sauront que ce coût doit être affecté.</span><span class="sxs-lookup"><span data-stu-id="bd747-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="bd747-946">Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l’organisation, selon les stratégies et les règles qui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="bd747-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="bd747-947">Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="bd747-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="bd747-948">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="bd747-949">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bd747-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="bd747-950">Total</span><span class="sxs-lookup"><span data-stu-id="bd747-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="bd747-951">CC099</span><span class="sxs-lookup"><span data-stu-id="bd747-951">CC099</span></span></th>
<th><span data-ttu-id="bd747-952">CC001</span><span class="sxs-lookup"><span data-stu-id="bd747-952">CC001</span></span></th>
<th><span data-ttu-id="bd747-953">CC002</span><span class="sxs-lookup"><span data-stu-id="bd747-953">CC002</span></span></th>
<th><span data-ttu-id="bd747-954">CC003</span><span class="sxs-lookup"><span data-stu-id="bd747-954">CC003</span></span></th>
<th><span data-ttu-id="bd747-955">CC004</span><span class="sxs-lookup"><span data-stu-id="bd747-955">CC004</span></span></th>
<th><span data-ttu-id="bd747-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="bd747-956">Proj 1</span></span></th>
<th><span data-ttu-id="bd747-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="bd747-957">Proj 2</span></span></th>
<th><span data-ttu-id="bd747-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bd747-958">Prod 1</span></span></th>
<th><span data-ttu-id="bd747-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bd747-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="bd747-960">10001 Électricité</span><span class="sxs-lookup"><span data-stu-id="bd747-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="bd747-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="bd747-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="bd747-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="bd747-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="bd747-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="bd747-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="bd747-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="bd747-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="bd747-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="bd747-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="bd747-970">Non classifié</span><span class="sxs-lookup"><span data-stu-id="bd747-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-971">0,00</span><span class="sxs-lookup"><span data-stu-id="bd747-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="bd747-972">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bd747-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-973">0,00</span><span class="sxs-lookup"><span data-stu-id="bd747-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-974">0,00</span><span class="sxs-lookup"><span data-stu-id="bd747-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-975">0,00</span><span class="sxs-lookup"><span data-stu-id="bd747-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-976">0,00</span><span class="sxs-lookup"><span data-stu-id="bd747-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-977">0,00</span><span class="sxs-lookup"><span data-stu-id="bd747-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="bd747-978">776.36</span><span class="sxs-lookup"><span data-stu-id="bd747-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-979">223.64</span><span class="sxs-lookup"><span data-stu-id="bd747-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-980"><strong>1 000,00</strong></span><span class="sxs-lookup"><span data-stu-id="bd747-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="bd747-981">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bd747-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-982">000</span><span class="sxs-lookup"><span data-stu-id="bd747-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-983">0,00</span><span class="sxs-lookup"><span data-stu-id="bd747-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-984">0,00</span><span class="sxs-lookup"><span data-stu-id="bd747-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-985">0,00</span><span class="sxs-lookup"><span data-stu-id="bd747-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-986">0,00</span><span class="sxs-lookup"><span data-stu-id="bd747-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-987">30,00</span><span class="sxs-lookup"><span data-stu-id="bd747-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-988">10,00</span><span class="sxs-lookup"><span data-stu-id="bd747-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="bd747-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="bd747-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bd747-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="bd747-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="bd747-992">Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût.</span><span class="sxs-lookup"><span data-stu-id="bd747-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="bd747-993">Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="bd747-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="bd747-994">Autrement dit, les objets de coût de plus bas niveau supportent le coût.</span><span class="sxs-lookup"><span data-stu-id="bd747-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="bd747-995">Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts.</span><span class="sxs-lookup"><span data-stu-id="bd747-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="bd747-996">Pour plus d’informations, voir [Stratégie de repositionnement des coûts et calcul des frais généraux](cost-rollup.md)..</span><span class="sxs-lookup"><span data-stu-id="bd747-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



