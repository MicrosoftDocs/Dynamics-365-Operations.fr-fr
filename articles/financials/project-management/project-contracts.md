---
title: Contrats de projet
description: "Cette rubrique décrit les contrats de projet à créer pour divers types de projets et de sources de financement (et en fournit des exemples), ainsi que la manière de gérer les contrats et facturer les clients des projets dans Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: KimANelson
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3a1bfd4bd5f396c05277159ac112eaa8197d5818
ms.openlocfilehash: c8328bd2d93bbe763e629248edc1b7b4576005ae
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="project-contracts"></a><span data-ttu-id="95bda-103">Contrats de projet</span><span class="sxs-lookup"><span data-stu-id="95bda-103">Project contracts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="95bda-104">Cet article décrit les contrats de projet à créer pour divers types de projets et de sources de financement (et en fournit des exemples), ainsi que la manière de gérer les contrats et facturer les clients des projets dans Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="95bda-104">This article provides examples of the project contracts that you can create for various types of projects and funding sources, and how you can manage contracts and invoice project customers in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

<span data-ttu-id="95bda-105">Le type de projet que vous créez pour un contrat de projet détermine la méthode utilisée pour facturer les clients du projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-105">The type of project that you create for a project contract determines the method that is used to invoice project customers.</span></span> <span data-ttu-id="95bda-106">Vous pouvez modifier un contrat de projet et le projet qui lui est associé, mais vous ne pouvez pas modifier le type de projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-106">You can change a project contract and the related project, but you can't change the project type.</span></span> 

<span data-ttu-id="95bda-107">En utilisant un contrat de projet, vous pouvez facturer un ou plusieurs projets à la fois.</span><span class="sxs-lookup"><span data-stu-id="95bda-107">By using a project contract, you can invoice one or more projects at the same time.</span></span> <span data-ttu-id="95bda-108">Le contrat de projet permet également de garantir qu'une procédure cohérente de facturation s'applique à chaque sous-projet d'une structure de projets.</span><span class="sxs-lookup"><span data-stu-id="95bda-108">The project contract also helps guarantee a consistent invoicing procedure for every subproject in a project structure.</span></span> 

<span data-ttu-id="95bda-109">Chaque projet qui sera facturé doit être associé à un contrat de projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-109">Every project that will be invoiced must be associated with a project contract.</span></span> <span data-ttu-id="95bda-110">Les paramètres pour un contrat de projet s'appliquent à tous les projets et sous-projets associés à ce contrat de projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-110">The settings for a project contract apply to all projects and subprojects that are associated with that project contract.</span></span> 

<span data-ttu-id="95bda-111">Dans un contrat de projet, il est possible de spécifier une ou plusieurs sources de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-111">A project contract can specify one or more sources of funding.</span></span> <span data-ttu-id="95bda-112">Par conséquent, vous pouvez diviser la facturation entre plusieurs investisseurs, définir des limites de financement afin que les sources de financement ne soient pas facturées au delà d'un montant spécifié, et configurer des règles de financement pour le débit des dépenses.</span><span class="sxs-lookup"><span data-stu-id="95bda-112">Therefore, you can split the billing among multiple funders, set up funding limits so that funding sources are not billed more than a specified amount, and configure funding rules for charging expenditures.</span></span>

## <a name="funding-for-project-contracts"></a><span data-ttu-id="95bda-113">Financement des contrats de projet</span><span class="sxs-lookup"><span data-stu-id="95bda-113">Funding for project contracts</span></span>
<span data-ttu-id="95bda-114">Certains contrats de projet spécifient que plusieurs parties partage la responsabilité du financement pour les coûts d'un projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-114">Some project contracts specify that multiple parties share the responsibility for funding the project costs.</span></span> <span data-ttu-id="95bda-115">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="95bda-115">Here are some examples:</span></span>

-   <span data-ttu-id="95bda-116">Un client important qui comporte plusieurs divisions demande que le financement d'un projet soit fractionné par division.</span><span class="sxs-lookup"><span data-stu-id="95bda-116">A large customer that has multiple divisions requests that funding of a project be split by division.</span></span>
-   <span data-ttu-id="95bda-117">Votre société partage les coûts d'un projet important avec une organisation externe.</span><span class="sxs-lookup"><span data-stu-id="95bda-117">Your company shares the costs of a large project with an external organization.</span></span>
-   <span data-ttu-id="95bda-118">Un projet de construction de route est cofinancé par deux municipalités.</span><span class="sxs-lookup"><span data-stu-id="95bda-118">A  road project is co-funded by two municipalities.</span></span>
-   <span data-ttu-id="95bda-119">Un projet de construction de pont est financé par une subvention gouvernementale et une société privée.</span><span class="sxs-lookup"><span data-stu-id="95bda-119">A bridge project is funded by a government grant and a private corporation.</span></span>

<span data-ttu-id="95bda-120">Dans Finance and Operations, vous pouvez fractionner la facturation pour une seule transaction ou un projet entier entre plusieurs clients, subventions ou organisations.</span><span class="sxs-lookup"><span data-stu-id="95bda-120">In Finance and Operations, you can split the billing for a single transaction or an entire project among multiple customers, grants, or organizations.</span></span> 

<span data-ttu-id="95bda-121">Dans les projets impliquant plusieurs investisseurs, les parties contribuant au financement d'un projet de financement avancé sont appelées sources de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-121">In projects that have multiple funders, all parties that contribute to the funding of an advanced funding project are called funding sources.</span></span> <span data-ttu-id="95bda-122">Une fois qu'un client, une organisation ou une subvention est défini comme source de financement, il peut être affecté à une ou plusieurs règles de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-122">After a customer, organization, or grant is defined as a funding source, it can be assigned to one or more funding rules.</span></span> <span data-ttu-id="95bda-123">Les règles de financement incluent les critères qui déterminent la façon dont les frais sont répartis entre les différentes sources de financement pour un projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-123">Funding rules contain the criteria that determines how charges are allocated to the various funding sources for a project.</span></span> 

<span data-ttu-id="95bda-124">Étant donné que les articles stockés, tels que ceux qui figurent sur les demandes d'achat et les commandes fournisseur, ne peuvent pas être fractionnés, le montant des coûts ne peut pas être divisé entre plusieurs sources de financement au moment de distribution.</span><span class="sxs-lookup"><span data-stu-id="95bda-124">Because stocked items, such as those that appear on purchase requisitions and purchase orders, can't be split, the cost amount can't be split among multiple funding sources at the time of distribution.</span></span> <span data-ttu-id="95bda-125">Par conséquent, la valeur de source de financement reste 0 (zéro) jusqu'à la validation de la sortie de stock.</span><span class="sxs-lookup"><span data-stu-id="95bda-125">Therefore, the funding source value remains 0 (zero) until the inventory issue is posted.</span></span> <span data-ttu-id="95bda-126">Une fois la sortie de stock validée, le montant des coûts est réparti conformément aux règles de répartition comptable du projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-126">When the inventory issue is posted, the cost amount is distributed according to the account distribution rules for the project.</span></span>

