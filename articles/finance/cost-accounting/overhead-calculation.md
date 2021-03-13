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
ms.openlocfilehash: d60248f2bd6774b2e9afdb3632b6eb31d67349ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009516"
---
# <a name="overhead-calculation"></a><span data-ttu-id="bdb1d-103">Calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="bdb1d-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bdb1d-104">Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="bdb1d-105">Définition des termes</span><span class="sxs-lookup"><span data-stu-id="bdb1d-105">Term definition</span></span>
---------------

<span data-ttu-id="bdb1d-106">Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="bdb1d-107">Les frais généraux permettent essentiellement l’identification des activités rémunératrices.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="bdb1d-108">Voici quelques exemples de frais généraux :</span><span class="sxs-lookup"><span data-stu-id="bdb1d-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="bdb1d-109">Loyer</span><span class="sxs-lookup"><span data-stu-id="bdb1d-109">Rent</span></span>
-   <span data-ttu-id="bdb1d-110">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-110">Electricity</span></span>
-   <span data-ttu-id="bdb1d-111">Salaires administratifs</span><span class="sxs-lookup"><span data-stu-id="bdb1d-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="bdb1d-112">Vue d’ensemble du calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="bdb1d-112">Overhead calculation overview</span></span>
<span data-ttu-id="bdb1d-113">Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l’ordre correct.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="bdb1d-114">Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="bdb1d-115">Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="bdb1d-116">Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="bdb1d-117">Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="bdb1d-118">L’ID de version unique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="bdb1d-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="bdb1d-119">Type de version</span><span class="sxs-lookup"><span data-stu-id="bdb1d-119">Version type</span></span>
-   <span data-ttu-id="bdb1d-120">Date et heure</span><span class="sxs-lookup"><span data-stu-id="bdb1d-120">Date and time</span></span>
-   <span data-ttu-id="bdb1d-121">Comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="bdb1d-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="bdb1d-122">Exercice</span><span class="sxs-lookup"><span data-stu-id="bdb1d-122">Fiscal year</span></span>
-   <span data-ttu-id="bdb1d-123">Période fiscale</span><span class="sxs-lookup"><span data-stu-id="bdb1d-123">Fiscal period</span></span>

<span data-ttu-id="bdb1d-124">Le calcul des frais généraux est effectué indépendamment de la version.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="bdb1d-125">Par conséquent, vous pouvez calculer la version de budget avant la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="bdb1d-126">Le calcul des frais généraux comporte quatre étapes, comme le montre l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="bdb1d-127">Dans chaque étape, un en-tête de journal avec des entrées de journal est créé.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="bdb1d-128">Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="bdb1d-129">Les stratégies et les règles s’appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="bdb1d-130">Par conséquent, vous disposez toujours d’une traçabilité complète.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="bdb1d-131">[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="bdb1d-132">Calculer et affecter les frais généraux Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="bdb1d-133">Dans la comptabilité financière, certaines coûts, tels que l’électricité, sont enregistrés comme montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="bdb1d-134">Par conséquent, l’analyse détaillée n’est pas fournie pour le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="bdb1d-135">Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l’organisation, les coûts doivent suivre les unités organisationnelles.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="bdb1d-136">Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="bdb1d-137">Dans la comptabilité, le coût de l’électricité peut être validé comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bdb1d-138">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-139">Centre de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-140">Compte principal</span><span class="sxs-lookup"><span data-stu-id="bdb1d-140">Main account</span></span></th>
<th><span data-ttu-id="bdb1d-141">Montant en devise comptable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-142">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-143">CC099</span><span class="sxs-lookup"><span data-stu-id="bdb1d-143">CC099</span></span></td>
<td><span data-ttu-id="bdb1d-144">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bdb1d-144">Default cost center</span></span></td>
<td><span data-ttu-id="bdb1d-145">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-145">10001</span></span></td>
<td><span data-ttu-id="bdb1d-146">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-146">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="bdb1d-148">Étape 1 : Traiter le calcul du comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="bdb1d-149">Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="bdb1d-150">Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="bdb1d-151">Définir la règle de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-151">Define the cost behavior rule</span></span>

<span data-ttu-id="bdb1d-152">Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="bdb1d-153">Les factures d’électricité correspondent souvent à cette définition.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="bdb1d-154">Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH).</span><span class="sxs-lookup"><span data-stu-id="bdb1d-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="bdb1d-155">Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :</span><span class="sxs-lookup"><span data-stu-id="bdb1d-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="bdb1d-156">Montant fixe 1 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="bdb1d-157">0 &lt;= 1 000,00 = Fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="bdb1d-158">1 000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="bdb1d-159">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bdb1d-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bdb1d-160">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bdb1d-160">Journal</span></span></th>
<th><span data-ttu-id="bdb1d-161">Type de journal</span><span class="sxs-lookup"><span data-stu-id="bdb1d-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="bdb1d-162">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="bdb1d-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="bdb1d-163">Version</span><span class="sxs-lookup"><span data-stu-id="bdb1d-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-164">00001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-164">00001</span></span></td>
<td><span data-ttu-id="bdb1d-165">Journal de calcul de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="bdb1d-166">Exercice</span><span class="sxs-lookup"><span data-stu-id="bdb1d-166">Fiscal</span></span></td>
<td><span data-ttu-id="bdb1d-167">2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-167">2017</span></span></td>
<td><span data-ttu-id="bdb1d-168">Période 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-168">Period 1</span></span></td>
<td><span data-ttu-id="bdb1d-169">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="bdb1d-170">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bdb1d-171">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-172">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-173">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-173">Cost element</span></span></th>
<th><span data-ttu-id="bdb1d-174">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-174">Cost behavior</span></span></th>
<th><span data-ttu-id="bdb1d-175">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-176">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-177">CC099</span><span class="sxs-lookup"><span data-stu-id="bdb1d-177">CC099</span></span></td>
<td><span data-ttu-id="bdb1d-178">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bdb1d-178">Default cost center</span></span></td>
<td><span data-ttu-id="bdb1d-179">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-179">10001</span></span></td>
<td><span data-ttu-id="bdb1d-180">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-180">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-181">Non classifié</span><span class="sxs-lookup"><span data-stu-id="bdb1d-181">Unclassified</span></span></td>
<td><span data-ttu-id="bdb1d-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="bdb1d-183">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-184">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-185">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-185">Cost element</span></span></th>
<th><span data-ttu-id="bdb1d-186">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-186">Cost behavior</span></span></th>
<th><span data-ttu-id="bdb1d-187">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-187">Amount</span></span></th>
<th><span data-ttu-id="bdb1d-188">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-189">CC099</span><span class="sxs-lookup"><span data-stu-id="bdb1d-189">CC099</span></span></td>
<td><span data-ttu-id="bdb1d-190">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bdb1d-190">Default cost center</span></span></td>
<td><span data-ttu-id="bdb1d-191">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-191">10001</span></span></td>
<td><span data-ttu-id="bdb1d-192">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-192">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-193">Non classifié</span><span class="sxs-lookup"><span data-stu-id="bdb1d-193">Unclassified</span></span></td>
<td><span data-ttu-id="bdb1d-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-194">10,000.00</span></span></td>
<td><span data-ttu-id="bdb1d-195">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-196">CC099</span><span class="sxs-lookup"><span data-stu-id="bdb1d-196">CC099</span></span></td>
<td><span data-ttu-id="bdb1d-197">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bdb1d-197">Default cost center</span></span></td>
<td><span data-ttu-id="bdb1d-198">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-198">10001</span></span></td>
<td><span data-ttu-id="bdb1d-199">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-199">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-200">Non classifié</span><span class="sxs-lookup"><span data-stu-id="bdb1d-200">Unclassified</span></span></td>
<td><span data-ttu-id="bdb1d-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-201">-10,000.00</span></span></td>
<td><span data-ttu-id="bdb1d-202">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-203">CC099</span><span class="sxs-lookup"><span data-stu-id="bdb1d-203">CC099</span></span></td>
<td><span data-ttu-id="bdb1d-204">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bdb1d-204">Default cost center</span></span></td>
<td><span data-ttu-id="bdb1d-205">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-205">10001</span></span></td>
<td><span data-ttu-id="bdb1d-206">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-206">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-207">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-207">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-208">1,000.00</span></span></td>
<td><span data-ttu-id="bdb1d-209">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-210">CC099</span><span class="sxs-lookup"><span data-stu-id="bdb1d-210">CC099</span></span></td>
<td><span data-ttu-id="bdb1d-211">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bdb1d-211">Default cost center</span></span></td>
<td><span data-ttu-id="bdb1d-212">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-212">10001</span></span></td>
<td><span data-ttu-id="bdb1d-213">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-213">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-214">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-214">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-215">9 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-215">9,000.00</span></span></td>
<td><span data-ttu-id="bdb1d-216">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-217">Pour plus d’informations, voir [Créer et affecter une stratégie de comportement de coûts à une unité de contrôle des coûts](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="bdb1d-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="bdb1d-218">Étape 2 : Traiter le calcul de distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="bdb1d-219">La distribution des coûts est utilisée pour redistribuer le coût d’un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="bdb1d-220">La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l’élément de coût principal du coût d’origine.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="bdb1d-221">Définir la règle de distribution de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-221">Define the cost distribution rule</span></span>

