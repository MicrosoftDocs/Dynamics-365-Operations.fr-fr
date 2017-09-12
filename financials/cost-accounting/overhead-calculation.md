---
title: "Calcul des frais généraux"
description: "Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux."
author: YuyuScheller
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 1eb5560ba795ab6df61b5af889049810dd00d79e
ms.contentlocale: fr-fr
ms.lasthandoff: 06/29/2017


---

# <a name="overhead-calculation"></a><span data-ttu-id="fa3a5-103">Calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="fa3a5-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="fa3a5-104">Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="fa3a5-105">Définition des termes</span><span class="sxs-lookup"><span data-stu-id="fa3a5-105">Term definition</span></span>
---------------

<span data-ttu-id="fa3a5-106">Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="fa3a5-107">Les frais généraux permettent essentiellement l'identification des activités rémunératrices.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="fa3a5-108">Voici quelques exemples de frais généraux :</span><span class="sxs-lookup"><span data-stu-id="fa3a5-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="fa3a5-109">Loyer</span><span class="sxs-lookup"><span data-stu-id="fa3a5-109">Rent</span></span>
-   <span data-ttu-id="fa3a5-110">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-110">Electricity</span></span>
-   <span data-ttu-id="fa3a5-111">Salaires administratifs</span><span class="sxs-lookup"><span data-stu-id="fa3a5-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="fa3a5-112">Vue d'ensemble du calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="fa3a5-112">Overhead calculation overview</span></span>
<span data-ttu-id="fa3a5-113">Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l'ordre correct.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="fa3a5-114">Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="fa3a5-115">Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="fa3a5-116">Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="fa3a5-117">Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="fa3a5-118">L'ID de version unique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="fa3a5-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="fa3a5-119">Type de version</span><span class="sxs-lookup"><span data-stu-id="fa3a5-119">Version type</span></span>
-   <span data-ttu-id="fa3a5-120">Date et heure</span><span class="sxs-lookup"><span data-stu-id="fa3a5-120">Date and time</span></span>
-   <span data-ttu-id="fa3a5-121">Comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="fa3a5-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="fa3a5-122">Exercice</span><span class="sxs-lookup"><span data-stu-id="fa3a5-122">Fiscal year</span></span>
-   <span data-ttu-id="fa3a5-123">Période fiscale</span><span class="sxs-lookup"><span data-stu-id="fa3a5-123">Fiscal period</span></span>