<span data-ttu-id="95bda-127">Voici quelques mesures que vous pouvez prendre pour faciliter le fractionnement de la facturation entre plusieurs sources de financement :</span><span class="sxs-lookup"><span data-stu-id="95bda-127">Here are some steps that you can take to make it easier to split the billing among multiple funding sources:</span></span>

-   <span data-ttu-id="95bda-128">Spécifiez l'utilisation par toutes les transactions entrées pour un projet de la même devise de vente que le contrat de projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-128">Specify that all transactions that are entered for a project use the same sales currency as the project contract.</span></span>
-   <span data-ttu-id="95bda-129">Paramétrez les limites de financement afin qu'une source de financement ne soit pas facturée d'un montant supérieur à celui spécifié pour un projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-129">Set up funding limits, so that a funding source isn't invoiced more than a specified amount toward a project.</span></span>
-   <span data-ttu-id="95bda-130">Configurez les règles et limites de financement pour chaque travailleur, article, catégorie, groupe de catégories et type de transaction (ou pour tous les types de transactions).</span><span class="sxs-lookup"><span data-stu-id="95bda-130">Configure funding rules and funding limits for each worker, item, category, category group, and transaction type (or for all transaction types).</span></span>
-   <span data-ttu-id="95bda-131">Sélectionnez les dates de début et de fin facultatives pour définir la période de validité de chaque règle de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-131">Select optional start and end dates to define the period when each funding rule is valid.</span></span>
-   <span data-ttu-id="95bda-132">Spécifiez le pourcentage dont chaque source de financement est responsable.</span><span class="sxs-lookup"><span data-stu-id="95bda-132">Specify the percentage that each funding source is responsible for.</span></span>
-   <span data-ttu-id="95bda-133">Spécifiez la source de financement responsable des différences d'arrondi causées par le calcul de l'allocation de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-133">Specify which funding source is responsible for rounding differences that are caused by funding allocation calculations.</span></span>
-   <span data-ttu-id="95bda-134">Paramétrez les règles qui déterminent la facturation des coûts de projet auprès des clients externes et des organisations internes.</span><span class="sxs-lookup"><span data-stu-id="95bda-134">Set up rules that determine how project costs are invoiced to external customers and charged to internal organizations.</span></span>
-   <span data-ttu-id="95bda-135">Enregistrez les transactions dans un compte de financement en attente jusqu'à l'obtention de financements supplémentaires ou la décision de prise en charge interne des coûts.</span><span class="sxs-lookup"><span data-stu-id="95bda-135">Record transactions in an on-hold funding account until additional funding can be obtained, or until you decide to bear the costs internally.</span></span>

<span data-ttu-id="95bda-136">Pour déterminer le groupe de taxe à associer à une transaction, une recherche d'affectation de groupe de taxe est effectuée dans le projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-136">To determine which tax group to associate with a transaction, the project is searched for a tax group assignment.</span></span> <span data-ttu-id="95bda-137">Si aucune affectation de groupe de taxe n'a été effectuée au niveau du projet, une recherche est effectuée dans le contrat de projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-137">If no tax group assignment has been made at the project level, the project contract is searched.</span></span>

### <a name="example-multiple-funding-sources-simple"></a><span data-ttu-id="95bda-138">Exemple : plusieurs sources de financement (simple)</span><span class="sxs-lookup"><span data-stu-id="95bda-138">Example: Multiple funding sources (simple)</span></span>

<span data-ttu-id="95bda-139">Le tableau suivant fournit des scénarios pour gérer la répartition de financement entre plusieurs sources de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-139">The following table provides scenarios for managing funding allocation among multiple funding sources.</span></span> <span data-ttu-id="95bda-140">Ces scénarios sont basés sur les suppositions suivantes :</span><span class="sxs-lookup"><span data-stu-id="95bda-140">These scenarios are based on the following assumptions:</span></span>

