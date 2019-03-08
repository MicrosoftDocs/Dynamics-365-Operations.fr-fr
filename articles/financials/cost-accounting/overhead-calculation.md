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
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "335115"
---
# <a name="overhead-calculation"></a><span data-ttu-id="872ba-103">Calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="872ba-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="872ba-104">Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="872ba-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="872ba-105">Définition des termes</span><span class="sxs-lookup"><span data-stu-id="872ba-105">Term definition</span></span>
---------------

<span data-ttu-id="872ba-106">Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique.</span><span class="sxs-lookup"><span data-stu-id="872ba-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="872ba-107">Les frais généraux permettent essentiellement l'identification des activités rémunératrices.</span><span class="sxs-lookup"><span data-stu-id="872ba-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="872ba-108">Voici quelques exemples de frais généraux :</span><span class="sxs-lookup"><span data-stu-id="872ba-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="872ba-109">Loyer</span><span class="sxs-lookup"><span data-stu-id="872ba-109">Rent</span></span>
-   <span data-ttu-id="872ba-110">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-110">Electricity</span></span>
-   <span data-ttu-id="872ba-111">Salaires administratifs</span><span class="sxs-lookup"><span data-stu-id="872ba-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="872ba-112">Vue d'ensemble du calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="872ba-112">Overhead calculation overview</span></span>
<span data-ttu-id="872ba-113">Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l'ordre correct.</span><span class="sxs-lookup"><span data-stu-id="872ba-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="872ba-114">Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées.</span><span class="sxs-lookup"><span data-stu-id="872ba-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="872ba-115">Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions.</span><span class="sxs-lookup"><span data-stu-id="872ba-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="872ba-116">Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable.</span><span class="sxs-lookup"><span data-stu-id="872ba-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="872ba-117">Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="872ba-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="872ba-118">L'ID de version unique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="872ba-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="872ba-119">Type de version</span><span class="sxs-lookup"><span data-stu-id="872ba-119">Version type</span></span>
-   <span data-ttu-id="872ba-120">Date et heure</span><span class="sxs-lookup"><span data-stu-id="872ba-120">Date and time</span></span>
-   <span data-ttu-id="872ba-121">Comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="872ba-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="872ba-122">Exercice</span><span class="sxs-lookup"><span data-stu-id="872ba-122">Fiscal year</span></span>
-   <span data-ttu-id="872ba-123">Période fiscale</span><span class="sxs-lookup"><span data-stu-id="872ba-123">Fiscal period</span></span>

<span data-ttu-id="872ba-124">Le calcul des frais généraux est effectué indépendamment de la version.</span><span class="sxs-lookup"><span data-stu-id="872ba-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="872ba-125">Par conséquent, vous pouvez calculer la version de budget avant la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="872ba-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="872ba-126">Le calcul des frais généraux comporte quatre étapes, comme le montre l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="872ba-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="872ba-127">Dans chaque étape, un en-tête de journal avec des entrées de journal est créé.</span><span class="sxs-lookup"><span data-stu-id="872ba-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="872ba-128">Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul.</span><span class="sxs-lookup"><span data-stu-id="872ba-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="872ba-129">Les stratégies et les règles s'appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie.</span><span class="sxs-lookup"><span data-stu-id="872ba-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="872ba-130">Par conséquent, vous disposez toujours d'une traçabilité complète.</span><span class="sxs-lookup"><span data-stu-id="872ba-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="872ba-131">[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="872ba-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="872ba-132">Calculer et affecter les frais généraux Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="872ba-133">Dans la comptabilité financière, certaines coûts, tels que l'électricité, sont enregistrés comme montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="872ba-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="872ba-134">Par conséquent, l'analyse détaillée n'est pas fournie pour le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="872ba-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="872ba-135">Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l'organisation, les coûts doivent suivre les unités organisationnelles.</span><span class="sxs-lookup"><span data-stu-id="872ba-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="872ba-136">Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste.</span><span class="sxs-lookup"><span data-stu-id="872ba-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="872ba-137">Dans la comptabilité, le coût de l'électricité peut être validé comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="872ba-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="872ba-138">Date comptable</span><span class="sxs-lookup"><span data-stu-id="872ba-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-139">Centre de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-140">Compte principal</span><span class="sxs-lookup"><span data-stu-id="872ba-140">Main account</span></span></th>
<th><span data-ttu-id="872ba-141">Montant en devise comptable</span><span class="sxs-lookup"><span data-stu-id="872ba-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-142">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="872ba-143">CC099</span><span class="sxs-lookup"><span data-stu-id="872ba-143">CC099</span></span></td>
<td><span data-ttu-id="872ba-144">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="872ba-144">Default cost center</span></span></td>
<td><span data-ttu-id="872ba-145">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-145">10001</span></span></td>
<td><span data-ttu-id="872ba-146">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-146">Electricity</span></span></td>
<td><span data-ttu-id="872ba-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="872ba-148">Étape 1 : Traiter le calcul du comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="872ba-149">Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="872ba-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="872ba-150">Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.</span><span class="sxs-lookup"><span data-stu-id="872ba-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="872ba-151">Définir la règle de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-151">Define the cost behavior rule</span></span>

<span data-ttu-id="872ba-152">Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation.</span><span class="sxs-lookup"><span data-stu-id="872ba-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="872ba-153">Les factures d'électricité correspondent souvent à cette définition.</span><span class="sxs-lookup"><span data-stu-id="872ba-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="872ba-154">Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH).</span><span class="sxs-lookup"><span data-stu-id="872ba-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="872ba-155">Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :</span><span class="sxs-lookup"><span data-stu-id="872ba-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="872ba-156">Montant fixe 1 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="872ba-157">0 &lt;= 1 000,00 = Fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="872ba-158">1 000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="872ba-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="872ba-159">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="872ba-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="872ba-160">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="872ba-160">Journal</span></span></th>
<th><span data-ttu-id="872ba-161">Type de journal</span><span class="sxs-lookup"><span data-stu-id="872ba-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="872ba-162">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="872ba-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="872ba-163">Version</span><span class="sxs-lookup"><span data-stu-id="872ba-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-164">00001</span><span class="sxs-lookup"><span data-stu-id="872ba-164">00001</span></span></td>
<td><span data-ttu-id="872ba-165">Journal de calcul de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="872ba-166">Exercice</span><span class="sxs-lookup"><span data-stu-id="872ba-166">Fiscal</span></span></td>
<td><span data-ttu-id="872ba-167">2017</span><span class="sxs-lookup"><span data-stu-id="872ba-167">2017</span></span></td>
<td><span data-ttu-id="872ba-168">Période 1</span><span class="sxs-lookup"><span data-stu-id="872ba-168">Period 1</span></span></td>
<td><span data-ttu-id="872ba-169">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="872ba-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="872ba-170">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="872ba-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="872ba-171">Date comptable</span><span class="sxs-lookup"><span data-stu-id="872ba-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-172">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-173">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-173">Cost element</span></span></th>
<th><span data-ttu-id="872ba-174">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-174">Cost behavior</span></span></th>
<th><span data-ttu-id="872ba-175">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-176">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="872ba-177">CC099</span><span class="sxs-lookup"><span data-stu-id="872ba-177">CC099</span></span></td>
<td><span data-ttu-id="872ba-178">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="872ba-178">Default cost center</span></span></td>
<td><span data-ttu-id="872ba-179">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-179">10001</span></span></td>
<td><span data-ttu-id="872ba-180">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-180">Electricity</span></span></td>
<td><span data-ttu-id="872ba-181">Non classifié</span><span class="sxs-lookup"><span data-stu-id="872ba-181">Unclassified</span></span></td>
<td><span data-ttu-id="872ba-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="872ba-183">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-184">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-185">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-185">Cost element</span></span></th>
<th><span data-ttu-id="872ba-186">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-186">Cost behavior</span></span></th>
<th><span data-ttu-id="872ba-187">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-187">Amount</span></span></th>
<th><span data-ttu-id="872ba-188">Date comptable</span><span class="sxs-lookup"><span data-stu-id="872ba-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-189">CC099</span><span class="sxs-lookup"><span data-stu-id="872ba-189">CC099</span></span></td>
<td><span data-ttu-id="872ba-190">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="872ba-190">Default cost center</span></span></td>
<td><span data-ttu-id="872ba-191">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-191">10001</span></span></td>
<td><span data-ttu-id="872ba-192">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-192">Electricity</span></span></td>
<td><span data-ttu-id="872ba-193">Non classifié</span><span class="sxs-lookup"><span data-stu-id="872ba-193">Unclassified</span></span></td>
<td><span data-ttu-id="872ba-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-194">10,000.00</span></span></td>
<td><span data-ttu-id="872ba-195">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-196">CC099</span><span class="sxs-lookup"><span data-stu-id="872ba-196">CC099</span></span></td>
<td><span data-ttu-id="872ba-197">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="872ba-197">Default cost center</span></span></td>
<td><span data-ttu-id="872ba-198">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-198">10001</span></span></td>
<td><span data-ttu-id="872ba-199">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-199">Electricity</span></span></td>
<td><span data-ttu-id="872ba-200">Non classifié</span><span class="sxs-lookup"><span data-stu-id="872ba-200">Unclassified</span></span></td>
<td><span data-ttu-id="872ba-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-201">-10,000.00</span></span></td>
<td><span data-ttu-id="872ba-202">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-203">CC099</span><span class="sxs-lookup"><span data-stu-id="872ba-203">CC099</span></span></td>
<td><span data-ttu-id="872ba-204">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="872ba-204">Default cost center</span></span></td>
<td><span data-ttu-id="872ba-205">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-205">10001</span></span></td>
<td><span data-ttu-id="872ba-206">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-206">Electricity</span></span></td>
<td><span data-ttu-id="872ba-207">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-207">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-208">1,000.00</span></span></td>
<td><span data-ttu-id="872ba-209">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-210">CC099</span><span class="sxs-lookup"><span data-stu-id="872ba-210">CC099</span></span></td>
<td><span data-ttu-id="872ba-211">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="872ba-211">Default cost center</span></span></td>
<td><span data-ttu-id="872ba-212">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-212">10001</span></span></td>
<td><span data-ttu-id="872ba-213">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-213">Electricity</span></span></td>
<td><span data-ttu-id="872ba-214">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-214">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-215">9 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-215">9,000.00</span></span></td>
<td><span data-ttu-id="872ba-216">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-217">Pour plus d'informations, voir [Créer et affecter une stratégie de comportement de coûts à une unité de contrôle des coûts](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="872ba-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="872ba-218">Étape 2 : Traiter le calcul de distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="872ba-219">La distribution des coûts est utilisée pour redistribuer le coût d'un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée.</span><span class="sxs-lookup"><span data-stu-id="872ba-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="872ba-220">La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l'élément de coût principal du coût d'origine.</span><span class="sxs-lookup"><span data-stu-id="872ba-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="872ba-221">Définir la règle de distribution de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-221">Define the cost distribution rule</span></span>