<span data-ttu-id="fa3a5-124">Le calcul des frais généraux est effectué indépendamment de la version.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="fa3a5-125">Par conséquent, vous pouvez calculer la version de budget avant la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="fa3a5-126">Le calcul des frais généraux comporte quatre étapes, comme le montre l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="fa3a5-127">Dans chaque étape, un en-tête de journal avec des entrées de journal est créé.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="fa3a5-128">Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="fa3a5-129">Les stratégies et les règles s'appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="fa3a5-130">Par conséquent, vous disposez toujours d'une traçabilité complète.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-130">Therefore, you always have full traceability.</span></span> 
<span data-ttu-id="fa3a5-131">[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="fa3a5-132">Calculer et affecter les frais généraux Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="fa3a5-133">Dans la comptabilité financière, certaines coûts, tels que l'électricité, sont enregistrés comme montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="fa3a5-134">Par conséquent, l'analyse détaillée n'est pas fournie pour le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="fa3a5-135">Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l'organisation, les coûts doivent suivre les unités organisationnelles.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="fa3a5-136">Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="fa3a5-137">Dans la comptabilité, le coût de l'électricité peut être validé comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fa3a5-138">Date comptable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-139">Centre de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-140">Compte principal</span><span class="sxs-lookup"><span data-stu-id="fa3a5-140">Main account</span></span></th>
<th><span data-ttu-id="fa3a5-141">Montant en devise comptable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-142">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-143">CC099</span><span class="sxs-lookup"><span data-stu-id="fa3a5-143">CC099</span></span></td>
<td><span data-ttu-id="fa3a5-144">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="fa3a5-144">Default cost center</span></span></td>
<td><span data-ttu-id="fa3a5-145">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-145">10001</span></span></td>
<td><span data-ttu-id="fa3a5-146">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-146">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="fa3a5-148">Étape 1 : Traiter le calcul du comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="fa3a5-149">Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="fa3a5-150">Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="fa3a5-151">Définir la règle de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-151">Define the cost behavior rule</span></span>

<span data-ttu-id="fa3a5-152">Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="fa3a5-153">Les factures d'électricité correspondent souvent à cette définition.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="fa3a5-154">Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH).</span><span class="sxs-lookup"><span data-stu-id="fa3a5-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="fa3a5-155">Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :</span><span class="sxs-lookup"><span data-stu-id="fa3a5-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="fa3a5-156">Montant fixe 1 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="fa3a5-157">0 &lt;= 1 000,00 = Fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="fa3a5-158">1 000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="fa3a5-159">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="fa3a5-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fa3a5-160">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="fa3a5-160">Journal</span></span></th>
<th><span data-ttu-id="fa3a5-161">Type de journal</span><span class="sxs-lookup"><span data-stu-id="fa3a5-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="fa3a5-162">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="fa3a5-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="fa3a5-163">Version</span><span class="sxs-lookup"><span data-stu-id="fa3a5-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-164">00001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-164">00001</span></span></td>
<td><span data-ttu-id="fa3a5-165">Journal de calcul de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="fa3a5-166">Exercice</span><span class="sxs-lookup"><span data-stu-id="fa3a5-166">Fiscal</span></span></td>
<td><span data-ttu-id="fa3a5-167">2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-167">2017</span></span></td>
<td><span data-ttu-id="fa3a5-168">Période 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-168">Period 1</span></span></td>
<td><span data-ttu-id="fa3a5-169">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="fa3a5-170">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fa3a5-171">Date comptable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-172">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-173">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-173">Cost element</span></span></th>
<th><span data-ttu-id="fa3a5-174">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-174">Cost behavior</span></span></th>
<th><span data-ttu-id="fa3a5-175">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-176">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-177">CC099</span><span class="sxs-lookup"><span data-stu-id="fa3a5-177">CC099</span></span></td>
<td><span data-ttu-id="fa3a5-178">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="fa3a5-178">Default cost center</span></span></td>
<td><span data-ttu-id="fa3a5-179">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-179">10001</span></span></td>
<td><span data-ttu-id="fa3a5-180">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-180">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-181">Non classifié</span><span class="sxs-lookup"><span data-stu-id="fa3a5-181">Unclassified</span></span></td>
<td><span data-ttu-id="fa3a5-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="fa3a5-183">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-184">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-185">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-185">Cost element</span></span></th>
<th><span data-ttu-id="fa3a5-186">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-186">Cost behavior</span></span></th>
<th><span data-ttu-id="fa3a5-187">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-187">Amount</span></span></th>
<th><span data-ttu-id="fa3a5-188">Date comptable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-189">CC099</span><span class="sxs-lookup"><span data-stu-id="fa3a5-189">CC099</span></span></td>
<td><span data-ttu-id="fa3a5-190">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="fa3a5-190">Default cost center</span></span></td>
<td><span data-ttu-id="fa3a5-191">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-191">10001</span></span></td>
<td><span data-ttu-id="fa3a5-192">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-192">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-193">Non classifié</span><span class="sxs-lookup"><span data-stu-id="fa3a5-193">Unclassified</span></span></td>
<td><span data-ttu-id="fa3a5-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-194">10,000.00</span></span></td>
<td><span data-ttu-id="fa3a5-195">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-196">CC099</span><span class="sxs-lookup"><span data-stu-id="fa3a5-196">CC099</span></span></td>
<td><span data-ttu-id="fa3a5-197">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="fa3a5-197">Default cost center</span></span></td>
<td><span data-ttu-id="fa3a5-198">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-198">10001</span></span></td>
<td><span data-ttu-id="fa3a5-199">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-199">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-200">Non classifié</span><span class="sxs-lookup"><span data-stu-id="fa3a5-200">Unclassified</span></span></td>
<td><span data-ttu-id="fa3a5-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-201">-10,000.00</span></span></td>
<td><span data-ttu-id="fa3a5-202">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-203">CC099</span><span class="sxs-lookup"><span data-stu-id="fa3a5-203">CC099</span></span></td>
<td><span data-ttu-id="fa3a5-204">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="fa3a5-204">Default cost center</span></span></td>
<td><span data-ttu-id="fa3a5-205">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-205">10001</span></span></td>
<td><span data-ttu-id="fa3a5-206">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-206">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-207">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-207">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-208">1,000.00</span></span></td>
<td><span data-ttu-id="fa3a5-209">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-210">CC099</span><span class="sxs-lookup"><span data-stu-id="fa3a5-210">CC099</span></span></td>
<td><span data-ttu-id="fa3a5-211">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="fa3a5-211">Default cost center</span></span></td>
<td><span data-ttu-id="fa3a5-212">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-212">10001</span></span></td>
<td><span data-ttu-id="fa3a5-213">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-213">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-214">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-214">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-215">9 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-215">9,000.00</span></span></td>
<td><span data-ttu-id="fa3a5-216">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-217">Pour obtenir des informations détaillées sur le comportement de coûts, voir la stratégie de comportement de coûts.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="fa3a5-218">(Notez que cette rubrique n'est pas complète et sera bientôt mise à jour.)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="fa3a5-219">Étape 2 : Traiter le calcul de distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="fa3a5-220">La distribution des coûts est utilisée pour redistribuer le coût d'un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="fa3a5-221">La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l'élément de coût principal du coût d'origine.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="fa3a5-222">Définir la règle de distribution de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-222">Define the cost distribution rule</span></span>

<span data-ttu-id="fa3a5-223">Dans la comptabilité financière, les coûts d'électricité sont souvent enregistrés comme un montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="fa3a5-224">Dans le Contrôle de gestion, cette approche n'est pas assez détaillée.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="fa3a5-225">Le coût variable doit être attribué aux différents objets de coûts sur une base juste.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="fa3a5-226">La base de répartition la plus logique est la consommation de l'électricité (KWH).</span><span class="sxs-lookup"><span data-stu-id="fa3a5-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="fa3a5-227">Un membre de dimension statistique nommé Électricité est créé, et la consommation d'électricité est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="fa3a5-228">Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-229">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-229">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="fa3a5-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-231">CC001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-231">CC001</span></span></td>
<td><span data-ttu-id="fa3a5-232">RH</span><span class="sxs-lookup"><span data-stu-id="fa3a5-232">HR</span></span></td>
<td><span data-ttu-id="fa3a5-233">1 000</span><span class="sxs-lookup"><span data-stu-id="fa3a5-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-234">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-234">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-235">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-235">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-236">6 000</span><span class="sxs-lookup"><span data-stu-id="fa3a5-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-237">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-237">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-238">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-238">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-239">0</span><span class="sxs-lookup"><span data-stu-id="fa3a5-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-240">Le tableau suivant illustre le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-241">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-241">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-242">Ampleur</span><span class="sxs-lookup"><span data-stu-id="fa3a5-242">Magnitude</span></span></th>
<th><span data-ttu-id="fa3a5-243">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="fa3a5-243">Allocation factor</span></span></th>
<th><span data-ttu-id="fa3a5-244">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-245">CC001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-245">CC001</span></span></td>
<td><span data-ttu-id="fa3a5-246">RH</span><span class="sxs-lookup"><span data-stu-id="fa3a5-246">HR</span></span></td>
<td><span data-ttu-id="fa3a5-247">1 000</span><span class="sxs-lookup"><span data-stu-id="fa3a5-247">1,000</span></span></td>
<td><span data-ttu-id="fa3a5-248">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="fa3a5-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="fa3a5-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-250">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-250">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-251">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-251">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-252">6 000</span><span class="sxs-lookup"><span data-stu-id="fa3a5-252">6,000</span></span></td>
<td><span data-ttu-id="fa3a5-253">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="fa3a5-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="fa3a5-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-255">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-255">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-256">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-256">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-257">0</span><span class="sxs-lookup"><span data-stu-id="fa3a5-257">0</span></span></td>
<td><span data-ttu-id="fa3a5-258">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="fa3a5-259">0,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-260">Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l'électricité.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="fa3a5-261">Vous pouvez obtenir ce résultat à l'aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-262">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-262">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-263">Formule</span><span class="sxs-lookup"><span data-stu-id="fa3a5-263">Formula</span></span></th>
<th><span data-ttu-id="fa3a5-264">Ampleur</span><span class="sxs-lookup"><span data-stu-id="fa3a5-264">Magnitude</span></span></th>
<th><span data-ttu-id="fa3a5-265">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="fa3a5-265">Allocation factor</span></span></th>
<th><span data-ttu-id="fa3a5-266">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-267">CC001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-267">CC001</span></span></td>
<td><span data-ttu-id="fa3a5-268">RH</span><span class="sxs-lookup"><span data-stu-id="fa3a5-268">HR</span></span></td>
<td><span data-ttu-id="fa3a5-269">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="fa3a5-270">1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-270">1</span></span></td>
<td><span data-ttu-id="fa3a5-271">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="fa3a5-272">500,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-273">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-273">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-274">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-274">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-275">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="fa3a5-276">1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-276">1</span></span></td>
<td><span data-ttu-id="fa3a5-277">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="fa3a5-278">500,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-279">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-279">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-280">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-280">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="fa3a5-282">0</span><span class="sxs-lookup"><span data-stu-id="fa3a5-282">0</span></span></td>
<td><span data-ttu-id="fa3a5-283">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="fa3a5-284">0,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="fa3a5-285">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="fa3a5-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fa3a5-286">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="fa3a5-286">Journal</span></span></th>
<th><span data-ttu-id="fa3a5-287">Type de journal</span><span class="sxs-lookup"><span data-stu-id="fa3a5-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="fa3a5-288">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="fa3a5-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="fa3a5-289">Version</span><span class="sxs-lookup"><span data-stu-id="fa3a5-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-290">00002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-290">00002</span></span></td>
<td><span data-ttu-id="fa3a5-291">Journal de calcul de la distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="fa3a5-292">Exercice</span><span class="sxs-lookup"><span data-stu-id="fa3a5-292">Fiscal</span></span></td>
<td><span data-ttu-id="fa3a5-293">2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-293">2017</span></span></td>
<td><span data-ttu-id="fa3a5-294">Période 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-294">Period 1</span></span></td>
<td><span data-ttu-id="fa3a5-295">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="fa3a5-296">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fa3a5-297">Date comptable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-298">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-299">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-299">Cost element</span></span></th>
<th><span data-ttu-id="fa3a5-300">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-300">Cost behavior</span></span></th>
<th><span data-ttu-id="fa3a5-301">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-302">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-303">CC099</span><span class="sxs-lookup"><span data-stu-id="fa3a5-303">CC099</span></span></td>
<td><span data-ttu-id="fa3a5-304">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="fa3a5-304">Default cost center</span></span></td>
<td><span data-ttu-id="fa3a5-305">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-305">10001</span></span></td>
<td><span data-ttu-id="fa3a5-306">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-306">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-307">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-307">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-308">1 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-309">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-310">CC099</span><span class="sxs-lookup"><span data-stu-id="fa3a5-310">CC099</span></span></td>
<td><span data-ttu-id="fa3a5-311">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="fa3a5-311">Default cost center</span></span></td>
<td><span data-ttu-id="fa3a5-312">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-312">10001</span></span></td>
<td><span data-ttu-id="fa3a5-313">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-313">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-314">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-314">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-315">9 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="fa3a5-316">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-317">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-318">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-318">Cost element</span></span></th>
<th><span data-ttu-id="fa3a5-319">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-319">Cost behavior</span></span></th>
<th><span data-ttu-id="fa3a5-320">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-320">Amount</span></span></th>
<th><span data-ttu-id="fa3a5-321">Date comptable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-322">CC099</span><span class="sxs-lookup"><span data-stu-id="fa3a5-322">CC099</span></span></td>
<td><span data-ttu-id="fa3a5-323">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="fa3a5-323">Default cost center</span></span></td>
<td><span data-ttu-id="fa3a5-324">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-324">10001</span></span></td>
<td><span data-ttu-id="fa3a5-325">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-325">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-326">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-326">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-327">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-327">-1,000.00</span></span></td>
<td><span data-ttu-id="fa3a5-328">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-329">CC001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-329">CC001</span></span></td>
<td><span data-ttu-id="fa3a5-330">RH</span><span class="sxs-lookup"><span data-stu-id="fa3a5-330">HR</span></span></td>
<td><span data-ttu-id="fa3a5-331">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-331">10001</span></span></td>
<td><span data-ttu-id="fa3a5-332">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-332">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-333">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-333">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-334">500,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-334">500.00</span></span></td>
<td><span data-ttu-id="fa3a5-335">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-336">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-336">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-337">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-337">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-338">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-338">10001</span></span></td>
<td><span data-ttu-id="fa3a5-339">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-339">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-340">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-340">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-341">500,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-341">500.00</span></span></td>
<td><span data-ttu-id="fa3a5-342">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-343">CC099</span><span class="sxs-lookup"><span data-stu-id="fa3a5-343">CC099</span></span></td>
<td><span data-ttu-id="fa3a5-344">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="fa3a5-344">Default cost center</span></span></td>
<td><span data-ttu-id="fa3a5-345">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-345">10001</span></span></td>
<td><span data-ttu-id="fa3a5-346">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-346">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-347">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-347">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-348">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-348">-9,000.00</span></span></td>
<td><span data-ttu-id="fa3a5-349">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-350">CC001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-350">CC001</span></span></td>
<td><span data-ttu-id="fa3a5-351">RH</span><span class="sxs-lookup"><span data-stu-id="fa3a5-351">HR</span></span></td>
<td><span data-ttu-id="fa3a5-352">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-352">10001</span></span></td>
<td><span data-ttu-id="fa3a5-353">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-353">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-354">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-354">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="fa3a5-355">1,285.71</span></span></td>
<td><span data-ttu-id="fa3a5-356">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-357">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-357">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-358">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-358">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-359">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-359">10001</span></span></td>
<td><span data-ttu-id="fa3a5-360">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-360">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-361">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-361">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="fa3a5-362">7,714.29</span></span></td>
<td><span data-ttu-id="fa3a5-363">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-364">Pour plus d'informations sur les bases de distribution et de répartition des coûts, consultez la stratégie de distribution des coûts et les bases de répartition.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="fa3a5-365">(Notez que cette rubrique n'est pas complète et sera bientôt mise à jour.)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="fa3a5-366">Étape 3 : Traitement du calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="fa3a5-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="fa3a5-367">Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="fa3a5-368">Les frais sont basés sur un taux de coût prédéterminé et l'ampleur de la base d'affectation de répartition.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="fa3a5-369">Définition du taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="fa3a5-369">Define the overhead rate</span></span>

<span data-ttu-id="fa3a5-370">L'objet de coût CC001 HR contribue à un ensemble de projets internes.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="fa3a5-371">Un membre de dimension statistique nommé Projets HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-372">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-372">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-373">Heures</span><span class="sxs-lookup"><span data-stu-id="fa3a5-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-374">Proj 1</span></span></td>
<td><span data-ttu-id="fa3a5-375">Projet 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-375">Project 1</span></span></td>
<td><span data-ttu-id="fa3a5-376">3</span><span class="sxs-lookup"><span data-stu-id="fa3a5-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-377">Proj 2</span></span></td>
<td><span data-ttu-id="fa3a5-378">Projet 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-378">Project 2</span></span></td>
<td><span data-ttu-id="fa3a5-379">1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-380">Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-381">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-381">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-382">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-382">Cost element</span></span></th>
<th><span data-ttu-id="fa3a5-383">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-383">Cost behavior</span></span></th>
<th><span data-ttu-id="fa3a5-384">Unités</span><span class="sxs-lookup"><span data-stu-id="fa3a5-384">Units</span></span></th>
<th><span data-ttu-id="fa3a5-385">Taux</span><span class="sxs-lookup"><span data-stu-id="fa3a5-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-386">CC001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-386">CC001</span></span></td>
<td><span data-ttu-id="fa3a5-387">RH</span><span class="sxs-lookup"><span data-stu-id="fa3a5-387">HR</span></span></td>
<td><span data-ttu-id="fa3a5-388">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-388">10001</span></span></td>
<td><span data-ttu-id="fa3a5-389">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-389">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-390">1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-390">1</span></span></td>
<td><span data-ttu-id="fa3a5-391">10</span><span class="sxs-lookup"><span data-stu-id="fa3a5-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-392">Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-393">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-393">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-394">Ampleur</span><span class="sxs-lookup"><span data-stu-id="fa3a5-394">Magnitude</span></span></th>
<th><span data-ttu-id="fa3a5-395">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-395">Cost element</span></span></th>
<th><span data-ttu-id="fa3a5-396">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="fa3a5-396">Allocation factor</span></span></th>
<th><span data-ttu-id="fa3a5-397">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-398">Proj 1</span></span></td>
<td><span data-ttu-id="fa3a5-399">Projet 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-399">Project 1</span></span></td>
<td><span data-ttu-id="fa3a5-400">3</span><span class="sxs-lookup"><span data-stu-id="fa3a5-400">3</span></span></td>
<td><span data-ttu-id="fa3a5-401">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-401">10001</span></span></td>
<td><span data-ttu-id="fa3a5-402">(3 ÷ 1) × 10m00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="fa3a5-403">30,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-404">Proj 2</span></span></td>
<td><span data-ttu-id="fa3a5-405">Projet 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-405">Project 2</span></span></td>
<td><span data-ttu-id="fa3a5-406">1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-406">1</span></span></td>
<td><span data-ttu-id="fa3a5-407">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-407">10001</span></span></td>
<td><span data-ttu-id="fa3a5-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="fa3a5-409">10,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="fa3a5-410">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="fa3a5-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fa3a5-411">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="fa3a5-411">Journal</span></span></th>
<th><span data-ttu-id="fa3a5-412">Type de journal</span><span class="sxs-lookup"><span data-stu-id="fa3a5-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="fa3a5-413">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="fa3a5-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="fa3a5-414">Version</span><span class="sxs-lookup"><span data-stu-id="fa3a5-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-415">00003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-415">00003</span></span></td>
<td><span data-ttu-id="fa3a5-416">Journal de calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="fa3a5-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="fa3a5-417">Exercice</span><span class="sxs-lookup"><span data-stu-id="fa3a5-417">Fiscal</span></span></td>
<td><span data-ttu-id="fa3a5-418">2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-418">2017</span></span></td>
<td><span data-ttu-id="fa3a5-419">Période 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-419">Period 1</span></span></td>
<td><span data-ttu-id="fa3a5-420">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="fa3a5-421">Entrées du journal (pour le calcul du taux de frais généraux)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fa3a5-422">Date comptable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-423">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-423">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-424">Ampleur</span><span class="sxs-lookup"><span data-stu-id="fa3a5-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-425">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-426">Proj 1</span></span></td>
<td><span data-ttu-id="fa3a5-427">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="fa3a5-428">3,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-429">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-430">Proj 2</span></span></td>
<td><span data-ttu-id="fa3a5-431">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="fa3a5-432">1,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="fa3a5-433">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-434">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-435">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-435">Cost element</span></span></th>
<th><span data-ttu-id="fa3a5-436">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-436">Cost behavior</span></span></th>
<th><span data-ttu-id="fa3a5-437">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-437">Amount</span></span></th>
<th><span data-ttu-id="fa3a5-438">Date comptable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-439">CC0001</span></span></td>
<td><span data-ttu-id="fa3a5-440">RH</span><span class="sxs-lookup"><span data-stu-id="fa3a5-440">HR</span></span></td>
<td><span data-ttu-id="fa3a5-441">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-441">10001</span></span></td>
<td><span data-ttu-id="fa3a5-442">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-442">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-443">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-443">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-444">-30.00</span></span></td>
<td><span data-ttu-id="fa3a5-445">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-446">Proj 1</span></span></td>
<td><span data-ttu-id="fa3a5-447">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="fa3a5-448">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-448">10001</span></span></td>
<td><span data-ttu-id="fa3a5-449">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-449">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-450">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-450">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-451">30,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-451">30.00</span></span></td>
<td><span data-ttu-id="fa3a5-452">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-453">CC001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-453">CC001</span></span></td>
<td><span data-ttu-id="fa3a5-454">RH</span><span class="sxs-lookup"><span data-stu-id="fa3a5-454">HR</span></span></td>
<td><span data-ttu-id="fa3a5-455">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-455">10001</span></span></td>
<td><span data-ttu-id="fa3a5-456">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-456">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-457">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-457">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-458">-10.00</span></span></td>
<td><span data-ttu-id="fa3a5-459">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-460">Proj 2</span></span></td>
<td><span data-ttu-id="fa3a5-461">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="fa3a5-462">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-462">10001</span></span></td>
<td><span data-ttu-id="fa3a5-463">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-463">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-464">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-464">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-465">10,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-465">10.00</span></span></td>
<td><span data-ttu-id="fa3a5-466">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-467">Pour plus d'informations sur la stratégie de taux de frais généraux, voir la stratégie et les bases de répartition afférentes.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="fa3a5-468">(Notez que cette rubrique n'est pas complète et sera bientôt mise à jour.)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="fa3a5-469">Étape 4 : Traiter le calcul de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="fa3a5-470">La répartition est utilisée pour affecter le solde d'un objet de coût à d'autres objets de coût en appliquant une base de répartition.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="fa3a5-471">Finance and Operations prend en charge la méthode de répartition réciproque.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="fa3a5-472">Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="fa3a5-473">Le système détermine automatiquement l'ordre correct selon lequel exécuter les répartitions.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="fa3a5-474">Le solde d'un objet de coût est réparti par une seule base de répartition.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="fa3a5-475">Les répartitions entre plusieurs dimensions d'objets de coût et leurs membres respectifs sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="fa3a5-476">L'ordre de répartition est contrôlé par l'unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-476">The allocation order is controlled by the cost control unit.</span></span> <span data-ttu-id="fa3a5-477">[![Méthode réciproque](./media/reciprocal-method.png)]</span><span class="sxs-lookup"><span data-stu-id="fa3a5-477">[![Reciprocal method](./media/reciprocal-method.png)]</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="fa3a5-478">Définir la répartition de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-478">Define the cost allocation</span></span>

<span data-ttu-id="fa3a5-479">Voici un exemple simple expliquant comment suivre le flux du coût.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="fa3a5-480">L'objet de coût CC001 HR contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="fa3a5-481">Un membre de dimension statistique nommé Services HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-482">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-482">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-483">Services HR</span><span class="sxs-lookup"><span data-stu-id="fa3a5-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-484">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-484">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-485">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-485">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-486">35</span><span class="sxs-lookup"><span data-stu-id="fa3a5-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-487">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-487">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-488">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-488">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-489">55</span><span class="sxs-lookup"><span data-stu-id="fa3a5-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-490">CC004</span><span class="sxs-lookup"><span data-stu-id="fa3a5-490">CC004</span></span></td>
<td><span data-ttu-id="fa3a5-491">Emballage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-491">Packaging</span></span></td>
<td><span data-ttu-id="fa3a5-492">10</span><span class="sxs-lookup"><span data-stu-id="fa3a5-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-493">L'objet de coût CC002 Finance contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="fa3a5-494">Un membre de dimension statistique nommé Services Finance est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-495">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-495">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-496">Services Finance</span><span class="sxs-lookup"><span data-stu-id="fa3a5-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-497">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-497">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-498">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-498">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-499">65</span><span class="sxs-lookup"><span data-stu-id="fa3a5-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-500">CC004</span><span class="sxs-lookup"><span data-stu-id="fa3a5-500">CC004</span></span></td>
<td><span data-ttu-id="fa3a5-501">Emballage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-501">Packaging</span></span></td>
<td><span data-ttu-id="fa3a5-502">35</span><span class="sxs-lookup"><span data-stu-id="fa3a5-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-503">L'objet de coût CC003 Assemblage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="fa3a5-504">Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-505">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-505">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-506">Services Assemblage (heures)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-507">Prod 1</span></span></td>
<td><span data-ttu-id="fa3a5-508">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-508">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-509">60</span><span class="sxs-lookup"><span data-stu-id="fa3a5-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-510">Prod 2</span></span></td>
<td><span data-ttu-id="fa3a5-511">Produit 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-511">Product 2</span></span></td>
<td><span data-ttu-id="fa3a5-512">20</span><span class="sxs-lookup"><span data-stu-id="fa3a5-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-513">L'objet de coût CC004 Emballage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="fa3a5-514">Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-515">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-515">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-516">Services Emballage (heures)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-517">Prod 1</span></span></td>
<td><span data-ttu-id="fa3a5-518">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-518">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-519">80</span><span class="sxs-lookup"><span data-stu-id="fa3a5-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-520">Prod 2</span></span></td>
<td><span data-ttu-id="fa3a5-521">Produit 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-521">Product 2</span></span></td>
<td><span data-ttu-id="fa3a5-522">15</span><span class="sxs-lookup"><span data-stu-id="fa3a5-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-523">**Remarque :** dans Finance and Operations, les mesures statistiques telles que les heures de production qu'un produit consomme peuvent être dérivées des données sources.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="fa3a5-524">Pour des informations détaillées sur les fournisseurs de mesures statistiques, voir le modèle de fournisseur de mesures statistiques.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="fa3a5-525">(Notez que cette rubrique n'est pas complète et sera bientôt mise à jour.) Le tableau suivant présente le résultat lorsque les services HR sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="fa3a5-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-526">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-526">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-527">Ampleur</span><span class="sxs-lookup"><span data-stu-id="fa3a5-527">Magnitude</span></span></th>
<th><span data-ttu-id="fa3a5-528">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="fa3a5-528">Allocation factor</span></span></th>
<th><span data-ttu-id="fa3a5-529">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-529">Amount</span></span></th>
<th><span data-ttu-id="fa3a5-530">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-531">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-531">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-532">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-532">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-533">35</span><span class="sxs-lookup"><span data-stu-id="fa3a5-533">35</span></span></td>
<td><span data-ttu-id="fa3a5-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="fa3a5-535">175.00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-535">175.00</span></span></td>
<td><span data-ttu-id="fa3a5-536">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-537">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-537">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-538">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-538">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-539">55</span><span class="sxs-lookup"><span data-stu-id="fa3a5-539">55</span></span></td>
<td><span data-ttu-id="fa3a5-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="fa3a5-541">275.00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-541">275.00</span></span></td>
<td><span data-ttu-id="fa3a5-542">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-543">CC004</span><span class="sxs-lookup"><span data-stu-id="fa3a5-543">CC004</span></span></td>
<td><span data-ttu-id="fa3a5-544">Emballage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-544">Packaging</span></span></td>
<td><span data-ttu-id="fa3a5-545">10</span><span class="sxs-lookup"><span data-stu-id="fa3a5-545">10</span></span></td>
<td><span data-ttu-id="fa3a5-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="fa3a5-547">50,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-547">50.00</span></span></td>
<td><span data-ttu-id="fa3a5-548">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-549">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-549">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-550">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-550">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-551">35</span><span class="sxs-lookup"><span data-stu-id="fa3a5-551">35</span></span></td>
<td><span data-ttu-id="fa3a5-552">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="fa3a5-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="fa3a5-553">436.00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-553">436.00</span></span></td>
<td><span data-ttu-id="fa3a5-554">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-555">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-555">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-556">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-556">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-557">55</span><span class="sxs-lookup"><span data-stu-id="fa3a5-557">55</span></span></td>
<td><span data-ttu-id="fa3a5-558">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="fa3a5-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="fa3a5-559">685.14</span><span class="sxs-lookup"><span data-stu-id="fa3a5-559">685.14</span></span></td>
<td><span data-ttu-id="fa3a5-560">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-561">CC004</span><span class="sxs-lookup"><span data-stu-id="fa3a5-561">CC004</span></span></td>
<td><span data-ttu-id="fa3a5-562">Emballage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-562">Packaging</span></span></td>
<td><span data-ttu-id="fa3a5-563">10</span><span class="sxs-lookup"><span data-stu-id="fa3a5-563">10</span></span></td>
<td><span data-ttu-id="fa3a5-564">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="fa3a5-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="fa3a5-565">124.57</span><span class="sxs-lookup"><span data-stu-id="fa3a5-565">124.57</span></span></td>
<td><span data-ttu-id="fa3a5-566">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-567">Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="fa3a5-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-568">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-568">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-569">Ampleur</span><span class="sxs-lookup"><span data-stu-id="fa3a5-569">Magnitude</span></span></th>
<th><span data-ttu-id="fa3a5-570">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="fa3a5-570">Allocation factor</span></span></th>
<th><span data-ttu-id="fa3a5-571">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-571">Amount</span></span></th>
<th><span data-ttu-id="fa3a5-572">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-573">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-573">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-574">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-574">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-575">65</span><span class="sxs-lookup"><span data-stu-id="fa3a5-575">65</span></span></td>
<td><span data-ttu-id="fa3a5-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="fa3a5-577">438.75</span><span class="sxs-lookup"><span data-stu-id="fa3a5-577">438.75</span></span></td>
<td><span data-ttu-id="fa3a5-578">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-579">CC004</span><span class="sxs-lookup"><span data-stu-id="fa3a5-579">CC004</span></span></td>
<td><span data-ttu-id="fa3a5-580">Emballage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-580">Packaging</span></span></td>
<td><span data-ttu-id="fa3a5-581">35</span><span class="sxs-lookup"><span data-stu-id="fa3a5-581">35</span></span></td>
<td><span data-ttu-id="fa3a5-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="fa3a5-583">236.25</span><span class="sxs-lookup"><span data-stu-id="fa3a5-583">236.25</span></span></td>
<td><span data-ttu-id="fa3a5-584">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-585">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-585">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-586">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-586">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-587">65</span><span class="sxs-lookup"><span data-stu-id="fa3a5-587">65</span></span></td>
<td><span data-ttu-id="fa3a5-588">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="fa3a5-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="fa3a5-589">5,297.69</span></span></td>
<td><span data-ttu-id="fa3a5-590">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-591">CC004</span><span class="sxs-lookup"><span data-stu-id="fa3a5-591">CC004</span></span></td>
<td><span data-ttu-id="fa3a5-592">Emballage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-592">Packaging</span></span></td>
<td><span data-ttu-id="fa3a5-593">35</span><span class="sxs-lookup"><span data-stu-id="fa3a5-593">35</span></span></td>
<td><span data-ttu-id="fa3a5-594">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="fa3a5-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="fa3a5-595">2,852.60</span></span></td>
<td><span data-ttu-id="fa3a5-596">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-597">Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="fa3a5-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-598">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-598">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-599">Ampleur</span><span class="sxs-lookup"><span data-stu-id="fa3a5-599">Magnitude</span></span></th>
<th><span data-ttu-id="fa3a5-600">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="fa3a5-600">Allocation factor</span></span></th>
<th><span data-ttu-id="fa3a5-601">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-601">Amount</span></span></th>
<th><span data-ttu-id="fa3a5-602">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-603">Prod 1</span></span></td>
<td><span data-ttu-id="fa3a5-604">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-604">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-605">60</span><span class="sxs-lookup"><span data-stu-id="fa3a5-605">60</span></span></td>
<td><span data-ttu-id="fa3a5-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="fa3a5-607">535.31</span><span class="sxs-lookup"><span data-stu-id="fa3a5-607">535.31</span></span></td>
<td><span data-ttu-id="fa3a5-608">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-609">Prod 2</span></span></td>
<td><span data-ttu-id="fa3a5-610">Produit 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-610">Product 2</span></span></td>
<td><span data-ttu-id="fa3a5-611">20</span><span class="sxs-lookup"><span data-stu-id="fa3a5-611">20</span></span></td>
<td><span data-ttu-id="fa3a5-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="fa3a5-613">178.44</span><span class="sxs-lookup"><span data-stu-id="fa3a5-613">178.44</span></span></td>
<td><span data-ttu-id="fa3a5-614">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-615">Prod 1</span></span></td>
<td><span data-ttu-id="fa3a5-616">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-616">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-617">60</span><span class="sxs-lookup"><span data-stu-id="fa3a5-617">60</span></span></td>
<td><span data-ttu-id="fa3a5-618">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="fa3a5-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="fa3a5-619">4,487.12</span></span></td>
<td><span data-ttu-id="fa3a5-620">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-621">Prod 2</span></span></td>
<td><span data-ttu-id="fa3a5-622">Produit 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-622">Product 2</span></span></td>
<td><span data-ttu-id="fa3a5-623">20</span><span class="sxs-lookup"><span data-stu-id="fa3a5-623">20</span></span></td>
<td><span data-ttu-id="fa3a5-624">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="fa3a5-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="fa3a5-625">1,495.71</span></span></td>
<td><span data-ttu-id="fa3a5-626">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa3a5-627">Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="fa3a5-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-628">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-628">Cost object</span></span></th>
<th><span data-ttu-id="fa3a5-629">Ampleur</span><span class="sxs-lookup"><span data-stu-id="fa3a5-629">Magnitude</span></span></th>
<th><span data-ttu-id="fa3a5-630">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="fa3a5-630">Allocation factor</span></span></th>
<th><span data-ttu-id="fa3a5-631">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-631">Amount</span></span></th>
<th><span data-ttu-id="fa3a5-632">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-633">Prod 1</span></span></td>
<td><span data-ttu-id="fa3a5-634">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-634">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-635">80</span><span class="sxs-lookup"><span data-stu-id="fa3a5-635">80</span></span></td>
<td><span data-ttu-id="fa3a5-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="fa3a5-637">241.05</span><span class="sxs-lookup"><span data-stu-id="fa3a5-637">241.05</span></span></td>
<td><span data-ttu-id="fa3a5-638">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-639">Prod 2</span></span></td>
<td><span data-ttu-id="fa3a5-640">Produit 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-640">Product 2</span></span></td>
<td><span data-ttu-id="fa3a5-641">15</span><span class="sxs-lookup"><span data-stu-id="fa3a5-641">15</span></span></td>
<td><span data-ttu-id="fa3a5-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="fa3a5-643">45.20</span><span class="sxs-lookup"><span data-stu-id="fa3a5-643">45.20</span></span></td>
<td><span data-ttu-id="fa3a5-644">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-645">Prod 1</span></span></td>
<td><span data-ttu-id="fa3a5-646">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-646">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-647">80</span><span class="sxs-lookup"><span data-stu-id="fa3a5-647">80</span></span></td>
<td><span data-ttu-id="fa3a5-648">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="fa3a5-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="fa3a5-649">2,507.09</span></span></td>
<td><span data-ttu-id="fa3a5-650">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-651">Prod 2</span></span></td>
<td><span data-ttu-id="fa3a5-652">Produit 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-652">Product 2</span></span></td>
<td><span data-ttu-id="fa3a5-653">15</span><span class="sxs-lookup"><span data-stu-id="fa3a5-653">15</span></span></td>
<td><span data-ttu-id="fa3a5-654">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="fa3a5-655">470.08</span><span class="sxs-lookup"><span data-stu-id="fa3a5-655">470.08</span></span></td>
<td><span data-ttu-id="fa3a5-656">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="fa3a5-657">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fa3a5-658">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="fa3a5-658">Journal</span></span></th>
<th><span data-ttu-id="fa3a5-659">Type de journal</span><span class="sxs-lookup"><span data-stu-id="fa3a5-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="fa3a5-660">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="fa3a5-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="fa3a5-661">Version</span><span class="sxs-lookup"><span data-stu-id="fa3a5-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-662">00004</span><span class="sxs-lookup"><span data-stu-id="fa3a5-662">00004</span></span></td>
<td><span data-ttu-id="fa3a5-663">Journal de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="fa3a5-664">Exercice</span><span class="sxs-lookup"><span data-stu-id="fa3a5-664">Fiscal</span></span></td>
<td><span data-ttu-id="fa3a5-665">2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-665">2017</span></span></td>
<td><span data-ttu-id="fa3a5-666">Période 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-666">Period 1</span></span></td>
<td><span data-ttu-id="fa3a5-667">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="fa3a5-668">Lignes de journal</span><span class="sxs-lookup"><span data-stu-id="fa3a5-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fa3a5-669">Date comptable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-670">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-671">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-671">Cost element</span></span></th>
<th><span data-ttu-id="fa3a5-672">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-672">Cost behavior</span></span></th>
<th><span data-ttu-id="fa3a5-673">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-674">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-675">CC001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-675">CC001</span></span></td>
<td><span data-ttu-id="fa3a5-676">RH</span><span class="sxs-lookup"><span data-stu-id="fa3a5-676">HR</span></span></td>
<td><span data-ttu-id="fa3a5-677">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-677">10001</span></span></td>
<td><span data-ttu-id="fa3a5-678">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-678">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-679">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-679">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-680">500,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-681">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-682">CC001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-682">CC001</span></span></td>
<td><span data-ttu-id="fa3a5-683">RH</span><span class="sxs-lookup"><span data-stu-id="fa3a5-683">HR</span></span></td>
<td><span data-ttu-id="fa3a5-684">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-684">10001</span></span></td>
<td><span data-ttu-id="fa3a5-685">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-685">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-686">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-686">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="fa3a5-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-688">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-689">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-689">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-690">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-690">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-691">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-691">10001</span></span></td>
<td><span data-ttu-id="fa3a5-692">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-692">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-693">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-693">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-694">675.00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-695">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-696">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-696">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-697">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-697">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-698">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-698">10001</span></span></td>
<td><span data-ttu-id="fa3a5-699">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-699">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-700">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-700">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="fa3a5-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-702">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-703">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-703">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-704">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-704">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-705">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-705">10001</span></span></td>
<td><span data-ttu-id="fa3a5-706">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-706">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-707">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-707">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-708">713.75</span><span class="sxs-lookup"><span data-stu-id="fa3a5-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-709">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-710">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-710">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-711">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-711">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-712">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-712">10001</span></span></td>
<td><span data-ttu-id="fa3a5-713">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-713">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-714">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-714">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="fa3a5-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-716">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-717">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-717">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-718">Emballage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-718">Packaging</span></span></td>
<td><span data-ttu-id="fa3a5-719">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-719">10001</span></span></td>
<td><span data-ttu-id="fa3a5-720">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-720">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-721">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-721">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-722">286.25</span><span class="sxs-lookup"><span data-stu-id="fa3a5-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-723">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-724">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-724">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-725">Emballage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-725">Packaging</span></span></td>
<td><span data-ttu-id="fa3a5-726">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-726">10001</span></span></td>
<td><span data-ttu-id="fa3a5-727">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-727">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-728">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-728">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="fa3a5-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-730">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-731">Prod 1</span></span></td>
<td><span data-ttu-id="fa3a5-732">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-732">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-733">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-733">10001</span></span></td>
<td><span data-ttu-id="fa3a5-734">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-734">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-735">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-735">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-736">776.36</span><span class="sxs-lookup"><span data-stu-id="fa3a5-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-737">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-738">Prod 1</span></span></td>
<td><span data-ttu-id="fa3a5-739">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-739">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-740">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-740">10001</span></span></td>
<td><span data-ttu-id="fa3a5-741">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-741">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-742">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-742">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="fa3a5-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-744">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-745">Prod 2</span></span></td>
<td><span data-ttu-id="fa3a5-746">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-746">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-747">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-747">10001</span></span></td>
<td><span data-ttu-id="fa3a5-748">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-748">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-749">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-749">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-750">223.64</span><span class="sxs-lookup"><span data-stu-id="fa3a5-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-751">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="fa3a5-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-752">Prod 2</span></span></td>
<td><span data-ttu-id="fa3a5-753">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-753">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-754">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-754">10001</span></span></td>
<td><span data-ttu-id="fa3a5-755">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-755">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-756">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-756">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="fa3a5-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="fa3a5-758">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fa3a5-759">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fa3a5-760">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-760">Cost element</span></span></th>
<th><span data-ttu-id="fa3a5-761">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="fa3a5-761">Cost behavior</span></span></th>
<th><span data-ttu-id="fa3a5-762">Montant</span><span class="sxs-lookup"><span data-stu-id="fa3a5-762">Amount</span></span></th>
<th><span data-ttu-id="fa3a5-763">Date comptable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fa3a5-764">CC001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-764">CC001</span></span></td>
<td><span data-ttu-id="fa3a5-765">RH</span><span class="sxs-lookup"><span data-stu-id="fa3a5-765">HR</span></span></td>
<td><span data-ttu-id="fa3a5-766">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-766">10001</span></span></td>
<td><span data-ttu-id="fa3a5-767">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-767">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-768">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-768">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-769">-500.00</span></span></td>
<td><span data-ttu-id="fa3a5-770">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-771">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-771">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-772">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-772">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-773">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-773">10001</span></span></td>
<td><span data-ttu-id="fa3a5-774">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-774">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-775">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-775">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-776">175.00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-776">175.00</span></span></td>
<td><span data-ttu-id="fa3a5-777">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-778">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-778">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-779">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-779">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-780">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-780">10001</span></span></td>
<td><span data-ttu-id="fa3a5-781">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-781">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-782">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-782">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-783">275.00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-783">275.00</span></span></td>
<td><span data-ttu-id="fa3a5-784">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-785">CC004</span><span class="sxs-lookup"><span data-stu-id="fa3a5-785">CC004</span></span></td>
<td><span data-ttu-id="fa3a5-786">Emballage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-786">Packaging</span></span></td>
<td><span data-ttu-id="fa3a5-787">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-787">10001</span></span></td>
<td><span data-ttu-id="fa3a5-788">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-788">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-789">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-789">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-790">50,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-790">50,00</span></span></td>
<td><span data-ttu-id="fa3a5-791">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-792">CC001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-792">CC001</span></span></td>
<td><span data-ttu-id="fa3a5-793">RH</span><span class="sxs-lookup"><span data-stu-id="fa3a5-793">HR</span></span></td>
<td><span data-ttu-id="fa3a5-794">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-794">10001</span></span></td>
<td><span data-ttu-id="fa3a5-795">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-795">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-796">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-796">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-797">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="fa3a5-797">-1,245.71</span></span></td>
<td><span data-ttu-id="fa3a5-798">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-799">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-799">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-800">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-800">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-801">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-801">10001</span></span></td>
<td><span data-ttu-id="fa3a5-802">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-802">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-803">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-803">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-804">436.00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-804">436.00</span></span></td>
<td><span data-ttu-id="fa3a5-805">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-806">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-806">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-807">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-807">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-808">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-808">10001</span></span></td>
<td><span data-ttu-id="fa3a5-809">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-809">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-810">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-810">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-811">685.14</span><span class="sxs-lookup"><span data-stu-id="fa3a5-811">685.14</span></span></td>
<td><span data-ttu-id="fa3a5-812">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-813">CC004</span><span class="sxs-lookup"><span data-stu-id="fa3a5-813">CC004</span></span></td>
<td><span data-ttu-id="fa3a5-814">Emballage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-814">Packaging</span></span></td>
<td><span data-ttu-id="fa3a5-815">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-815">10001</span></span></td>
<td><span data-ttu-id="fa3a5-816">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-816">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-817">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-817">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-818">124.57</span><span class="sxs-lookup"><span data-stu-id="fa3a5-818">124.57</span></span></td>
<td><span data-ttu-id="fa3a5-819">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-820">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-820">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-821">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-821">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-822">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-822">10001</span></span></td>
<td><span data-ttu-id="fa3a5-823">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-823">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-824">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-824">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-825">-675.00</span></span></td>
<td><span data-ttu-id="fa3a5-826">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-827">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-827">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-828">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-828">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-829">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-829">10001</span></span></td>
<td><span data-ttu-id="fa3a5-830">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-830">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-831">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-831">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-832">438.75</span><span class="sxs-lookup"><span data-stu-id="fa3a5-832">438.75</span></span></td>
<td><span data-ttu-id="fa3a5-833">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-834">CC004</span><span class="sxs-lookup"><span data-stu-id="fa3a5-834">CC004</span></span></td>
<td><span data-ttu-id="fa3a5-835">Emballage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-835">Packaging</span></span></td>
<td><span data-ttu-id="fa3a5-836">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-836">10001</span></span></td>
<td><span data-ttu-id="fa3a5-837">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-837">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-838">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-838">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-839">236.25</span><span class="sxs-lookup"><span data-stu-id="fa3a5-839">236.25</span></span></td>
<td><span data-ttu-id="fa3a5-840">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-841">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-841">CC002</span></span></td>
<td><span data-ttu-id="fa3a5-842">Finances</span><span class="sxs-lookup"><span data-stu-id="fa3a5-842">Finance</span></span></td>
<td><span data-ttu-id="fa3a5-843">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-843">10001</span></span></td>
<td><span data-ttu-id="fa3a5-844">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-844">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-845">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-845">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-846">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="fa3a5-846">-8,150.29</span></span></td>
<td><span data-ttu-id="fa3a5-847">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-848">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-848">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-849">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-849">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-850">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-850">10001</span></span></td>
<td><span data-ttu-id="fa3a5-851">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-851">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-852">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-852">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="fa3a5-853">5,297.69</span></span></td>
<td><span data-ttu-id="fa3a5-854">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-855">CC004</span><span class="sxs-lookup"><span data-stu-id="fa3a5-855">CC004</span></span></td>
<td><span data-ttu-id="fa3a5-856">Emballage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-856">Packaging</span></span></td>
<td><span data-ttu-id="fa3a5-857">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-857">10001</span></span></td>
<td><span data-ttu-id="fa3a5-858">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-858">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-859">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-859">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="fa3a5-860">2,852.60</span></span></td>
<td><span data-ttu-id="fa3a5-861">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-862">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-862">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-863">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-863">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-864">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-864">10001</span></span></td>
<td><span data-ttu-id="fa3a5-865">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-865">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-866">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-866">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="fa3a5-867">-713.75</span></span></td>
<td><span data-ttu-id="fa3a5-868">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-869">Prod 1</span></span></td>
<td><span data-ttu-id="fa3a5-870">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-870">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-871">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-871">10001</span></span></td>
<td><span data-ttu-id="fa3a5-872">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-872">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-873">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-873">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-874">535.31</span><span class="sxs-lookup"><span data-stu-id="fa3a5-874">535.31</span></span></td>
<td><span data-ttu-id="fa3a5-875">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-876">Prod 2</span></span></td>
<td><span data-ttu-id="fa3a5-877">Produit 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-877">Product 2</span></span></td>
<td><span data-ttu-id="fa3a5-878">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-878">10001</span></span></td>
<td><span data-ttu-id="fa3a5-879">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-879">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-880">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-880">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-881">178.44</span><span class="sxs-lookup"><span data-stu-id="fa3a5-881">178.44</span></span></td>
<td><span data-ttu-id="fa3a5-882">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-883">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-883">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-884">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-884">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-885">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-885">10001</span></span></td>
<td><span data-ttu-id="fa3a5-886">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-886">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-887">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-887">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-888">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="fa3a5-888">-5,982.83</span></span></td>
<td><span data-ttu-id="fa3a5-889">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-890">Prod 1</span></span></td>
<td><span data-ttu-id="fa3a5-891">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-891">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-892">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-892">10001</span></span></td>
<td><span data-ttu-id="fa3a5-893">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-893">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-894">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-894">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="fa3a5-895">4,487.12</span></span></td>
<td><span data-ttu-id="fa3a5-896">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-897">Prod 2</span></span></td>
<td><span data-ttu-id="fa3a5-898">Produit 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-898">Product 2</span></span></td>
<td><span data-ttu-id="fa3a5-899">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-899">10001</span></span></td>
<td><span data-ttu-id="fa3a5-900">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-900">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-901">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-901">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="fa3a5-902">1,495.71</span></span></td>
<td><span data-ttu-id="fa3a5-903">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-904">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-904">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-905">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-905">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-906">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-906">10001</span></span></td>
<td><span data-ttu-id="fa3a5-907">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-907">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-908">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-908">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="fa3a5-909">-286.25</span></span></td>
<td><span data-ttu-id="fa3a5-910">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-911">Prod 1</span></span></td>
<td><span data-ttu-id="fa3a5-912">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-912">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-913">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-913">10001</span></span></td>
<td><span data-ttu-id="fa3a5-914">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-914">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-915">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-915">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-916">241.05</span><span class="sxs-lookup"><span data-stu-id="fa3a5-916">241.05</span></span></td>
<td><span data-ttu-id="fa3a5-917">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-918">Prod 2</span></span></td>
<td><span data-ttu-id="fa3a5-919">Produit 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-919">Product 2</span></span></td>
<td><span data-ttu-id="fa3a5-920">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-920">10001</span></span></td>
<td><span data-ttu-id="fa3a5-921">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-921">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-922">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-922">Fixed cost</span></span></td>
<td><span data-ttu-id="fa3a5-923">45.20</span><span class="sxs-lookup"><span data-stu-id="fa3a5-923">45.20</span></span></td>
<td><span data-ttu-id="fa3a5-924">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-925">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-925">CC003</span></span></td>
<td><span data-ttu-id="fa3a5-926">Assemblage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-926">Assembly</span></span></td>
<td><span data-ttu-id="fa3a5-927">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-927">10001</span></span></td>
<td><span data-ttu-id="fa3a5-928">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-928">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-929">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-929">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-930">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="fa3a5-930">-2,977.17</span></span></td>
<td><span data-ttu-id="fa3a5-931">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-932">Prod 1</span></span></td>
<td><span data-ttu-id="fa3a5-933">Produit 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-933">Product 1</span></span></td>
<td><span data-ttu-id="fa3a5-934">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-934">10001</span></span></td>
<td><span data-ttu-id="fa3a5-935">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-935">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-936">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-936">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="fa3a5-937">2,507.09</span></span></td>
<td><span data-ttu-id="fa3a5-938">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa3a5-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-939">Prod 2</span></span></td>
<td><span data-ttu-id="fa3a5-940">Produit 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-940">Product 2</span></span></td>
<td><span data-ttu-id="fa3a5-941">10001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-941">10001</span></span></td>
<td><span data-ttu-id="fa3a5-942">Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-942">Electricity</span></span></td>
<td><span data-ttu-id="fa3a5-943">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-943">Variable cost</span></span></td>
<td><span data-ttu-id="fa3a5-944">470.08</span><span class="sxs-lookup"><span data-stu-id="fa3a5-944">470.08</span></span></td>
<td><span data-ttu-id="fa3a5-945">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="fa3a5-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="fa3a5-946">Conclusion</span><span class="sxs-lookup"><span data-stu-id="fa3a5-946">Conclusion</span></span>
<span data-ttu-id="fa3a5-947">Dans la comptabilité financière, un coût de 10 000,00 pour l'électricité est imputé sur un ID de centre de coût fictif.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="fa3a5-948">Par conséquent, les comptables sauront que ce coût doit être affecté.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="fa3a5-949">Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l'organisation, selon les stratégies et les règles qui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="fa3a5-950">Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="fa3a5-951">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="fa3a5-952">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="fa3a5-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="fa3a5-953">Total</span><span class="sxs-lookup"><span data-stu-id="fa3a5-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="fa3a5-954">CC099</span><span class="sxs-lookup"><span data-stu-id="fa3a5-954">CC099</span></span></th>
<th><span data-ttu-id="fa3a5-955">CC001</span><span class="sxs-lookup"><span data-stu-id="fa3a5-955">CC001</span></span></th>
<th><span data-ttu-id="fa3a5-956">CC002</span><span class="sxs-lookup"><span data-stu-id="fa3a5-956">CC002</span></span></th>
<th><span data-ttu-id="fa3a5-957">CC003</span><span class="sxs-lookup"><span data-stu-id="fa3a5-957">CC003</span></span></th>
<th><span data-ttu-id="fa3a5-958">CC004</span><span class="sxs-lookup"><span data-stu-id="fa3a5-958">CC004</span></span></th>
<th><span data-ttu-id="fa3a5-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-959">Proj 1</span></span></th>
<th><span data-ttu-id="fa3a5-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-960">Proj 2</span></span></th>
<th><span data-ttu-id="fa3a5-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fa3a5-961">Prod 1</span></span></th>
<th><span data-ttu-id="fa3a5-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fa3a5-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="fa3a5-963">10001 Électricité</span><span class="sxs-lookup"><span data-stu-id="fa3a5-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="fa3a5-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="fa3a5-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="fa3a5-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="fa3a5-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="fa3a5-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="fa3a5-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="fa3a5-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="fa3a5-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="fa3a5-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="fa3a5-973">Non classifié</span><span class="sxs-lookup"><span data-stu-id="fa3a5-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-974">0,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="fa3a5-975">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="fa3a5-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-976">0,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-977">0,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-978">0,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-979">0,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-980">0,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-981">776.36</span><span class="sxs-lookup"><span data-stu-id="fa3a5-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-982">223.64</span><span class="sxs-lookup"><span data-stu-id="fa3a5-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-983"><strong>1 000,00</strong></span><span class="sxs-lookup"><span data-stu-id="fa3a5-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="fa3a5-984">Coût variable</span><span class="sxs-lookup"><span data-stu-id="fa3a5-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-985">000</span><span class="sxs-lookup"><span data-stu-id="fa3a5-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-986">0,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-987">0,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-988">0,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-989">0,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-990">30,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-991">10,00</span><span class="sxs-lookup"><span data-stu-id="fa3a5-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="fa3a5-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="fa3a5-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fa3a5-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="fa3a5-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="fa3a5-995">Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="fa3a5-996">Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l'organisation.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="fa3a5-997">Autrement dit, les objets de coût de plus bas niveau supportent le coût.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="fa3a5-998">Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="fa3a5-999">Pour plus d'informations, voir la stratégie de repositionnement des coûts.</span><span class="sxs-lookup"><span data-stu-id="fa3a5-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="fa3a5-1000">(Notez que cette rubrique n'est pas complète et sera bientôt mise à jour.)</span><span class="sxs-lookup"><span data-stu-id="fa3a5-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