<span data-ttu-id="bdb1d-222">Dans la comptabilité financière, les coûts d’électricité sont souvent enregistrés comme un montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="bdb1d-223">Dans le Contrôle de gestion, cette approche n’est pas assez détaillée.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="bdb1d-224">Le coût variable doit être attribué aux différents objets de coûts sur une base juste.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="bdb1d-225">La base de répartition la plus logique est la consommation de l’électricité (KWH).</span><span class="sxs-lookup"><span data-stu-id="bdb1d-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="bdb1d-226">Un membre de dimension statistique nommé Électricité est créé, et la consommation d’électricité est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="bdb1d-227">Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-228">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-228">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="bdb1d-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-230">CC001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-230">CC001</span></span></td>
<td><span data-ttu-id="bdb1d-231">RH</span><span class="sxs-lookup"><span data-stu-id="bdb1d-231">HR</span></span></td>
<td><span data-ttu-id="bdb1d-232">1 000</span><span class="sxs-lookup"><span data-stu-id="bdb1d-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-233">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-233">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-234">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-234">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-235">6 000</span><span class="sxs-lookup"><span data-stu-id="bdb1d-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-236">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-236">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-237">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-237">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-238">0</span><span class="sxs-lookup"><span data-stu-id="bdb1d-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-239">Le tableau suivant illustre le résultat lorsque la consommation d’électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-240">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-240">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-241">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bdb1d-241">Magnitude</span></span></th>
<th><span data-ttu-id="bdb1d-242">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bdb1d-242">Allocation factor</span></span></th>
<th><span data-ttu-id="bdb1d-243">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-244">CC001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-244">CC001</span></span></td>
<td><span data-ttu-id="bdb1d-245">RH</span><span class="sxs-lookup"><span data-stu-id="bdb1d-245">HR</span></span></td>
<td><span data-ttu-id="bdb1d-246">1 000</span><span class="sxs-lookup"><span data-stu-id="bdb1d-246">1,000</span></span></td>
<td><span data-ttu-id="bdb1d-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="bdb1d-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="bdb1d-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-249">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-249">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-250">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-250">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-251">6 000</span><span class="sxs-lookup"><span data-stu-id="bdb1d-251">6,000</span></span></td>
<td><span data-ttu-id="bdb1d-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="bdb1d-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="bdb1d-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-254">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-254">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-255">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-255">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-256">0</span><span class="sxs-lookup"><span data-stu-id="bdb1d-256">0</span></span></td>
<td><span data-ttu-id="bdb1d-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="bdb1d-258">0,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-259">Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l’électricité.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="bdb1d-260">Vous pouvez obtenir ce résultat à l’aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d’électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-261">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-261">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-262">Formule</span><span class="sxs-lookup"><span data-stu-id="bdb1d-262">Formula</span></span></th>
<th><span data-ttu-id="bdb1d-263">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bdb1d-263">Magnitude</span></span></th>
<th><span data-ttu-id="bdb1d-264">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bdb1d-264">Allocation factor</span></span></th>
<th><span data-ttu-id="bdb1d-265">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-266">CC001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-266">CC001</span></span></td>
<td><span data-ttu-id="bdb1d-267">RH</span><span class="sxs-lookup"><span data-stu-id="bdb1d-267">HR</span></span></td>
<td><span data-ttu-id="bdb1d-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="bdb1d-269">1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-269">1</span></span></td>
<td><span data-ttu-id="bdb1d-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="bdb1d-271">500,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-272">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-272">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-273">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-273">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="bdb1d-275">1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-275">1</span></span></td>
<td><span data-ttu-id="bdb1d-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="bdb1d-277">500,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-278">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-278">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-279">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-279">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="bdb1d-281">0</span><span class="sxs-lookup"><span data-stu-id="bdb1d-281">0</span></span></td>
<td><span data-ttu-id="bdb1d-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="bdb1d-283">0,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="bdb1d-284">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bdb1d-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bdb1d-285">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bdb1d-285">Journal</span></span></th>
<th><span data-ttu-id="bdb1d-286">Type de journal</span><span class="sxs-lookup"><span data-stu-id="bdb1d-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="bdb1d-287">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="bdb1d-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="bdb1d-288">Version</span><span class="sxs-lookup"><span data-stu-id="bdb1d-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-289">00002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-289">00002</span></span></td>
<td><span data-ttu-id="bdb1d-290">Journal de calcul de la distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="bdb1d-291">Exercice</span><span class="sxs-lookup"><span data-stu-id="bdb1d-291">Fiscal</span></span></td>
<td><span data-ttu-id="bdb1d-292">2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-292">2017</span></span></td>
<td><span data-ttu-id="bdb1d-293">Période 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-293">Period 1</span></span></td>
<td><span data-ttu-id="bdb1d-294">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="bdb1d-295">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bdb1d-296">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-297">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-298">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-298">Cost element</span></span></th>
<th><span data-ttu-id="bdb1d-299">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-299">Cost behavior</span></span></th>
<th><span data-ttu-id="bdb1d-300">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-301">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-302">CC099</span><span class="sxs-lookup"><span data-stu-id="bdb1d-302">CC099</span></span></td>
<td><span data-ttu-id="bdb1d-303">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bdb1d-303">Default cost center</span></span></td>
<td><span data-ttu-id="bdb1d-304">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-304">10001</span></span></td>
<td><span data-ttu-id="bdb1d-305">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-305">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-306">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-306">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-308">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-309">CC099</span><span class="sxs-lookup"><span data-stu-id="bdb1d-309">CC099</span></span></td>
<td><span data-ttu-id="bdb1d-310">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bdb1d-310">Default cost center</span></span></td>
<td><span data-ttu-id="bdb1d-311">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-311">10001</span></span></td>
<td><span data-ttu-id="bdb1d-312">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-312">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-313">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-313">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-314">9 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="bdb1d-315">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-316">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-317">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-317">Cost element</span></span></th>
<th><span data-ttu-id="bdb1d-318">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-318">Cost behavior</span></span></th>
<th><span data-ttu-id="bdb1d-319">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-319">Amount</span></span></th>
<th><span data-ttu-id="bdb1d-320">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-321">CC099</span><span class="sxs-lookup"><span data-stu-id="bdb1d-321">CC099</span></span></td>
<td><span data-ttu-id="bdb1d-322">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bdb1d-322">Default cost center</span></span></td>
<td><span data-ttu-id="bdb1d-323">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-323">10001</span></span></td>
<td><span data-ttu-id="bdb1d-324">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-324">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-325">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-325">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-326">-1,000.00</span></span></td>
<td><span data-ttu-id="bdb1d-327">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-328">CC001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-328">CC001</span></span></td>
<td><span data-ttu-id="bdb1d-329">RH</span><span class="sxs-lookup"><span data-stu-id="bdb1d-329">HR</span></span></td>
<td><span data-ttu-id="bdb1d-330">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-330">10001</span></span></td>
<td><span data-ttu-id="bdb1d-331">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-331">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-332">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-332">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-333">500,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-333">500.00</span></span></td>
<td><span data-ttu-id="bdb1d-334">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-335">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-335">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-336">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-336">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-337">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-337">10001</span></span></td>
<td><span data-ttu-id="bdb1d-338">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-338">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-339">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-339">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-340">500,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-340">500.00</span></span></td>
<td><span data-ttu-id="bdb1d-341">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-342">CC099</span><span class="sxs-lookup"><span data-stu-id="bdb1d-342">CC099</span></span></td>
<td><span data-ttu-id="bdb1d-343">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="bdb1d-343">Default cost center</span></span></td>
<td><span data-ttu-id="bdb1d-344">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-344">10001</span></span></td>
<td><span data-ttu-id="bdb1d-345">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-345">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-346">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-346">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-347">-9,000.00</span></span></td>
<td><span data-ttu-id="bdb1d-348">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-349">CC001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-349">CC001</span></span></td>
<td><span data-ttu-id="bdb1d-350">RH</span><span class="sxs-lookup"><span data-stu-id="bdb1d-350">HR</span></span></td>
<td><span data-ttu-id="bdb1d-351">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-351">10001</span></span></td>
<td><span data-ttu-id="bdb1d-352">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-352">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-353">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-353">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="bdb1d-354">1,285.71</span></span></td>
<td><span data-ttu-id="bdb1d-355">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-356">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-356">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-357">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-357">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-358">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-358">10001</span></span></td>
<td><span data-ttu-id="bdb1d-359">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-359">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-360">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-360">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="bdb1d-361">7,714.29</span></span></td>
<td><span data-ttu-id="bdb1d-362">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-363">Pour plus d’informations, voir [Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="bdb1d-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="bdb1d-364">Étape 3 : Traitement du calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="bdb1d-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="bdb1d-365">Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="bdb1d-366">Les frais sont basés sur un taux de coût prédéterminé et l’ampleur de la base d’affectation de répartition.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="bdb1d-367">Définition du taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="bdb1d-367">Define the overhead rate</span></span>

