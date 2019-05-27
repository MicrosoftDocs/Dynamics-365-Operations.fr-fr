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
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544053"
---
# <a name="overhead-calculation"></a><span data-ttu-id="2a980-103">Calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="2a980-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2a980-104">Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="2a980-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="2a980-105">Définition des termes</span><span class="sxs-lookup"><span data-stu-id="2a980-105">Term definition</span></span>
---------------

<span data-ttu-id="2a980-106">Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique.</span><span class="sxs-lookup"><span data-stu-id="2a980-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="2a980-107">Les frais généraux permettent essentiellement l'identification des activités rémunératrices.</span><span class="sxs-lookup"><span data-stu-id="2a980-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="2a980-108">Voici quelques exemples de frais généraux :</span><span class="sxs-lookup"><span data-stu-id="2a980-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="2a980-109">Loyer</span><span class="sxs-lookup"><span data-stu-id="2a980-109">Rent</span></span>
-   <span data-ttu-id="2a980-110">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-110">Electricity</span></span>
-   <span data-ttu-id="2a980-111">Salaires administratifs</span><span class="sxs-lookup"><span data-stu-id="2a980-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="2a980-112">Vue d'ensemble du calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="2a980-112">Overhead calculation overview</span></span>
<span data-ttu-id="2a980-113">Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l'ordre correct.</span><span class="sxs-lookup"><span data-stu-id="2a980-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="2a980-114">Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées.</span><span class="sxs-lookup"><span data-stu-id="2a980-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="2a980-115">Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions.</span><span class="sxs-lookup"><span data-stu-id="2a980-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="2a980-116">Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable.</span><span class="sxs-lookup"><span data-stu-id="2a980-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="2a980-117">Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="2a980-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="2a980-118">L'ID de version unique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2a980-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="2a980-119">Type de version</span><span class="sxs-lookup"><span data-stu-id="2a980-119">Version type</span></span>
-   <span data-ttu-id="2a980-120">Date et heure</span><span class="sxs-lookup"><span data-stu-id="2a980-120">Date and time</span></span>
-   <span data-ttu-id="2a980-121">Comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="2a980-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="2a980-122">Exercice</span><span class="sxs-lookup"><span data-stu-id="2a980-122">Fiscal year</span></span>
-   <span data-ttu-id="2a980-123">Période fiscale</span><span class="sxs-lookup"><span data-stu-id="2a980-123">Fiscal period</span></span>

<span data-ttu-id="2a980-124">Le calcul des frais généraux est effectué indépendamment de la version.</span><span class="sxs-lookup"><span data-stu-id="2a980-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="2a980-125">Par conséquent, vous pouvez calculer la version de budget avant la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="2a980-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="2a980-126">Le calcul des frais généraux comporte quatre étapes, comme le montre l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="2a980-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="2a980-127">Dans chaque étape, un en-tête de journal avec des entrées de journal est créé.</span><span class="sxs-lookup"><span data-stu-id="2a980-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="2a980-128">Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul.</span><span class="sxs-lookup"><span data-stu-id="2a980-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="2a980-129">Les stratégies et les règles s'appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie.</span><span class="sxs-lookup"><span data-stu-id="2a980-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="2a980-130">Par conséquent, vous disposez toujours d'une traçabilité complète.</span><span class="sxs-lookup"><span data-stu-id="2a980-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="2a980-131">[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="2a980-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="2a980-132">Calculer et affecter les frais généraux Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="2a980-133">Dans la comptabilité financière, certaines coûts, tels que l'électricité, sont enregistrés comme montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="2a980-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="2a980-134">Par conséquent, l'analyse détaillée n'est pas fournie pour le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="2a980-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="2a980-135">Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l'organisation, les coûts doivent suivre les unités organisationnelles.</span><span class="sxs-lookup"><span data-stu-id="2a980-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="2a980-136">Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste.</span><span class="sxs-lookup"><span data-stu-id="2a980-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="2a980-137">Dans la comptabilité, le coût de l'électricité peut être validé comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="2a980-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2a980-138">Date comptable</span><span class="sxs-lookup"><span data-stu-id="2a980-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-139">Centre de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-140">Compte principal</span><span class="sxs-lookup"><span data-stu-id="2a980-140">Main account</span></span></th>
<th><span data-ttu-id="2a980-141">Montant en devise comptable</span><span class="sxs-lookup"><span data-stu-id="2a980-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-142">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="2a980-143">CC099</span><span class="sxs-lookup"><span data-stu-id="2a980-143">CC099</span></span></td>
<td><span data-ttu-id="2a980-144">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="2a980-144">Default cost center</span></span></td>
<td><span data-ttu-id="2a980-145">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-145">10001</span></span></td>
<td><span data-ttu-id="2a980-146">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-146">Electricity</span></span></td>
<td><span data-ttu-id="2a980-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="2a980-148">Étape 1 : Traiter le calcul du comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="2a980-149">Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="2a980-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="2a980-150">Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.</span><span class="sxs-lookup"><span data-stu-id="2a980-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="2a980-151">Définir la règle de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-151">Define the cost behavior rule</span></span>

<span data-ttu-id="2a980-152">Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation.</span><span class="sxs-lookup"><span data-stu-id="2a980-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="2a980-153">Les factures d'électricité correspondent souvent à cette définition.</span><span class="sxs-lookup"><span data-stu-id="2a980-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="2a980-154">Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH).</span><span class="sxs-lookup"><span data-stu-id="2a980-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="2a980-155">Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :</span><span class="sxs-lookup"><span data-stu-id="2a980-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="2a980-156">Montant fixe 1 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="2a980-157">0 &lt;= 1 000,00 = Fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="2a980-158">1 000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="2a980-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="2a980-159">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="2a980-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2a980-160">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="2a980-160">Journal</span></span></th>
<th><span data-ttu-id="2a980-161">Type de journal</span><span class="sxs-lookup"><span data-stu-id="2a980-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2a980-162">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="2a980-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2a980-163">Version</span><span class="sxs-lookup"><span data-stu-id="2a980-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-164">00001</span><span class="sxs-lookup"><span data-stu-id="2a980-164">00001</span></span></td>
<td><span data-ttu-id="2a980-165">Journal de calcul de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="2a980-166">Exercice</span><span class="sxs-lookup"><span data-stu-id="2a980-166">Fiscal</span></span></td>
<td><span data-ttu-id="2a980-167">2017</span><span class="sxs-lookup"><span data-stu-id="2a980-167">2017</span></span></td>
<td><span data-ttu-id="2a980-168">Période 1</span><span class="sxs-lookup"><span data-stu-id="2a980-168">Period 1</span></span></td>
<td><span data-ttu-id="2a980-169">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="2a980-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="2a980-170">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="2a980-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2a980-171">Date comptable</span><span class="sxs-lookup"><span data-stu-id="2a980-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-172">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-173">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-173">Cost element</span></span></th>
<th><span data-ttu-id="2a980-174">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-174">Cost behavior</span></span></th>
<th><span data-ttu-id="2a980-175">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-176">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="2a980-177">CC099</span><span class="sxs-lookup"><span data-stu-id="2a980-177">CC099</span></span></td>
<td><span data-ttu-id="2a980-178">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="2a980-178">Default cost center</span></span></td>
<td><span data-ttu-id="2a980-179">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-179">10001</span></span></td>
<td><span data-ttu-id="2a980-180">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-180">Electricity</span></span></td>
<td><span data-ttu-id="2a980-181">Non classifié</span><span class="sxs-lookup"><span data-stu-id="2a980-181">Unclassified</span></span></td>
<td><span data-ttu-id="2a980-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2a980-183">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-184">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-185">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-185">Cost element</span></span></th>
<th><span data-ttu-id="2a980-186">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-186">Cost behavior</span></span></th>
<th><span data-ttu-id="2a980-187">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-187">Amount</span></span></th>
<th><span data-ttu-id="2a980-188">Date comptable</span><span class="sxs-lookup"><span data-stu-id="2a980-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-189">CC099</span><span class="sxs-lookup"><span data-stu-id="2a980-189">CC099</span></span></td>
<td><span data-ttu-id="2a980-190">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="2a980-190">Default cost center</span></span></td>
<td><span data-ttu-id="2a980-191">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-191">10001</span></span></td>
<td><span data-ttu-id="2a980-192">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-192">Electricity</span></span></td>
<td><span data-ttu-id="2a980-193">Non classifié</span><span class="sxs-lookup"><span data-stu-id="2a980-193">Unclassified</span></span></td>
<td><span data-ttu-id="2a980-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-194">10,000.00</span></span></td>
<td><span data-ttu-id="2a980-195">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-196">CC099</span><span class="sxs-lookup"><span data-stu-id="2a980-196">CC099</span></span></td>
<td><span data-ttu-id="2a980-197">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="2a980-197">Default cost center</span></span></td>
<td><span data-ttu-id="2a980-198">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-198">10001</span></span></td>
<td><span data-ttu-id="2a980-199">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-199">Electricity</span></span></td>
<td><span data-ttu-id="2a980-200">Non classifié</span><span class="sxs-lookup"><span data-stu-id="2a980-200">Unclassified</span></span></td>
<td><span data-ttu-id="2a980-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-201">-10,000.00</span></span></td>
<td><span data-ttu-id="2a980-202">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-203">CC099</span><span class="sxs-lookup"><span data-stu-id="2a980-203">CC099</span></span></td>
<td><span data-ttu-id="2a980-204">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="2a980-204">Default cost center</span></span></td>
<td><span data-ttu-id="2a980-205">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-205">10001</span></span></td>
<td><span data-ttu-id="2a980-206">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-206">Electricity</span></span></td>
<td><span data-ttu-id="2a980-207">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-207">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-208">1,000.00</span></span></td>
<td><span data-ttu-id="2a980-209">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-210">CC099</span><span class="sxs-lookup"><span data-stu-id="2a980-210">CC099</span></span></td>
<td><span data-ttu-id="2a980-211">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="2a980-211">Default cost center</span></span></td>
<td><span data-ttu-id="2a980-212">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-212">10001</span></span></td>
<td><span data-ttu-id="2a980-213">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-213">Electricity</span></span></td>
<td><span data-ttu-id="2a980-214">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-214">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-215">9 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-215">9,000.00</span></span></td>
<td><span data-ttu-id="2a980-216">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-217">Pour plus d'informations, voir [Créer et affecter une stratégie de comportement de coûts à une unité de contrôle des coûts](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="2a980-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="2a980-218">Étape 2 : Traiter le calcul de distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="2a980-219">La distribution des coûts est utilisée pour redistribuer le coût d'un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée.</span><span class="sxs-lookup"><span data-stu-id="2a980-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="2a980-220">La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l'élément de coût principal du coût d'origine.</span><span class="sxs-lookup"><span data-stu-id="2a980-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="2a980-221">Définir la règle de distribution de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-221">Define the cost distribution rule</span></span>

