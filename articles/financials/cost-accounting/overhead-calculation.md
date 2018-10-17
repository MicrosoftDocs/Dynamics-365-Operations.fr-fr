---
title: "Calcul des frais généraux"
description: "Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux."
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 12ae99c15bafcd9cc08b30903fe3f251f446b17d
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.contentlocale: fr-fr
ms.lasthandoff: 10/05/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="f741f-103">Calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="f741f-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f741f-104">Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="f741f-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="f741f-105">Définition des termes</span><span class="sxs-lookup"><span data-stu-id="f741f-105">Term definition</span></span>
---------------

<span data-ttu-id="f741f-106">Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique.</span><span class="sxs-lookup"><span data-stu-id="f741f-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="f741f-107">Les frais généraux permettent essentiellement l'identification des activités rémunératrices.</span><span class="sxs-lookup"><span data-stu-id="f741f-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="f741f-108">Voici quelques exemples de frais généraux :</span><span class="sxs-lookup"><span data-stu-id="f741f-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="f741f-109">Loyer</span><span class="sxs-lookup"><span data-stu-id="f741f-109">Rent</span></span>
-   <span data-ttu-id="f741f-110">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-110">Electricity</span></span>
-   <span data-ttu-id="f741f-111">Salaires administratifs</span><span class="sxs-lookup"><span data-stu-id="f741f-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="f741f-112">Vue d'ensemble du calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="f741f-112">Overhead calculation overview</span></span>
<span data-ttu-id="f741f-113">Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l'ordre correct.</span><span class="sxs-lookup"><span data-stu-id="f741f-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="f741f-114">Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées.</span><span class="sxs-lookup"><span data-stu-id="f741f-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="f741f-115">Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions.</span><span class="sxs-lookup"><span data-stu-id="f741f-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="f741f-116">Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable.</span><span class="sxs-lookup"><span data-stu-id="f741f-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="f741f-117">Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="f741f-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="f741f-118">L'ID de version unique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f741f-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="f741f-119">Type de version</span><span class="sxs-lookup"><span data-stu-id="f741f-119">Version type</span></span>
-   <span data-ttu-id="f741f-120">Date et heure</span><span class="sxs-lookup"><span data-stu-id="f741f-120">Date and time</span></span>
-   <span data-ttu-id="f741f-121">Comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="f741f-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="f741f-122">Exercice</span><span class="sxs-lookup"><span data-stu-id="f741f-122">Fiscal year</span></span>
-   <span data-ttu-id="f741f-123">Période fiscale</span><span class="sxs-lookup"><span data-stu-id="f741f-123">Fiscal period</span></span>

<span data-ttu-id="f741f-124">Le calcul des frais généraux est effectué indépendamment de la version.</span><span class="sxs-lookup"><span data-stu-id="f741f-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="f741f-125">Par conséquent, vous pouvez calculer la version de budget avant la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="f741f-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="f741f-126">Le calcul des frais généraux comporte quatre étapes, comme le montre l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="f741f-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="f741f-127">Dans chaque étape, un en-tête de journal avec des entrées de journal est créé.</span><span class="sxs-lookup"><span data-stu-id="f741f-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="f741f-128">Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul.</span><span class="sxs-lookup"><span data-stu-id="f741f-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="f741f-129">Les stratégies et les règles s'appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie.</span><span class="sxs-lookup"><span data-stu-id="f741f-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="f741f-130">Par conséquent, vous disposez toujours d'une traçabilité complète.</span><span class="sxs-lookup"><span data-stu-id="f741f-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="f741f-131">[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="f741f-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="f741f-132">Calculer et affecter les frais généraux Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="f741f-133">Dans la comptabilité financière, certaines coûts, tels que l'électricité, sont enregistrés comme montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="f741f-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="f741f-134">Par conséquent, l'analyse détaillée n'est pas fournie pour le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="f741f-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="f741f-135">Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l'organisation, les coûts doivent suivre les unités organisationnelles.</span><span class="sxs-lookup"><span data-stu-id="f741f-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="f741f-136">Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste.</span><span class="sxs-lookup"><span data-stu-id="f741f-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="f741f-137">Dans la comptabilité, le coût de l'électricité peut être validé comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="f741f-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f741f-138">Date comptable</span><span class="sxs-lookup"><span data-stu-id="f741f-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-139">Centre de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-140">Compte principal</span><span class="sxs-lookup"><span data-stu-id="f741f-140">Main account</span></span></th>
<th><span data-ttu-id="f741f-141">Montant en devise comptable</span><span class="sxs-lookup"><span data-stu-id="f741f-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-142">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="f741f-143">CC099</span><span class="sxs-lookup"><span data-stu-id="f741f-143">CC099</span></span></td>
<td><span data-ttu-id="f741f-144">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="f741f-144">Default cost center</span></span></td>
<td><span data-ttu-id="f741f-145">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-145">10001</span></span></td>
<td><span data-ttu-id="f741f-146">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-146">Electricity</span></span></td>
<td><span data-ttu-id="f741f-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="f741f-148">Étape 1 : Traiter le calcul du comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="f741f-149">Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="f741f-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="f741f-150">Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.</span><span class="sxs-lookup"><span data-stu-id="f741f-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="f741f-151">Définir la règle de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-151">Define the cost behavior rule</span></span>

<span data-ttu-id="f741f-152">Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation.</span><span class="sxs-lookup"><span data-stu-id="f741f-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="f741f-153">Les factures d'électricité correspondent souvent à cette définition.</span><span class="sxs-lookup"><span data-stu-id="f741f-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="f741f-154">Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH).</span><span class="sxs-lookup"><span data-stu-id="f741f-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="f741f-155">Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :</span><span class="sxs-lookup"><span data-stu-id="f741f-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="f741f-156">Montant fixe 1 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="f741f-157">0 &lt;= 1 000,00 = Fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="f741f-158">1 000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="f741f-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="f741f-159">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="f741f-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f741f-160">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="f741f-160">Journal</span></span></th>
<th><span data-ttu-id="f741f-161">Type de journal</span><span class="sxs-lookup"><span data-stu-id="f741f-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="f741f-162">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="f741f-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="f741f-163">Version</span><span class="sxs-lookup"><span data-stu-id="f741f-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-164">00001</span><span class="sxs-lookup"><span data-stu-id="f741f-164">00001</span></span></td>
<td><span data-ttu-id="f741f-165">Journal de calcul de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="f741f-166">Exercice</span><span class="sxs-lookup"><span data-stu-id="f741f-166">Fiscal</span></span></td>
<td><span data-ttu-id="f741f-167">2017</span><span class="sxs-lookup"><span data-stu-id="f741f-167">2017</span></span></td>
<td><span data-ttu-id="f741f-168">Période 1</span><span class="sxs-lookup"><span data-stu-id="f741f-168">Period 1</span></span></td>
<td><span data-ttu-id="f741f-169">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="f741f-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="f741f-170">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="f741f-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f741f-171">Date comptable</span><span class="sxs-lookup"><span data-stu-id="f741f-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-172">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-173">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-173">Cost element</span></span></th>
<th><span data-ttu-id="f741f-174">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-174">Cost behavior</span></span></th>
<th><span data-ttu-id="f741f-175">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-176">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="f741f-177">CC099</span><span class="sxs-lookup"><span data-stu-id="f741f-177">CC099</span></span></td>
<td><span data-ttu-id="f741f-178">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="f741f-178">Default cost center</span></span></td>
<td><span data-ttu-id="f741f-179">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-179">10001</span></span></td>
<td><span data-ttu-id="f741f-180">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-180">Electricity</span></span></td>
<td><span data-ttu-id="f741f-181">Non classifié</span><span class="sxs-lookup"><span data-stu-id="f741f-181">Unclassified</span></span></td>
<td><span data-ttu-id="f741f-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="f741f-183">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-184">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-185">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-185">Cost element</span></span></th>
<th><span data-ttu-id="f741f-186">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-186">Cost behavior</span></span></th>
<th><span data-ttu-id="f741f-187">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-187">Amount</span></span></th>
<th><span data-ttu-id="f741f-188">Date comptable</span><span class="sxs-lookup"><span data-stu-id="f741f-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-189">CC099</span><span class="sxs-lookup"><span data-stu-id="f741f-189">CC099</span></span></td>
<td><span data-ttu-id="f741f-190">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="f741f-190">Default cost center</span></span></td>
<td><span data-ttu-id="f741f-191">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-191">10001</span></span></td>
<td><span data-ttu-id="f741f-192">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-192">Electricity</span></span></td>
<td><span data-ttu-id="f741f-193">Non classifié</span><span class="sxs-lookup"><span data-stu-id="f741f-193">Unclassified</span></span></td>
<td><span data-ttu-id="f741f-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-194">10,000.00</span></span></td>
<td><span data-ttu-id="f741f-195">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-196">CC099</span><span class="sxs-lookup"><span data-stu-id="f741f-196">CC099</span></span></td>
<td><span data-ttu-id="f741f-197">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="f741f-197">Default cost center</span></span></td>
<td><span data-ttu-id="f741f-198">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-198">10001</span></span></td>
<td><span data-ttu-id="f741f-199">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-199">Electricity</span></span></td>
<td><span data-ttu-id="f741f-200">Non classifié</span><span class="sxs-lookup"><span data-stu-id="f741f-200">Unclassified</span></span></td>
<td><span data-ttu-id="f741f-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-201">-10,000.00</span></span></td>
<td><span data-ttu-id="f741f-202">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-203">CC099</span><span class="sxs-lookup"><span data-stu-id="f741f-203">CC099</span></span></td>
<td><span data-ttu-id="f741f-204">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="f741f-204">Default cost center</span></span></td>
<td><span data-ttu-id="f741f-205">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-205">10001</span></span></td>
<td><span data-ttu-id="f741f-206">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-206">Electricity</span></span></td>
<td><span data-ttu-id="f741f-207">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-207">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-208">1,000.00</span></span></td>
<td><span data-ttu-id="f741f-209">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-210">CC099</span><span class="sxs-lookup"><span data-stu-id="f741f-210">CC099</span></span></td>
<td><span data-ttu-id="f741f-211">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="f741f-211">Default cost center</span></span></td>
<td><span data-ttu-id="f741f-212">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-212">10001</span></span></td>
<td><span data-ttu-id="f741f-213">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-213">Electricity</span></span></td>
<td><span data-ttu-id="f741f-214">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-214">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-215">9 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-215">9,000.00</span></span></td>
<td><span data-ttu-id="f741f-216">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-217">Pour plus d'informations, voir [Créer et affecter une stratégie de comportement de coûts à une unité de contrôle des coûts](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="f741f-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="f741f-218">Étape 2 : Traiter le calcul de distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="f741f-219">La distribution des coûts est utilisée pour redistribuer le coût d'un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée.</span><span class="sxs-lookup"><span data-stu-id="f741f-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="f741f-220">La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l'élément de coût principal du coût d'origine.</span><span class="sxs-lookup"><span data-stu-id="f741f-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="f741f-221">Définir la règle de distribution de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-221">Define the cost distribution rule</span></span>