-   <span data-ttu-id="95bda-141">Les paramètres de priorité sont factorisés dans la répartition des fonds avant l'application d'autres critères de règle de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-141">Priority settings are factored into the allocation of funds before other funding rule criteria are applied.</span></span>
-   <span data-ttu-id="95bda-142">Aucune plage de dates n'a été spécifiée pour définir la période pendant laquelle la règle de financement est valide.</span><span class="sxs-lookup"><span data-stu-id="95bda-142">No date range has been specified to define the period d when the funding rule is valid.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="95bda-143"><strong>Scénario</strong></span><span class="sxs-lookup"><span data-stu-id="95bda-143"><strong>Scenario</strong></span></span></td>
<td><span data-ttu-id="95bda-144"><strong>Source de financement </strong></span><span class="sxs-lookup"><span data-stu-id="95bda-144"><strong>Funding source</strong></span></span></td>
<td><span data-ttu-id="95bda-145"><strong>Pourcentage de répartition </strong></span><span class="sxs-lookup"><span data-stu-id="95bda-145"><strong>Allocation percentage</strong></span></span></td>
<td><span data-ttu-id="95bda-146"><strong>Priorité de répartition </strong></span><span class="sxs-lookup"><span data-stu-id="95bda-146"><strong>Allocation priority</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="95bda-147">Vous souhaitez affecter des coûts à une source de financement jusqu'à ce que les fonds associés soient épuisés, affecter des coûts à une deuxième source de financement jusqu'à ce que les fonds associés soient épuisés, puis finalement affecter les coûts restants à une troisième source de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-147">You want to allocate costs to one funding source until its funds are exhausted, allocate costs to a second funding source until its funds are exhausted, and finally allocate the remaining costs to a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="95bda-148">Source　de financement　1</span><span class="sxs-lookup"><span data-stu-id="95bda-148">Funding　source　1</span></span></li>
<li><span data-ttu-id="95bda-149">Source　de financement　2</span><span class="sxs-lookup"><span data-stu-id="95bda-149">Funding　source　2</span></span></li>
<li><span data-ttu-id="95bda-150">Source　de financement　3</span><span class="sxs-lookup"><span data-stu-id="95bda-150">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="95bda-151">100 %</span><span class="sxs-lookup"><span data-stu-id="95bda-151">100%</span></span></li>
<li><span data-ttu-id="95bda-152">100 %</span><span class="sxs-lookup"><span data-stu-id="95bda-152">100%</span></span></li>
<li><span data-ttu-id="95bda-153">100 %</span><span class="sxs-lookup"><span data-stu-id="95bda-153">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="95bda-154">1</span><span class="sxs-lookup"><span data-stu-id="95bda-154">1</span></span></li>
<li><span data-ttu-id="95bda-155">2</span><span class="sxs-lookup"><span data-stu-id="95bda-155">2</span></span></li>
<li><span data-ttu-id="95bda-156">3</span><span class="sxs-lookup"><span data-stu-id="95bda-156">3</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="95bda-157">Vous souhaitez affecter 75 % des coûts à une source de financement et 25 % à une deuxième source de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-157">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="95bda-158">Lorsque l'une de ces sources de financement est épuisée, vous souhaitez payer les coûts restants à partir d'une troisième source de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-158">When either of those funding sources is exhausted, you want to pay the remaining costs from a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="95bda-159">Source　de financement　1</span><span class="sxs-lookup"><span data-stu-id="95bda-159">Funding　source　1</span></span></li>
<li><span data-ttu-id="95bda-160">Source　de financement　2</span><span class="sxs-lookup"><span data-stu-id="95bda-160">Funding　source　2</span></span></li>
<li><span data-ttu-id="95bda-161">Source　de financement　3</span><span class="sxs-lookup"><span data-stu-id="95bda-161">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="95bda-162">75 %</span><span class="sxs-lookup"><span data-stu-id="95bda-162">75%</span></span></li>
<li><span data-ttu-id="95bda-163">25 %</span><span class="sxs-lookup"><span data-stu-id="95bda-163">25%</span></span></li>
<li><span data-ttu-id="95bda-164">100 %</span><span class="sxs-lookup"><span data-stu-id="95bda-164">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="95bda-165">1</span><span class="sxs-lookup"><span data-stu-id="95bda-165">1</span></span></li>
<li><span data-ttu-id="95bda-166">1</span><span class="sxs-lookup"><span data-stu-id="95bda-166">1</span></span></li>
<li><span data-ttu-id="95bda-167">2</span><span class="sxs-lookup"><span data-stu-id="95bda-167">2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="95bda-168">Vous souhaitez affecter 75 % des coûts à une source de financement et 25 % à une deuxième source de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-168">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="95bda-169">Lorsque l'une des sources de financement est épuisée, vous souhaitez fractionner les coûts restants entre une troisième et une quatrième sources de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-169">When either of those funding sources is exhausted, you want to split the remaining costs between a third funding source and a fourth funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="95bda-170">Source　de financement　1</span><span class="sxs-lookup"><span data-stu-id="95bda-170">Funding　source　1</span></span></li>
<li><span data-ttu-id="95bda-171">Source　de financement　2</span><span class="sxs-lookup"><span data-stu-id="95bda-171">Funding　source　2</span></span></li>
<li><span data-ttu-id="95bda-172">Source　de financement　3</span><span class="sxs-lookup"><span data-stu-id="95bda-172">Funding　source　3</span></span></li>
<li><span data-ttu-id="95bda-173">Source　de financement　4</span><span class="sxs-lookup"><span data-stu-id="95bda-173">Funding　source　4</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="95bda-174">75 %</span><span class="sxs-lookup"><span data-stu-id="95bda-174">75%</span></span></li>
<li><span data-ttu-id="95bda-175">25 %</span><span class="sxs-lookup"><span data-stu-id="95bda-175">25%</span></span></li>
<li><span data-ttu-id="95bda-176">50 %</span><span class="sxs-lookup"><span data-stu-id="95bda-176">50%</span></span></li>
<li><span data-ttu-id="95bda-177">50 %</span><span class="sxs-lookup"><span data-stu-id="95bda-177">50%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="95bda-178">1</span><span class="sxs-lookup"><span data-stu-id="95bda-178">1</span></span></li>
<li><span data-ttu-id="95bda-179">1</span><span class="sxs-lookup"><span data-stu-id="95bda-179">1</span></span></li>
<li><span data-ttu-id="95bda-180">2</span><span class="sxs-lookup"><span data-stu-id="95bda-180">2</span></span></li>
<li><span data-ttu-id="95bda-181">2</span><span class="sxs-lookup"><span data-stu-id="95bda-181">2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="95bda-182">Vous souhaitez affecter les premiers 25 % des coûts à une source de financement et le reste à une seconde source de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-182">You want to allocate the first 25 percent of costs to one funding source and the rest to a second funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="95bda-183">Source　de financement　1</span><span class="sxs-lookup"><span data-stu-id="95bda-183">Funding　source　1</span></span></li>
<li><span data-ttu-id="95bda-184">Source　de financement　2</span><span class="sxs-lookup"><span data-stu-id="95bda-184">Funding　source　2</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="95bda-185">25 %</span><span class="sxs-lookup"><span data-stu-id="95bda-185">25%</span></span></li>
<li><span data-ttu-id="95bda-186">100 %</span><span class="sxs-lookup"><span data-stu-id="95bda-186">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="95bda-187">1</span><span class="sxs-lookup"><span data-stu-id="95bda-187">1</span></span></li>
<li><span data-ttu-id="95bda-188">2</span><span class="sxs-lookup"><span data-stu-id="95bda-188">2</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a><span data-ttu-id="95bda-189">Exemple : plusieurs sources de financement (complexe)</span><span class="sxs-lookup"><span data-stu-id="95bda-189">Example: Multiple funding sources (complex)</span></span>

<span data-ttu-id="95bda-190">Vous avez trois sources de financement que vous souhaitez utiliser dans l'ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="95bda-190">You have three funding sources that you want to use in the following order:</span></span>

1.  <span data-ttu-id="95bda-191">Utilisez la source de financement 2 et la source de financement 3 de manière égale jusqu'à ce que la source de financement 2 soit épuisée.</span><span class="sxs-lookup"><span data-stu-id="95bda-191">Use funding source 2 and funding source 3 equally until funding source 2 is exhausted.</span></span>
2.  <span data-ttu-id="95bda-192">Continuez à utiliser la source de financement 3 jusqu'à ce qu'elle soit épuisée.</span><span class="sxs-lookup"><span data-stu-id="95bda-192">Continue to use funding source 3 until it is exhausted.</span></span>
3.  <span data-ttu-id="95bda-193">Utilisez la source de financement 1 après épuisement de la source de financement 3.</span><span class="sxs-lookup"><span data-stu-id="95bda-193">Use funding source 1 after funding source 3 is exhausted.</span></span>

<span data-ttu-id="95bda-194">Pour atteindre cet objectif, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="95bda-194">To accomplish this goal, you must do the following:</span></span>

-   <span data-ttu-id="95bda-195">Paramétrez des limites de financement pour la source de financement 2 et la source de financement 3 pour leurs montants respectifs.</span><span class="sxs-lookup"><span data-stu-id="95bda-195">Set up funding limits for funding source 2 and funding source 3, for their respective amounts.</span></span>
-   <span data-ttu-id="95bda-196">Créez les règles de financement suivantes :</span><span class="sxs-lookup"><span data-stu-id="95bda-196">Create the following funding rules:</span></span>
    -   <span data-ttu-id="95bda-197">Règle 1 (Priorité 1) : affectez 50 % des transactions à la source de financement 2 et 50 % à la source de financement 3.</span><span class="sxs-lookup"><span data-stu-id="95bda-197">Rule 1 (Priority 1): Allocate 50 percent of transactions to funding source 2 and 50 percent to funding source 3.</span></span>
    -   <span data-ttu-id="95bda-198">Règle 2 (Priorité 2) : affectez 100 % des transactions à la source de financement 3.</span><span class="sxs-lookup"><span data-stu-id="95bda-198">Rule 2 (Priority 2): Allocate 100 percent of transactions to funding source 3.</span></span>
    -   <span data-ttu-id="95bda-199">Règle 3 (Priorité 3) : affectez 100 % des transactions à la source de financement 1.</span><span class="sxs-lookup"><span data-stu-id="95bda-199">Rule 3 (Priority 3): Allocate 100 percent of transactions to funding source 1.</span></span>

