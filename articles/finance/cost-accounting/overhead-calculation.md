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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 954e0669c3d24bcc20fe667c22b7dcc367aba1e7
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770802"
---
# <a name="overhead-calculation"></a><span data-ttu-id="5705b-103">Calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="5705b-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5705b-104">Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="5705b-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="5705b-105">Définition des termes</span><span class="sxs-lookup"><span data-stu-id="5705b-105">Term definition</span></span>
---------------

<span data-ttu-id="5705b-106">Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique.</span><span class="sxs-lookup"><span data-stu-id="5705b-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="5705b-107">Les frais généraux permettent essentiellement l'identification des activités rémunératrices.</span><span class="sxs-lookup"><span data-stu-id="5705b-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="5705b-108">Voici quelques exemples de frais généraux :</span><span class="sxs-lookup"><span data-stu-id="5705b-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="5705b-109">Loyer</span><span class="sxs-lookup"><span data-stu-id="5705b-109">Rent</span></span>
-   <span data-ttu-id="5705b-110">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-110">Electricity</span></span>
-   <span data-ttu-id="5705b-111">Salaires administratifs</span><span class="sxs-lookup"><span data-stu-id="5705b-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="5705b-112">Vue d'ensemble du calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="5705b-112">Overhead calculation overview</span></span>
<span data-ttu-id="5705b-113">Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l'ordre correct.</span><span class="sxs-lookup"><span data-stu-id="5705b-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="5705b-114">Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées.</span><span class="sxs-lookup"><span data-stu-id="5705b-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="5705b-115">Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions.</span><span class="sxs-lookup"><span data-stu-id="5705b-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="5705b-116">Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable.</span><span class="sxs-lookup"><span data-stu-id="5705b-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="5705b-117">Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="5705b-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="5705b-118">L'ID de version unique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="5705b-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="5705b-119">Type de version</span><span class="sxs-lookup"><span data-stu-id="5705b-119">Version type</span></span>
-   <span data-ttu-id="5705b-120">Date et heure</span><span class="sxs-lookup"><span data-stu-id="5705b-120">Date and time</span></span>
-   <span data-ttu-id="5705b-121">Comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="5705b-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="5705b-122">Exercice</span><span class="sxs-lookup"><span data-stu-id="5705b-122">Fiscal year</span></span>
-   <span data-ttu-id="5705b-123">Période fiscale</span><span class="sxs-lookup"><span data-stu-id="5705b-123">Fiscal period</span></span>

<span data-ttu-id="5705b-124">Le calcul des frais généraux est effectué indépendamment de la version.</span><span class="sxs-lookup"><span data-stu-id="5705b-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="5705b-125">Par conséquent, vous pouvez calculer la version de budget avant la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="5705b-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="5705b-126">Le calcul des frais généraux comporte quatre étapes, comme le montre l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="5705b-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="5705b-127">Dans chaque étape, un en-tête de journal avec des entrées de journal est créé.</span><span class="sxs-lookup"><span data-stu-id="5705b-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="5705b-128">Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul.</span><span class="sxs-lookup"><span data-stu-id="5705b-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="5705b-129">Les stratégies et les règles s'appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie.</span><span class="sxs-lookup"><span data-stu-id="5705b-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="5705b-130">Par conséquent, vous disposez toujours d'une traçabilité complète.</span><span class="sxs-lookup"><span data-stu-id="5705b-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="5705b-131">[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="5705b-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="5705b-132">Calculer et affecter les frais généraux Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="5705b-133">Dans la comptabilité financière, certaines coûts, tels que l'électricité, sont enregistrés comme montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="5705b-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="5705b-134">Par conséquent, l'analyse détaillée n'est pas fournie pour le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="5705b-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="5705b-135">Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l'organisation, les coûts doivent suivre les unités organisationnelles.</span><span class="sxs-lookup"><span data-stu-id="5705b-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="5705b-136">Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste.</span><span class="sxs-lookup"><span data-stu-id="5705b-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="5705b-137">Dans la comptabilité, le coût de l'électricité peut être validé comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5705b-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5705b-138">Date comptable</span><span class="sxs-lookup"><span data-stu-id="5705b-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-139">Centre de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-140">Compte principal</span><span class="sxs-lookup"><span data-stu-id="5705b-140">Main account</span></span></th>
<th><span data-ttu-id="5705b-141">Montant en devise comptable</span><span class="sxs-lookup"><span data-stu-id="5705b-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-142">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="5705b-143">CC099</span><span class="sxs-lookup"><span data-stu-id="5705b-143">CC099</span></span></td>
<td><span data-ttu-id="5705b-144">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="5705b-144">Default cost center</span></span></td>
<td><span data-ttu-id="5705b-145">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-145">10001</span></span></td>
<td><span data-ttu-id="5705b-146">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-146">Electricity</span></span></td>
<td><span data-ttu-id="5705b-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="5705b-148">Étape 1 : Traiter le calcul du comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="5705b-149">Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="5705b-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="5705b-150">Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.</span><span class="sxs-lookup"><span data-stu-id="5705b-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="5705b-151">Définir la règle de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-151">Define the cost behavior rule</span></span>

<span data-ttu-id="5705b-152">Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation.</span><span class="sxs-lookup"><span data-stu-id="5705b-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="5705b-153">Les factures d'électricité correspondent souvent à cette définition.</span><span class="sxs-lookup"><span data-stu-id="5705b-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="5705b-154">Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH).</span><span class="sxs-lookup"><span data-stu-id="5705b-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="5705b-155">Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :</span><span class="sxs-lookup"><span data-stu-id="5705b-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="5705b-156">Montant fixe 1 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="5705b-157">0 &lt;= 1 000,00 = Fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="5705b-158">1 000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="5705b-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="5705b-159">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="5705b-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5705b-160">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="5705b-160">Journal</span></span></th>
<th><span data-ttu-id="5705b-161">Type de journal</span><span class="sxs-lookup"><span data-stu-id="5705b-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5705b-162">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="5705b-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5705b-163">Version</span><span class="sxs-lookup"><span data-stu-id="5705b-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-164">00001</span><span class="sxs-lookup"><span data-stu-id="5705b-164">00001</span></span></td>
<td><span data-ttu-id="5705b-165">Journal de calcul de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="5705b-166">Exercice</span><span class="sxs-lookup"><span data-stu-id="5705b-166">Fiscal</span></span></td>
<td><span data-ttu-id="5705b-167">2017</span><span class="sxs-lookup"><span data-stu-id="5705b-167">2017</span></span></td>
<td><span data-ttu-id="5705b-168">Période 1</span><span class="sxs-lookup"><span data-stu-id="5705b-168">Period 1</span></span></td>
<td><span data-ttu-id="5705b-169">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="5705b-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5705b-170">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="5705b-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5705b-171">Date comptable</span><span class="sxs-lookup"><span data-stu-id="5705b-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-172">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-173">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-173">Cost element</span></span></th>
<th><span data-ttu-id="5705b-174">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-174">Cost behavior</span></span></th>
<th><span data-ttu-id="5705b-175">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-176">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="5705b-177">CC099</span><span class="sxs-lookup"><span data-stu-id="5705b-177">CC099</span></span></td>
<td><span data-ttu-id="5705b-178">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="5705b-178">Default cost center</span></span></td>
<td><span data-ttu-id="5705b-179">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-179">10001</span></span></td>
<td><span data-ttu-id="5705b-180">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-180">Electricity</span></span></td>
<td><span data-ttu-id="5705b-181">Non classifié</span><span class="sxs-lookup"><span data-stu-id="5705b-181">Unclassified</span></span></td>
<td><span data-ttu-id="5705b-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5705b-183">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-184">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-185">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-185">Cost element</span></span></th>
<th><span data-ttu-id="5705b-186">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-186">Cost behavior</span></span></th>
<th><span data-ttu-id="5705b-187">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-187">Amount</span></span></th>
<th><span data-ttu-id="5705b-188">Date comptable</span><span class="sxs-lookup"><span data-stu-id="5705b-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-189">CC099</span><span class="sxs-lookup"><span data-stu-id="5705b-189">CC099</span></span></td>
<td><span data-ttu-id="5705b-190">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="5705b-190">Default cost center</span></span></td>
<td><span data-ttu-id="5705b-191">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-191">10001</span></span></td>
<td><span data-ttu-id="5705b-192">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-192">Electricity</span></span></td>
<td><span data-ttu-id="5705b-193">Non classifié</span><span class="sxs-lookup"><span data-stu-id="5705b-193">Unclassified</span></span></td>
<td><span data-ttu-id="5705b-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-194">10,000.00</span></span></td>
<td><span data-ttu-id="5705b-195">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-196">CC099</span><span class="sxs-lookup"><span data-stu-id="5705b-196">CC099</span></span></td>
<td><span data-ttu-id="5705b-197">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="5705b-197">Default cost center</span></span></td>
<td><span data-ttu-id="5705b-198">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-198">10001</span></span></td>
<td><span data-ttu-id="5705b-199">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-199">Electricity</span></span></td>
<td><span data-ttu-id="5705b-200">Non classifié</span><span class="sxs-lookup"><span data-stu-id="5705b-200">Unclassified</span></span></td>
<td><span data-ttu-id="5705b-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-201">-10,000.00</span></span></td>
<td><span data-ttu-id="5705b-202">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-203">CC099</span><span class="sxs-lookup"><span data-stu-id="5705b-203">CC099</span></span></td>
<td><span data-ttu-id="5705b-204">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="5705b-204">Default cost center</span></span></td>
<td><span data-ttu-id="5705b-205">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-205">10001</span></span></td>
<td><span data-ttu-id="5705b-206">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-206">Electricity</span></span></td>
<td><span data-ttu-id="5705b-207">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-207">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-208">1,000.00</span></span></td>
<td><span data-ttu-id="5705b-209">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-210">CC099</span><span class="sxs-lookup"><span data-stu-id="5705b-210">CC099</span></span></td>
<td><span data-ttu-id="5705b-211">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="5705b-211">Default cost center</span></span></td>
<td><span data-ttu-id="5705b-212">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-212">10001</span></span></td>
<td><span data-ttu-id="5705b-213">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-213">Electricity</span></span></td>
<td><span data-ttu-id="5705b-214">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-214">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-215">9 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-215">9,000.00</span></span></td>
<td><span data-ttu-id="5705b-216">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-217">Pour plus d'informations, voir [Créer et affecter une stratégie de comportement de coûts à une unité de contrôle des coûts](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="5705b-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="5705b-218">Étape 2 : Traiter le calcul de distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="5705b-219">La distribution des coûts est utilisée pour redistribuer le coût d'un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée.</span><span class="sxs-lookup"><span data-stu-id="5705b-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="5705b-220">La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l'élément de coût principal du coût d'origine.</span><span class="sxs-lookup"><span data-stu-id="5705b-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="5705b-221">Définir la règle de distribution de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-221">Define the cost distribution rule</span></span>