<span data-ttu-id="f741f-222">Dans la comptabilité financière, les coûts d'électricité sont souvent enregistrés comme un montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="f741f-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="f741f-223">Dans le Contrôle de gestion, cette approche n'est pas assez détaillée.</span><span class="sxs-lookup"><span data-stu-id="f741f-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="f741f-224">Le coût variable doit être attribué aux différents objets de coûts sur une base juste.</span><span class="sxs-lookup"><span data-stu-id="f741f-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="f741f-225">La base de répartition la plus logique est la consommation de l'électricité (KWH).</span><span class="sxs-lookup"><span data-stu-id="f741f-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="f741f-226">Un membre de dimension statistique nommé Électricité est créé, et la consommation d'électricité est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="f741f-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="f741f-227">Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="f741f-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-228">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-228">Cost object</span></span></th>
<th><span data-ttu-id="f741f-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="f741f-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-230">CC001</span><span class="sxs-lookup"><span data-stu-id="f741f-230">CC001</span></span></td>
<td><span data-ttu-id="f741f-231">RH</span><span class="sxs-lookup"><span data-stu-id="f741f-231">HR</span></span></td>
<td><span data-ttu-id="f741f-232">1 000</span><span class="sxs-lookup"><span data-stu-id="f741f-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-233">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-233">CC002</span></span></td>
<td><span data-ttu-id="f741f-234">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-234">Finance</span></span></td>
<td><span data-ttu-id="f741f-235">6 000</span><span class="sxs-lookup"><span data-stu-id="f741f-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-236">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-236">CC003</span></span></td>
<td><span data-ttu-id="f741f-237">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-237">Assembly</span></span></td>
<td><span data-ttu-id="f741f-238">0</span><span class="sxs-lookup"><span data-stu-id="f741f-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-239">Le tableau suivant illustre le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="f741f-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-240">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-240">Cost object</span></span></th>
<th><span data-ttu-id="f741f-241">Ampleur</span><span class="sxs-lookup"><span data-stu-id="f741f-241">Magnitude</span></span></th>
<th><span data-ttu-id="f741f-242">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="f741f-242">Allocation factor</span></span></th>
<th><span data-ttu-id="f741f-243">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-244">CC001</span><span class="sxs-lookup"><span data-stu-id="f741f-244">CC001</span></span></td>
<td><span data-ttu-id="f741f-245">RH</span><span class="sxs-lookup"><span data-stu-id="f741f-245">HR</span></span></td>
<td><span data-ttu-id="f741f-246">1 000</span><span class="sxs-lookup"><span data-stu-id="f741f-246">1,000</span></span></td>
<td><span data-ttu-id="f741f-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="f741f-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="f741f-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-249">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-249">CC002</span></span></td>
<td><span data-ttu-id="f741f-250">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-250">Finance</span></span></td>
<td><span data-ttu-id="f741f-251">6 000</span><span class="sxs-lookup"><span data-stu-id="f741f-251">6,000</span></span></td>
<td><span data-ttu-id="f741f-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="f741f-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="f741f-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-254">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-254">CC003</span></span></td>
<td><span data-ttu-id="f741f-255">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-255">Assembly</span></span></td>
<td><span data-ttu-id="f741f-256">0</span><span class="sxs-lookup"><span data-stu-id="f741f-256">0</span></span></td>
<td><span data-ttu-id="f741f-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="f741f-258">0,00</span><span class="sxs-lookup"><span data-stu-id="f741f-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-259">Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l'électricité.</span><span class="sxs-lookup"><span data-stu-id="f741f-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="f741f-260">Vous pouvez obtenir ce résultat à l'aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="f741f-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-261">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-261">Cost object</span></span></th>
<th><span data-ttu-id="f741f-262">Formule</span><span class="sxs-lookup"><span data-stu-id="f741f-262">Formula</span></span></th>
<th><span data-ttu-id="f741f-263">Ampleur</span><span class="sxs-lookup"><span data-stu-id="f741f-263">Magnitude</span></span></th>
<th><span data-ttu-id="f741f-264">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="f741f-264">Allocation factor</span></span></th>
<th><span data-ttu-id="f741f-265">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-266">CC001</span><span class="sxs-lookup"><span data-stu-id="f741f-266">CC001</span></span></td>
<td><span data-ttu-id="f741f-267">RH</span><span class="sxs-lookup"><span data-stu-id="f741f-267">HR</span></span></td>
<td><span data-ttu-id="f741f-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="f741f-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="f741f-269">1</span><span class="sxs-lookup"><span data-stu-id="f741f-269">1</span></span></td>
<td><span data-ttu-id="f741f-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="f741f-271">500,00</span><span class="sxs-lookup"><span data-stu-id="f741f-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-272">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-272">CC002</span></span></td>
<td><span data-ttu-id="f741f-273">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-273">Finance</span></span></td>
<td><span data-ttu-id="f741f-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="f741f-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="f741f-275">1</span><span class="sxs-lookup"><span data-stu-id="f741f-275">1</span></span></td>
<td><span data-ttu-id="f741f-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="f741f-277">500,00</span><span class="sxs-lookup"><span data-stu-id="f741f-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-278">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-278">CC003</span></span></td>
<td><span data-ttu-id="f741f-279">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-279">Assembly</span></span></td>
<td><span data-ttu-id="f741f-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="f741f-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="f741f-281">0</span><span class="sxs-lookup"><span data-stu-id="f741f-281">0</span></span></td>
<td><span data-ttu-id="f741f-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="f741f-283">0,00</span><span class="sxs-lookup"><span data-stu-id="f741f-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="f741f-284">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="f741f-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f741f-285">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="f741f-285">Journal</span></span></th>
<th><span data-ttu-id="f741f-286">Type de journal</span><span class="sxs-lookup"><span data-stu-id="f741f-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="f741f-287">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="f741f-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="f741f-288">Version</span><span class="sxs-lookup"><span data-stu-id="f741f-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-289">00002</span><span class="sxs-lookup"><span data-stu-id="f741f-289">00002</span></span></td>
<td><span data-ttu-id="f741f-290">Journal de calcul de la distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="f741f-291">Exercice</span><span class="sxs-lookup"><span data-stu-id="f741f-291">Fiscal</span></span></td>
<td><span data-ttu-id="f741f-292">2017</span><span class="sxs-lookup"><span data-stu-id="f741f-292">2017</span></span></td>
<td><span data-ttu-id="f741f-293">Période 1</span><span class="sxs-lookup"><span data-stu-id="f741f-293">Period 1</span></span></td>
<td><span data-ttu-id="f741f-294">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="f741f-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="f741f-295">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="f741f-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f741f-296">Date comptable</span><span class="sxs-lookup"><span data-stu-id="f741f-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-297">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-298">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-298">Cost element</span></span></th>
<th><span data-ttu-id="f741f-299">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-299">Cost behavior</span></span></th>
<th><span data-ttu-id="f741f-300">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-301">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-302">CC099</span><span class="sxs-lookup"><span data-stu-id="f741f-302">CC099</span></span></td>
<td><span data-ttu-id="f741f-303">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="f741f-303">Default cost center</span></span></td>
<td><span data-ttu-id="f741f-304">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-304">10001</span></span></td>
<td><span data-ttu-id="f741f-305">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-305">Electricity</span></span></td>
<td><span data-ttu-id="f741f-306">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-306">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-308">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-309">CC099</span><span class="sxs-lookup"><span data-stu-id="f741f-309">CC099</span></span></td>
<td><span data-ttu-id="f741f-310">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="f741f-310">Default cost center</span></span></td>
<td><span data-ttu-id="f741f-311">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-311">10001</span></span></td>
<td><span data-ttu-id="f741f-312">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-312">Electricity</span></span></td>
<td><span data-ttu-id="f741f-313">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-313">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-314">9 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="f741f-315">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-316">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-317">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-317">Cost element</span></span></th>
<th><span data-ttu-id="f741f-318">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-318">Cost behavior</span></span></th>
<th><span data-ttu-id="f741f-319">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-319">Amount</span></span></th>
<th><span data-ttu-id="f741f-320">Date comptable</span><span class="sxs-lookup"><span data-stu-id="f741f-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-321">CC099</span><span class="sxs-lookup"><span data-stu-id="f741f-321">CC099</span></span></td>
<td><span data-ttu-id="f741f-322">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="f741f-322">Default cost center</span></span></td>
<td><span data-ttu-id="f741f-323">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-323">10001</span></span></td>
<td><span data-ttu-id="f741f-324">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-324">Electricity</span></span></td>
<td><span data-ttu-id="f741f-325">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-325">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-326">-1,000.00</span></span></td>
<td><span data-ttu-id="f741f-327">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-328">CC001</span><span class="sxs-lookup"><span data-stu-id="f741f-328">CC001</span></span></td>
<td><span data-ttu-id="f741f-329">RH</span><span class="sxs-lookup"><span data-stu-id="f741f-329">HR</span></span></td>
<td><span data-ttu-id="f741f-330">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-330">10001</span></span></td>
<td><span data-ttu-id="f741f-331">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-331">Electricity</span></span></td>
<td><span data-ttu-id="f741f-332">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-332">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-333">500,00</span><span class="sxs-lookup"><span data-stu-id="f741f-333">500.00</span></span></td>
<td><span data-ttu-id="f741f-334">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-335">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-335">CC002</span></span></td>
<td><span data-ttu-id="f741f-336">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-336">Finance</span></span></td>
<td><span data-ttu-id="f741f-337">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-337">10001</span></span></td>
<td><span data-ttu-id="f741f-338">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-338">Electricity</span></span></td>
<td><span data-ttu-id="f741f-339">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-339">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-340">500,00</span><span class="sxs-lookup"><span data-stu-id="f741f-340">500.00</span></span></td>
<td><span data-ttu-id="f741f-341">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-342">CC099</span><span class="sxs-lookup"><span data-stu-id="f741f-342">CC099</span></span></td>
<td><span data-ttu-id="f741f-343">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="f741f-343">Default cost center</span></span></td>
<td><span data-ttu-id="f741f-344">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-344">10001</span></span></td>
<td><span data-ttu-id="f741f-345">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-345">Electricity</span></span></td>
<td><span data-ttu-id="f741f-346">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-346">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="f741f-347">-9,000.00</span></span></td>
<td><span data-ttu-id="f741f-348">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-349">CC001</span><span class="sxs-lookup"><span data-stu-id="f741f-349">CC001</span></span></td>
<td><span data-ttu-id="f741f-350">RH</span><span class="sxs-lookup"><span data-stu-id="f741f-350">HR</span></span></td>
<td><span data-ttu-id="f741f-351">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-351">10001</span></span></td>
<td><span data-ttu-id="f741f-352">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-352">Electricity</span></span></td>
<td><span data-ttu-id="f741f-353">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-353">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="f741f-354">1,285.71</span></span></td>
<td><span data-ttu-id="f741f-355">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-356">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-356">CC002</span></span></td>
<td><span data-ttu-id="f741f-357">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-357">Finance</span></span></td>
<td><span data-ttu-id="f741f-358">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-358">10001</span></span></td>
<td><span data-ttu-id="f741f-359">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-359">Electricity</span></span></td>
<td><span data-ttu-id="f741f-360">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-360">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="f741f-361">7,714.29</span></span></td>
<td><span data-ttu-id="f741f-362">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-363">Pour plus d'informations, voir [Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="f741f-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="f741f-364">Étape 3 : Traitement du calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="f741f-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="f741f-365">Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût.</span><span class="sxs-lookup"><span data-stu-id="f741f-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="f741f-366">Les frais sont basés sur un taux de coût prédéterminé et l'ampleur de la base d'affectation de répartition.</span><span class="sxs-lookup"><span data-stu-id="f741f-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="f741f-367">Définition du taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="f741f-367">Define the overhead rate</span></span>