<span data-ttu-id="95bda-200">Ce paramétrage fonctionne car les transactions sont vérifiées par rapport aux règles et aux limites afin de déterminer si l'une de celles-ci s'applique à la transaction.</span><span class="sxs-lookup"><span data-stu-id="95bda-200">This setup works because transactions are checked against rules and limits to determine whether any of them apply to the transaction.</span></span> <span data-ttu-id="95bda-201">Si aucune règle ni limite spécifique ne s'applique à la transaction, la règle Toutes les transactions s'applique.</span><span class="sxs-lookup"><span data-stu-id="95bda-201">If no specific rules or limits apply to the transaction, the All transactions rule applies.</span></span> <span data-ttu-id="95bda-202">La règle Toutes les transactions met en correspondance toutes les transactions.</span><span class="sxs-lookup"><span data-stu-id="95bda-202">The All transactions rule matches all transactions.</span></span> 

<span data-ttu-id="95bda-203">Si une règle est trouvée qui correspond à une transaction, le pourcentage affecté à cette règle est appliqué en premier, mais seulement une fois que les correspondances sont vérifiées par rapport aux limites paramétrées.</span><span class="sxs-lookup"><span data-stu-id="95bda-203">If a rule is found that matches a transaction, the percentage that has been allocated in that rule is applied first, but only after the matches are checked against any limits that have been set up.</span></span> <span data-ttu-id="95bda-204">Si une limite a été respectée et que les fonds d'une source de financement sont épuisés, la règle de financement associée à la limite de financement est ignorée et le programme recherche la règle suivante qui s'applique.</span><span class="sxs-lookup"><span data-stu-id="95bda-204">If a limit has been met, and a funding source’s funds are exhausted, the funding rule that is associated with the funding limit is disregarded, and the program checks for the next rule that applies.</span></span> 

<span data-ttu-id="95bda-205">Dans certains cas, seule une partie d'une transaction peut être affectée en fonction d'une règle.</span><span class="sxs-lookup"><span data-stu-id="95bda-205">In some cases, only part of a transaction can be allocated under a rule.</span></span> <span data-ttu-id="95bda-206">Cela peut se produire car une limite est atteinte lorsque la transaction est affectée.</span><span class="sxs-lookup"><span data-stu-id="95bda-206">This might happen because a limit is reached when the transaction is allocated.</span></span> <span data-ttu-id="95bda-207">Dans ce cas, seul un certain montant est affecté conformément à cette règle, par exemple, 50 % à chaque source de financement.</span><span class="sxs-lookup"><span data-stu-id="95bda-207">In this case, only a certain amount is allocated according to that rule, such as 50 percent to each funding source.</span></span> <span data-ttu-id="95bda-208">C'est le cas dans la règle 1, décrite plus haut dans cette section.</span><span class="sxs-lookup"><span data-stu-id="95bda-208">This is the case in rule 1, which is described earlier in this section.</span></span> <span data-ttu-id="95bda-209">Le reste est affecté conformément à la règle suivante de la séquence.</span><span class="sxs-lookup"><span data-stu-id="95bda-209">The remainder is allocated according to the next rule in the sequence.</span></span> 

