---
title: "Calcul des frais généraux"
description: "Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: f56feac74dfe78b740342688a908d001614cffd0
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="ec15d-103">Calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="ec15d-103">Overhead calculation</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="ec15d-104">Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="ec15d-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="ec15d-105">Définition des termes</span><span class="sxs-lookup"><span data-stu-id="ec15d-105">Term definition</span></span>
---------------

<span data-ttu-id="ec15d-106">Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique.</span><span class="sxs-lookup"><span data-stu-id="ec15d-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="ec15d-107">Les frais généraux permettent essentiellement l'identification des activités rémunératrices.</span><span class="sxs-lookup"><span data-stu-id="ec15d-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="ec15d-108">Voici quelques exemples de frais généraux :</span><span class="sxs-lookup"><span data-stu-id="ec15d-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="ec15d-109">Loyer</span><span class="sxs-lookup"><span data-stu-id="ec15d-109">Rent</span></span>
-   <span data-ttu-id="ec15d-110">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-110">Electricity</span></span>
-   <span data-ttu-id="ec15d-111">Salaires administratifs</span><span class="sxs-lookup"><span data-stu-id="ec15d-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="ec15d-112">Vue d'ensemble du calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="ec15d-112">Overhead calculation overview</span></span>
<span data-ttu-id="ec15d-113">Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l'ordre correct.</span><span class="sxs-lookup"><span data-stu-id="ec15d-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="ec15d-114">Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées.</span><span class="sxs-lookup"><span data-stu-id="ec15d-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="ec15d-115">Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions.</span><span class="sxs-lookup"><span data-stu-id="ec15d-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="ec15d-116">Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable.</span><span class="sxs-lookup"><span data-stu-id="ec15d-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="ec15d-117">Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="ec15d-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="ec15d-118">L'ID de version unique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ec15d-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="ec15d-119">Type de version</span><span class="sxs-lookup"><span data-stu-id="ec15d-119">Version type</span></span>
-   <span data-ttu-id="ec15d-120">Date et heure</span><span class="sxs-lookup"><span data-stu-id="ec15d-120">Date and time</span></span>
-   <span data-ttu-id="ec15d-121">Comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="ec15d-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="ec15d-122">Exercice</span><span class="sxs-lookup"><span data-stu-id="ec15d-122">Fiscal year</span></span>
-   <span data-ttu-id="ec15d-123">Période fiscale</span><span class="sxs-lookup"><span data-stu-id="ec15d-123">Fiscal period</span></span>

<span data-ttu-id="ec15d-124">Le calcul des frais généraux est effectué indépendamment de la version.</span><span class="sxs-lookup"><span data-stu-id="ec15d-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="ec15d-125">Par conséquent, vous pouvez calculer la version de budget avant la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="ec15d-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="ec15d-126">Le calcul des frais généraux comporte quatre étapes, comme le montre l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="ec15d-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="ec15d-127">Dans chaque étape, un en-tête de journal avec des entrées de journal est créé.</span><span class="sxs-lookup"><span data-stu-id="ec15d-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="ec15d-128">Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul.</span><span class="sxs-lookup"><span data-stu-id="ec15d-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="ec15d-129">Les stratégies et les règles s'appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie.</span><span class="sxs-lookup"><span data-stu-id="ec15d-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="ec15d-130">Par conséquent, vous disposez toujours d'une traçabilité complète.</span><span class="sxs-lookup"><span data-stu-id="ec15d-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="ec15d-131">[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="ec15d-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="ec15d-132">Calculer et affecter les frais généraux Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="ec15d-133">Dans la comptabilité financière, certaines coûts, tels que l'électricité, sont enregistrés comme montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="ec15d-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="ec15d-134">Par conséquent, l'analyse détaillée n'est pas fournie pour le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="ec15d-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="ec15d-135">Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l'organisation, les coûts doivent suivre les unités organisationnelles.</span><span class="sxs-lookup"><span data-stu-id="ec15d-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="ec15d-136">Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste.</span><span class="sxs-lookup"><span data-stu-id="ec15d-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="ec15d-137">Dans la comptabilité, le coût de l'électricité peut être validé comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="ec15d-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec15d-138">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec15d-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-139">Centre de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-140">Compte principal</span><span class="sxs-lookup"><span data-stu-id="ec15d-140">Main account</span></span></th>
<th><span data-ttu-id="ec15d-141">Montant en devise comptable</span><span class="sxs-lookup"><span data-stu-id="ec15d-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-142">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="ec15d-143">CC099</span><span class="sxs-lookup"><span data-stu-id="ec15d-143">CC099</span></span></td>
<td><span data-ttu-id="ec15d-144">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec15d-144">Default cost center</span></span></td>
<td><span data-ttu-id="ec15d-145">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-145">10001</span></span></td>
<td><span data-ttu-id="ec15d-146">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-146">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="ec15d-148">Étape 1 : Traiter le calcul du comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="ec15d-149">Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="ec15d-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="ec15d-150">Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.</span><span class="sxs-lookup"><span data-stu-id="ec15d-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="ec15d-151">Définir la règle de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-151">Define the cost behavior rule</span></span>

<span data-ttu-id="ec15d-152">Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation.</span><span class="sxs-lookup"><span data-stu-id="ec15d-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="ec15d-153">Les factures d'électricité correspondent souvent à cette définition.</span><span class="sxs-lookup"><span data-stu-id="ec15d-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="ec15d-154">Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH).</span><span class="sxs-lookup"><span data-stu-id="ec15d-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="ec15d-155">Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :</span><span class="sxs-lookup"><span data-stu-id="ec15d-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="ec15d-156">Montant fixe 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="ec15d-157">0 &lt;= 1 000,00 = Fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="ec15d-158">1 000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="ec15d-159">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec15d-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec15d-160">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec15d-160">Journal</span></span></th>
<th><span data-ttu-id="ec15d-161">Type de journal</span><span class="sxs-lookup"><span data-stu-id="ec15d-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ec15d-162">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="ec15d-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ec15d-163">Version</span><span class="sxs-lookup"><span data-stu-id="ec15d-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-164">00001</span><span class="sxs-lookup"><span data-stu-id="ec15d-164">00001</span></span></td>
<td><span data-ttu-id="ec15d-165">Journal de calcul de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="ec15d-166">Exercice</span><span class="sxs-lookup"><span data-stu-id="ec15d-166">Fiscal</span></span></td>
<td><span data-ttu-id="ec15d-167">2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-167">2017</span></span></td>
<td><span data-ttu-id="ec15d-168">Période 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-168">Period 1</span></span></td>
<td><span data-ttu-id="ec15d-169">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ec15d-170">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="ec15d-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec15d-171">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec15d-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-172">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-173">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-173">Cost element</span></span></th>
<th><span data-ttu-id="ec15d-174">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-174">Cost behavior</span></span></th>
<th><span data-ttu-id="ec15d-175">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-176">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="ec15d-177">CC099</span><span class="sxs-lookup"><span data-stu-id="ec15d-177">CC099</span></span></td>
<td><span data-ttu-id="ec15d-178">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec15d-178">Default cost center</span></span></td>
<td><span data-ttu-id="ec15d-179">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-179">10001</span></span></td>
<td><span data-ttu-id="ec15d-180">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-180">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-181">Non classifié</span><span class="sxs-lookup"><span data-stu-id="ec15d-181">Unclassified</span></span></td>
<td><span data-ttu-id="ec15d-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ec15d-183">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-184">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-185">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-185">Cost element</span></span></th>
<th><span data-ttu-id="ec15d-186">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-186">Cost behavior</span></span></th>
<th><span data-ttu-id="ec15d-187">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-187">Amount</span></span></th>
<th><span data-ttu-id="ec15d-188">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec15d-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-189">CC099</span><span class="sxs-lookup"><span data-stu-id="ec15d-189">CC099</span></span></td>
<td><span data-ttu-id="ec15d-190">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec15d-190">Default cost center</span></span></td>
<td><span data-ttu-id="ec15d-191">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-191">10001</span></span></td>
<td><span data-ttu-id="ec15d-192">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-192">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-193">Non classifié</span><span class="sxs-lookup"><span data-stu-id="ec15d-193">Unclassified</span></span></td>
<td><span data-ttu-id="ec15d-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-194">10,000.00</span></span></td>
<td><span data-ttu-id="ec15d-195">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-196">CC099</span><span class="sxs-lookup"><span data-stu-id="ec15d-196">CC099</span></span></td>
<td><span data-ttu-id="ec15d-197">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec15d-197">Default cost center</span></span></td>
<td><span data-ttu-id="ec15d-198">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-198">10001</span></span></td>
<td><span data-ttu-id="ec15d-199">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-199">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-200">Non classifié</span><span class="sxs-lookup"><span data-stu-id="ec15d-200">Unclassified</span></span></td>
<td><span data-ttu-id="ec15d-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-201">-10,000.00</span></span></td>
<td><span data-ttu-id="ec15d-202">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-203">CC099</span><span class="sxs-lookup"><span data-stu-id="ec15d-203">CC099</span></span></td>
<td><span data-ttu-id="ec15d-204">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec15d-204">Default cost center</span></span></td>
<td><span data-ttu-id="ec15d-205">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-205">10001</span></span></td>
<td><span data-ttu-id="ec15d-206">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-206">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-207">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-207">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-208">1,000.00</span></span></td>
<td><span data-ttu-id="ec15d-209">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-210">CC099</span><span class="sxs-lookup"><span data-stu-id="ec15d-210">CC099</span></span></td>
<td><span data-ttu-id="ec15d-211">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec15d-211">Default cost center</span></span></td>
<td><span data-ttu-id="ec15d-212">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-212">10001</span></span></td>
<td><span data-ttu-id="ec15d-213">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-213">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-214">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-214">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-215">9 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-215">9,000.00</span></span></td>
<td><span data-ttu-id="ec15d-216">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-217">Pour obtenir des informations détaillées sur le comportement de coûts, voir la stratégie de comportement de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec15d-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="ec15d-218">(Notez que cette rubrique n'est pas complète et sera bientôt mise à jour.)</span><span class="sxs-lookup"><span data-stu-id="ec15d-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="ec15d-219">Étape 2 : Traiter le calcul de distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="ec15d-220">La distribution des coûts est utilisée pour redistribuer le coût d'un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée.</span><span class="sxs-lookup"><span data-stu-id="ec15d-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="ec15d-221">La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l'élément de coût principal du coût d'origine.</span><span class="sxs-lookup"><span data-stu-id="ec15d-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="ec15d-222">Définir la règle de distribution de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-222">Define the cost distribution rule</span></span>