<span data-ttu-id="f741f-368">L'objet de coût CC001 HR contribue à un ensemble de projets internes.</span><span class="sxs-lookup"><span data-stu-id="f741f-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="f741f-369">Un membre de dimension statistique nommé Projets HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="f741f-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-370">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-370">Cost object</span></span></th>
<th><span data-ttu-id="f741f-371">Heures</span><span class="sxs-lookup"><span data-stu-id="f741f-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="f741f-372">Proj 1</span></span></td>
<td><span data-ttu-id="f741f-373">Projet 1</span><span class="sxs-lookup"><span data-stu-id="f741f-373">Project 1</span></span></td>
<td><span data-ttu-id="f741f-374">3</span><span class="sxs-lookup"><span data-stu-id="f741f-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="f741f-375">Proj 2</span></span></td>
<td><span data-ttu-id="f741f-376">Projet 2</span><span class="sxs-lookup"><span data-stu-id="f741f-376">Project 2</span></span></td>
<td><span data-ttu-id="f741f-377">1</span><span class="sxs-lookup"><span data-stu-id="f741f-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-378">Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.</span><span class="sxs-lookup"><span data-stu-id="f741f-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-379">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-379">Cost object</span></span></th>
<th><span data-ttu-id="f741f-380">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-380">Cost element</span></span></th>
<th><span data-ttu-id="f741f-381">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-381">Cost behavior</span></span></th>
<th><span data-ttu-id="f741f-382">Unités</span><span class="sxs-lookup"><span data-stu-id="f741f-382">Units</span></span></th>
<th><span data-ttu-id="f741f-383">Taux</span><span class="sxs-lookup"><span data-stu-id="f741f-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-384">CC001</span><span class="sxs-lookup"><span data-stu-id="f741f-384">CC001</span></span></td>
<td><span data-ttu-id="f741f-385">RH</span><span class="sxs-lookup"><span data-stu-id="f741f-385">HR</span></span></td>
<td><span data-ttu-id="f741f-386">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-386">10001</span></span></td>
<td><span data-ttu-id="f741f-387">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-387">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-388">1</span><span class="sxs-lookup"><span data-stu-id="f741f-388">1</span></span></td>
<td><span data-ttu-id="f741f-389">10</span><span class="sxs-lookup"><span data-stu-id="f741f-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-390">Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="f741f-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-391">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-391">Cost object</span></span></th>
<th><span data-ttu-id="f741f-392">Ampleur</span><span class="sxs-lookup"><span data-stu-id="f741f-392">Magnitude</span></span></th>
<th><span data-ttu-id="f741f-393">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-393">Cost element</span></span></th>
<th><span data-ttu-id="f741f-394">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="f741f-394">Allocation factor</span></span></th>
<th><span data-ttu-id="f741f-395">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="f741f-396">Proj 1</span></span></td>
<td><span data-ttu-id="f741f-397">Projet 1</span><span class="sxs-lookup"><span data-stu-id="f741f-397">Project 1</span></span></td>
<td><span data-ttu-id="f741f-398">3</span><span class="sxs-lookup"><span data-stu-id="f741f-398">3</span></span></td>
<td><span data-ttu-id="f741f-399">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-399">10001</span></span></td>
<td><span data-ttu-id="f741f-400">(3 ÷ 1) × 10m00</span><span class="sxs-lookup"><span data-stu-id="f741f-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="f741f-401">30,00</span><span class="sxs-lookup"><span data-stu-id="f741f-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="f741f-402">Proj 2</span></span></td>
<td><span data-ttu-id="f741f-403">Projet 2</span><span class="sxs-lookup"><span data-stu-id="f741f-403">Project 2</span></span></td>
<td><span data-ttu-id="f741f-404">1</span><span class="sxs-lookup"><span data-stu-id="f741f-404">1</span></span></td>
<td><span data-ttu-id="f741f-405">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-405">10001</span></span></td>
<td><span data-ttu-id="f741f-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="f741f-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="f741f-407">10,00</span><span class="sxs-lookup"><span data-stu-id="f741f-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="f741f-408">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="f741f-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f741f-409">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="f741f-409">Journal</span></span></th>
<th><span data-ttu-id="f741f-410">Type de journal</span><span class="sxs-lookup"><span data-stu-id="f741f-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="f741f-411">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="f741f-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="f741f-412">Version</span><span class="sxs-lookup"><span data-stu-id="f741f-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-413">00003</span><span class="sxs-lookup"><span data-stu-id="f741f-413">00003</span></span></td>
<td><span data-ttu-id="f741f-414">Journal de calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="f741f-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="f741f-415">Exercice</span><span class="sxs-lookup"><span data-stu-id="f741f-415">Fiscal</span></span></td>
<td><span data-ttu-id="f741f-416">2017</span><span class="sxs-lookup"><span data-stu-id="f741f-416">2017</span></span></td>
<td><span data-ttu-id="f741f-417">Période 1</span><span class="sxs-lookup"><span data-stu-id="f741f-417">Period 1</span></span></td>
<td><span data-ttu-id="f741f-418">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="f741f-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="f741f-419">Entrées du journal (pour le calcul du taux de frais généraux)</span><span class="sxs-lookup"><span data-stu-id="f741f-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f741f-420">Date comptable</span><span class="sxs-lookup"><span data-stu-id="f741f-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-421">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-421">Cost object</span></span></th>
<th><span data-ttu-id="f741f-422">Ampleur</span><span class="sxs-lookup"><span data-stu-id="f741f-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-423">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="f741f-424">Proj 1</span></span></td>
<td><span data-ttu-id="f741f-425">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="f741f-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="f741f-426">3,00</span><span class="sxs-lookup"><span data-stu-id="f741f-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-427">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="f741f-428">Proj 2</span></span></td>
<td><span data-ttu-id="f741f-429">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="f741f-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="f741f-430">1,00</span><span class="sxs-lookup"><span data-stu-id="f741f-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="f741f-431">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-432">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-433">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-433">Cost element</span></span></th>
<th><span data-ttu-id="f741f-434">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-434">Cost behavior</span></span></th>
<th><span data-ttu-id="f741f-435">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-435">Amount</span></span></th>
<th><span data-ttu-id="f741f-436">Date comptable</span><span class="sxs-lookup"><span data-stu-id="f741f-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="f741f-437">CC0001</span></span></td>
<td><span data-ttu-id="f741f-438">RH</span><span class="sxs-lookup"><span data-stu-id="f741f-438">HR</span></span></td>
<td><span data-ttu-id="f741f-439">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-439">10001</span></span></td>
<td><span data-ttu-id="f741f-440">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-440">Electricity</span></span></td>
<td><span data-ttu-id="f741f-441">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-441">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="f741f-442">-30.00</span></span></td>
<td><span data-ttu-id="f741f-443">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="f741f-444">Proj 1</span></span></td>
<td><span data-ttu-id="f741f-445">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="f741f-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="f741f-446">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-446">10001</span></span></td>
<td><span data-ttu-id="f741f-447">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-447">Electricity</span></span></td>
<td><span data-ttu-id="f741f-448">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-448">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-449">30,00</span><span class="sxs-lookup"><span data-stu-id="f741f-449">30.00</span></span></td>
<td><span data-ttu-id="f741f-450">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-451">CC001</span><span class="sxs-lookup"><span data-stu-id="f741f-451">CC001</span></span></td>
<td><span data-ttu-id="f741f-452">RH</span><span class="sxs-lookup"><span data-stu-id="f741f-452">HR</span></span></td>
<td><span data-ttu-id="f741f-453">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-453">10001</span></span></td>
<td><span data-ttu-id="f741f-454">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-454">Electricity</span></span></td>
<td><span data-ttu-id="f741f-455">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-455">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="f741f-456">-10.00</span></span></td>
<td><span data-ttu-id="f741f-457">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="f741f-458">Proj 2</span></span></td>
<td><span data-ttu-id="f741f-459">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="f741f-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="f741f-460">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-460">10001</span></span></td>
<td><span data-ttu-id="f741f-461">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-461">Electricity</span></span></td>
<td><span data-ttu-id="f741f-462">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-462">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-463">10.00</span><span class="sxs-lookup"><span data-stu-id="f741f-463">10.00</span></span></td>
<td><span data-ttu-id="f741f-464">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-465">Pour plus d'informations, voir [Exécuter le calcul des frais généraux](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="f741f-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="f741f-466">Étape 4 : Traiter le calcul de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="f741f-467">La répartition est utilisée pour affecter le solde d'un objet de coût à d'autres objets de coût en appliquant une base de répartition.</span><span class="sxs-lookup"><span data-stu-id="f741f-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="f741f-468">Finance and Operations prend en charge la méthode de répartition réciproque.</span><span class="sxs-lookup"><span data-stu-id="f741f-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="f741f-469">Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés.</span><span class="sxs-lookup"><span data-stu-id="f741f-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="f741f-470">Le système détermine automatiquement l'ordre correct selon lequel exécuter les répartitions.</span><span class="sxs-lookup"><span data-stu-id="f741f-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="f741f-471">Le solde d'un objet de coût est réparti par une seule base de répartition.</span><span class="sxs-lookup"><span data-stu-id="f741f-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="f741f-472">Les répartitions entre plusieurs dimensions d'objets de coût et leurs membres respectifs sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="f741f-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="f741f-473">L'ordre de répartition est contrôlé par l'unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="f741f-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="f741f-474">[![Méthode réciproque](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="f741f-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="f741f-475">Définir la répartition de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-475">Define the cost allocation</span></span>

<span data-ttu-id="f741f-476">Voici un exemple simple expliquant comment suivre le flux du coût.</span><span class="sxs-lookup"><span data-stu-id="f741f-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="f741f-477">L'objet de coût CC001 HR contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="f741f-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="f741f-478">Un membre de dimension statistique nommé Services HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="f741f-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-479">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-479">Cost object</span></span></th>
<th><span data-ttu-id="f741f-480">Services HR</span><span class="sxs-lookup"><span data-stu-id="f741f-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-481">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-481">CC002</span></span></td>
<td><span data-ttu-id="f741f-482">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-482">Finance</span></span></td>
<td><span data-ttu-id="f741f-483">35</span><span class="sxs-lookup"><span data-stu-id="f741f-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-484">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-484">CC003</span></span></td>
<td><span data-ttu-id="f741f-485">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-485">Assembly</span></span></td>
<td><span data-ttu-id="f741f-486">55</span><span class="sxs-lookup"><span data-stu-id="f741f-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-487">CC004</span><span class="sxs-lookup"><span data-stu-id="f741f-487">CC004</span></span></td>
<td><span data-ttu-id="f741f-488">Emballage</span><span class="sxs-lookup"><span data-stu-id="f741f-488">Packaging</span></span></td>
<td><span data-ttu-id="f741f-489">10</span><span class="sxs-lookup"><span data-stu-id="f741f-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-490">L'objet de coût CC002 Finance contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="f741f-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="f741f-491">Un membre de dimension statistique nommé Services Finance est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="f741f-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-492">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-492">Cost object</span></span></th>
<th><span data-ttu-id="f741f-493">Services Finance</span><span class="sxs-lookup"><span data-stu-id="f741f-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-494">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-494">CC003</span></span></td>
<td><span data-ttu-id="f741f-495">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-495">Assembly</span></span></td>
<td><span data-ttu-id="f741f-496">65</span><span class="sxs-lookup"><span data-stu-id="f741f-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-497">CC004</span><span class="sxs-lookup"><span data-stu-id="f741f-497">CC004</span></span></td>
<td><span data-ttu-id="f741f-498">Emballage</span><span class="sxs-lookup"><span data-stu-id="f741f-498">Packaging</span></span></td>
<td><span data-ttu-id="f741f-499">35</span><span class="sxs-lookup"><span data-stu-id="f741f-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-500">L'objet de coût CC003 Assemblage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="f741f-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="f741f-501">Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="f741f-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-502">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-502">Cost object</span></span></th>
<th><span data-ttu-id="f741f-503">Services Assemblage (heures)</span><span class="sxs-lookup"><span data-stu-id="f741f-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-504">Prod 1</span></span></td>
<td><span data-ttu-id="f741f-505">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-505">Product 1</span></span></td>
<td><span data-ttu-id="f741f-506">60</span><span class="sxs-lookup"><span data-stu-id="f741f-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-507">Prod 2</span></span></td>
<td><span data-ttu-id="f741f-508">Produit 2</span><span class="sxs-lookup"><span data-stu-id="f741f-508">Product 2</span></span></td>
<td><span data-ttu-id="f741f-509">20</span><span class="sxs-lookup"><span data-stu-id="f741f-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-510">L'objet de coût CC004 Emballage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="f741f-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="f741f-511">Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="f741f-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-512">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-512">Cost object</span></span></th>
<th><span data-ttu-id="f741f-513">Services Emballage (heures)</span><span class="sxs-lookup"><span data-stu-id="f741f-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-514">Prod 1</span></span></td>
<td><span data-ttu-id="f741f-515">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-515">Product 1</span></span></td>
<td><span data-ttu-id="f741f-516">80</span><span class="sxs-lookup"><span data-stu-id="f741f-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-517">Prod 2</span></span></td>
<td><span data-ttu-id="f741f-518">Produit 2</span><span class="sxs-lookup"><span data-stu-id="f741f-518">Product 2</span></span></td>
<td><span data-ttu-id="f741f-519">15</span><span class="sxs-lookup"><span data-stu-id="f741f-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="f741f-520">Dans Finance and Operations, les mesures statistiques telles que les heures de production qu'un produit consomme peuvent être dérivées des données sources.</span><span class="sxs-lookup"><span data-stu-id="f741f-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="f741f-521">Pour plus d'informations, voir [Modèle de fournisseur de mesures statistiques](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="f741f-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="f741f-522">Le tableau suivant présente le résultat lorsque les services RH sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="f741f-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-523">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-523">Cost object</span></span></th>
<th><span data-ttu-id="f741f-524">Ampleur</span><span class="sxs-lookup"><span data-stu-id="f741f-524">Magnitude</span></span></th>
<th><span data-ttu-id="f741f-525">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="f741f-525">Allocation factor</span></span></th>
<th><span data-ttu-id="f741f-526">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-526">Amount</span></span></th>
<th><span data-ttu-id="f741f-527">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-528">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-528">CC002</span></span></td>
<td><span data-ttu-id="f741f-529">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-529">Finance</span></span></td>
<td><span data-ttu-id="f741f-530">35</span><span class="sxs-lookup"><span data-stu-id="f741f-530">35</span></span></td>
<td><span data-ttu-id="f741f-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="f741f-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="f741f-532">175.00</span><span class="sxs-lookup"><span data-stu-id="f741f-532">175.00</span></span></td>
<td><span data-ttu-id="f741f-533">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-534">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-534">CC003</span></span></td>
<td><span data-ttu-id="f741f-535">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-535">Assembly</span></span></td>
<td><span data-ttu-id="f741f-536">55</span><span class="sxs-lookup"><span data-stu-id="f741f-536">55</span></span></td>
<td><span data-ttu-id="f741f-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="f741f-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="f741f-538">275.00</span><span class="sxs-lookup"><span data-stu-id="f741f-538">275.00</span></span></td>
<td><span data-ttu-id="f741f-539">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-540">CC004</span><span class="sxs-lookup"><span data-stu-id="f741f-540">CC004</span></span></td>
<td><span data-ttu-id="f741f-541">Emballage</span><span class="sxs-lookup"><span data-stu-id="f741f-541">Packaging</span></span></td>
<td><span data-ttu-id="f741f-542">10</span><span class="sxs-lookup"><span data-stu-id="f741f-542">10</span></span></td>
<td><span data-ttu-id="f741f-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="f741f-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="f741f-544">50,00</span><span class="sxs-lookup"><span data-stu-id="f741f-544">50.00</span></span></td>
<td><span data-ttu-id="f741f-545">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-546">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-546">CC002</span></span></td>
<td><span data-ttu-id="f741f-547">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-547">Finance</span></span></td>
<td><span data-ttu-id="f741f-548">35</span><span class="sxs-lookup"><span data-stu-id="f741f-548">35</span></span></td>
<td><span data-ttu-id="f741f-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="f741f-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="f741f-550">436.00</span><span class="sxs-lookup"><span data-stu-id="f741f-550">436.00</span></span></td>
<td><span data-ttu-id="f741f-551">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-552">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-552">CC003</span></span></td>
<td><span data-ttu-id="f741f-553">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-553">Assembly</span></span></td>
<td><span data-ttu-id="f741f-554">55</span><span class="sxs-lookup"><span data-stu-id="f741f-554">55</span></span></td>
<td><span data-ttu-id="f741f-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="f741f-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="f741f-556">685.14</span><span class="sxs-lookup"><span data-stu-id="f741f-556">685.14</span></span></td>
<td><span data-ttu-id="f741f-557">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-558">CC004</span><span class="sxs-lookup"><span data-stu-id="f741f-558">CC004</span></span></td>
<td><span data-ttu-id="f741f-559">Emballage</span><span class="sxs-lookup"><span data-stu-id="f741f-559">Packaging</span></span></td>
<td><span data-ttu-id="f741f-560">10</span><span class="sxs-lookup"><span data-stu-id="f741f-560">10</span></span></td>
<td><span data-ttu-id="f741f-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="f741f-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="f741f-562">124.57</span><span class="sxs-lookup"><span data-stu-id="f741f-562">124.57</span></span></td>
<td><span data-ttu-id="f741f-563">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-564">Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="f741f-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-565">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-565">Cost object</span></span></th>
<th><span data-ttu-id="f741f-566">Ampleur</span><span class="sxs-lookup"><span data-stu-id="f741f-566">Magnitude</span></span></th>
<th><span data-ttu-id="f741f-567">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="f741f-567">Allocation factor</span></span></th>
<th><span data-ttu-id="f741f-568">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-568">Amount</span></span></th>
<th><span data-ttu-id="f741f-569">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-570">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-570">CC003</span></span></td>
<td><span data-ttu-id="f741f-571">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-571">Assembly</span></span></td>
<td><span data-ttu-id="f741f-572">65</span><span class="sxs-lookup"><span data-stu-id="f741f-572">65</span></span></td>
<td><span data-ttu-id="f741f-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="f741f-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="f741f-574">438.75</span><span class="sxs-lookup"><span data-stu-id="f741f-574">438.75</span></span></td>
<td><span data-ttu-id="f741f-575">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-576">CC004</span><span class="sxs-lookup"><span data-stu-id="f741f-576">CC004</span></span></td>
<td><span data-ttu-id="f741f-577">Emballage</span><span class="sxs-lookup"><span data-stu-id="f741f-577">Packaging</span></span></td>
<td><span data-ttu-id="f741f-578">35</span><span class="sxs-lookup"><span data-stu-id="f741f-578">35</span></span></td>
<td><span data-ttu-id="f741f-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="f741f-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="f741f-580">236.25</span><span class="sxs-lookup"><span data-stu-id="f741f-580">236.25</span></span></td>
<td><span data-ttu-id="f741f-581">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-582">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-582">CC003</span></span></td>
<td><span data-ttu-id="f741f-583">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-583">Assembly</span></span></td>
<td><span data-ttu-id="f741f-584">65</span><span class="sxs-lookup"><span data-stu-id="f741f-584">65</span></span></td>
<td><span data-ttu-id="f741f-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="f741f-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="f741f-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="f741f-586">5,297.69</span></span></td>
<td><span data-ttu-id="f741f-587">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-588">CC004</span><span class="sxs-lookup"><span data-stu-id="f741f-588">CC004</span></span></td>
<td><span data-ttu-id="f741f-589">Emballage</span><span class="sxs-lookup"><span data-stu-id="f741f-589">Packaging</span></span></td>
<td><span data-ttu-id="f741f-590">35</span><span class="sxs-lookup"><span data-stu-id="f741f-590">35</span></span></td>
<td><span data-ttu-id="f741f-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="f741f-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="f741f-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="f741f-592">2,852.60</span></span></td>
<td><span data-ttu-id="f741f-593">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-594">Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="f741f-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-595">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-595">Cost object</span></span></th>
<th><span data-ttu-id="f741f-596">Ampleur</span><span class="sxs-lookup"><span data-stu-id="f741f-596">Magnitude</span></span></th>
<th><span data-ttu-id="f741f-597">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="f741f-597">Allocation factor</span></span></th>
<th><span data-ttu-id="f741f-598">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-598">Amount</span></span></th>
<th><span data-ttu-id="f741f-599">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-600">Prod 1</span></span></td>
<td><span data-ttu-id="f741f-601">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-601">Product 1</span></span></td>
<td><span data-ttu-id="f741f-602">60</span><span class="sxs-lookup"><span data-stu-id="f741f-602">60</span></span></td>
<td><span data-ttu-id="f741f-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="f741f-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="f741f-604">535.31</span><span class="sxs-lookup"><span data-stu-id="f741f-604">535.31</span></span></td>
<td><span data-ttu-id="f741f-605">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-606">Prod 2</span></span></td>
<td><span data-ttu-id="f741f-607">Produit 2</span><span class="sxs-lookup"><span data-stu-id="f741f-607">Product 2</span></span></td>
<td><span data-ttu-id="f741f-608">20</span><span class="sxs-lookup"><span data-stu-id="f741f-608">20</span></span></td>
<td><span data-ttu-id="f741f-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="f741f-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="f741f-610">178.44</span><span class="sxs-lookup"><span data-stu-id="f741f-610">178.44</span></span></td>
<td><span data-ttu-id="f741f-611">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-612">Prod 1</span></span></td>
<td><span data-ttu-id="f741f-613">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-613">Product 1</span></span></td>
<td><span data-ttu-id="f741f-614">60</span><span class="sxs-lookup"><span data-stu-id="f741f-614">60</span></span></td>
<td><span data-ttu-id="f741f-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="f741f-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="f741f-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="f741f-616">4,487.12</span></span></td>
<td><span data-ttu-id="f741f-617">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-618">Prod 2</span></span></td>
<td><span data-ttu-id="f741f-619">Produit 2</span><span class="sxs-lookup"><span data-stu-id="f741f-619">Product 2</span></span></td>
<td><span data-ttu-id="f741f-620">20</span><span class="sxs-lookup"><span data-stu-id="f741f-620">20</span></span></td>
<td><span data-ttu-id="f741f-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="f741f-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="f741f-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="f741f-622">1,495.71</span></span></td>
<td><span data-ttu-id="f741f-623">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f741f-624">Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="f741f-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-625">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-625">Cost object</span></span></th>
<th><span data-ttu-id="f741f-626">Ampleur</span><span class="sxs-lookup"><span data-stu-id="f741f-626">Magnitude</span></span></th>
<th><span data-ttu-id="f741f-627">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="f741f-627">Allocation factor</span></span></th>
<th><span data-ttu-id="f741f-628">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-628">Amount</span></span></th>
<th><span data-ttu-id="f741f-629">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-630">Prod 1</span></span></td>
<td><span data-ttu-id="f741f-631">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-631">Product 1</span></span></td>
<td><span data-ttu-id="f741f-632">80</span><span class="sxs-lookup"><span data-stu-id="f741f-632">80</span></span></td>
<td><span data-ttu-id="f741f-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="f741f-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="f741f-634">241.05</span><span class="sxs-lookup"><span data-stu-id="f741f-634">241.05</span></span></td>
<td><span data-ttu-id="f741f-635">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-636">Prod 2</span></span></td>
<td><span data-ttu-id="f741f-637">Produit 2</span><span class="sxs-lookup"><span data-stu-id="f741f-637">Product 2</span></span></td>
<td><span data-ttu-id="f741f-638">15</span><span class="sxs-lookup"><span data-stu-id="f741f-638">15</span></span></td>
<td><span data-ttu-id="f741f-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="f741f-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="f741f-640">45.20</span><span class="sxs-lookup"><span data-stu-id="f741f-640">45.20</span></span></td>
<td><span data-ttu-id="f741f-641">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-642">Prod 1</span></span></td>
<td><span data-ttu-id="f741f-643">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-643">Product 1</span></span></td>
<td><span data-ttu-id="f741f-644">80</span><span class="sxs-lookup"><span data-stu-id="f741f-644">80</span></span></td>
<td><span data-ttu-id="f741f-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="f741f-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="f741f-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="f741f-646">2,507.09</span></span></td>
<td><span data-ttu-id="f741f-647">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-648">Prod 2</span></span></td>
<td><span data-ttu-id="f741f-649">Produit 2</span><span class="sxs-lookup"><span data-stu-id="f741f-649">Product 2</span></span></td>
<td><span data-ttu-id="f741f-650">15</span><span class="sxs-lookup"><span data-stu-id="f741f-650">15</span></span></td>
<td><span data-ttu-id="f741f-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="f741f-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="f741f-652">470.08</span><span class="sxs-lookup"><span data-stu-id="f741f-652">470.08</span></span></td>
<td><span data-ttu-id="f741f-653">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="f741f-654">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="f741f-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f741f-655">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="f741f-655">Journal</span></span></th>
<th><span data-ttu-id="f741f-656">Type de journal</span><span class="sxs-lookup"><span data-stu-id="f741f-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="f741f-657">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="f741f-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="f741f-658">Version</span><span class="sxs-lookup"><span data-stu-id="f741f-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-659">00004</span><span class="sxs-lookup"><span data-stu-id="f741f-659">00004</span></span></td>
<td><span data-ttu-id="f741f-660">Journal de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="f741f-661">Exercice</span><span class="sxs-lookup"><span data-stu-id="f741f-661">Fiscal</span></span></td>
<td><span data-ttu-id="f741f-662">2017</span><span class="sxs-lookup"><span data-stu-id="f741f-662">2017</span></span></td>
<td><span data-ttu-id="f741f-663">Période 1</span><span class="sxs-lookup"><span data-stu-id="f741f-663">Period 1</span></span></td>
<td><span data-ttu-id="f741f-664">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="f741f-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="f741f-665">Lignes de journal</span><span class="sxs-lookup"><span data-stu-id="f741f-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f741f-666">Date comptable</span><span class="sxs-lookup"><span data-stu-id="f741f-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-667">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-668">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-668">Cost element</span></span></th>
<th><span data-ttu-id="f741f-669">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-669">Cost behavior</span></span></th>
<th><span data-ttu-id="f741f-670">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-671">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-672">CC001</span><span class="sxs-lookup"><span data-stu-id="f741f-672">CC001</span></span></td>
<td><span data-ttu-id="f741f-673">RH</span><span class="sxs-lookup"><span data-stu-id="f741f-673">HR</span></span></td>
<td><span data-ttu-id="f741f-674">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-674">10001</span></span></td>
<td><span data-ttu-id="f741f-675">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-675">Electricity</span></span></td>
<td><span data-ttu-id="f741f-676">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-676">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-677">500,00</span><span class="sxs-lookup"><span data-stu-id="f741f-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-678">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-679">CC001</span><span class="sxs-lookup"><span data-stu-id="f741f-679">CC001</span></span></td>
<td><span data-ttu-id="f741f-680">RH</span><span class="sxs-lookup"><span data-stu-id="f741f-680">HR</span></span></td>
<td><span data-ttu-id="f741f-681">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-681">10001</span></span></td>
<td><span data-ttu-id="f741f-682">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-682">Electricity</span></span></td>
<td><span data-ttu-id="f741f-683">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-683">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="f741f-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-685">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-686">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-686">CC002</span></span></td>
<td><span data-ttu-id="f741f-687">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-687">Finance</span></span></td>
<td><span data-ttu-id="f741f-688">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-688">10001</span></span></td>
<td><span data-ttu-id="f741f-689">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-689">Electricity</span></span></td>
<td><span data-ttu-id="f741f-690">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-690">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-691">675.00</span><span class="sxs-lookup"><span data-stu-id="f741f-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-692">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-693">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-693">CC002</span></span></td>
<td><span data-ttu-id="f741f-694">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-694">Finance</span></span></td>
<td><span data-ttu-id="f741f-695">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-695">10001</span></span></td>
<td><span data-ttu-id="f741f-696">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-696">Electricity</span></span></td>
<td><span data-ttu-id="f741f-697">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-697">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="f741f-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-699">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-700">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-700">CC003</span></span></td>
<td><span data-ttu-id="f741f-701">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-701">Assembly</span></span></td>
<td><span data-ttu-id="f741f-702">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-702">10001</span></span></td>
<td><span data-ttu-id="f741f-703">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-703">Electricity</span></span></td>
<td><span data-ttu-id="f741f-704">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-704">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-705">713.75</span><span class="sxs-lookup"><span data-stu-id="f741f-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-706">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-707">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-707">CC003</span></span></td>
<td><span data-ttu-id="f741f-708">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-708">Assembly</span></span></td>
<td><span data-ttu-id="f741f-709">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-709">10001</span></span></td>
<td><span data-ttu-id="f741f-710">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-710">Electricity</span></span></td>
<td><span data-ttu-id="f741f-711">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-711">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="f741f-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-713">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-714">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-714">CC003</span></span></td>
<td><span data-ttu-id="f741f-715">Emballage</span><span class="sxs-lookup"><span data-stu-id="f741f-715">Packaging</span></span></td>
<td><span data-ttu-id="f741f-716">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-716">10001</span></span></td>
<td><span data-ttu-id="f741f-717">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-717">Electricity</span></span></td>
<td><span data-ttu-id="f741f-718">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-718">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-719">286.25</span><span class="sxs-lookup"><span data-stu-id="f741f-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-720">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-721">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-721">CC003</span></span></td>
<td><span data-ttu-id="f741f-722">Emballage</span><span class="sxs-lookup"><span data-stu-id="f741f-722">Packaging</span></span></td>
<td><span data-ttu-id="f741f-723">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-723">10001</span></span></td>
<td><span data-ttu-id="f741f-724">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-724">Electricity</span></span></td>
<td><span data-ttu-id="f741f-725">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-725">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="f741f-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-727">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-728">Prod 1</span></span></td>
<td><span data-ttu-id="f741f-729">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-729">Product 1</span></span></td>
<td><span data-ttu-id="f741f-730">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-730">10001</span></span></td>
<td><span data-ttu-id="f741f-731">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-731">Electricity</span></span></td>
<td><span data-ttu-id="f741f-732">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-732">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-733">776.36</span><span class="sxs-lookup"><span data-stu-id="f741f-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-734">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-735">Prod 1</span></span></td>
<td><span data-ttu-id="f741f-736">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-736">Product 1</span></span></td>
<td><span data-ttu-id="f741f-737">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-737">10001</span></span></td>
<td><span data-ttu-id="f741f-738">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-738">Electricity</span></span></td>
<td><span data-ttu-id="f741f-739">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-739">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="f741f-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-741">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-742">Prod 2</span></span></td>
<td><span data-ttu-id="f741f-743">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-743">Product 1</span></span></td>
<td><span data-ttu-id="f741f-744">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-744">10001</span></span></td>
<td><span data-ttu-id="f741f-745">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-745">Electricity</span></span></td>
<td><span data-ttu-id="f741f-746">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-746">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-747">223.64</span><span class="sxs-lookup"><span data-stu-id="f741f-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-748">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="f741f-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-749">Prod 2</span></span></td>
<td><span data-ttu-id="f741f-750">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-750">Product 1</span></span></td>
<td><span data-ttu-id="f741f-751">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-751">10001</span></span></td>
<td><span data-ttu-id="f741f-752">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-752">Electricity</span></span></td>
<td><span data-ttu-id="f741f-753">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-753">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="f741f-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="f741f-755">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f741f-756">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f741f-757">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-757">Cost element</span></span></th>
<th><span data-ttu-id="f741f-758">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="f741f-758">Cost behavior</span></span></th>
<th><span data-ttu-id="f741f-759">Montant</span><span class="sxs-lookup"><span data-stu-id="f741f-759">Amount</span></span></th>
<th><span data-ttu-id="f741f-760">Date comptable</span><span class="sxs-lookup"><span data-stu-id="f741f-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f741f-761">CC001</span><span class="sxs-lookup"><span data-stu-id="f741f-761">CC001</span></span></td>
<td><span data-ttu-id="f741f-762">RH</span><span class="sxs-lookup"><span data-stu-id="f741f-762">HR</span></span></td>
<td><span data-ttu-id="f741f-763">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-763">10001</span></span></td>
<td><span data-ttu-id="f741f-764">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-764">Electricity</span></span></td>
<td><span data-ttu-id="f741f-765">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-765">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="f741f-766">-500.00</span></span></td>
<td><span data-ttu-id="f741f-767">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-768">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-768">CC002</span></span></td>
<td><span data-ttu-id="f741f-769">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-769">Finance</span></span></td>
<td><span data-ttu-id="f741f-770">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-770">10001</span></span></td>
<td><span data-ttu-id="f741f-771">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-771">Electricity</span></span></td>
<td><span data-ttu-id="f741f-772">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-772">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-773">175.00</span><span class="sxs-lookup"><span data-stu-id="f741f-773">175.00</span></span></td>
<td><span data-ttu-id="f741f-774">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-775">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-775">CC003</span></span></td>
<td><span data-ttu-id="f741f-776">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-776">Assembly</span></span></td>
<td><span data-ttu-id="f741f-777">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-777">10001</span></span></td>
<td><span data-ttu-id="f741f-778">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-778">Electricity</span></span></td>
<td><span data-ttu-id="f741f-779">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-779">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-780">275.00</span><span class="sxs-lookup"><span data-stu-id="f741f-780">275.00</span></span></td>
<td><span data-ttu-id="f741f-781">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-782">CC004</span><span class="sxs-lookup"><span data-stu-id="f741f-782">CC004</span></span></td>
<td><span data-ttu-id="f741f-783">Emballage</span><span class="sxs-lookup"><span data-stu-id="f741f-783">Packaging</span></span></td>
<td><span data-ttu-id="f741f-784">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-784">10001</span></span></td>
<td><span data-ttu-id="f741f-785">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-785">Electricity</span></span></td>
<td><span data-ttu-id="f741f-786">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-786">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-787">50,00</span><span class="sxs-lookup"><span data-stu-id="f741f-787">50,00</span></span></td>
<td><span data-ttu-id="f741f-788">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-789">CC001</span><span class="sxs-lookup"><span data-stu-id="f741f-789">CC001</span></span></td>
<td><span data-ttu-id="f741f-790">RH</span><span class="sxs-lookup"><span data-stu-id="f741f-790">HR</span></span></td>
<td><span data-ttu-id="f741f-791">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-791">10001</span></span></td>
<td><span data-ttu-id="f741f-792">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-792">Electricity</span></span></td>
<td><span data-ttu-id="f741f-793">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-793">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="f741f-794">-1,245.71</span></span></td>
<td><span data-ttu-id="f741f-795">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-796">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-796">CC002</span></span></td>
<td><span data-ttu-id="f741f-797">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-797">Finance</span></span></td>
<td><span data-ttu-id="f741f-798">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-798">10001</span></span></td>
<td><span data-ttu-id="f741f-799">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-799">Electricity</span></span></td>
<td><span data-ttu-id="f741f-800">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-800">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-801">436.00</span><span class="sxs-lookup"><span data-stu-id="f741f-801">436.00</span></span></td>
<td><span data-ttu-id="f741f-802">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-803">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-803">CC003</span></span></td>
<td><span data-ttu-id="f741f-804">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-804">Assembly</span></span></td>
<td><span data-ttu-id="f741f-805">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-805">10001</span></span></td>
<td><span data-ttu-id="f741f-806">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-806">Electricity</span></span></td>
<td><span data-ttu-id="f741f-807">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-807">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-808">685.14</span><span class="sxs-lookup"><span data-stu-id="f741f-808">685.14</span></span></td>
<td><span data-ttu-id="f741f-809">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-810">CC004</span><span class="sxs-lookup"><span data-stu-id="f741f-810">CC004</span></span></td>
<td><span data-ttu-id="f741f-811">Emballage</span><span class="sxs-lookup"><span data-stu-id="f741f-811">Packaging</span></span></td>
<td><span data-ttu-id="f741f-812">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-812">10001</span></span></td>
<td><span data-ttu-id="f741f-813">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-813">Electricity</span></span></td>
<td><span data-ttu-id="f741f-814">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-814">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-815">124.57</span><span class="sxs-lookup"><span data-stu-id="f741f-815">124.57</span></span></td>
<td><span data-ttu-id="f741f-816">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-817">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-817">CC002</span></span></td>
<td><span data-ttu-id="f741f-818">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-818">Finance</span></span></td>
<td><span data-ttu-id="f741f-819">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-819">10001</span></span></td>
<td><span data-ttu-id="f741f-820">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-820">Electricity</span></span></td>
<td><span data-ttu-id="f741f-821">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-821">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="f741f-822">-675.00</span></span></td>
<td><span data-ttu-id="f741f-823">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-824">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-824">CC003</span></span></td>
<td><span data-ttu-id="f741f-825">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-825">Assembly</span></span></td>
<td><span data-ttu-id="f741f-826">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-826">10001</span></span></td>
<td><span data-ttu-id="f741f-827">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-827">Electricity</span></span></td>
<td><span data-ttu-id="f741f-828">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-828">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-829">438.75</span><span class="sxs-lookup"><span data-stu-id="f741f-829">438.75</span></span></td>
<td><span data-ttu-id="f741f-830">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-831">CC004</span><span class="sxs-lookup"><span data-stu-id="f741f-831">CC004</span></span></td>
<td><span data-ttu-id="f741f-832">Emballage</span><span class="sxs-lookup"><span data-stu-id="f741f-832">Packaging</span></span></td>
<td><span data-ttu-id="f741f-833">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-833">10001</span></span></td>
<td><span data-ttu-id="f741f-834">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-834">Electricity</span></span></td>
<td><span data-ttu-id="f741f-835">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-835">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-836">236.25</span><span class="sxs-lookup"><span data-stu-id="f741f-836">236.25</span></span></td>
<td><span data-ttu-id="f741f-837">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-838">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-838">CC002</span></span></td>
<td><span data-ttu-id="f741f-839">Finances</span><span class="sxs-lookup"><span data-stu-id="f741f-839">Finance</span></span></td>
<td><span data-ttu-id="f741f-840">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-840">10001</span></span></td>
<td><span data-ttu-id="f741f-841">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-841">Electricity</span></span></td>
<td><span data-ttu-id="f741f-842">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-842">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="f741f-843">-8,150.29</span></span></td>
<td><span data-ttu-id="f741f-844">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-845">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-845">CC003</span></span></td>
<td><span data-ttu-id="f741f-846">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-846">Assembly</span></span></td>
<td><span data-ttu-id="f741f-847">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-847">10001</span></span></td>
<td><span data-ttu-id="f741f-848">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-848">Electricity</span></span></td>
<td><span data-ttu-id="f741f-849">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-849">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="f741f-850">5,297.69</span></span></td>
<td><span data-ttu-id="f741f-851">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-852">CC004</span><span class="sxs-lookup"><span data-stu-id="f741f-852">CC004</span></span></td>
<td><span data-ttu-id="f741f-853">Emballage</span><span class="sxs-lookup"><span data-stu-id="f741f-853">Packaging</span></span></td>
<td><span data-ttu-id="f741f-854">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-854">10001</span></span></td>
<td><span data-ttu-id="f741f-855">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-855">Electricity</span></span></td>
<td><span data-ttu-id="f741f-856">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-856">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="f741f-857">2,852.60</span></span></td>
<td><span data-ttu-id="f741f-858">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-859">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-859">CC003</span></span></td>
<td><span data-ttu-id="f741f-860">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-860">Assembly</span></span></td>
<td><span data-ttu-id="f741f-861">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-861">10001</span></span></td>
<td><span data-ttu-id="f741f-862">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-862">Electricity</span></span></td>
<td><span data-ttu-id="f741f-863">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-863">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="f741f-864">-713.75</span></span></td>
<td><span data-ttu-id="f741f-865">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-866">Prod 1</span></span></td>
<td><span data-ttu-id="f741f-867">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-867">Product 1</span></span></td>
<td><span data-ttu-id="f741f-868">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-868">10001</span></span></td>
<td><span data-ttu-id="f741f-869">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-869">Electricity</span></span></td>
<td><span data-ttu-id="f741f-870">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-870">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-871">535.31</span><span class="sxs-lookup"><span data-stu-id="f741f-871">535.31</span></span></td>
<td><span data-ttu-id="f741f-872">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-873">Prod 2</span></span></td>
<td><span data-ttu-id="f741f-874">Produit 2</span><span class="sxs-lookup"><span data-stu-id="f741f-874">Product 2</span></span></td>
<td><span data-ttu-id="f741f-875">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-875">10001</span></span></td>
<td><span data-ttu-id="f741f-876">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-876">Electricity</span></span></td>
<td><span data-ttu-id="f741f-877">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-877">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-878">178.44</span><span class="sxs-lookup"><span data-stu-id="f741f-878">178.44</span></span></td>
<td><span data-ttu-id="f741f-879">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-880">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-880">CC003</span></span></td>
<td><span data-ttu-id="f741f-881">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-881">Assembly</span></span></td>
<td><span data-ttu-id="f741f-882">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-882">10001</span></span></td>
<td><span data-ttu-id="f741f-883">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-883">Electricity</span></span></td>
<td><span data-ttu-id="f741f-884">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-884">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="f741f-885">-5,982.83</span></span></td>
<td><span data-ttu-id="f741f-886">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-887">Prod 1</span></span></td>
<td><span data-ttu-id="f741f-888">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-888">Product 1</span></span></td>
<td><span data-ttu-id="f741f-889">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-889">10001</span></span></td>
<td><span data-ttu-id="f741f-890">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-890">Electricity</span></span></td>
<td><span data-ttu-id="f741f-891">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-891">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="f741f-892">4,487.12</span></span></td>
<td><span data-ttu-id="f741f-893">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-894">Prod 2</span></span></td>
<td><span data-ttu-id="f741f-895">Produit 2</span><span class="sxs-lookup"><span data-stu-id="f741f-895">Product 2</span></span></td>
<td><span data-ttu-id="f741f-896">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-896">10001</span></span></td>
<td><span data-ttu-id="f741f-897">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-897">Electricity</span></span></td>
<td><span data-ttu-id="f741f-898">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-898">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="f741f-899">1,495.71</span></span></td>
<td><span data-ttu-id="f741f-900">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-901">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-901">CC003</span></span></td>
<td><span data-ttu-id="f741f-902">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-902">Assembly</span></span></td>
<td><span data-ttu-id="f741f-903">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-903">10001</span></span></td>
<td><span data-ttu-id="f741f-904">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-904">Electricity</span></span></td>
<td><span data-ttu-id="f741f-905">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-905">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="f741f-906">-286.25</span></span></td>
<td><span data-ttu-id="f741f-907">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-908">Prod 1</span></span></td>
<td><span data-ttu-id="f741f-909">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-909">Product 1</span></span></td>
<td><span data-ttu-id="f741f-910">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-910">10001</span></span></td>
<td><span data-ttu-id="f741f-911">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-911">Electricity</span></span></td>
<td><span data-ttu-id="f741f-912">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-912">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-913">241.05</span><span class="sxs-lookup"><span data-stu-id="f741f-913">241.05</span></span></td>
<td><span data-ttu-id="f741f-914">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-915">Prod 2</span></span></td>
<td><span data-ttu-id="f741f-916">Produit 2</span><span class="sxs-lookup"><span data-stu-id="f741f-916">Product 2</span></span></td>
<td><span data-ttu-id="f741f-917">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-917">10001</span></span></td>
<td><span data-ttu-id="f741f-918">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-918">Electricity</span></span></td>
<td><span data-ttu-id="f741f-919">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-919">Fixed cost</span></span></td>
<td><span data-ttu-id="f741f-920">45.20</span><span class="sxs-lookup"><span data-stu-id="f741f-920">45.20</span></span></td>
<td><span data-ttu-id="f741f-921">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-922">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-922">CC003</span></span></td>
<td><span data-ttu-id="f741f-923">Assemblage</span><span class="sxs-lookup"><span data-stu-id="f741f-923">Assembly</span></span></td>
<td><span data-ttu-id="f741f-924">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-924">10001</span></span></td>
<td><span data-ttu-id="f741f-925">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-925">Electricity</span></span></td>
<td><span data-ttu-id="f741f-926">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-926">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="f741f-927">-2,977.17</span></span></td>
<td><span data-ttu-id="f741f-928">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-929">Prod 1</span></span></td>
<td><span data-ttu-id="f741f-930">Produit 1</span><span class="sxs-lookup"><span data-stu-id="f741f-930">Product 1</span></span></td>
<td><span data-ttu-id="f741f-931">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-931">10001</span></span></td>
<td><span data-ttu-id="f741f-932">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-932">Electricity</span></span></td>
<td><span data-ttu-id="f741f-933">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-933">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="f741f-934">2,507.09</span></span></td>
<td><span data-ttu-id="f741f-935">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f741f-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-936">Prod 2</span></span></td>
<td><span data-ttu-id="f741f-937">Produit 2</span><span class="sxs-lookup"><span data-stu-id="f741f-937">Product 2</span></span></td>
<td><span data-ttu-id="f741f-938">10001</span><span class="sxs-lookup"><span data-stu-id="f741f-938">10001</span></span></td>
<td><span data-ttu-id="f741f-939">Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-939">Electricity</span></span></td>
<td><span data-ttu-id="f741f-940">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-940">Variable cost</span></span></td>
<td><span data-ttu-id="f741f-941">470.08</span><span class="sxs-lookup"><span data-stu-id="f741f-941">470.08</span></span></td>
<td><span data-ttu-id="f741f-942">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="f741f-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="f741f-943">Conclusion</span><span class="sxs-lookup"><span data-stu-id="f741f-943">Conclusion</span></span>
<span data-ttu-id="f741f-944">Dans la comptabilité financière, un coût de 10 000,00 pour l'électricité est imputé sur un ID de centre de coût fictif.</span><span class="sxs-lookup"><span data-stu-id="f741f-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="f741f-945">Par conséquent, les comptables sauront que ce coût doit être affecté.</span><span class="sxs-lookup"><span data-stu-id="f741f-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="f741f-946">Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l'organisation, selon les stratégies et les règles qui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="f741f-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="f741f-947">Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="f741f-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="f741f-948">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="f741f-949">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="f741f-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="f741f-950">Total</span><span class="sxs-lookup"><span data-stu-id="f741f-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="f741f-951">CC099</span><span class="sxs-lookup"><span data-stu-id="f741f-951">CC099</span></span></th>
<th><span data-ttu-id="f741f-952">CC001</span><span class="sxs-lookup"><span data-stu-id="f741f-952">CC001</span></span></th>
<th><span data-ttu-id="f741f-953">CC002</span><span class="sxs-lookup"><span data-stu-id="f741f-953">CC002</span></span></th>
<th><span data-ttu-id="f741f-954">CC003</span><span class="sxs-lookup"><span data-stu-id="f741f-954">CC003</span></span></th>
<th><span data-ttu-id="f741f-955">CC004</span><span class="sxs-lookup"><span data-stu-id="f741f-955">CC004</span></span></th>
<th><span data-ttu-id="f741f-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="f741f-956">Proj 1</span></span></th>
<th><span data-ttu-id="f741f-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="f741f-957">Proj 2</span></span></th>
<th><span data-ttu-id="f741f-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f741f-958">Prod 1</span></span></th>
<th><span data-ttu-id="f741f-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f741f-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="f741f-960">10001 Électricité</span><span class="sxs-lookup"><span data-stu-id="f741f-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="f741f-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="f741f-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="f741f-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="f741f-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="f741f-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="f741f-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="f741f-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="f741f-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="f741f-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="f741f-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="f741f-970">Non classifié</span><span class="sxs-lookup"><span data-stu-id="f741f-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-971">0,00</span><span class="sxs-lookup"><span data-stu-id="f741f-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="f741f-972">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="f741f-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-973">0,00</span><span class="sxs-lookup"><span data-stu-id="f741f-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-974">0,00</span><span class="sxs-lookup"><span data-stu-id="f741f-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-975">0,00</span><span class="sxs-lookup"><span data-stu-id="f741f-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-976">0,00</span><span class="sxs-lookup"><span data-stu-id="f741f-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-977">0,00</span><span class="sxs-lookup"><span data-stu-id="f741f-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="f741f-978">776.36</span><span class="sxs-lookup"><span data-stu-id="f741f-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-979">223.64</span><span class="sxs-lookup"><span data-stu-id="f741f-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-980"><strong>1 000,00</strong></span><span class="sxs-lookup"><span data-stu-id="f741f-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="f741f-981">Coût variable</span><span class="sxs-lookup"><span data-stu-id="f741f-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-982">000</span><span class="sxs-lookup"><span data-stu-id="f741f-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-983">0,00</span><span class="sxs-lookup"><span data-stu-id="f741f-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-984">0,00</span><span class="sxs-lookup"><span data-stu-id="f741f-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-985">0,00</span><span class="sxs-lookup"><span data-stu-id="f741f-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-986">0,00</span><span class="sxs-lookup"><span data-stu-id="f741f-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-987">30,00</span><span class="sxs-lookup"><span data-stu-id="f741f-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-988">10,00</span><span class="sxs-lookup"><span data-stu-id="f741f-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="f741f-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="f741f-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f741f-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="f741f-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="f741f-992">Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût.</span><span class="sxs-lookup"><span data-stu-id="f741f-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="f741f-993">Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l'organisation.</span><span class="sxs-lookup"><span data-stu-id="f741f-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="f741f-994">Autrement dit, les objets de coût de plus bas niveau supportent le coût.</span><span class="sxs-lookup"><span data-stu-id="f741f-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="f741f-995">Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts.</span><span class="sxs-lookup"><span data-stu-id="f741f-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="f741f-996">Pour plus d'informations, voir [Repositionnement des coûts](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="f741f-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>