<span data-ttu-id="95bda-210">Le tableau suivant présente ce scénario plus en détail.</span><span class="sxs-lookup"><span data-stu-id="95bda-210">The following table examines this scenario in more detail.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="95bda-211"><strong>Vue </strong></span><span class="sxs-lookup"><span data-stu-id="95bda-211"><strong>Focus</strong></span></span></td>
<td><span data-ttu-id="95bda-212"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="95bda-212"><strong>Details</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="95bda-213">Règles de financement</span><span class="sxs-lookup"><span data-stu-id="95bda-213">Funding rules</span></span></td>
<td><ul>
<li><span data-ttu-id="95bda-214">Règle 1 (Priorité 1) : Toutes les transactions.</span><span class="sxs-lookup"><span data-stu-id="95bda-214">Rule 1 (Priority 1): All transactions.</span></span> <span data-ttu-id="95bda-215">Affectez 50 % à la source de financement 2 et 50 % à la source de financement 3.</span><span class="sxs-lookup"><span data-stu-id="95bda-215">Allocate funding source 2 at 50% and funding source 3 at 50%.</span></span></li>
<li><span data-ttu-id="95bda-216">Règle 2 (Priorité 2) : Toutes les transactions.</span><span class="sxs-lookup"><span data-stu-id="95bda-216">Rule 2 (Priority 2): All transactions.</span></span> <span data-ttu-id="95bda-217">Affectez 100 % à la source de financement 3.</span><span class="sxs-lookup"><span data-stu-id="95bda-217">Allocate funding source 3 at 100%.</span></span></li>
<li><span data-ttu-id="95bda-218">Règle 3 (Priorité 2) : Toutes les transactions.</span><span class="sxs-lookup"><span data-stu-id="95bda-218">Rule 3 (Priority 2): All transactions.</span></span> <span data-ttu-id="95bda-219">Affectez 100 % à la source de financement 1.</span><span class="sxs-lookup"><span data-stu-id="95bda-219">Allocate funding source 1 at 100%.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="95bda-220">Limites de financement</span><span class="sxs-lookup"><span data-stu-id="95bda-220">Funding limits</span></span></td>
<td><ul>
<li><span data-ttu-id="95bda-221">Limite de la source de financement 1 = 10 000,00</span><span class="sxs-lookup"><span data-stu-id="95bda-221">Funding source 1 limit = 10,000.00</span></span></li>
<li><span data-ttu-id="95bda-222">Limite de la source de financement 2 = 500,00</span><span class="sxs-lookup"><span data-stu-id="95bda-222">Funding source 2 limit = 500.00</span></span></li>
<li><span data-ttu-id="95bda-223">Limite de la source de financement 3 = 750,00</span><span class="sxs-lookup"><span data-stu-id="95bda-223">Funding source 3 limit = 750.00</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="95bda-224">Transaction 1</span><span class="sxs-lookup"><span data-stu-id="95bda-224">Transaction 1</span></span></td>
<td><span data-ttu-id="95bda-225"><strong>Montant de la transaction :</strong> 100,00<strong>Financement :</strong> la transaction est payée conformément à la règle 1 uniquement, car la transaction est intégralement payée une fois la règle 1 appliquée.</span><span class="sxs-lookup"><span data-stu-id="95bda-225"><strong>Transaction amount:</strong> 100.00<strong>Funding:</strong> The transaction is paid according to rule 1 only, because the transaction is fully paid after rule 1 is applied.</span></span> <span data-ttu-id="95bda-226">La transaction est financée de manière égale entre la source de financement 2 et la source de financement 3.</span><span class="sxs-lookup"><span data-stu-id="95bda-226">The transaction is funded equally between funding source 2 and funding source 3.</span></span>
<ul>
<li><span data-ttu-id="95bda-227">Source de financement 2 : 50,00</span><span class="sxs-lookup"><span data-stu-id="95bda-227">Funding source 2: 50.00</span></span></li>
<li><span data-ttu-id="95bda-228">Source de financement 3 : 50,00</span><span class="sxs-lookup"><span data-stu-id="95bda-228">Funding source 3: 50.00</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="95bda-229">Transaction 2</span><span class="sxs-lookup"><span data-stu-id="95bda-229">Transaction 2</span></span></td>
<td><span data-ttu-id="95bda-230"><strong>Montant de la transaction :</strong> 5 000,00<strong>Financement :</strong> la transaction est payée conformément aux trois règles.</span><span class="sxs-lookup"><span data-stu-id="95bda-230"><strong>Transaction amount:</strong> 5,000.00<strong>Funding:</strong> The transaction is paid according to all three rules.</span></span> <span data-ttu-id="95bda-231"><strong>Règle 1</strong>
</span><span class="sxs-lookup"><span data-stu-id="95bda-231"><strong>Rule 1</strong>
</span></span><ul>
<li><span data-ttu-id="95bda-232">Source de financement 2 : 450,00</span><span class="sxs-lookup"><span data-stu-id="95bda-232">Funding source 2: 450.00</span></span></li>
<li><span data-ttu-id="95bda-233">Source de financement 3 : 450,00</span><span class="sxs-lookup"><span data-stu-id="95bda-233">Funding source 3: 450.00</span></span></li>
</ul><span data-ttu-id="95bda-234">
<strong>Règle 2</strong>
</span><span class="sxs-lookup"><span data-stu-id="95bda-234">
<strong>Rule 2</strong>
</span></span><ul>
<li><span data-ttu-id="95bda-235">Source de financement 3 :: 250,00 (= 750,00 – 50,00 – 450,00)</span><span class="sxs-lookup"><span data-stu-id="95bda-235">Funding source 3: 250.00 (= 750.00 – 50.00 – 450.00)</span></span></li>
</ul><span data-ttu-id="95bda-236">
<strong>Règle 3</strong>
</span><span class="sxs-lookup"><span data-stu-id="95bda-236">
<strong>Rule 3</strong>
</span></span><ul>
<li><span data-ttu-id="95bda-237">Source de financement 1 : 3 850,00 (= 5 000,00 – 450,00 – 450,00 – 250,00)</span><span class="sxs-lookup"><span data-stu-id="95bda-237">Funding source 1: 3,850.00 (= 5,000.00 – 450.00 – 450.00 – 250.00)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="95bda-238">Total des fonds distribués pour chaque source de financement</span><span class="sxs-lookup"><span data-stu-id="95bda-238">Total funds that are distributed for each funding source</span></span></td>
<td><ul>
<li><span data-ttu-id="95bda-239">Source de financement 1 : 3 850,00</span><span class="sxs-lookup"><span data-stu-id="95bda-239">Funding source 1: 3,850.00</span></span></li>
<li><span data-ttu-id="95bda-240">Source de financement 2 : 500,00</span><span class="sxs-lookup"><span data-stu-id="95bda-240">Funding source 2: 500.00</span></span></li>
<li><span data-ttu-id="95bda-241">Source de financement 3 : 750,00</span><span class="sxs-lookup"><span data-stu-id="95bda-241">Funding source 3: 750.00</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a><span data-ttu-id="95bda-242">Règles de facturation</span><span class="sxs-lookup"><span data-stu-id="95bda-242">Billing rules</span></span>
<span data-ttu-id="95bda-243">Lorsque vous négociez un contrat de projet avec un client, vous définissez comment et quand facturer le client pour le travail effectué sur le projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-243">When you negotiate a project contract with a customer, you define how and when you can invoice the customer for work on a project.</span></span> <span data-ttu-id="95bda-244">Après avoir établi le contrat de projet et le projet, vous pouvez définir des règles de facturation spécifiques au projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-244">After you set up the project contract and the project, you can set up billing rules for the project.</span></span> <span data-ttu-id="95bda-245">Les règles de facturation sont basés sur les conditions du projet qui sont spécifiées dans le contrat de projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-245">Billing rules are based on the project terms that are specified in the project contract.</span></span> <span data-ttu-id="95bda-246">Les règles de facturation que vous pouvez créer dépendent des conditions du contrat de projet et du type de projet, par exemple Régie ou Prix fixe, que vous associez à la règle de facturation.</span><span class="sxs-lookup"><span data-stu-id="95bda-246">The billing rules that you can create depend on the terms of the project contract and the project type, such as Time and material or Fixed-price, that you associate with the billing rule.</span></span> <span data-ttu-id="95bda-247">Vous pouvez créer plusieurs règles de facturation pour un contrat de projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-247">You can create more than one billing rule for a project contract.</span></span> <span data-ttu-id="95bda-248">Vous pouvez également affecter une règle de facturation à plusieurs projets associés au même contrat de projet et avoir des conditions de facturation similaires.</span><span class="sxs-lookup"><span data-stu-id="95bda-248">You can also assign a billing rule to multiple projects that are associated with the same project contract and have similar billing terms.</span></span> 

<span data-ttu-id="95bda-249">Vous pouvez définir les types de règles de facturation suivants :</span><span class="sxs-lookup"><span data-stu-id="95bda-249">You can set up the following types of billing rules:</span></span>

-   <span data-ttu-id="95bda-250">**Unité de livraison** – Facturer le client à la fin d'une unité de livraison.</span><span class="sxs-lookup"><span data-stu-id="95bda-250">**Unit of delivery** – Invoice a customer when you complete a unit of delivery.</span></span> <span data-ttu-id="95bda-251">Les unités de livraison sont définies dans le contrat.</span><span class="sxs-lookup"><span data-stu-id="95bda-251">You define the units of delivery in the contract.</span></span>
-   <span data-ttu-id="95bda-252">**Progression** – Facturer le client après avoir accompli un pourcentage défini du projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-252">**Progress** – Invoice a customer when you complete a specified percentage of the project.</span></span> <span data-ttu-id="95bda-253">Vous pouvez paramétrer une règle de facturation pour calculer automatiquement le pourcentage de travail réalisé ou calculer manuellement le pourcentage de travail accompli et le montant à facturer au client.</span><span class="sxs-lookup"><span data-stu-id="95bda-253">You can set up a billing rule to automatically calculate the percentage of work completed, or you can manually calculate the percentage of work completed and the amount to invoice the customer.</span></span>
-   <span data-ttu-id="95bda-254">**Jalon** – Facturer au client le montant total correspondant à un jalon du projet une fois celui-ci atteint.</span><span class="sxs-lookup"><span data-stu-id="95bda-254">**Milestone** – Invoice a customer for the full amount of a project milestone when the milestone is reached.</span></span>
-   <span data-ttu-id="95bda-255">**Frais** – Facturer au client les services fournis plus les frais de gestion ; ces derniers correspondant généralement à un pourcentage du coût des services.</span><span class="sxs-lookup"><span data-stu-id="95bda-255">**Fee** – Invoice a customer for your services plus a management fee, which is typically a percentage of the cost of services.</span></span>
-   <span data-ttu-id="95bda-256">**Régie** – Facturer le client pour la valeur des heures et du matériel affectés à un projet en régie.</span><span class="sxs-lookup"><span data-stu-id="95bda-256">**Time and material** – Invoice a customer for the value of time and materials that are used on a project.</span></span>