<span data-ttu-id="872ba-222">Dans la comptabilité financière, les coûts d'électricité sont souvent enregistrés comme un montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="872ba-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="872ba-223">Dans le Contrôle de gestion, cette approche n'est pas assez détaillée.</span><span class="sxs-lookup"><span data-stu-id="872ba-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="872ba-224">Le coût variable doit être attribué aux différents objets de coûts sur une base juste.</span><span class="sxs-lookup"><span data-stu-id="872ba-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="872ba-225">La base de répartition la plus logique est la consommation de l'électricité (KWH).</span><span class="sxs-lookup"><span data-stu-id="872ba-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="872ba-226">Un membre de dimension statistique nommé Électricité est créé, et la consommation d'électricité est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="872ba-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="872ba-227">Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="872ba-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-228">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-228">Cost object</span></span></th>
<th><span data-ttu-id="872ba-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="872ba-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-230">CC001</span><span class="sxs-lookup"><span data-stu-id="872ba-230">CC001</span></span></td>
<td><span data-ttu-id="872ba-231">RH</span><span class="sxs-lookup"><span data-stu-id="872ba-231">HR</span></span></td>
<td><span data-ttu-id="872ba-232">1 000</span><span class="sxs-lookup"><span data-stu-id="872ba-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-233">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-233">CC002</span></span></td>
<td><span data-ttu-id="872ba-234">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-234">Finance</span></span></td>
<td><span data-ttu-id="872ba-235">6 000</span><span class="sxs-lookup"><span data-stu-id="872ba-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-236">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-236">CC003</span></span></td>
<td><span data-ttu-id="872ba-237">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-237">Assembly</span></span></td>
<td><span data-ttu-id="872ba-238">0</span><span class="sxs-lookup"><span data-stu-id="872ba-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-239">Le tableau suivant illustre le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="872ba-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-240">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-240">Cost object</span></span></th>
<th><span data-ttu-id="872ba-241">Ampleur</span><span class="sxs-lookup"><span data-stu-id="872ba-241">Magnitude</span></span></th>
<th><span data-ttu-id="872ba-242">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="872ba-242">Allocation factor</span></span></th>
<th><span data-ttu-id="872ba-243">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-244">CC001</span><span class="sxs-lookup"><span data-stu-id="872ba-244">CC001</span></span></td>
<td><span data-ttu-id="872ba-245">RH</span><span class="sxs-lookup"><span data-stu-id="872ba-245">HR</span></span></td>
<td><span data-ttu-id="872ba-246">1 000</span><span class="sxs-lookup"><span data-stu-id="872ba-246">1,000</span></span></td>
<td><span data-ttu-id="872ba-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="872ba-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="872ba-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-249">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-249">CC002</span></span></td>
<td><span data-ttu-id="872ba-250">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-250">Finance</span></span></td>
<td><span data-ttu-id="872ba-251">6 000</span><span class="sxs-lookup"><span data-stu-id="872ba-251">6,000</span></span></td>
<td><span data-ttu-id="872ba-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="872ba-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="872ba-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-254">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-254">CC003</span></span></td>
<td><span data-ttu-id="872ba-255">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-255">Assembly</span></span></td>
<td><span data-ttu-id="872ba-256">0</span><span class="sxs-lookup"><span data-stu-id="872ba-256">0</span></span></td>
<td><span data-ttu-id="872ba-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="872ba-258">0,00</span><span class="sxs-lookup"><span data-stu-id="872ba-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-259">Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l'électricité.</span><span class="sxs-lookup"><span data-stu-id="872ba-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="872ba-260">Vous pouvez obtenir ce résultat à l'aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="872ba-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-261">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-261">Cost object</span></span></th>
<th><span data-ttu-id="872ba-262">Formule</span><span class="sxs-lookup"><span data-stu-id="872ba-262">Formula</span></span></th>
<th><span data-ttu-id="872ba-263">Ampleur</span><span class="sxs-lookup"><span data-stu-id="872ba-263">Magnitude</span></span></th>
<th><span data-ttu-id="872ba-264">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="872ba-264">Allocation factor</span></span></th>
<th><span data-ttu-id="872ba-265">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-266">CC001</span><span class="sxs-lookup"><span data-stu-id="872ba-266">CC001</span></span></td>
<td><span data-ttu-id="872ba-267">RH</span><span class="sxs-lookup"><span data-stu-id="872ba-267">HR</span></span></td>
<td><span data-ttu-id="872ba-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="872ba-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="872ba-269">1</span><span class="sxs-lookup"><span data-stu-id="872ba-269">1</span></span></td>
<td><span data-ttu-id="872ba-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="872ba-271">500,00</span><span class="sxs-lookup"><span data-stu-id="872ba-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-272">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-272">CC002</span></span></td>
<td><span data-ttu-id="872ba-273">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-273">Finance</span></span></td>
<td><span data-ttu-id="872ba-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="872ba-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="872ba-275">1</span><span class="sxs-lookup"><span data-stu-id="872ba-275">1</span></span></td>
<td><span data-ttu-id="872ba-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="872ba-277">500,00</span><span class="sxs-lookup"><span data-stu-id="872ba-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-278">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-278">CC003</span></span></td>
<td><span data-ttu-id="872ba-279">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-279">Assembly</span></span></td>
<td><span data-ttu-id="872ba-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="872ba-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="872ba-281">0</span><span class="sxs-lookup"><span data-stu-id="872ba-281">0</span></span></td>
<td><span data-ttu-id="872ba-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="872ba-283">0,00</span><span class="sxs-lookup"><span data-stu-id="872ba-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="872ba-284">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="872ba-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="872ba-285">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="872ba-285">Journal</span></span></th>
<th><span data-ttu-id="872ba-286">Type de journal</span><span class="sxs-lookup"><span data-stu-id="872ba-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="872ba-287">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="872ba-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="872ba-288">Version</span><span class="sxs-lookup"><span data-stu-id="872ba-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-289">00002</span><span class="sxs-lookup"><span data-stu-id="872ba-289">00002</span></span></td>
<td><span data-ttu-id="872ba-290">Journal de calcul de la distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="872ba-291">Exercice</span><span class="sxs-lookup"><span data-stu-id="872ba-291">Fiscal</span></span></td>
<td><span data-ttu-id="872ba-292">2017</span><span class="sxs-lookup"><span data-stu-id="872ba-292">2017</span></span></td>
<td><span data-ttu-id="872ba-293">Période 1</span><span class="sxs-lookup"><span data-stu-id="872ba-293">Period 1</span></span></td>
<td><span data-ttu-id="872ba-294">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="872ba-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="872ba-295">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="872ba-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="872ba-296">Date comptable</span><span class="sxs-lookup"><span data-stu-id="872ba-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-297">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-298">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-298">Cost element</span></span></th>
<th><span data-ttu-id="872ba-299">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-299">Cost behavior</span></span></th>
<th><span data-ttu-id="872ba-300">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-301">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-302">CC099</span><span class="sxs-lookup"><span data-stu-id="872ba-302">CC099</span></span></td>
<td><span data-ttu-id="872ba-303">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="872ba-303">Default cost center</span></span></td>
<td><span data-ttu-id="872ba-304">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-304">10001</span></span></td>
<td><span data-ttu-id="872ba-305">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-305">Electricity</span></span></td>
<td><span data-ttu-id="872ba-306">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-306">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-308">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-309">CC099</span><span class="sxs-lookup"><span data-stu-id="872ba-309">CC099</span></span></td>
<td><span data-ttu-id="872ba-310">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="872ba-310">Default cost center</span></span></td>
<td><span data-ttu-id="872ba-311">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-311">10001</span></span></td>
<td><span data-ttu-id="872ba-312">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-312">Electricity</span></span></td>
<td><span data-ttu-id="872ba-313">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-313">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-314">9 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="872ba-315">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-316">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-317">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-317">Cost element</span></span></th>
<th><span data-ttu-id="872ba-318">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-318">Cost behavior</span></span></th>
<th><span data-ttu-id="872ba-319">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-319">Amount</span></span></th>
<th><span data-ttu-id="872ba-320">Date comptable</span><span class="sxs-lookup"><span data-stu-id="872ba-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-321">CC099</span><span class="sxs-lookup"><span data-stu-id="872ba-321">CC099</span></span></td>
<td><span data-ttu-id="872ba-322">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="872ba-322">Default cost center</span></span></td>
<td><span data-ttu-id="872ba-323">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-323">10001</span></span></td>
<td><span data-ttu-id="872ba-324">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-324">Electricity</span></span></td>
<td><span data-ttu-id="872ba-325">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-325">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-326">-1,000.00</span></span></td>
<td><span data-ttu-id="872ba-327">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-328">CC001</span><span class="sxs-lookup"><span data-stu-id="872ba-328">CC001</span></span></td>
<td><span data-ttu-id="872ba-329">RH</span><span class="sxs-lookup"><span data-stu-id="872ba-329">HR</span></span></td>
<td><span data-ttu-id="872ba-330">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-330">10001</span></span></td>
<td><span data-ttu-id="872ba-331">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-331">Electricity</span></span></td>
<td><span data-ttu-id="872ba-332">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-332">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-333">500,00</span><span class="sxs-lookup"><span data-stu-id="872ba-333">500.00</span></span></td>
<td><span data-ttu-id="872ba-334">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-335">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-335">CC002</span></span></td>
<td><span data-ttu-id="872ba-336">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-336">Finance</span></span></td>
<td><span data-ttu-id="872ba-337">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-337">10001</span></span></td>
<td><span data-ttu-id="872ba-338">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-338">Electricity</span></span></td>
<td><span data-ttu-id="872ba-339">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-339">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-340">500,00</span><span class="sxs-lookup"><span data-stu-id="872ba-340">500.00</span></span></td>
<td><span data-ttu-id="872ba-341">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-342">CC099</span><span class="sxs-lookup"><span data-stu-id="872ba-342">CC099</span></span></td>
<td><span data-ttu-id="872ba-343">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="872ba-343">Default cost center</span></span></td>
<td><span data-ttu-id="872ba-344">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-344">10001</span></span></td>
<td><span data-ttu-id="872ba-345">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-345">Electricity</span></span></td>
<td><span data-ttu-id="872ba-346">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-346">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="872ba-347">-9,000.00</span></span></td>
<td><span data-ttu-id="872ba-348">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-349">CC001</span><span class="sxs-lookup"><span data-stu-id="872ba-349">CC001</span></span></td>
<td><span data-ttu-id="872ba-350">RH</span><span class="sxs-lookup"><span data-stu-id="872ba-350">HR</span></span></td>
<td><span data-ttu-id="872ba-351">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-351">10001</span></span></td>
<td><span data-ttu-id="872ba-352">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-352">Electricity</span></span></td>
<td><span data-ttu-id="872ba-353">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-353">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="872ba-354">1,285.71</span></span></td>
<td><span data-ttu-id="872ba-355">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-356">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-356">CC002</span></span></td>
<td><span data-ttu-id="872ba-357">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-357">Finance</span></span></td>
<td><span data-ttu-id="872ba-358">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-358">10001</span></span></td>
<td><span data-ttu-id="872ba-359">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-359">Electricity</span></span></td>
<td><span data-ttu-id="872ba-360">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-360">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="872ba-361">7,714.29</span></span></td>
<td><span data-ttu-id="872ba-362">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-363">Pour plus d'informations, voir [Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="872ba-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="872ba-364">Étape 3 : Traitement du calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="872ba-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="872ba-365">Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût.</span><span class="sxs-lookup"><span data-stu-id="872ba-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="872ba-366">Les frais sont basés sur un taux de coût prédéterminé et l'ampleur de la base d'affectation de répartition.</span><span class="sxs-lookup"><span data-stu-id="872ba-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="872ba-367">Définition du taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="872ba-367">Define the overhead rate</span></span>