<span data-ttu-id="2a980-222">Dans la comptabilité financière, les coûts d'électricité sont souvent enregistrés comme un montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="2a980-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="2a980-223">Dans le Contrôle de gestion, cette approche n'est pas assez détaillée.</span><span class="sxs-lookup"><span data-stu-id="2a980-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="2a980-224">Le coût variable doit être attribué aux différents objets de coûts sur une base juste.</span><span class="sxs-lookup"><span data-stu-id="2a980-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="2a980-225">La base de répartition la plus logique est la consommation de l'électricité (KWH).</span><span class="sxs-lookup"><span data-stu-id="2a980-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="2a980-226">Un membre de dimension statistique nommé Électricité est créé, et la consommation d'électricité est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="2a980-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="2a980-227">Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="2a980-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-228">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-228">Cost object</span></span></th>
<th><span data-ttu-id="2a980-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="2a980-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-230">CC001</span><span class="sxs-lookup"><span data-stu-id="2a980-230">CC001</span></span></td>
<td><span data-ttu-id="2a980-231">RH</span><span class="sxs-lookup"><span data-stu-id="2a980-231">HR</span></span></td>
<td><span data-ttu-id="2a980-232">1 000</span><span class="sxs-lookup"><span data-stu-id="2a980-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-233">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-233">CC002</span></span></td>
<td><span data-ttu-id="2a980-234">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-234">Finance</span></span></td>
<td><span data-ttu-id="2a980-235">6 000</span><span class="sxs-lookup"><span data-stu-id="2a980-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-236">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-236">CC003</span></span></td>
<td><span data-ttu-id="2a980-237">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-237">Assembly</span></span></td>
<td><span data-ttu-id="2a980-238">0</span><span class="sxs-lookup"><span data-stu-id="2a980-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-239">Le tableau suivant illustre le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="2a980-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-240">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-240">Cost object</span></span></th>
<th><span data-ttu-id="2a980-241">Ampleur</span><span class="sxs-lookup"><span data-stu-id="2a980-241">Magnitude</span></span></th>
<th><span data-ttu-id="2a980-242">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="2a980-242">Allocation factor</span></span></th>
<th><span data-ttu-id="2a980-243">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-244">CC001</span><span class="sxs-lookup"><span data-stu-id="2a980-244">CC001</span></span></td>
<td><span data-ttu-id="2a980-245">RH</span><span class="sxs-lookup"><span data-stu-id="2a980-245">HR</span></span></td>
<td><span data-ttu-id="2a980-246">1 000</span><span class="sxs-lookup"><span data-stu-id="2a980-246">1,000</span></span></td>
<td><span data-ttu-id="2a980-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="2a980-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="2a980-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-249">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-249">CC002</span></span></td>
<td><span data-ttu-id="2a980-250">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-250">Finance</span></span></td>
<td><span data-ttu-id="2a980-251">6 000</span><span class="sxs-lookup"><span data-stu-id="2a980-251">6,000</span></span></td>
<td><span data-ttu-id="2a980-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="2a980-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="2a980-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-254">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-254">CC003</span></span></td>
<td><span data-ttu-id="2a980-255">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-255">Assembly</span></span></td>
<td><span data-ttu-id="2a980-256">0</span><span class="sxs-lookup"><span data-stu-id="2a980-256">0</span></span></td>
<td><span data-ttu-id="2a980-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="2a980-258">0,00</span><span class="sxs-lookup"><span data-stu-id="2a980-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-259">Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l'électricité.</span><span class="sxs-lookup"><span data-stu-id="2a980-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="2a980-260">Vous pouvez obtenir ce résultat à l'aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="2a980-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-261">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-261">Cost object</span></span></th>
<th><span data-ttu-id="2a980-262">Formule</span><span class="sxs-lookup"><span data-stu-id="2a980-262">Formula</span></span></th>
<th><span data-ttu-id="2a980-263">Ampleur</span><span class="sxs-lookup"><span data-stu-id="2a980-263">Magnitude</span></span></th>
<th><span data-ttu-id="2a980-264">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="2a980-264">Allocation factor</span></span></th>
<th><span data-ttu-id="2a980-265">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-266">CC001</span><span class="sxs-lookup"><span data-stu-id="2a980-266">CC001</span></span></td>
<td><span data-ttu-id="2a980-267">RH</span><span class="sxs-lookup"><span data-stu-id="2a980-267">HR</span></span></td>
<td><span data-ttu-id="2a980-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="2a980-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="2a980-269">1</span><span class="sxs-lookup"><span data-stu-id="2a980-269">1</span></span></td>
<td><span data-ttu-id="2a980-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="2a980-271">500,00</span><span class="sxs-lookup"><span data-stu-id="2a980-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-272">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-272">CC002</span></span></td>
<td><span data-ttu-id="2a980-273">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-273">Finance</span></span></td>
<td><span data-ttu-id="2a980-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="2a980-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="2a980-275">1</span><span class="sxs-lookup"><span data-stu-id="2a980-275">1</span></span></td>
<td><span data-ttu-id="2a980-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="2a980-277">500,00</span><span class="sxs-lookup"><span data-stu-id="2a980-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-278">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-278">CC003</span></span></td>
<td><span data-ttu-id="2a980-279">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-279">Assembly</span></span></td>
<td><span data-ttu-id="2a980-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="2a980-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="2a980-281">0</span><span class="sxs-lookup"><span data-stu-id="2a980-281">0</span></span></td>
<td><span data-ttu-id="2a980-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="2a980-283">0,00</span><span class="sxs-lookup"><span data-stu-id="2a980-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="2a980-284">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="2a980-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2a980-285">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="2a980-285">Journal</span></span></th>
<th><span data-ttu-id="2a980-286">Type de journal</span><span class="sxs-lookup"><span data-stu-id="2a980-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2a980-287">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="2a980-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2a980-288">Version</span><span class="sxs-lookup"><span data-stu-id="2a980-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-289">00002</span><span class="sxs-lookup"><span data-stu-id="2a980-289">00002</span></span></td>
<td><span data-ttu-id="2a980-290">Journal de calcul de la distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="2a980-291">Exercice</span><span class="sxs-lookup"><span data-stu-id="2a980-291">Fiscal</span></span></td>
<td><span data-ttu-id="2a980-292">2017</span><span class="sxs-lookup"><span data-stu-id="2a980-292">2017</span></span></td>
<td><span data-ttu-id="2a980-293">Période 1</span><span class="sxs-lookup"><span data-stu-id="2a980-293">Period 1</span></span></td>
<td><span data-ttu-id="2a980-294">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="2a980-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="2a980-295">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="2a980-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2a980-296">Date comptable</span><span class="sxs-lookup"><span data-stu-id="2a980-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-297">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-298">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-298">Cost element</span></span></th>
<th><span data-ttu-id="2a980-299">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-299">Cost behavior</span></span></th>
<th><span data-ttu-id="2a980-300">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-301">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-302">CC099</span><span class="sxs-lookup"><span data-stu-id="2a980-302">CC099</span></span></td>
<td><span data-ttu-id="2a980-303">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="2a980-303">Default cost center</span></span></td>
<td><span data-ttu-id="2a980-304">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-304">10001</span></span></td>
<td><span data-ttu-id="2a980-305">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-305">Electricity</span></span></td>
<td><span data-ttu-id="2a980-306">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-306">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-308">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-309">CC099</span><span class="sxs-lookup"><span data-stu-id="2a980-309">CC099</span></span></td>
<td><span data-ttu-id="2a980-310">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="2a980-310">Default cost center</span></span></td>
<td><span data-ttu-id="2a980-311">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-311">10001</span></span></td>
<td><span data-ttu-id="2a980-312">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-312">Electricity</span></span></td>
<td><span data-ttu-id="2a980-313">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-313">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-314">9 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2a980-315">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-316">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-317">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-317">Cost element</span></span></th>
<th><span data-ttu-id="2a980-318">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-318">Cost behavior</span></span></th>
<th><span data-ttu-id="2a980-319">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-319">Amount</span></span></th>
<th><span data-ttu-id="2a980-320">Date comptable</span><span class="sxs-lookup"><span data-stu-id="2a980-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-321">CC099</span><span class="sxs-lookup"><span data-stu-id="2a980-321">CC099</span></span></td>
<td><span data-ttu-id="2a980-322">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="2a980-322">Default cost center</span></span></td>
<td><span data-ttu-id="2a980-323">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-323">10001</span></span></td>
<td><span data-ttu-id="2a980-324">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-324">Electricity</span></span></td>
<td><span data-ttu-id="2a980-325">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-325">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-326">-1,000.00</span></span></td>
<td><span data-ttu-id="2a980-327">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-328">CC001</span><span class="sxs-lookup"><span data-stu-id="2a980-328">CC001</span></span></td>
<td><span data-ttu-id="2a980-329">RH</span><span class="sxs-lookup"><span data-stu-id="2a980-329">HR</span></span></td>
<td><span data-ttu-id="2a980-330">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-330">10001</span></span></td>
<td><span data-ttu-id="2a980-331">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-331">Electricity</span></span></td>
<td><span data-ttu-id="2a980-332">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-332">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-333">500,00</span><span class="sxs-lookup"><span data-stu-id="2a980-333">500.00</span></span></td>
<td><span data-ttu-id="2a980-334">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-335">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-335">CC002</span></span></td>
<td><span data-ttu-id="2a980-336">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-336">Finance</span></span></td>
<td><span data-ttu-id="2a980-337">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-337">10001</span></span></td>
<td><span data-ttu-id="2a980-338">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-338">Electricity</span></span></td>
<td><span data-ttu-id="2a980-339">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-339">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-340">500,00</span><span class="sxs-lookup"><span data-stu-id="2a980-340">500.00</span></span></td>
<td><span data-ttu-id="2a980-341">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-342">CC099</span><span class="sxs-lookup"><span data-stu-id="2a980-342">CC099</span></span></td>
<td><span data-ttu-id="2a980-343">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="2a980-343">Default cost center</span></span></td>
<td><span data-ttu-id="2a980-344">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-344">10001</span></span></td>
<td><span data-ttu-id="2a980-345">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-345">Electricity</span></span></td>
<td><span data-ttu-id="2a980-346">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-346">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="2a980-347">-9,000.00</span></span></td>
<td><span data-ttu-id="2a980-348">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-349">CC001</span><span class="sxs-lookup"><span data-stu-id="2a980-349">CC001</span></span></td>
<td><span data-ttu-id="2a980-350">RH</span><span class="sxs-lookup"><span data-stu-id="2a980-350">HR</span></span></td>
<td><span data-ttu-id="2a980-351">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-351">10001</span></span></td>
<td><span data-ttu-id="2a980-352">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-352">Electricity</span></span></td>
<td><span data-ttu-id="2a980-353">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-353">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="2a980-354">1,285.71</span></span></td>
<td><span data-ttu-id="2a980-355">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-356">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-356">CC002</span></span></td>
<td><span data-ttu-id="2a980-357">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-357">Finance</span></span></td>
<td><span data-ttu-id="2a980-358">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-358">10001</span></span></td>
<td><span data-ttu-id="2a980-359">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-359">Electricity</span></span></td>
<td><span data-ttu-id="2a980-360">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-360">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="2a980-361">7,714.29</span></span></td>
<td><span data-ttu-id="2a980-362">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-363">Pour plus d'informations, voir [Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="2a980-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="2a980-364">Étape 3 : Traitement du calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="2a980-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="2a980-365">Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût.</span><span class="sxs-lookup"><span data-stu-id="2a980-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="2a980-366">Les frais sont basés sur un taux de coût prédéterminé et l'ampleur de la base d'affectation de répartition.</span><span class="sxs-lookup"><span data-stu-id="2a980-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="2a980-367">Définition du taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="2a980-367">Define the overhead rate</span></span>