<span data-ttu-id="95bda-257">Pour tous les types de règles de facturation, vous pouvez spécifier un pourcentage de rétention qui est déduit des factures client jusqu'à ce qu'un projet atteigne un stade convenu.</span><span class="sxs-lookup"><span data-stu-id="95bda-257">For all types of billing rules, you can specify a retention percentage that is deducted from customer invoices until a project reaches an agreed-upon stage.</span></span> <span data-ttu-id="95bda-258">Le pourcentage de rétention de paiement est spécifié dans le contrat de projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-258">The payment retention percentage is specified in the project contract.</span></span> <span data-ttu-id="95bda-259">Le montant est calculé selon et soustrait de la valeur totale des lignes d'une facture client.</span><span class="sxs-lookup"><span data-stu-id="95bda-259">The amount is calculated based on, and subtracted from, the total value of the lines in a customer invoice.</span></span> 

<span data-ttu-id="95bda-260">Pour les règles de facturation **Régie** et **Progression**, vous pouvez affecter des catégories facturables.</span><span class="sxs-lookup"><span data-stu-id="95bda-260">For **Time and material** and **Progress** billing rules, you can assign chargeable categories.</span></span> <span data-ttu-id="95bda-261">Les catégories facturables indiquent les transactions à inclure dans les factures client.</span><span class="sxs-lookup"><span data-stu-id="95bda-261">Chargeable categories indicate the transactions that should be included in customer invoices.</span></span> 

<span data-ttu-id="95bda-262">Ainsi, au moment de la facturation, le montant de la facture pour le projet est calculé sur la base de ces règles et une proposition de facture de projet est générée.</span><span class="sxs-lookup"><span data-stu-id="95bda-262">When you are ready to invoice the customer, the amount to invoice for the project is calculated based on the billing rules, and a project invoice proposal is generated.</span></span> 

<span data-ttu-id="95bda-263">Les sections suivantes présentent des exemples qui illustrent la manière de paramétrer et de gérer les règles de facturation pour un projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-263">The following sections provide examples that show how to set up and manage billing rules for a project.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a><span data-ttu-id="95bda-264">Exemple : création d'une règle de facturation basée sur le nombre d'unités livrées</span><span class="sxs-lookup"><span data-stu-id="95bda-264">Example: Create a billing rule that is based on the number of units delivered</span></span>

<span data-ttu-id="95bda-265">Votre organisation conclut un accord pour fournir un total de cinq sessions de formation aux employés d'un client à un coût de 10 000 par session de formation.</span><span class="sxs-lookup"><span data-stu-id="95bda-265">Your organization enters into an agreement to provide a total of five training sessions to a customer’s employees at a cost of 10,000 per training session.</span></span> <span data-ttu-id="95bda-266">Vous établissez votre facture à la fin de chaque session de formation.</span><span class="sxs-lookup"><span data-stu-id="95bda-266">You invoice the customer after each training session.</span></span> 

<span data-ttu-id="95bda-267">Lorsque vous paramétrez les règles de facturation du contrat, vous utilisez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="95bda-267">When you set up the billing rules for the contract, you use the following values:</span></span>

-   <span data-ttu-id="95bda-268">Une unité de livraison correspond à une session de formation.</span><span class="sxs-lookup"><span data-stu-id="95bda-268">The unit of delivery is one training session.</span></span>
-   <span data-ttu-id="95bda-269">Le prix unitaire est de 10 000 euros par session de formation.</span><span class="sxs-lookup"><span data-stu-id="95bda-269">The unit price is 10,000 per training session.</span></span>
-   <span data-ttu-id="95bda-270">Le nombre total d'unités est de cinq sessions de formation.</span><span class="sxs-lookup"><span data-stu-id="95bda-270">The total number of units is five training sessions.</span></span>

<span data-ttu-id="95bda-271">À la fin d'une session de formation, vous pouvez créer une facture d'un montant de 10 000 pour la première unité livrée et envoyer la facture au client.</span><span class="sxs-lookup"><span data-stu-id="95bda-271">When you have completed one training session, you can create an invoice for 10,000, for the first unit that was delivered, and send the invoice to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a><span data-ttu-id="95bda-272">Exemple : création d'une règle de facturation basée sur un pourcentage défini d'achèvement du projet (calcul manuel)</span><span class="sxs-lookup"><span data-stu-id="95bda-272">Example: Create a billing rule that is based on a specified percentage of project completion (manual calculation)</span></span>

<span data-ttu-id="95bda-273">Votre organisation, une société spécialisée dans la consultance logicielle, conclut un accord avec un client pour assurer le développement d'une partie d'un produit développé par le client.</span><span class="sxs-lookup"><span data-stu-id="95bda-273">Your organization, a software consulting firm, enters into an agreement with a customer to develop part of a product that the customer is developing.</span></span> <span data-ttu-id="95bda-274">Votre organisation s'est engagée à livrer le code logiciel sur une période de six mois.</span><span class="sxs-lookup"><span data-stu-id="95bda-274">Your organization agrees to deliver the software code over a period of six months.</span></span> <span data-ttu-id="95bda-275">Le client a accepté de verser à votre organisation un total de 100 000 euros en échange de ce travail.</span><span class="sxs-lookup"><span data-stu-id="95bda-275">The customer agrees to pay your organization a total of 100,000 for the work.</span></span> <span data-ttu-id="95bda-276">Vous créez une règle de facturation pour facturer le client sur la base du pourcentage de travail accompli pour le projet, tel que défini dans le contrat.</span><span class="sxs-lookup"><span data-stu-id="95bda-276">You create a billing rule to invoice the customer based on the percentage of work that is completed on the project, as specified in the contract.</span></span>

-   <span data-ttu-id="95bda-277">À la fin du premier mois, vous rencontrez le client pour déterminer le pourcentage de travail réalisé.</span><span class="sxs-lookup"><span data-stu-id="95bda-277">At the end of the first month, you meet with the customer to determine the percentage of work completed.</span></span> <span data-ttu-id="95bda-278">Après examen du projet par vous-même et votre client, vous décidez que le projet est réalisé à 15 %.</span><span class="sxs-lookup"><span data-stu-id="95bda-278">After you and the customer review the project, you decide that the project is 15 percent completed.</span></span>
-   <span data-ttu-id="95bda-279">Vous créez une facture d'un montant de 15 000 (15 % de 100 000) et l'envoyez au client.</span><span class="sxs-lookup"><span data-stu-id="95bda-279">You create an invoice for 15,000 (15 percent of 100,000) and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a><span data-ttu-id="95bda-280">Exemple : création d'une règle de facturation basée sur un pourcentage défini d'achèvement du projet (calcul automatique)</span><span class="sxs-lookup"><span data-stu-id="95bda-280">Example: Create a billing rule that is based on a specified percentage of project completion (automatic calculation)</span></span>

