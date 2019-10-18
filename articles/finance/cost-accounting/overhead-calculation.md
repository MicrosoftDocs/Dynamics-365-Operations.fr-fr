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
ms.openlocfilehash: 6c045f82f3288dba193721dd80c90e68750af9a7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177736"
---
# <a name="overhead-calculation"></a><span data-ttu-id="ec916-103">Calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="ec916-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ec916-104">Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.</span><span class="sxs-lookup"><span data-stu-id="ec916-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="ec916-105">Définition des termes</span><span class="sxs-lookup"><span data-stu-id="ec916-105">Term definition</span></span>
---------------

<span data-ttu-id="ec916-106">Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique.</span><span class="sxs-lookup"><span data-stu-id="ec916-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="ec916-107">Les frais généraux permettent essentiellement l'identification des activités rémunératrices.</span><span class="sxs-lookup"><span data-stu-id="ec916-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="ec916-108">Voici quelques exemples de frais généraux :</span><span class="sxs-lookup"><span data-stu-id="ec916-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="ec916-109">Loyer</span><span class="sxs-lookup"><span data-stu-id="ec916-109">Rent</span></span>
-   <span data-ttu-id="ec916-110">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-110">Electricity</span></span>
-   <span data-ttu-id="ec916-111">Salaires administratifs</span><span class="sxs-lookup"><span data-stu-id="ec916-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="ec916-112">Vue d'ensemble du calcul des frais généraux</span><span class="sxs-lookup"><span data-stu-id="ec916-112">Overhead calculation overview</span></span>
<span data-ttu-id="ec916-113">Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l'ordre correct.</span><span class="sxs-lookup"><span data-stu-id="ec916-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="ec916-114">Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées.</span><span class="sxs-lookup"><span data-stu-id="ec916-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="ec916-115">Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions.</span><span class="sxs-lookup"><span data-stu-id="ec916-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="ec916-116">Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable.</span><span class="sxs-lookup"><span data-stu-id="ec916-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="ec916-117">Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="ec916-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="ec916-118">L'ID de version unique inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ec916-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="ec916-119">Type de version</span><span class="sxs-lookup"><span data-stu-id="ec916-119">Version type</span></span>
-   <span data-ttu-id="ec916-120">Date et heure</span><span class="sxs-lookup"><span data-stu-id="ec916-120">Date and time</span></span>
-   <span data-ttu-id="ec916-121">Comptabilité de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="ec916-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="ec916-122">Exercice</span><span class="sxs-lookup"><span data-stu-id="ec916-122">Fiscal year</span></span>
-   <span data-ttu-id="ec916-123">Période fiscale</span><span class="sxs-lookup"><span data-stu-id="ec916-123">Fiscal period</span></span>

<span data-ttu-id="ec916-124">Le calcul des frais généraux est effectué indépendamment de la version.</span><span class="sxs-lookup"><span data-stu-id="ec916-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="ec916-125">Par conséquent, vous pouvez calculer la version de budget avant la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="ec916-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="ec916-126">Le calcul des frais généraux comporte quatre étapes, comme le montre l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="ec916-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="ec916-127">Dans chaque étape, un en-tête de journal avec des entrées de journal est créé.</span><span class="sxs-lookup"><span data-stu-id="ec916-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="ec916-128">Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul.</span><span class="sxs-lookup"><span data-stu-id="ec916-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="ec916-129">Les stratégies et les règles s'appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie.</span><span class="sxs-lookup"><span data-stu-id="ec916-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="ec916-130">Par conséquent, vous disposez toujours d'une traçabilité complète.</span><span class="sxs-lookup"><span data-stu-id="ec916-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="ec916-131">[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="ec916-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="ec916-132">Calculer et affecter les frais généraux Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="ec916-133">Dans la comptabilité financière, certaines coûts, tels que l'électricité, sont enregistrés comme montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="ec916-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="ec916-134">Par conséquent, l'analyse détaillée n'est pas fournie pour le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="ec916-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="ec916-135">Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l'organisation, les coûts doivent suivre les unités organisationnelles.</span><span class="sxs-lookup"><span data-stu-id="ec916-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="ec916-136">Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste.</span><span class="sxs-lookup"><span data-stu-id="ec916-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="ec916-137">Dans la comptabilité, le coût de l'électricité peut être validé comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="ec916-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec916-138">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec916-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-139">Centre de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-140">Compte principal</span><span class="sxs-lookup"><span data-stu-id="ec916-140">Main account</span></span></th>
<th><span data-ttu-id="ec916-141">Montant en devise comptable</span><span class="sxs-lookup"><span data-stu-id="ec916-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-142">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="ec916-143">CC099</span><span class="sxs-lookup"><span data-stu-id="ec916-143">CC099</span></span></td>
<td><span data-ttu-id="ec916-144">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec916-144">Default cost center</span></span></td>
<td><span data-ttu-id="ec916-145">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-145">10001</span></span></td>
<td><span data-ttu-id="ec916-146">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-146">Electricity</span></span></td>
<td><span data-ttu-id="ec916-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="ec916-148">Étape 1 : Traiter le calcul du comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="ec916-149">Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="ec916-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="ec916-150">Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.</span><span class="sxs-lookup"><span data-stu-id="ec916-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="ec916-151">Définir la règle de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-151">Define the cost behavior rule</span></span>

<span data-ttu-id="ec916-152">Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation.</span><span class="sxs-lookup"><span data-stu-id="ec916-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="ec916-153">Les factures d'électricité correspondent souvent à cette définition.</span><span class="sxs-lookup"><span data-stu-id="ec916-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="ec916-154">Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH).</span><span class="sxs-lookup"><span data-stu-id="ec916-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="ec916-155">Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :</span><span class="sxs-lookup"><span data-stu-id="ec916-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="ec916-156">Montant fixe 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="ec916-157">0 &lt;= 1 000,00 = Fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="ec916-158">1 000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="ec916-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="ec916-159">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec916-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec916-160">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec916-160">Journal</span></span></th>
<th><span data-ttu-id="ec916-161">Type de journal</span><span class="sxs-lookup"><span data-stu-id="ec916-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ec916-162">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="ec916-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ec916-163">Version</span><span class="sxs-lookup"><span data-stu-id="ec916-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-164">00001</span><span class="sxs-lookup"><span data-stu-id="ec916-164">00001</span></span></td>
<td><span data-ttu-id="ec916-165">Journal de calcul de comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="ec916-166">Exercice</span><span class="sxs-lookup"><span data-stu-id="ec916-166">Fiscal</span></span></td>
<td><span data-ttu-id="ec916-167">2017</span><span class="sxs-lookup"><span data-stu-id="ec916-167">2017</span></span></td>
<td><span data-ttu-id="ec916-168">Période 1</span><span class="sxs-lookup"><span data-stu-id="ec916-168">Period 1</span></span></td>
<td><span data-ttu-id="ec916-169">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="ec916-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ec916-170">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="ec916-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec916-171">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec916-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-172">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-173">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-173">Cost element</span></span></th>
<th><span data-ttu-id="ec916-174">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-174">Cost behavior</span></span></th>
<th><span data-ttu-id="ec916-175">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-176">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="ec916-177">CC099</span><span class="sxs-lookup"><span data-stu-id="ec916-177">CC099</span></span></td>
<td><span data-ttu-id="ec916-178">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec916-178">Default cost center</span></span></td>
<td><span data-ttu-id="ec916-179">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-179">10001</span></span></td>
<td><span data-ttu-id="ec916-180">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-180">Electricity</span></span></td>
<td><span data-ttu-id="ec916-181">Non classifié</span><span class="sxs-lookup"><span data-stu-id="ec916-181">Unclassified</span></span></td>
<td><span data-ttu-id="ec916-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ec916-183">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-184">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-185">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-185">Cost element</span></span></th>
<th><span data-ttu-id="ec916-186">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-186">Cost behavior</span></span></th>
<th><span data-ttu-id="ec916-187">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-187">Amount</span></span></th>
<th><span data-ttu-id="ec916-188">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec916-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-189">CC099</span><span class="sxs-lookup"><span data-stu-id="ec916-189">CC099</span></span></td>
<td><span data-ttu-id="ec916-190">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec916-190">Default cost center</span></span></td>
<td><span data-ttu-id="ec916-191">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-191">10001</span></span></td>
<td><span data-ttu-id="ec916-192">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-192">Electricity</span></span></td>
<td><span data-ttu-id="ec916-193">Non classifié</span><span class="sxs-lookup"><span data-stu-id="ec916-193">Unclassified</span></span></td>
<td><span data-ttu-id="ec916-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-194">10,000.00</span></span></td>
<td><span data-ttu-id="ec916-195">3 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-196">CC099</span><span class="sxs-lookup"><span data-stu-id="ec916-196">CC099</span></span></td>
<td><span data-ttu-id="ec916-197">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec916-197">Default cost center</span></span></td>
<td><span data-ttu-id="ec916-198">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-198">10001</span></span></td>
<td><span data-ttu-id="ec916-199">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-199">Electricity</span></span></td>
<td><span data-ttu-id="ec916-200">Non classifié</span><span class="sxs-lookup"><span data-stu-id="ec916-200">Unclassified</span></span></td>
<td><span data-ttu-id="ec916-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-201">-10,000.00</span></span></td>
<td><span data-ttu-id="ec916-202">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-203">CC099</span><span class="sxs-lookup"><span data-stu-id="ec916-203">CC099</span></span></td>
<td><span data-ttu-id="ec916-204">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec916-204">Default cost center</span></span></td>
<td><span data-ttu-id="ec916-205">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-205">10001</span></span></td>
<td><span data-ttu-id="ec916-206">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-206">Electricity</span></span></td>
<td><span data-ttu-id="ec916-207">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-207">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-208">1,000.00</span></span></td>
<td><span data-ttu-id="ec916-209">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-210">CC099</span><span class="sxs-lookup"><span data-stu-id="ec916-210">CC099</span></span></td>
<td><span data-ttu-id="ec916-211">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec916-211">Default cost center</span></span></td>
<td><span data-ttu-id="ec916-212">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-212">10001</span></span></td>
<td><span data-ttu-id="ec916-213">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-213">Electricity</span></span></td>
<td><span data-ttu-id="ec916-214">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-214">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-215">9 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-215">9,000.00</span></span></td>
<td><span data-ttu-id="ec916-216">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-217">Pour plus d'informations, voir [Créer et affecter une stratégie de comportement de coûts à une unité de contrôle des coûts](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="ec916-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="ec916-218">Étape 2 : Traiter le calcul de distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="ec916-219">La distribution des coûts est utilisée pour redistribuer le coût d'un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée.</span><span class="sxs-lookup"><span data-stu-id="ec916-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="ec916-220">La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l'élément de coût principal du coût d'origine.</span><span class="sxs-lookup"><span data-stu-id="ec916-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="ec916-221">Définir la règle de distribution de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-221">Define the cost distribution rule</span></span>

