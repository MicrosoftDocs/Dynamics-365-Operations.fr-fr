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
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 882804141a6b520e2420343958c7a6b02a7e09ae
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208845"
---
# <a name="overhead-calculation"></a><span data-ttu-id="7ad78-103">Calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="7ad78-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ad78-104">Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="7ad78-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="7ad78-105">Définition des termes</span><span class="sxs-lookup"><span data-stu-id="7ad78-105">Term definition</span></span>
---------------

<span data-ttu-id="7ad78-106">Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique.</span><span class="sxs-lookup"><span data-stu-id="7ad78-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="7ad78-107">Les frais généraux permettent essentiellement l’identification des activités rémunératrices.</span><span class="sxs-lookup"><span data-stu-id="7ad78-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="7ad78-108">Voici quelques exemples de frais généraux :</span><span class="sxs-lookup"><span data-stu-id="7ad78-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="7ad78-109">Loyer</span><span class="sxs-lookup"><span data-stu-id="7ad78-109">Rent</span></span>
-   <span data-ttu-id="7ad78-110">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-110">Electricity</span></span>
-   <span data-ttu-id="7ad78-111">Salaires administratifs</span><span class="sxs-lookup"><span data-stu-id="7ad78-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="7ad78-112">Vue d’ensemble du calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="7ad78-112">Overhead calculation overview</span></span>
<span data-ttu-id="7ad78-113">Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l’ordre correct.</span><span class="sxs-lookup"><span data-stu-id="7ad78-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="7ad78-114">Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées.</span><span class="sxs-lookup"><span data-stu-id="7ad78-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="7ad78-115">Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions.</span><span class="sxs-lookup"><span data-stu-id="7ad78-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="7ad78-116">Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable.</span><span class="sxs-lookup"><span data-stu-id="7ad78-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="7ad78-117">Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="7ad78-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="7ad78-118">L’ID de version unique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7ad78-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="7ad78-119">Type de version</span><span class="sxs-lookup"><span data-stu-id="7ad78-119">Version type</span></span>
-   <span data-ttu-id="7ad78-120">Date et heure</span><span class="sxs-lookup"><span data-stu-id="7ad78-120">Date and time</span></span>
-   <span data-ttu-id="7ad78-121">Comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="7ad78-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="7ad78-122">Exercice</span><span class="sxs-lookup"><span data-stu-id="7ad78-122">Fiscal year</span></span>
-   <span data-ttu-id="7ad78-123">Période fiscale</span><span class="sxs-lookup"><span data-stu-id="7ad78-123">Fiscal period</span></span>

<span data-ttu-id="7ad78-124">Le calcul des frais généraux est effectué indépendamment de la version.</span><span class="sxs-lookup"><span data-stu-id="7ad78-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="7ad78-125">Par conséquent, vous pouvez calculer la version de budget avant la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="7ad78-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="7ad78-126">Le calcul des frais généraux comporte quatre étapes, comme le montre l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="7ad78-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="7ad78-127">Dans chaque étape, un en-tête de journal avec des entrées de journal est créé.</span><span class="sxs-lookup"><span data-stu-id="7ad78-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="7ad78-128">Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul.</span><span class="sxs-lookup"><span data-stu-id="7ad78-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="7ad78-129">Les stratégies et les règles s’appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie.</span><span class="sxs-lookup"><span data-stu-id="7ad78-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="7ad78-130">Par conséquent, vous disposez toujours d’une traçabilité complète.</span><span class="sxs-lookup"><span data-stu-id="7ad78-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="7ad78-131">[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="7ad78-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="7ad78-132">Calculer et affecter les frais généraux Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="7ad78-133">Dans la comptabilité financière, certaines coûts, tels que l’électricité, sont enregistrés comme montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="7ad78-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="7ad78-134">Par conséquent, l’analyse détaillée n’est pas fournie pour le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="7ad78-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="7ad78-135">Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l’organisation, les coûts doivent suivre les unités organisationnelles.</span><span class="sxs-lookup"><span data-stu-id="7ad78-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="7ad78-136">Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste.</span><span class="sxs-lookup"><span data-stu-id="7ad78-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="7ad78-137">Dans la comptabilité, le coût de l’électricité peut être validé comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="7ad78-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7ad78-138">Date comptable</span><span class="sxs-lookup"><span data-stu-id="7ad78-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-139">Centre de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-140">Compte principal</span><span class="sxs-lookup"><span data-stu-id="7ad78-140">Main account</span></span></th>
<th><span data-ttu-id="7ad78-141">Montant en devise comptable</span><span class="sxs-lookup"><span data-stu-id="7ad78-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-142">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="7ad78-143">CC099</span><span class="sxs-lookup"><span data-stu-id="7ad78-143">CC099</span></span></td>
<td><span data-ttu-id="7ad78-144">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="7ad78-144">Default cost center</span></span></td>
<td><span data-ttu-id="7ad78-145">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-145">10001</span></span></td>
<td><span data-ttu-id="7ad78-146">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-146">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="7ad78-148">Étape 1 : Traiter le calcul du comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="7ad78-149">Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="7ad78-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="7ad78-150">Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.</span><span class="sxs-lookup"><span data-stu-id="7ad78-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="7ad78-151">Définir la règle de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-151">Define the cost behavior rule</span></span>

<span data-ttu-id="7ad78-152">Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation.</span><span class="sxs-lookup"><span data-stu-id="7ad78-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="7ad78-153">Les factures d’électricité correspondent souvent à cette définition.</span><span class="sxs-lookup"><span data-stu-id="7ad78-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="7ad78-154">Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH).</span><span class="sxs-lookup"><span data-stu-id="7ad78-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="7ad78-155">Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :</span><span class="sxs-lookup"><span data-stu-id="7ad78-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="7ad78-156">Montant fixe 1 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="7ad78-157">0 &lt;= 1 000,00 = Fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="7ad78-158">1 000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="7ad78-159">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="7ad78-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7ad78-160">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="7ad78-160">Journal</span></span></th>
<th><span data-ttu-id="7ad78-161">Type de journal</span><span class="sxs-lookup"><span data-stu-id="7ad78-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="7ad78-162">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="7ad78-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="7ad78-163">Version</span><span class="sxs-lookup"><span data-stu-id="7ad78-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-164">00001</span><span class="sxs-lookup"><span data-stu-id="7ad78-164">00001</span></span></td>
<td><span data-ttu-id="7ad78-165">Journal de calcul de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="7ad78-166">Exercice</span><span class="sxs-lookup"><span data-stu-id="7ad78-166">Fiscal</span></span></td>
<td><span data-ttu-id="7ad78-167">2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-167">2017</span></span></td>
<td><span data-ttu-id="7ad78-168">Période 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-168">Period 1</span></span></td>
<td><span data-ttu-id="7ad78-169">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="7ad78-170">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="7ad78-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7ad78-171">Date comptable</span><span class="sxs-lookup"><span data-stu-id="7ad78-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-172">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-173">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-173">Cost element</span></span></th>
<th><span data-ttu-id="7ad78-174">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-174">Cost behavior</span></span></th>
<th><span data-ttu-id="7ad78-175">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-176">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="7ad78-177">CC099</span><span class="sxs-lookup"><span data-stu-id="7ad78-177">CC099</span></span></td>
<td><span data-ttu-id="7ad78-178">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="7ad78-178">Default cost center</span></span></td>
<td><span data-ttu-id="7ad78-179">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-179">10001</span></span></td>
<td><span data-ttu-id="7ad78-180">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-180">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-181">Non classifié</span><span class="sxs-lookup"><span data-stu-id="7ad78-181">Unclassified</span></span></td>
<td><span data-ttu-id="7ad78-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="7ad78-183">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-184">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-185">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-185">Cost element</span></span></th>
<th><span data-ttu-id="7ad78-186">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-186">Cost behavior</span></span></th>
<th><span data-ttu-id="7ad78-187">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-187">Amount</span></span></th>
<th><span data-ttu-id="7ad78-188">Date comptable</span><span class="sxs-lookup"><span data-stu-id="7ad78-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-189">CC099</span><span class="sxs-lookup"><span data-stu-id="7ad78-189">CC099</span></span></td>
<td><span data-ttu-id="7ad78-190">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="7ad78-190">Default cost center</span></span></td>
<td><span data-ttu-id="7ad78-191">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-191">10001</span></span></td>
<td><span data-ttu-id="7ad78-192">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-192">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-193">Non classifié</span><span class="sxs-lookup"><span data-stu-id="7ad78-193">Unclassified</span></span></td>
<td><span data-ttu-id="7ad78-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-194">10,000.00</span></span></td>
<td><span data-ttu-id="7ad78-195">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-196">CC099</span><span class="sxs-lookup"><span data-stu-id="7ad78-196">CC099</span></span></td>
<td><span data-ttu-id="7ad78-197">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="7ad78-197">Default cost center</span></span></td>
<td><span data-ttu-id="7ad78-198">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-198">10001</span></span></td>
<td><span data-ttu-id="7ad78-199">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-199">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-200">Non classifié</span><span class="sxs-lookup"><span data-stu-id="7ad78-200">Unclassified</span></span></td>
<td><span data-ttu-id="7ad78-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-201">-10,000.00</span></span></td>
<td><span data-ttu-id="7ad78-202">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-203">CC099</span><span class="sxs-lookup"><span data-stu-id="7ad78-203">CC099</span></span></td>
<td><span data-ttu-id="7ad78-204">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="7ad78-204">Default cost center</span></span></td>
<td><span data-ttu-id="7ad78-205">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-205">10001</span></span></td>
<td><span data-ttu-id="7ad78-206">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-206">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-207">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-207">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-208">1,000.00</span></span></td>
<td><span data-ttu-id="7ad78-209">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-210">CC099</span><span class="sxs-lookup"><span data-stu-id="7ad78-210">CC099</span></span></td>
<td><span data-ttu-id="7ad78-211">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="7ad78-211">Default cost center</span></span></td>
<td><span data-ttu-id="7ad78-212">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-212">10001</span></span></td>
<td><span data-ttu-id="7ad78-213">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-213">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-214">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-214">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-215">9 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-215">9,000.00</span></span></td>
<td><span data-ttu-id="7ad78-216">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-217">Pour plus d’informations, voir [Créer et affecter une stratégie de comportement de coûts à une unité de contrôle des coûts](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="7ad78-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="7ad78-218">Étape 2 : Traiter le calcul de distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="7ad78-219">La distribution des coûts est utilisée pour redistribuer le coût d’un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée.</span><span class="sxs-lookup"><span data-stu-id="7ad78-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="7ad78-220">La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l’élément de coût principal du coût d’origine.</span><span class="sxs-lookup"><span data-stu-id="7ad78-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="7ad78-221">Définir la règle de distribution de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-221">Define the cost distribution rule</span></span>