<span data-ttu-id="95bda-281">Votre organisation, une société de développement de logiciels, accepte de développer un module de gestion des salaires pour un client pour un montant de 30 000.</span><span class="sxs-lookup"><span data-stu-id="95bda-281">Your organization, a software development firm, agrees to develop a payroll accounting package for a customer for 30,000.</span></span> <span data-ttu-id="95bda-282">Le client s'est engagé à payer votre organisation sur la base du pourcentage de travail réalisé.</span><span class="sxs-lookup"><span data-stu-id="95bda-282">The customer agrees to pay your organization based on the percentage of work completed.</span></span> <span data-ttu-id="95bda-283">Vous estimez que le coût du projet s'élève à 20 000 euros.</span><span class="sxs-lookup"><span data-stu-id="95bda-283">You estimate that the project costs are 20,000.</span></span> <span data-ttu-id="95bda-284">Le contrat de projet spécifie les catégories de travail que vous utilisez dans le processus de facturation.</span><span class="sxs-lookup"><span data-stu-id="95bda-284">The project contract specifies the categories of work that you use in the billing process.</span></span> <span data-ttu-id="95bda-285">Vous paramétrez des règles de facturation qui calculent automatiquement les montants à facturer pour le pourcentage de travail réalisé dans chaque catégorie.</span><span class="sxs-lookup"><span data-stu-id="95bda-285">You set up billing rules that automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="95bda-286">Vous définissez un budget pour chaque catégorie :</span><span class="sxs-lookup"><span data-stu-id="95bda-286">You set up a budget for each category:</span></span>

-   <span data-ttu-id="95bda-287">**Développement** – Coût de 15 000 et produit de 20 000</span><span class="sxs-lookup"><span data-stu-id="95bda-287">**Development** – Cost of 15,000 and revenue of 20,000</span></span>
-   <span data-ttu-id="95bda-288">**Installation** – Coût de 5 000 et produit de 10 000</span><span class="sxs-lookup"><span data-stu-id="95bda-288">**Installation** – Cost of 5,000 and revenue of 10,000</span></span>

<span data-ttu-id="95bda-289">Lorsque vous créez votre première facture client, son montant est automatiquement calculé sur la base des informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="95bda-289">When you create a customer invoice for the first time, the invoice amount is automatically calculated based on the following information:</span></span>

-   <span data-ttu-id="95bda-290">Après un mois, le salarié qui travaille sur le projet soumet une feuille de temps pour le projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-290">After a month, the worker on the project submits a timesheet for the project.</span></span> <span data-ttu-id="95bda-291">Le coût des heures du consultant est de 5 000 euros pour le développement et de 1 000 euros pour l'installation.</span><span class="sxs-lookup"><span data-stu-id="95bda-291">The cost of the worker’s hours is 5,000 for development and 1,000 for installation.</span></span> <span data-ttu-id="95bda-292">Le travail de développement est réalisé à 33 % (coût réel de 5 000/coût budgétaire de 15 000) et le travail d'installation à 20 % (coût réel de 1 000/coût budgétaire de 5 000).</span><span class="sxs-lookup"><span data-stu-id="95bda-292">The development work is 33 percent completed (5,000 actual cost/15,000 budget cost), and the installation work is 20 percent completed (1,000 actual cost/5,000 budget cost).</span></span>
-   <span data-ttu-id="95bda-293">Le montant de 8 667 est calculé automatiquement (33 % de 20 000 + 20 % de 10 000).</span><span class="sxs-lookup"><span data-stu-id="95bda-293">The invoice amount of 8,667 is automatically calculated (33 percent of 20,000 + 20 percent of 10,000).</span></span>
-   <span data-ttu-id="95bda-294">Vous créez une facture d'un montant de 8 667 et l'envoyez au client.</span><span class="sxs-lookup"><span data-stu-id="95bda-294">You create an invoice for 8,667 and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a><span data-ttu-id="95bda-295">Exemple : création d'une règle de facturation basée sur des jalons prédéfinis</span><span class="sxs-lookup"><span data-stu-id="95bda-295">Example: Create a billing rule that is based on agreed-upon milestones</span></span>

<span data-ttu-id="95bda-296">Votre organisation, une société spécialisée en conseil de gestion, accepte de réaliser une étude de marché sur un produit de consommation que le client prévoit de vendre.</span><span class="sxs-lookup"><span data-stu-id="95bda-296">Your organization, a management consulting firm, agrees to conduct market research for a consumer product that the customer plans to sell.</span></span> <span data-ttu-id="95bda-297">L'accord prévoit que le client utilisera vos services pendant une période de trois mois à compter du mois du mars contre la somme de 50 000 euros.</span><span class="sxs-lookup"><span data-stu-id="95bda-297">The customer agrees to use your services for a period of three months, starting in March, and agrees to pay your organization 50,000.</span></span> <span data-ttu-id="95bda-298">Le projet comporte trois jalons :</span><span class="sxs-lookup"><span data-stu-id="95bda-298">The project has three milestones:</span></span>

-   <span data-ttu-id="95bda-299">Jalon 1 : collecte de données sur les consommateurs – 31 mars</span><span class="sxs-lookup"><span data-stu-id="95bda-299">Milestone 1: Collect consumer data – March 31</span></span>
-   <span data-ttu-id="95bda-300">Jalon 2 : analyse des données sur les consommateurs – 30 avril</span><span class="sxs-lookup"><span data-stu-id="95bda-300">Milestone 2: Analyze consumer data – April 30</span></span>
-   <span data-ttu-id="95bda-301">Jalon 3 : présentation d'une proposition de viabilité du produit – 31 mai</span><span class="sxs-lookup"><span data-stu-id="95bda-301">Milestone 3: Present a product viability proposal – May 31</span></span>

<span data-ttu-id="95bda-302">Le client s'est engagé à payer à votre organisation 10 000 pour le premier jalon, 20 000 pour le second jalon et 20 000 pour le troisième jalon.</span><span class="sxs-lookup"><span data-stu-id="95bda-302">The customer agrees to pay your organization 10,000 for the first milestone, 20,000 for the second milestone, and 20,000 for the third milestone.</span></span> 

<span data-ttu-id="95bda-303">Le contrat de projet stipule que le client sera facturé en fonction du jalon qui est atteint.</span><span class="sxs-lookup"><span data-stu-id="95bda-303">When you set up the project contract, you agree to bill the customer based on the milestone that has been completed.</span></span> <span data-ttu-id="95bda-304">La règle de facturation doit être définie en deux étapes :</span><span class="sxs-lookup"><span data-stu-id="95bda-304">The billing rule setup includes the following steps:</span></span>

-   <span data-ttu-id="95bda-305">Définition des jalons du projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-305">Define the project milestones.</span></span>
-   <span data-ttu-id="95bda-306">Définissez le montant à facturer au client lorsque chaque jalon est atteint.</span><span class="sxs-lookup"><span data-stu-id="95bda-306">Define the amount to invoice the customer when each milestone is completed.</span></span>

<span data-ttu-id="95bda-307">Lorsque le premier jalon est atteint, le 31 mars, vous marquez le jalon comme terminé, puis créez une facture d'un montant de 10 000 et vous l'envoyez au client.</span><span class="sxs-lookup"><span data-stu-id="95bda-307">When the first milestone is completed on March 31, you mark the milestone as completed, and then create an invoice for 10,000 and send it to the customer.</span></span> <span data-ttu-id="95bda-308">Vous ne pouvez pas créer une facture pour un jalon tant vous n'avez pas marqué le jalon comme terminé.</span><span class="sxs-lookup"><span data-stu-id="95bda-308">You can’t create an invoice for a milestone until you have marked the milestone as completed.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a><span data-ttu-id="95bda-309">Exemple : création d'une règle de facturation basée sur des services fournis plus les frais de gestion associés</span><span class="sxs-lookup"><span data-stu-id="95bda-309">Example: Create a billing rule that is based on services plus a management fee</span></span>