<span data-ttu-id="2a980-368">L'objet de coût CC001 HR contribue à un ensemble de projets internes.</span><span class="sxs-lookup"><span data-stu-id="2a980-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="2a980-369">Un membre de dimension statistique nommé Projets HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="2a980-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-370">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-370">Cost object</span></span></th>
<th><span data-ttu-id="2a980-371">Heures</span><span class="sxs-lookup"><span data-stu-id="2a980-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2a980-372">Proj 1</span></span></td>
<td><span data-ttu-id="2a980-373">Projet 1</span><span class="sxs-lookup"><span data-stu-id="2a980-373">Project 1</span></span></td>
<td><span data-ttu-id="2a980-374">3</span><span class="sxs-lookup"><span data-stu-id="2a980-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2a980-375">Proj 2</span></span></td>
<td><span data-ttu-id="2a980-376">Projet 2</span><span class="sxs-lookup"><span data-stu-id="2a980-376">Project 2</span></span></td>
<td><span data-ttu-id="2a980-377">1</span><span class="sxs-lookup"><span data-stu-id="2a980-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-378">Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.</span><span class="sxs-lookup"><span data-stu-id="2a980-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-379">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-379">Cost object</span></span></th>
<th><span data-ttu-id="2a980-380">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-380">Cost element</span></span></th>
<th><span data-ttu-id="2a980-381">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-381">Cost behavior</span></span></th>
<th><span data-ttu-id="2a980-382">Unités</span><span class="sxs-lookup"><span data-stu-id="2a980-382">Units</span></span></th>
<th><span data-ttu-id="2a980-383">Taux</span><span class="sxs-lookup"><span data-stu-id="2a980-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-384">CC001</span><span class="sxs-lookup"><span data-stu-id="2a980-384">CC001</span></span></td>
<td><span data-ttu-id="2a980-385">RH</span><span class="sxs-lookup"><span data-stu-id="2a980-385">HR</span></span></td>
<td><span data-ttu-id="2a980-386">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-386">10001</span></span></td>
<td><span data-ttu-id="2a980-387">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-387">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-388">1</span><span class="sxs-lookup"><span data-stu-id="2a980-388">1</span></span></td>
<td><span data-ttu-id="2a980-389">10</span><span class="sxs-lookup"><span data-stu-id="2a980-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-390">Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="2a980-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-391">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-391">Cost object</span></span></th>
<th><span data-ttu-id="2a980-392">Ampleur</span><span class="sxs-lookup"><span data-stu-id="2a980-392">Magnitude</span></span></th>
<th><span data-ttu-id="2a980-393">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-393">Cost element</span></span></th>
<th><span data-ttu-id="2a980-394">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="2a980-394">Allocation factor</span></span></th>
<th><span data-ttu-id="2a980-395">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2a980-396">Proj 1</span></span></td>
<td><span data-ttu-id="2a980-397">Projet 1</span><span class="sxs-lookup"><span data-stu-id="2a980-397">Project 1</span></span></td>
<td><span data-ttu-id="2a980-398">3</span><span class="sxs-lookup"><span data-stu-id="2a980-398">3</span></span></td>
<td><span data-ttu-id="2a980-399">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-399">10001</span></span></td>
<td><span data-ttu-id="2a980-400">(3 ÷ 1) × 10m00</span><span class="sxs-lookup"><span data-stu-id="2a980-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="2a980-401">30,00</span><span class="sxs-lookup"><span data-stu-id="2a980-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2a980-402">Proj 2</span></span></td>
<td><span data-ttu-id="2a980-403">Projet 2</span><span class="sxs-lookup"><span data-stu-id="2a980-403">Project 2</span></span></td>
<td><span data-ttu-id="2a980-404">1</span><span class="sxs-lookup"><span data-stu-id="2a980-404">1</span></span></td>
<td><span data-ttu-id="2a980-405">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-405">10001</span></span></td>
<td><span data-ttu-id="2a980-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="2a980-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="2a980-407">10,00</span><span class="sxs-lookup"><span data-stu-id="2a980-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="2a980-408">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="2a980-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2a980-409">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="2a980-409">Journal</span></span></th>
<th><span data-ttu-id="2a980-410">Type de journal</span><span class="sxs-lookup"><span data-stu-id="2a980-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2a980-411">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="2a980-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2a980-412">Version</span><span class="sxs-lookup"><span data-stu-id="2a980-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-413">00003</span><span class="sxs-lookup"><span data-stu-id="2a980-413">00003</span></span></td>
<td><span data-ttu-id="2a980-414">Journal de calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="2a980-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="2a980-415">Exercice</span><span class="sxs-lookup"><span data-stu-id="2a980-415">Fiscal</span></span></td>
<td><span data-ttu-id="2a980-416">2017</span><span class="sxs-lookup"><span data-stu-id="2a980-416">2017</span></span></td>
<td><span data-ttu-id="2a980-417">Période 1</span><span class="sxs-lookup"><span data-stu-id="2a980-417">Period 1</span></span></td>
<td><span data-ttu-id="2a980-418">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="2a980-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="2a980-419">Entrées du journal (pour le calcul du taux de frais généraux)</span><span class="sxs-lookup"><span data-stu-id="2a980-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2a980-420">Date comptable</span><span class="sxs-lookup"><span data-stu-id="2a980-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-421">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-421">Cost object</span></span></th>
<th><span data-ttu-id="2a980-422">Ampleur</span><span class="sxs-lookup"><span data-stu-id="2a980-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-423">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2a980-424">Proj 1</span></span></td>
<td><span data-ttu-id="2a980-425">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="2a980-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="2a980-426">3,00</span><span class="sxs-lookup"><span data-stu-id="2a980-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-427">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2a980-428">Proj 2</span></span></td>
<td><span data-ttu-id="2a980-429">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="2a980-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="2a980-430">1,00</span><span class="sxs-lookup"><span data-stu-id="2a980-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2a980-431">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-432">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-433">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-433">Cost element</span></span></th>
<th><span data-ttu-id="2a980-434">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-434">Cost behavior</span></span></th>
<th><span data-ttu-id="2a980-435">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-435">Amount</span></span></th>
<th><span data-ttu-id="2a980-436">Date comptable</span><span class="sxs-lookup"><span data-stu-id="2a980-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="2a980-437">CC0001</span></span></td>
<td><span data-ttu-id="2a980-438">RH</span><span class="sxs-lookup"><span data-stu-id="2a980-438">HR</span></span></td>
<td><span data-ttu-id="2a980-439">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-439">10001</span></span></td>
<td><span data-ttu-id="2a980-440">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-440">Electricity</span></span></td>
<td><span data-ttu-id="2a980-441">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-441">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="2a980-442">-30.00</span></span></td>
<td><span data-ttu-id="2a980-443">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2a980-444">Proj 1</span></span></td>
<td><span data-ttu-id="2a980-445">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="2a980-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="2a980-446">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-446">10001</span></span></td>
<td><span data-ttu-id="2a980-447">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-447">Electricity</span></span></td>
<td><span data-ttu-id="2a980-448">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-448">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-449">30,00</span><span class="sxs-lookup"><span data-stu-id="2a980-449">30.00</span></span></td>
<td><span data-ttu-id="2a980-450">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-451">CC001</span><span class="sxs-lookup"><span data-stu-id="2a980-451">CC001</span></span></td>
<td><span data-ttu-id="2a980-452">RH</span><span class="sxs-lookup"><span data-stu-id="2a980-452">HR</span></span></td>
<td><span data-ttu-id="2a980-453">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-453">10001</span></span></td>
<td><span data-ttu-id="2a980-454">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-454">Electricity</span></span></td>
<td><span data-ttu-id="2a980-455">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-455">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="2a980-456">-10.00</span></span></td>
<td><span data-ttu-id="2a980-457">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2a980-458">Proj 2</span></span></td>
<td><span data-ttu-id="2a980-459">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="2a980-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="2a980-460">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-460">10001</span></span></td>
<td><span data-ttu-id="2a980-461">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-461">Electricity</span></span></td>
<td><span data-ttu-id="2a980-462">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-462">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-463">10.00</span><span class="sxs-lookup"><span data-stu-id="2a980-463">10.00</span></span></td>
<td><span data-ttu-id="2a980-464">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-465">Pour plus d'informations, voir [Exécuter le calcul des frais généraux](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="2a980-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="2a980-466">Étape 4 : Traiter le calcul de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="2a980-467">La répartition est utilisée pour affecter le solde d'un objet de coût à d'autres objets de coût en appliquant une base de répartition.</span><span class="sxs-lookup"><span data-stu-id="2a980-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="2a980-468">Finance and Operations prend en charge la méthode de répartition réciproque.</span><span class="sxs-lookup"><span data-stu-id="2a980-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="2a980-469">Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés.</span><span class="sxs-lookup"><span data-stu-id="2a980-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="2a980-470">Le système détermine automatiquement l'ordre correct selon lequel exécuter les répartitions.</span><span class="sxs-lookup"><span data-stu-id="2a980-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="2a980-471">Le solde d'un objet de coût est réparti par une seule base de répartition.</span><span class="sxs-lookup"><span data-stu-id="2a980-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="2a980-472">Les répartitions entre plusieurs dimensions d'objets de coût et leurs membres respectifs sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="2a980-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="2a980-473">L'ordre de répartition est contrôlé par l'unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="2a980-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="2a980-474">[![Méthode réciproque](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="2a980-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="2a980-475">Définir la répartition de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-475">Define the cost allocation</span></span>

<span data-ttu-id="2a980-476">Voici un exemple simple expliquant comment suivre le flux du coût.</span><span class="sxs-lookup"><span data-stu-id="2a980-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="2a980-477">L'objet de coût CC001 HR contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="2a980-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="2a980-478">Un membre de dimension statistique nommé Services HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="2a980-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-479">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-479">Cost object</span></span></th>
<th><span data-ttu-id="2a980-480">Services HR</span><span class="sxs-lookup"><span data-stu-id="2a980-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-481">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-481">CC002</span></span></td>
<td><span data-ttu-id="2a980-482">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-482">Finance</span></span></td>
<td><span data-ttu-id="2a980-483">35</span><span class="sxs-lookup"><span data-stu-id="2a980-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-484">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-484">CC003</span></span></td>
<td><span data-ttu-id="2a980-485">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-485">Assembly</span></span></td>
<td><span data-ttu-id="2a980-486">55</span><span class="sxs-lookup"><span data-stu-id="2a980-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-487">CC004</span><span class="sxs-lookup"><span data-stu-id="2a980-487">CC004</span></span></td>
<td><span data-ttu-id="2a980-488">Emballage</span><span class="sxs-lookup"><span data-stu-id="2a980-488">Packaging</span></span></td>
<td><span data-ttu-id="2a980-489">10</span><span class="sxs-lookup"><span data-stu-id="2a980-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-490">L'objet de coût CC002 Finance contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="2a980-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="2a980-491">Un membre de dimension statistique nommé Services Finance est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="2a980-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-492">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-492">Cost object</span></span></th>
<th><span data-ttu-id="2a980-493">Services Finance</span><span class="sxs-lookup"><span data-stu-id="2a980-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-494">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-494">CC003</span></span></td>
<td><span data-ttu-id="2a980-495">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-495">Assembly</span></span></td>
<td><span data-ttu-id="2a980-496">65</span><span class="sxs-lookup"><span data-stu-id="2a980-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-497">CC004</span><span class="sxs-lookup"><span data-stu-id="2a980-497">CC004</span></span></td>
<td><span data-ttu-id="2a980-498">Emballage</span><span class="sxs-lookup"><span data-stu-id="2a980-498">Packaging</span></span></td>
<td><span data-ttu-id="2a980-499">35</span><span class="sxs-lookup"><span data-stu-id="2a980-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-500">L'objet de coût CC003 Assemblage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="2a980-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="2a980-501">Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="2a980-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-502">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-502">Cost object</span></span></th>
<th><span data-ttu-id="2a980-503">Services Assemblage (heures)</span><span class="sxs-lookup"><span data-stu-id="2a980-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-504">Prod 1</span></span></td>
<td><span data-ttu-id="2a980-505">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-505">Product 1</span></span></td>
<td><span data-ttu-id="2a980-506">60</span><span class="sxs-lookup"><span data-stu-id="2a980-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-507">Prod 2</span></span></td>
<td><span data-ttu-id="2a980-508">Produit 2</span><span class="sxs-lookup"><span data-stu-id="2a980-508">Product 2</span></span></td>
<td><span data-ttu-id="2a980-509">20</span><span class="sxs-lookup"><span data-stu-id="2a980-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-510">L'objet de coût CC004 Emballage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="2a980-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="2a980-511">Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="2a980-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-512">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-512">Cost object</span></span></th>
<th><span data-ttu-id="2a980-513">Services Emballage (heures)</span><span class="sxs-lookup"><span data-stu-id="2a980-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-514">Prod 1</span></span></td>
<td><span data-ttu-id="2a980-515">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-515">Product 1</span></span></td>
<td><span data-ttu-id="2a980-516">80</span><span class="sxs-lookup"><span data-stu-id="2a980-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-517">Prod 2</span></span></td>
<td><span data-ttu-id="2a980-518">Produit 2</span><span class="sxs-lookup"><span data-stu-id="2a980-518">Product 2</span></span></td>
<td><span data-ttu-id="2a980-519">15</span><span class="sxs-lookup"><span data-stu-id="2a980-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="2a980-520">Dans Finance and Operations, les mesures statistiques telles que les heures de production qu'un produit consomme peuvent être dérivées des données sources.</span><span class="sxs-lookup"><span data-stu-id="2a980-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="2a980-521">Pour plus d'informations, voir [Modèle de fournisseur de mesures statistiques](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="2a980-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="2a980-522">Le tableau suivant présente le résultat lorsque les services RH sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="2a980-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-523">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-523">Cost object</span></span></th>
<th><span data-ttu-id="2a980-524">Ampleur</span><span class="sxs-lookup"><span data-stu-id="2a980-524">Magnitude</span></span></th>
<th><span data-ttu-id="2a980-525">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="2a980-525">Allocation factor</span></span></th>
<th><span data-ttu-id="2a980-526">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-526">Amount</span></span></th>
<th><span data-ttu-id="2a980-527">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-528">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-528">CC002</span></span></td>
<td><span data-ttu-id="2a980-529">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-529">Finance</span></span></td>
<td><span data-ttu-id="2a980-530">35</span><span class="sxs-lookup"><span data-stu-id="2a980-530">35</span></span></td>
<td><span data-ttu-id="2a980-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="2a980-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="2a980-532">175.00</span><span class="sxs-lookup"><span data-stu-id="2a980-532">175.00</span></span></td>
<td><span data-ttu-id="2a980-533">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-534">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-534">CC003</span></span></td>
<td><span data-ttu-id="2a980-535">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-535">Assembly</span></span></td>
<td><span data-ttu-id="2a980-536">55</span><span class="sxs-lookup"><span data-stu-id="2a980-536">55</span></span></td>
<td><span data-ttu-id="2a980-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="2a980-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="2a980-538">275.00</span><span class="sxs-lookup"><span data-stu-id="2a980-538">275.00</span></span></td>
<td><span data-ttu-id="2a980-539">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-540">CC004</span><span class="sxs-lookup"><span data-stu-id="2a980-540">CC004</span></span></td>
<td><span data-ttu-id="2a980-541">Emballage</span><span class="sxs-lookup"><span data-stu-id="2a980-541">Packaging</span></span></td>
<td><span data-ttu-id="2a980-542">10</span><span class="sxs-lookup"><span data-stu-id="2a980-542">10</span></span></td>
<td><span data-ttu-id="2a980-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="2a980-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="2a980-544">50,00</span><span class="sxs-lookup"><span data-stu-id="2a980-544">50.00</span></span></td>
<td><span data-ttu-id="2a980-545">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-546">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-546">CC002</span></span></td>
<td><span data-ttu-id="2a980-547">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-547">Finance</span></span></td>
<td><span data-ttu-id="2a980-548">35</span><span class="sxs-lookup"><span data-stu-id="2a980-548">35</span></span></td>
<td><span data-ttu-id="2a980-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="2a980-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="2a980-550">436.00</span><span class="sxs-lookup"><span data-stu-id="2a980-550">436.00</span></span></td>
<td><span data-ttu-id="2a980-551">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-552">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-552">CC003</span></span></td>
<td><span data-ttu-id="2a980-553">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-553">Assembly</span></span></td>
<td><span data-ttu-id="2a980-554">55</span><span class="sxs-lookup"><span data-stu-id="2a980-554">55</span></span></td>
<td><span data-ttu-id="2a980-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="2a980-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="2a980-556">685.14</span><span class="sxs-lookup"><span data-stu-id="2a980-556">685.14</span></span></td>
<td><span data-ttu-id="2a980-557">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-558">CC004</span><span class="sxs-lookup"><span data-stu-id="2a980-558">CC004</span></span></td>
<td><span data-ttu-id="2a980-559">Emballage</span><span class="sxs-lookup"><span data-stu-id="2a980-559">Packaging</span></span></td>
<td><span data-ttu-id="2a980-560">10</span><span class="sxs-lookup"><span data-stu-id="2a980-560">10</span></span></td>
<td><span data-ttu-id="2a980-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="2a980-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="2a980-562">124.57</span><span class="sxs-lookup"><span data-stu-id="2a980-562">124.57</span></span></td>
<td><span data-ttu-id="2a980-563">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-564">Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="2a980-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-565">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-565">Cost object</span></span></th>
<th><span data-ttu-id="2a980-566">Ampleur</span><span class="sxs-lookup"><span data-stu-id="2a980-566">Magnitude</span></span></th>
<th><span data-ttu-id="2a980-567">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="2a980-567">Allocation factor</span></span></th>
<th><span data-ttu-id="2a980-568">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-568">Amount</span></span></th>
<th><span data-ttu-id="2a980-569">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-570">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-570">CC003</span></span></td>
<td><span data-ttu-id="2a980-571">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-571">Assembly</span></span></td>
<td><span data-ttu-id="2a980-572">65</span><span class="sxs-lookup"><span data-stu-id="2a980-572">65</span></span></td>
<td><span data-ttu-id="2a980-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="2a980-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="2a980-574">438.75</span><span class="sxs-lookup"><span data-stu-id="2a980-574">438.75</span></span></td>
<td><span data-ttu-id="2a980-575">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-576">CC004</span><span class="sxs-lookup"><span data-stu-id="2a980-576">CC004</span></span></td>
<td><span data-ttu-id="2a980-577">Emballage</span><span class="sxs-lookup"><span data-stu-id="2a980-577">Packaging</span></span></td>
<td><span data-ttu-id="2a980-578">35</span><span class="sxs-lookup"><span data-stu-id="2a980-578">35</span></span></td>
<td><span data-ttu-id="2a980-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="2a980-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="2a980-580">236.25</span><span class="sxs-lookup"><span data-stu-id="2a980-580">236.25</span></span></td>
<td><span data-ttu-id="2a980-581">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-582">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-582">CC003</span></span></td>
<td><span data-ttu-id="2a980-583">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-583">Assembly</span></span></td>
<td><span data-ttu-id="2a980-584">65</span><span class="sxs-lookup"><span data-stu-id="2a980-584">65</span></span></td>
<td><span data-ttu-id="2a980-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="2a980-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="2a980-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="2a980-586">5,297.69</span></span></td>
<td><span data-ttu-id="2a980-587">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-588">CC004</span><span class="sxs-lookup"><span data-stu-id="2a980-588">CC004</span></span></td>
<td><span data-ttu-id="2a980-589">Emballage</span><span class="sxs-lookup"><span data-stu-id="2a980-589">Packaging</span></span></td>
<td><span data-ttu-id="2a980-590">35</span><span class="sxs-lookup"><span data-stu-id="2a980-590">35</span></span></td>
<td><span data-ttu-id="2a980-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="2a980-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="2a980-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="2a980-592">2,852.60</span></span></td>
<td><span data-ttu-id="2a980-593">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-594">Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="2a980-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-595">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-595">Cost object</span></span></th>
<th><span data-ttu-id="2a980-596">Ampleur</span><span class="sxs-lookup"><span data-stu-id="2a980-596">Magnitude</span></span></th>
<th><span data-ttu-id="2a980-597">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="2a980-597">Allocation factor</span></span></th>
<th><span data-ttu-id="2a980-598">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-598">Amount</span></span></th>
<th><span data-ttu-id="2a980-599">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-600">Prod 1</span></span></td>
<td><span data-ttu-id="2a980-601">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-601">Product 1</span></span></td>
<td><span data-ttu-id="2a980-602">60</span><span class="sxs-lookup"><span data-stu-id="2a980-602">60</span></span></td>
<td><span data-ttu-id="2a980-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="2a980-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="2a980-604">535.31</span><span class="sxs-lookup"><span data-stu-id="2a980-604">535.31</span></span></td>
<td><span data-ttu-id="2a980-605">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-606">Prod 2</span></span></td>
<td><span data-ttu-id="2a980-607">Produit 2</span><span class="sxs-lookup"><span data-stu-id="2a980-607">Product 2</span></span></td>
<td><span data-ttu-id="2a980-608">20</span><span class="sxs-lookup"><span data-stu-id="2a980-608">20</span></span></td>
<td><span data-ttu-id="2a980-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="2a980-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="2a980-610">178.44</span><span class="sxs-lookup"><span data-stu-id="2a980-610">178.44</span></span></td>
<td><span data-ttu-id="2a980-611">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-612">Prod 1</span></span></td>
<td><span data-ttu-id="2a980-613">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-613">Product 1</span></span></td>
<td><span data-ttu-id="2a980-614">60</span><span class="sxs-lookup"><span data-stu-id="2a980-614">60</span></span></td>
<td><span data-ttu-id="2a980-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="2a980-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="2a980-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="2a980-616">4,487.12</span></span></td>
<td><span data-ttu-id="2a980-617">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-618">Prod 2</span></span></td>
<td><span data-ttu-id="2a980-619">Produit 2</span><span class="sxs-lookup"><span data-stu-id="2a980-619">Product 2</span></span></td>
<td><span data-ttu-id="2a980-620">20</span><span class="sxs-lookup"><span data-stu-id="2a980-620">20</span></span></td>
<td><span data-ttu-id="2a980-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="2a980-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="2a980-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="2a980-622">1,495.71</span></span></td>
<td><span data-ttu-id="2a980-623">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2a980-624">Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="2a980-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-625">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-625">Cost object</span></span></th>
<th><span data-ttu-id="2a980-626">Ampleur</span><span class="sxs-lookup"><span data-stu-id="2a980-626">Magnitude</span></span></th>
<th><span data-ttu-id="2a980-627">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="2a980-627">Allocation factor</span></span></th>
<th><span data-ttu-id="2a980-628">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-628">Amount</span></span></th>
<th><span data-ttu-id="2a980-629">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-630">Prod 1</span></span></td>
<td><span data-ttu-id="2a980-631">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-631">Product 1</span></span></td>
<td><span data-ttu-id="2a980-632">80</span><span class="sxs-lookup"><span data-stu-id="2a980-632">80</span></span></td>
<td><span data-ttu-id="2a980-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="2a980-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="2a980-634">241.05</span><span class="sxs-lookup"><span data-stu-id="2a980-634">241.05</span></span></td>
<td><span data-ttu-id="2a980-635">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-636">Prod 2</span></span></td>
<td><span data-ttu-id="2a980-637">Produit 2</span><span class="sxs-lookup"><span data-stu-id="2a980-637">Product 2</span></span></td>
<td><span data-ttu-id="2a980-638">15</span><span class="sxs-lookup"><span data-stu-id="2a980-638">15</span></span></td>
<td><span data-ttu-id="2a980-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="2a980-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="2a980-640">45.20</span><span class="sxs-lookup"><span data-stu-id="2a980-640">45.20</span></span></td>
<td><span data-ttu-id="2a980-641">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-642">Prod 1</span></span></td>
<td><span data-ttu-id="2a980-643">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-643">Product 1</span></span></td>
<td><span data-ttu-id="2a980-644">80</span><span class="sxs-lookup"><span data-stu-id="2a980-644">80</span></span></td>
<td><span data-ttu-id="2a980-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="2a980-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="2a980-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="2a980-646">2,507.09</span></span></td>
<td><span data-ttu-id="2a980-647">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-648">Prod 2</span></span></td>
<td><span data-ttu-id="2a980-649">Produit 2</span><span class="sxs-lookup"><span data-stu-id="2a980-649">Product 2</span></span></td>
<td><span data-ttu-id="2a980-650">15</span><span class="sxs-lookup"><span data-stu-id="2a980-650">15</span></span></td>
<td><span data-ttu-id="2a980-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="2a980-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="2a980-652">470.08</span><span class="sxs-lookup"><span data-stu-id="2a980-652">470.08</span></span></td>
<td><span data-ttu-id="2a980-653">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="2a980-654">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="2a980-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2a980-655">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="2a980-655">Journal</span></span></th>
<th><span data-ttu-id="2a980-656">Type de journal</span><span class="sxs-lookup"><span data-stu-id="2a980-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2a980-657">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="2a980-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2a980-658">Version</span><span class="sxs-lookup"><span data-stu-id="2a980-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-659">00004</span><span class="sxs-lookup"><span data-stu-id="2a980-659">00004</span></span></td>
<td><span data-ttu-id="2a980-660">Journal de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="2a980-661">Exercice</span><span class="sxs-lookup"><span data-stu-id="2a980-661">Fiscal</span></span></td>
<td><span data-ttu-id="2a980-662">2017</span><span class="sxs-lookup"><span data-stu-id="2a980-662">2017</span></span></td>
<td><span data-ttu-id="2a980-663">Période 1</span><span class="sxs-lookup"><span data-stu-id="2a980-663">Period 1</span></span></td>
<td><span data-ttu-id="2a980-664">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="2a980-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="2a980-665">Lignes de journal</span><span class="sxs-lookup"><span data-stu-id="2a980-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2a980-666">Date comptable</span><span class="sxs-lookup"><span data-stu-id="2a980-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-667">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-668">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-668">Cost element</span></span></th>
<th><span data-ttu-id="2a980-669">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-669">Cost behavior</span></span></th>
<th><span data-ttu-id="2a980-670">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-671">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-672">CC001</span><span class="sxs-lookup"><span data-stu-id="2a980-672">CC001</span></span></td>
<td><span data-ttu-id="2a980-673">RH</span><span class="sxs-lookup"><span data-stu-id="2a980-673">HR</span></span></td>
<td><span data-ttu-id="2a980-674">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-674">10001</span></span></td>
<td><span data-ttu-id="2a980-675">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-675">Electricity</span></span></td>
<td><span data-ttu-id="2a980-676">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-676">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-677">500,00</span><span class="sxs-lookup"><span data-stu-id="2a980-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-678">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-679">CC001</span><span class="sxs-lookup"><span data-stu-id="2a980-679">CC001</span></span></td>
<td><span data-ttu-id="2a980-680">RH</span><span class="sxs-lookup"><span data-stu-id="2a980-680">HR</span></span></td>
<td><span data-ttu-id="2a980-681">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-681">10001</span></span></td>
<td><span data-ttu-id="2a980-682">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-682">Electricity</span></span></td>
<td><span data-ttu-id="2a980-683">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-683">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="2a980-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-685">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-686">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-686">CC002</span></span></td>
<td><span data-ttu-id="2a980-687">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-687">Finance</span></span></td>
<td><span data-ttu-id="2a980-688">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-688">10001</span></span></td>
<td><span data-ttu-id="2a980-689">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-689">Electricity</span></span></td>
<td><span data-ttu-id="2a980-690">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-690">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-691">675.00</span><span class="sxs-lookup"><span data-stu-id="2a980-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-692">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-693">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-693">CC002</span></span></td>
<td><span data-ttu-id="2a980-694">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-694">Finance</span></span></td>
<td><span data-ttu-id="2a980-695">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-695">10001</span></span></td>
<td><span data-ttu-id="2a980-696">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-696">Electricity</span></span></td>
<td><span data-ttu-id="2a980-697">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-697">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="2a980-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-699">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-700">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-700">CC003</span></span></td>
<td><span data-ttu-id="2a980-701">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-701">Assembly</span></span></td>
<td><span data-ttu-id="2a980-702">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-702">10001</span></span></td>
<td><span data-ttu-id="2a980-703">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-703">Electricity</span></span></td>
<td><span data-ttu-id="2a980-704">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-704">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-705">713.75</span><span class="sxs-lookup"><span data-stu-id="2a980-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-706">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-707">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-707">CC003</span></span></td>
<td><span data-ttu-id="2a980-708">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-708">Assembly</span></span></td>
<td><span data-ttu-id="2a980-709">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-709">10001</span></span></td>
<td><span data-ttu-id="2a980-710">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-710">Electricity</span></span></td>
<td><span data-ttu-id="2a980-711">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-711">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="2a980-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-713">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-714">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-714">CC003</span></span></td>
<td><span data-ttu-id="2a980-715">Emballage</span><span class="sxs-lookup"><span data-stu-id="2a980-715">Packaging</span></span></td>
<td><span data-ttu-id="2a980-716">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-716">10001</span></span></td>
<td><span data-ttu-id="2a980-717">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-717">Electricity</span></span></td>
<td><span data-ttu-id="2a980-718">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-718">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-719">286.25</span><span class="sxs-lookup"><span data-stu-id="2a980-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-720">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-721">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-721">CC003</span></span></td>
<td><span data-ttu-id="2a980-722">Emballage</span><span class="sxs-lookup"><span data-stu-id="2a980-722">Packaging</span></span></td>
<td><span data-ttu-id="2a980-723">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-723">10001</span></span></td>
<td><span data-ttu-id="2a980-724">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-724">Electricity</span></span></td>
<td><span data-ttu-id="2a980-725">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-725">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="2a980-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-727">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-728">Prod 1</span></span></td>
<td><span data-ttu-id="2a980-729">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-729">Product 1</span></span></td>
<td><span data-ttu-id="2a980-730">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-730">10001</span></span></td>
<td><span data-ttu-id="2a980-731">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-731">Electricity</span></span></td>
<td><span data-ttu-id="2a980-732">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-732">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-733">776.36</span><span class="sxs-lookup"><span data-stu-id="2a980-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-734">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-735">Prod 1</span></span></td>
<td><span data-ttu-id="2a980-736">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-736">Product 1</span></span></td>
<td><span data-ttu-id="2a980-737">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-737">10001</span></span></td>
<td><span data-ttu-id="2a980-738">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-738">Electricity</span></span></td>
<td><span data-ttu-id="2a980-739">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-739">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="2a980-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-741">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-742">Prod 2</span></span></td>
<td><span data-ttu-id="2a980-743">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-743">Product 1</span></span></td>
<td><span data-ttu-id="2a980-744">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-744">10001</span></span></td>
<td><span data-ttu-id="2a980-745">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-745">Electricity</span></span></td>
<td><span data-ttu-id="2a980-746">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-746">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-747">223.64</span><span class="sxs-lookup"><span data-stu-id="2a980-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-748">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="2a980-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-749">Prod 2</span></span></td>
<td><span data-ttu-id="2a980-750">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-750">Product 1</span></span></td>
<td><span data-ttu-id="2a980-751">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-751">10001</span></span></td>
<td><span data-ttu-id="2a980-752">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-752">Electricity</span></span></td>
<td><span data-ttu-id="2a980-753">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-753">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="2a980-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2a980-755">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2a980-756">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2a980-757">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-757">Cost element</span></span></th>
<th><span data-ttu-id="2a980-758">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="2a980-758">Cost behavior</span></span></th>
<th><span data-ttu-id="2a980-759">Montant</span><span class="sxs-lookup"><span data-stu-id="2a980-759">Amount</span></span></th>
<th><span data-ttu-id="2a980-760">Date comptable</span><span class="sxs-lookup"><span data-stu-id="2a980-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2a980-761">CC001</span><span class="sxs-lookup"><span data-stu-id="2a980-761">CC001</span></span></td>
<td><span data-ttu-id="2a980-762">RH</span><span class="sxs-lookup"><span data-stu-id="2a980-762">HR</span></span></td>
<td><span data-ttu-id="2a980-763">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-763">10001</span></span></td>
<td><span data-ttu-id="2a980-764">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-764">Electricity</span></span></td>
<td><span data-ttu-id="2a980-765">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-765">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="2a980-766">-500.00</span></span></td>
<td><span data-ttu-id="2a980-767">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-768">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-768">CC002</span></span></td>
<td><span data-ttu-id="2a980-769">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-769">Finance</span></span></td>
<td><span data-ttu-id="2a980-770">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-770">10001</span></span></td>
<td><span data-ttu-id="2a980-771">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-771">Electricity</span></span></td>
<td><span data-ttu-id="2a980-772">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-772">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-773">175.00</span><span class="sxs-lookup"><span data-stu-id="2a980-773">175.00</span></span></td>
<td><span data-ttu-id="2a980-774">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-775">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-775">CC003</span></span></td>
<td><span data-ttu-id="2a980-776">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-776">Assembly</span></span></td>
<td><span data-ttu-id="2a980-777">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-777">10001</span></span></td>
<td><span data-ttu-id="2a980-778">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-778">Electricity</span></span></td>
<td><span data-ttu-id="2a980-779">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-779">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-780">275.00</span><span class="sxs-lookup"><span data-stu-id="2a980-780">275.00</span></span></td>
<td><span data-ttu-id="2a980-781">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-782">CC004</span><span class="sxs-lookup"><span data-stu-id="2a980-782">CC004</span></span></td>
<td><span data-ttu-id="2a980-783">Emballage</span><span class="sxs-lookup"><span data-stu-id="2a980-783">Packaging</span></span></td>
<td><span data-ttu-id="2a980-784">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-784">10001</span></span></td>
<td><span data-ttu-id="2a980-785">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-785">Electricity</span></span></td>
<td><span data-ttu-id="2a980-786">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-786">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-787">50,00</span><span class="sxs-lookup"><span data-stu-id="2a980-787">50,00</span></span></td>
<td><span data-ttu-id="2a980-788">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-789">CC001</span><span class="sxs-lookup"><span data-stu-id="2a980-789">CC001</span></span></td>
<td><span data-ttu-id="2a980-790">RH</span><span class="sxs-lookup"><span data-stu-id="2a980-790">HR</span></span></td>
<td><span data-ttu-id="2a980-791">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-791">10001</span></span></td>
<td><span data-ttu-id="2a980-792">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-792">Electricity</span></span></td>
<td><span data-ttu-id="2a980-793">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-793">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="2a980-794">-1,245.71</span></span></td>
<td><span data-ttu-id="2a980-795">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-796">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-796">CC002</span></span></td>
<td><span data-ttu-id="2a980-797">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-797">Finance</span></span></td>
<td><span data-ttu-id="2a980-798">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-798">10001</span></span></td>
<td><span data-ttu-id="2a980-799">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-799">Electricity</span></span></td>
<td><span data-ttu-id="2a980-800">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-800">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-801">436.00</span><span class="sxs-lookup"><span data-stu-id="2a980-801">436.00</span></span></td>
<td><span data-ttu-id="2a980-802">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-803">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-803">CC003</span></span></td>
<td><span data-ttu-id="2a980-804">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-804">Assembly</span></span></td>
<td><span data-ttu-id="2a980-805">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-805">10001</span></span></td>
<td><span data-ttu-id="2a980-806">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-806">Electricity</span></span></td>
<td><span data-ttu-id="2a980-807">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-807">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-808">685.14</span><span class="sxs-lookup"><span data-stu-id="2a980-808">685.14</span></span></td>
<td><span data-ttu-id="2a980-809">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-810">CC004</span><span class="sxs-lookup"><span data-stu-id="2a980-810">CC004</span></span></td>
<td><span data-ttu-id="2a980-811">Emballage</span><span class="sxs-lookup"><span data-stu-id="2a980-811">Packaging</span></span></td>
<td><span data-ttu-id="2a980-812">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-812">10001</span></span></td>
<td><span data-ttu-id="2a980-813">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-813">Electricity</span></span></td>
<td><span data-ttu-id="2a980-814">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-814">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-815">124.57</span><span class="sxs-lookup"><span data-stu-id="2a980-815">124.57</span></span></td>
<td><span data-ttu-id="2a980-816">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-817">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-817">CC002</span></span></td>
<td><span data-ttu-id="2a980-818">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-818">Finance</span></span></td>
<td><span data-ttu-id="2a980-819">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-819">10001</span></span></td>
<td><span data-ttu-id="2a980-820">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-820">Electricity</span></span></td>
<td><span data-ttu-id="2a980-821">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-821">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="2a980-822">-675.00</span></span></td>
<td><span data-ttu-id="2a980-823">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-824">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-824">CC003</span></span></td>
<td><span data-ttu-id="2a980-825">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-825">Assembly</span></span></td>
<td><span data-ttu-id="2a980-826">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-826">10001</span></span></td>
<td><span data-ttu-id="2a980-827">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-827">Electricity</span></span></td>
<td><span data-ttu-id="2a980-828">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-828">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-829">438.75</span><span class="sxs-lookup"><span data-stu-id="2a980-829">438.75</span></span></td>
<td><span data-ttu-id="2a980-830">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-831">CC004</span><span class="sxs-lookup"><span data-stu-id="2a980-831">CC004</span></span></td>
<td><span data-ttu-id="2a980-832">Emballage</span><span class="sxs-lookup"><span data-stu-id="2a980-832">Packaging</span></span></td>
<td><span data-ttu-id="2a980-833">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-833">10001</span></span></td>
<td><span data-ttu-id="2a980-834">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-834">Electricity</span></span></td>
<td><span data-ttu-id="2a980-835">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-835">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-836">236.25</span><span class="sxs-lookup"><span data-stu-id="2a980-836">236.25</span></span></td>
<td><span data-ttu-id="2a980-837">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-838">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-838">CC002</span></span></td>
<td><span data-ttu-id="2a980-839">Finances</span><span class="sxs-lookup"><span data-stu-id="2a980-839">Finance</span></span></td>
<td><span data-ttu-id="2a980-840">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-840">10001</span></span></td>
<td><span data-ttu-id="2a980-841">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-841">Electricity</span></span></td>
<td><span data-ttu-id="2a980-842">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-842">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="2a980-843">-8,150.29</span></span></td>
<td><span data-ttu-id="2a980-844">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-845">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-845">CC003</span></span></td>
<td><span data-ttu-id="2a980-846">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-846">Assembly</span></span></td>
<td><span data-ttu-id="2a980-847">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-847">10001</span></span></td>
<td><span data-ttu-id="2a980-848">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-848">Electricity</span></span></td>
<td><span data-ttu-id="2a980-849">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-849">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="2a980-850">5,297.69</span></span></td>
<td><span data-ttu-id="2a980-851">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-852">CC004</span><span class="sxs-lookup"><span data-stu-id="2a980-852">CC004</span></span></td>
<td><span data-ttu-id="2a980-853">Emballage</span><span class="sxs-lookup"><span data-stu-id="2a980-853">Packaging</span></span></td>
<td><span data-ttu-id="2a980-854">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-854">10001</span></span></td>
<td><span data-ttu-id="2a980-855">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-855">Electricity</span></span></td>
<td><span data-ttu-id="2a980-856">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-856">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="2a980-857">2,852.60</span></span></td>
<td><span data-ttu-id="2a980-858">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-859">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-859">CC003</span></span></td>
<td><span data-ttu-id="2a980-860">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-860">Assembly</span></span></td>
<td><span data-ttu-id="2a980-861">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-861">10001</span></span></td>
<td><span data-ttu-id="2a980-862">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-862">Electricity</span></span></td>
<td><span data-ttu-id="2a980-863">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-863">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="2a980-864">-713.75</span></span></td>
<td><span data-ttu-id="2a980-865">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-866">Prod 1</span></span></td>
<td><span data-ttu-id="2a980-867">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-867">Product 1</span></span></td>
<td><span data-ttu-id="2a980-868">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-868">10001</span></span></td>
<td><span data-ttu-id="2a980-869">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-869">Electricity</span></span></td>
<td><span data-ttu-id="2a980-870">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-870">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-871">535.31</span><span class="sxs-lookup"><span data-stu-id="2a980-871">535.31</span></span></td>
<td><span data-ttu-id="2a980-872">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-873">Prod 2</span></span></td>
<td><span data-ttu-id="2a980-874">Produit 2</span><span class="sxs-lookup"><span data-stu-id="2a980-874">Product 2</span></span></td>
<td><span data-ttu-id="2a980-875">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-875">10001</span></span></td>
<td><span data-ttu-id="2a980-876">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-876">Electricity</span></span></td>
<td><span data-ttu-id="2a980-877">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-877">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-878">178.44</span><span class="sxs-lookup"><span data-stu-id="2a980-878">178.44</span></span></td>
<td><span data-ttu-id="2a980-879">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-880">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-880">CC003</span></span></td>
<td><span data-ttu-id="2a980-881">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-881">Assembly</span></span></td>
<td><span data-ttu-id="2a980-882">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-882">10001</span></span></td>
<td><span data-ttu-id="2a980-883">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-883">Electricity</span></span></td>
<td><span data-ttu-id="2a980-884">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-884">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="2a980-885">-5,982.83</span></span></td>
<td><span data-ttu-id="2a980-886">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-887">Prod 1</span></span></td>
<td><span data-ttu-id="2a980-888">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-888">Product 1</span></span></td>
<td><span data-ttu-id="2a980-889">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-889">10001</span></span></td>
<td><span data-ttu-id="2a980-890">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-890">Electricity</span></span></td>
<td><span data-ttu-id="2a980-891">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-891">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="2a980-892">4,487.12</span></span></td>
<td><span data-ttu-id="2a980-893">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-894">Prod 2</span></span></td>
<td><span data-ttu-id="2a980-895">Produit 2</span><span class="sxs-lookup"><span data-stu-id="2a980-895">Product 2</span></span></td>
<td><span data-ttu-id="2a980-896">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-896">10001</span></span></td>
<td><span data-ttu-id="2a980-897">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-897">Electricity</span></span></td>
<td><span data-ttu-id="2a980-898">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-898">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="2a980-899">1,495.71</span></span></td>
<td><span data-ttu-id="2a980-900">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-901">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-901">CC003</span></span></td>
<td><span data-ttu-id="2a980-902">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-902">Assembly</span></span></td>
<td><span data-ttu-id="2a980-903">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-903">10001</span></span></td>
<td><span data-ttu-id="2a980-904">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-904">Electricity</span></span></td>
<td><span data-ttu-id="2a980-905">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-905">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="2a980-906">-286.25</span></span></td>
<td><span data-ttu-id="2a980-907">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-908">Prod 1</span></span></td>
<td><span data-ttu-id="2a980-909">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-909">Product 1</span></span></td>
<td><span data-ttu-id="2a980-910">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-910">10001</span></span></td>
<td><span data-ttu-id="2a980-911">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-911">Electricity</span></span></td>
<td><span data-ttu-id="2a980-912">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-912">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-913">241.05</span><span class="sxs-lookup"><span data-stu-id="2a980-913">241.05</span></span></td>
<td><span data-ttu-id="2a980-914">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-915">Prod 2</span></span></td>
<td><span data-ttu-id="2a980-916">Produit 2</span><span class="sxs-lookup"><span data-stu-id="2a980-916">Product 2</span></span></td>
<td><span data-ttu-id="2a980-917">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-917">10001</span></span></td>
<td><span data-ttu-id="2a980-918">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-918">Electricity</span></span></td>
<td><span data-ttu-id="2a980-919">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-919">Fixed cost</span></span></td>
<td><span data-ttu-id="2a980-920">45.20</span><span class="sxs-lookup"><span data-stu-id="2a980-920">45.20</span></span></td>
<td><span data-ttu-id="2a980-921">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-922">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-922">CC003</span></span></td>
<td><span data-ttu-id="2a980-923">Assemblage</span><span class="sxs-lookup"><span data-stu-id="2a980-923">Assembly</span></span></td>
<td><span data-ttu-id="2a980-924">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-924">10001</span></span></td>
<td><span data-ttu-id="2a980-925">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-925">Electricity</span></span></td>
<td><span data-ttu-id="2a980-926">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-926">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="2a980-927">-2,977.17</span></span></td>
<td><span data-ttu-id="2a980-928">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-929">Prod 1</span></span></td>
<td><span data-ttu-id="2a980-930">Produit 1</span><span class="sxs-lookup"><span data-stu-id="2a980-930">Product 1</span></span></td>
<td><span data-ttu-id="2a980-931">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-931">10001</span></span></td>
<td><span data-ttu-id="2a980-932">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-932">Electricity</span></span></td>
<td><span data-ttu-id="2a980-933">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-933">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="2a980-934">2,507.09</span></span></td>
<td><span data-ttu-id="2a980-935">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2a980-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-936">Prod 2</span></span></td>
<td><span data-ttu-id="2a980-937">Produit 2</span><span class="sxs-lookup"><span data-stu-id="2a980-937">Product 2</span></span></td>
<td><span data-ttu-id="2a980-938">10001</span><span class="sxs-lookup"><span data-stu-id="2a980-938">10001</span></span></td>
<td><span data-ttu-id="2a980-939">Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-939">Electricity</span></span></td>
<td><span data-ttu-id="2a980-940">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-940">Variable cost</span></span></td>
<td><span data-ttu-id="2a980-941">470.08</span><span class="sxs-lookup"><span data-stu-id="2a980-941">470.08</span></span></td>
<td><span data-ttu-id="2a980-942">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="2a980-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="2a980-943">Conclusion</span><span class="sxs-lookup"><span data-stu-id="2a980-943">Conclusion</span></span>
<span data-ttu-id="2a980-944">Dans la comptabilité financière, un coût de 10 000,00 pour l'électricité est imputé sur un ID de centre de coût fictif.</span><span class="sxs-lookup"><span data-stu-id="2a980-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="2a980-945">Par conséquent, les comptables sauront que ce coût doit être affecté.</span><span class="sxs-lookup"><span data-stu-id="2a980-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="2a980-946">Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l'organisation, selon les stratégies et les règles qui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="2a980-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="2a980-947">Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="2a980-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="2a980-948">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="2a980-949">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="2a980-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="2a980-950">Total</span><span class="sxs-lookup"><span data-stu-id="2a980-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="2a980-951">CC099</span><span class="sxs-lookup"><span data-stu-id="2a980-951">CC099</span></span></th>
<th><span data-ttu-id="2a980-952">CC001</span><span class="sxs-lookup"><span data-stu-id="2a980-952">CC001</span></span></th>
<th><span data-ttu-id="2a980-953">CC002</span><span class="sxs-lookup"><span data-stu-id="2a980-953">CC002</span></span></th>
<th><span data-ttu-id="2a980-954">CC003</span><span class="sxs-lookup"><span data-stu-id="2a980-954">CC003</span></span></th>
<th><span data-ttu-id="2a980-955">CC004</span><span class="sxs-lookup"><span data-stu-id="2a980-955">CC004</span></span></th>
<th><span data-ttu-id="2a980-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2a980-956">Proj 1</span></span></th>
<th><span data-ttu-id="2a980-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2a980-957">Proj 2</span></span></th>
<th><span data-ttu-id="2a980-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2a980-958">Prod 1</span></span></th>
<th><span data-ttu-id="2a980-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2a980-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="2a980-960">10001 Électricité</span><span class="sxs-lookup"><span data-stu-id="2a980-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="2a980-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="2a980-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="2a980-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="2a980-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="2a980-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="2a980-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="2a980-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="2a980-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="2a980-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="2a980-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="2a980-970">Non classifié</span><span class="sxs-lookup"><span data-stu-id="2a980-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-971">0,00</span><span class="sxs-lookup"><span data-stu-id="2a980-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="2a980-972">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="2a980-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-973">0,00</span><span class="sxs-lookup"><span data-stu-id="2a980-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-974">0,00</span><span class="sxs-lookup"><span data-stu-id="2a980-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-975">0,00</span><span class="sxs-lookup"><span data-stu-id="2a980-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-976">0,00</span><span class="sxs-lookup"><span data-stu-id="2a980-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-977">0,00</span><span class="sxs-lookup"><span data-stu-id="2a980-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="2a980-978">776.36</span><span class="sxs-lookup"><span data-stu-id="2a980-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-979">223.64</span><span class="sxs-lookup"><span data-stu-id="2a980-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-980"><strong>1 000,00</strong></span><span class="sxs-lookup"><span data-stu-id="2a980-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="2a980-981">Coût variable</span><span class="sxs-lookup"><span data-stu-id="2a980-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-982">000</span><span class="sxs-lookup"><span data-stu-id="2a980-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-983">0,00</span><span class="sxs-lookup"><span data-stu-id="2a980-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-984">0,00</span><span class="sxs-lookup"><span data-stu-id="2a980-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-985">0,00</span><span class="sxs-lookup"><span data-stu-id="2a980-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-986">0,00</span><span class="sxs-lookup"><span data-stu-id="2a980-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-987">30,00</span><span class="sxs-lookup"><span data-stu-id="2a980-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-988">10,00</span><span class="sxs-lookup"><span data-stu-id="2a980-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="2a980-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="2a980-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2a980-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="2a980-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="2a980-992">Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût.</span><span class="sxs-lookup"><span data-stu-id="2a980-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="2a980-993">Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l'organisation.</span><span class="sxs-lookup"><span data-stu-id="2a980-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="2a980-994">Autrement dit, les objets de coût de plus bas niveau supportent le coût.</span><span class="sxs-lookup"><span data-stu-id="2a980-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="2a980-995">Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts.</span><span class="sxs-lookup"><span data-stu-id="2a980-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="2a980-996">Pour plus d'informations, voir [Repositionnement des coûts](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="2a980-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