<span data-ttu-id="872ba-368">L'objet de coût CC001 HR contribue à un ensemble de projets internes.</span><span class="sxs-lookup"><span data-stu-id="872ba-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="872ba-369">Un membre de dimension statistique nommé Projets HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="872ba-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-370">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-370">Cost object</span></span></th>
<th><span data-ttu-id="872ba-371">Heures</span><span class="sxs-lookup"><span data-stu-id="872ba-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="872ba-372">Proj 1</span></span></td>
<td><span data-ttu-id="872ba-373">Projet 1</span><span class="sxs-lookup"><span data-stu-id="872ba-373">Project 1</span></span></td>
<td><span data-ttu-id="872ba-374">3</span><span class="sxs-lookup"><span data-stu-id="872ba-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="872ba-375">Proj 2</span></span></td>
<td><span data-ttu-id="872ba-376">Projet 2</span><span class="sxs-lookup"><span data-stu-id="872ba-376">Project 2</span></span></td>
<td><span data-ttu-id="872ba-377">1</span><span class="sxs-lookup"><span data-stu-id="872ba-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-378">Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.</span><span class="sxs-lookup"><span data-stu-id="872ba-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-379">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-379">Cost object</span></span></th>
<th><span data-ttu-id="872ba-380">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-380">Cost element</span></span></th>
<th><span data-ttu-id="872ba-381">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-381">Cost behavior</span></span></th>
<th><span data-ttu-id="872ba-382">Unités</span><span class="sxs-lookup"><span data-stu-id="872ba-382">Units</span></span></th>
<th><span data-ttu-id="872ba-383">Taux</span><span class="sxs-lookup"><span data-stu-id="872ba-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-384">CC001</span><span class="sxs-lookup"><span data-stu-id="872ba-384">CC001</span></span></td>
<td><span data-ttu-id="872ba-385">RH</span><span class="sxs-lookup"><span data-stu-id="872ba-385">HR</span></span></td>
<td><span data-ttu-id="872ba-386">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-386">10001</span></span></td>
<td><span data-ttu-id="872ba-387">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-387">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-388">1</span><span class="sxs-lookup"><span data-stu-id="872ba-388">1</span></span></td>
<td><span data-ttu-id="872ba-389">10</span><span class="sxs-lookup"><span data-stu-id="872ba-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-390">Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="872ba-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-391">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-391">Cost object</span></span></th>
<th><span data-ttu-id="872ba-392">Ampleur</span><span class="sxs-lookup"><span data-stu-id="872ba-392">Magnitude</span></span></th>
<th><span data-ttu-id="872ba-393">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-393">Cost element</span></span></th>
<th><span data-ttu-id="872ba-394">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="872ba-394">Allocation factor</span></span></th>
<th><span data-ttu-id="872ba-395">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="872ba-396">Proj 1</span></span></td>
<td><span data-ttu-id="872ba-397">Projet 1</span><span class="sxs-lookup"><span data-stu-id="872ba-397">Project 1</span></span></td>
<td><span data-ttu-id="872ba-398">3</span><span class="sxs-lookup"><span data-stu-id="872ba-398">3</span></span></td>
<td><span data-ttu-id="872ba-399">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-399">10001</span></span></td>
<td><span data-ttu-id="872ba-400">(3 ÷ 1) × 10m00</span><span class="sxs-lookup"><span data-stu-id="872ba-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="872ba-401">30,00</span><span class="sxs-lookup"><span data-stu-id="872ba-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="872ba-402">Proj 2</span></span></td>
<td><span data-ttu-id="872ba-403">Projet 2</span><span class="sxs-lookup"><span data-stu-id="872ba-403">Project 2</span></span></td>
<td><span data-ttu-id="872ba-404">1</span><span class="sxs-lookup"><span data-stu-id="872ba-404">1</span></span></td>
<td><span data-ttu-id="872ba-405">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-405">10001</span></span></td>
<td><span data-ttu-id="872ba-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="872ba-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="872ba-407">10,00</span><span class="sxs-lookup"><span data-stu-id="872ba-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="872ba-408">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="872ba-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="872ba-409">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="872ba-409">Journal</span></span></th>
<th><span data-ttu-id="872ba-410">Type de journal</span><span class="sxs-lookup"><span data-stu-id="872ba-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="872ba-411">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="872ba-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="872ba-412">Version</span><span class="sxs-lookup"><span data-stu-id="872ba-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-413">00003</span><span class="sxs-lookup"><span data-stu-id="872ba-413">00003</span></span></td>
<td><span data-ttu-id="872ba-414">Journal de calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="872ba-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="872ba-415">Exercice</span><span class="sxs-lookup"><span data-stu-id="872ba-415">Fiscal</span></span></td>
<td><span data-ttu-id="872ba-416">2017</span><span class="sxs-lookup"><span data-stu-id="872ba-416">2017</span></span></td>
<td><span data-ttu-id="872ba-417">Période 1</span><span class="sxs-lookup"><span data-stu-id="872ba-417">Period 1</span></span></td>
<td><span data-ttu-id="872ba-418">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="872ba-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="872ba-419">Entrées du journal (pour le calcul du taux de frais généraux)</span><span class="sxs-lookup"><span data-stu-id="872ba-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="872ba-420">Date comptable</span><span class="sxs-lookup"><span data-stu-id="872ba-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-421">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-421">Cost object</span></span></th>
<th><span data-ttu-id="872ba-422">Ampleur</span><span class="sxs-lookup"><span data-stu-id="872ba-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-423">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="872ba-424">Proj 1</span></span></td>
<td><span data-ttu-id="872ba-425">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="872ba-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="872ba-426">3,00</span><span class="sxs-lookup"><span data-stu-id="872ba-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-427">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="872ba-428">Proj 2</span></span></td>
<td><span data-ttu-id="872ba-429">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="872ba-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="872ba-430">1,00</span><span class="sxs-lookup"><span data-stu-id="872ba-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="872ba-431">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-432">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-433">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-433">Cost element</span></span></th>
<th><span data-ttu-id="872ba-434">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-434">Cost behavior</span></span></th>
<th><span data-ttu-id="872ba-435">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-435">Amount</span></span></th>
<th><span data-ttu-id="872ba-436">Date comptable</span><span class="sxs-lookup"><span data-stu-id="872ba-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="872ba-437">CC0001</span></span></td>
<td><span data-ttu-id="872ba-438">RH</span><span class="sxs-lookup"><span data-stu-id="872ba-438">HR</span></span></td>
<td><span data-ttu-id="872ba-439">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-439">10001</span></span></td>
<td><span data-ttu-id="872ba-440">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-440">Electricity</span></span></td>
<td><span data-ttu-id="872ba-441">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-441">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="872ba-442">-30.00</span></span></td>
<td><span data-ttu-id="872ba-443">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="872ba-444">Proj 1</span></span></td>
<td><span data-ttu-id="872ba-445">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="872ba-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="872ba-446">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-446">10001</span></span></td>
<td><span data-ttu-id="872ba-447">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-447">Electricity</span></span></td>
<td><span data-ttu-id="872ba-448">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-448">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-449">30,00</span><span class="sxs-lookup"><span data-stu-id="872ba-449">30.00</span></span></td>
<td><span data-ttu-id="872ba-450">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-451">CC001</span><span class="sxs-lookup"><span data-stu-id="872ba-451">CC001</span></span></td>
<td><span data-ttu-id="872ba-452">RH</span><span class="sxs-lookup"><span data-stu-id="872ba-452">HR</span></span></td>
<td><span data-ttu-id="872ba-453">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-453">10001</span></span></td>
<td><span data-ttu-id="872ba-454">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-454">Electricity</span></span></td>
<td><span data-ttu-id="872ba-455">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-455">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="872ba-456">-10.00</span></span></td>
<td><span data-ttu-id="872ba-457">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="872ba-458">Proj 2</span></span></td>
<td><span data-ttu-id="872ba-459">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="872ba-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="872ba-460">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-460">10001</span></span></td>
<td><span data-ttu-id="872ba-461">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-461">Electricity</span></span></td>
<td><span data-ttu-id="872ba-462">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-462">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-463">10.00</span><span class="sxs-lookup"><span data-stu-id="872ba-463">10.00</span></span></td>
<td><span data-ttu-id="872ba-464">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-465">Pour plus d'informations, voir [Exécuter le calcul des frais généraux](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="872ba-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="872ba-466">Étape 4 : Traiter le calcul de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="872ba-467">La répartition est utilisée pour affecter le solde d'un objet de coût à d'autres objets de coût en appliquant une base de répartition.</span><span class="sxs-lookup"><span data-stu-id="872ba-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="872ba-468">Finance and Operations prend en charge la méthode de répartition réciproque.</span><span class="sxs-lookup"><span data-stu-id="872ba-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="872ba-469">Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés.</span><span class="sxs-lookup"><span data-stu-id="872ba-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="872ba-470">Le système détermine automatiquement l'ordre correct selon lequel exécuter les répartitions.</span><span class="sxs-lookup"><span data-stu-id="872ba-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="872ba-471">Le solde d'un objet de coût est réparti par une seule base de répartition.</span><span class="sxs-lookup"><span data-stu-id="872ba-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="872ba-472">Les répartitions entre plusieurs dimensions d'objets de coût et leurs membres respectifs sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="872ba-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="872ba-473">L'ordre de répartition est contrôlé par l'unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="872ba-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="872ba-474">[![Méthode réciproque](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="872ba-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="872ba-475">Définir la répartition de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-475">Define the cost allocation</span></span>

<span data-ttu-id="872ba-476">Voici un exemple simple expliquant comment suivre le flux du coût.</span><span class="sxs-lookup"><span data-stu-id="872ba-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="872ba-477">L'objet de coût CC001 HR contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="872ba-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="872ba-478">Un membre de dimension statistique nommé Services HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="872ba-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-479">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-479">Cost object</span></span></th>
<th><span data-ttu-id="872ba-480">Services HR</span><span class="sxs-lookup"><span data-stu-id="872ba-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-481">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-481">CC002</span></span></td>
<td><span data-ttu-id="872ba-482">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-482">Finance</span></span></td>
<td><span data-ttu-id="872ba-483">35</span><span class="sxs-lookup"><span data-stu-id="872ba-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-484">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-484">CC003</span></span></td>
<td><span data-ttu-id="872ba-485">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-485">Assembly</span></span></td>
<td><span data-ttu-id="872ba-486">55</span><span class="sxs-lookup"><span data-stu-id="872ba-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-487">CC004</span><span class="sxs-lookup"><span data-stu-id="872ba-487">CC004</span></span></td>
<td><span data-ttu-id="872ba-488">Emballage</span><span class="sxs-lookup"><span data-stu-id="872ba-488">Packaging</span></span></td>
<td><span data-ttu-id="872ba-489">10</span><span class="sxs-lookup"><span data-stu-id="872ba-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-490">L'objet de coût CC002 Finance contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="872ba-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="872ba-491">Un membre de dimension statistique nommé Services Finance est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="872ba-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-492">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-492">Cost object</span></span></th>
<th><span data-ttu-id="872ba-493">Services Finance</span><span class="sxs-lookup"><span data-stu-id="872ba-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-494">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-494">CC003</span></span></td>
<td><span data-ttu-id="872ba-495">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-495">Assembly</span></span></td>
<td><span data-ttu-id="872ba-496">65</span><span class="sxs-lookup"><span data-stu-id="872ba-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-497">CC004</span><span class="sxs-lookup"><span data-stu-id="872ba-497">CC004</span></span></td>
<td><span data-ttu-id="872ba-498">Emballage</span><span class="sxs-lookup"><span data-stu-id="872ba-498">Packaging</span></span></td>
<td><span data-ttu-id="872ba-499">35</span><span class="sxs-lookup"><span data-stu-id="872ba-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-500">L'objet de coût CC003 Assemblage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="872ba-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="872ba-501">Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="872ba-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-502">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-502">Cost object</span></span></th>
<th><span data-ttu-id="872ba-503">Services Assemblage (heures)</span><span class="sxs-lookup"><span data-stu-id="872ba-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-504">Prod 1</span></span></td>
<td><span data-ttu-id="872ba-505">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-505">Product 1</span></span></td>
<td><span data-ttu-id="872ba-506">60</span><span class="sxs-lookup"><span data-stu-id="872ba-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-507">Prod 2</span></span></td>
<td><span data-ttu-id="872ba-508">Produit 2</span><span class="sxs-lookup"><span data-stu-id="872ba-508">Product 2</span></span></td>
<td><span data-ttu-id="872ba-509">20</span><span class="sxs-lookup"><span data-stu-id="872ba-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-510">L'objet de coût CC004 Emballage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="872ba-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="872ba-511">Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="872ba-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-512">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-512">Cost object</span></span></th>
<th><span data-ttu-id="872ba-513">Services Emballage (heures)</span><span class="sxs-lookup"><span data-stu-id="872ba-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-514">Prod 1</span></span></td>
<td><span data-ttu-id="872ba-515">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-515">Product 1</span></span></td>
<td><span data-ttu-id="872ba-516">80</span><span class="sxs-lookup"><span data-stu-id="872ba-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-517">Prod 2</span></span></td>
<td><span data-ttu-id="872ba-518">Produit 2</span><span class="sxs-lookup"><span data-stu-id="872ba-518">Product 2</span></span></td>
<td><span data-ttu-id="872ba-519">15</span><span class="sxs-lookup"><span data-stu-id="872ba-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="872ba-520">Dans Finance and Operations, les mesures statistiques telles que les heures de production qu'un produit consomme peuvent être dérivées des données sources.</span><span class="sxs-lookup"><span data-stu-id="872ba-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="872ba-521">Pour plus d'informations, voir [Modèle de fournisseur de mesures statistiques](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="872ba-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="872ba-522">Le tableau suivant présente le résultat lorsque les services RH sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="872ba-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-523">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-523">Cost object</span></span></th>
<th><span data-ttu-id="872ba-524">Ampleur</span><span class="sxs-lookup"><span data-stu-id="872ba-524">Magnitude</span></span></th>
<th><span data-ttu-id="872ba-525">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="872ba-525">Allocation factor</span></span></th>
<th><span data-ttu-id="872ba-526">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-526">Amount</span></span></th>
<th><span data-ttu-id="872ba-527">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-528">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-528">CC002</span></span></td>
<td><span data-ttu-id="872ba-529">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-529">Finance</span></span></td>
<td><span data-ttu-id="872ba-530">35</span><span class="sxs-lookup"><span data-stu-id="872ba-530">35</span></span></td>
<td><span data-ttu-id="872ba-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="872ba-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="872ba-532">175.00</span><span class="sxs-lookup"><span data-stu-id="872ba-532">175.00</span></span></td>
<td><span data-ttu-id="872ba-533">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-534">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-534">CC003</span></span></td>
<td><span data-ttu-id="872ba-535">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-535">Assembly</span></span></td>
<td><span data-ttu-id="872ba-536">55</span><span class="sxs-lookup"><span data-stu-id="872ba-536">55</span></span></td>
<td><span data-ttu-id="872ba-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="872ba-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="872ba-538">275.00</span><span class="sxs-lookup"><span data-stu-id="872ba-538">275.00</span></span></td>
<td><span data-ttu-id="872ba-539">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-540">CC004</span><span class="sxs-lookup"><span data-stu-id="872ba-540">CC004</span></span></td>
<td><span data-ttu-id="872ba-541">Emballage</span><span class="sxs-lookup"><span data-stu-id="872ba-541">Packaging</span></span></td>
<td><span data-ttu-id="872ba-542">10</span><span class="sxs-lookup"><span data-stu-id="872ba-542">10</span></span></td>
<td><span data-ttu-id="872ba-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="872ba-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="872ba-544">50,00</span><span class="sxs-lookup"><span data-stu-id="872ba-544">50.00</span></span></td>
<td><span data-ttu-id="872ba-545">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-546">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-546">CC002</span></span></td>
<td><span data-ttu-id="872ba-547">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-547">Finance</span></span></td>
<td><span data-ttu-id="872ba-548">35</span><span class="sxs-lookup"><span data-stu-id="872ba-548">35</span></span></td>
<td><span data-ttu-id="872ba-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="872ba-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="872ba-550">436.00</span><span class="sxs-lookup"><span data-stu-id="872ba-550">436.00</span></span></td>
<td><span data-ttu-id="872ba-551">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-552">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-552">CC003</span></span></td>
<td><span data-ttu-id="872ba-553">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-553">Assembly</span></span></td>
<td><span data-ttu-id="872ba-554">55</span><span class="sxs-lookup"><span data-stu-id="872ba-554">55</span></span></td>
<td><span data-ttu-id="872ba-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="872ba-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="872ba-556">685.14</span><span class="sxs-lookup"><span data-stu-id="872ba-556">685.14</span></span></td>
<td><span data-ttu-id="872ba-557">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-558">CC004</span><span class="sxs-lookup"><span data-stu-id="872ba-558">CC004</span></span></td>
<td><span data-ttu-id="872ba-559">Emballage</span><span class="sxs-lookup"><span data-stu-id="872ba-559">Packaging</span></span></td>
<td><span data-ttu-id="872ba-560">10</span><span class="sxs-lookup"><span data-stu-id="872ba-560">10</span></span></td>
<td><span data-ttu-id="872ba-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="872ba-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="872ba-562">124.57</span><span class="sxs-lookup"><span data-stu-id="872ba-562">124.57</span></span></td>
<td><span data-ttu-id="872ba-563">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-564">Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="872ba-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-565">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-565">Cost object</span></span></th>
<th><span data-ttu-id="872ba-566">Ampleur</span><span class="sxs-lookup"><span data-stu-id="872ba-566">Magnitude</span></span></th>
<th><span data-ttu-id="872ba-567">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="872ba-567">Allocation factor</span></span></th>
<th><span data-ttu-id="872ba-568">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-568">Amount</span></span></th>
<th><span data-ttu-id="872ba-569">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-570">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-570">CC003</span></span></td>
<td><span data-ttu-id="872ba-571">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-571">Assembly</span></span></td>
<td><span data-ttu-id="872ba-572">65</span><span class="sxs-lookup"><span data-stu-id="872ba-572">65</span></span></td>
<td><span data-ttu-id="872ba-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="872ba-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="872ba-574">438.75</span><span class="sxs-lookup"><span data-stu-id="872ba-574">438.75</span></span></td>
<td><span data-ttu-id="872ba-575">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-576">CC004</span><span class="sxs-lookup"><span data-stu-id="872ba-576">CC004</span></span></td>
<td><span data-ttu-id="872ba-577">Emballage</span><span class="sxs-lookup"><span data-stu-id="872ba-577">Packaging</span></span></td>
<td><span data-ttu-id="872ba-578">35</span><span class="sxs-lookup"><span data-stu-id="872ba-578">35</span></span></td>
<td><span data-ttu-id="872ba-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="872ba-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="872ba-580">236.25</span><span class="sxs-lookup"><span data-stu-id="872ba-580">236.25</span></span></td>
<td><span data-ttu-id="872ba-581">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-582">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-582">CC003</span></span></td>
<td><span data-ttu-id="872ba-583">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-583">Assembly</span></span></td>
<td><span data-ttu-id="872ba-584">65</span><span class="sxs-lookup"><span data-stu-id="872ba-584">65</span></span></td>
<td><span data-ttu-id="872ba-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="872ba-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="872ba-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="872ba-586">5,297.69</span></span></td>
<td><span data-ttu-id="872ba-587">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-588">CC004</span><span class="sxs-lookup"><span data-stu-id="872ba-588">CC004</span></span></td>
<td><span data-ttu-id="872ba-589">Emballage</span><span class="sxs-lookup"><span data-stu-id="872ba-589">Packaging</span></span></td>
<td><span data-ttu-id="872ba-590">35</span><span class="sxs-lookup"><span data-stu-id="872ba-590">35</span></span></td>
<td><span data-ttu-id="872ba-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="872ba-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="872ba-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="872ba-592">2,852.60</span></span></td>
<td><span data-ttu-id="872ba-593">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-594">Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="872ba-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-595">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-595">Cost object</span></span></th>
<th><span data-ttu-id="872ba-596">Ampleur</span><span class="sxs-lookup"><span data-stu-id="872ba-596">Magnitude</span></span></th>
<th><span data-ttu-id="872ba-597">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="872ba-597">Allocation factor</span></span></th>
<th><span data-ttu-id="872ba-598">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-598">Amount</span></span></th>
<th><span data-ttu-id="872ba-599">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-600">Prod 1</span></span></td>
<td><span data-ttu-id="872ba-601">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-601">Product 1</span></span></td>
<td><span data-ttu-id="872ba-602">60</span><span class="sxs-lookup"><span data-stu-id="872ba-602">60</span></span></td>
<td><span data-ttu-id="872ba-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="872ba-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="872ba-604">535.31</span><span class="sxs-lookup"><span data-stu-id="872ba-604">535.31</span></span></td>
<td><span data-ttu-id="872ba-605">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-606">Prod 2</span></span></td>
<td><span data-ttu-id="872ba-607">Produit 2</span><span class="sxs-lookup"><span data-stu-id="872ba-607">Product 2</span></span></td>
<td><span data-ttu-id="872ba-608">20</span><span class="sxs-lookup"><span data-stu-id="872ba-608">20</span></span></td>
<td><span data-ttu-id="872ba-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="872ba-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="872ba-610">178.44</span><span class="sxs-lookup"><span data-stu-id="872ba-610">178.44</span></span></td>
<td><span data-ttu-id="872ba-611">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-612">Prod 1</span></span></td>
<td><span data-ttu-id="872ba-613">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-613">Product 1</span></span></td>
<td><span data-ttu-id="872ba-614">60</span><span class="sxs-lookup"><span data-stu-id="872ba-614">60</span></span></td>
<td><span data-ttu-id="872ba-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="872ba-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="872ba-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="872ba-616">4,487.12</span></span></td>
<td><span data-ttu-id="872ba-617">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-618">Prod 2</span></span></td>
<td><span data-ttu-id="872ba-619">Produit 2</span><span class="sxs-lookup"><span data-stu-id="872ba-619">Product 2</span></span></td>
<td><span data-ttu-id="872ba-620">20</span><span class="sxs-lookup"><span data-stu-id="872ba-620">20</span></span></td>
<td><span data-ttu-id="872ba-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="872ba-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="872ba-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="872ba-622">1,495.71</span></span></td>
<td><span data-ttu-id="872ba-623">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="872ba-624">Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="872ba-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-625">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-625">Cost object</span></span></th>
<th><span data-ttu-id="872ba-626">Ampleur</span><span class="sxs-lookup"><span data-stu-id="872ba-626">Magnitude</span></span></th>
<th><span data-ttu-id="872ba-627">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="872ba-627">Allocation factor</span></span></th>
<th><span data-ttu-id="872ba-628">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-628">Amount</span></span></th>
<th><span data-ttu-id="872ba-629">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-630">Prod 1</span></span></td>
<td><span data-ttu-id="872ba-631">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-631">Product 1</span></span></td>
<td><span data-ttu-id="872ba-632">80</span><span class="sxs-lookup"><span data-stu-id="872ba-632">80</span></span></td>
<td><span data-ttu-id="872ba-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="872ba-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="872ba-634">241.05</span><span class="sxs-lookup"><span data-stu-id="872ba-634">241.05</span></span></td>
<td><span data-ttu-id="872ba-635">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-636">Prod 2</span></span></td>
<td><span data-ttu-id="872ba-637">Produit 2</span><span class="sxs-lookup"><span data-stu-id="872ba-637">Product 2</span></span></td>
<td><span data-ttu-id="872ba-638">15</span><span class="sxs-lookup"><span data-stu-id="872ba-638">15</span></span></td>
<td><span data-ttu-id="872ba-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="872ba-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="872ba-640">45.20</span><span class="sxs-lookup"><span data-stu-id="872ba-640">45.20</span></span></td>
<td><span data-ttu-id="872ba-641">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-642">Prod 1</span></span></td>
<td><span data-ttu-id="872ba-643">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-643">Product 1</span></span></td>
<td><span data-ttu-id="872ba-644">80</span><span class="sxs-lookup"><span data-stu-id="872ba-644">80</span></span></td>
<td><span data-ttu-id="872ba-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="872ba-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="872ba-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="872ba-646">2,507.09</span></span></td>
<td><span data-ttu-id="872ba-647">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-648">Prod 2</span></span></td>
<td><span data-ttu-id="872ba-649">Produit 2</span><span class="sxs-lookup"><span data-stu-id="872ba-649">Product 2</span></span></td>
<td><span data-ttu-id="872ba-650">15</span><span class="sxs-lookup"><span data-stu-id="872ba-650">15</span></span></td>
<td><span data-ttu-id="872ba-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="872ba-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="872ba-652">470.08</span><span class="sxs-lookup"><span data-stu-id="872ba-652">470.08</span></span></td>
<td><span data-ttu-id="872ba-653">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="872ba-654">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="872ba-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="872ba-655">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="872ba-655">Journal</span></span></th>
<th><span data-ttu-id="872ba-656">Type de journal</span><span class="sxs-lookup"><span data-stu-id="872ba-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="872ba-657">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="872ba-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="872ba-658">Version</span><span class="sxs-lookup"><span data-stu-id="872ba-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-659">00004</span><span class="sxs-lookup"><span data-stu-id="872ba-659">00004</span></span></td>
<td><span data-ttu-id="872ba-660">Journal de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="872ba-661">Exercice</span><span class="sxs-lookup"><span data-stu-id="872ba-661">Fiscal</span></span></td>
<td><span data-ttu-id="872ba-662">2017</span><span class="sxs-lookup"><span data-stu-id="872ba-662">2017</span></span></td>
<td><span data-ttu-id="872ba-663">Période 1</span><span class="sxs-lookup"><span data-stu-id="872ba-663">Period 1</span></span></td>
<td><span data-ttu-id="872ba-664">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="872ba-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="872ba-665">Lignes de journal</span><span class="sxs-lookup"><span data-stu-id="872ba-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="872ba-666">Date comptable</span><span class="sxs-lookup"><span data-stu-id="872ba-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-667">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-668">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-668">Cost element</span></span></th>
<th><span data-ttu-id="872ba-669">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-669">Cost behavior</span></span></th>
<th><span data-ttu-id="872ba-670">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-671">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-672">CC001</span><span class="sxs-lookup"><span data-stu-id="872ba-672">CC001</span></span></td>
<td><span data-ttu-id="872ba-673">RH</span><span class="sxs-lookup"><span data-stu-id="872ba-673">HR</span></span></td>
<td><span data-ttu-id="872ba-674">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-674">10001</span></span></td>
<td><span data-ttu-id="872ba-675">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-675">Electricity</span></span></td>
<td><span data-ttu-id="872ba-676">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-676">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-677">500,00</span><span class="sxs-lookup"><span data-stu-id="872ba-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-678">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-679">CC001</span><span class="sxs-lookup"><span data-stu-id="872ba-679">CC001</span></span></td>
<td><span data-ttu-id="872ba-680">RH</span><span class="sxs-lookup"><span data-stu-id="872ba-680">HR</span></span></td>
<td><span data-ttu-id="872ba-681">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-681">10001</span></span></td>
<td><span data-ttu-id="872ba-682">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-682">Electricity</span></span></td>
<td><span data-ttu-id="872ba-683">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-683">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="872ba-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-685">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-686">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-686">CC002</span></span></td>
<td><span data-ttu-id="872ba-687">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-687">Finance</span></span></td>
<td><span data-ttu-id="872ba-688">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-688">10001</span></span></td>
<td><span data-ttu-id="872ba-689">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-689">Electricity</span></span></td>
<td><span data-ttu-id="872ba-690">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-690">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-691">675.00</span><span class="sxs-lookup"><span data-stu-id="872ba-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-692">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-693">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-693">CC002</span></span></td>
<td><span data-ttu-id="872ba-694">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-694">Finance</span></span></td>
<td><span data-ttu-id="872ba-695">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-695">10001</span></span></td>
<td><span data-ttu-id="872ba-696">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-696">Electricity</span></span></td>
<td><span data-ttu-id="872ba-697">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-697">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="872ba-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-699">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-700">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-700">CC003</span></span></td>
<td><span data-ttu-id="872ba-701">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-701">Assembly</span></span></td>
<td><span data-ttu-id="872ba-702">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-702">10001</span></span></td>
<td><span data-ttu-id="872ba-703">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-703">Electricity</span></span></td>
<td><span data-ttu-id="872ba-704">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-704">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-705">713.75</span><span class="sxs-lookup"><span data-stu-id="872ba-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-706">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-707">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-707">CC003</span></span></td>
<td><span data-ttu-id="872ba-708">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-708">Assembly</span></span></td>
<td><span data-ttu-id="872ba-709">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-709">10001</span></span></td>
<td><span data-ttu-id="872ba-710">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-710">Electricity</span></span></td>
<td><span data-ttu-id="872ba-711">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-711">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="872ba-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-713">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-714">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-714">CC003</span></span></td>
<td><span data-ttu-id="872ba-715">Emballage</span><span class="sxs-lookup"><span data-stu-id="872ba-715">Packaging</span></span></td>
<td><span data-ttu-id="872ba-716">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-716">10001</span></span></td>
<td><span data-ttu-id="872ba-717">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-717">Electricity</span></span></td>
<td><span data-ttu-id="872ba-718">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-718">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-719">286.25</span><span class="sxs-lookup"><span data-stu-id="872ba-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-720">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-721">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-721">CC003</span></span></td>
<td><span data-ttu-id="872ba-722">Emballage</span><span class="sxs-lookup"><span data-stu-id="872ba-722">Packaging</span></span></td>
<td><span data-ttu-id="872ba-723">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-723">10001</span></span></td>
<td><span data-ttu-id="872ba-724">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-724">Electricity</span></span></td>
<td><span data-ttu-id="872ba-725">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-725">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="872ba-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-727">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-728">Prod 1</span></span></td>
<td><span data-ttu-id="872ba-729">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-729">Product 1</span></span></td>
<td><span data-ttu-id="872ba-730">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-730">10001</span></span></td>
<td><span data-ttu-id="872ba-731">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-731">Electricity</span></span></td>
<td><span data-ttu-id="872ba-732">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-732">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-733">776.36</span><span class="sxs-lookup"><span data-stu-id="872ba-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-734">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-735">Prod 1</span></span></td>
<td><span data-ttu-id="872ba-736">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-736">Product 1</span></span></td>
<td><span data-ttu-id="872ba-737">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-737">10001</span></span></td>
<td><span data-ttu-id="872ba-738">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-738">Electricity</span></span></td>
<td><span data-ttu-id="872ba-739">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-739">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="872ba-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-741">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-742">Prod 2</span></span></td>
<td><span data-ttu-id="872ba-743">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-743">Product 1</span></span></td>
<td><span data-ttu-id="872ba-744">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-744">10001</span></span></td>
<td><span data-ttu-id="872ba-745">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-745">Electricity</span></span></td>
<td><span data-ttu-id="872ba-746">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-746">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-747">223.64</span><span class="sxs-lookup"><span data-stu-id="872ba-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-748">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="872ba-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-749">Prod 2</span></span></td>
<td><span data-ttu-id="872ba-750">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-750">Product 1</span></span></td>
<td><span data-ttu-id="872ba-751">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-751">10001</span></span></td>
<td><span data-ttu-id="872ba-752">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-752">Electricity</span></span></td>
<td><span data-ttu-id="872ba-753">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-753">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="872ba-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="872ba-755">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="872ba-756">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="872ba-757">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-757">Cost element</span></span></th>
<th><span data-ttu-id="872ba-758">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="872ba-758">Cost behavior</span></span></th>
<th><span data-ttu-id="872ba-759">Montant</span><span class="sxs-lookup"><span data-stu-id="872ba-759">Amount</span></span></th>
<th><span data-ttu-id="872ba-760">Date comptable</span><span class="sxs-lookup"><span data-stu-id="872ba-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="872ba-761">CC001</span><span class="sxs-lookup"><span data-stu-id="872ba-761">CC001</span></span></td>
<td><span data-ttu-id="872ba-762">RH</span><span class="sxs-lookup"><span data-stu-id="872ba-762">HR</span></span></td>
<td><span data-ttu-id="872ba-763">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-763">10001</span></span></td>
<td><span data-ttu-id="872ba-764">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-764">Electricity</span></span></td>
<td><span data-ttu-id="872ba-765">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-765">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="872ba-766">-500.00</span></span></td>
<td><span data-ttu-id="872ba-767">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-768">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-768">CC002</span></span></td>
<td><span data-ttu-id="872ba-769">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-769">Finance</span></span></td>
<td><span data-ttu-id="872ba-770">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-770">10001</span></span></td>
<td><span data-ttu-id="872ba-771">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-771">Electricity</span></span></td>
<td><span data-ttu-id="872ba-772">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-772">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-773">175.00</span><span class="sxs-lookup"><span data-stu-id="872ba-773">175.00</span></span></td>
<td><span data-ttu-id="872ba-774">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-775">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-775">CC003</span></span></td>
<td><span data-ttu-id="872ba-776">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-776">Assembly</span></span></td>
<td><span data-ttu-id="872ba-777">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-777">10001</span></span></td>
<td><span data-ttu-id="872ba-778">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-778">Electricity</span></span></td>
<td><span data-ttu-id="872ba-779">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-779">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-780">275.00</span><span class="sxs-lookup"><span data-stu-id="872ba-780">275.00</span></span></td>
<td><span data-ttu-id="872ba-781">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-782">CC004</span><span class="sxs-lookup"><span data-stu-id="872ba-782">CC004</span></span></td>
<td><span data-ttu-id="872ba-783">Emballage</span><span class="sxs-lookup"><span data-stu-id="872ba-783">Packaging</span></span></td>
<td><span data-ttu-id="872ba-784">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-784">10001</span></span></td>
<td><span data-ttu-id="872ba-785">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-785">Electricity</span></span></td>
<td><span data-ttu-id="872ba-786">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-786">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-787">50,00</span><span class="sxs-lookup"><span data-stu-id="872ba-787">50,00</span></span></td>
<td><span data-ttu-id="872ba-788">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-789">CC001</span><span class="sxs-lookup"><span data-stu-id="872ba-789">CC001</span></span></td>
<td><span data-ttu-id="872ba-790">RH</span><span class="sxs-lookup"><span data-stu-id="872ba-790">HR</span></span></td>
<td><span data-ttu-id="872ba-791">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-791">10001</span></span></td>
<td><span data-ttu-id="872ba-792">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-792">Electricity</span></span></td>
<td><span data-ttu-id="872ba-793">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-793">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="872ba-794">-1,245.71</span></span></td>
<td><span data-ttu-id="872ba-795">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-796">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-796">CC002</span></span></td>
<td><span data-ttu-id="872ba-797">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-797">Finance</span></span></td>
<td><span data-ttu-id="872ba-798">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-798">10001</span></span></td>
<td><span data-ttu-id="872ba-799">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-799">Electricity</span></span></td>
<td><span data-ttu-id="872ba-800">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-800">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-801">436.00</span><span class="sxs-lookup"><span data-stu-id="872ba-801">436.00</span></span></td>
<td><span data-ttu-id="872ba-802">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-803">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-803">CC003</span></span></td>
<td><span data-ttu-id="872ba-804">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-804">Assembly</span></span></td>
<td><span data-ttu-id="872ba-805">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-805">10001</span></span></td>
<td><span data-ttu-id="872ba-806">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-806">Electricity</span></span></td>
<td><span data-ttu-id="872ba-807">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-807">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-808">685.14</span><span class="sxs-lookup"><span data-stu-id="872ba-808">685.14</span></span></td>
<td><span data-ttu-id="872ba-809">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-810">CC004</span><span class="sxs-lookup"><span data-stu-id="872ba-810">CC004</span></span></td>
<td><span data-ttu-id="872ba-811">Emballage</span><span class="sxs-lookup"><span data-stu-id="872ba-811">Packaging</span></span></td>
<td><span data-ttu-id="872ba-812">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-812">10001</span></span></td>
<td><span data-ttu-id="872ba-813">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-813">Electricity</span></span></td>
<td><span data-ttu-id="872ba-814">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-814">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-815">124.57</span><span class="sxs-lookup"><span data-stu-id="872ba-815">124.57</span></span></td>
<td><span data-ttu-id="872ba-816">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-817">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-817">CC002</span></span></td>
<td><span data-ttu-id="872ba-818">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-818">Finance</span></span></td>
<td><span data-ttu-id="872ba-819">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-819">10001</span></span></td>
<td><span data-ttu-id="872ba-820">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-820">Electricity</span></span></td>
<td><span data-ttu-id="872ba-821">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-821">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="872ba-822">-675.00</span></span></td>
<td><span data-ttu-id="872ba-823">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-824">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-824">CC003</span></span></td>
<td><span data-ttu-id="872ba-825">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-825">Assembly</span></span></td>
<td><span data-ttu-id="872ba-826">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-826">10001</span></span></td>
<td><span data-ttu-id="872ba-827">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-827">Electricity</span></span></td>
<td><span data-ttu-id="872ba-828">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-828">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-829">438.75</span><span class="sxs-lookup"><span data-stu-id="872ba-829">438.75</span></span></td>
<td><span data-ttu-id="872ba-830">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-831">CC004</span><span class="sxs-lookup"><span data-stu-id="872ba-831">CC004</span></span></td>
<td><span data-ttu-id="872ba-832">Emballage</span><span class="sxs-lookup"><span data-stu-id="872ba-832">Packaging</span></span></td>
<td><span data-ttu-id="872ba-833">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-833">10001</span></span></td>
<td><span data-ttu-id="872ba-834">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-834">Electricity</span></span></td>
<td><span data-ttu-id="872ba-835">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-835">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-836">236.25</span><span class="sxs-lookup"><span data-stu-id="872ba-836">236.25</span></span></td>
<td><span data-ttu-id="872ba-837">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-838">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-838">CC002</span></span></td>
<td><span data-ttu-id="872ba-839">Finances</span><span class="sxs-lookup"><span data-stu-id="872ba-839">Finance</span></span></td>
<td><span data-ttu-id="872ba-840">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-840">10001</span></span></td>
<td><span data-ttu-id="872ba-841">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-841">Electricity</span></span></td>
<td><span data-ttu-id="872ba-842">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-842">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="872ba-843">-8,150.29</span></span></td>
<td><span data-ttu-id="872ba-844">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-845">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-845">CC003</span></span></td>
<td><span data-ttu-id="872ba-846">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-846">Assembly</span></span></td>
<td><span data-ttu-id="872ba-847">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-847">10001</span></span></td>
<td><span data-ttu-id="872ba-848">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-848">Electricity</span></span></td>
<td><span data-ttu-id="872ba-849">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-849">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="872ba-850">5,297.69</span></span></td>
<td><span data-ttu-id="872ba-851">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-852">CC004</span><span class="sxs-lookup"><span data-stu-id="872ba-852">CC004</span></span></td>
<td><span data-ttu-id="872ba-853">Emballage</span><span class="sxs-lookup"><span data-stu-id="872ba-853">Packaging</span></span></td>
<td><span data-ttu-id="872ba-854">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-854">10001</span></span></td>
<td><span data-ttu-id="872ba-855">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-855">Electricity</span></span></td>
<td><span data-ttu-id="872ba-856">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-856">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="872ba-857">2,852.60</span></span></td>
<td><span data-ttu-id="872ba-858">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-859">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-859">CC003</span></span></td>
<td><span data-ttu-id="872ba-860">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-860">Assembly</span></span></td>
<td><span data-ttu-id="872ba-861">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-861">10001</span></span></td>
<td><span data-ttu-id="872ba-862">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-862">Electricity</span></span></td>
<td><span data-ttu-id="872ba-863">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-863">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="872ba-864">-713.75</span></span></td>
<td><span data-ttu-id="872ba-865">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-866">Prod 1</span></span></td>
<td><span data-ttu-id="872ba-867">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-867">Product 1</span></span></td>
<td><span data-ttu-id="872ba-868">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-868">10001</span></span></td>
<td><span data-ttu-id="872ba-869">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-869">Electricity</span></span></td>
<td><span data-ttu-id="872ba-870">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-870">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-871">535.31</span><span class="sxs-lookup"><span data-stu-id="872ba-871">535.31</span></span></td>
<td><span data-ttu-id="872ba-872">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-873">Prod 2</span></span></td>
<td><span data-ttu-id="872ba-874">Produit 2</span><span class="sxs-lookup"><span data-stu-id="872ba-874">Product 2</span></span></td>
<td><span data-ttu-id="872ba-875">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-875">10001</span></span></td>
<td><span data-ttu-id="872ba-876">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-876">Electricity</span></span></td>
<td><span data-ttu-id="872ba-877">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-877">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-878">178.44</span><span class="sxs-lookup"><span data-stu-id="872ba-878">178.44</span></span></td>
<td><span data-ttu-id="872ba-879">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-880">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-880">CC003</span></span></td>
<td><span data-ttu-id="872ba-881">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-881">Assembly</span></span></td>
<td><span data-ttu-id="872ba-882">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-882">10001</span></span></td>
<td><span data-ttu-id="872ba-883">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-883">Electricity</span></span></td>
<td><span data-ttu-id="872ba-884">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-884">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="872ba-885">-5,982.83</span></span></td>
<td><span data-ttu-id="872ba-886">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-887">Prod 1</span></span></td>
<td><span data-ttu-id="872ba-888">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-888">Product 1</span></span></td>
<td><span data-ttu-id="872ba-889">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-889">10001</span></span></td>
<td><span data-ttu-id="872ba-890">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-890">Electricity</span></span></td>
<td><span data-ttu-id="872ba-891">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-891">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="872ba-892">4,487.12</span></span></td>
<td><span data-ttu-id="872ba-893">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-894">Prod 2</span></span></td>
<td><span data-ttu-id="872ba-895">Produit 2</span><span class="sxs-lookup"><span data-stu-id="872ba-895">Product 2</span></span></td>
<td><span data-ttu-id="872ba-896">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-896">10001</span></span></td>
<td><span data-ttu-id="872ba-897">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-897">Electricity</span></span></td>
<td><span data-ttu-id="872ba-898">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-898">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="872ba-899">1,495.71</span></span></td>
<td><span data-ttu-id="872ba-900">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-901">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-901">CC003</span></span></td>
<td><span data-ttu-id="872ba-902">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-902">Assembly</span></span></td>
<td><span data-ttu-id="872ba-903">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-903">10001</span></span></td>
<td><span data-ttu-id="872ba-904">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-904">Electricity</span></span></td>
<td><span data-ttu-id="872ba-905">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-905">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="872ba-906">-286.25</span></span></td>
<td><span data-ttu-id="872ba-907">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-908">Prod 1</span></span></td>
<td><span data-ttu-id="872ba-909">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-909">Product 1</span></span></td>
<td><span data-ttu-id="872ba-910">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-910">10001</span></span></td>
<td><span data-ttu-id="872ba-911">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-911">Electricity</span></span></td>
<td><span data-ttu-id="872ba-912">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-912">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-913">241.05</span><span class="sxs-lookup"><span data-stu-id="872ba-913">241.05</span></span></td>
<td><span data-ttu-id="872ba-914">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-915">Prod 2</span></span></td>
<td><span data-ttu-id="872ba-916">Produit 2</span><span class="sxs-lookup"><span data-stu-id="872ba-916">Product 2</span></span></td>
<td><span data-ttu-id="872ba-917">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-917">10001</span></span></td>
<td><span data-ttu-id="872ba-918">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-918">Electricity</span></span></td>
<td><span data-ttu-id="872ba-919">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-919">Fixed cost</span></span></td>
<td><span data-ttu-id="872ba-920">45.20</span><span class="sxs-lookup"><span data-stu-id="872ba-920">45.20</span></span></td>
<td><span data-ttu-id="872ba-921">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-922">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-922">CC003</span></span></td>
<td><span data-ttu-id="872ba-923">Assemblage</span><span class="sxs-lookup"><span data-stu-id="872ba-923">Assembly</span></span></td>
<td><span data-ttu-id="872ba-924">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-924">10001</span></span></td>
<td><span data-ttu-id="872ba-925">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-925">Electricity</span></span></td>
<td><span data-ttu-id="872ba-926">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-926">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="872ba-927">-2,977.17</span></span></td>
<td><span data-ttu-id="872ba-928">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-929">Prod 1</span></span></td>
<td><span data-ttu-id="872ba-930">Produit 1</span><span class="sxs-lookup"><span data-stu-id="872ba-930">Product 1</span></span></td>
<td><span data-ttu-id="872ba-931">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-931">10001</span></span></td>
<td><span data-ttu-id="872ba-932">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-932">Electricity</span></span></td>
<td><span data-ttu-id="872ba-933">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-933">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="872ba-934">2,507.09</span></span></td>
<td><span data-ttu-id="872ba-935">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="872ba-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-936">Prod 2</span></span></td>
<td><span data-ttu-id="872ba-937">Produit 2</span><span class="sxs-lookup"><span data-stu-id="872ba-937">Product 2</span></span></td>
<td><span data-ttu-id="872ba-938">10001</span><span class="sxs-lookup"><span data-stu-id="872ba-938">10001</span></span></td>
<td><span data-ttu-id="872ba-939">Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-939">Electricity</span></span></td>
<td><span data-ttu-id="872ba-940">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-940">Variable cost</span></span></td>
<td><span data-ttu-id="872ba-941">470.08</span><span class="sxs-lookup"><span data-stu-id="872ba-941">470.08</span></span></td>
<td><span data-ttu-id="872ba-942">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="872ba-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="872ba-943">Conclusion</span><span class="sxs-lookup"><span data-stu-id="872ba-943">Conclusion</span></span>
<span data-ttu-id="872ba-944">Dans la comptabilité financière, un coût de 10 000,00 pour l'électricité est imputé sur un ID de centre de coût fictif.</span><span class="sxs-lookup"><span data-stu-id="872ba-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="872ba-945">Par conséquent, les comptables sauront que ce coût doit être affecté.</span><span class="sxs-lookup"><span data-stu-id="872ba-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="872ba-946">Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l'organisation, selon les stratégies et les règles qui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="872ba-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="872ba-947">Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="872ba-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="872ba-948">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="872ba-949">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="872ba-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="872ba-950">Total</span><span class="sxs-lookup"><span data-stu-id="872ba-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="872ba-951">CC099</span><span class="sxs-lookup"><span data-stu-id="872ba-951">CC099</span></span></th>
<th><span data-ttu-id="872ba-952">CC001</span><span class="sxs-lookup"><span data-stu-id="872ba-952">CC001</span></span></th>
<th><span data-ttu-id="872ba-953">CC002</span><span class="sxs-lookup"><span data-stu-id="872ba-953">CC002</span></span></th>
<th><span data-ttu-id="872ba-954">CC003</span><span class="sxs-lookup"><span data-stu-id="872ba-954">CC003</span></span></th>
<th><span data-ttu-id="872ba-955">CC004</span><span class="sxs-lookup"><span data-stu-id="872ba-955">CC004</span></span></th>
<th><span data-ttu-id="872ba-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="872ba-956">Proj 1</span></span></th>
<th><span data-ttu-id="872ba-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="872ba-957">Proj 2</span></span></th>
<th><span data-ttu-id="872ba-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="872ba-958">Prod 1</span></span></th>
<th><span data-ttu-id="872ba-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="872ba-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="872ba-960">10001 Électricité</span><span class="sxs-lookup"><span data-stu-id="872ba-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="872ba-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="872ba-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="872ba-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="872ba-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="872ba-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="872ba-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="872ba-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="872ba-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="872ba-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="872ba-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="872ba-970">Non classifié</span><span class="sxs-lookup"><span data-stu-id="872ba-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-971">0,00</span><span class="sxs-lookup"><span data-stu-id="872ba-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="872ba-972">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="872ba-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-973">0,00</span><span class="sxs-lookup"><span data-stu-id="872ba-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-974">0,00</span><span class="sxs-lookup"><span data-stu-id="872ba-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-975">0,00</span><span class="sxs-lookup"><span data-stu-id="872ba-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-976">0,00</span><span class="sxs-lookup"><span data-stu-id="872ba-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-977">0,00</span><span class="sxs-lookup"><span data-stu-id="872ba-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="872ba-978">776.36</span><span class="sxs-lookup"><span data-stu-id="872ba-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-979">223.64</span><span class="sxs-lookup"><span data-stu-id="872ba-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-980"><strong>1 000,00</strong></span><span class="sxs-lookup"><span data-stu-id="872ba-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="872ba-981">Coût variable</span><span class="sxs-lookup"><span data-stu-id="872ba-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-982">000</span><span class="sxs-lookup"><span data-stu-id="872ba-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-983">0,00</span><span class="sxs-lookup"><span data-stu-id="872ba-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-984">0,00</span><span class="sxs-lookup"><span data-stu-id="872ba-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-985">0,00</span><span class="sxs-lookup"><span data-stu-id="872ba-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-986">0,00</span><span class="sxs-lookup"><span data-stu-id="872ba-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-987">30,00</span><span class="sxs-lookup"><span data-stu-id="872ba-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-988">10,00</span><span class="sxs-lookup"><span data-stu-id="872ba-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="872ba-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="872ba-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="872ba-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="872ba-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="872ba-992">Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût.</span><span class="sxs-lookup"><span data-stu-id="872ba-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="872ba-993">Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l'organisation.</span><span class="sxs-lookup"><span data-stu-id="872ba-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="872ba-994">Autrement dit, les objets de coût de plus bas niveau supportent le coût.</span><span class="sxs-lookup"><span data-stu-id="872ba-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="872ba-995">Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts.</span><span class="sxs-lookup"><span data-stu-id="872ba-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="872ba-996">Pour plus d'informations, voir [Repositionnement des coûts](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="872ba-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