<span data-ttu-id="95bda-310">Votre organisation, une société spécialisée dans le conseil de gestion, accepter de réaliser une étude de marché pour évaluer la viabilité d'un produit que le client, une société de vente au détail, est en train de développer.</span><span class="sxs-lookup"><span data-stu-id="95bda-310">Your organization, a management consulting firm, agrees to conduct market research to evaluate the viability of a product that the customer, a retail company, is developing.</span></span> <span data-ttu-id="95bda-311">Les conditions de l'accord spécifient que vous fournirez les services de vos trois meilleurs consultants en gestion, qui mèneront les recherches dans le cadre d'un contrat en régie.</span><span class="sxs-lookup"><span data-stu-id="95bda-311">The terms of the agreement specify that you will provide the services of your top three management consultants, who will conduct the research on a time-and-materials basis.</span></span> <span data-ttu-id="95bda-312">Le client s'engage à payer 100 par heure, plus 10 % de frais de gestion calculés à partir des heures de conseil facturées pour le projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-312">The customer agrees to pay 100 per hour, plus a 10 percent management fee for the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="95bda-313">Au moment de la définition du contrat de projet, créez une règle de facturation pour ajouter 10 % de frais de gestion aux heures de conseil facturées pour le projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-313">When you set up the project contract, create a billing rule to add a 10 percent management fee to the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="95bda-314">Lors de la création d'une facture, vous facturez les heures de consultance plus 10 % de frais de gestion.</span><span class="sxs-lookup"><span data-stu-id="95bda-314">When you create an invoice for the customer, the customer is billed a 10 percent management fee plus the cost of the consulting hours.</span></span> <span data-ttu-id="95bda-315">Par exemple, si les trois consultants ont travaillé pendant un total de 200 heures sur le projet, une facture d'un montant de 22 000 est créée, sur la base du calcul suivant :</span><span class="sxs-lookup"><span data-stu-id="95bda-315">For example, if the three consultants worked a total of 200 hours on the project, an invoice for 22,000 is created based on the following calculation:</span></span>

-   <span data-ttu-id="95bda-316">200 heures à 100 euros l'heure = 20 000 euros</span><span class="sxs-lookup"><span data-stu-id="95bda-316">200 hours at 100 per hour = 20,000</span></span>
-   <span data-ttu-id="95bda-317">10 % de frais de gestion = 2 000</span><span class="sxs-lookup"><span data-stu-id="95bda-317">10 percent management fee = 2,000</span></span>
-   <span data-ttu-id="95bda-318">Montant total facturé = 22 000</span><span class="sxs-lookup"><span data-stu-id="95bda-318">Total invoice amount = 22,000</span></span>

<span data-ttu-id="95bda-319">Si les frais sont imposable pour un client, et que vous sélectionnez un groupe de taxe dans le contrat de projet, le groupe de taxe est automatiquement entré dans une règle de facturation pour les frais.</span><span class="sxs-lookup"><span data-stu-id="95bda-319">If fees are taxable to a customer, and you select a sales tax group in the project contract, the sales tax group is automatically entered in a billing rule for fees.</span></span>

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a><span data-ttu-id="95bda-320">Exemple : création d'une règle de facturation pour un contrat en régie</span><span class="sxs-lookup"><span data-stu-id="95bda-320">Example: Create a billing rule for the value of time and materials</span></span>

<span data-ttu-id="95bda-321">Votre organisation, une société spécialisée dans le conseil en matière de développement de logiciels, s'est engagée auprès d'un client à fournir cinq consultants techniques pour travailler sur un projet de développement logiciel durant les six prochains mois.</span><span class="sxs-lookup"><span data-stu-id="95bda-321">Your organization, a software consulting firm, agrees to provide five technical consultants to work on a software development project for a customer for the next six months.</span></span> <span data-ttu-id="95bda-322">Le client accepte de payer 150 pour chaque heure de conseil, plus le coût des fournitures de bureau.</span><span class="sxs-lookup"><span data-stu-id="95bda-322">The customer agrees to pay 150 for each consulting hour, plus the cost of office supplies.</span></span> <span data-ttu-id="95bda-323">Votre organisation envoie une facture au client à la fin de chaque mois.</span><span class="sxs-lookup"><span data-stu-id="95bda-323">Your organization sends an invoice to the customer at the end of each month.</span></span> 

<span data-ttu-id="95bda-324">Lorsque vous définissez le contrat de projet, vous convenez que le temps passé et le matériel utilisé pour le projet seront facturé au client sur une base mensuelle.</span><span class="sxs-lookup"><span data-stu-id="95bda-324">When you set up the project contract, you agree to bill the customer each month for time and materials on the project.</span></span> <span data-ttu-id="95bda-325">Vous créez une règle de facturation qui comporte les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="95bda-325">You create a billing rule that includes the following information:</span></span>

-   <span data-ttu-id="95bda-326">La durée du contrat est de six mois.</span><span class="sxs-lookup"><span data-stu-id="95bda-326">The contract period is six months.</span></span>
-   <span data-ttu-id="95bda-327">Les prestations de conseil sont calculées à un taux de 150 de l'heure.</span><span class="sxs-lookup"><span data-stu-id="95bda-327">Consulting time is calculated at a rate of 150 per hour.</span></span>
-   <span data-ttu-id="95bda-328">Les fournitures de bureau sont facturées au prix de revient, et le coût total du projet ne doit pas dépasser 10 000 pour le projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-328">Office supplies are invoiced at cost, and the total cost for the project must not exceed 10,000.</span></span>
-   <span data-ttu-id="95bda-329">Vous créez une facture client à la fin de chaque mois du calendrier pendant la durée du projet.</span><span class="sxs-lookup"><span data-stu-id="95bda-329">You create a customer invoice at the end of each calendar month during the project.</span></span>

<span data-ttu-id="95bda-330">Durant le premier mois, un total de 800 heures sont enregistrées par les consultants.</span><span class="sxs-lookup"><span data-stu-id="95bda-330">During the first month, a total of 800 hours are recorded by the consultants on the project.</span></span> <span data-ttu-id="95bda-331">Le coût des fournitures de bureau facturées pour le projet s'élève à 2 000.</span><span class="sxs-lookup"><span data-stu-id="95bda-331">The cost of office supplies that are charged to the project is 2,000.</span></span> <span data-ttu-id="95bda-332">Par conséquent, à la fin du mois, vous créez une facture de 122 000, qui englobe 800 heures à 150 de l'heure, plus 2 000 de fournitures de bureau.</span><span class="sxs-lookup"><span data-stu-id="95bda-332">Therefore, at the end of the month, you create an invoice for 122,000, which is calculated as 800 hours at 150 per hour, plus 2,000 for office supplies.</span></span>