<span data-ttu-id="7ad78-222">Dans la comptabilité financière, les coûts d’électricité sont souvent enregistrés comme un montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="7ad78-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="7ad78-223">Dans le Contrôle de gestion, cette approche n’est pas assez détaillée.</span><span class="sxs-lookup"><span data-stu-id="7ad78-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="7ad78-224">Le coût variable doit être attribué aux différents objets de coûts sur une base juste.</span><span class="sxs-lookup"><span data-stu-id="7ad78-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="7ad78-225">La base de répartition la plus logique est la consommation de l’électricité (KWH).</span><span class="sxs-lookup"><span data-stu-id="7ad78-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="7ad78-226">Un membre de dimension statistique nommé Électricité est créé, et la consommation d’électricité est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="7ad78-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="7ad78-227">Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="7ad78-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-228">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-228">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="7ad78-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-230">CC001</span><span class="sxs-lookup"><span data-stu-id="7ad78-230">CC001</span></span></td>
<td><span data-ttu-id="7ad78-231">RH</span><span class="sxs-lookup"><span data-stu-id="7ad78-231">HR</span></span></td>
<td><span data-ttu-id="7ad78-232">1 000</span><span class="sxs-lookup"><span data-stu-id="7ad78-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-233">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-233">CC002</span></span></td>
<td><span data-ttu-id="7ad78-234">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-234">Finance</span></span></td>
<td><span data-ttu-id="7ad78-235">6 000</span><span class="sxs-lookup"><span data-stu-id="7ad78-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-236">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-236">CC003</span></span></td>
<td><span data-ttu-id="7ad78-237">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-237">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-238">0</span><span class="sxs-lookup"><span data-stu-id="7ad78-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-239">Le tableau suivant illustre le résultat lorsque la consommation d’électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="7ad78-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-240">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-240">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-241">Ampleur</span><span class="sxs-lookup"><span data-stu-id="7ad78-241">Magnitude</span></span></th>
<th><span data-ttu-id="7ad78-242">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="7ad78-242">Allocation factor</span></span></th>
<th><span data-ttu-id="7ad78-243">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-244">CC001</span><span class="sxs-lookup"><span data-stu-id="7ad78-244">CC001</span></span></td>
<td><span data-ttu-id="7ad78-245">RH</span><span class="sxs-lookup"><span data-stu-id="7ad78-245">HR</span></span></td>
<td><span data-ttu-id="7ad78-246">1 000</span><span class="sxs-lookup"><span data-stu-id="7ad78-246">1,000</span></span></td>
<td><span data-ttu-id="7ad78-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="7ad78-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="7ad78-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-249">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-249">CC002</span></span></td>
<td><span data-ttu-id="7ad78-250">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-250">Finance</span></span></td>
<td><span data-ttu-id="7ad78-251">6 000</span><span class="sxs-lookup"><span data-stu-id="7ad78-251">6,000</span></span></td>
<td><span data-ttu-id="7ad78-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="7ad78-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="7ad78-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-254">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-254">CC003</span></span></td>
<td><span data-ttu-id="7ad78-255">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-255">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-256">0</span><span class="sxs-lookup"><span data-stu-id="7ad78-256">0</span></span></td>
<td><span data-ttu-id="7ad78-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="7ad78-258">0,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-259">Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l’électricité.</span><span class="sxs-lookup"><span data-stu-id="7ad78-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="7ad78-260">Vous pouvez obtenir ce résultat à l’aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d’électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="7ad78-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-261">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-261">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-262">Formule</span><span class="sxs-lookup"><span data-stu-id="7ad78-262">Formula</span></span></th>
<th><span data-ttu-id="7ad78-263">Ampleur</span><span class="sxs-lookup"><span data-stu-id="7ad78-263">Magnitude</span></span></th>
<th><span data-ttu-id="7ad78-264">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="7ad78-264">Allocation factor</span></span></th>
<th><span data-ttu-id="7ad78-265">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-266">CC001</span><span class="sxs-lookup"><span data-stu-id="7ad78-266">CC001</span></span></td>
<td><span data-ttu-id="7ad78-267">RH</span><span class="sxs-lookup"><span data-stu-id="7ad78-267">HR</span></span></td>
<td><span data-ttu-id="7ad78-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="7ad78-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="7ad78-269">1</span><span class="sxs-lookup"><span data-stu-id="7ad78-269">1</span></span></td>
<td><span data-ttu-id="7ad78-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="7ad78-271">500,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-272">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-272">CC002</span></span></td>
<td><span data-ttu-id="7ad78-273">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-273">Finance</span></span></td>
<td><span data-ttu-id="7ad78-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="7ad78-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="7ad78-275">1</span><span class="sxs-lookup"><span data-stu-id="7ad78-275">1</span></span></td>
<td><span data-ttu-id="7ad78-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="7ad78-277">500,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-278">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-278">CC003</span></span></td>
<td><span data-ttu-id="7ad78-279">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-279">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="7ad78-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="7ad78-281">0</span><span class="sxs-lookup"><span data-stu-id="7ad78-281">0</span></span></td>
<td><span data-ttu-id="7ad78-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="7ad78-283">0,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="7ad78-284">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="7ad78-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7ad78-285">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="7ad78-285">Journal</span></span></th>
<th><span data-ttu-id="7ad78-286">Type de journal</span><span class="sxs-lookup"><span data-stu-id="7ad78-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="7ad78-287">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="7ad78-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="7ad78-288">Version</span><span class="sxs-lookup"><span data-stu-id="7ad78-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-289">00002</span><span class="sxs-lookup"><span data-stu-id="7ad78-289">00002</span></span></td>
<td><span data-ttu-id="7ad78-290">Journal de calcul de la distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="7ad78-291">Exercice</span><span class="sxs-lookup"><span data-stu-id="7ad78-291">Fiscal</span></span></td>
<td><span data-ttu-id="7ad78-292">2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-292">2017</span></span></td>
<td><span data-ttu-id="7ad78-293">Période 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-293">Period 1</span></span></td>
<td><span data-ttu-id="7ad78-294">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="7ad78-295">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="7ad78-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7ad78-296">Date comptable</span><span class="sxs-lookup"><span data-stu-id="7ad78-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-297">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-298">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-298">Cost element</span></span></th>
<th><span data-ttu-id="7ad78-299">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-299">Cost behavior</span></span></th>
<th><span data-ttu-id="7ad78-300">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-301">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-302">CC099</span><span class="sxs-lookup"><span data-stu-id="7ad78-302">CC099</span></span></td>
<td><span data-ttu-id="7ad78-303">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="7ad78-303">Default cost center</span></span></td>
<td><span data-ttu-id="7ad78-304">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-304">10001</span></span></td>
<td><span data-ttu-id="7ad78-305">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-305">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-306">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-306">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-308">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-309">CC099</span><span class="sxs-lookup"><span data-stu-id="7ad78-309">CC099</span></span></td>
<td><span data-ttu-id="7ad78-310">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="7ad78-310">Default cost center</span></span></td>
<td><span data-ttu-id="7ad78-311">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-311">10001</span></span></td>
<td><span data-ttu-id="7ad78-312">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-312">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-313">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-313">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-314">9 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="7ad78-315">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-316">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-317">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-317">Cost element</span></span></th>
<th><span data-ttu-id="7ad78-318">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-318">Cost behavior</span></span></th>
<th><span data-ttu-id="7ad78-319">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-319">Amount</span></span></th>
<th><span data-ttu-id="7ad78-320">Date comptable</span><span class="sxs-lookup"><span data-stu-id="7ad78-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-321">CC099</span><span class="sxs-lookup"><span data-stu-id="7ad78-321">CC099</span></span></td>
<td><span data-ttu-id="7ad78-322">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="7ad78-322">Default cost center</span></span></td>
<td><span data-ttu-id="7ad78-323">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-323">10001</span></span></td>
<td><span data-ttu-id="7ad78-324">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-324">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-325">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-325">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-326">-1,000.00</span></span></td>
<td><span data-ttu-id="7ad78-327">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-328">CC001</span><span class="sxs-lookup"><span data-stu-id="7ad78-328">CC001</span></span></td>
<td><span data-ttu-id="7ad78-329">RH</span><span class="sxs-lookup"><span data-stu-id="7ad78-329">HR</span></span></td>
<td><span data-ttu-id="7ad78-330">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-330">10001</span></span></td>
<td><span data-ttu-id="7ad78-331">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-331">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-332">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-332">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-333">500,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-333">500.00</span></span></td>
<td><span data-ttu-id="7ad78-334">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-335">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-335">CC002</span></span></td>
<td><span data-ttu-id="7ad78-336">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-336">Finance</span></span></td>
<td><span data-ttu-id="7ad78-337">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-337">10001</span></span></td>
<td><span data-ttu-id="7ad78-338">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-338">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-339">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-339">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-340">500,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-340">500.00</span></span></td>
<td><span data-ttu-id="7ad78-341">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-342">CC099</span><span class="sxs-lookup"><span data-stu-id="7ad78-342">CC099</span></span></td>
<td><span data-ttu-id="7ad78-343">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="7ad78-343">Default cost center</span></span></td>
<td><span data-ttu-id="7ad78-344">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-344">10001</span></span></td>
<td><span data-ttu-id="7ad78-345">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-345">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-346">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-346">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-347">-9,000.00</span></span></td>
<td><span data-ttu-id="7ad78-348">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-349">CC001</span><span class="sxs-lookup"><span data-stu-id="7ad78-349">CC001</span></span></td>
<td><span data-ttu-id="7ad78-350">RH</span><span class="sxs-lookup"><span data-stu-id="7ad78-350">HR</span></span></td>
<td><span data-ttu-id="7ad78-351">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-351">10001</span></span></td>
<td><span data-ttu-id="7ad78-352">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-352">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-353">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-353">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="7ad78-354">1,285.71</span></span></td>
<td><span data-ttu-id="7ad78-355">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-356">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-356">CC002</span></span></td>
<td><span data-ttu-id="7ad78-357">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-357">Finance</span></span></td>
<td><span data-ttu-id="7ad78-358">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-358">10001</span></span></td>
<td><span data-ttu-id="7ad78-359">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-359">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-360">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-360">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="7ad78-361">7,714.29</span></span></td>
<td><span data-ttu-id="7ad78-362">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-363">Pour plus d’informations, voir [Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="7ad78-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="7ad78-364">Étape 3 : Traitement du calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="7ad78-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="7ad78-365">Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût.</span><span class="sxs-lookup"><span data-stu-id="7ad78-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="7ad78-366">Les frais sont basés sur un taux de coût prédéterminé et l’ampleur de la base d’affectation de répartition.</span><span class="sxs-lookup"><span data-stu-id="7ad78-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="7ad78-367">Définition du taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="7ad78-367">Define the overhead rate</span></span>