<span data-ttu-id="5705b-222">Dans la comptabilité financière, les coûts d'électricité sont souvent enregistrés comme un montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="5705b-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="5705b-223">Dans le Contrôle de gestion, cette approche n'est pas assez détaillée.</span><span class="sxs-lookup"><span data-stu-id="5705b-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="5705b-224">Le coût variable doit être attribué aux différents objets de coûts sur une base juste.</span><span class="sxs-lookup"><span data-stu-id="5705b-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="5705b-225">La base de répartition la plus logique est la consommation de l'électricité (KWH).</span><span class="sxs-lookup"><span data-stu-id="5705b-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="5705b-226">Un membre de dimension statistique nommé Électricité est créé, et la consommation d'électricité est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="5705b-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="5705b-227">Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="5705b-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-228">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-228">Cost object</span></span></th>
<th><span data-ttu-id="5705b-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="5705b-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-230">CC001</span><span class="sxs-lookup"><span data-stu-id="5705b-230">CC001</span></span></td>
<td><span data-ttu-id="5705b-231">RH</span><span class="sxs-lookup"><span data-stu-id="5705b-231">HR</span></span></td>
<td><span data-ttu-id="5705b-232">1 000</span><span class="sxs-lookup"><span data-stu-id="5705b-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-233">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-233">CC002</span></span></td>
<td><span data-ttu-id="5705b-234">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-234">Finance</span></span></td>
<td><span data-ttu-id="5705b-235">6 000</span><span class="sxs-lookup"><span data-stu-id="5705b-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-236">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-236">CC003</span></span></td>
<td><span data-ttu-id="5705b-237">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-237">Assembly</span></span></td>
<td><span data-ttu-id="5705b-238">0</span><span class="sxs-lookup"><span data-stu-id="5705b-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-239">Le tableau suivant illustre le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="5705b-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-240">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-240">Cost object</span></span></th>
<th><span data-ttu-id="5705b-241">Ampleur</span><span class="sxs-lookup"><span data-stu-id="5705b-241">Magnitude</span></span></th>
<th><span data-ttu-id="5705b-242">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="5705b-242">Allocation factor</span></span></th>
<th><span data-ttu-id="5705b-243">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-244">CC001</span><span class="sxs-lookup"><span data-stu-id="5705b-244">CC001</span></span></td>
<td><span data-ttu-id="5705b-245">RH</span><span class="sxs-lookup"><span data-stu-id="5705b-245">HR</span></span></td>
<td><span data-ttu-id="5705b-246">1 000</span><span class="sxs-lookup"><span data-stu-id="5705b-246">1,000</span></span></td>
<td><span data-ttu-id="5705b-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5705b-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="5705b-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-249">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-249">CC002</span></span></td>
<td><span data-ttu-id="5705b-250">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-250">Finance</span></span></td>
<td><span data-ttu-id="5705b-251">6 000</span><span class="sxs-lookup"><span data-stu-id="5705b-251">6,000</span></span></td>
<td><span data-ttu-id="5705b-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5705b-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="5705b-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-254">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-254">CC003</span></span></td>
<td><span data-ttu-id="5705b-255">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-255">Assembly</span></span></td>
<td><span data-ttu-id="5705b-256">0</span><span class="sxs-lookup"><span data-stu-id="5705b-256">0</span></span></td>
<td><span data-ttu-id="5705b-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5705b-258">0,00</span><span class="sxs-lookup"><span data-stu-id="5705b-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-259">Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l'électricité.</span><span class="sxs-lookup"><span data-stu-id="5705b-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="5705b-260">Vous pouvez obtenir ce résultat à l'aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="5705b-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-261">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-261">Cost object</span></span></th>
<th><span data-ttu-id="5705b-262">Formule</span><span class="sxs-lookup"><span data-stu-id="5705b-262">Formula</span></span></th>
<th><span data-ttu-id="5705b-263">Ampleur</span><span class="sxs-lookup"><span data-stu-id="5705b-263">Magnitude</span></span></th>
<th><span data-ttu-id="5705b-264">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="5705b-264">Allocation factor</span></span></th>
<th><span data-ttu-id="5705b-265">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-266">CC001</span><span class="sxs-lookup"><span data-stu-id="5705b-266">CC001</span></span></td>
<td><span data-ttu-id="5705b-267">RH</span><span class="sxs-lookup"><span data-stu-id="5705b-267">HR</span></span></td>
<td><span data-ttu-id="5705b-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="5705b-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5705b-269">1</span><span class="sxs-lookup"><span data-stu-id="5705b-269">1</span></span></td>
<td><span data-ttu-id="5705b-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5705b-271">500,00</span><span class="sxs-lookup"><span data-stu-id="5705b-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-272">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-272">CC002</span></span></td>
<td><span data-ttu-id="5705b-273">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-273">Finance</span></span></td>
<td><span data-ttu-id="5705b-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="5705b-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5705b-275">1</span><span class="sxs-lookup"><span data-stu-id="5705b-275">1</span></span></td>
<td><span data-ttu-id="5705b-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5705b-277">500,00</span><span class="sxs-lookup"><span data-stu-id="5705b-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-278">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-278">CC003</span></span></td>
<td><span data-ttu-id="5705b-279">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-279">Assembly</span></span></td>
<td><span data-ttu-id="5705b-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="5705b-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5705b-281">0</span><span class="sxs-lookup"><span data-stu-id="5705b-281">0</span></span></td>
<td><span data-ttu-id="5705b-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5705b-283">0,00</span><span class="sxs-lookup"><span data-stu-id="5705b-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="5705b-284">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="5705b-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5705b-285">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="5705b-285">Journal</span></span></th>
<th><span data-ttu-id="5705b-286">Type de journal</span><span class="sxs-lookup"><span data-stu-id="5705b-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5705b-287">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="5705b-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5705b-288">Version</span><span class="sxs-lookup"><span data-stu-id="5705b-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-289">00002</span><span class="sxs-lookup"><span data-stu-id="5705b-289">00002</span></span></td>
<td><span data-ttu-id="5705b-290">Journal de calcul de la distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="5705b-291">Exercice</span><span class="sxs-lookup"><span data-stu-id="5705b-291">Fiscal</span></span></td>
<td><span data-ttu-id="5705b-292">2017</span><span class="sxs-lookup"><span data-stu-id="5705b-292">2017</span></span></td>
<td><span data-ttu-id="5705b-293">Période 1</span><span class="sxs-lookup"><span data-stu-id="5705b-293">Period 1</span></span></td>
<td><span data-ttu-id="5705b-294">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="5705b-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5705b-295">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="5705b-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5705b-296">Date comptable</span><span class="sxs-lookup"><span data-stu-id="5705b-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-297">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-298">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-298">Cost element</span></span></th>
<th><span data-ttu-id="5705b-299">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-299">Cost behavior</span></span></th>
<th><span data-ttu-id="5705b-300">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-301">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-302">CC099</span><span class="sxs-lookup"><span data-stu-id="5705b-302">CC099</span></span></td>
<td><span data-ttu-id="5705b-303">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="5705b-303">Default cost center</span></span></td>
<td><span data-ttu-id="5705b-304">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-304">10001</span></span></td>
<td><span data-ttu-id="5705b-305">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-305">Electricity</span></span></td>
<td><span data-ttu-id="5705b-306">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-306">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-308">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-309">CC099</span><span class="sxs-lookup"><span data-stu-id="5705b-309">CC099</span></span></td>
<td><span data-ttu-id="5705b-310">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="5705b-310">Default cost center</span></span></td>
<td><span data-ttu-id="5705b-311">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-311">10001</span></span></td>
<td><span data-ttu-id="5705b-312">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-312">Electricity</span></span></td>
<td><span data-ttu-id="5705b-313">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-313">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-314">9 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5705b-315">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-316">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-317">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-317">Cost element</span></span></th>
<th><span data-ttu-id="5705b-318">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-318">Cost behavior</span></span></th>
<th><span data-ttu-id="5705b-319">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-319">Amount</span></span></th>
<th><span data-ttu-id="5705b-320">Date comptable</span><span class="sxs-lookup"><span data-stu-id="5705b-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-321">CC099</span><span class="sxs-lookup"><span data-stu-id="5705b-321">CC099</span></span></td>
<td><span data-ttu-id="5705b-322">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="5705b-322">Default cost center</span></span></td>
<td><span data-ttu-id="5705b-323">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-323">10001</span></span></td>
<td><span data-ttu-id="5705b-324">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-324">Electricity</span></span></td>
<td><span data-ttu-id="5705b-325">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-325">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-326">-1,000.00</span></span></td>
<td><span data-ttu-id="5705b-327">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-328">CC001</span><span class="sxs-lookup"><span data-stu-id="5705b-328">CC001</span></span></td>
<td><span data-ttu-id="5705b-329">RH</span><span class="sxs-lookup"><span data-stu-id="5705b-329">HR</span></span></td>
<td><span data-ttu-id="5705b-330">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-330">10001</span></span></td>
<td><span data-ttu-id="5705b-331">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-331">Electricity</span></span></td>
<td><span data-ttu-id="5705b-332">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-332">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-333">500,00</span><span class="sxs-lookup"><span data-stu-id="5705b-333">500.00</span></span></td>
<td><span data-ttu-id="5705b-334">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-335">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-335">CC002</span></span></td>
<td><span data-ttu-id="5705b-336">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-336">Finance</span></span></td>
<td><span data-ttu-id="5705b-337">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-337">10001</span></span></td>
<td><span data-ttu-id="5705b-338">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-338">Electricity</span></span></td>
<td><span data-ttu-id="5705b-339">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-339">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-340">500,00</span><span class="sxs-lookup"><span data-stu-id="5705b-340">500.00</span></span></td>
<td><span data-ttu-id="5705b-341">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-342">CC099</span><span class="sxs-lookup"><span data-stu-id="5705b-342">CC099</span></span></td>
<td><span data-ttu-id="5705b-343">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="5705b-343">Default cost center</span></span></td>
<td><span data-ttu-id="5705b-344">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-344">10001</span></span></td>
<td><span data-ttu-id="5705b-345">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-345">Electricity</span></span></td>
<td><span data-ttu-id="5705b-346">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-346">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="5705b-347">-9,000.00</span></span></td>
<td><span data-ttu-id="5705b-348">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-349">CC001</span><span class="sxs-lookup"><span data-stu-id="5705b-349">CC001</span></span></td>
<td><span data-ttu-id="5705b-350">RH</span><span class="sxs-lookup"><span data-stu-id="5705b-350">HR</span></span></td>
<td><span data-ttu-id="5705b-351">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-351">10001</span></span></td>
<td><span data-ttu-id="5705b-352">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-352">Electricity</span></span></td>
<td><span data-ttu-id="5705b-353">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-353">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="5705b-354">1,285.71</span></span></td>
<td><span data-ttu-id="5705b-355">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-356">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-356">CC002</span></span></td>
<td><span data-ttu-id="5705b-357">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-357">Finance</span></span></td>
<td><span data-ttu-id="5705b-358">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-358">10001</span></span></td>
<td><span data-ttu-id="5705b-359">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-359">Electricity</span></span></td>
<td><span data-ttu-id="5705b-360">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-360">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="5705b-361">7,714.29</span></span></td>
<td><span data-ttu-id="5705b-362">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-363">Pour plus d'informations, voir [Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="5705b-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="5705b-364">Étape 3 : Traitement du calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="5705b-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="5705b-365">Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût.</span><span class="sxs-lookup"><span data-stu-id="5705b-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="5705b-366">Les frais sont basés sur un taux de coût prédéterminé et l'ampleur de la base d'affectation de répartition.</span><span class="sxs-lookup"><span data-stu-id="5705b-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="5705b-367">Définition du taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="5705b-367">Define the overhead rate</span></span>