<span data-ttu-id="ec916-222">Dans la comptabilité financière, les coûts d'électricité sont souvent enregistrés comme un montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="ec916-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="ec916-223">Dans le Contrôle de gestion, cette approche n'est pas assez détaillée.</span><span class="sxs-lookup"><span data-stu-id="ec916-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="ec916-224">Le coût variable doit être attribué aux différents objets de coûts sur une base juste.</span><span class="sxs-lookup"><span data-stu-id="ec916-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="ec916-225">La base de répartition la plus logique est la consommation de l'électricité (KWH).</span><span class="sxs-lookup"><span data-stu-id="ec916-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="ec916-226">Un membre de dimension statistique nommé Électricité est créé, et la consommation d'électricité est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="ec916-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="ec916-227">Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="ec916-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-228">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-228">Cost object</span></span></th>
<th><span data-ttu-id="ec916-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="ec916-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-230">CC001</span><span class="sxs-lookup"><span data-stu-id="ec916-230">CC001</span></span></td>
<td><span data-ttu-id="ec916-231">RH</span><span class="sxs-lookup"><span data-stu-id="ec916-231">HR</span></span></td>
<td><span data-ttu-id="ec916-232">1 000</span><span class="sxs-lookup"><span data-stu-id="ec916-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-233">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-233">CC002</span></span></td>
<td><span data-ttu-id="ec916-234">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-234">Finance</span></span></td>
<td><span data-ttu-id="ec916-235">6 000</span><span class="sxs-lookup"><span data-stu-id="ec916-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-236">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-236">CC003</span></span></td>
<td><span data-ttu-id="ec916-237">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-237">Assembly</span></span></td>
<td><span data-ttu-id="ec916-238">0</span><span class="sxs-lookup"><span data-stu-id="ec916-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-239">Le tableau suivant illustre le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="ec916-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-240">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-240">Cost object</span></span></th>
<th><span data-ttu-id="ec916-241">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec916-241">Magnitude</span></span></th>
<th><span data-ttu-id="ec916-242">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec916-242">Allocation factor</span></span></th>
<th><span data-ttu-id="ec916-243">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-244">CC001</span><span class="sxs-lookup"><span data-stu-id="ec916-244">CC001</span></span></td>
<td><span data-ttu-id="ec916-245">RH</span><span class="sxs-lookup"><span data-stu-id="ec916-245">HR</span></span></td>
<td><span data-ttu-id="ec916-246">1 000</span><span class="sxs-lookup"><span data-stu-id="ec916-246">1,000</span></span></td>
<td><span data-ttu-id="ec916-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ec916-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ec916-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-249">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-249">CC002</span></span></td>
<td><span data-ttu-id="ec916-250">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-250">Finance</span></span></td>
<td><span data-ttu-id="ec916-251">6 000</span><span class="sxs-lookup"><span data-stu-id="ec916-251">6,000</span></span></td>
<td><span data-ttu-id="ec916-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ec916-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ec916-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-254">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-254">CC003</span></span></td>
<td><span data-ttu-id="ec916-255">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-255">Assembly</span></span></td>
<td><span data-ttu-id="ec916-256">0</span><span class="sxs-lookup"><span data-stu-id="ec916-256">0</span></span></td>
<td><span data-ttu-id="ec916-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ec916-258">0,00</span><span class="sxs-lookup"><span data-stu-id="ec916-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-259">Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l'électricité.</span><span class="sxs-lookup"><span data-stu-id="ec916-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="ec916-260">Vous pouvez obtenir ce résultat à l'aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d'électricité est appliquée comme base de répartition de coûts variables.</span><span class="sxs-lookup"><span data-stu-id="ec916-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-261">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-261">Cost object</span></span></th>
<th><span data-ttu-id="ec916-262">Formule</span><span class="sxs-lookup"><span data-stu-id="ec916-262">Formula</span></span></th>
<th><span data-ttu-id="ec916-263">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec916-263">Magnitude</span></span></th>
<th><span data-ttu-id="ec916-264">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec916-264">Allocation factor</span></span></th>
<th><span data-ttu-id="ec916-265">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-266">CC001</span><span class="sxs-lookup"><span data-stu-id="ec916-266">CC001</span></span></td>
<td><span data-ttu-id="ec916-267">RH</span><span class="sxs-lookup"><span data-stu-id="ec916-267">HR</span></span></td>
<td><span data-ttu-id="ec916-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ec916-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ec916-269">1</span><span class="sxs-lookup"><span data-stu-id="ec916-269">1</span></span></td>
<td><span data-ttu-id="ec916-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ec916-271">500,00</span><span class="sxs-lookup"><span data-stu-id="ec916-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-272">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-272">CC002</span></span></td>
<td><span data-ttu-id="ec916-273">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-273">Finance</span></span></td>
<td><span data-ttu-id="ec916-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ec916-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ec916-275">1</span><span class="sxs-lookup"><span data-stu-id="ec916-275">1</span></span></td>
<td><span data-ttu-id="ec916-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ec916-277">500,00</span><span class="sxs-lookup"><span data-stu-id="ec916-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-278">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-278">CC003</span></span></td>
<td><span data-ttu-id="ec916-279">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-279">Assembly</span></span></td>
<td><span data-ttu-id="ec916-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ec916-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ec916-281">0</span><span class="sxs-lookup"><span data-stu-id="ec916-281">0</span></span></td>
<td><span data-ttu-id="ec916-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ec916-283">0,00</span><span class="sxs-lookup"><span data-stu-id="ec916-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ec916-284">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec916-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec916-285">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec916-285">Journal</span></span></th>
<th><span data-ttu-id="ec916-286">Type de journal</span><span class="sxs-lookup"><span data-stu-id="ec916-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ec916-287">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="ec916-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ec916-288">Version</span><span class="sxs-lookup"><span data-stu-id="ec916-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-289">00002</span><span class="sxs-lookup"><span data-stu-id="ec916-289">00002</span></span></td>
<td><span data-ttu-id="ec916-290">Journal de calcul de la distribution des coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="ec916-291">Exercice</span><span class="sxs-lookup"><span data-stu-id="ec916-291">Fiscal</span></span></td>
<td><span data-ttu-id="ec916-292">2017</span><span class="sxs-lookup"><span data-stu-id="ec916-292">2017</span></span></td>
<td><span data-ttu-id="ec916-293">Période 1</span><span class="sxs-lookup"><span data-stu-id="ec916-293">Period 1</span></span></td>
<td><span data-ttu-id="ec916-294">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="ec916-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ec916-295">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="ec916-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec916-296">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec916-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-297">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-298">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-298">Cost element</span></span></th>
<th><span data-ttu-id="ec916-299">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-299">Cost behavior</span></span></th>
<th><span data-ttu-id="ec916-300">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-301">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-302">CC099</span><span class="sxs-lookup"><span data-stu-id="ec916-302">CC099</span></span></td>
<td><span data-ttu-id="ec916-303">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec916-303">Default cost center</span></span></td>
<td><span data-ttu-id="ec916-304">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-304">10001</span></span></td>
<td><span data-ttu-id="ec916-305">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-305">Electricity</span></span></td>
<td><span data-ttu-id="ec916-306">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-306">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-308">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-309">CC099</span><span class="sxs-lookup"><span data-stu-id="ec916-309">CC099</span></span></td>
<td><span data-ttu-id="ec916-310">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec916-310">Default cost center</span></span></td>
<td><span data-ttu-id="ec916-311">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-311">10001</span></span></td>
<td><span data-ttu-id="ec916-312">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-312">Electricity</span></span></td>
<td><span data-ttu-id="ec916-313">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-313">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-314">9 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ec916-315">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-316">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-317">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-317">Cost element</span></span></th>
<th><span data-ttu-id="ec916-318">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-318">Cost behavior</span></span></th>
<th><span data-ttu-id="ec916-319">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-319">Amount</span></span></th>
<th><span data-ttu-id="ec916-320">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec916-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-321">CC099</span><span class="sxs-lookup"><span data-stu-id="ec916-321">CC099</span></span></td>
<td><span data-ttu-id="ec916-322">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec916-322">Default cost center</span></span></td>
<td><span data-ttu-id="ec916-323">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-323">10001</span></span></td>
<td><span data-ttu-id="ec916-324">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-324">Electricity</span></span></td>
<td><span data-ttu-id="ec916-325">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-325">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-326">-1,000.00</span></span></td>
<td><span data-ttu-id="ec916-327">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-328">CC001</span><span class="sxs-lookup"><span data-stu-id="ec916-328">CC001</span></span></td>
<td><span data-ttu-id="ec916-329">RH</span><span class="sxs-lookup"><span data-stu-id="ec916-329">HR</span></span></td>
<td><span data-ttu-id="ec916-330">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-330">10001</span></span></td>
<td><span data-ttu-id="ec916-331">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-331">Electricity</span></span></td>
<td><span data-ttu-id="ec916-332">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-332">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-333">500,00</span><span class="sxs-lookup"><span data-stu-id="ec916-333">500.00</span></span></td>
<td><span data-ttu-id="ec916-334">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-335">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-335">CC002</span></span></td>
<td><span data-ttu-id="ec916-336">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-336">Finance</span></span></td>
<td><span data-ttu-id="ec916-337">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-337">10001</span></span></td>
<td><span data-ttu-id="ec916-338">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-338">Electricity</span></span></td>
<td><span data-ttu-id="ec916-339">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-339">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-340">500,00</span><span class="sxs-lookup"><span data-stu-id="ec916-340">500.00</span></span></td>
<td><span data-ttu-id="ec916-341">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-342">CC099</span><span class="sxs-lookup"><span data-stu-id="ec916-342">CC099</span></span></td>
<td><span data-ttu-id="ec916-343">Centre de coût par défaut</span><span class="sxs-lookup"><span data-stu-id="ec916-343">Default cost center</span></span></td>
<td><span data-ttu-id="ec916-344">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-344">10001</span></span></td>
<td><span data-ttu-id="ec916-345">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-345">Electricity</span></span></td>
<td><span data-ttu-id="ec916-346">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-346">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="ec916-347">-9,000.00</span></span></td>
<td><span data-ttu-id="ec916-348">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-349">CC001</span><span class="sxs-lookup"><span data-stu-id="ec916-349">CC001</span></span></td>
<td><span data-ttu-id="ec916-350">RH</span><span class="sxs-lookup"><span data-stu-id="ec916-350">HR</span></span></td>
<td><span data-ttu-id="ec916-351">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-351">10001</span></span></td>
<td><span data-ttu-id="ec916-352">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-352">Electricity</span></span></td>
<td><span data-ttu-id="ec916-353">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-353">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ec916-354">1,285.71</span></span></td>
<td><span data-ttu-id="ec916-355">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-356">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-356">CC002</span></span></td>
<td><span data-ttu-id="ec916-357">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-357">Finance</span></span></td>
<td><span data-ttu-id="ec916-358">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-358">10001</span></span></td>
<td><span data-ttu-id="ec916-359">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-359">Electricity</span></span></td>
<td><span data-ttu-id="ec916-360">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-360">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ec916-361">7,714.29</span></span></td>
<td><span data-ttu-id="ec916-362">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-363">Pour plus d'informations, voir [Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="ec916-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="ec916-364">Étape 3 : Traitement du calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="ec916-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="ec916-365">Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût.</span><span class="sxs-lookup"><span data-stu-id="ec916-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="ec916-366">Les frais sont basés sur un taux de coût prédéterminé et l'ampleur de la base d'affectation de répartition.</span><span class="sxs-lookup"><span data-stu-id="ec916-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="ec916-367">Définition du taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="ec916-367">Define the overhead rate</span></span>