<span data-ttu-id="7ad78-368">L’objet de coût CC001 HR contribue à un ensemble de projets internes.</span><span class="sxs-lookup"><span data-stu-id="7ad78-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="7ad78-369">Un membre de dimension statistique nommé Projets HR est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="7ad78-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-370">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-370">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-371">Heures</span><span class="sxs-lookup"><span data-stu-id="7ad78-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-372">Proj 1</span></span></td>
<td><span data-ttu-id="7ad78-373">Projet 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-373">Project 1</span></span></td>
<td><span data-ttu-id="7ad78-374">3</span><span class="sxs-lookup"><span data-stu-id="7ad78-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-375">Proj 2</span></span></td>
<td><span data-ttu-id="7ad78-376">Projet 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-376">Project 2</span></span></td>
<td><span data-ttu-id="7ad78-377">1</span><span class="sxs-lookup"><span data-stu-id="7ad78-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-378">Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.</span><span class="sxs-lookup"><span data-stu-id="7ad78-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-379">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-379">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-380">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-380">Cost element</span></span></th>
<th><span data-ttu-id="7ad78-381">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-381">Cost behavior</span></span></th>
<th><span data-ttu-id="7ad78-382">Unités</span><span class="sxs-lookup"><span data-stu-id="7ad78-382">Units</span></span></th>
<th><span data-ttu-id="7ad78-383">Taux</span><span class="sxs-lookup"><span data-stu-id="7ad78-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-384">CC001</span><span class="sxs-lookup"><span data-stu-id="7ad78-384">CC001</span></span></td>
<td><span data-ttu-id="7ad78-385">RH</span><span class="sxs-lookup"><span data-stu-id="7ad78-385">HR</span></span></td>
<td><span data-ttu-id="7ad78-386">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-386">10001</span></span></td>
<td><span data-ttu-id="7ad78-387">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-387">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-388">1</span><span class="sxs-lookup"><span data-stu-id="7ad78-388">1</span></span></td>
<td><span data-ttu-id="7ad78-389">10</span><span class="sxs-lookup"><span data-stu-id="7ad78-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-390">Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="7ad78-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-391">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-391">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-392">Ampleur</span><span class="sxs-lookup"><span data-stu-id="7ad78-392">Magnitude</span></span></th>
<th><span data-ttu-id="7ad78-393">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-393">Cost element</span></span></th>
<th><span data-ttu-id="7ad78-394">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="7ad78-394">Allocation factor</span></span></th>
<th><span data-ttu-id="7ad78-395">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-396">Proj 1</span></span></td>
<td><span data-ttu-id="7ad78-397">Projet 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-397">Project 1</span></span></td>
<td><span data-ttu-id="7ad78-398">3</span><span class="sxs-lookup"><span data-stu-id="7ad78-398">3</span></span></td>
<td><span data-ttu-id="7ad78-399">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-399">10001</span></span></td>
<td><span data-ttu-id="7ad78-400">(3 ÷ 1) × 10m00</span><span class="sxs-lookup"><span data-stu-id="7ad78-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="7ad78-401">30,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-402">Proj 2</span></span></td>
<td><span data-ttu-id="7ad78-403">Projet 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-403">Project 2</span></span></td>
<td><span data-ttu-id="7ad78-404">1</span><span class="sxs-lookup"><span data-stu-id="7ad78-404">1</span></span></td>
<td><span data-ttu-id="7ad78-405">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-405">10001</span></span></td>
<td><span data-ttu-id="7ad78-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="7ad78-407">10,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="7ad78-408">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="7ad78-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7ad78-409">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="7ad78-409">Journal</span></span></th>
<th><span data-ttu-id="7ad78-410">Type de journal</span><span class="sxs-lookup"><span data-stu-id="7ad78-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="7ad78-411">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="7ad78-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="7ad78-412">Version</span><span class="sxs-lookup"><span data-stu-id="7ad78-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-413">00003</span><span class="sxs-lookup"><span data-stu-id="7ad78-413">00003</span></span></td>
<td><span data-ttu-id="7ad78-414">Journal de calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="7ad78-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="7ad78-415">Exercice</span><span class="sxs-lookup"><span data-stu-id="7ad78-415">Fiscal</span></span></td>
<td><span data-ttu-id="7ad78-416">2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-416">2017</span></span></td>
<td><span data-ttu-id="7ad78-417">Période 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-417">Period 1</span></span></td>
<td><span data-ttu-id="7ad78-418">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="7ad78-419">Entrées du journal (pour le calcul du taux de frais généraux)</span><span class="sxs-lookup"><span data-stu-id="7ad78-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7ad78-420">Date comptable</span><span class="sxs-lookup"><span data-stu-id="7ad78-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-421">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-421">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-422">Ampleur</span><span class="sxs-lookup"><span data-stu-id="7ad78-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-423">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-424">Proj 1</span></span></td>
<td><span data-ttu-id="7ad78-425">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="7ad78-426">3,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-427">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-428">Proj 2</span></span></td>
<td><span data-ttu-id="7ad78-429">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="7ad78-430">1,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="7ad78-431">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-432">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-433">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-433">Cost element</span></span></th>
<th><span data-ttu-id="7ad78-434">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-434">Cost behavior</span></span></th>
<th><span data-ttu-id="7ad78-435">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-435">Amount</span></span></th>
<th><span data-ttu-id="7ad78-436">Date comptable</span><span class="sxs-lookup"><span data-stu-id="7ad78-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="7ad78-437">CC0001</span></span></td>
<td><span data-ttu-id="7ad78-438">RH</span><span class="sxs-lookup"><span data-stu-id="7ad78-438">HR</span></span></td>
<td><span data-ttu-id="7ad78-439">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-439">10001</span></span></td>
<td><span data-ttu-id="7ad78-440">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-440">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-441">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-441">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-442">-30.00</span></span></td>
<td><span data-ttu-id="7ad78-443">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-444">Proj 1</span></span></td>
<td><span data-ttu-id="7ad78-445">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="7ad78-446">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-446">10001</span></span></td>
<td><span data-ttu-id="7ad78-447">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-447">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-448">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-448">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-449">30,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-449">30.00</span></span></td>
<td><span data-ttu-id="7ad78-450">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-451">CC001</span><span class="sxs-lookup"><span data-stu-id="7ad78-451">CC001</span></span></td>
<td><span data-ttu-id="7ad78-452">RH</span><span class="sxs-lookup"><span data-stu-id="7ad78-452">HR</span></span></td>
<td><span data-ttu-id="7ad78-453">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-453">10001</span></span></td>
<td><span data-ttu-id="7ad78-454">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-454">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-455">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-455">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-456">-10.00</span></span></td>
<td><span data-ttu-id="7ad78-457">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-458">Proj 2</span></span></td>
<td><span data-ttu-id="7ad78-459">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="7ad78-460">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-460">10001</span></span></td>
<td><span data-ttu-id="7ad78-461">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-461">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-462">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-462">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-463">10.00</span><span class="sxs-lookup"><span data-stu-id="7ad78-463">10.00</span></span></td>
<td><span data-ttu-id="7ad78-464">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-465">Pour plus d’informations, voir [Exécuter le calcul des frais généraux](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="7ad78-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="7ad78-466">Étape 4 : Traiter le calcul de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="7ad78-467">La répartition est utilisée pour affecter le solde d’un objet de coût à d’autres objets de coût en appliquant une base de répartition.</span><span class="sxs-lookup"><span data-stu-id="7ad78-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="7ad78-468">Finance prend en charge la méthode de répartition réciproque.</span><span class="sxs-lookup"><span data-stu-id="7ad78-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="7ad78-469">Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés.</span><span class="sxs-lookup"><span data-stu-id="7ad78-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="7ad78-470">Le système détermine automatiquement l’ordre correct selon lequel exécuter les répartitions.</span><span class="sxs-lookup"><span data-stu-id="7ad78-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="7ad78-471">Le solde d’un objet de coût est réparti par une seule base de répartition.</span><span class="sxs-lookup"><span data-stu-id="7ad78-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="7ad78-472">Les répartitions entre plusieurs dimensions d’objets de coût et leurs membres respectifs sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="7ad78-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="7ad78-473">L’ordre de répartition est contrôlé par l’unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="7ad78-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="7ad78-474">[![Méthode réciproque](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="7ad78-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="7ad78-475">Définir la répartition de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-475">Define the cost allocation</span></span>