<span data-ttu-id="ec15d-223">Dans la comptabilité financière, les coûts d'électricité sont souvent enregistrés comme un montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="ec15d-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="ec15d-224">Dans le Contrôle de gestion, cette approche n'est pas assez détaillée.</span><span class="sxs-lookup"><span data-stu-id="ec15d-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="ec15d-225">Le coût variable doit être attribué aux différents objets de coûts sur une base juste.</span><span class="sxs-lookup"><span data-stu-id="ec15d-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="ec15d-226">La base de répartition la plus logique est la consommation de l'électricité (KWH).</span><span class="sxs-lookup"><span data-stu-id="ec15d-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="ec15d-227">Un membre de dimension statistique nommé Électricité est créé, et la consommation d'électricité est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="ec15d-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="ec15d-228">Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="ec15d-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-229">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-229">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="ec15d-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-231">CC001</span><span class="sxs-lookup"><span data-stu-id="ec15d-231">CC001</span></span></td>
<td><span data-ttu-id="ec15d-232">RH</span><span class="sxs-lookup"><span data-stu-id="ec15d-232">HR</span></span></td>
<td><span data-ttu-id="ec15d-233">1 000</span><span class="sxs-lookup"><span data-stu-id="ec15d-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-234">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-234">CC002</span></span></td>
<td><span data-ttu-id="ec15d-235">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-235">Finance</span></span></td>
<td><span data-ttu-id="ec15d-236">6 000</span><span class="sxs-lookup"><span data-stu-id="ec15d-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-237">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-237">CC003</span></span></td>
<td><span data-ttu-id="ec15d-238">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-238">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-239">0</span><span class="sxs-lookup"><span data-stu-id="ec15d-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-240">Le tableau suivant illustre le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="ec15d-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-241">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-241">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-242">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec15d-242">Magnitude</span></span></th>
<th><span data-ttu-id="ec15d-243">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec15d-243">Allocation factor</span></span></th>
<th><span data-ttu-id="ec15d-244">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-245">CC001</span><span class="sxs-lookup"><span data-stu-id="ec15d-245">CC001</span></span></td>
<td><span data-ttu-id="ec15d-246">RH</span><span class="sxs-lookup"><span data-stu-id="ec15d-246">HR</span></span></td>
<td><span data-ttu-id="ec15d-247">1 000</span><span class="sxs-lookup"><span data-stu-id="ec15d-247">1,000</span></span></td>
<td><span data-ttu-id="ec15d-248">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ec15d-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ec15d-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-250">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-250">CC002</span></span></td>
<td><span data-ttu-id="ec15d-251">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-251">Finance</span></span></td>
<td><span data-ttu-id="ec15d-252">6 000</span><span class="sxs-lookup"><span data-stu-id="ec15d-252">6,000</span></span></td>
<td><span data-ttu-id="ec15d-253">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ec15d-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ec15d-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-255">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-255">CC003</span></span></td>
<td><span data-ttu-id="ec15d-256">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-256">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-257">0</span><span class="sxs-lookup"><span data-stu-id="ec15d-257">0</span></span></td>
<td><span data-ttu-id="ec15d-258">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ec15d-259">0,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-260">Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l'électricité.</span><span class="sxs-lookup"><span data-stu-id="ec15d-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="ec15d-261">Vous pouvez obtenir ce résultat à l'aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="ec15d-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-262">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-262">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-263">Formule</span><span class="sxs-lookup"><span data-stu-id="ec15d-263">Formula</span></span></th>
<th><span data-ttu-id="ec15d-264">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec15d-264">Magnitude</span></span></th>
<th><span data-ttu-id="ec15d-265">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec15d-265">Allocation factor</span></span></th>
<th><span data-ttu-id="ec15d-266">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-267">CC001</span><span class="sxs-lookup"><span data-stu-id="ec15d-267">CC001</span></span></td>
<td><span data-ttu-id="ec15d-268">RH</span><span class="sxs-lookup"><span data-stu-id="ec15d-268">HR</span></span></td>
<td><span data-ttu-id="ec15d-269">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ec15d-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ec15d-270">1</span><span class="sxs-lookup"><span data-stu-id="ec15d-270">1</span></span></td>
<td><span data-ttu-id="ec15d-271">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ec15d-272">500,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-273">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-273">CC002</span></span></td>
<td><span data-ttu-id="ec15d-274">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-274">Finance</span></span></td>
<td><span data-ttu-id="ec15d-275">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ec15d-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ec15d-276">1</span><span class="sxs-lookup"><span data-stu-id="ec15d-276">1</span></span></td>
<td><span data-ttu-id="ec15d-277">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ec15d-278">500,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-279">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-279">CC003</span></span></td>
<td><span data-ttu-id="ec15d-280">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-280">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ec15d-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ec15d-282">0</span><span class="sxs-lookup"><span data-stu-id="ec15d-282">0</span></span></td>
<td><span data-ttu-id="ec15d-283">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ec15d-284">0,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ec15d-285">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec15d-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec15d-286">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec15d-286">Journal</span></span></th>
<th><span data-ttu-id="ec15d-287">Type de journal</span><span class="sxs-lookup"><span data-stu-id="ec15d-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ec15d-288">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="ec15d-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ec15d-289">Version</span><span class="sxs-lookup"><span data-stu-id="ec15d-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-290">00002</span><span class="sxs-lookup"><span data-stu-id="ec15d-290">00002</span></span></td>
<td><span data-ttu-id="ec15d-291">Journal de calcul de la distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="ec15d-292">Exercice</span><span class="sxs-lookup"><span data-stu-id="ec15d-292">Fiscal</span></span></td>
<td><span data-ttu-id="ec15d-293">2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-293">2017</span></span></td>
<td><span data-ttu-id="ec15d-294">Période 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-294">Period 1</span></span></td>
<td><span data-ttu-id="ec15d-295">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ec15d-296">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="ec15d-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec15d-297">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec15d-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-298">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-299">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-299">Cost element</span></span></th>
<th><span data-ttu-id="ec15d-300">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-300">Cost behavior</span></span></th>
<th><span data-ttu-id="ec15d-301">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-302">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-303">CC099</span><span class="sxs-lookup"><span data-stu-id="ec15d-303">CC099</span></span></td>
<td><span data-ttu-id="ec15d-304">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec15d-304">Default cost center</span></span></td>
<td><span data-ttu-id="ec15d-305">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-305">10001</span></span></td>
<td><span data-ttu-id="ec15d-306">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-306">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-307">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-307">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-308">1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-309">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-310">CC099</span><span class="sxs-lookup"><span data-stu-id="ec15d-310">CC099</span></span></td>
<td><span data-ttu-id="ec15d-311">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec15d-311">Default cost center</span></span></td>
<td><span data-ttu-id="ec15d-312">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-312">10001</span></span></td>
<td><span data-ttu-id="ec15d-313">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-313">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-314">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-314">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-315">9 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ec15d-316">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-317">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-318">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-318">Cost element</span></span></th>
<th><span data-ttu-id="ec15d-319">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-319">Cost behavior</span></span></th>
<th><span data-ttu-id="ec15d-320">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-320">Amount</span></span></th>
<th><span data-ttu-id="ec15d-321">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec15d-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-322">CC099</span><span class="sxs-lookup"><span data-stu-id="ec15d-322">CC099</span></span></td>
<td><span data-ttu-id="ec15d-323">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec15d-323">Default cost center</span></span></td>
<td><span data-ttu-id="ec15d-324">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-324">10001</span></span></td>
<td><span data-ttu-id="ec15d-325">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-325">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-326">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-326">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-327">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-327">-1,000.00</span></span></td>
<td><span data-ttu-id="ec15d-328">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-329">CC001</span><span class="sxs-lookup"><span data-stu-id="ec15d-329">CC001</span></span></td>
<td><span data-ttu-id="ec15d-330">RH</span><span class="sxs-lookup"><span data-stu-id="ec15d-330">HR</span></span></td>
<td><span data-ttu-id="ec15d-331">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-331">10001</span></span></td>
<td><span data-ttu-id="ec15d-332">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-332">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-333">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-333">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-334">500,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-334">500.00</span></span></td>
<td><span data-ttu-id="ec15d-335">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-336">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-336">CC002</span></span></td>
<td><span data-ttu-id="ec15d-337">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-337">Finance</span></span></td>
<td><span data-ttu-id="ec15d-338">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-338">10001</span></span></td>
<td><span data-ttu-id="ec15d-339">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-339">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-340">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-340">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-341">500,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-341">500.00</span></span></td>
<td><span data-ttu-id="ec15d-342">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-343">CC099</span><span class="sxs-lookup"><span data-stu-id="ec15d-343">CC099</span></span></td>
<td><span data-ttu-id="ec15d-344">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec15d-344">Default cost center</span></span></td>
<td><span data-ttu-id="ec15d-345">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-345">10001</span></span></td>
<td><span data-ttu-id="ec15d-346">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-346">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-347">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-347">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-348">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-348">-9,000.00</span></span></td>
<td><span data-ttu-id="ec15d-349">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-350">CC001</span><span class="sxs-lookup"><span data-stu-id="ec15d-350">CC001</span></span></td>
<td><span data-ttu-id="ec15d-351">RH</span><span class="sxs-lookup"><span data-stu-id="ec15d-351">HR</span></span></td>
<td><span data-ttu-id="ec15d-352">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-352">10001</span></span></td>
<td><span data-ttu-id="ec15d-353">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-353">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-354">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-354">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ec15d-355">1,285.71</span></span></td>
<td><span data-ttu-id="ec15d-356">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-357">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-357">CC002</span></span></td>
<td><span data-ttu-id="ec15d-358">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-358">Finance</span></span></td>
<td><span data-ttu-id="ec15d-359">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-359">10001</span></span></td>
<td><span data-ttu-id="ec15d-360">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-360">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-361">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-361">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ec15d-362">7,714.29</span></span></td>
<td><span data-ttu-id="ec15d-363">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-364">Pour plus d'informations sur les bases de distribution et de répartition des coûts, consultez la stratégie de distribution des coûts et les bases de répartition.</span><span class="sxs-lookup"><span data-stu-id="ec15d-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="ec15d-365">(Notez que cette rubrique n'est pas complète et sera bientôt mise à jour.)</span><span class="sxs-lookup"><span data-stu-id="ec15d-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="ec15d-366">Étape 3 : Traitement du calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="ec15d-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="ec15d-367">Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût.</span><span class="sxs-lookup"><span data-stu-id="ec15d-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="ec15d-368">Les frais sont basés sur un taux de coût prédéterminé et l'ampleur de la base d'affectation de répartition.</span><span class="sxs-lookup"><span data-stu-id="ec15d-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="ec15d-369">Définition du taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="ec15d-369">Define the overhead rate</span></span>

<span data-ttu-id="ec15d-370">L'objet de coût CC001 HR contribue à un ensemble de projets internes.</span><span class="sxs-lookup"><span data-stu-id="ec15d-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="ec15d-371">Un membre de dimension statistique nommé Projets HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ec15d-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-372">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-372">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-373">Heures</span><span class="sxs-lookup"><span data-stu-id="ec15d-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-374">Proj 1</span></span></td>
<td><span data-ttu-id="ec15d-375">Projet 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-375">Project 1</span></span></td>
<td><span data-ttu-id="ec15d-376">3</span><span class="sxs-lookup"><span data-stu-id="ec15d-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-377">Proj 2</span></span></td>
<td><span data-ttu-id="ec15d-378">Projet 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-378">Project 2</span></span></td>
<td><span data-ttu-id="ec15d-379">1</span><span class="sxs-lookup"><span data-stu-id="ec15d-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-380">Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.</span><span class="sxs-lookup"><span data-stu-id="ec15d-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-381">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-381">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-382">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-382">Cost element</span></span></th>
<th><span data-ttu-id="ec15d-383">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-383">Cost behavior</span></span></th>
<th><span data-ttu-id="ec15d-384">Unités</span><span class="sxs-lookup"><span data-stu-id="ec15d-384">Units</span></span></th>
<th><span data-ttu-id="ec15d-385">Taux</span><span class="sxs-lookup"><span data-stu-id="ec15d-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-386">CC001</span><span class="sxs-lookup"><span data-stu-id="ec15d-386">CC001</span></span></td>
<td><span data-ttu-id="ec15d-387">RH</span><span class="sxs-lookup"><span data-stu-id="ec15d-387">HR</span></span></td>
<td><span data-ttu-id="ec15d-388">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-388">10001</span></span></td>
<td><span data-ttu-id="ec15d-389">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-389">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-390">1</span><span class="sxs-lookup"><span data-stu-id="ec15d-390">1</span></span></td>
<td><span data-ttu-id="ec15d-391">10</span><span class="sxs-lookup"><span data-stu-id="ec15d-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-392">Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="ec15d-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-393">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-393">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-394">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec15d-394">Magnitude</span></span></th>
<th><span data-ttu-id="ec15d-395">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-395">Cost element</span></span></th>
<th><span data-ttu-id="ec15d-396">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec15d-396">Allocation factor</span></span></th>
<th><span data-ttu-id="ec15d-397">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-398">Proj 1</span></span></td>
<td><span data-ttu-id="ec15d-399">Projet 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-399">Project 1</span></span></td>
<td><span data-ttu-id="ec15d-400">3</span><span class="sxs-lookup"><span data-stu-id="ec15d-400">3</span></span></td>
<td><span data-ttu-id="ec15d-401">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-401">10001</span></span></td>
<td><span data-ttu-id="ec15d-402">(3 ÷ 1) × 10m00</span><span class="sxs-lookup"><span data-stu-id="ec15d-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ec15d-403">30,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-404">Proj 2</span></span></td>
<td><span data-ttu-id="ec15d-405">Projet 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-405">Project 2</span></span></td>
<td><span data-ttu-id="ec15d-406">1</span><span class="sxs-lookup"><span data-stu-id="ec15d-406">1</span></span></td>
<td><span data-ttu-id="ec15d-407">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-407">10001</span></span></td>
<td><span data-ttu-id="ec15d-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ec15d-409">10,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ec15d-410">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec15d-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec15d-411">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec15d-411">Journal</span></span></th>
<th><span data-ttu-id="ec15d-412">Type de journal</span><span class="sxs-lookup"><span data-stu-id="ec15d-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ec15d-413">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="ec15d-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ec15d-414">Version</span><span class="sxs-lookup"><span data-stu-id="ec15d-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-415">00003</span><span class="sxs-lookup"><span data-stu-id="ec15d-415">00003</span></span></td>
<td><span data-ttu-id="ec15d-416">Journal de calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="ec15d-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="ec15d-417">Exercice</span><span class="sxs-lookup"><span data-stu-id="ec15d-417">Fiscal</span></span></td>
<td><span data-ttu-id="ec15d-418">2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-418">2017</span></span></td>
<td><span data-ttu-id="ec15d-419">Période 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-419">Period 1</span></span></td>
<td><span data-ttu-id="ec15d-420">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="ec15d-421">Entrées du journal (pour le calcul du taux de frais généraux)</span><span class="sxs-lookup"><span data-stu-id="ec15d-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec15d-422">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec15d-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-423">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-423">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-424">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec15d-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-425">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-426">Proj 1</span></span></td>
<td><span data-ttu-id="ec15d-427">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ec15d-428">3,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-429">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-430">Proj 2</span></span></td>
<td><span data-ttu-id="ec15d-431">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ec15d-432">1,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ec15d-433">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-434">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-435">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-435">Cost element</span></span></th>
<th><span data-ttu-id="ec15d-436">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-436">Cost behavior</span></span></th>
<th><span data-ttu-id="ec15d-437">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-437">Amount</span></span></th>
<th><span data-ttu-id="ec15d-438">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec15d-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="ec15d-439">CC0001</span></span></td>
<td><span data-ttu-id="ec15d-440">RH</span><span class="sxs-lookup"><span data-stu-id="ec15d-440">HR</span></span></td>
<td><span data-ttu-id="ec15d-441">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-441">10001</span></span></td>
<td><span data-ttu-id="ec15d-442">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-442">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-443">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-443">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-444">-30.00</span></span></td>
<td><span data-ttu-id="ec15d-445">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-446">Proj 1</span></span></td>
<td><span data-ttu-id="ec15d-447">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ec15d-448">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-448">10001</span></span></td>
<td><span data-ttu-id="ec15d-449">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-449">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-450">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-450">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-451">30,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-451">30.00</span></span></td>
<td><span data-ttu-id="ec15d-452">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-453">CC001</span><span class="sxs-lookup"><span data-stu-id="ec15d-453">CC001</span></span></td>
<td><span data-ttu-id="ec15d-454">RH</span><span class="sxs-lookup"><span data-stu-id="ec15d-454">HR</span></span></td>
<td><span data-ttu-id="ec15d-455">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-455">10001</span></span></td>
<td><span data-ttu-id="ec15d-456">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-456">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-457">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-457">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-458">-10.00</span></span></td>
<td><span data-ttu-id="ec15d-459">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-460">Proj 2</span></span></td>
<td><span data-ttu-id="ec15d-461">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ec15d-462">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-462">10001</span></span></td>
<td><span data-ttu-id="ec15d-463">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-463">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-464">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-464">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-465">10,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-465">10.00</span></span></td>
<td><span data-ttu-id="ec15d-466">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-467">Pour plus d'informations sur la stratégie de taux de frais généraux, voir la stratégie et les bases de répartition afférentes.</span><span class="sxs-lookup"><span data-stu-id="ec15d-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="ec15d-468">(Notez que cette rubrique n'est pas complète et sera bientôt mise à jour.)</span><span class="sxs-lookup"><span data-stu-id="ec15d-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="ec15d-469">Étape 4 : Traiter le calcul de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="ec15d-470">La répartition est utilisée pour affecter le solde d'un objet de coût à d'autres objets de coût en appliquant une base de répartition.</span><span class="sxs-lookup"><span data-stu-id="ec15d-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="ec15d-471">Finance and Operations prend en charge la méthode de répartition réciproque.</span><span class="sxs-lookup"><span data-stu-id="ec15d-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="ec15d-472">Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés.</span><span class="sxs-lookup"><span data-stu-id="ec15d-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="ec15d-473">Le système détermine automatiquement l'ordre correct selon lequel exécuter les répartitions.</span><span class="sxs-lookup"><span data-stu-id="ec15d-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="ec15d-474">Le solde d'un objet de coût est réparti par une seule base de répartition.</span><span class="sxs-lookup"><span data-stu-id="ec15d-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="ec15d-475">Les répartitions entre plusieurs dimensions d'objets de coût et leurs membres respectifs sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="ec15d-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="ec15d-476">L'ordre de répartition est contrôlé par l'unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="ec15d-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="ec15d-477">[![Méthode réciproque](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="ec15d-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="ec15d-478">Définir la répartition de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-478">Define the cost allocation</span></span>

<span data-ttu-id="ec15d-479">Voici un exemple simple expliquant comment suivre le flux du coût.</span><span class="sxs-lookup"><span data-stu-id="ec15d-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="ec15d-480">L'objet de coût CC001 HR contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec15d-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="ec15d-481">Un membre de dimension statistique nommé Services HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ec15d-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-482">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-482">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-483">Services HR</span><span class="sxs-lookup"><span data-stu-id="ec15d-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-484">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-484">CC002</span></span></td>
<td><span data-ttu-id="ec15d-485">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-485">Finance</span></span></td>
<td><span data-ttu-id="ec15d-486">35</span><span class="sxs-lookup"><span data-stu-id="ec15d-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-487">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-487">CC003</span></span></td>
<td><span data-ttu-id="ec15d-488">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-488">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-489">55</span><span class="sxs-lookup"><span data-stu-id="ec15d-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-490">CC004</span><span class="sxs-lookup"><span data-stu-id="ec15d-490">CC004</span></span></td>
<td><span data-ttu-id="ec15d-491">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec15d-491">Packaging</span></span></td>
<td><span data-ttu-id="ec15d-492">10</span><span class="sxs-lookup"><span data-stu-id="ec15d-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-493">L'objet de coût CC002 Finance contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec15d-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="ec15d-494">Un membre de dimension statistique nommé Services Finance est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ec15d-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-495">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-495">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-496">Services Finance</span><span class="sxs-lookup"><span data-stu-id="ec15d-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-497">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-497">CC003</span></span></td>
<td><span data-ttu-id="ec15d-498">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-498">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-499">65</span><span class="sxs-lookup"><span data-stu-id="ec15d-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-500">CC004</span><span class="sxs-lookup"><span data-stu-id="ec15d-500">CC004</span></span></td>
<td><span data-ttu-id="ec15d-501">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec15d-501">Packaging</span></span></td>
<td><span data-ttu-id="ec15d-502">35</span><span class="sxs-lookup"><span data-stu-id="ec15d-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-503">L'objet de coût CC003 Assemblage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec15d-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="ec15d-504">Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ec15d-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-505">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-505">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-506">Services Assemblage (heures)</span><span class="sxs-lookup"><span data-stu-id="ec15d-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-507">Prod 1</span></span></td>
<td><span data-ttu-id="ec15d-508">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-508">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-509">60</span><span class="sxs-lookup"><span data-stu-id="ec15d-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-510">Prod 2</span></span></td>
<td><span data-ttu-id="ec15d-511">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-511">Product 2</span></span></td>
<td><span data-ttu-id="ec15d-512">20</span><span class="sxs-lookup"><span data-stu-id="ec15d-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-513">L'objet de coût CC004 Emballage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec15d-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="ec15d-514">Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ec15d-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-515">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-515">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-516">Services Emballage (heures)</span><span class="sxs-lookup"><span data-stu-id="ec15d-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-517">Prod 1</span></span></td>
<td><span data-ttu-id="ec15d-518">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-518">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-519">80</span><span class="sxs-lookup"><span data-stu-id="ec15d-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-520">Prod 2</span></span></td>
<td><span data-ttu-id="ec15d-521">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-521">Product 2</span></span></td>
<td><span data-ttu-id="ec15d-522">15</span><span class="sxs-lookup"><span data-stu-id="ec15d-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-523">**Remarque :** dans Finance and Operations, les mesures statistiques telles que les heures de production qu'un produit consomme peuvent être dérivées des données sources.</span><span class="sxs-lookup"><span data-stu-id="ec15d-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="ec15d-524">Pour des informations détaillées sur les fournisseurs de mesures statistiques, voir le modèle de fournisseur de mesures statistiques.</span><span class="sxs-lookup"><span data-stu-id="ec15d-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="ec15d-525">(Notez que cette rubrique n'est pas complète et sera bientôt mise à jour.) Le tableau suivant présente le résultat lorsque les services HR sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="ec15d-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-526">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-526">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-527">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec15d-527">Magnitude</span></span></th>
<th><span data-ttu-id="ec15d-528">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec15d-528">Allocation factor</span></span></th>
<th><span data-ttu-id="ec15d-529">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-529">Amount</span></span></th>
<th><span data-ttu-id="ec15d-530">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-531">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-531">CC002</span></span></td>
<td><span data-ttu-id="ec15d-532">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-532">Finance</span></span></td>
<td><span data-ttu-id="ec15d-533">35</span><span class="sxs-lookup"><span data-stu-id="ec15d-533">35</span></span></td>
<td><span data-ttu-id="ec15d-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ec15d-535">175.00</span><span class="sxs-lookup"><span data-stu-id="ec15d-535">175.00</span></span></td>
<td><span data-ttu-id="ec15d-536">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-537">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-537">CC003</span></span></td>
<td><span data-ttu-id="ec15d-538">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-538">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-539">55</span><span class="sxs-lookup"><span data-stu-id="ec15d-539">55</span></span></td>
<td><span data-ttu-id="ec15d-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ec15d-541">275.00</span><span class="sxs-lookup"><span data-stu-id="ec15d-541">275.00</span></span></td>
<td><span data-ttu-id="ec15d-542">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-543">CC004</span><span class="sxs-lookup"><span data-stu-id="ec15d-543">CC004</span></span></td>
<td><span data-ttu-id="ec15d-544">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec15d-544">Packaging</span></span></td>
<td><span data-ttu-id="ec15d-545">10</span><span class="sxs-lookup"><span data-stu-id="ec15d-545">10</span></span></td>
<td><span data-ttu-id="ec15d-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ec15d-547">50,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-547">50.00</span></span></td>
<td><span data-ttu-id="ec15d-548">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-549">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-549">CC002</span></span></td>
<td><span data-ttu-id="ec15d-550">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-550">Finance</span></span></td>
<td><span data-ttu-id="ec15d-551">35</span><span class="sxs-lookup"><span data-stu-id="ec15d-551">35</span></span></td>
<td><span data-ttu-id="ec15d-552">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="ec15d-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ec15d-553">436.00</span><span class="sxs-lookup"><span data-stu-id="ec15d-553">436.00</span></span></td>
<td><span data-ttu-id="ec15d-554">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-555">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-555">CC003</span></span></td>
<td><span data-ttu-id="ec15d-556">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-556">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-557">55</span><span class="sxs-lookup"><span data-stu-id="ec15d-557">55</span></span></td>
<td><span data-ttu-id="ec15d-558">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="ec15d-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ec15d-559">685.14</span><span class="sxs-lookup"><span data-stu-id="ec15d-559">685.14</span></span></td>
<td><span data-ttu-id="ec15d-560">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-561">CC004</span><span class="sxs-lookup"><span data-stu-id="ec15d-561">CC004</span></span></td>
<td><span data-ttu-id="ec15d-562">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec15d-562">Packaging</span></span></td>
<td><span data-ttu-id="ec15d-563">10</span><span class="sxs-lookup"><span data-stu-id="ec15d-563">10</span></span></td>
<td><span data-ttu-id="ec15d-564">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="ec15d-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ec15d-565">124.57</span><span class="sxs-lookup"><span data-stu-id="ec15d-565">124.57</span></span></td>
<td><span data-ttu-id="ec15d-566">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-567">Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="ec15d-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-568">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-568">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-569">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec15d-569">Magnitude</span></span></th>
<th><span data-ttu-id="ec15d-570">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec15d-570">Allocation factor</span></span></th>
<th><span data-ttu-id="ec15d-571">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-571">Amount</span></span></th>
<th><span data-ttu-id="ec15d-572">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-573">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-573">CC003</span></span></td>
<td><span data-ttu-id="ec15d-574">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-574">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-575">65</span><span class="sxs-lookup"><span data-stu-id="ec15d-575">65</span></span></td>
<td><span data-ttu-id="ec15d-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="ec15d-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ec15d-577">438.75</span><span class="sxs-lookup"><span data-stu-id="ec15d-577">438.75</span></span></td>
<td><span data-ttu-id="ec15d-578">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-579">CC004</span><span class="sxs-lookup"><span data-stu-id="ec15d-579">CC004</span></span></td>
<td><span data-ttu-id="ec15d-580">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec15d-580">Packaging</span></span></td>
<td><span data-ttu-id="ec15d-581">35</span><span class="sxs-lookup"><span data-stu-id="ec15d-581">35</span></span></td>
<td><span data-ttu-id="ec15d-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="ec15d-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ec15d-583">236.25</span><span class="sxs-lookup"><span data-stu-id="ec15d-583">236.25</span></span></td>
<td><span data-ttu-id="ec15d-584">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-585">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-585">CC003</span></span></td>
<td><span data-ttu-id="ec15d-586">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-586">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-587">65</span><span class="sxs-lookup"><span data-stu-id="ec15d-587">65</span></span></td>
<td><span data-ttu-id="ec15d-588">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="ec15d-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ec15d-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ec15d-589">5,297.69</span></span></td>
<td><span data-ttu-id="ec15d-590">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-591">CC004</span><span class="sxs-lookup"><span data-stu-id="ec15d-591">CC004</span></span></td>
<td><span data-ttu-id="ec15d-592">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec15d-592">Packaging</span></span></td>
<td><span data-ttu-id="ec15d-593">35</span><span class="sxs-lookup"><span data-stu-id="ec15d-593">35</span></span></td>
<td><span data-ttu-id="ec15d-594">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="ec15d-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ec15d-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ec15d-595">2,852.60</span></span></td>
<td><span data-ttu-id="ec15d-596">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-597">Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="ec15d-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-598">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-598">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-599">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec15d-599">Magnitude</span></span></th>
<th><span data-ttu-id="ec15d-600">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec15d-600">Allocation factor</span></span></th>
<th><span data-ttu-id="ec15d-601">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-601">Amount</span></span></th>
<th><span data-ttu-id="ec15d-602">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-603">Prod 1</span></span></td>
<td><span data-ttu-id="ec15d-604">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-604">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-605">60</span><span class="sxs-lookup"><span data-stu-id="ec15d-605">60</span></span></td>
<td><span data-ttu-id="ec15d-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="ec15d-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ec15d-607">535.31</span><span class="sxs-lookup"><span data-stu-id="ec15d-607">535.31</span></span></td>
<td><span data-ttu-id="ec15d-608">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-609">Prod 2</span></span></td>
<td><span data-ttu-id="ec15d-610">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-610">Product 2</span></span></td>
<td><span data-ttu-id="ec15d-611">20</span><span class="sxs-lookup"><span data-stu-id="ec15d-611">20</span></span></td>
<td><span data-ttu-id="ec15d-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="ec15d-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ec15d-613">178.44</span><span class="sxs-lookup"><span data-stu-id="ec15d-613">178.44</span></span></td>
<td><span data-ttu-id="ec15d-614">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-615">Prod 1</span></span></td>
<td><span data-ttu-id="ec15d-616">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-616">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-617">60</span><span class="sxs-lookup"><span data-stu-id="ec15d-617">60</span></span></td>
<td><span data-ttu-id="ec15d-618">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="ec15d-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ec15d-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ec15d-619">4,487.12</span></span></td>
<td><span data-ttu-id="ec15d-620">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-621">Prod 2</span></span></td>
<td><span data-ttu-id="ec15d-622">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-622">Product 2</span></span></td>
<td><span data-ttu-id="ec15d-623">20</span><span class="sxs-lookup"><span data-stu-id="ec15d-623">20</span></span></td>
<td><span data-ttu-id="ec15d-624">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="ec15d-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ec15d-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ec15d-625">1,495.71</span></span></td>
<td><span data-ttu-id="ec15d-626">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec15d-627">Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="ec15d-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-628">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-628">Cost object</span></span></th>
<th><span data-ttu-id="ec15d-629">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec15d-629">Magnitude</span></span></th>
<th><span data-ttu-id="ec15d-630">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec15d-630">Allocation factor</span></span></th>
<th><span data-ttu-id="ec15d-631">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-631">Amount</span></span></th>
<th><span data-ttu-id="ec15d-632">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-633">Prod 1</span></span></td>
<td><span data-ttu-id="ec15d-634">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-634">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-635">80</span><span class="sxs-lookup"><span data-stu-id="ec15d-635">80</span></span></td>
<td><span data-ttu-id="ec15d-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="ec15d-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ec15d-637">241.05</span><span class="sxs-lookup"><span data-stu-id="ec15d-637">241.05</span></span></td>
<td><span data-ttu-id="ec15d-638">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-639">Prod 2</span></span></td>
<td><span data-ttu-id="ec15d-640">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-640">Product 2</span></span></td>
<td><span data-ttu-id="ec15d-641">15</span><span class="sxs-lookup"><span data-stu-id="ec15d-641">15</span></span></td>
<td><span data-ttu-id="ec15d-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="ec15d-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ec15d-643">45.20</span><span class="sxs-lookup"><span data-stu-id="ec15d-643">45.20</span></span></td>
<td><span data-ttu-id="ec15d-644">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-645">Prod 1</span></span></td>
<td><span data-ttu-id="ec15d-646">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-646">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-647">80</span><span class="sxs-lookup"><span data-stu-id="ec15d-647">80</span></span></td>
<td><span data-ttu-id="ec15d-648">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="ec15d-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ec15d-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ec15d-649">2,507.09</span></span></td>
<td><span data-ttu-id="ec15d-650">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-651">Prod 2</span></span></td>
<td><span data-ttu-id="ec15d-652">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-652">Product 2</span></span></td>
<td><span data-ttu-id="ec15d-653">15</span><span class="sxs-lookup"><span data-stu-id="ec15d-653">15</span></span></td>
<td><span data-ttu-id="ec15d-654">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="ec15d-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ec15d-655">470.08</span><span class="sxs-lookup"><span data-stu-id="ec15d-655">470.08</span></span></td>
<td><span data-ttu-id="ec15d-656">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ec15d-657">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="ec15d-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec15d-658">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec15d-658">Journal</span></span></th>
<th><span data-ttu-id="ec15d-659">Type de journal</span><span class="sxs-lookup"><span data-stu-id="ec15d-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ec15d-660">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="ec15d-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ec15d-661">Version</span><span class="sxs-lookup"><span data-stu-id="ec15d-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-662">00004</span><span class="sxs-lookup"><span data-stu-id="ec15d-662">00004</span></span></td>
<td><span data-ttu-id="ec15d-663">Journal de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="ec15d-664">Exercice</span><span class="sxs-lookup"><span data-stu-id="ec15d-664">Fiscal</span></span></td>
<td><span data-ttu-id="ec15d-665">2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-665">2017</span></span></td>
<td><span data-ttu-id="ec15d-666">Période 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-666">Period 1</span></span></td>
<td><span data-ttu-id="ec15d-667">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="ec15d-668">Lignes de journal</span><span class="sxs-lookup"><span data-stu-id="ec15d-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec15d-669">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec15d-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-670">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-671">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-671">Cost element</span></span></th>
<th><span data-ttu-id="ec15d-672">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-672">Cost behavior</span></span></th>
<th><span data-ttu-id="ec15d-673">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-674">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-675">CC001</span><span class="sxs-lookup"><span data-stu-id="ec15d-675">CC001</span></span></td>
<td><span data-ttu-id="ec15d-676">RH</span><span class="sxs-lookup"><span data-stu-id="ec15d-676">HR</span></span></td>
<td><span data-ttu-id="ec15d-677">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-677">10001</span></span></td>
<td><span data-ttu-id="ec15d-678">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-678">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-679">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-679">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-680">500,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-681">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-682">CC001</span><span class="sxs-lookup"><span data-stu-id="ec15d-682">CC001</span></span></td>
<td><span data-ttu-id="ec15d-683">RH</span><span class="sxs-lookup"><span data-stu-id="ec15d-683">HR</span></span></td>
<td><span data-ttu-id="ec15d-684">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-684">10001</span></span></td>
<td><span data-ttu-id="ec15d-685">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-685">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-686">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-686">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="ec15d-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-688">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-689">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-689">CC002</span></span></td>
<td><span data-ttu-id="ec15d-690">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-690">Finance</span></span></td>
<td><span data-ttu-id="ec15d-691">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-691">10001</span></span></td>
<td><span data-ttu-id="ec15d-692">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-692">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-693">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-693">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-694">675.00</span><span class="sxs-lookup"><span data-stu-id="ec15d-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-695">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-696">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-696">CC002</span></span></td>
<td><span data-ttu-id="ec15d-697">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-697">Finance</span></span></td>
<td><span data-ttu-id="ec15d-698">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-698">10001</span></span></td>
<td><span data-ttu-id="ec15d-699">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-699">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-700">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-700">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="ec15d-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-702">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-703">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-703">CC003</span></span></td>
<td><span data-ttu-id="ec15d-704">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-704">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-705">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-705">10001</span></span></td>
<td><span data-ttu-id="ec15d-706">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-706">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-707">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-707">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-708">713.75</span><span class="sxs-lookup"><span data-stu-id="ec15d-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-709">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-710">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-710">CC003</span></span></td>
<td><span data-ttu-id="ec15d-711">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-711">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-712">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-712">10001</span></span></td>
<td><span data-ttu-id="ec15d-713">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-713">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-714">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-714">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="ec15d-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-716">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-717">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-717">CC003</span></span></td>
<td><span data-ttu-id="ec15d-718">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec15d-718">Packaging</span></span></td>
<td><span data-ttu-id="ec15d-719">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-719">10001</span></span></td>
<td><span data-ttu-id="ec15d-720">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-720">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-721">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-721">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-722">286.25</span><span class="sxs-lookup"><span data-stu-id="ec15d-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-723">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-724">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-724">CC003</span></span></td>
<td><span data-ttu-id="ec15d-725">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec15d-725">Packaging</span></span></td>
<td><span data-ttu-id="ec15d-726">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-726">10001</span></span></td>
<td><span data-ttu-id="ec15d-727">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-727">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-728">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-728">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="ec15d-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-730">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-731">Prod 1</span></span></td>
<td><span data-ttu-id="ec15d-732">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-732">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-733">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-733">10001</span></span></td>
<td><span data-ttu-id="ec15d-734">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-734">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-735">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-735">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-736">776.36</span><span class="sxs-lookup"><span data-stu-id="ec15d-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-737">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-738">Prod 1</span></span></td>
<td><span data-ttu-id="ec15d-739">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-739">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-740">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-740">10001</span></span></td>
<td><span data-ttu-id="ec15d-741">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-741">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-742">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-742">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ec15d-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-744">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-745">Prod 2</span></span></td>
<td><span data-ttu-id="ec15d-746">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-746">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-747">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-747">10001</span></span></td>
<td><span data-ttu-id="ec15d-748">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-748">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-749">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-749">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-750">223.64</span><span class="sxs-lookup"><span data-stu-id="ec15d-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-751">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec15d-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-752">Prod 2</span></span></td>
<td><span data-ttu-id="ec15d-753">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-753">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-754">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-754">10001</span></span></td>
<td><span data-ttu-id="ec15d-755">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-755">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-756">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-756">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ec15d-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ec15d-758">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec15d-759">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec15d-760">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-760">Cost element</span></span></th>
<th><span data-ttu-id="ec15d-761">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec15d-761">Cost behavior</span></span></th>
<th><span data-ttu-id="ec15d-762">Montant</span><span class="sxs-lookup"><span data-stu-id="ec15d-762">Amount</span></span></th>
<th><span data-ttu-id="ec15d-763">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec15d-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec15d-764">CC001</span><span class="sxs-lookup"><span data-stu-id="ec15d-764">CC001</span></span></td>
<td><span data-ttu-id="ec15d-765">RH</span><span class="sxs-lookup"><span data-stu-id="ec15d-765">HR</span></span></td>
<td><span data-ttu-id="ec15d-766">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-766">10001</span></span></td>
<td><span data-ttu-id="ec15d-767">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-767">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-768">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-768">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-769">-500.00</span></span></td>
<td><span data-ttu-id="ec15d-770">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-771">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-771">CC002</span></span></td>
<td><span data-ttu-id="ec15d-772">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-772">Finance</span></span></td>
<td><span data-ttu-id="ec15d-773">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-773">10001</span></span></td>
<td><span data-ttu-id="ec15d-774">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-774">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-775">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-775">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-776">175.00</span><span class="sxs-lookup"><span data-stu-id="ec15d-776">175.00</span></span></td>
<td><span data-ttu-id="ec15d-777">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-778">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-778">CC003</span></span></td>
<td><span data-ttu-id="ec15d-779">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-779">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-780">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-780">10001</span></span></td>
<td><span data-ttu-id="ec15d-781">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-781">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-782">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-782">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-783">275.00</span><span class="sxs-lookup"><span data-stu-id="ec15d-783">275.00</span></span></td>
<td><span data-ttu-id="ec15d-784">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-785">CC004</span><span class="sxs-lookup"><span data-stu-id="ec15d-785">CC004</span></span></td>
<td><span data-ttu-id="ec15d-786">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec15d-786">Packaging</span></span></td>
<td><span data-ttu-id="ec15d-787">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-787">10001</span></span></td>
<td><span data-ttu-id="ec15d-788">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-788">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-789">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-789">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-790">50,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-790">50,00</span></span></td>
<td><span data-ttu-id="ec15d-791">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-792">CC001</span><span class="sxs-lookup"><span data-stu-id="ec15d-792">CC001</span></span></td>
<td><span data-ttu-id="ec15d-793">RH</span><span class="sxs-lookup"><span data-stu-id="ec15d-793">HR</span></span></td>
<td><span data-ttu-id="ec15d-794">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-794">10001</span></span></td>
<td><span data-ttu-id="ec15d-795">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-795">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-796">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-796">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-797">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="ec15d-797">-1,245.71</span></span></td>
<td><span data-ttu-id="ec15d-798">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-799">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-799">CC002</span></span></td>
<td><span data-ttu-id="ec15d-800">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-800">Finance</span></span></td>
<td><span data-ttu-id="ec15d-801">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-801">10001</span></span></td>
<td><span data-ttu-id="ec15d-802">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-802">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-803">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-803">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-804">436.00</span><span class="sxs-lookup"><span data-stu-id="ec15d-804">436.00</span></span></td>
<td><span data-ttu-id="ec15d-805">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-806">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-806">CC003</span></span></td>
<td><span data-ttu-id="ec15d-807">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-807">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-808">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-808">10001</span></span></td>
<td><span data-ttu-id="ec15d-809">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-809">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-810">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-810">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-811">685.14</span><span class="sxs-lookup"><span data-stu-id="ec15d-811">685.14</span></span></td>
<td><span data-ttu-id="ec15d-812">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-813">CC004</span><span class="sxs-lookup"><span data-stu-id="ec15d-813">CC004</span></span></td>
<td><span data-ttu-id="ec15d-814">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec15d-814">Packaging</span></span></td>
<td><span data-ttu-id="ec15d-815">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-815">10001</span></span></td>
<td><span data-ttu-id="ec15d-816">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-816">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-817">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-817">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-818">124.57</span><span class="sxs-lookup"><span data-stu-id="ec15d-818">124.57</span></span></td>
<td><span data-ttu-id="ec15d-819">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-820">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-820">CC002</span></span></td>
<td><span data-ttu-id="ec15d-821">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-821">Finance</span></span></td>
<td><span data-ttu-id="ec15d-822">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-822">10001</span></span></td>
<td><span data-ttu-id="ec15d-823">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-823">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-824">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-824">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-825">-675.00</span></span></td>
<td><span data-ttu-id="ec15d-826">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-827">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-827">CC003</span></span></td>
<td><span data-ttu-id="ec15d-828">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-828">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-829">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-829">10001</span></span></td>
<td><span data-ttu-id="ec15d-830">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-830">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-831">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-831">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-832">438.75</span><span class="sxs-lookup"><span data-stu-id="ec15d-832">438.75</span></span></td>
<td><span data-ttu-id="ec15d-833">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-834">CC004</span><span class="sxs-lookup"><span data-stu-id="ec15d-834">CC004</span></span></td>
<td><span data-ttu-id="ec15d-835">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec15d-835">Packaging</span></span></td>
<td><span data-ttu-id="ec15d-836">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-836">10001</span></span></td>
<td><span data-ttu-id="ec15d-837">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-837">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-838">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-838">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-839">236.25</span><span class="sxs-lookup"><span data-stu-id="ec15d-839">236.25</span></span></td>
<td><span data-ttu-id="ec15d-840">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-841">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-841">CC002</span></span></td>
<td><span data-ttu-id="ec15d-842">Finances</span><span class="sxs-lookup"><span data-stu-id="ec15d-842">Finance</span></span></td>
<td><span data-ttu-id="ec15d-843">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-843">10001</span></span></td>
<td><span data-ttu-id="ec15d-844">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-844">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-845">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-845">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-846">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="ec15d-846">-8,150.29</span></span></td>
<td><span data-ttu-id="ec15d-847">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-848">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-848">CC003</span></span></td>
<td><span data-ttu-id="ec15d-849">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-849">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-850">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-850">10001</span></span></td>
<td><span data-ttu-id="ec15d-851">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-851">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-852">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-852">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ec15d-853">5,297.69</span></span></td>
<td><span data-ttu-id="ec15d-854">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-855">CC004</span><span class="sxs-lookup"><span data-stu-id="ec15d-855">CC004</span></span></td>
<td><span data-ttu-id="ec15d-856">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec15d-856">Packaging</span></span></td>
<td><span data-ttu-id="ec15d-857">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-857">10001</span></span></td>
<td><span data-ttu-id="ec15d-858">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-858">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-859">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-859">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ec15d-860">2,852.60</span></span></td>
<td><span data-ttu-id="ec15d-861">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-862">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-862">CC003</span></span></td>
<td><span data-ttu-id="ec15d-863">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-863">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-864">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-864">10001</span></span></td>
<td><span data-ttu-id="ec15d-865">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-865">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-866">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-866">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="ec15d-867">-713.75</span></span></td>
<td><span data-ttu-id="ec15d-868">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-869">Prod 1</span></span></td>
<td><span data-ttu-id="ec15d-870">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-870">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-871">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-871">10001</span></span></td>
<td><span data-ttu-id="ec15d-872">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-872">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-873">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-873">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-874">535.31</span><span class="sxs-lookup"><span data-stu-id="ec15d-874">535.31</span></span></td>
<td><span data-ttu-id="ec15d-875">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-876">Prod 2</span></span></td>
<td><span data-ttu-id="ec15d-877">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-877">Product 2</span></span></td>
<td><span data-ttu-id="ec15d-878">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-878">10001</span></span></td>
<td><span data-ttu-id="ec15d-879">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-879">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-880">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-880">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-881">178.44</span><span class="sxs-lookup"><span data-stu-id="ec15d-881">178.44</span></span></td>
<td><span data-ttu-id="ec15d-882">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-883">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-883">CC003</span></span></td>
<td><span data-ttu-id="ec15d-884">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-884">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-885">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-885">10001</span></span></td>
<td><span data-ttu-id="ec15d-886">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-886">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-887">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-887">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-888">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="ec15d-888">-5,982.83</span></span></td>
<td><span data-ttu-id="ec15d-889">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-890">Prod 1</span></span></td>
<td><span data-ttu-id="ec15d-891">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-891">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-892">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-892">10001</span></span></td>
<td><span data-ttu-id="ec15d-893">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-893">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-894">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-894">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ec15d-895">4,487.12</span></span></td>
<td><span data-ttu-id="ec15d-896">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-897">Prod 2</span></span></td>
<td><span data-ttu-id="ec15d-898">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-898">Product 2</span></span></td>
<td><span data-ttu-id="ec15d-899">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-899">10001</span></span></td>
<td><span data-ttu-id="ec15d-900">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-900">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-901">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-901">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ec15d-902">1,495.71</span></span></td>
<td><span data-ttu-id="ec15d-903">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-904">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-904">CC003</span></span></td>
<td><span data-ttu-id="ec15d-905">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-905">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-906">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-906">10001</span></span></td>
<td><span data-ttu-id="ec15d-907">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-907">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-908">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-908">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="ec15d-909">-286.25</span></span></td>
<td><span data-ttu-id="ec15d-910">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-911">Prod 1</span></span></td>
<td><span data-ttu-id="ec15d-912">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-912">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-913">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-913">10001</span></span></td>
<td><span data-ttu-id="ec15d-914">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-914">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-915">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-915">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-916">241.05</span><span class="sxs-lookup"><span data-stu-id="ec15d-916">241.05</span></span></td>
<td><span data-ttu-id="ec15d-917">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-918">Prod 2</span></span></td>
<td><span data-ttu-id="ec15d-919">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-919">Product 2</span></span></td>
<td><span data-ttu-id="ec15d-920">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-920">10001</span></span></td>
<td><span data-ttu-id="ec15d-921">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-921">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-922">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-922">Fixed cost</span></span></td>
<td><span data-ttu-id="ec15d-923">45.20</span><span class="sxs-lookup"><span data-stu-id="ec15d-923">45.20</span></span></td>
<td><span data-ttu-id="ec15d-924">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-925">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-925">CC003</span></span></td>
<td><span data-ttu-id="ec15d-926">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec15d-926">Assembly</span></span></td>
<td><span data-ttu-id="ec15d-927">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-927">10001</span></span></td>
<td><span data-ttu-id="ec15d-928">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-928">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-929">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-929">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-930">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="ec15d-930">-2,977.17</span></span></td>
<td><span data-ttu-id="ec15d-931">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-932">Prod 1</span></span></td>
<td><span data-ttu-id="ec15d-933">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-933">Product 1</span></span></td>
<td><span data-ttu-id="ec15d-934">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-934">10001</span></span></td>
<td><span data-ttu-id="ec15d-935">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-935">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-936">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-936">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ec15d-937">2,507.09</span></span></td>
<td><span data-ttu-id="ec15d-938">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec15d-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-939">Prod 2</span></span></td>
<td><span data-ttu-id="ec15d-940">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-940">Product 2</span></span></td>
<td><span data-ttu-id="ec15d-941">10001</span><span class="sxs-lookup"><span data-stu-id="ec15d-941">10001</span></span></td>
<td><span data-ttu-id="ec15d-942">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-942">Electricity</span></span></td>
<td><span data-ttu-id="ec15d-943">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-943">Variable cost</span></span></td>
<td><span data-ttu-id="ec15d-944">470.08</span><span class="sxs-lookup"><span data-stu-id="ec15d-944">470.08</span></span></td>
<td><span data-ttu-id="ec15d-945">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec15d-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="ec15d-946">Conclusion</span><span class="sxs-lookup"><span data-stu-id="ec15d-946">Conclusion</span></span>
<span data-ttu-id="ec15d-947">Dans la comptabilité financière, un coût de 10 000,00 pour l'électricité est imputé sur un ID de centre de coût fictif.</span><span class="sxs-lookup"><span data-stu-id="ec15d-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="ec15d-948">Par conséquent, les comptables sauront que ce coût doit être affecté.</span><span class="sxs-lookup"><span data-stu-id="ec15d-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="ec15d-949">Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l'organisation, selon les stratégies et les règles qui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="ec15d-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="ec15d-950">Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="ec15d-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="ec15d-951">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="ec15d-952">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec15d-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="ec15d-953">Total</span><span class="sxs-lookup"><span data-stu-id="ec15d-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ec15d-954">CC099</span><span class="sxs-lookup"><span data-stu-id="ec15d-954">CC099</span></span></th>
<th><span data-ttu-id="ec15d-955">CC001</span><span class="sxs-lookup"><span data-stu-id="ec15d-955">CC001</span></span></th>
<th><span data-ttu-id="ec15d-956">CC002</span><span class="sxs-lookup"><span data-stu-id="ec15d-956">CC002</span></span></th>
<th><span data-ttu-id="ec15d-957">CC003</span><span class="sxs-lookup"><span data-stu-id="ec15d-957">CC003</span></span></th>
<th><span data-ttu-id="ec15d-958">CC004</span><span class="sxs-lookup"><span data-stu-id="ec15d-958">CC004</span></span></th>
<th><span data-ttu-id="ec15d-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-959">Proj 1</span></span></th>
<th><span data-ttu-id="ec15d-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-960">Proj 2</span></span></th>
<th><span data-ttu-id="ec15d-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec15d-961">Prod 1</span></span></th>
<th><span data-ttu-id="ec15d-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec15d-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="ec15d-963">10001 Électricité</span><span class="sxs-lookup"><span data-stu-id="ec15d-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec15d-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec15d-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec15d-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec15d-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec15d-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec15d-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="ec15d-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="ec15d-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec15d-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="ec15d-973">Non classifié</span><span class="sxs-lookup"><span data-stu-id="ec15d-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-974">0,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="ec15d-975">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec15d-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-976">0,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-977">0,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-978">0,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-979">0,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-980">0,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-981">776.36</span><span class="sxs-lookup"><span data-stu-id="ec15d-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-982">223.64</span><span class="sxs-lookup"><span data-stu-id="ec15d-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-983"><strong>1 000,00</strong></span><span class="sxs-lookup"><span data-stu-id="ec15d-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="ec15d-984">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec15d-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-985">000</span><span class="sxs-lookup"><span data-stu-id="ec15d-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-986">0,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-987">0,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-988">0,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-989">0,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-990">30,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-991">10,00</span><span class="sxs-lookup"><span data-stu-id="ec15d-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ec15d-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ec15d-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec15d-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec15d-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ec15d-995">Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût.</span><span class="sxs-lookup"><span data-stu-id="ec15d-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="ec15d-996">Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l'organisation.</span><span class="sxs-lookup"><span data-stu-id="ec15d-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="ec15d-997">Autrement dit, les objets de coût de plus bas niveau supportent le coût.</span><span class="sxs-lookup"><span data-stu-id="ec15d-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="ec15d-998">Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec15d-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="ec15d-999">Pour plus d'informations, voir la stratégie de repositionnement des coûts.</span><span class="sxs-lookup"><span data-stu-id="ec15d-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="ec15d-1000">(Notez que cette rubrique n'est pas complète et sera bientôt mise à jour.)</span><span class="sxs-lookup"><span data-stu-id="ec15d-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