<span data-ttu-id="bdb1d-368">L’objet de coût CC001 HR contribue à un ensemble de projets internes.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="bdb1d-369">Un membre de dimension statistique nommé Projets HR est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-370">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-370">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-371">Heures</span><span class="sxs-lookup"><span data-stu-id="bdb1d-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-372">Proj 1</span></span></td>
<td><span data-ttu-id="bdb1d-373">Projet 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-373">Project 1</span></span></td>
<td><span data-ttu-id="bdb1d-374">3</span><span class="sxs-lookup"><span data-stu-id="bdb1d-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-375">Proj 2</span></span></td>
<td><span data-ttu-id="bdb1d-376">Projet 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-376">Project 2</span></span></td>
<td><span data-ttu-id="bdb1d-377">1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-378">Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-379">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-379">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-380">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-380">Cost element</span></span></th>
<th><span data-ttu-id="bdb1d-381">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-381">Cost behavior</span></span></th>
<th><span data-ttu-id="bdb1d-382">Unités</span><span class="sxs-lookup"><span data-stu-id="bdb1d-382">Units</span></span></th>
<th><span data-ttu-id="bdb1d-383">Taux</span><span class="sxs-lookup"><span data-stu-id="bdb1d-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-384">CC001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-384">CC001</span></span></td>
<td><span data-ttu-id="bdb1d-385">RH</span><span class="sxs-lookup"><span data-stu-id="bdb1d-385">HR</span></span></td>
<td><span data-ttu-id="bdb1d-386">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-386">10001</span></span></td>
<td><span data-ttu-id="bdb1d-387">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-387">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-388">1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-388">1</span></span></td>
<td><span data-ttu-id="bdb1d-389">10</span><span class="sxs-lookup"><span data-stu-id="bdb1d-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-390">Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-391">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-391">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-392">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bdb1d-392">Magnitude</span></span></th>
<th><span data-ttu-id="bdb1d-393">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-393">Cost element</span></span></th>
<th><span data-ttu-id="bdb1d-394">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bdb1d-394">Allocation factor</span></span></th>
<th><span data-ttu-id="bdb1d-395">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-396">Proj 1</span></span></td>
<td><span data-ttu-id="bdb1d-397">Projet 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-397">Project 1</span></span></td>
<td><span data-ttu-id="bdb1d-398">3</span><span class="sxs-lookup"><span data-stu-id="bdb1d-398">3</span></span></td>
<td><span data-ttu-id="bdb1d-399">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-399">10001</span></span></td>
<td><span data-ttu-id="bdb1d-400">(3 ÷ 1) × 10m00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="bdb1d-401">30,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-402">Proj 2</span></span></td>
<td><span data-ttu-id="bdb1d-403">Projet 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-403">Project 2</span></span></td>
<td><span data-ttu-id="bdb1d-404">1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-404">1</span></span></td>
<td><span data-ttu-id="bdb1d-405">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-405">10001</span></span></td>
<td><span data-ttu-id="bdb1d-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="bdb1d-407">10,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="bdb1d-408">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bdb1d-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bdb1d-409">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bdb1d-409">Journal</span></span></th>
<th><span data-ttu-id="bdb1d-410">Type de journal</span><span class="sxs-lookup"><span data-stu-id="bdb1d-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="bdb1d-411">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="bdb1d-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="bdb1d-412">Version</span><span class="sxs-lookup"><span data-stu-id="bdb1d-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-413">00003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-413">00003</span></span></td>
<td><span data-ttu-id="bdb1d-414">Journal de calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="bdb1d-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="bdb1d-415">Exercice</span><span class="sxs-lookup"><span data-stu-id="bdb1d-415">Fiscal</span></span></td>
<td><span data-ttu-id="bdb1d-416">2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-416">2017</span></span></td>
<td><span data-ttu-id="bdb1d-417">Période 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-417">Period 1</span></span></td>
<td><span data-ttu-id="bdb1d-418">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="bdb1d-419">Entrées du journal (pour le calcul du taux de frais généraux)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bdb1d-420">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-421">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-421">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-422">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bdb1d-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-423">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-424">Proj 1</span></span></td>
<td><span data-ttu-id="bdb1d-425">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="bdb1d-426">3,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-427">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-428">Proj 2</span></span></td>
<td><span data-ttu-id="bdb1d-429">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="bdb1d-430">1,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="bdb1d-431">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-432">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-433">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-433">Cost element</span></span></th>
<th><span data-ttu-id="bdb1d-434">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-434">Cost behavior</span></span></th>
<th><span data-ttu-id="bdb1d-435">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-435">Amount</span></span></th>
<th><span data-ttu-id="bdb1d-436">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-437">CC0001</span></span></td>
<td><span data-ttu-id="bdb1d-438">RH</span><span class="sxs-lookup"><span data-stu-id="bdb1d-438">HR</span></span></td>
<td><span data-ttu-id="bdb1d-439">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-439">10001</span></span></td>
<td><span data-ttu-id="bdb1d-440">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-440">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-441">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-441">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-442">-30.00</span></span></td>
<td><span data-ttu-id="bdb1d-443">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-444">Proj 1</span></span></td>
<td><span data-ttu-id="bdb1d-445">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="bdb1d-446">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-446">10001</span></span></td>
<td><span data-ttu-id="bdb1d-447">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-447">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-448">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-448">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-449">30,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-449">30.00</span></span></td>
<td><span data-ttu-id="bdb1d-450">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-451">CC001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-451">CC001</span></span></td>
<td><span data-ttu-id="bdb1d-452">RH</span><span class="sxs-lookup"><span data-stu-id="bdb1d-452">HR</span></span></td>
<td><span data-ttu-id="bdb1d-453">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-453">10001</span></span></td>
<td><span data-ttu-id="bdb1d-454">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-454">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-455">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-455">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-456">-10.00</span></span></td>
<td><span data-ttu-id="bdb1d-457">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-458">Proj 2</span></span></td>
<td><span data-ttu-id="bdb1d-459">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="bdb1d-460">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-460">10001</span></span></td>
<td><span data-ttu-id="bdb1d-461">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-461">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-462">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-462">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-463">10.00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-463">10.00</span></span></td>
<td><span data-ttu-id="bdb1d-464">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-465">Pour plus d’informations, voir [Exécuter le calcul des frais généraux](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="bdb1d-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="bdb1d-466">Étape 4 : Traiter le calcul de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="bdb1d-467">La répartition est utilisée pour affecter le solde d’un objet de coût à d’autres objets de coût en appliquant une base de répartition.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="bdb1d-468">Finance prend en charge la méthode de répartition réciproque.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="bdb1d-469">Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="bdb1d-470">Le système détermine automatiquement l’ordre correct selon lequel exécuter les répartitions.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="bdb1d-471">Le solde d’un objet de coût est réparti par une seule base de répartition.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="bdb1d-472">Les répartitions entre plusieurs dimensions d’objets de coût et leurs membres respectifs sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="bdb1d-473">L’ordre de répartition est contrôlé par l’unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="bdb1d-474">[![Méthode réciproque](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="bdb1d-475">Définir la répartition de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-475">Define the cost allocation</span></span>

<span data-ttu-id="bdb1d-476">Voici un exemple simple expliquant comment suivre le flux du coût.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="bdb1d-477">L’objet de coût CC001 HR contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="bdb1d-478">Un membre de dimension statistique nommé Services HR est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-479">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-479">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-480">Services HR</span><span class="sxs-lookup"><span data-stu-id="bdb1d-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-481">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-481">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-482">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-482">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-483">35</span><span class="sxs-lookup"><span data-stu-id="bdb1d-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-484">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-484">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-485">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-485">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-486">55</span><span class="sxs-lookup"><span data-stu-id="bdb1d-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-487">CC004</span><span class="sxs-lookup"><span data-stu-id="bdb1d-487">CC004</span></span></td>
<td><span data-ttu-id="bdb1d-488">Emballage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-488">Packaging</span></span></td>
<td><span data-ttu-id="bdb1d-489">10</span><span class="sxs-lookup"><span data-stu-id="bdb1d-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-490">L’objet de coût CC002 Finance contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="bdb1d-491">Un membre de dimension statistique nommé Services Finance est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-492">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-492">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-493">Services Finance</span><span class="sxs-lookup"><span data-stu-id="bdb1d-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-494">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-494">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-495">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-495">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-496">65</span><span class="sxs-lookup"><span data-stu-id="bdb1d-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-497">CC004</span><span class="sxs-lookup"><span data-stu-id="bdb1d-497">CC004</span></span></td>
<td><span data-ttu-id="bdb1d-498">Emballage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-498">Packaging</span></span></td>
<td><span data-ttu-id="bdb1d-499">35</span><span class="sxs-lookup"><span data-stu-id="bdb1d-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-500">L’objet de coût CC003 Assemblage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="bdb1d-501">Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-502">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-502">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-503">Services Assemblage (heures)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-504">Prod 1</span></span></td>
<td><span data-ttu-id="bdb1d-505">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-505">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-506">60</span><span class="sxs-lookup"><span data-stu-id="bdb1d-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-507">Prod 2</span></span></td>
<td><span data-ttu-id="bdb1d-508">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-508">Product 2</span></span></td>
<td><span data-ttu-id="bdb1d-509">20</span><span class="sxs-lookup"><span data-stu-id="bdb1d-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-510">L’objet de coût CC004 Emballage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="bdb1d-511">Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l’ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-512">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-512">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-513">Services Emballage (heures)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-514">Prod 1</span></span></td>
<td><span data-ttu-id="bdb1d-515">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-515">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-516">80</span><span class="sxs-lookup"><span data-stu-id="bdb1d-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-517">Prod 2</span></span></td>
<td><span data-ttu-id="bdb1d-518">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-518">Product 2</span></span></td>
<td><span data-ttu-id="bdb1d-519">15</span><span class="sxs-lookup"><span data-stu-id="bdb1d-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="bdb1d-520">Les mesures statistiques telles que les heures de production qu’un produit consomme peuvent être dérivées des données sources.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="bdb1d-521">Pour plus d’informations, voir [Modèle de fournisseur de mesures statistiques](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="bdb1d-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="bdb1d-522">Le tableau suivant présente le résultat lorsque les services RH sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="bdb1d-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-523">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-523">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-524">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bdb1d-524">Magnitude</span></span></th>
<th><span data-ttu-id="bdb1d-525">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bdb1d-525">Allocation factor</span></span></th>
<th><span data-ttu-id="bdb1d-526">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-526">Amount</span></span></th>
<th><span data-ttu-id="bdb1d-527">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-528">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-528">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-529">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-529">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-530">35</span><span class="sxs-lookup"><span data-stu-id="bdb1d-530">35</span></span></td>
<td><span data-ttu-id="bdb1d-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="bdb1d-532">175.00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-532">175.00</span></span></td>
<td><span data-ttu-id="bdb1d-533">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-534">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-534">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-535">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-535">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-536">55</span><span class="sxs-lookup"><span data-stu-id="bdb1d-536">55</span></span></td>
<td><span data-ttu-id="bdb1d-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="bdb1d-538">275.00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-538">275.00</span></span></td>
<td><span data-ttu-id="bdb1d-539">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-540">CC004</span><span class="sxs-lookup"><span data-stu-id="bdb1d-540">CC004</span></span></td>
<td><span data-ttu-id="bdb1d-541">Emballage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-541">Packaging</span></span></td>
<td><span data-ttu-id="bdb1d-542">10</span><span class="sxs-lookup"><span data-stu-id="bdb1d-542">10</span></span></td>
<td><span data-ttu-id="bdb1d-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="bdb1d-544">50,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-544">50.00</span></span></td>
<td><span data-ttu-id="bdb1d-545">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-546">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-546">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-547">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-547">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-548">35</span><span class="sxs-lookup"><span data-stu-id="bdb1d-548">35</span></span></td>
<td><span data-ttu-id="bdb1d-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="bdb1d-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="bdb1d-550">436.00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-550">436.00</span></span></td>
<td><span data-ttu-id="bdb1d-551">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-552">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-552">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-553">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-553">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-554">55</span><span class="sxs-lookup"><span data-stu-id="bdb1d-554">55</span></span></td>
<td><span data-ttu-id="bdb1d-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="bdb1d-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="bdb1d-556">685.14</span><span class="sxs-lookup"><span data-stu-id="bdb1d-556">685.14</span></span></td>
<td><span data-ttu-id="bdb1d-557">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-558">CC004</span><span class="sxs-lookup"><span data-stu-id="bdb1d-558">CC004</span></span></td>
<td><span data-ttu-id="bdb1d-559">Emballage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-559">Packaging</span></span></td>
<td><span data-ttu-id="bdb1d-560">10</span><span class="sxs-lookup"><span data-stu-id="bdb1d-560">10</span></span></td>
<td><span data-ttu-id="bdb1d-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="bdb1d-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="bdb1d-562">124.57</span><span class="sxs-lookup"><span data-stu-id="bdb1d-562">124.57</span></span></td>
<td><span data-ttu-id="bdb1d-563">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-564">Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="bdb1d-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-565">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-565">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-566">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bdb1d-566">Magnitude</span></span></th>
<th><span data-ttu-id="bdb1d-567">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bdb1d-567">Allocation factor</span></span></th>
<th><span data-ttu-id="bdb1d-568">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-568">Amount</span></span></th>
<th><span data-ttu-id="bdb1d-569">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-570">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-570">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-571">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-571">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-572">65</span><span class="sxs-lookup"><span data-stu-id="bdb1d-572">65</span></span></td>
<td><span data-ttu-id="bdb1d-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="bdb1d-574">438.75</span><span class="sxs-lookup"><span data-stu-id="bdb1d-574">438.75</span></span></td>
<td><span data-ttu-id="bdb1d-575">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-576">CC004</span><span class="sxs-lookup"><span data-stu-id="bdb1d-576">CC004</span></span></td>
<td><span data-ttu-id="bdb1d-577">Emballage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-577">Packaging</span></span></td>
<td><span data-ttu-id="bdb1d-578">35</span><span class="sxs-lookup"><span data-stu-id="bdb1d-578">35</span></span></td>
<td><span data-ttu-id="bdb1d-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="bdb1d-580">236.25</span><span class="sxs-lookup"><span data-stu-id="bdb1d-580">236.25</span></span></td>
<td><span data-ttu-id="bdb1d-581">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-582">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-582">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-583">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-583">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-584">65</span><span class="sxs-lookup"><span data-stu-id="bdb1d-584">65</span></span></td>
<td><span data-ttu-id="bdb1d-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="bdb1d-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="bdb1d-586">5,297.69</span></span></td>
<td><span data-ttu-id="bdb1d-587">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-588">CC004</span><span class="sxs-lookup"><span data-stu-id="bdb1d-588">CC004</span></span></td>
<td><span data-ttu-id="bdb1d-589">Emballage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-589">Packaging</span></span></td>
<td><span data-ttu-id="bdb1d-590">35</span><span class="sxs-lookup"><span data-stu-id="bdb1d-590">35</span></span></td>
<td><span data-ttu-id="bdb1d-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="bdb1d-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="bdb1d-592">2,852.60</span></span></td>
<td><span data-ttu-id="bdb1d-593">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-594">Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="bdb1d-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-595">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-595">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-596">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bdb1d-596">Magnitude</span></span></th>
<th><span data-ttu-id="bdb1d-597">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bdb1d-597">Allocation factor</span></span></th>
<th><span data-ttu-id="bdb1d-598">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-598">Amount</span></span></th>
<th><span data-ttu-id="bdb1d-599">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-600">Prod 1</span></span></td>
<td><span data-ttu-id="bdb1d-601">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-601">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-602">60</span><span class="sxs-lookup"><span data-stu-id="bdb1d-602">60</span></span></td>
<td><span data-ttu-id="bdb1d-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="bdb1d-604">535.31</span><span class="sxs-lookup"><span data-stu-id="bdb1d-604">535.31</span></span></td>
<td><span data-ttu-id="bdb1d-605">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-606">Prod 2</span></span></td>
<td><span data-ttu-id="bdb1d-607">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-607">Product 2</span></span></td>
<td><span data-ttu-id="bdb1d-608">20</span><span class="sxs-lookup"><span data-stu-id="bdb1d-608">20</span></span></td>
<td><span data-ttu-id="bdb1d-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="bdb1d-610">178.44</span><span class="sxs-lookup"><span data-stu-id="bdb1d-610">178.44</span></span></td>
<td><span data-ttu-id="bdb1d-611">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-612">Prod 1</span></span></td>
<td><span data-ttu-id="bdb1d-613">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-613">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-614">60</span><span class="sxs-lookup"><span data-stu-id="bdb1d-614">60</span></span></td>
<td><span data-ttu-id="bdb1d-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="bdb1d-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="bdb1d-616">4,487.12</span></span></td>
<td><span data-ttu-id="bdb1d-617">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-618">Prod 2</span></span></td>
<td><span data-ttu-id="bdb1d-619">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-619">Product 2</span></span></td>
<td><span data-ttu-id="bdb1d-620">20</span><span class="sxs-lookup"><span data-stu-id="bdb1d-620">20</span></span></td>
<td><span data-ttu-id="bdb1d-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="bdb1d-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="bdb1d-622">1,495.71</span></span></td>
<td><span data-ttu-id="bdb1d-623">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bdb1d-624">Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="bdb1d-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-625">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-625">Cost object</span></span></th>
<th><span data-ttu-id="bdb1d-626">Ampleur</span><span class="sxs-lookup"><span data-stu-id="bdb1d-626">Magnitude</span></span></th>
<th><span data-ttu-id="bdb1d-627">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="bdb1d-627">Allocation factor</span></span></th>
<th><span data-ttu-id="bdb1d-628">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-628">Amount</span></span></th>
<th><span data-ttu-id="bdb1d-629">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-630">Prod 1</span></span></td>
<td><span data-ttu-id="bdb1d-631">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-631">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-632">80</span><span class="sxs-lookup"><span data-stu-id="bdb1d-632">80</span></span></td>
<td><span data-ttu-id="bdb1d-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="bdb1d-634">241.05</span><span class="sxs-lookup"><span data-stu-id="bdb1d-634">241.05</span></span></td>
<td><span data-ttu-id="bdb1d-635">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-636">Prod 2</span></span></td>
<td><span data-ttu-id="bdb1d-637">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-637">Product 2</span></span></td>
<td><span data-ttu-id="bdb1d-638">15</span><span class="sxs-lookup"><span data-stu-id="bdb1d-638">15</span></span></td>
<td><span data-ttu-id="bdb1d-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="bdb1d-640">45.20</span><span class="sxs-lookup"><span data-stu-id="bdb1d-640">45.20</span></span></td>
<td><span data-ttu-id="bdb1d-641">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-642">Prod 1</span></span></td>
<td><span data-ttu-id="bdb1d-643">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-643">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-644">80</span><span class="sxs-lookup"><span data-stu-id="bdb1d-644">80</span></span></td>
<td><span data-ttu-id="bdb1d-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="bdb1d-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="bdb1d-646">2,507.09</span></span></td>
<td><span data-ttu-id="bdb1d-647">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-648">Prod 2</span></span></td>
<td><span data-ttu-id="bdb1d-649">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-649">Product 2</span></span></td>
<td><span data-ttu-id="bdb1d-650">15</span><span class="sxs-lookup"><span data-stu-id="bdb1d-650">15</span></span></td>
<td><span data-ttu-id="bdb1d-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="bdb1d-652">470.08</span><span class="sxs-lookup"><span data-stu-id="bdb1d-652">470.08</span></span></td>
<td><span data-ttu-id="bdb1d-653">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="bdb1d-654">Entrées du journal (pour le solde d’objet de coût)</span><span class="sxs-lookup"><span data-stu-id="bdb1d-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bdb1d-655">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="bdb1d-655">Journal</span></span></th>
<th><span data-ttu-id="bdb1d-656">Type de journal</span><span class="sxs-lookup"><span data-stu-id="bdb1d-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="bdb1d-657">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="bdb1d-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="bdb1d-658">Version</span><span class="sxs-lookup"><span data-stu-id="bdb1d-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-659">00004</span><span class="sxs-lookup"><span data-stu-id="bdb1d-659">00004</span></span></td>
<td><span data-ttu-id="bdb1d-660">Journal de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="bdb1d-661">Exercice</span><span class="sxs-lookup"><span data-stu-id="bdb1d-661">Fiscal</span></span></td>
<td><span data-ttu-id="bdb1d-662">2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-662">2017</span></span></td>
<td><span data-ttu-id="bdb1d-663">Période 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-663">Period 1</span></span></td>
<td><span data-ttu-id="bdb1d-664">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="bdb1d-665">Lignes de journal</span><span class="sxs-lookup"><span data-stu-id="bdb1d-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bdb1d-666">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-667">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-668">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-668">Cost element</span></span></th>
<th><span data-ttu-id="bdb1d-669">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-669">Cost behavior</span></span></th>
<th><span data-ttu-id="bdb1d-670">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-671">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-672">CC001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-672">CC001</span></span></td>
<td><span data-ttu-id="bdb1d-673">RH</span><span class="sxs-lookup"><span data-stu-id="bdb1d-673">HR</span></span></td>
<td><span data-ttu-id="bdb1d-674">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-674">10001</span></span></td>
<td><span data-ttu-id="bdb1d-675">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-675">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-676">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-676">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-677">500,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-678">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-679">CC001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-679">CC001</span></span></td>
<td><span data-ttu-id="bdb1d-680">RH</span><span class="sxs-lookup"><span data-stu-id="bdb1d-680">HR</span></span></td>
<td><span data-ttu-id="bdb1d-681">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-681">10001</span></span></td>
<td><span data-ttu-id="bdb1d-682">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-682">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-683">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-683">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="bdb1d-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-685">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-686">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-686">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-687">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-687">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-688">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-688">10001</span></span></td>
<td><span data-ttu-id="bdb1d-689">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-689">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-690">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-690">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-691">675.00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-692">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-693">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-693">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-694">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-694">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-695">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-695">10001</span></span></td>
<td><span data-ttu-id="bdb1d-696">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-696">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-697">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-697">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="bdb1d-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-699">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-700">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-700">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-701">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-701">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-702">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-702">10001</span></span></td>
<td><span data-ttu-id="bdb1d-703">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-703">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-704">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-704">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-705">713.75</span><span class="sxs-lookup"><span data-stu-id="bdb1d-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-706">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-707">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-707">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-708">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-708">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-709">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-709">10001</span></span></td>
<td><span data-ttu-id="bdb1d-710">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-710">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-711">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-711">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="bdb1d-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-713">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-714">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-714">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-715">Emballage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-715">Packaging</span></span></td>
<td><span data-ttu-id="bdb1d-716">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-716">10001</span></span></td>
<td><span data-ttu-id="bdb1d-717">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-717">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-718">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-718">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-719">286.25</span><span class="sxs-lookup"><span data-stu-id="bdb1d-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-720">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-721">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-721">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-722">Emballage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-722">Packaging</span></span></td>
<td><span data-ttu-id="bdb1d-723">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-723">10001</span></span></td>
<td><span data-ttu-id="bdb1d-724">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-724">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-725">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-725">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="bdb1d-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-727">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-728">Prod 1</span></span></td>
<td><span data-ttu-id="bdb1d-729">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-729">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-730">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-730">10001</span></span></td>
<td><span data-ttu-id="bdb1d-731">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-731">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-732">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-732">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-733">776.36</span><span class="sxs-lookup"><span data-stu-id="bdb1d-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-734">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-735">Prod 1</span></span></td>
<td><span data-ttu-id="bdb1d-736">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-736">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-737">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-737">10001</span></span></td>
<td><span data-ttu-id="bdb1d-738">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-738">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-739">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-739">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="bdb1d-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-741">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-742">Prod 2</span></span></td>
<td><span data-ttu-id="bdb1d-743">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-743">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-744">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-744">10001</span></span></td>
<td><span data-ttu-id="bdb1d-745">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-745">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-746">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-746">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-747">223.64</span><span class="sxs-lookup"><span data-stu-id="bdb1d-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-748">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="bdb1d-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-749">Prod 2</span></span></td>
<td><span data-ttu-id="bdb1d-750">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-750">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-751">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-751">10001</span></span></td>
<td><span data-ttu-id="bdb1d-752">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-752">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-753">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-753">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="bdb1d-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="bdb1d-755">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bdb1d-756">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bdb1d-757">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-757">Cost element</span></span></th>
<th><span data-ttu-id="bdb1d-758">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="bdb1d-758">Cost behavior</span></span></th>
<th><span data-ttu-id="bdb1d-759">Montant</span><span class="sxs-lookup"><span data-stu-id="bdb1d-759">Amount</span></span></th>
<th><span data-ttu-id="bdb1d-760">Date comptable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bdb1d-761">CC001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-761">CC001</span></span></td>
<td><span data-ttu-id="bdb1d-762">RH</span><span class="sxs-lookup"><span data-stu-id="bdb1d-762">HR</span></span></td>
<td><span data-ttu-id="bdb1d-763">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-763">10001</span></span></td>
<td><span data-ttu-id="bdb1d-764">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-764">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-765">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-765">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-766">-500.00</span></span></td>
<td><span data-ttu-id="bdb1d-767">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-768">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-768">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-769">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-769">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-770">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-770">10001</span></span></td>
<td><span data-ttu-id="bdb1d-771">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-771">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-772">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-772">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-773">175.00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-773">175.00</span></span></td>
<td><span data-ttu-id="bdb1d-774">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-775">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-775">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-776">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-776">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-777">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-777">10001</span></span></td>
<td><span data-ttu-id="bdb1d-778">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-778">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-779">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-779">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-780">275.00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-780">275.00</span></span></td>
<td><span data-ttu-id="bdb1d-781">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-782">CC004</span><span class="sxs-lookup"><span data-stu-id="bdb1d-782">CC004</span></span></td>
<td><span data-ttu-id="bdb1d-783">Emballage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-783">Packaging</span></span></td>
<td><span data-ttu-id="bdb1d-784">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-784">10001</span></span></td>
<td><span data-ttu-id="bdb1d-785">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-785">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-786">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-786">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-787">50,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-787">50,00</span></span></td>
<td><span data-ttu-id="bdb1d-788">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-789">CC001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-789">CC001</span></span></td>
<td><span data-ttu-id="bdb1d-790">RH</span><span class="sxs-lookup"><span data-stu-id="bdb1d-790">HR</span></span></td>
<td><span data-ttu-id="bdb1d-791">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-791">10001</span></span></td>
<td><span data-ttu-id="bdb1d-792">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-792">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-793">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-793">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="bdb1d-794">-1,245.71</span></span></td>
<td><span data-ttu-id="bdb1d-795">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-796">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-796">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-797">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-797">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-798">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-798">10001</span></span></td>
<td><span data-ttu-id="bdb1d-799">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-799">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-800">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-800">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-801">436.00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-801">436.00</span></span></td>
<td><span data-ttu-id="bdb1d-802">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-803">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-803">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-804">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-804">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-805">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-805">10001</span></span></td>
<td><span data-ttu-id="bdb1d-806">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-806">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-807">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-807">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-808">685.14</span><span class="sxs-lookup"><span data-stu-id="bdb1d-808">685.14</span></span></td>
<td><span data-ttu-id="bdb1d-809">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-810">CC004</span><span class="sxs-lookup"><span data-stu-id="bdb1d-810">CC004</span></span></td>
<td><span data-ttu-id="bdb1d-811">Emballage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-811">Packaging</span></span></td>
<td><span data-ttu-id="bdb1d-812">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-812">10001</span></span></td>
<td><span data-ttu-id="bdb1d-813">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-813">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-814">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-814">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-815">124.57</span><span class="sxs-lookup"><span data-stu-id="bdb1d-815">124.57</span></span></td>
<td><span data-ttu-id="bdb1d-816">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-817">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-817">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-818">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-818">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-819">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-819">10001</span></span></td>
<td><span data-ttu-id="bdb1d-820">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-820">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-821">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-821">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-822">-675.00</span></span></td>
<td><span data-ttu-id="bdb1d-823">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-824">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-824">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-825">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-825">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-826">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-826">10001</span></span></td>
<td><span data-ttu-id="bdb1d-827">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-827">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-828">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-828">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-829">438.75</span><span class="sxs-lookup"><span data-stu-id="bdb1d-829">438.75</span></span></td>
<td><span data-ttu-id="bdb1d-830">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-831">CC004</span><span class="sxs-lookup"><span data-stu-id="bdb1d-831">CC004</span></span></td>
<td><span data-ttu-id="bdb1d-832">Emballage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-832">Packaging</span></span></td>
<td><span data-ttu-id="bdb1d-833">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-833">10001</span></span></td>
<td><span data-ttu-id="bdb1d-834">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-834">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-835">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-835">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-836">236.25</span><span class="sxs-lookup"><span data-stu-id="bdb1d-836">236.25</span></span></td>
<td><span data-ttu-id="bdb1d-837">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-838">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-838">CC002</span></span></td>
<td><span data-ttu-id="bdb1d-839">Finances</span><span class="sxs-lookup"><span data-stu-id="bdb1d-839">Finance</span></span></td>
<td><span data-ttu-id="bdb1d-840">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-840">10001</span></span></td>
<td><span data-ttu-id="bdb1d-841">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-841">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-842">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-842">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="bdb1d-843">-8,150.29</span></span></td>
<td><span data-ttu-id="bdb1d-844">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-845">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-845">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-846">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-846">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-847">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-847">10001</span></span></td>
<td><span data-ttu-id="bdb1d-848">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-848">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-849">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-849">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="bdb1d-850">5,297.69</span></span></td>
<td><span data-ttu-id="bdb1d-851">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-852">CC004</span><span class="sxs-lookup"><span data-stu-id="bdb1d-852">CC004</span></span></td>
<td><span data-ttu-id="bdb1d-853">Emballage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-853">Packaging</span></span></td>
<td><span data-ttu-id="bdb1d-854">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-854">10001</span></span></td>
<td><span data-ttu-id="bdb1d-855">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-855">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-856">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-856">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="bdb1d-857">2,852.60</span></span></td>
<td><span data-ttu-id="bdb1d-858">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-859">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-859">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-860">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-860">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-861">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-861">10001</span></span></td>
<td><span data-ttu-id="bdb1d-862">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-862">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-863">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-863">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="bdb1d-864">-713.75</span></span></td>
<td><span data-ttu-id="bdb1d-865">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-866">Prod 1</span></span></td>
<td><span data-ttu-id="bdb1d-867">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-867">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-868">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-868">10001</span></span></td>
<td><span data-ttu-id="bdb1d-869">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-869">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-870">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-870">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-871">535.31</span><span class="sxs-lookup"><span data-stu-id="bdb1d-871">535.31</span></span></td>
<td><span data-ttu-id="bdb1d-872">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-873">Prod 2</span></span></td>
<td><span data-ttu-id="bdb1d-874">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-874">Product 2</span></span></td>
<td><span data-ttu-id="bdb1d-875">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-875">10001</span></span></td>
<td><span data-ttu-id="bdb1d-876">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-876">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-877">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-877">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-878">178.44</span><span class="sxs-lookup"><span data-stu-id="bdb1d-878">178.44</span></span></td>
<td><span data-ttu-id="bdb1d-879">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-880">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-880">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-881">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-881">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-882">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-882">10001</span></span></td>
<td><span data-ttu-id="bdb1d-883">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-883">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-884">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-884">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="bdb1d-885">-5,982.83</span></span></td>
<td><span data-ttu-id="bdb1d-886">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-887">Prod 1</span></span></td>
<td><span data-ttu-id="bdb1d-888">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-888">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-889">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-889">10001</span></span></td>
<td><span data-ttu-id="bdb1d-890">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-890">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-891">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-891">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="bdb1d-892">4,487.12</span></span></td>
<td><span data-ttu-id="bdb1d-893">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-894">Prod 2</span></span></td>
<td><span data-ttu-id="bdb1d-895">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-895">Product 2</span></span></td>
<td><span data-ttu-id="bdb1d-896">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-896">10001</span></span></td>
<td><span data-ttu-id="bdb1d-897">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-897">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-898">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-898">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="bdb1d-899">1,495.71</span></span></td>
<td><span data-ttu-id="bdb1d-900">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-901">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-901">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-902">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-902">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-903">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-903">10001</span></span></td>
<td><span data-ttu-id="bdb1d-904">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-904">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-905">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-905">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="bdb1d-906">-286.25</span></span></td>
<td><span data-ttu-id="bdb1d-907">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-908">Prod 1</span></span></td>
<td><span data-ttu-id="bdb1d-909">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-909">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-910">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-910">10001</span></span></td>
<td><span data-ttu-id="bdb1d-911">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-911">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-912">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-912">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-913">241.05</span><span class="sxs-lookup"><span data-stu-id="bdb1d-913">241.05</span></span></td>
<td><span data-ttu-id="bdb1d-914">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-915">Prod 2</span></span></td>
<td><span data-ttu-id="bdb1d-916">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-916">Product 2</span></span></td>
<td><span data-ttu-id="bdb1d-917">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-917">10001</span></span></td>
<td><span data-ttu-id="bdb1d-918">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-918">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-919">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-919">Fixed cost</span></span></td>
<td><span data-ttu-id="bdb1d-920">45.20</span><span class="sxs-lookup"><span data-stu-id="bdb1d-920">45.20</span></span></td>
<td><span data-ttu-id="bdb1d-921">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-922">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-922">CC003</span></span></td>
<td><span data-ttu-id="bdb1d-923">Assemblage</span><span class="sxs-lookup"><span data-stu-id="bdb1d-923">Assembly</span></span></td>
<td><span data-ttu-id="bdb1d-924">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-924">10001</span></span></td>
<td><span data-ttu-id="bdb1d-925">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-925">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-926">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-926">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="bdb1d-927">-2,977.17</span></span></td>
<td><span data-ttu-id="bdb1d-928">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-929">Prod 1</span></span></td>
<td><span data-ttu-id="bdb1d-930">Produit 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-930">Product 1</span></span></td>
<td><span data-ttu-id="bdb1d-931">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-931">10001</span></span></td>
<td><span data-ttu-id="bdb1d-932">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-932">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-933">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-933">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="bdb1d-934">2,507.09</span></span></td>
<td><span data-ttu-id="bdb1d-935">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bdb1d-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-936">Prod 2</span></span></td>
<td><span data-ttu-id="bdb1d-937">Produit 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-937">Product 2</span></span></td>
<td><span data-ttu-id="bdb1d-938">10001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-938">10001</span></span></td>
<td><span data-ttu-id="bdb1d-939">Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-939">Electricity</span></span></td>
<td><span data-ttu-id="bdb1d-940">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-940">Variable cost</span></span></td>
<td><span data-ttu-id="bdb1d-941">470.08</span><span class="sxs-lookup"><span data-stu-id="bdb1d-941">470.08</span></span></td>
<td><span data-ttu-id="bdb1d-942">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="bdb1d-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="bdb1d-943">Conclusion</span><span class="sxs-lookup"><span data-stu-id="bdb1d-943">Conclusion</span></span>
<span data-ttu-id="bdb1d-944">Dans la comptabilité financière, un coût de 10 000,00 pour l’électricité est imputé sur un ID de centre de coût fictif.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="bdb1d-945">Par conséquent, les comptables sauront que ce coût doit être affecté.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="bdb1d-946">Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l’organisation, selon les stratégies et les règles qui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="bdb1d-947">Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="bdb1d-948">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="bdb1d-949">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="bdb1d-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="bdb1d-950">Total</span><span class="sxs-lookup"><span data-stu-id="bdb1d-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="bdb1d-951">CC099</span><span class="sxs-lookup"><span data-stu-id="bdb1d-951">CC099</span></span></th>
<th><span data-ttu-id="bdb1d-952">CC001</span><span class="sxs-lookup"><span data-stu-id="bdb1d-952">CC001</span></span></th>
<th><span data-ttu-id="bdb1d-953">CC002</span><span class="sxs-lookup"><span data-stu-id="bdb1d-953">CC002</span></span></th>
<th><span data-ttu-id="bdb1d-954">CC003</span><span class="sxs-lookup"><span data-stu-id="bdb1d-954">CC003</span></span></th>
<th><span data-ttu-id="bdb1d-955">CC004</span><span class="sxs-lookup"><span data-stu-id="bdb1d-955">CC004</span></span></th>
<th><span data-ttu-id="bdb1d-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-956">Proj 1</span></span></th>
<th><span data-ttu-id="bdb1d-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-957">Proj 2</span></span></th>
<th><span data-ttu-id="bdb1d-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="bdb1d-958">Prod 1</span></span></th>
<th><span data-ttu-id="bdb1d-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="bdb1d-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="bdb1d-960">10001 Électricité</span><span class="sxs-lookup"><span data-stu-id="bdb1d-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="bdb1d-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="bdb1d-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="bdb1d-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="bdb1d-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="bdb1d-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="bdb1d-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="bdb1d-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="bdb1d-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="bdb1d-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="bdb1d-970">Non classifié</span><span class="sxs-lookup"><span data-stu-id="bdb1d-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-971">0,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="bdb1d-972">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="bdb1d-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-973">0,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-974">0,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-975">0,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-976">0,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-977">0,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-978">776.36</span><span class="sxs-lookup"><span data-stu-id="bdb1d-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-979">223.64</span><span class="sxs-lookup"><span data-stu-id="bdb1d-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-980"><strong>1 000,00</strong></span><span class="sxs-lookup"><span data-stu-id="bdb1d-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="bdb1d-981">Coût variable</span><span class="sxs-lookup"><span data-stu-id="bdb1d-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-982">000</span><span class="sxs-lookup"><span data-stu-id="bdb1d-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-983">0,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-984">0,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-985">0,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-986">0,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-987">30,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-988">10,00</span><span class="sxs-lookup"><span data-stu-id="bdb1d-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="bdb1d-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="bdb1d-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bdb1d-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="bdb1d-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="bdb1d-992">Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="bdb1d-993">Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="bdb1d-994">Autrement dit, les objets de coût de plus bas niveau supportent le coût.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="bdb1d-995">Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="bdb1d-996">Pour plus d’informations, voir [Stratégie de repositionnement des coûts et calcul des frais généraux](cost-rollup.md)..</span><span class="sxs-lookup"><span data-stu-id="bdb1d-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