<span data-ttu-id="7ad78-476">Voici un exemple simple expliquant comment suivre le flux du coût.</span><span class="sxs-lookup"><span data-stu-id="7ad78-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="7ad78-477">L’objet de coût CC001 HR contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="7ad78-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="7ad78-478">Un membre de dimension statistique nommé Services HR est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="7ad78-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-479">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-479">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-480">Services HR</span><span class="sxs-lookup"><span data-stu-id="7ad78-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-481">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-481">CC002</span></span></td>
<td><span data-ttu-id="7ad78-482">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-482">Finance</span></span></td>
<td><span data-ttu-id="7ad78-483">35</span><span class="sxs-lookup"><span data-stu-id="7ad78-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-484">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-484">CC003</span></span></td>
<td><span data-ttu-id="7ad78-485">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-485">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-486">55</span><span class="sxs-lookup"><span data-stu-id="7ad78-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-487">CC004</span><span class="sxs-lookup"><span data-stu-id="7ad78-487">CC004</span></span></td>
<td><span data-ttu-id="7ad78-488">Emballage</span><span class="sxs-lookup"><span data-stu-id="7ad78-488">Packaging</span></span></td>
<td><span data-ttu-id="7ad78-489">10</span><span class="sxs-lookup"><span data-stu-id="7ad78-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-490">L’objet de coût CC002 Finance contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="7ad78-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="7ad78-491">Un membre de dimension statistique nommé Services Finance est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="7ad78-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-492">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-492">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-493">Services Finance</span><span class="sxs-lookup"><span data-stu-id="7ad78-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-494">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-494">CC003</span></span></td>
<td><span data-ttu-id="7ad78-495">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-495">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-496">65</span><span class="sxs-lookup"><span data-stu-id="7ad78-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-497">CC004</span><span class="sxs-lookup"><span data-stu-id="7ad78-497">CC004</span></span></td>
<td><span data-ttu-id="7ad78-498">Emballage</span><span class="sxs-lookup"><span data-stu-id="7ad78-498">Packaging</span></span></td>
<td><span data-ttu-id="7ad78-499">35</span><span class="sxs-lookup"><span data-stu-id="7ad78-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-500">L’objet de coût CC003 Assemblage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="7ad78-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="7ad78-501">Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="7ad78-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-502">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-502">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-503">Services Assemblage (heures)</span><span class="sxs-lookup"><span data-stu-id="7ad78-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-504">Prod 1</span></span></td>
<td><span data-ttu-id="7ad78-505">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-505">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-506">60</span><span class="sxs-lookup"><span data-stu-id="7ad78-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-507">Prod 2</span></span></td>
<td><span data-ttu-id="7ad78-508">Produit 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-508">Product 2</span></span></td>
<td><span data-ttu-id="7ad78-509">20</span><span class="sxs-lookup"><span data-stu-id="7ad78-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-510">L’objet de coût CC004 Emballage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="7ad78-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="7ad78-511">Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="7ad78-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-512">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-512">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-513">Services Emballage (heures)</span><span class="sxs-lookup"><span data-stu-id="7ad78-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-514">Prod 1</span></span></td>
<td><span data-ttu-id="7ad78-515">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-515">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-516">80</span><span class="sxs-lookup"><span data-stu-id="7ad78-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-517">Prod 2</span></span></td>
<td><span data-ttu-id="7ad78-518">Produit 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-518">Product 2</span></span></td>
<td><span data-ttu-id="7ad78-519">15</span><span class="sxs-lookup"><span data-stu-id="7ad78-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="7ad78-520">Les mesures statistiques telles que les heures de production qu’un produit consomme peuvent être dérivées des données sources.</span><span class="sxs-lookup"><span data-stu-id="7ad78-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="7ad78-521">Pour plus d’informations, voir [Modèle de fournisseur de mesures statistiques](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="7ad78-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="7ad78-522">Le tableau suivant présente le résultat lorsque les services RH sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="7ad78-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-523">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-523">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-524">Ampleur</span><span class="sxs-lookup"><span data-stu-id="7ad78-524">Magnitude</span></span></th>
<th><span data-ttu-id="7ad78-525">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="7ad78-525">Allocation factor</span></span></th>
<th><span data-ttu-id="7ad78-526">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-526">Amount</span></span></th>
<th><span data-ttu-id="7ad78-527">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-528">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-528">CC002</span></span></td>
<td><span data-ttu-id="7ad78-529">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-529">Finance</span></span></td>
<td><span data-ttu-id="7ad78-530">35</span><span class="sxs-lookup"><span data-stu-id="7ad78-530">35</span></span></td>
<td><span data-ttu-id="7ad78-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="7ad78-532">175.00</span><span class="sxs-lookup"><span data-stu-id="7ad78-532">175.00</span></span></td>
<td><span data-ttu-id="7ad78-533">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-534">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-534">CC003</span></span></td>
<td><span data-ttu-id="7ad78-535">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-535">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-536">55</span><span class="sxs-lookup"><span data-stu-id="7ad78-536">55</span></span></td>
<td><span data-ttu-id="7ad78-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="7ad78-538">275.00</span><span class="sxs-lookup"><span data-stu-id="7ad78-538">275.00</span></span></td>
<td><span data-ttu-id="7ad78-539">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-540">CC004</span><span class="sxs-lookup"><span data-stu-id="7ad78-540">CC004</span></span></td>
<td><span data-ttu-id="7ad78-541">Emballage</span><span class="sxs-lookup"><span data-stu-id="7ad78-541">Packaging</span></span></td>
<td><span data-ttu-id="7ad78-542">10</span><span class="sxs-lookup"><span data-stu-id="7ad78-542">10</span></span></td>
<td><span data-ttu-id="7ad78-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="7ad78-544">50,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-544">50.00</span></span></td>
<td><span data-ttu-id="7ad78-545">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-546">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-546">CC002</span></span></td>
<td><span data-ttu-id="7ad78-547">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-547">Finance</span></span></td>
<td><span data-ttu-id="7ad78-548">35</span><span class="sxs-lookup"><span data-stu-id="7ad78-548">35</span></span></td>
<td><span data-ttu-id="7ad78-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="7ad78-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="7ad78-550">436.00</span><span class="sxs-lookup"><span data-stu-id="7ad78-550">436.00</span></span></td>
<td><span data-ttu-id="7ad78-551">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-552">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-552">CC003</span></span></td>
<td><span data-ttu-id="7ad78-553">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-553">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-554">55</span><span class="sxs-lookup"><span data-stu-id="7ad78-554">55</span></span></td>
<td><span data-ttu-id="7ad78-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="7ad78-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="7ad78-556">685.14</span><span class="sxs-lookup"><span data-stu-id="7ad78-556">685.14</span></span></td>
<td><span data-ttu-id="7ad78-557">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-558">CC004</span><span class="sxs-lookup"><span data-stu-id="7ad78-558">CC004</span></span></td>
<td><span data-ttu-id="7ad78-559">Emballage</span><span class="sxs-lookup"><span data-stu-id="7ad78-559">Packaging</span></span></td>
<td><span data-ttu-id="7ad78-560">10</span><span class="sxs-lookup"><span data-stu-id="7ad78-560">10</span></span></td>
<td><span data-ttu-id="7ad78-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="7ad78-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="7ad78-562">124.57</span><span class="sxs-lookup"><span data-stu-id="7ad78-562">124.57</span></span></td>
<td><span data-ttu-id="7ad78-563">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-564">Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="7ad78-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-565">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-565">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-566">Ampleur</span><span class="sxs-lookup"><span data-stu-id="7ad78-566">Magnitude</span></span></th>
<th><span data-ttu-id="7ad78-567">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="7ad78-567">Allocation factor</span></span></th>
<th><span data-ttu-id="7ad78-568">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-568">Amount</span></span></th>
<th><span data-ttu-id="7ad78-569">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-570">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-570">CC003</span></span></td>
<td><span data-ttu-id="7ad78-571">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-571">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-572">65</span><span class="sxs-lookup"><span data-stu-id="7ad78-572">65</span></span></td>
<td><span data-ttu-id="7ad78-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="7ad78-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="7ad78-574">438.75</span><span class="sxs-lookup"><span data-stu-id="7ad78-574">438.75</span></span></td>
<td><span data-ttu-id="7ad78-575">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-576">CC004</span><span class="sxs-lookup"><span data-stu-id="7ad78-576">CC004</span></span></td>
<td><span data-ttu-id="7ad78-577">Emballage</span><span class="sxs-lookup"><span data-stu-id="7ad78-577">Packaging</span></span></td>
<td><span data-ttu-id="7ad78-578">35</span><span class="sxs-lookup"><span data-stu-id="7ad78-578">35</span></span></td>
<td><span data-ttu-id="7ad78-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="7ad78-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="7ad78-580">236.25</span><span class="sxs-lookup"><span data-stu-id="7ad78-580">236.25</span></span></td>
<td><span data-ttu-id="7ad78-581">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-582">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-582">CC003</span></span></td>
<td><span data-ttu-id="7ad78-583">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-583">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-584">65</span><span class="sxs-lookup"><span data-stu-id="7ad78-584">65</span></span></td>
<td><span data-ttu-id="7ad78-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="7ad78-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="7ad78-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="7ad78-586">5,297.69</span></span></td>
<td><span data-ttu-id="7ad78-587">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-588">CC004</span><span class="sxs-lookup"><span data-stu-id="7ad78-588">CC004</span></span></td>
<td><span data-ttu-id="7ad78-589">Emballage</span><span class="sxs-lookup"><span data-stu-id="7ad78-589">Packaging</span></span></td>
<td><span data-ttu-id="7ad78-590">35</span><span class="sxs-lookup"><span data-stu-id="7ad78-590">35</span></span></td>
<td><span data-ttu-id="7ad78-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="7ad78-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="7ad78-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="7ad78-592">2,852.60</span></span></td>
<td><span data-ttu-id="7ad78-593">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-594">Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="7ad78-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-595">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-595">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-596">Ampleur</span><span class="sxs-lookup"><span data-stu-id="7ad78-596">Magnitude</span></span></th>
<th><span data-ttu-id="7ad78-597">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="7ad78-597">Allocation factor</span></span></th>
<th><span data-ttu-id="7ad78-598">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-598">Amount</span></span></th>
<th><span data-ttu-id="7ad78-599">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-600">Prod 1</span></span></td>
<td><span data-ttu-id="7ad78-601">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-601">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-602">60</span><span class="sxs-lookup"><span data-stu-id="7ad78-602">60</span></span></td>
<td><span data-ttu-id="7ad78-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="7ad78-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="7ad78-604">535.31</span><span class="sxs-lookup"><span data-stu-id="7ad78-604">535.31</span></span></td>
<td><span data-ttu-id="7ad78-605">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-606">Prod 2</span></span></td>
<td><span data-ttu-id="7ad78-607">Produit 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-607">Product 2</span></span></td>
<td><span data-ttu-id="7ad78-608">20</span><span class="sxs-lookup"><span data-stu-id="7ad78-608">20</span></span></td>
<td><span data-ttu-id="7ad78-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="7ad78-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="7ad78-610">178.44</span><span class="sxs-lookup"><span data-stu-id="7ad78-610">178.44</span></span></td>
<td><span data-ttu-id="7ad78-611">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-612">Prod 1</span></span></td>
<td><span data-ttu-id="7ad78-613">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-613">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-614">60</span><span class="sxs-lookup"><span data-stu-id="7ad78-614">60</span></span></td>
<td><span data-ttu-id="7ad78-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="7ad78-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="7ad78-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="7ad78-616">4,487.12</span></span></td>
<td><span data-ttu-id="7ad78-617">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-618">Prod 2</span></span></td>
<td><span data-ttu-id="7ad78-619">Produit 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-619">Product 2</span></span></td>
<td><span data-ttu-id="7ad78-620">20</span><span class="sxs-lookup"><span data-stu-id="7ad78-620">20</span></span></td>
<td><span data-ttu-id="7ad78-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="7ad78-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="7ad78-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="7ad78-622">1,495.71</span></span></td>
<td><span data-ttu-id="7ad78-623">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7ad78-624">Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="7ad78-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-625">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-625">Cost object</span></span></th>
<th><span data-ttu-id="7ad78-626">Ampleur</span><span class="sxs-lookup"><span data-stu-id="7ad78-626">Magnitude</span></span></th>
<th><span data-ttu-id="7ad78-627">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="7ad78-627">Allocation factor</span></span></th>
<th><span data-ttu-id="7ad78-628">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-628">Amount</span></span></th>
<th><span data-ttu-id="7ad78-629">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-630">Prod 1</span></span></td>
<td><span data-ttu-id="7ad78-631">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-631">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-632">80</span><span class="sxs-lookup"><span data-stu-id="7ad78-632">80</span></span></td>
<td><span data-ttu-id="7ad78-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="7ad78-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="7ad78-634">241.05</span><span class="sxs-lookup"><span data-stu-id="7ad78-634">241.05</span></span></td>
<td><span data-ttu-id="7ad78-635">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-636">Prod 2</span></span></td>
<td><span data-ttu-id="7ad78-637">Produit 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-637">Product 2</span></span></td>
<td><span data-ttu-id="7ad78-638">15</span><span class="sxs-lookup"><span data-stu-id="7ad78-638">15</span></span></td>
<td><span data-ttu-id="7ad78-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="7ad78-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="7ad78-640">45.20</span><span class="sxs-lookup"><span data-stu-id="7ad78-640">45.20</span></span></td>
<td><span data-ttu-id="7ad78-641">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-642">Prod 1</span></span></td>
<td><span data-ttu-id="7ad78-643">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-643">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-644">80</span><span class="sxs-lookup"><span data-stu-id="7ad78-644">80</span></span></td>
<td><span data-ttu-id="7ad78-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="7ad78-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="7ad78-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="7ad78-646">2,507.09</span></span></td>
<td><span data-ttu-id="7ad78-647">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-648">Prod 2</span></span></td>
<td><span data-ttu-id="7ad78-649">Produit 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-649">Product 2</span></span></td>
<td><span data-ttu-id="7ad78-650">15</span><span class="sxs-lookup"><span data-stu-id="7ad78-650">15</span></span></td>
<td><span data-ttu-id="7ad78-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="7ad78-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="7ad78-652">470.08</span><span class="sxs-lookup"><span data-stu-id="7ad78-652">470.08</span></span></td>
<td><span data-ttu-id="7ad78-653">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="7ad78-654">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="7ad78-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7ad78-655">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="7ad78-655">Journal</span></span></th>
<th><span data-ttu-id="7ad78-656">Type de journal</span><span class="sxs-lookup"><span data-stu-id="7ad78-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="7ad78-657">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="7ad78-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="7ad78-658">Version</span><span class="sxs-lookup"><span data-stu-id="7ad78-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-659">00004</span><span class="sxs-lookup"><span data-stu-id="7ad78-659">00004</span></span></td>
<td><span data-ttu-id="7ad78-660">Journal de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="7ad78-661">Exercice</span><span class="sxs-lookup"><span data-stu-id="7ad78-661">Fiscal</span></span></td>
<td><span data-ttu-id="7ad78-662">2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-662">2017</span></span></td>
<td><span data-ttu-id="7ad78-663">Période 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-663">Period 1</span></span></td>
<td><span data-ttu-id="7ad78-664">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="7ad78-665">Lignes de journal</span><span class="sxs-lookup"><span data-stu-id="7ad78-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7ad78-666">Date comptable</span><span class="sxs-lookup"><span data-stu-id="7ad78-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-667">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-668">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-668">Cost element</span></span></th>
<th><span data-ttu-id="7ad78-669">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-669">Cost behavior</span></span></th>
<th><span data-ttu-id="7ad78-670">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-671">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-672">CC001</span><span class="sxs-lookup"><span data-stu-id="7ad78-672">CC001</span></span></td>
<td><span data-ttu-id="7ad78-673">RH</span><span class="sxs-lookup"><span data-stu-id="7ad78-673">HR</span></span></td>
<td><span data-ttu-id="7ad78-674">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-674">10001</span></span></td>
<td><span data-ttu-id="7ad78-675">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-675">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-676">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-676">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-677">500,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-678">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-679">CC001</span><span class="sxs-lookup"><span data-stu-id="7ad78-679">CC001</span></span></td>
<td><span data-ttu-id="7ad78-680">RH</span><span class="sxs-lookup"><span data-stu-id="7ad78-680">HR</span></span></td>
<td><span data-ttu-id="7ad78-681">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-681">10001</span></span></td>
<td><span data-ttu-id="7ad78-682">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-682">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-683">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-683">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="7ad78-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-685">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-686">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-686">CC002</span></span></td>
<td><span data-ttu-id="7ad78-687">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-687">Finance</span></span></td>
<td><span data-ttu-id="7ad78-688">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-688">10001</span></span></td>
<td><span data-ttu-id="7ad78-689">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-689">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-690">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-690">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-691">675.00</span><span class="sxs-lookup"><span data-stu-id="7ad78-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-692">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-693">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-693">CC002</span></span></td>
<td><span data-ttu-id="7ad78-694">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-694">Finance</span></span></td>
<td><span data-ttu-id="7ad78-695">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-695">10001</span></span></td>
<td><span data-ttu-id="7ad78-696">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-696">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-697">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-697">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="7ad78-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-699">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-700">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-700">CC003</span></span></td>
<td><span data-ttu-id="7ad78-701">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-701">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-702">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-702">10001</span></span></td>
<td><span data-ttu-id="7ad78-703">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-703">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-704">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-704">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-705">713.75</span><span class="sxs-lookup"><span data-stu-id="7ad78-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-706">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-707">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-707">CC003</span></span></td>
<td><span data-ttu-id="7ad78-708">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-708">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-709">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-709">10001</span></span></td>
<td><span data-ttu-id="7ad78-710">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-710">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-711">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-711">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="7ad78-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-713">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-714">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-714">CC003</span></span></td>
<td><span data-ttu-id="7ad78-715">Emballage</span><span class="sxs-lookup"><span data-stu-id="7ad78-715">Packaging</span></span></td>
<td><span data-ttu-id="7ad78-716">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-716">10001</span></span></td>
<td><span data-ttu-id="7ad78-717">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-717">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-718">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-718">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-719">286.25</span><span class="sxs-lookup"><span data-stu-id="7ad78-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-720">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-721">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-721">CC003</span></span></td>
<td><span data-ttu-id="7ad78-722">Emballage</span><span class="sxs-lookup"><span data-stu-id="7ad78-722">Packaging</span></span></td>
<td><span data-ttu-id="7ad78-723">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-723">10001</span></span></td>
<td><span data-ttu-id="7ad78-724">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-724">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-725">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-725">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="7ad78-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-727">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-728">Prod 1</span></span></td>
<td><span data-ttu-id="7ad78-729">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-729">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-730">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-730">10001</span></span></td>
<td><span data-ttu-id="7ad78-731">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-731">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-732">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-732">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-733">776.36</span><span class="sxs-lookup"><span data-stu-id="7ad78-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-734">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-735">Prod 1</span></span></td>
<td><span data-ttu-id="7ad78-736">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-736">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-737">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-737">10001</span></span></td>
<td><span data-ttu-id="7ad78-738">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-738">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-739">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-739">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="7ad78-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-741">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-742">Prod 2</span></span></td>
<td><span data-ttu-id="7ad78-743">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-743">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-744">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-744">10001</span></span></td>
<td><span data-ttu-id="7ad78-745">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-745">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-746">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-746">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-747">223.64</span><span class="sxs-lookup"><span data-stu-id="7ad78-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-748">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="7ad78-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-749">Prod 2</span></span></td>
<td><span data-ttu-id="7ad78-750">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-750">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-751">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-751">10001</span></span></td>
<td><span data-ttu-id="7ad78-752">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-752">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-753">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-753">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="7ad78-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="7ad78-755">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7ad78-756">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7ad78-757">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-757">Cost element</span></span></th>
<th><span data-ttu-id="7ad78-758">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="7ad78-758">Cost behavior</span></span></th>
<th><span data-ttu-id="7ad78-759">Montant</span><span class="sxs-lookup"><span data-stu-id="7ad78-759">Amount</span></span></th>
<th><span data-ttu-id="7ad78-760">Date comptable</span><span class="sxs-lookup"><span data-stu-id="7ad78-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7ad78-761">CC001</span><span class="sxs-lookup"><span data-stu-id="7ad78-761">CC001</span></span></td>
<td><span data-ttu-id="7ad78-762">RH</span><span class="sxs-lookup"><span data-stu-id="7ad78-762">HR</span></span></td>
<td><span data-ttu-id="7ad78-763">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-763">10001</span></span></td>
<td><span data-ttu-id="7ad78-764">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-764">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-765">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-765">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-766">-500.00</span></span></td>
<td><span data-ttu-id="7ad78-767">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-768">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-768">CC002</span></span></td>
<td><span data-ttu-id="7ad78-769">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-769">Finance</span></span></td>
<td><span data-ttu-id="7ad78-770">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-770">10001</span></span></td>
<td><span data-ttu-id="7ad78-771">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-771">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-772">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-772">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-773">175.00</span><span class="sxs-lookup"><span data-stu-id="7ad78-773">175.00</span></span></td>
<td><span data-ttu-id="7ad78-774">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-775">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-775">CC003</span></span></td>
<td><span data-ttu-id="7ad78-776">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-776">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-777">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-777">10001</span></span></td>
<td><span data-ttu-id="7ad78-778">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-778">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-779">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-779">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-780">275.00</span><span class="sxs-lookup"><span data-stu-id="7ad78-780">275.00</span></span></td>
<td><span data-ttu-id="7ad78-781">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-782">CC004</span><span class="sxs-lookup"><span data-stu-id="7ad78-782">CC004</span></span></td>
<td><span data-ttu-id="7ad78-783">Emballage</span><span class="sxs-lookup"><span data-stu-id="7ad78-783">Packaging</span></span></td>
<td><span data-ttu-id="7ad78-784">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-784">10001</span></span></td>
<td><span data-ttu-id="7ad78-785">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-785">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-786">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-786">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-787">50,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-787">50,00</span></span></td>
<td><span data-ttu-id="7ad78-788">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-789">CC001</span><span class="sxs-lookup"><span data-stu-id="7ad78-789">CC001</span></span></td>
<td><span data-ttu-id="7ad78-790">RH</span><span class="sxs-lookup"><span data-stu-id="7ad78-790">HR</span></span></td>
<td><span data-ttu-id="7ad78-791">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-791">10001</span></span></td>
<td><span data-ttu-id="7ad78-792">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-792">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-793">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-793">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="7ad78-794">-1,245.71</span></span></td>
<td><span data-ttu-id="7ad78-795">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-796">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-796">CC002</span></span></td>
<td><span data-ttu-id="7ad78-797">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-797">Finance</span></span></td>
<td><span data-ttu-id="7ad78-798">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-798">10001</span></span></td>
<td><span data-ttu-id="7ad78-799">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-799">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-800">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-800">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-801">436.00</span><span class="sxs-lookup"><span data-stu-id="7ad78-801">436.00</span></span></td>
<td><span data-ttu-id="7ad78-802">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-803">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-803">CC003</span></span></td>
<td><span data-ttu-id="7ad78-804">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-804">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-805">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-805">10001</span></span></td>
<td><span data-ttu-id="7ad78-806">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-806">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-807">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-807">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-808">685.14</span><span class="sxs-lookup"><span data-stu-id="7ad78-808">685.14</span></span></td>
<td><span data-ttu-id="7ad78-809">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-810">CC004</span><span class="sxs-lookup"><span data-stu-id="7ad78-810">CC004</span></span></td>
<td><span data-ttu-id="7ad78-811">Emballage</span><span class="sxs-lookup"><span data-stu-id="7ad78-811">Packaging</span></span></td>
<td><span data-ttu-id="7ad78-812">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-812">10001</span></span></td>
<td><span data-ttu-id="7ad78-813">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-813">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-814">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-814">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-815">124.57</span><span class="sxs-lookup"><span data-stu-id="7ad78-815">124.57</span></span></td>
<td><span data-ttu-id="7ad78-816">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-817">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-817">CC002</span></span></td>
<td><span data-ttu-id="7ad78-818">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-818">Finance</span></span></td>
<td><span data-ttu-id="7ad78-819">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-819">10001</span></span></td>
<td><span data-ttu-id="7ad78-820">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-820">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-821">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-821">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-822">-675.00</span></span></td>
<td><span data-ttu-id="7ad78-823">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-824">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-824">CC003</span></span></td>
<td><span data-ttu-id="7ad78-825">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-825">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-826">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-826">10001</span></span></td>
<td><span data-ttu-id="7ad78-827">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-827">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-828">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-828">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-829">438.75</span><span class="sxs-lookup"><span data-stu-id="7ad78-829">438.75</span></span></td>
<td><span data-ttu-id="7ad78-830">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-831">CC004</span><span class="sxs-lookup"><span data-stu-id="7ad78-831">CC004</span></span></td>
<td><span data-ttu-id="7ad78-832">Emballage</span><span class="sxs-lookup"><span data-stu-id="7ad78-832">Packaging</span></span></td>
<td><span data-ttu-id="7ad78-833">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-833">10001</span></span></td>
<td><span data-ttu-id="7ad78-834">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-834">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-835">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-835">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-836">236.25</span><span class="sxs-lookup"><span data-stu-id="7ad78-836">236.25</span></span></td>
<td><span data-ttu-id="7ad78-837">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-838">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-838">CC002</span></span></td>
<td><span data-ttu-id="7ad78-839">Finances</span><span class="sxs-lookup"><span data-stu-id="7ad78-839">Finance</span></span></td>
<td><span data-ttu-id="7ad78-840">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-840">10001</span></span></td>
<td><span data-ttu-id="7ad78-841">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-841">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-842">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-842">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="7ad78-843">-8,150.29</span></span></td>
<td><span data-ttu-id="7ad78-844">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-845">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-845">CC003</span></span></td>
<td><span data-ttu-id="7ad78-846">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-846">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-847">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-847">10001</span></span></td>
<td><span data-ttu-id="7ad78-848">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-848">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-849">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-849">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="7ad78-850">5,297.69</span></span></td>
<td><span data-ttu-id="7ad78-851">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-852">CC004</span><span class="sxs-lookup"><span data-stu-id="7ad78-852">CC004</span></span></td>
<td><span data-ttu-id="7ad78-853">Emballage</span><span class="sxs-lookup"><span data-stu-id="7ad78-853">Packaging</span></span></td>
<td><span data-ttu-id="7ad78-854">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-854">10001</span></span></td>
<td><span data-ttu-id="7ad78-855">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-855">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-856">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-856">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="7ad78-857">2,852.60</span></span></td>
<td><span data-ttu-id="7ad78-858">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-859">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-859">CC003</span></span></td>
<td><span data-ttu-id="7ad78-860">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-860">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-861">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-861">10001</span></span></td>
<td><span data-ttu-id="7ad78-862">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-862">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-863">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-863">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="7ad78-864">-713.75</span></span></td>
<td><span data-ttu-id="7ad78-865">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-866">Prod 1</span></span></td>
<td><span data-ttu-id="7ad78-867">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-867">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-868">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-868">10001</span></span></td>
<td><span data-ttu-id="7ad78-869">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-869">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-870">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-870">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-871">535.31</span><span class="sxs-lookup"><span data-stu-id="7ad78-871">535.31</span></span></td>
<td><span data-ttu-id="7ad78-872">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-873">Prod 2</span></span></td>
<td><span data-ttu-id="7ad78-874">Produit 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-874">Product 2</span></span></td>
<td><span data-ttu-id="7ad78-875">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-875">10001</span></span></td>
<td><span data-ttu-id="7ad78-876">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-876">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-877">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-877">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-878">178.44</span><span class="sxs-lookup"><span data-stu-id="7ad78-878">178.44</span></span></td>
<td><span data-ttu-id="7ad78-879">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-880">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-880">CC003</span></span></td>
<td><span data-ttu-id="7ad78-881">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-881">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-882">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-882">10001</span></span></td>
<td><span data-ttu-id="7ad78-883">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-883">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-884">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-884">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="7ad78-885">-5,982.83</span></span></td>
<td><span data-ttu-id="7ad78-886">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-887">Prod 1</span></span></td>
<td><span data-ttu-id="7ad78-888">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-888">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-889">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-889">10001</span></span></td>
<td><span data-ttu-id="7ad78-890">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-890">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-891">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-891">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="7ad78-892">4,487.12</span></span></td>
<td><span data-ttu-id="7ad78-893">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-894">Prod 2</span></span></td>
<td><span data-ttu-id="7ad78-895">Produit 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-895">Product 2</span></span></td>
<td><span data-ttu-id="7ad78-896">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-896">10001</span></span></td>
<td><span data-ttu-id="7ad78-897">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-897">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-898">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-898">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="7ad78-899">1,495.71</span></span></td>
<td><span data-ttu-id="7ad78-900">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-901">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-901">CC003</span></span></td>
<td><span data-ttu-id="7ad78-902">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-902">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-903">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-903">10001</span></span></td>
<td><span data-ttu-id="7ad78-904">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-904">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-905">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-905">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="7ad78-906">-286.25</span></span></td>
<td><span data-ttu-id="7ad78-907">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-908">Prod 1</span></span></td>
<td><span data-ttu-id="7ad78-909">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-909">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-910">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-910">10001</span></span></td>
<td><span data-ttu-id="7ad78-911">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-911">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-912">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-912">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-913">241.05</span><span class="sxs-lookup"><span data-stu-id="7ad78-913">241.05</span></span></td>
<td><span data-ttu-id="7ad78-914">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-915">Prod 2</span></span></td>
<td><span data-ttu-id="7ad78-916">Produit 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-916">Product 2</span></span></td>
<td><span data-ttu-id="7ad78-917">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-917">10001</span></span></td>
<td><span data-ttu-id="7ad78-918">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-918">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-919">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-919">Fixed cost</span></span></td>
<td><span data-ttu-id="7ad78-920">45.20</span><span class="sxs-lookup"><span data-stu-id="7ad78-920">45.20</span></span></td>
<td><span data-ttu-id="7ad78-921">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-922">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-922">CC003</span></span></td>
<td><span data-ttu-id="7ad78-923">Assemblage</span><span class="sxs-lookup"><span data-stu-id="7ad78-923">Assembly</span></span></td>
<td><span data-ttu-id="7ad78-924">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-924">10001</span></span></td>
<td><span data-ttu-id="7ad78-925">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-925">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-926">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-926">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="7ad78-927">-2,977.17</span></span></td>
<td><span data-ttu-id="7ad78-928">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-929">Prod 1</span></span></td>
<td><span data-ttu-id="7ad78-930">Produit 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-930">Product 1</span></span></td>
<td><span data-ttu-id="7ad78-931">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-931">10001</span></span></td>
<td><span data-ttu-id="7ad78-932">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-932">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-933">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-933">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="7ad78-934">2,507.09</span></span></td>
<td><span data-ttu-id="7ad78-935">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7ad78-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-936">Prod 2</span></span></td>
<td><span data-ttu-id="7ad78-937">Produit 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-937">Product 2</span></span></td>
<td><span data-ttu-id="7ad78-938">10001</span><span class="sxs-lookup"><span data-stu-id="7ad78-938">10001</span></span></td>
<td><span data-ttu-id="7ad78-939">Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-939">Electricity</span></span></td>
<td><span data-ttu-id="7ad78-940">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-940">Variable cost</span></span></td>
<td><span data-ttu-id="7ad78-941">470.08</span><span class="sxs-lookup"><span data-stu-id="7ad78-941">470.08</span></span></td>
<td><span data-ttu-id="7ad78-942">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="7ad78-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="7ad78-943">Conclusion</span><span class="sxs-lookup"><span data-stu-id="7ad78-943">Conclusion</span></span>
<span data-ttu-id="7ad78-944">Dans la comptabilité financière, un coût de 10 000,00 pour l’électricité est imputé sur un ID de centre de coût fictif.</span><span class="sxs-lookup"><span data-stu-id="7ad78-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="7ad78-945">Par conséquent, les comptables sauront que ce coût doit être affecté.</span><span class="sxs-lookup"><span data-stu-id="7ad78-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="7ad78-946">Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l’organisation, selon les stratégies et les règles qui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="7ad78-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="7ad78-947">Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="7ad78-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="7ad78-948">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="7ad78-949">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="7ad78-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="7ad78-950">Total</span><span class="sxs-lookup"><span data-stu-id="7ad78-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="7ad78-951">CC099</span><span class="sxs-lookup"><span data-stu-id="7ad78-951">CC099</span></span></th>
<th><span data-ttu-id="7ad78-952">CC001</span><span class="sxs-lookup"><span data-stu-id="7ad78-952">CC001</span></span></th>
<th><span data-ttu-id="7ad78-953">CC002</span><span class="sxs-lookup"><span data-stu-id="7ad78-953">CC002</span></span></th>
<th><span data-ttu-id="7ad78-954">CC003</span><span class="sxs-lookup"><span data-stu-id="7ad78-954">CC003</span></span></th>
<th><span data-ttu-id="7ad78-955">CC004</span><span class="sxs-lookup"><span data-stu-id="7ad78-955">CC004</span></span></th>
<th><span data-ttu-id="7ad78-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-956">Proj 1</span></span></th>
<th><span data-ttu-id="7ad78-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-957">Proj 2</span></span></th>
<th><span data-ttu-id="7ad78-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7ad78-958">Prod 1</span></span></th>
<th><span data-ttu-id="7ad78-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7ad78-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="7ad78-960">10001 Électricité</span><span class="sxs-lookup"><span data-stu-id="7ad78-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ad78-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ad78-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ad78-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ad78-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ad78-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ad78-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="7ad78-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="7ad78-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ad78-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="7ad78-970">Non classifié</span><span class="sxs-lookup"><span data-stu-id="7ad78-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-971">0,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="7ad78-972">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="7ad78-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-973">0,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-974">0,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-975">0,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-976">0,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-977">0,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-978">776.36</span><span class="sxs-lookup"><span data-stu-id="7ad78-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-979">223.64</span><span class="sxs-lookup"><span data-stu-id="7ad78-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-980"><strong>1 000,00</strong></span><span class="sxs-lookup"><span data-stu-id="7ad78-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="7ad78-981">Coût variable</span><span class="sxs-lookup"><span data-stu-id="7ad78-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-982">000</span><span class="sxs-lookup"><span data-stu-id="7ad78-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-983">0,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-984">0,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-985">0,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-986">0,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-987">30,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-988">10,00</span><span class="sxs-lookup"><span data-stu-id="7ad78-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="7ad78-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="7ad78-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7ad78-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ad78-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="7ad78-992">Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût.</span><span class="sxs-lookup"><span data-stu-id="7ad78-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="7ad78-993">Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="7ad78-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="7ad78-994">Autrement dit, les objets de coût de plus bas niveau supportent le coût.</span><span class="sxs-lookup"><span data-stu-id="7ad78-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="7ad78-995">Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts.</span><span class="sxs-lookup"><span data-stu-id="7ad78-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="7ad78-996">Pour plus d’informations, voir [Stratégie de repositionnement des coûts et calcul des frais généraux](cost-rollup.md)..</span><span class="sxs-lookup"><span data-stu-id="7ad78-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]