<span data-ttu-id="5705b-368">L'objet de coût CC001 HR contribue à un ensemble de projets internes.</span><span class="sxs-lookup"><span data-stu-id="5705b-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="5705b-369">Un membre de dimension statistique nommé Projets HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="5705b-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-370">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-370">Cost object</span></span></th>
<th><span data-ttu-id="5705b-371">Heures</span><span class="sxs-lookup"><span data-stu-id="5705b-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5705b-372">Proj 1</span></span></td>
<td><span data-ttu-id="5705b-373">Projet 1</span><span class="sxs-lookup"><span data-stu-id="5705b-373">Project 1</span></span></td>
<td><span data-ttu-id="5705b-374">3</span><span class="sxs-lookup"><span data-stu-id="5705b-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5705b-375">Proj 2</span></span></td>
<td><span data-ttu-id="5705b-376">Projet 2</span><span class="sxs-lookup"><span data-stu-id="5705b-376">Project 2</span></span></td>
<td><span data-ttu-id="5705b-377">1</span><span class="sxs-lookup"><span data-stu-id="5705b-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-378">Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.</span><span class="sxs-lookup"><span data-stu-id="5705b-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-379">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-379">Cost object</span></span></th>
<th><span data-ttu-id="5705b-380">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-380">Cost element</span></span></th>
<th><span data-ttu-id="5705b-381">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-381">Cost behavior</span></span></th>
<th><span data-ttu-id="5705b-382">Unités</span><span class="sxs-lookup"><span data-stu-id="5705b-382">Units</span></span></th>
<th><span data-ttu-id="5705b-383">Taux</span><span class="sxs-lookup"><span data-stu-id="5705b-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-384">CC001</span><span class="sxs-lookup"><span data-stu-id="5705b-384">CC001</span></span></td>
<td><span data-ttu-id="5705b-385">RH</span><span class="sxs-lookup"><span data-stu-id="5705b-385">HR</span></span></td>
<td><span data-ttu-id="5705b-386">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-386">10001</span></span></td>
<td><span data-ttu-id="5705b-387">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-387">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-388">1</span><span class="sxs-lookup"><span data-stu-id="5705b-388">1</span></span></td>
<td><span data-ttu-id="5705b-389">10</span><span class="sxs-lookup"><span data-stu-id="5705b-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-390">Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="5705b-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-391">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-391">Cost object</span></span></th>
<th><span data-ttu-id="5705b-392">Ampleur</span><span class="sxs-lookup"><span data-stu-id="5705b-392">Magnitude</span></span></th>
<th><span data-ttu-id="5705b-393">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-393">Cost element</span></span></th>
<th><span data-ttu-id="5705b-394">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="5705b-394">Allocation factor</span></span></th>
<th><span data-ttu-id="5705b-395">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5705b-396">Proj 1</span></span></td>
<td><span data-ttu-id="5705b-397">Projet 1</span><span class="sxs-lookup"><span data-stu-id="5705b-397">Project 1</span></span></td>
<td><span data-ttu-id="5705b-398">3</span><span class="sxs-lookup"><span data-stu-id="5705b-398">3</span></span></td>
<td><span data-ttu-id="5705b-399">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-399">10001</span></span></td>
<td><span data-ttu-id="5705b-400">(3 ÷ 1) × 10m00</span><span class="sxs-lookup"><span data-stu-id="5705b-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="5705b-401">30,00</span><span class="sxs-lookup"><span data-stu-id="5705b-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5705b-402">Proj 2</span></span></td>
<td><span data-ttu-id="5705b-403">Projet 2</span><span class="sxs-lookup"><span data-stu-id="5705b-403">Project 2</span></span></td>
<td><span data-ttu-id="5705b-404">1</span><span class="sxs-lookup"><span data-stu-id="5705b-404">1</span></span></td>
<td><span data-ttu-id="5705b-405">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-405">10001</span></span></td>
<td><span data-ttu-id="5705b-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="5705b-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="5705b-407">10,00</span><span class="sxs-lookup"><span data-stu-id="5705b-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="5705b-408">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="5705b-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5705b-409">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="5705b-409">Journal</span></span></th>
<th><span data-ttu-id="5705b-410">Type de journal</span><span class="sxs-lookup"><span data-stu-id="5705b-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5705b-411">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="5705b-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5705b-412">Version</span><span class="sxs-lookup"><span data-stu-id="5705b-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-413">00003</span><span class="sxs-lookup"><span data-stu-id="5705b-413">00003</span></span></td>
<td><span data-ttu-id="5705b-414">Journal de calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="5705b-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="5705b-415">Exercice</span><span class="sxs-lookup"><span data-stu-id="5705b-415">Fiscal</span></span></td>
<td><span data-ttu-id="5705b-416">2017</span><span class="sxs-lookup"><span data-stu-id="5705b-416">2017</span></span></td>
<td><span data-ttu-id="5705b-417">Période 1</span><span class="sxs-lookup"><span data-stu-id="5705b-417">Period 1</span></span></td>
<td><span data-ttu-id="5705b-418">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="5705b-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="5705b-419">Entrées du journal (pour le calcul du taux de frais généraux)</span><span class="sxs-lookup"><span data-stu-id="5705b-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5705b-420">Date comptable</span><span class="sxs-lookup"><span data-stu-id="5705b-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-421">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-421">Cost object</span></span></th>
<th><span data-ttu-id="5705b-422">Ampleur</span><span class="sxs-lookup"><span data-stu-id="5705b-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-423">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5705b-424">Proj 1</span></span></td>
<td><span data-ttu-id="5705b-425">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="5705b-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="5705b-426">3,00</span><span class="sxs-lookup"><span data-stu-id="5705b-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-427">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5705b-428">Proj 2</span></span></td>
<td><span data-ttu-id="5705b-429">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="5705b-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="5705b-430">1,00</span><span class="sxs-lookup"><span data-stu-id="5705b-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5705b-431">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-432">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-433">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-433">Cost element</span></span></th>
<th><span data-ttu-id="5705b-434">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-434">Cost behavior</span></span></th>
<th><span data-ttu-id="5705b-435">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-435">Amount</span></span></th>
<th><span data-ttu-id="5705b-436">Date comptable</span><span class="sxs-lookup"><span data-stu-id="5705b-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="5705b-437">CC0001</span></span></td>
<td><span data-ttu-id="5705b-438">RH</span><span class="sxs-lookup"><span data-stu-id="5705b-438">HR</span></span></td>
<td><span data-ttu-id="5705b-439">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-439">10001</span></span></td>
<td><span data-ttu-id="5705b-440">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-440">Electricity</span></span></td>
<td><span data-ttu-id="5705b-441">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-441">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="5705b-442">-30.00</span></span></td>
<td><span data-ttu-id="5705b-443">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5705b-444">Proj 1</span></span></td>
<td><span data-ttu-id="5705b-445">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="5705b-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="5705b-446">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-446">10001</span></span></td>
<td><span data-ttu-id="5705b-447">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-447">Electricity</span></span></td>
<td><span data-ttu-id="5705b-448">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-448">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-449">30,00</span><span class="sxs-lookup"><span data-stu-id="5705b-449">30.00</span></span></td>
<td><span data-ttu-id="5705b-450">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-451">CC001</span><span class="sxs-lookup"><span data-stu-id="5705b-451">CC001</span></span></td>
<td><span data-ttu-id="5705b-452">RH</span><span class="sxs-lookup"><span data-stu-id="5705b-452">HR</span></span></td>
<td><span data-ttu-id="5705b-453">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-453">10001</span></span></td>
<td><span data-ttu-id="5705b-454">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-454">Electricity</span></span></td>
<td><span data-ttu-id="5705b-455">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-455">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="5705b-456">-10.00</span></span></td>
<td><span data-ttu-id="5705b-457">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5705b-458">Proj 2</span></span></td>
<td><span data-ttu-id="5705b-459">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="5705b-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="5705b-460">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-460">10001</span></span></td>
<td><span data-ttu-id="5705b-461">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-461">Electricity</span></span></td>
<td><span data-ttu-id="5705b-462">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-462">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-463">10.00</span><span class="sxs-lookup"><span data-stu-id="5705b-463">10.00</span></span></td>
<td><span data-ttu-id="5705b-464">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-465">Pour plus d'informations, voir [Exécuter le calcul des frais généraux](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="5705b-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="5705b-466">Étape 4 : Traiter le calcul de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="5705b-467">La répartition est utilisée pour affecter le solde d'un objet de coût à d'autres objets de coût en appliquant une base de répartition.</span><span class="sxs-lookup"><span data-stu-id="5705b-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="5705b-468">Finance prend en charge la méthode de répartition réciproque.</span><span class="sxs-lookup"><span data-stu-id="5705b-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="5705b-469">Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés.</span><span class="sxs-lookup"><span data-stu-id="5705b-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="5705b-470">Le système détermine automatiquement l'ordre correct selon lequel exécuter les répartitions.</span><span class="sxs-lookup"><span data-stu-id="5705b-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="5705b-471">Le solde d'un objet de coût est réparti par une seule base de répartition.</span><span class="sxs-lookup"><span data-stu-id="5705b-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="5705b-472">Les répartitions entre plusieurs dimensions d'objets de coût et leurs membres respectifs sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="5705b-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="5705b-473">L'ordre de répartition est contrôlé par l'unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="5705b-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="5705b-474">[![Méthode réciproque](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="5705b-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="5705b-475">Définir la répartition de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-475">Define the cost allocation</span></span>

<span data-ttu-id="5705b-476">Voici un exemple simple expliquant comment suivre le flux du coût.</span><span class="sxs-lookup"><span data-stu-id="5705b-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="5705b-477">L'objet de coût CC001 HR contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="5705b-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="5705b-478">Un membre de dimension statistique nommé Services HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="5705b-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-479">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-479">Cost object</span></span></th>
<th><span data-ttu-id="5705b-480">Services HR</span><span class="sxs-lookup"><span data-stu-id="5705b-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-481">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-481">CC002</span></span></td>
<td><span data-ttu-id="5705b-482">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-482">Finance</span></span></td>
<td><span data-ttu-id="5705b-483">35</span><span class="sxs-lookup"><span data-stu-id="5705b-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-484">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-484">CC003</span></span></td>
<td><span data-ttu-id="5705b-485">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-485">Assembly</span></span></td>
<td><span data-ttu-id="5705b-486">55</span><span class="sxs-lookup"><span data-stu-id="5705b-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-487">CC004</span><span class="sxs-lookup"><span data-stu-id="5705b-487">CC004</span></span></td>
<td><span data-ttu-id="5705b-488">Emballage</span><span class="sxs-lookup"><span data-stu-id="5705b-488">Packaging</span></span></td>
<td><span data-ttu-id="5705b-489">10</span><span class="sxs-lookup"><span data-stu-id="5705b-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-490">L'objet de coût CC002 Finance contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="5705b-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="5705b-491">Un membre de dimension statistique nommé Services Finance est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="5705b-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-492">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-492">Cost object</span></span></th>
<th><span data-ttu-id="5705b-493">Services Finance</span><span class="sxs-lookup"><span data-stu-id="5705b-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-494">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-494">CC003</span></span></td>
<td><span data-ttu-id="5705b-495">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-495">Assembly</span></span></td>
<td><span data-ttu-id="5705b-496">65</span><span class="sxs-lookup"><span data-stu-id="5705b-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-497">CC004</span><span class="sxs-lookup"><span data-stu-id="5705b-497">CC004</span></span></td>
<td><span data-ttu-id="5705b-498">Emballage</span><span class="sxs-lookup"><span data-stu-id="5705b-498">Packaging</span></span></td>
<td><span data-ttu-id="5705b-499">35</span><span class="sxs-lookup"><span data-stu-id="5705b-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-500">L'objet de coût CC003 Assemblage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="5705b-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="5705b-501">Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="5705b-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-502">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-502">Cost object</span></span></th>
<th><span data-ttu-id="5705b-503">Services Assemblage (heures)</span><span class="sxs-lookup"><span data-stu-id="5705b-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-504">Prod 1</span></span></td>
<td><span data-ttu-id="5705b-505">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-505">Product 1</span></span></td>
<td><span data-ttu-id="5705b-506">60</span><span class="sxs-lookup"><span data-stu-id="5705b-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-507">Prod 2</span></span></td>
<td><span data-ttu-id="5705b-508">Produit 2</span><span class="sxs-lookup"><span data-stu-id="5705b-508">Product 2</span></span></td>
<td><span data-ttu-id="5705b-509">20</span><span class="sxs-lookup"><span data-stu-id="5705b-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-510">L'objet de coût CC004 Emballage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="5705b-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="5705b-511">Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="5705b-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-512">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-512">Cost object</span></span></th>
<th><span data-ttu-id="5705b-513">Services Emballage (heures)</span><span class="sxs-lookup"><span data-stu-id="5705b-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-514">Prod 1</span></span></td>
<td><span data-ttu-id="5705b-515">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-515">Product 1</span></span></td>
<td><span data-ttu-id="5705b-516">80</span><span class="sxs-lookup"><span data-stu-id="5705b-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-517">Prod 2</span></span></td>
<td><span data-ttu-id="5705b-518">Produit 2</span><span class="sxs-lookup"><span data-stu-id="5705b-518">Product 2</span></span></td>
<td><span data-ttu-id="5705b-519">15</span><span class="sxs-lookup"><span data-stu-id="5705b-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="5705b-520">Les mesures statistiques telles que les heures de production qu'un produit consomme peuvent être dérivées des données sources.</span><span class="sxs-lookup"><span data-stu-id="5705b-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="5705b-521">Pour plus d'informations, voir [Modèle de fournisseur de mesures statistiques](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="5705b-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="5705b-522">Le tableau suivant présente le résultat lorsque les services RH sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="5705b-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-523">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-523">Cost object</span></span></th>
<th><span data-ttu-id="5705b-524">Ampleur</span><span class="sxs-lookup"><span data-stu-id="5705b-524">Magnitude</span></span></th>
<th><span data-ttu-id="5705b-525">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="5705b-525">Allocation factor</span></span></th>
<th><span data-ttu-id="5705b-526">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-526">Amount</span></span></th>
<th><span data-ttu-id="5705b-527">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-528">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-528">CC002</span></span></td>
<td><span data-ttu-id="5705b-529">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-529">Finance</span></span></td>
<td><span data-ttu-id="5705b-530">35</span><span class="sxs-lookup"><span data-stu-id="5705b-530">35</span></span></td>
<td><span data-ttu-id="5705b-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="5705b-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5705b-532">175.00</span><span class="sxs-lookup"><span data-stu-id="5705b-532">175.00</span></span></td>
<td><span data-ttu-id="5705b-533">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-534">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-534">CC003</span></span></td>
<td><span data-ttu-id="5705b-535">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-535">Assembly</span></span></td>
<td><span data-ttu-id="5705b-536">55</span><span class="sxs-lookup"><span data-stu-id="5705b-536">55</span></span></td>
<td><span data-ttu-id="5705b-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="5705b-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5705b-538">275.00</span><span class="sxs-lookup"><span data-stu-id="5705b-538">275.00</span></span></td>
<td><span data-ttu-id="5705b-539">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-540">CC004</span><span class="sxs-lookup"><span data-stu-id="5705b-540">CC004</span></span></td>
<td><span data-ttu-id="5705b-541">Emballage</span><span class="sxs-lookup"><span data-stu-id="5705b-541">Packaging</span></span></td>
<td><span data-ttu-id="5705b-542">10</span><span class="sxs-lookup"><span data-stu-id="5705b-542">10</span></span></td>
<td><span data-ttu-id="5705b-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="5705b-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5705b-544">50,00</span><span class="sxs-lookup"><span data-stu-id="5705b-544">50.00</span></span></td>
<td><span data-ttu-id="5705b-545">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-546">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-546">CC002</span></span></td>
<td><span data-ttu-id="5705b-547">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-547">Finance</span></span></td>
<td><span data-ttu-id="5705b-548">35</span><span class="sxs-lookup"><span data-stu-id="5705b-548">35</span></span></td>
<td><span data-ttu-id="5705b-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="5705b-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5705b-550">436.00</span><span class="sxs-lookup"><span data-stu-id="5705b-550">436.00</span></span></td>
<td><span data-ttu-id="5705b-551">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-552">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-552">CC003</span></span></td>
<td><span data-ttu-id="5705b-553">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-553">Assembly</span></span></td>
<td><span data-ttu-id="5705b-554">55</span><span class="sxs-lookup"><span data-stu-id="5705b-554">55</span></span></td>
<td><span data-ttu-id="5705b-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="5705b-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5705b-556">685.14</span><span class="sxs-lookup"><span data-stu-id="5705b-556">685.14</span></span></td>
<td><span data-ttu-id="5705b-557">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-558">CC004</span><span class="sxs-lookup"><span data-stu-id="5705b-558">CC004</span></span></td>
<td><span data-ttu-id="5705b-559">Emballage</span><span class="sxs-lookup"><span data-stu-id="5705b-559">Packaging</span></span></td>
<td><span data-ttu-id="5705b-560">10</span><span class="sxs-lookup"><span data-stu-id="5705b-560">10</span></span></td>
<td><span data-ttu-id="5705b-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="5705b-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5705b-562">124.57</span><span class="sxs-lookup"><span data-stu-id="5705b-562">124.57</span></span></td>
<td><span data-ttu-id="5705b-563">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-564">Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="5705b-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-565">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-565">Cost object</span></span></th>
<th><span data-ttu-id="5705b-566">Ampleur</span><span class="sxs-lookup"><span data-stu-id="5705b-566">Magnitude</span></span></th>
<th><span data-ttu-id="5705b-567">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="5705b-567">Allocation factor</span></span></th>
<th><span data-ttu-id="5705b-568">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-568">Amount</span></span></th>
<th><span data-ttu-id="5705b-569">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-570">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-570">CC003</span></span></td>
<td><span data-ttu-id="5705b-571">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-571">Assembly</span></span></td>
<td><span data-ttu-id="5705b-572">65</span><span class="sxs-lookup"><span data-stu-id="5705b-572">65</span></span></td>
<td><span data-ttu-id="5705b-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="5705b-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="5705b-574">438.75</span><span class="sxs-lookup"><span data-stu-id="5705b-574">438.75</span></span></td>
<td><span data-ttu-id="5705b-575">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-576">CC004</span><span class="sxs-lookup"><span data-stu-id="5705b-576">CC004</span></span></td>
<td><span data-ttu-id="5705b-577">Emballage</span><span class="sxs-lookup"><span data-stu-id="5705b-577">Packaging</span></span></td>
<td><span data-ttu-id="5705b-578">35</span><span class="sxs-lookup"><span data-stu-id="5705b-578">35</span></span></td>
<td><span data-ttu-id="5705b-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="5705b-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="5705b-580">236.25</span><span class="sxs-lookup"><span data-stu-id="5705b-580">236.25</span></span></td>
<td><span data-ttu-id="5705b-581">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-582">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-582">CC003</span></span></td>
<td><span data-ttu-id="5705b-583">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-583">Assembly</span></span></td>
<td><span data-ttu-id="5705b-584">65</span><span class="sxs-lookup"><span data-stu-id="5705b-584">65</span></span></td>
<td><span data-ttu-id="5705b-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="5705b-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="5705b-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="5705b-586">5,297.69</span></span></td>
<td><span data-ttu-id="5705b-587">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-588">CC004</span><span class="sxs-lookup"><span data-stu-id="5705b-588">CC004</span></span></td>
<td><span data-ttu-id="5705b-589">Emballage</span><span class="sxs-lookup"><span data-stu-id="5705b-589">Packaging</span></span></td>
<td><span data-ttu-id="5705b-590">35</span><span class="sxs-lookup"><span data-stu-id="5705b-590">35</span></span></td>
<td><span data-ttu-id="5705b-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="5705b-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="5705b-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="5705b-592">2,852.60</span></span></td>
<td><span data-ttu-id="5705b-593">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-594">Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="5705b-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-595">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-595">Cost object</span></span></th>
<th><span data-ttu-id="5705b-596">Ampleur</span><span class="sxs-lookup"><span data-stu-id="5705b-596">Magnitude</span></span></th>
<th><span data-ttu-id="5705b-597">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="5705b-597">Allocation factor</span></span></th>
<th><span data-ttu-id="5705b-598">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-598">Amount</span></span></th>
<th><span data-ttu-id="5705b-599">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-600">Prod 1</span></span></td>
<td><span data-ttu-id="5705b-601">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-601">Product 1</span></span></td>
<td><span data-ttu-id="5705b-602">60</span><span class="sxs-lookup"><span data-stu-id="5705b-602">60</span></span></td>
<td><span data-ttu-id="5705b-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="5705b-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="5705b-604">535.31</span><span class="sxs-lookup"><span data-stu-id="5705b-604">535.31</span></span></td>
<td><span data-ttu-id="5705b-605">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-606">Prod 2</span></span></td>
<td><span data-ttu-id="5705b-607">Produit 2</span><span class="sxs-lookup"><span data-stu-id="5705b-607">Product 2</span></span></td>
<td><span data-ttu-id="5705b-608">20</span><span class="sxs-lookup"><span data-stu-id="5705b-608">20</span></span></td>
<td><span data-ttu-id="5705b-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="5705b-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="5705b-610">178.44</span><span class="sxs-lookup"><span data-stu-id="5705b-610">178.44</span></span></td>
<td><span data-ttu-id="5705b-611">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-612">Prod 1</span></span></td>
<td><span data-ttu-id="5705b-613">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-613">Product 1</span></span></td>
<td><span data-ttu-id="5705b-614">60</span><span class="sxs-lookup"><span data-stu-id="5705b-614">60</span></span></td>
<td><span data-ttu-id="5705b-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="5705b-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="5705b-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="5705b-616">4,487.12</span></span></td>
<td><span data-ttu-id="5705b-617">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-618">Prod 2</span></span></td>
<td><span data-ttu-id="5705b-619">Produit 2</span><span class="sxs-lookup"><span data-stu-id="5705b-619">Product 2</span></span></td>
<td><span data-ttu-id="5705b-620">20</span><span class="sxs-lookup"><span data-stu-id="5705b-620">20</span></span></td>
<td><span data-ttu-id="5705b-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="5705b-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="5705b-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="5705b-622">1,495.71</span></span></td>
<td><span data-ttu-id="5705b-623">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5705b-624">Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="5705b-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-625">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-625">Cost object</span></span></th>
<th><span data-ttu-id="5705b-626">Ampleur</span><span class="sxs-lookup"><span data-stu-id="5705b-626">Magnitude</span></span></th>
<th><span data-ttu-id="5705b-627">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="5705b-627">Allocation factor</span></span></th>
<th><span data-ttu-id="5705b-628">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-628">Amount</span></span></th>
<th><span data-ttu-id="5705b-629">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-630">Prod 1</span></span></td>
<td><span data-ttu-id="5705b-631">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-631">Product 1</span></span></td>
<td><span data-ttu-id="5705b-632">80</span><span class="sxs-lookup"><span data-stu-id="5705b-632">80</span></span></td>
<td><span data-ttu-id="5705b-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="5705b-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="5705b-634">241.05</span><span class="sxs-lookup"><span data-stu-id="5705b-634">241.05</span></span></td>
<td><span data-ttu-id="5705b-635">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-636">Prod 2</span></span></td>
<td><span data-ttu-id="5705b-637">Produit 2</span><span class="sxs-lookup"><span data-stu-id="5705b-637">Product 2</span></span></td>
<td><span data-ttu-id="5705b-638">15</span><span class="sxs-lookup"><span data-stu-id="5705b-638">15</span></span></td>
<td><span data-ttu-id="5705b-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="5705b-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="5705b-640">45.20</span><span class="sxs-lookup"><span data-stu-id="5705b-640">45.20</span></span></td>
<td><span data-ttu-id="5705b-641">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-642">Prod 1</span></span></td>
<td><span data-ttu-id="5705b-643">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-643">Product 1</span></span></td>
<td><span data-ttu-id="5705b-644">80</span><span class="sxs-lookup"><span data-stu-id="5705b-644">80</span></span></td>
<td><span data-ttu-id="5705b-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="5705b-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="5705b-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="5705b-646">2,507.09</span></span></td>
<td><span data-ttu-id="5705b-647">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-648">Prod 2</span></span></td>
<td><span data-ttu-id="5705b-649">Produit 2</span><span class="sxs-lookup"><span data-stu-id="5705b-649">Product 2</span></span></td>
<td><span data-ttu-id="5705b-650">15</span><span class="sxs-lookup"><span data-stu-id="5705b-650">15</span></span></td>
<td><span data-ttu-id="5705b-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="5705b-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="5705b-652">470.08</span><span class="sxs-lookup"><span data-stu-id="5705b-652">470.08</span></span></td>
<td><span data-ttu-id="5705b-653">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5705b-654">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="5705b-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5705b-655">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="5705b-655">Journal</span></span></th>
<th><span data-ttu-id="5705b-656">Type de journal</span><span class="sxs-lookup"><span data-stu-id="5705b-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5705b-657">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="5705b-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5705b-658">Version</span><span class="sxs-lookup"><span data-stu-id="5705b-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-659">00004</span><span class="sxs-lookup"><span data-stu-id="5705b-659">00004</span></span></td>
<td><span data-ttu-id="5705b-660">Journal de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="5705b-661">Exercice</span><span class="sxs-lookup"><span data-stu-id="5705b-661">Fiscal</span></span></td>
<td><span data-ttu-id="5705b-662">2017</span><span class="sxs-lookup"><span data-stu-id="5705b-662">2017</span></span></td>
<td><span data-ttu-id="5705b-663">Période 1</span><span class="sxs-lookup"><span data-stu-id="5705b-663">Period 1</span></span></td>
<td><span data-ttu-id="5705b-664">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="5705b-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="5705b-665">Lignes de journal</span><span class="sxs-lookup"><span data-stu-id="5705b-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5705b-666">Date comptable</span><span class="sxs-lookup"><span data-stu-id="5705b-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-667">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-668">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-668">Cost element</span></span></th>
<th><span data-ttu-id="5705b-669">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-669">Cost behavior</span></span></th>
<th><span data-ttu-id="5705b-670">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-671">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-672">CC001</span><span class="sxs-lookup"><span data-stu-id="5705b-672">CC001</span></span></td>
<td><span data-ttu-id="5705b-673">RH</span><span class="sxs-lookup"><span data-stu-id="5705b-673">HR</span></span></td>
<td><span data-ttu-id="5705b-674">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-674">10001</span></span></td>
<td><span data-ttu-id="5705b-675">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-675">Electricity</span></span></td>
<td><span data-ttu-id="5705b-676">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-676">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-677">500,00</span><span class="sxs-lookup"><span data-stu-id="5705b-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-678">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-679">CC001</span><span class="sxs-lookup"><span data-stu-id="5705b-679">CC001</span></span></td>
<td><span data-ttu-id="5705b-680">RH</span><span class="sxs-lookup"><span data-stu-id="5705b-680">HR</span></span></td>
<td><span data-ttu-id="5705b-681">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-681">10001</span></span></td>
<td><span data-ttu-id="5705b-682">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-682">Electricity</span></span></td>
<td><span data-ttu-id="5705b-683">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-683">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="5705b-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-685">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-686">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-686">CC002</span></span></td>
<td><span data-ttu-id="5705b-687">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-687">Finance</span></span></td>
<td><span data-ttu-id="5705b-688">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-688">10001</span></span></td>
<td><span data-ttu-id="5705b-689">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-689">Electricity</span></span></td>
<td><span data-ttu-id="5705b-690">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-690">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-691">675.00</span><span class="sxs-lookup"><span data-stu-id="5705b-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-692">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-693">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-693">CC002</span></span></td>
<td><span data-ttu-id="5705b-694">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-694">Finance</span></span></td>
<td><span data-ttu-id="5705b-695">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-695">10001</span></span></td>
<td><span data-ttu-id="5705b-696">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-696">Electricity</span></span></td>
<td><span data-ttu-id="5705b-697">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-697">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="5705b-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-699">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-700">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-700">CC003</span></span></td>
<td><span data-ttu-id="5705b-701">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-701">Assembly</span></span></td>
<td><span data-ttu-id="5705b-702">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-702">10001</span></span></td>
<td><span data-ttu-id="5705b-703">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-703">Electricity</span></span></td>
<td><span data-ttu-id="5705b-704">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-704">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-705">713.75</span><span class="sxs-lookup"><span data-stu-id="5705b-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-706">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-707">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-707">CC003</span></span></td>
<td><span data-ttu-id="5705b-708">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-708">Assembly</span></span></td>
<td><span data-ttu-id="5705b-709">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-709">10001</span></span></td>
<td><span data-ttu-id="5705b-710">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-710">Electricity</span></span></td>
<td><span data-ttu-id="5705b-711">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-711">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="5705b-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-713">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-714">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-714">CC003</span></span></td>
<td><span data-ttu-id="5705b-715">Emballage</span><span class="sxs-lookup"><span data-stu-id="5705b-715">Packaging</span></span></td>
<td><span data-ttu-id="5705b-716">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-716">10001</span></span></td>
<td><span data-ttu-id="5705b-717">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-717">Electricity</span></span></td>
<td><span data-ttu-id="5705b-718">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-718">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-719">286.25</span><span class="sxs-lookup"><span data-stu-id="5705b-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-720">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-721">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-721">CC003</span></span></td>
<td><span data-ttu-id="5705b-722">Emballage</span><span class="sxs-lookup"><span data-stu-id="5705b-722">Packaging</span></span></td>
<td><span data-ttu-id="5705b-723">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-723">10001</span></span></td>
<td><span data-ttu-id="5705b-724">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-724">Electricity</span></span></td>
<td><span data-ttu-id="5705b-725">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-725">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="5705b-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-727">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-728">Prod 1</span></span></td>
<td><span data-ttu-id="5705b-729">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-729">Product 1</span></span></td>
<td><span data-ttu-id="5705b-730">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-730">10001</span></span></td>
<td><span data-ttu-id="5705b-731">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-731">Electricity</span></span></td>
<td><span data-ttu-id="5705b-732">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-732">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-733">776.36</span><span class="sxs-lookup"><span data-stu-id="5705b-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-734">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-735">Prod 1</span></span></td>
<td><span data-ttu-id="5705b-736">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-736">Product 1</span></span></td>
<td><span data-ttu-id="5705b-737">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-737">10001</span></span></td>
<td><span data-ttu-id="5705b-738">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-738">Electricity</span></span></td>
<td><span data-ttu-id="5705b-739">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-739">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="5705b-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-741">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-742">Prod 2</span></span></td>
<td><span data-ttu-id="5705b-743">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-743">Product 1</span></span></td>
<td><span data-ttu-id="5705b-744">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-744">10001</span></span></td>
<td><span data-ttu-id="5705b-745">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-745">Electricity</span></span></td>
<td><span data-ttu-id="5705b-746">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-746">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-747">223.64</span><span class="sxs-lookup"><span data-stu-id="5705b-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-748">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="5705b-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-749">Prod 2</span></span></td>
<td><span data-ttu-id="5705b-750">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-750">Product 1</span></span></td>
<td><span data-ttu-id="5705b-751">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-751">10001</span></span></td>
<td><span data-ttu-id="5705b-752">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-752">Electricity</span></span></td>
<td><span data-ttu-id="5705b-753">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-753">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="5705b-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5705b-755">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5705b-756">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5705b-757">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-757">Cost element</span></span></th>
<th><span data-ttu-id="5705b-758">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="5705b-758">Cost behavior</span></span></th>
<th><span data-ttu-id="5705b-759">Montant</span><span class="sxs-lookup"><span data-stu-id="5705b-759">Amount</span></span></th>
<th><span data-ttu-id="5705b-760">Date comptable</span><span class="sxs-lookup"><span data-stu-id="5705b-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5705b-761">CC001</span><span class="sxs-lookup"><span data-stu-id="5705b-761">CC001</span></span></td>
<td><span data-ttu-id="5705b-762">RH</span><span class="sxs-lookup"><span data-stu-id="5705b-762">HR</span></span></td>
<td><span data-ttu-id="5705b-763">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-763">10001</span></span></td>
<td><span data-ttu-id="5705b-764">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-764">Electricity</span></span></td>
<td><span data-ttu-id="5705b-765">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-765">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="5705b-766">-500.00</span></span></td>
<td><span data-ttu-id="5705b-767">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-768">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-768">CC002</span></span></td>
<td><span data-ttu-id="5705b-769">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-769">Finance</span></span></td>
<td><span data-ttu-id="5705b-770">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-770">10001</span></span></td>
<td><span data-ttu-id="5705b-771">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-771">Electricity</span></span></td>
<td><span data-ttu-id="5705b-772">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-772">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-773">175.00</span><span class="sxs-lookup"><span data-stu-id="5705b-773">175.00</span></span></td>
<td><span data-ttu-id="5705b-774">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-775">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-775">CC003</span></span></td>
<td><span data-ttu-id="5705b-776">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-776">Assembly</span></span></td>
<td><span data-ttu-id="5705b-777">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-777">10001</span></span></td>
<td><span data-ttu-id="5705b-778">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-778">Electricity</span></span></td>
<td><span data-ttu-id="5705b-779">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-779">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-780">275.00</span><span class="sxs-lookup"><span data-stu-id="5705b-780">275.00</span></span></td>
<td><span data-ttu-id="5705b-781">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-782">CC004</span><span class="sxs-lookup"><span data-stu-id="5705b-782">CC004</span></span></td>
<td><span data-ttu-id="5705b-783">Emballage</span><span class="sxs-lookup"><span data-stu-id="5705b-783">Packaging</span></span></td>
<td><span data-ttu-id="5705b-784">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-784">10001</span></span></td>
<td><span data-ttu-id="5705b-785">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-785">Electricity</span></span></td>
<td><span data-ttu-id="5705b-786">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-786">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-787">50,00</span><span class="sxs-lookup"><span data-stu-id="5705b-787">50,00</span></span></td>
<td><span data-ttu-id="5705b-788">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-789">CC001</span><span class="sxs-lookup"><span data-stu-id="5705b-789">CC001</span></span></td>
<td><span data-ttu-id="5705b-790">RH</span><span class="sxs-lookup"><span data-stu-id="5705b-790">HR</span></span></td>
<td><span data-ttu-id="5705b-791">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-791">10001</span></span></td>
<td><span data-ttu-id="5705b-792">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-792">Electricity</span></span></td>
<td><span data-ttu-id="5705b-793">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-793">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="5705b-794">-1,245.71</span></span></td>
<td><span data-ttu-id="5705b-795">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-796">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-796">CC002</span></span></td>
<td><span data-ttu-id="5705b-797">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-797">Finance</span></span></td>
<td><span data-ttu-id="5705b-798">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-798">10001</span></span></td>
<td><span data-ttu-id="5705b-799">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-799">Electricity</span></span></td>
<td><span data-ttu-id="5705b-800">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-800">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-801">436.00</span><span class="sxs-lookup"><span data-stu-id="5705b-801">436.00</span></span></td>
<td><span data-ttu-id="5705b-802">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-803">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-803">CC003</span></span></td>
<td><span data-ttu-id="5705b-804">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-804">Assembly</span></span></td>
<td><span data-ttu-id="5705b-805">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-805">10001</span></span></td>
<td><span data-ttu-id="5705b-806">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-806">Electricity</span></span></td>
<td><span data-ttu-id="5705b-807">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-807">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-808">685.14</span><span class="sxs-lookup"><span data-stu-id="5705b-808">685.14</span></span></td>
<td><span data-ttu-id="5705b-809">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-810">CC004</span><span class="sxs-lookup"><span data-stu-id="5705b-810">CC004</span></span></td>
<td><span data-ttu-id="5705b-811">Emballage</span><span class="sxs-lookup"><span data-stu-id="5705b-811">Packaging</span></span></td>
<td><span data-ttu-id="5705b-812">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-812">10001</span></span></td>
<td><span data-ttu-id="5705b-813">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-813">Electricity</span></span></td>
<td><span data-ttu-id="5705b-814">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-814">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-815">124.57</span><span class="sxs-lookup"><span data-stu-id="5705b-815">124.57</span></span></td>
<td><span data-ttu-id="5705b-816">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-817">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-817">CC002</span></span></td>
<td><span data-ttu-id="5705b-818">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-818">Finance</span></span></td>
<td><span data-ttu-id="5705b-819">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-819">10001</span></span></td>
<td><span data-ttu-id="5705b-820">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-820">Electricity</span></span></td>
<td><span data-ttu-id="5705b-821">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-821">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="5705b-822">-675.00</span></span></td>
<td><span data-ttu-id="5705b-823">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-824">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-824">CC003</span></span></td>
<td><span data-ttu-id="5705b-825">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-825">Assembly</span></span></td>
<td><span data-ttu-id="5705b-826">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-826">10001</span></span></td>
<td><span data-ttu-id="5705b-827">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-827">Electricity</span></span></td>
<td><span data-ttu-id="5705b-828">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-828">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-829">438.75</span><span class="sxs-lookup"><span data-stu-id="5705b-829">438.75</span></span></td>
<td><span data-ttu-id="5705b-830">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-831">CC004</span><span class="sxs-lookup"><span data-stu-id="5705b-831">CC004</span></span></td>
<td><span data-ttu-id="5705b-832">Emballage</span><span class="sxs-lookup"><span data-stu-id="5705b-832">Packaging</span></span></td>
<td><span data-ttu-id="5705b-833">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-833">10001</span></span></td>
<td><span data-ttu-id="5705b-834">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-834">Electricity</span></span></td>
<td><span data-ttu-id="5705b-835">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-835">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-836">236.25</span><span class="sxs-lookup"><span data-stu-id="5705b-836">236.25</span></span></td>
<td><span data-ttu-id="5705b-837">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-838">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-838">CC002</span></span></td>
<td><span data-ttu-id="5705b-839">Finances</span><span class="sxs-lookup"><span data-stu-id="5705b-839">Finance</span></span></td>
<td><span data-ttu-id="5705b-840">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-840">10001</span></span></td>
<td><span data-ttu-id="5705b-841">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-841">Electricity</span></span></td>
<td><span data-ttu-id="5705b-842">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-842">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="5705b-843">-8,150.29</span></span></td>
<td><span data-ttu-id="5705b-844">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-845">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-845">CC003</span></span></td>
<td><span data-ttu-id="5705b-846">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-846">Assembly</span></span></td>
<td><span data-ttu-id="5705b-847">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-847">10001</span></span></td>
<td><span data-ttu-id="5705b-848">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-848">Electricity</span></span></td>
<td><span data-ttu-id="5705b-849">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-849">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="5705b-850">5,297.69</span></span></td>
<td><span data-ttu-id="5705b-851">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-852">CC004</span><span class="sxs-lookup"><span data-stu-id="5705b-852">CC004</span></span></td>
<td><span data-ttu-id="5705b-853">Emballage</span><span class="sxs-lookup"><span data-stu-id="5705b-853">Packaging</span></span></td>
<td><span data-ttu-id="5705b-854">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-854">10001</span></span></td>
<td><span data-ttu-id="5705b-855">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-855">Electricity</span></span></td>
<td><span data-ttu-id="5705b-856">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-856">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="5705b-857">2,852.60</span></span></td>
<td><span data-ttu-id="5705b-858">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-859">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-859">CC003</span></span></td>
<td><span data-ttu-id="5705b-860">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-860">Assembly</span></span></td>
<td><span data-ttu-id="5705b-861">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-861">10001</span></span></td>
<td><span data-ttu-id="5705b-862">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-862">Electricity</span></span></td>
<td><span data-ttu-id="5705b-863">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-863">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="5705b-864">-713.75</span></span></td>
<td><span data-ttu-id="5705b-865">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-866">Prod 1</span></span></td>
<td><span data-ttu-id="5705b-867">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-867">Product 1</span></span></td>
<td><span data-ttu-id="5705b-868">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-868">10001</span></span></td>
<td><span data-ttu-id="5705b-869">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-869">Electricity</span></span></td>
<td><span data-ttu-id="5705b-870">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-870">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-871">535.31</span><span class="sxs-lookup"><span data-stu-id="5705b-871">535.31</span></span></td>
<td><span data-ttu-id="5705b-872">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-873">Prod 2</span></span></td>
<td><span data-ttu-id="5705b-874">Produit 2</span><span class="sxs-lookup"><span data-stu-id="5705b-874">Product 2</span></span></td>
<td><span data-ttu-id="5705b-875">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-875">10001</span></span></td>
<td><span data-ttu-id="5705b-876">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-876">Electricity</span></span></td>
<td><span data-ttu-id="5705b-877">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-877">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-878">178.44</span><span class="sxs-lookup"><span data-stu-id="5705b-878">178.44</span></span></td>
<td><span data-ttu-id="5705b-879">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-880">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-880">CC003</span></span></td>
<td><span data-ttu-id="5705b-881">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-881">Assembly</span></span></td>
<td><span data-ttu-id="5705b-882">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-882">10001</span></span></td>
<td><span data-ttu-id="5705b-883">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-883">Electricity</span></span></td>
<td><span data-ttu-id="5705b-884">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-884">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="5705b-885">-5,982.83</span></span></td>
<td><span data-ttu-id="5705b-886">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-887">Prod 1</span></span></td>
<td><span data-ttu-id="5705b-888">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-888">Product 1</span></span></td>
<td><span data-ttu-id="5705b-889">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-889">10001</span></span></td>
<td><span data-ttu-id="5705b-890">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-890">Electricity</span></span></td>
<td><span data-ttu-id="5705b-891">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-891">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="5705b-892">4,487.12</span></span></td>
<td><span data-ttu-id="5705b-893">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-894">Prod 2</span></span></td>
<td><span data-ttu-id="5705b-895">Produit 2</span><span class="sxs-lookup"><span data-stu-id="5705b-895">Product 2</span></span></td>
<td><span data-ttu-id="5705b-896">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-896">10001</span></span></td>
<td><span data-ttu-id="5705b-897">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-897">Electricity</span></span></td>
<td><span data-ttu-id="5705b-898">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-898">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="5705b-899">1,495.71</span></span></td>
<td><span data-ttu-id="5705b-900">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-901">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-901">CC003</span></span></td>
<td><span data-ttu-id="5705b-902">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-902">Assembly</span></span></td>
<td><span data-ttu-id="5705b-903">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-903">10001</span></span></td>
<td><span data-ttu-id="5705b-904">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-904">Electricity</span></span></td>
<td><span data-ttu-id="5705b-905">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-905">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="5705b-906">-286.25</span></span></td>
<td><span data-ttu-id="5705b-907">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-908">Prod 1</span></span></td>
<td><span data-ttu-id="5705b-909">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-909">Product 1</span></span></td>
<td><span data-ttu-id="5705b-910">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-910">10001</span></span></td>
<td><span data-ttu-id="5705b-911">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-911">Electricity</span></span></td>
<td><span data-ttu-id="5705b-912">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-912">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-913">241.05</span><span class="sxs-lookup"><span data-stu-id="5705b-913">241.05</span></span></td>
<td><span data-ttu-id="5705b-914">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-915">Prod 2</span></span></td>
<td><span data-ttu-id="5705b-916">Produit 2</span><span class="sxs-lookup"><span data-stu-id="5705b-916">Product 2</span></span></td>
<td><span data-ttu-id="5705b-917">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-917">10001</span></span></td>
<td><span data-ttu-id="5705b-918">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-918">Electricity</span></span></td>
<td><span data-ttu-id="5705b-919">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-919">Fixed cost</span></span></td>
<td><span data-ttu-id="5705b-920">45.20</span><span class="sxs-lookup"><span data-stu-id="5705b-920">45.20</span></span></td>
<td><span data-ttu-id="5705b-921">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-922">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-922">CC003</span></span></td>
<td><span data-ttu-id="5705b-923">Assemblage</span><span class="sxs-lookup"><span data-stu-id="5705b-923">Assembly</span></span></td>
<td><span data-ttu-id="5705b-924">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-924">10001</span></span></td>
<td><span data-ttu-id="5705b-925">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-925">Electricity</span></span></td>
<td><span data-ttu-id="5705b-926">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-926">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="5705b-927">-2,977.17</span></span></td>
<td><span data-ttu-id="5705b-928">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-929">Prod 1</span></span></td>
<td><span data-ttu-id="5705b-930">Produit 1</span><span class="sxs-lookup"><span data-stu-id="5705b-930">Product 1</span></span></td>
<td><span data-ttu-id="5705b-931">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-931">10001</span></span></td>
<td><span data-ttu-id="5705b-932">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-932">Electricity</span></span></td>
<td><span data-ttu-id="5705b-933">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-933">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="5705b-934">2,507.09</span></span></td>
<td><span data-ttu-id="5705b-935">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5705b-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-936">Prod 2</span></span></td>
<td><span data-ttu-id="5705b-937">Produit 2</span><span class="sxs-lookup"><span data-stu-id="5705b-937">Product 2</span></span></td>
<td><span data-ttu-id="5705b-938">10001</span><span class="sxs-lookup"><span data-stu-id="5705b-938">10001</span></span></td>
<td><span data-ttu-id="5705b-939">Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-939">Electricity</span></span></td>
<td><span data-ttu-id="5705b-940">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-940">Variable cost</span></span></td>
<td><span data-ttu-id="5705b-941">470.08</span><span class="sxs-lookup"><span data-stu-id="5705b-941">470.08</span></span></td>
<td><span data-ttu-id="5705b-942">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="5705b-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="5705b-943">Conclusion</span><span class="sxs-lookup"><span data-stu-id="5705b-943">Conclusion</span></span>
<span data-ttu-id="5705b-944">Dans la comptabilité financière, un coût de 10 000,00 pour l'électricité est imputé sur un ID de centre de coût fictif.</span><span class="sxs-lookup"><span data-stu-id="5705b-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="5705b-945">Par conséquent, les comptables sauront que ce coût doit être affecté.</span><span class="sxs-lookup"><span data-stu-id="5705b-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="5705b-946">Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l'organisation, selon les stratégies et les règles qui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="5705b-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="5705b-947">Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="5705b-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="5705b-948">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="5705b-949">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5705b-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="5705b-950">Total</span><span class="sxs-lookup"><span data-stu-id="5705b-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="5705b-951">CC099</span><span class="sxs-lookup"><span data-stu-id="5705b-951">CC099</span></span></th>
<th><span data-ttu-id="5705b-952">CC001</span><span class="sxs-lookup"><span data-stu-id="5705b-952">CC001</span></span></th>
<th><span data-ttu-id="5705b-953">CC002</span><span class="sxs-lookup"><span data-stu-id="5705b-953">CC002</span></span></th>
<th><span data-ttu-id="5705b-954">CC003</span><span class="sxs-lookup"><span data-stu-id="5705b-954">CC003</span></span></th>
<th><span data-ttu-id="5705b-955">CC004</span><span class="sxs-lookup"><span data-stu-id="5705b-955">CC004</span></span></th>
<th><span data-ttu-id="5705b-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5705b-956">Proj 1</span></span></th>
<th><span data-ttu-id="5705b-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5705b-957">Proj 2</span></span></th>
<th><span data-ttu-id="5705b-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5705b-958">Prod 1</span></span></th>
<th><span data-ttu-id="5705b-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5705b-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="5705b-960">10001 Électricité</span><span class="sxs-lookup"><span data-stu-id="5705b-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="5705b-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="5705b-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="5705b-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="5705b-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="5705b-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="5705b-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="5705b-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="5705b-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="5705b-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="5705b-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="5705b-970">Non classifié</span><span class="sxs-lookup"><span data-stu-id="5705b-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-971">0,00</span><span class="sxs-lookup"><span data-stu-id="5705b-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="5705b-972">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="5705b-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-973">0,00</span><span class="sxs-lookup"><span data-stu-id="5705b-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-974">0,00</span><span class="sxs-lookup"><span data-stu-id="5705b-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-975">0,00</span><span class="sxs-lookup"><span data-stu-id="5705b-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-976">0,00</span><span class="sxs-lookup"><span data-stu-id="5705b-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-977">0,00</span><span class="sxs-lookup"><span data-stu-id="5705b-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="5705b-978">776.36</span><span class="sxs-lookup"><span data-stu-id="5705b-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-979">223.64</span><span class="sxs-lookup"><span data-stu-id="5705b-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-980"><strong>1 000,00</strong></span><span class="sxs-lookup"><span data-stu-id="5705b-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="5705b-981">Coût variable</span><span class="sxs-lookup"><span data-stu-id="5705b-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-982">000</span><span class="sxs-lookup"><span data-stu-id="5705b-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-983">0,00</span><span class="sxs-lookup"><span data-stu-id="5705b-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-984">0,00</span><span class="sxs-lookup"><span data-stu-id="5705b-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-985">0,00</span><span class="sxs-lookup"><span data-stu-id="5705b-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-986">0,00</span><span class="sxs-lookup"><span data-stu-id="5705b-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-987">30,00</span><span class="sxs-lookup"><span data-stu-id="5705b-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-988">10,00</span><span class="sxs-lookup"><span data-stu-id="5705b-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="5705b-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="5705b-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5705b-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="5705b-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="5705b-992">Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût.</span><span class="sxs-lookup"><span data-stu-id="5705b-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="5705b-993">Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l'organisation.</span><span class="sxs-lookup"><span data-stu-id="5705b-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="5705b-994">Autrement dit, les objets de coût de plus bas niveau supportent le coût.</span><span class="sxs-lookup"><span data-stu-id="5705b-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="5705b-995">Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts.</span><span class="sxs-lookup"><span data-stu-id="5705b-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="5705b-996">Pour plus d'informations, voir [Stratégie de repositionnement des coûts et calcul des frais généraux](cost-rollup.md)..</span><span class="sxs-lookup"><span data-stu-id="5705b-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