<span data-ttu-id="ec916-368">L'objet de coût CC001 HR contribue à un ensemble de projets internes.</span><span class="sxs-lookup"><span data-stu-id="ec916-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="ec916-369">Un membre de dimension statistique nommé Projets HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ec916-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-370">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-370">Cost object</span></span></th>
<th><span data-ttu-id="ec916-371">Heures</span><span class="sxs-lookup"><span data-stu-id="ec916-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ec916-372">Proj 1</span></span></td>
<td><span data-ttu-id="ec916-373">Projet 1</span><span class="sxs-lookup"><span data-stu-id="ec916-373">Project 1</span></span></td>
<td><span data-ttu-id="ec916-374">3</span><span class="sxs-lookup"><span data-stu-id="ec916-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ec916-375">Proj 2</span></span></td>
<td><span data-ttu-id="ec916-376">Projet 2</span><span class="sxs-lookup"><span data-stu-id="ec916-376">Project 2</span></span></td>
<td><span data-ttu-id="ec916-377">1</span><span class="sxs-lookup"><span data-stu-id="ec916-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-378">Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.</span><span class="sxs-lookup"><span data-stu-id="ec916-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-379">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-379">Cost object</span></span></th>
<th><span data-ttu-id="ec916-380">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-380">Cost element</span></span></th>
<th><span data-ttu-id="ec916-381">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-381">Cost behavior</span></span></th>
<th><span data-ttu-id="ec916-382">Unités</span><span class="sxs-lookup"><span data-stu-id="ec916-382">Units</span></span></th>
<th><span data-ttu-id="ec916-383">Taux</span><span class="sxs-lookup"><span data-stu-id="ec916-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-384">CC001</span><span class="sxs-lookup"><span data-stu-id="ec916-384">CC001</span></span></td>
<td><span data-ttu-id="ec916-385">RH</span><span class="sxs-lookup"><span data-stu-id="ec916-385">HR</span></span></td>
<td><span data-ttu-id="ec916-386">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-386">10001</span></span></td>
<td><span data-ttu-id="ec916-387">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-387">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-388">1</span><span class="sxs-lookup"><span data-stu-id="ec916-388">1</span></span></td>
<td><span data-ttu-id="ec916-389">10</span><span class="sxs-lookup"><span data-stu-id="ec916-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-390">Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.</span><span class="sxs-lookup"><span data-stu-id="ec916-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-391">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-391">Cost object</span></span></th>
<th><span data-ttu-id="ec916-392">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec916-392">Magnitude</span></span></th>
<th><span data-ttu-id="ec916-393">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-393">Cost element</span></span></th>
<th><span data-ttu-id="ec916-394">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec916-394">Allocation factor</span></span></th>
<th><span data-ttu-id="ec916-395">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ec916-396">Proj 1</span></span></td>
<td><span data-ttu-id="ec916-397">Projet 1</span><span class="sxs-lookup"><span data-stu-id="ec916-397">Project 1</span></span></td>
<td><span data-ttu-id="ec916-398">3</span><span class="sxs-lookup"><span data-stu-id="ec916-398">3</span></span></td>
<td><span data-ttu-id="ec916-399">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-399">10001</span></span></td>
<td><span data-ttu-id="ec916-400">(3 ÷ 1) × 10m00</span><span class="sxs-lookup"><span data-stu-id="ec916-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ec916-401">30,00</span><span class="sxs-lookup"><span data-stu-id="ec916-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ec916-402">Proj 2</span></span></td>
<td><span data-ttu-id="ec916-403">Projet 2</span><span class="sxs-lookup"><span data-stu-id="ec916-403">Project 2</span></span></td>
<td><span data-ttu-id="ec916-404">1</span><span class="sxs-lookup"><span data-stu-id="ec916-404">1</span></span></td>
<td><span data-ttu-id="ec916-405">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-405">10001</span></span></td>
<td><span data-ttu-id="ec916-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="ec916-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ec916-407">10,00</span><span class="sxs-lookup"><span data-stu-id="ec916-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ec916-408">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec916-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec916-409">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec916-409">Journal</span></span></th>
<th><span data-ttu-id="ec916-410">Type de journal</span><span class="sxs-lookup"><span data-stu-id="ec916-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ec916-411">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="ec916-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ec916-412">Version</span><span class="sxs-lookup"><span data-stu-id="ec916-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-413">00003</span><span class="sxs-lookup"><span data-stu-id="ec916-413">00003</span></span></td>
<td><span data-ttu-id="ec916-414">Journal de calcul de taux de frais généraux</span><span class="sxs-lookup"><span data-stu-id="ec916-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="ec916-415">Exercice</span><span class="sxs-lookup"><span data-stu-id="ec916-415">Fiscal</span></span></td>
<td><span data-ttu-id="ec916-416">2017</span><span class="sxs-lookup"><span data-stu-id="ec916-416">2017</span></span></td>
<td><span data-ttu-id="ec916-417">Période 1</span><span class="sxs-lookup"><span data-stu-id="ec916-417">Period 1</span></span></td>
<td><span data-ttu-id="ec916-418">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="ec916-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="ec916-419">Entrées du journal (pour le calcul du taux de frais généraux)</span><span class="sxs-lookup"><span data-stu-id="ec916-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec916-420">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec916-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-421">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-421">Cost object</span></span></th>
<th><span data-ttu-id="ec916-422">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec916-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-423">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ec916-424">Proj 1</span></span></td>
<td><span data-ttu-id="ec916-425">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="ec916-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ec916-426">3,00</span><span class="sxs-lookup"><span data-stu-id="ec916-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-427">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ec916-428">Proj 2</span></span></td>
<td><span data-ttu-id="ec916-429">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="ec916-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ec916-430">1,00</span><span class="sxs-lookup"><span data-stu-id="ec916-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ec916-431">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-432">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-433">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-433">Cost element</span></span></th>
<th><span data-ttu-id="ec916-434">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-434">Cost behavior</span></span></th>
<th><span data-ttu-id="ec916-435">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-435">Amount</span></span></th>
<th><span data-ttu-id="ec916-436">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec916-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="ec916-437">CC0001</span></span></td>
<td><span data-ttu-id="ec916-438">RH</span><span class="sxs-lookup"><span data-stu-id="ec916-438">HR</span></span></td>
<td><span data-ttu-id="ec916-439">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-439">10001</span></span></td>
<td><span data-ttu-id="ec916-440">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-440">Electricity</span></span></td>
<td><span data-ttu-id="ec916-441">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-441">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="ec916-442">-30.00</span></span></td>
<td><span data-ttu-id="ec916-443">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ec916-444">Proj 1</span></span></td>
<td><span data-ttu-id="ec916-445">Projet interne 1</span><span class="sxs-lookup"><span data-stu-id="ec916-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ec916-446">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-446">10001</span></span></td>
<td><span data-ttu-id="ec916-447">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-447">Electricity</span></span></td>
<td><span data-ttu-id="ec916-448">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-448">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-449">30,00</span><span class="sxs-lookup"><span data-stu-id="ec916-449">30.00</span></span></td>
<td><span data-ttu-id="ec916-450">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-451">CC001</span><span class="sxs-lookup"><span data-stu-id="ec916-451">CC001</span></span></td>
<td><span data-ttu-id="ec916-452">RH</span><span class="sxs-lookup"><span data-stu-id="ec916-452">HR</span></span></td>
<td><span data-ttu-id="ec916-453">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-453">10001</span></span></td>
<td><span data-ttu-id="ec916-454">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-454">Electricity</span></span></td>
<td><span data-ttu-id="ec916-455">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-455">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="ec916-456">-10.00</span></span></td>
<td><span data-ttu-id="ec916-457">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ec916-458">Proj 2</span></span></td>
<td><span data-ttu-id="ec916-459">Projet interne 2</span><span class="sxs-lookup"><span data-stu-id="ec916-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ec916-460">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-460">10001</span></span></td>
<td><span data-ttu-id="ec916-461">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-461">Electricity</span></span></td>
<td><span data-ttu-id="ec916-462">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-462">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-463">10.00</span><span class="sxs-lookup"><span data-stu-id="ec916-463">10.00</span></span></td>
<td><span data-ttu-id="ec916-464">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-465">Pour plus d'informations, voir [Exécuter le calcul des frais généraux](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="ec916-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="ec916-466">Étape 4 : Traiter le calcul de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="ec916-467">La répartition est utilisée pour affecter le solde d'un objet de coût à d'autres objets de coût en appliquant une base de répartition.</span><span class="sxs-lookup"><span data-stu-id="ec916-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="ec916-468">Finance prend en charge la méthode de répartition réciproque.</span><span class="sxs-lookup"><span data-stu-id="ec916-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="ec916-469">Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés.</span><span class="sxs-lookup"><span data-stu-id="ec916-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="ec916-470">Le système détermine automatiquement l'ordre correct selon lequel exécuter les répartitions.</span><span class="sxs-lookup"><span data-stu-id="ec916-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="ec916-471">Le solde d'un objet de coût est réparti par une seule base de répartition.</span><span class="sxs-lookup"><span data-stu-id="ec916-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="ec916-472">Les répartitions entre plusieurs dimensions d'objets de coût et leurs membres respectifs sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="ec916-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="ec916-473">L'ordre de répartition est contrôlé par l'unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="ec916-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="ec916-474">[![Méthode réciproque](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="ec916-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="ec916-475">Définir la répartition de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-475">Define the cost allocation</span></span>

<span data-ttu-id="ec916-476">Voici un exemple simple expliquant comment suivre le flux du coût.</span><span class="sxs-lookup"><span data-stu-id="ec916-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="ec916-477">L'objet de coût CC001 HR contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec916-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="ec916-478">Un membre de dimension statistique nommé Services HR est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ec916-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-479">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-479">Cost object</span></span></th>
<th><span data-ttu-id="ec916-480">Services HR</span><span class="sxs-lookup"><span data-stu-id="ec916-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-481">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-481">CC002</span></span></td>
<td><span data-ttu-id="ec916-482">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-482">Finance</span></span></td>
<td><span data-ttu-id="ec916-483">35</span><span class="sxs-lookup"><span data-stu-id="ec916-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-484">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-484">CC003</span></span></td>
<td><span data-ttu-id="ec916-485">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-485">Assembly</span></span></td>
<td><span data-ttu-id="ec916-486">55</span><span class="sxs-lookup"><span data-stu-id="ec916-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-487">CC004</span><span class="sxs-lookup"><span data-stu-id="ec916-487">CC004</span></span></td>
<td><span data-ttu-id="ec916-488">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec916-488">Packaging</span></span></td>
<td><span data-ttu-id="ec916-489">10</span><span class="sxs-lookup"><span data-stu-id="ec916-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-490">L'objet de coût CC002 Finance contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec916-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="ec916-491">Un membre de dimension statistique nommé Services Finance est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ec916-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-492">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-492">Cost object</span></span></th>
<th><span data-ttu-id="ec916-493">Services Finance</span><span class="sxs-lookup"><span data-stu-id="ec916-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-494">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-494">CC003</span></span></td>
<td><span data-ttu-id="ec916-495">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-495">Assembly</span></span></td>
<td><span data-ttu-id="ec916-496">65</span><span class="sxs-lookup"><span data-stu-id="ec916-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-497">CC004</span><span class="sxs-lookup"><span data-stu-id="ec916-497">CC004</span></span></td>
<td><span data-ttu-id="ec916-498">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec916-498">Packaging</span></span></td>
<td><span data-ttu-id="ec916-499">35</span><span class="sxs-lookup"><span data-stu-id="ec916-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-500">L'objet de coût CC003 Assemblage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec916-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="ec916-501">Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ec916-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-502">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-502">Cost object</span></span></th>
<th><span data-ttu-id="ec916-503">Services Assemblage (heures)</span><span class="sxs-lookup"><span data-stu-id="ec916-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-504">Prod 1</span></span></td>
<td><span data-ttu-id="ec916-505">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-505">Product 1</span></span></td>
<td><span data-ttu-id="ec916-506">60</span><span class="sxs-lookup"><span data-stu-id="ec916-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-507">Prod 2</span></span></td>
<td><span data-ttu-id="ec916-508">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec916-508">Product 2</span></span></td>
<td><span data-ttu-id="ec916-509">20</span><span class="sxs-lookup"><span data-stu-id="ec916-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-510">L'objet de coût CC004 Emballage contribue à plusieurs objets de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec916-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="ec916-511">Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l'ampleur de consommation.</span><span class="sxs-lookup"><span data-stu-id="ec916-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-512">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-512">Cost object</span></span></th>
<th><span data-ttu-id="ec916-513">Services Emballage (heures)</span><span class="sxs-lookup"><span data-stu-id="ec916-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-514">Prod 1</span></span></td>
<td><span data-ttu-id="ec916-515">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-515">Product 1</span></span></td>
<td><span data-ttu-id="ec916-516">80</span><span class="sxs-lookup"><span data-stu-id="ec916-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-517">Prod 2</span></span></td>
<td><span data-ttu-id="ec916-518">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec916-518">Product 2</span></span></td>
<td><span data-ttu-id="ec916-519">15</span><span class="sxs-lookup"><span data-stu-id="ec916-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ec916-520">Les mesures statistiques telles que les heures de production qu'un produit consomme peuvent être dérivées des données sources.</span><span class="sxs-lookup"><span data-stu-id="ec916-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="ec916-521">Pour plus d'informations, voir [Modèle de fournisseur de mesures statistiques](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="ec916-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="ec916-522">Le tableau suivant présente le résultat lorsque les services RH sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="ec916-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-523">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-523">Cost object</span></span></th>
<th><span data-ttu-id="ec916-524">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec916-524">Magnitude</span></span></th>
<th><span data-ttu-id="ec916-525">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec916-525">Allocation factor</span></span></th>
<th><span data-ttu-id="ec916-526">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-526">Amount</span></span></th>
<th><span data-ttu-id="ec916-527">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-528">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-528">CC002</span></span></td>
<td><span data-ttu-id="ec916-529">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-529">Finance</span></span></td>
<td><span data-ttu-id="ec916-530">35</span><span class="sxs-lookup"><span data-stu-id="ec916-530">35</span></span></td>
<td><span data-ttu-id="ec916-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ec916-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ec916-532">175.00</span><span class="sxs-lookup"><span data-stu-id="ec916-532">175.00</span></span></td>
<td><span data-ttu-id="ec916-533">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-534">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-534">CC003</span></span></td>
<td><span data-ttu-id="ec916-535">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-535">Assembly</span></span></td>
<td><span data-ttu-id="ec916-536">55</span><span class="sxs-lookup"><span data-stu-id="ec916-536">55</span></span></td>
<td><span data-ttu-id="ec916-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ec916-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ec916-538">275.00</span><span class="sxs-lookup"><span data-stu-id="ec916-538">275.00</span></span></td>
<td><span data-ttu-id="ec916-539">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-540">CC004</span><span class="sxs-lookup"><span data-stu-id="ec916-540">CC004</span></span></td>
<td><span data-ttu-id="ec916-541">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec916-541">Packaging</span></span></td>
<td><span data-ttu-id="ec916-542">10</span><span class="sxs-lookup"><span data-stu-id="ec916-542">10</span></span></td>
<td><span data-ttu-id="ec916-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ec916-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ec916-544">50,00</span><span class="sxs-lookup"><span data-stu-id="ec916-544">50.00</span></span></td>
<td><span data-ttu-id="ec916-545">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-546">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-546">CC002</span></span></td>
<td><span data-ttu-id="ec916-547">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-547">Finance</span></span></td>
<td><span data-ttu-id="ec916-548">35</span><span class="sxs-lookup"><span data-stu-id="ec916-548">35</span></span></td>
<td><span data-ttu-id="ec916-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="ec916-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ec916-550">436.00</span><span class="sxs-lookup"><span data-stu-id="ec916-550">436.00</span></span></td>
<td><span data-ttu-id="ec916-551">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-552">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-552">CC003</span></span></td>
<td><span data-ttu-id="ec916-553">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-553">Assembly</span></span></td>
<td><span data-ttu-id="ec916-554">55</span><span class="sxs-lookup"><span data-stu-id="ec916-554">55</span></span></td>
<td><span data-ttu-id="ec916-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="ec916-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ec916-556">685.14</span><span class="sxs-lookup"><span data-stu-id="ec916-556">685.14</span></span></td>
<td><span data-ttu-id="ec916-557">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-558">CC004</span><span class="sxs-lookup"><span data-stu-id="ec916-558">CC004</span></span></td>
<td><span data-ttu-id="ec916-559">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec916-559">Packaging</span></span></td>
<td><span data-ttu-id="ec916-560">10</span><span class="sxs-lookup"><span data-stu-id="ec916-560">10</span></span></td>
<td><span data-ttu-id="ec916-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="ec916-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ec916-562">124.57</span><span class="sxs-lookup"><span data-stu-id="ec916-562">124.57</span></span></td>
<td><span data-ttu-id="ec916-563">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-564">Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="ec916-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-565">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-565">Cost object</span></span></th>
<th><span data-ttu-id="ec916-566">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec916-566">Magnitude</span></span></th>
<th><span data-ttu-id="ec916-567">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec916-567">Allocation factor</span></span></th>
<th><span data-ttu-id="ec916-568">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-568">Amount</span></span></th>
<th><span data-ttu-id="ec916-569">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-570">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-570">CC003</span></span></td>
<td><span data-ttu-id="ec916-571">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-571">Assembly</span></span></td>
<td><span data-ttu-id="ec916-572">65</span><span class="sxs-lookup"><span data-stu-id="ec916-572">65</span></span></td>
<td><span data-ttu-id="ec916-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="ec916-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ec916-574">438.75</span><span class="sxs-lookup"><span data-stu-id="ec916-574">438.75</span></span></td>
<td><span data-ttu-id="ec916-575">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-576">CC004</span><span class="sxs-lookup"><span data-stu-id="ec916-576">CC004</span></span></td>
<td><span data-ttu-id="ec916-577">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec916-577">Packaging</span></span></td>
<td><span data-ttu-id="ec916-578">35</span><span class="sxs-lookup"><span data-stu-id="ec916-578">35</span></span></td>
<td><span data-ttu-id="ec916-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="ec916-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ec916-580">236.25</span><span class="sxs-lookup"><span data-stu-id="ec916-580">236.25</span></span></td>
<td><span data-ttu-id="ec916-581">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-582">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-582">CC003</span></span></td>
<td><span data-ttu-id="ec916-583">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-583">Assembly</span></span></td>
<td><span data-ttu-id="ec916-584">65</span><span class="sxs-lookup"><span data-stu-id="ec916-584">65</span></span></td>
<td><span data-ttu-id="ec916-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="ec916-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ec916-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ec916-586">5,297.69</span></span></td>
<td><span data-ttu-id="ec916-587">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-588">CC004</span><span class="sxs-lookup"><span data-stu-id="ec916-588">CC004</span></span></td>
<td><span data-ttu-id="ec916-589">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec916-589">Packaging</span></span></td>
<td><span data-ttu-id="ec916-590">35</span><span class="sxs-lookup"><span data-stu-id="ec916-590">35</span></span></td>
<td><span data-ttu-id="ec916-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="ec916-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ec916-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ec916-592">2,852.60</span></span></td>
<td><span data-ttu-id="ec916-593">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-594">Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="ec916-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-595">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-595">Cost object</span></span></th>
<th><span data-ttu-id="ec916-596">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec916-596">Magnitude</span></span></th>
<th><span data-ttu-id="ec916-597">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec916-597">Allocation factor</span></span></th>
<th><span data-ttu-id="ec916-598">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-598">Amount</span></span></th>
<th><span data-ttu-id="ec916-599">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-600">Prod 1</span></span></td>
<td><span data-ttu-id="ec916-601">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-601">Product 1</span></span></td>
<td><span data-ttu-id="ec916-602">60</span><span class="sxs-lookup"><span data-stu-id="ec916-602">60</span></span></td>
<td><span data-ttu-id="ec916-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="ec916-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ec916-604">535.31</span><span class="sxs-lookup"><span data-stu-id="ec916-604">535.31</span></span></td>
<td><span data-ttu-id="ec916-605">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-606">Prod 2</span></span></td>
<td><span data-ttu-id="ec916-607">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec916-607">Product 2</span></span></td>
<td><span data-ttu-id="ec916-608">20</span><span class="sxs-lookup"><span data-stu-id="ec916-608">20</span></span></td>
<td><span data-ttu-id="ec916-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="ec916-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ec916-610">178.44</span><span class="sxs-lookup"><span data-stu-id="ec916-610">178.44</span></span></td>
<td><span data-ttu-id="ec916-611">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-612">Prod 1</span></span></td>
<td><span data-ttu-id="ec916-613">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-613">Product 1</span></span></td>
<td><span data-ttu-id="ec916-614">60</span><span class="sxs-lookup"><span data-stu-id="ec916-614">60</span></span></td>
<td><span data-ttu-id="ec916-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="ec916-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ec916-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ec916-616">4,487.12</span></span></td>
<td><span data-ttu-id="ec916-617">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-618">Prod 2</span></span></td>
<td><span data-ttu-id="ec916-619">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec916-619">Product 2</span></span></td>
<td><span data-ttu-id="ec916-620">20</span><span class="sxs-lookup"><span data-stu-id="ec916-620">20</span></span></td>
<td><span data-ttu-id="ec916-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="ec916-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ec916-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ec916-622">1,495.71</span></span></td>
<td><span data-ttu-id="ec916-623">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec916-624">Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).</span><span class="sxs-lookup"><span data-stu-id="ec916-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-625">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-625">Cost object</span></span></th>
<th><span data-ttu-id="ec916-626">Ampleur</span><span class="sxs-lookup"><span data-stu-id="ec916-626">Magnitude</span></span></th>
<th><span data-ttu-id="ec916-627">Facteur de répartition</span><span class="sxs-lookup"><span data-stu-id="ec916-627">Allocation factor</span></span></th>
<th><span data-ttu-id="ec916-628">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-628">Amount</span></span></th>
<th><span data-ttu-id="ec916-629">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-630">Prod 1</span></span></td>
<td><span data-ttu-id="ec916-631">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-631">Product 1</span></span></td>
<td><span data-ttu-id="ec916-632">80</span><span class="sxs-lookup"><span data-stu-id="ec916-632">80</span></span></td>
<td><span data-ttu-id="ec916-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="ec916-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ec916-634">241.05</span><span class="sxs-lookup"><span data-stu-id="ec916-634">241.05</span></span></td>
<td><span data-ttu-id="ec916-635">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-636">Prod 2</span></span></td>
<td><span data-ttu-id="ec916-637">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec916-637">Product 2</span></span></td>
<td><span data-ttu-id="ec916-638">15</span><span class="sxs-lookup"><span data-stu-id="ec916-638">15</span></span></td>
<td><span data-ttu-id="ec916-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="ec916-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ec916-640">45.20</span><span class="sxs-lookup"><span data-stu-id="ec916-640">45.20</span></span></td>
<td><span data-ttu-id="ec916-641">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-642">Prod 1</span></span></td>
<td><span data-ttu-id="ec916-643">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-643">Product 1</span></span></td>
<td><span data-ttu-id="ec916-644">80</span><span class="sxs-lookup"><span data-stu-id="ec916-644">80</span></span></td>
<td><span data-ttu-id="ec916-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="ec916-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ec916-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ec916-646">2,507.09</span></span></td>
<td><span data-ttu-id="ec916-647">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-648">Prod 2</span></span></td>
<td><span data-ttu-id="ec916-649">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec916-649">Product 2</span></span></td>
<td><span data-ttu-id="ec916-650">15</span><span class="sxs-lookup"><span data-stu-id="ec916-650">15</span></span></td>
<td><span data-ttu-id="ec916-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="ec916-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ec916-652">470.08</span><span class="sxs-lookup"><span data-stu-id="ec916-652">470.08</span></span></td>
<td><span data-ttu-id="ec916-653">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ec916-654">Entrées du journal (pour le solde d'objet de coût)</span><span class="sxs-lookup"><span data-stu-id="ec916-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec916-655">Journal de saisie</span><span class="sxs-lookup"><span data-stu-id="ec916-655">Journal</span></span></th>
<th><span data-ttu-id="ec916-656">Type de journal</span><span class="sxs-lookup"><span data-stu-id="ec916-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ec916-657">Période de calendrier fiscal</span><span class="sxs-lookup"><span data-stu-id="ec916-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ec916-658">Version</span><span class="sxs-lookup"><span data-stu-id="ec916-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-659">00004</span><span class="sxs-lookup"><span data-stu-id="ec916-659">00004</span></span></td>
<td><span data-ttu-id="ec916-660">Journal de répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="ec916-661">Exercice</span><span class="sxs-lookup"><span data-stu-id="ec916-661">Fiscal</span></span></td>
<td><span data-ttu-id="ec916-662">2017</span><span class="sxs-lookup"><span data-stu-id="ec916-662">2017</span></span></td>
<td><span data-ttu-id="ec916-663">Période 1</span><span class="sxs-lookup"><span data-stu-id="ec916-663">Period 1</span></span></td>
<td><span data-ttu-id="ec916-664">Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</span><span class="sxs-lookup"><span data-stu-id="ec916-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="ec916-665">Lignes de journal</span><span class="sxs-lookup"><span data-stu-id="ec916-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ec916-666">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec916-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-667">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-668">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-668">Cost element</span></span></th>
<th><span data-ttu-id="ec916-669">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-669">Cost behavior</span></span></th>
<th><span data-ttu-id="ec916-670">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-671">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-672">CC001</span><span class="sxs-lookup"><span data-stu-id="ec916-672">CC001</span></span></td>
<td><span data-ttu-id="ec916-673">RH</span><span class="sxs-lookup"><span data-stu-id="ec916-673">HR</span></span></td>
<td><span data-ttu-id="ec916-674">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-674">10001</span></span></td>
<td><span data-ttu-id="ec916-675">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-675">Electricity</span></span></td>
<td><span data-ttu-id="ec916-676">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-676">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-677">500,00</span><span class="sxs-lookup"><span data-stu-id="ec916-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-678">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-679">CC001</span><span class="sxs-lookup"><span data-stu-id="ec916-679">CC001</span></span></td>
<td><span data-ttu-id="ec916-680">RH</span><span class="sxs-lookup"><span data-stu-id="ec916-680">HR</span></span></td>
<td><span data-ttu-id="ec916-681">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-681">10001</span></span></td>
<td><span data-ttu-id="ec916-682">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-682">Electricity</span></span></td>
<td><span data-ttu-id="ec916-683">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-683">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="ec916-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-685">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-686">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-686">CC002</span></span></td>
<td><span data-ttu-id="ec916-687">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-687">Finance</span></span></td>
<td><span data-ttu-id="ec916-688">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-688">10001</span></span></td>
<td><span data-ttu-id="ec916-689">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-689">Electricity</span></span></td>
<td><span data-ttu-id="ec916-690">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-690">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-691">675.00</span><span class="sxs-lookup"><span data-stu-id="ec916-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-692">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-693">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-693">CC002</span></span></td>
<td><span data-ttu-id="ec916-694">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-694">Finance</span></span></td>
<td><span data-ttu-id="ec916-695">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-695">10001</span></span></td>
<td><span data-ttu-id="ec916-696">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-696">Electricity</span></span></td>
<td><span data-ttu-id="ec916-697">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-697">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="ec916-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-699">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-700">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-700">CC003</span></span></td>
<td><span data-ttu-id="ec916-701">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-701">Assembly</span></span></td>
<td><span data-ttu-id="ec916-702">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-702">10001</span></span></td>
<td><span data-ttu-id="ec916-703">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-703">Electricity</span></span></td>
<td><span data-ttu-id="ec916-704">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-704">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-705">713.75</span><span class="sxs-lookup"><span data-stu-id="ec916-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-706">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-707">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-707">CC003</span></span></td>
<td><span data-ttu-id="ec916-708">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-708">Assembly</span></span></td>
<td><span data-ttu-id="ec916-709">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-709">10001</span></span></td>
<td><span data-ttu-id="ec916-710">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-710">Electricity</span></span></td>
<td><span data-ttu-id="ec916-711">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-711">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="ec916-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-713">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-714">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-714">CC003</span></span></td>
<td><span data-ttu-id="ec916-715">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec916-715">Packaging</span></span></td>
<td><span data-ttu-id="ec916-716">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-716">10001</span></span></td>
<td><span data-ttu-id="ec916-717">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-717">Electricity</span></span></td>
<td><span data-ttu-id="ec916-718">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-718">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-719">286.25</span><span class="sxs-lookup"><span data-stu-id="ec916-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-720">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-721">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-721">CC003</span></span></td>
<td><span data-ttu-id="ec916-722">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec916-722">Packaging</span></span></td>
<td><span data-ttu-id="ec916-723">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-723">10001</span></span></td>
<td><span data-ttu-id="ec916-724">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-724">Electricity</span></span></td>
<td><span data-ttu-id="ec916-725">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-725">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="ec916-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-727">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-728">Prod 1</span></span></td>
<td><span data-ttu-id="ec916-729">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-729">Product 1</span></span></td>
<td><span data-ttu-id="ec916-730">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-730">10001</span></span></td>
<td><span data-ttu-id="ec916-731">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-731">Electricity</span></span></td>
<td><span data-ttu-id="ec916-732">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-732">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-733">776.36</span><span class="sxs-lookup"><span data-stu-id="ec916-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-734">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-735">Prod 1</span></span></td>
<td><span data-ttu-id="ec916-736">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-736">Product 1</span></span></td>
<td><span data-ttu-id="ec916-737">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-737">10001</span></span></td>
<td><span data-ttu-id="ec916-738">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-738">Electricity</span></span></td>
<td><span data-ttu-id="ec916-739">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-739">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ec916-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-741">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-742">Prod 2</span></span></td>
<td><span data-ttu-id="ec916-743">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-743">Product 1</span></span></td>
<td><span data-ttu-id="ec916-744">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-744">10001</span></span></td>
<td><span data-ttu-id="ec916-745">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-745">Electricity</span></span></td>
<td><span data-ttu-id="ec916-746">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-746">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-747">223.64</span><span class="sxs-lookup"><span data-stu-id="ec916-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-748">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="ec916-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-749">Prod 2</span></span></td>
<td><span data-ttu-id="ec916-750">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-750">Product 1</span></span></td>
<td><span data-ttu-id="ec916-751">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-751">10001</span></span></td>
<td><span data-ttu-id="ec916-752">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-752">Electricity</span></span></td>
<td><span data-ttu-id="ec916-753">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-753">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ec916-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ec916-755">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ec916-756">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ec916-757">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-757">Cost element</span></span></th>
<th><span data-ttu-id="ec916-758">Comportement de coûts</span><span class="sxs-lookup"><span data-stu-id="ec916-758">Cost behavior</span></span></th>
<th><span data-ttu-id="ec916-759">Montant</span><span class="sxs-lookup"><span data-stu-id="ec916-759">Amount</span></span></th>
<th><span data-ttu-id="ec916-760">Date comptable</span><span class="sxs-lookup"><span data-stu-id="ec916-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ec916-761">CC001</span><span class="sxs-lookup"><span data-stu-id="ec916-761">CC001</span></span></td>
<td><span data-ttu-id="ec916-762">RH</span><span class="sxs-lookup"><span data-stu-id="ec916-762">HR</span></span></td>
<td><span data-ttu-id="ec916-763">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-763">10001</span></span></td>
<td><span data-ttu-id="ec916-764">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-764">Electricity</span></span></td>
<td><span data-ttu-id="ec916-765">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-765">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="ec916-766">-500.00</span></span></td>
<td><span data-ttu-id="ec916-767">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-768">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-768">CC002</span></span></td>
<td><span data-ttu-id="ec916-769">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-769">Finance</span></span></td>
<td><span data-ttu-id="ec916-770">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-770">10001</span></span></td>
<td><span data-ttu-id="ec916-771">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-771">Electricity</span></span></td>
<td><span data-ttu-id="ec916-772">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-772">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-773">175.00</span><span class="sxs-lookup"><span data-stu-id="ec916-773">175.00</span></span></td>
<td><span data-ttu-id="ec916-774">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-775">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-775">CC003</span></span></td>
<td><span data-ttu-id="ec916-776">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-776">Assembly</span></span></td>
<td><span data-ttu-id="ec916-777">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-777">10001</span></span></td>
<td><span data-ttu-id="ec916-778">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-778">Electricity</span></span></td>
<td><span data-ttu-id="ec916-779">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-779">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-780">275.00</span><span class="sxs-lookup"><span data-stu-id="ec916-780">275.00</span></span></td>
<td><span data-ttu-id="ec916-781">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-782">CC004</span><span class="sxs-lookup"><span data-stu-id="ec916-782">CC004</span></span></td>
<td><span data-ttu-id="ec916-783">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec916-783">Packaging</span></span></td>
<td><span data-ttu-id="ec916-784">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-784">10001</span></span></td>
<td><span data-ttu-id="ec916-785">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-785">Electricity</span></span></td>
<td><span data-ttu-id="ec916-786">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-786">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-787">50,00</span><span class="sxs-lookup"><span data-stu-id="ec916-787">50,00</span></span></td>
<td><span data-ttu-id="ec916-788">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-789">CC001</span><span class="sxs-lookup"><span data-stu-id="ec916-789">CC001</span></span></td>
<td><span data-ttu-id="ec916-790">RH</span><span class="sxs-lookup"><span data-stu-id="ec916-790">HR</span></span></td>
<td><span data-ttu-id="ec916-791">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-791">10001</span></span></td>
<td><span data-ttu-id="ec916-792">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-792">Electricity</span></span></td>
<td><span data-ttu-id="ec916-793">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-793">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="ec916-794">-1,245.71</span></span></td>
<td><span data-ttu-id="ec916-795">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-796">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-796">CC002</span></span></td>
<td><span data-ttu-id="ec916-797">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-797">Finance</span></span></td>
<td><span data-ttu-id="ec916-798">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-798">10001</span></span></td>
<td><span data-ttu-id="ec916-799">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-799">Electricity</span></span></td>
<td><span data-ttu-id="ec916-800">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-800">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-801">436.00</span><span class="sxs-lookup"><span data-stu-id="ec916-801">436.00</span></span></td>
<td><span data-ttu-id="ec916-802">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-803">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-803">CC003</span></span></td>
<td><span data-ttu-id="ec916-804">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-804">Assembly</span></span></td>
<td><span data-ttu-id="ec916-805">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-805">10001</span></span></td>
<td><span data-ttu-id="ec916-806">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-806">Electricity</span></span></td>
<td><span data-ttu-id="ec916-807">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-807">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-808">685.14</span><span class="sxs-lookup"><span data-stu-id="ec916-808">685.14</span></span></td>
<td><span data-ttu-id="ec916-809">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-810">CC004</span><span class="sxs-lookup"><span data-stu-id="ec916-810">CC004</span></span></td>
<td><span data-ttu-id="ec916-811">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec916-811">Packaging</span></span></td>
<td><span data-ttu-id="ec916-812">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-812">10001</span></span></td>
<td><span data-ttu-id="ec916-813">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-813">Electricity</span></span></td>
<td><span data-ttu-id="ec916-814">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-814">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-815">124.57</span><span class="sxs-lookup"><span data-stu-id="ec916-815">124.57</span></span></td>
<td><span data-ttu-id="ec916-816">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-817">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-817">CC002</span></span></td>
<td><span data-ttu-id="ec916-818">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-818">Finance</span></span></td>
<td><span data-ttu-id="ec916-819">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-819">10001</span></span></td>
<td><span data-ttu-id="ec916-820">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-820">Electricity</span></span></td>
<td><span data-ttu-id="ec916-821">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-821">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="ec916-822">-675.00</span></span></td>
<td><span data-ttu-id="ec916-823">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-824">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-824">CC003</span></span></td>
<td><span data-ttu-id="ec916-825">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-825">Assembly</span></span></td>
<td><span data-ttu-id="ec916-826">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-826">10001</span></span></td>
<td><span data-ttu-id="ec916-827">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-827">Electricity</span></span></td>
<td><span data-ttu-id="ec916-828">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-828">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-829">438.75</span><span class="sxs-lookup"><span data-stu-id="ec916-829">438.75</span></span></td>
<td><span data-ttu-id="ec916-830">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-831">CC004</span><span class="sxs-lookup"><span data-stu-id="ec916-831">CC004</span></span></td>
<td><span data-ttu-id="ec916-832">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec916-832">Packaging</span></span></td>
<td><span data-ttu-id="ec916-833">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-833">10001</span></span></td>
<td><span data-ttu-id="ec916-834">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-834">Electricity</span></span></td>
<td><span data-ttu-id="ec916-835">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-835">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-836">236.25</span><span class="sxs-lookup"><span data-stu-id="ec916-836">236.25</span></span></td>
<td><span data-ttu-id="ec916-837">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-838">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-838">CC002</span></span></td>
<td><span data-ttu-id="ec916-839">Finances</span><span class="sxs-lookup"><span data-stu-id="ec916-839">Finance</span></span></td>
<td><span data-ttu-id="ec916-840">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-840">10001</span></span></td>
<td><span data-ttu-id="ec916-841">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-841">Electricity</span></span></td>
<td><span data-ttu-id="ec916-842">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-842">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="ec916-843">-8,150.29</span></span></td>
<td><span data-ttu-id="ec916-844">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-845">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-845">CC003</span></span></td>
<td><span data-ttu-id="ec916-846">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-846">Assembly</span></span></td>
<td><span data-ttu-id="ec916-847">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-847">10001</span></span></td>
<td><span data-ttu-id="ec916-848">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-848">Electricity</span></span></td>
<td><span data-ttu-id="ec916-849">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-849">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ec916-850">5,297.69</span></span></td>
<td><span data-ttu-id="ec916-851">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-852">CC004</span><span class="sxs-lookup"><span data-stu-id="ec916-852">CC004</span></span></td>
<td><span data-ttu-id="ec916-853">Emballage</span><span class="sxs-lookup"><span data-stu-id="ec916-853">Packaging</span></span></td>
<td><span data-ttu-id="ec916-854">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-854">10001</span></span></td>
<td><span data-ttu-id="ec916-855">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-855">Electricity</span></span></td>
<td><span data-ttu-id="ec916-856">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-856">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ec916-857">2,852.60</span></span></td>
<td><span data-ttu-id="ec916-858">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-859">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-859">CC003</span></span></td>
<td><span data-ttu-id="ec916-860">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-860">Assembly</span></span></td>
<td><span data-ttu-id="ec916-861">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-861">10001</span></span></td>
<td><span data-ttu-id="ec916-862">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-862">Electricity</span></span></td>
<td><span data-ttu-id="ec916-863">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-863">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="ec916-864">-713.75</span></span></td>
<td><span data-ttu-id="ec916-865">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-866">Prod 1</span></span></td>
<td><span data-ttu-id="ec916-867">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-867">Product 1</span></span></td>
<td><span data-ttu-id="ec916-868">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-868">10001</span></span></td>
<td><span data-ttu-id="ec916-869">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-869">Electricity</span></span></td>
<td><span data-ttu-id="ec916-870">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-870">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-871">535.31</span><span class="sxs-lookup"><span data-stu-id="ec916-871">535.31</span></span></td>
<td><span data-ttu-id="ec916-872">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-873">Prod 2</span></span></td>
<td><span data-ttu-id="ec916-874">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec916-874">Product 2</span></span></td>
<td><span data-ttu-id="ec916-875">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-875">10001</span></span></td>
<td><span data-ttu-id="ec916-876">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-876">Electricity</span></span></td>
<td><span data-ttu-id="ec916-877">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-877">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-878">178.44</span><span class="sxs-lookup"><span data-stu-id="ec916-878">178.44</span></span></td>
<td><span data-ttu-id="ec916-879">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-880">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-880">CC003</span></span></td>
<td><span data-ttu-id="ec916-881">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-881">Assembly</span></span></td>
<td><span data-ttu-id="ec916-882">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-882">10001</span></span></td>
<td><span data-ttu-id="ec916-883">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-883">Electricity</span></span></td>
<td><span data-ttu-id="ec916-884">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-884">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="ec916-885">-5,982.83</span></span></td>
<td><span data-ttu-id="ec916-886">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-887">Prod 1</span></span></td>
<td><span data-ttu-id="ec916-888">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-888">Product 1</span></span></td>
<td><span data-ttu-id="ec916-889">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-889">10001</span></span></td>
<td><span data-ttu-id="ec916-890">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-890">Electricity</span></span></td>
<td><span data-ttu-id="ec916-891">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-891">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ec916-892">4,487.12</span></span></td>
<td><span data-ttu-id="ec916-893">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-894">Prod 2</span></span></td>
<td><span data-ttu-id="ec916-895">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec916-895">Product 2</span></span></td>
<td><span data-ttu-id="ec916-896">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-896">10001</span></span></td>
<td><span data-ttu-id="ec916-897">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-897">Electricity</span></span></td>
<td><span data-ttu-id="ec916-898">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-898">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ec916-899">1,495.71</span></span></td>
<td><span data-ttu-id="ec916-900">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-901">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-901">CC003</span></span></td>
<td><span data-ttu-id="ec916-902">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-902">Assembly</span></span></td>
<td><span data-ttu-id="ec916-903">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-903">10001</span></span></td>
<td><span data-ttu-id="ec916-904">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-904">Electricity</span></span></td>
<td><span data-ttu-id="ec916-905">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-905">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="ec916-906">-286.25</span></span></td>
<td><span data-ttu-id="ec916-907">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-908">Prod 1</span></span></td>
<td><span data-ttu-id="ec916-909">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-909">Product 1</span></span></td>
<td><span data-ttu-id="ec916-910">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-910">10001</span></span></td>
<td><span data-ttu-id="ec916-911">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-911">Electricity</span></span></td>
<td><span data-ttu-id="ec916-912">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-912">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-913">241.05</span><span class="sxs-lookup"><span data-stu-id="ec916-913">241.05</span></span></td>
<td><span data-ttu-id="ec916-914">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-915">Prod 2</span></span></td>
<td><span data-ttu-id="ec916-916">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec916-916">Product 2</span></span></td>
<td><span data-ttu-id="ec916-917">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-917">10001</span></span></td>
<td><span data-ttu-id="ec916-918">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-918">Electricity</span></span></td>
<td><span data-ttu-id="ec916-919">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-919">Fixed cost</span></span></td>
<td><span data-ttu-id="ec916-920">45.20</span><span class="sxs-lookup"><span data-stu-id="ec916-920">45.20</span></span></td>
<td><span data-ttu-id="ec916-921">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-922">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-922">CC003</span></span></td>
<td><span data-ttu-id="ec916-923">Assemblage</span><span class="sxs-lookup"><span data-stu-id="ec916-923">Assembly</span></span></td>
<td><span data-ttu-id="ec916-924">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-924">10001</span></span></td>
<td><span data-ttu-id="ec916-925">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-925">Electricity</span></span></td>
<td><span data-ttu-id="ec916-926">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-926">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="ec916-927">-2,977.17</span></span></td>
<td><span data-ttu-id="ec916-928">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-929">Prod 1</span></span></td>
<td><span data-ttu-id="ec916-930">Produit 1</span><span class="sxs-lookup"><span data-stu-id="ec916-930">Product 1</span></span></td>
<td><span data-ttu-id="ec916-931">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-931">10001</span></span></td>
<td><span data-ttu-id="ec916-932">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-932">Electricity</span></span></td>
<td><span data-ttu-id="ec916-933">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-933">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ec916-934">2,507.09</span></span></td>
<td><span data-ttu-id="ec916-935">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ec916-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-936">Prod 2</span></span></td>
<td><span data-ttu-id="ec916-937">Produit 2</span><span class="sxs-lookup"><span data-stu-id="ec916-937">Product 2</span></span></td>
<td><span data-ttu-id="ec916-938">10001</span><span class="sxs-lookup"><span data-stu-id="ec916-938">10001</span></span></td>
<td><span data-ttu-id="ec916-939">Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-939">Electricity</span></span></td>
<td><span data-ttu-id="ec916-940">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-940">Variable cost</span></span></td>
<td><span data-ttu-id="ec916-941">470.08</span><span class="sxs-lookup"><span data-stu-id="ec916-941">470.08</span></span></td>
<td><span data-ttu-id="ec916-942">31 janvier 2017</span><span class="sxs-lookup"><span data-stu-id="ec916-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="ec916-943">Conclusion</span><span class="sxs-lookup"><span data-stu-id="ec916-943">Conclusion</span></span>
<span data-ttu-id="ec916-944">Dans la comptabilité financière, un coût de 10 000,00 pour l'électricité est imputé sur un ID de centre de coût fictif.</span><span class="sxs-lookup"><span data-stu-id="ec916-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="ec916-945">Par conséquent, les comptables sauront que ce coût doit être affecté.</span><span class="sxs-lookup"><span data-stu-id="ec916-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="ec916-946">Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l'organisation, selon les stratégies et les règles qui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="ec916-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="ec916-947">Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.</span><span class="sxs-lookup"><span data-stu-id="ec916-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="ec916-948">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="ec916-949">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="ec916-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="ec916-950">Total</span><span class="sxs-lookup"><span data-stu-id="ec916-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ec916-951">CC099</span><span class="sxs-lookup"><span data-stu-id="ec916-951">CC099</span></span></th>
<th><span data-ttu-id="ec916-952">CC001</span><span class="sxs-lookup"><span data-stu-id="ec916-952">CC001</span></span></th>
<th><span data-ttu-id="ec916-953">CC002</span><span class="sxs-lookup"><span data-stu-id="ec916-953">CC002</span></span></th>
<th><span data-ttu-id="ec916-954">CC003</span><span class="sxs-lookup"><span data-stu-id="ec916-954">CC003</span></span></th>
<th><span data-ttu-id="ec916-955">CC004</span><span class="sxs-lookup"><span data-stu-id="ec916-955">CC004</span></span></th>
<th><span data-ttu-id="ec916-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ec916-956">Proj 1</span></span></th>
<th><span data-ttu-id="ec916-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ec916-957">Proj 2</span></span></th>
<th><span data-ttu-id="ec916-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ec916-958">Prod 1</span></span></th>
<th><span data-ttu-id="ec916-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ec916-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="ec916-960">10001 Électricité</span><span class="sxs-lookup"><span data-stu-id="ec916-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec916-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec916-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec916-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec916-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ec916-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec916-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec916-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="ec916-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="ec916-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec916-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="ec916-970">Non classifié</span><span class="sxs-lookup"><span data-stu-id="ec916-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-971">0,00</span><span class="sxs-lookup"><span data-stu-id="ec916-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="ec916-972">Coût fixe</span><span class="sxs-lookup"><span data-stu-id="ec916-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-973">0,00</span><span class="sxs-lookup"><span data-stu-id="ec916-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-974">0,00</span><span class="sxs-lookup"><span data-stu-id="ec916-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-975">0,00</span><span class="sxs-lookup"><span data-stu-id="ec916-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-976">0,00</span><span class="sxs-lookup"><span data-stu-id="ec916-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-977">0,00</span><span class="sxs-lookup"><span data-stu-id="ec916-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ec916-978">776.36</span><span class="sxs-lookup"><span data-stu-id="ec916-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-979">223.64</span><span class="sxs-lookup"><span data-stu-id="ec916-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-980"><strong>1 000,00</strong></span><span class="sxs-lookup"><span data-stu-id="ec916-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="ec916-981">Coût variable</span><span class="sxs-lookup"><span data-stu-id="ec916-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-982">000</span><span class="sxs-lookup"><span data-stu-id="ec916-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-983">0,00</span><span class="sxs-lookup"><span data-stu-id="ec916-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-984">0,00</span><span class="sxs-lookup"><span data-stu-id="ec916-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-985">0,00</span><span class="sxs-lookup"><span data-stu-id="ec916-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-986">0,00</span><span class="sxs-lookup"><span data-stu-id="ec916-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-987">30,00</span><span class="sxs-lookup"><span data-stu-id="ec916-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-988">10,00</span><span class="sxs-lookup"><span data-stu-id="ec916-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ec916-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ec916-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ec916-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ec916-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ec916-992">Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût.</span><span class="sxs-lookup"><span data-stu-id="ec916-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="ec916-993">Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l'organisation.</span><span class="sxs-lookup"><span data-stu-id="ec916-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="ec916-994">Autrement dit, les objets de coût de plus bas niveau supportent le coût.</span><span class="sxs-lookup"><span data-stu-id="ec916-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="ec916-995">Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts.</span><span class="sxs-lookup"><span data-stu-id="ec916-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="ec916-996">Pour plus d'informations, voir [Repositionnement des coûts](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="ec916-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



