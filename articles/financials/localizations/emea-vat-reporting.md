---
title: "Déclaration de TVA pour l'Europe"
description: "Cette rubrique fournit des informations générales sur le paramétrage et la génération de la déclaration de TVA pour certains pays européens."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 266844
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 411f1d9d62ff1e4cedc2f4146a1f4208ee94a383
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="vat-reporting-for-europe"></a><span data-ttu-id="9ce6a-103">Déclaration de TVA pour l'Europe</span><span class="sxs-lookup"><span data-stu-id="9ce6a-103">VAT reporting for Europe</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9ce6a-104">Cette rubrique fournit des informations générales sur le paramétrage et la génération de la déclaration de TVA pour certains pays européens.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-104">This topic provides general information about setting up and generating the value-added tax (VAT) statement for some European countries.</span></span>

<span data-ttu-id="9ce6a-105">Cette rubrique fournit une approche générique du paramétrage et de la génération de la déclaration de TVA.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-105">This topic provides a generic approach to setting up and generating the VAT statement.</span></span> <span data-ttu-id="9ce6a-106">Cette approche est commune pour les utilisateurs dans les entités juridiques des pays/régions suivants :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-106">This approach is common for users in legal entities in the following countries/regions:</span></span>

-   <span data-ttu-id="9ce6a-107">Autriche</span><span class="sxs-lookup"><span data-stu-id="9ce6a-107">Austria</span></span>
-   <span data-ttu-id="9ce6a-108">Belgique</span><span class="sxs-lookup"><span data-stu-id="9ce6a-108">Belgium</span></span>
-   <span data-ttu-id="9ce6a-109">République tchèque</span><span class="sxs-lookup"><span data-stu-id="9ce6a-109">Czech Republic</span></span>
-   <span data-ttu-id="9ce6a-110">Estonie</span><span class="sxs-lookup"><span data-stu-id="9ce6a-110">Estonia</span></span>
-   <span data-ttu-id="9ce6a-111">Finlande</span><span class="sxs-lookup"><span data-stu-id="9ce6a-111">Finland</span></span>
-   <span data-ttu-id="9ce6a-112">Allemagne</span><span class="sxs-lookup"><span data-stu-id="9ce6a-112">Germany</span></span>
-   <span data-ttu-id="9ce6a-113">Lettonie</span><span class="sxs-lookup"><span data-stu-id="9ce6a-113">Latvia</span></span>
-   <span data-ttu-id="9ce6a-114">Lituanie</span><span class="sxs-lookup"><span data-stu-id="9ce6a-114">Lithuania</span></span>
-   <span data-ttu-id="9ce6a-115">Pays-Bas</span><span class="sxs-lookup"><span data-stu-id="9ce6a-115">Netherlands</span></span>
-   <span data-ttu-id="9ce6a-116">Suède</span><span class="sxs-lookup"><span data-stu-id="9ce6a-116">Sweden</span></span>

## <a name="vat-statement-overview"></a><span data-ttu-id="9ce6a-117">Vue d'ensemble de la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="9ce6a-117">VAT statement overview</span></span>
<span data-ttu-id="9ce6a-118">La déclaration de TVA est basée sur les montants des transactions de taxe.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-118">The VAT statement is based on tax transactions’ amounts.</span></span> <span data-ttu-id="9ce6a-119">Le processus de génération d'une déclaration de TVA fait partie du processus de paiement de la taxe, qui est implémenté via la fonction Régler et valider la taxe.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-119">The process of generating a VAT statement is part of the Sales tax payment process, which is implemented through the Settle and post sales tax function.</span></span> <span data-ttu-id="9ce6a-120">Cette fonction calcule la taxe due pour une période donnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-120">This function calculates the sales tax that is due for a given period.</span></span> <span data-ttu-id="9ce6a-121">Le calcul du règlement inclut la taxe validée pour la période de règlement sélectionnée pour les transactions de taxe.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-121">The settlement calculation includes the posted sales tax for the selected settlement period for the tax transactions.</span></span> <span data-ttu-id="9ce6a-122">Le processus de calcul des données d'une déclaration de TVA est basé sur la relation entre les codes taxe et les codes déclaration de taxe, où les codes déclaration de taxe correspondent aux zones de déclaration de TVA (ou balises en XML).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-122">The process for calculating data for a VAT statement is based on the relationship between sales tax codes and sales tax reporting codes, where sales tax reporting codes match the VAT statements boxes (or tags in XML).</span></span> <span data-ttu-id="9ce6a-123">Pour chaque code taxe, des codes déclaration de taxe doivent être définis pour chaque type de transaction, par exemple les ventes imposables, les achats imposables, les importations imposables.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-123">For each sales tax code, sales tax reporting codes should be set up for each type of transaction, such as taxable sales, taxable purchases, taxable import.</span></span> <span data-ttu-id="9ce6a-124">Ces types de transactions sont décrits dans la section Codes taxe pour la déclaration de TVA plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-124">These type of transactions are described in the Sales tax codes for VAT reporting section later in this topic.</span></span>

<span data-ttu-id="9ce6a-125">Pour chaque code déclaration de taxe, une présentation d'état spécifique doit être déterminée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-125">For each sales tax reporting code, a specific report layout should be determined.</span></span> <span data-ttu-id="9ce6a-126">Les codes taxe sont également liés à une administration fiscale spécifique via des périodes de règlement de la taxe.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-126">At the same time, sales tax codes are linked to a specific sales tax authority through sales tax settlement periods.</span></span> <span data-ttu-id="9ce6a-127">Pour chaque administration fiscale, une présentation d'état doit être déterminée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-127">For every sales tax authority, a report layout should be determined.</span></span> <span data-ttu-id="9ce6a-128">Ainsi, seuls les codes déclaration de taxe avec la même présentation d'état paramétrée pour une administration fiscale dans les périodes de règlement de la taxe pour le code taxe peuvent être sélectionnés dans le paramétrage d'état du code taxe.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-128">Thus, only sales tax reporting codes with the same report layout that is set up for a sales tax authority in sales tax settlement periods for the sales tax code can be selected in the report setup of the sales tax code.</span></span> <span data-ttu-id="9ce6a-129">Une transaction de taxe générée lors de la validation d'une commande ou d'un journal, contient un code taxe, une source de taxe, une direction de taxe et des montants de transaction (montant de base de la taxe et montant de la taxe dans la devise comptable, la devise de taxe et la devise de la transaction).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-129">A sales tax transaction generated upon posting an order or a journal, contains a sales tax code, sales tax source, sales tax direction, and transaction amounts (tax base amount and tax amount in accounting currency, sales-tax currency, and transaction currency).</span></span> <span data-ttu-id="9ce6a-130">Selon la combinaison d'attributs de transaction de taxe, les montants des transactions composent les montants totaux pour les codes déclaration de taxe spécifiés pour les codes taxe.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-130">Based on the combination of tax transaction attributes, transaction amounts compose total amounts for sales tax reporting codes specified for sales tax codes.</span></span> <span data-ttu-id="9ce6a-131">La relation des données est illustrée dans le graphique ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-131">The following illustration shows the data relationship.</span></span>

![diagramme](./media/diagram4.jpg)

## <a name="vat-statement-setup"></a><span data-ttu-id="9ce6a-133">Paramétrage de la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="9ce6a-133">VAT statement setup</span></span>
<span data-ttu-id="9ce6a-134">Pour générer une déclaration de TVA, vous devez paramétrer les éléments suivants.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-134">To generate a VAT statement you must set up the following.</span></span>

### <a name="sales-tax-authorities-for-vat-reporting"></a><span data-ttu-id="9ce6a-135">Administrations fiscales pour la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="9ce6a-135">Sales tax authorities for VAT reporting</span></span>

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](general-ledger/tasks/set-up-sales-tax-authorities). -->
<span data-ttu-id="9ce6a-136">Avant de paramétrer les codes déclaration de taxe, vous devez sélectionner la présentation d'état correcte pour l'administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-136">Before you can set up sales tax reporting codes, you must select the correct report layout for the sales tax authority.</span></span> <span data-ttu-id="9ce6a-137">Dans la page **Administrations fiscales**, dans la section **Général**, sélectionnez une **Présentation d'état**.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-137">On the **Sales tax authorities** page, in the **General** section, select a **Report layout**.</span></span> <span data-ttu-id="9ce6a-138">Cette présentation sera utilisée lors du paramétrage des codes déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-138">This layout will be used when you set up sales tax reporting codes.</span></span>

### <a name="sales-tax-reporting-codes"></a><span data-ttu-id="9ce6a-139">Codes déclaration de taxe</span><span class="sxs-lookup"><span data-stu-id="9ce6a-139">Sales tax reporting codes</span></span>

<span data-ttu-id="9ce6a-140">Les codes déclaration de taxe sont des codes de zone dans la déclaration de TVA ou des noms de balise au format XML.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-140">Sales tax reporting codes are box codes in the VAT statement or tag names in XML format.</span></span> <span data-ttu-id="9ce6a-141">Ces codes sont utilisés pour regrouper et préparer les montants pour l'état.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-141">These codes are used to aggregate and prepare amounts for the report.</span></span> <span data-ttu-id="9ce6a-142">Lorsque vous configurez le format de génération d'états électroniques de la déclaration de TVA, les noms des montants de résultat sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-142">When you configure the electronic reporting format of the VAT statement, the names of the result amounts will be used.</span></span> <span data-ttu-id="9ce6a-143">Vous pouvez créer et tenir à jour les codes déclaration de taxe dans la page **Codes déclaration de taxe**.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-143">You can create and maintain sales tax reporting codes on the **Sales tax reporting codes** page.</span></span> <span data-ttu-id="9ce6a-144">Vous devez affecter une présentation d'état à chaque code.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-144">You must assign each code a report layout.</span></span> <span data-ttu-id="9ce6a-145">Après avoir créé les codes déclaration de taxe, vous pouvez choisir les codes dans la section **Paramétrage d'état** de la page **Codes taxe**.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-145">After you create the sales tax reporting codes, you can choose the codes in the **Report setup** section on the **Sales tax codes** page.</span></span> <!---For more information, see [Set up sales tax reporting codes](../general-ledger/tasks/set-up-sales-tax-reporting-codes.md).-->

### <a name="sales-tax-codes-for-vat-reporting"></a><span data-ttu-id="9ce6a-146">Codes taxe pour la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="9ce6a-146">Sales tax codes for VAT reporting</span></span>

<!---For general information about setting up sales tax codes, see [Set up sales tax codes](../general-ledger/tasks/set-up-sales-tax-codes.md).--> Base amounts and tax amounts of sales tax transactions can be aggregated on reporting codes in the VAT statement (XML tags or declaration boxes). You can set this up by associating sales tax reporting codes for different transaction types for sales tax codes on the **Sales tax codes** page. The following table describes the transaction types in the report setup for sales tax codes. The calculation includes transactions for all types of sources except sales tax.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9ce6a-147"><strong>Type de transaction</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-147"><strong>Transaction type</strong></span></span></td>
<td><span data-ttu-id="9ce6a-148"><strong>Description des transactions et des montants à comptabiliser sur le type de transaction</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-148"><strong>Description of transactions and amounts to be counted on the transaction type</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9ce6a-149"><strong>Ventes soumises à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-149"><strong>Taxable Sales</strong></span></span></td>
<td><span data-ttu-id="9ce6a-150">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-150">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-151">La date de transaction se trouve dans la période sélectionnée/</span><span class="sxs-lookup"><span data-stu-id="9ce6a-151">Transaction date is in the selected period/</span></span></li>
<li><span data-ttu-id="9ce6a-152">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-152">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="9ce6a-153">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-153">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9ce6a-154"><strong>Vente détaxée</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-154"><strong>Tax-free sales</strong></span></span></td>
<td><span data-ttu-id="9ce6a-155">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-155">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-156">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-156">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-157">La vente est de type exportation (la <strong>Direction de la taxe</strong> est <strong>Vente détaxée</strong>).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-157">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="9ce6a-158">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-158">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9ce6a-159"><strong>Taxe collectée</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-159"><strong>Sales tax payable</strong></span></span></td>
<td><span data-ttu-id="9ce6a-160">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-160">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-161">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-161">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-162">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-162">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="9ce6a-163">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-163">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9ce6a-164"><strong>Avoir soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-164"><strong>Taxable sales credit note</strong></span></span></td>
<td><span data-ttu-id="9ce6a-165">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-165">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-166">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-166">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-167">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-167">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="9ce6a-168">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-168">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9ce6a-169"><strong>Avoir sur vente exonéré de taxe</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-169"><strong>Fax exempt sales credit note</strong></span></span></td>
<td><span data-ttu-id="9ce6a-170">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-170">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-171">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-171">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-172">La vente est de type exportation (la <strong>Direction de la taxe</strong> est <strong>Vente détaxée</strong>).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-172">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="9ce6a-173">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-173">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9ce6a-174"><strong>Taxe sur avoir sur vente</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-174"><strong>Sales tax on sales credit note</strong></span></span></td>
<td><span data-ttu-id="9ce6a-175">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-175">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-176">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-176">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-177">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-177">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="9ce6a-178">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-178">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9ce6a-179"><strong>Achats soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-179"><strong>Taxable purchases</strong></span></span></td>
<td><span data-ttu-id="9ce6a-180">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-180">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-181">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-181">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-182">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-182">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="9ce6a-183">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-183">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9ce6a-184"><strong>Achat détaxé</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-184"><strong>Tax-free purchase</strong></span></span></td>
<td><span data-ttu-id="9ce6a-185">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-185">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-186">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-186">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-187">L'achat est de type importation (la <strong>Direction de la taxe</strong> est <strong>Achat détaxé</strong>).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-187">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="9ce6a-188">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-188">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9ce6a-189"><strong>Taxe déductible</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-189"><strong>Sales tax receivable</strong></span></span></td>
<td><span data-ttu-id="9ce6a-190">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-190">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-191">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-191">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-192">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-192">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="9ce6a-193">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-193">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9ce6a-194"><strong>Avoir sur achat soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-194"><strong>Taxable purchase credit note</strong></span></span></td>
<td><span data-ttu-id="9ce6a-195">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-195">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-196">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-196">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-197">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-197">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="9ce6a-198">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-198">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9ce6a-199"><strong>Avoir sur achat exonéré de taxe</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-199"><strong>Tax exempt purchase credit note</strong></span></span></td>
<td><span data-ttu-id="9ce6a-200">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-200">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-201">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-201">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-202">L'achat est de type importation (la <strong>Direction de la taxe</strong> est <strong>Achat détaxé</strong>).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-202">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="9ce6a-203">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-203">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9ce6a-204"><strong>Taxe sur avoir sur achat</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-204"><strong>Sales tax on purchase credit note</strong></span></span></td>
<td><span data-ttu-id="9ce6a-205">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-205">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-206">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-206">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-207">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="9ce6a-207">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="9ce6a-208">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-208">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9ce6a-209"><strong>Importation soumise à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-209"><strong>Taxable import</strong></span></span></td>
<td><span data-ttu-id="9ce6a-210">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-210">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-211">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-211">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-212">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-212"><strong>Tax direction</strong> is <strong>Use tax</strong></span></span></li>
<li><span data-ttu-id="9ce6a-213">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-213">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9ce6a-214"><strong>Contrepartie des importations soumises à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-214"><strong>Offset taxable import</strong></span></span></td>
<td><span data-ttu-id="9ce6a-215">Somme contrepassée des <strong>Montants de base de la taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-215">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-216">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-216">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-217">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-217"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="9ce6a-218">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-218">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9ce6a-219"><strong>Avoir sur importation soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-219"><strong>Taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="9ce6a-220">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-220">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-221">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-221">Transaction date is in the selected period.</span></span></li>
<span data-ttu-id="9ce6a-222">e</span><span class="sxs-lookup"><span data-stu-id="9ce6a-222">e</span></span><li><span data-ttu-id="9ce6a-223">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-223"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="9ce6a-224">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-224">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9ce6a-225"><strong>Contrepartie des avoirs sur importations soumises à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-225"><strong>Offset taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="9ce6a-226">Somme contrepassée des <strong>Montants de base de la taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-226">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-227">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-227">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-228">La Direction de la taxe est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-228">Tax direction is <strong>Use tax</strong>.</span></span></li>
<span data-ttu-id="9ce6a-229">d</span><span class="sxs-lookup"><span data-stu-id="9ce6a-229">d</span></span><li><span data-ttu-id="9ce6a-230">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-230">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9ce6a-231"><strong>Taxe d'utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-231"><strong>Use tax</strong></span></span></td>
<td><span data-ttu-id="9ce6a-232">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-232">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-233">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-233">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-234">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-234"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="9ce6a-235">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-235">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9ce6a-236"><strong>Contrepartie taxe d'utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="9ce6a-236"><strong>Offset use tax</strong></span></span></td>
<td><span data-ttu-id="9ce6a-237">Somme contrepassée des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-237">Reversed sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9ce6a-238">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-238">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="9ce6a-239">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-239"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="9ce6a-240">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-240">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="9ce6a-241">Pour le tableau ci-dessus, on suppose que les critères suivants sont remplis :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-241">For the table above, it is assumed that the following criteria are met:</span></span> 
> -   <span data-ttu-id="9ce6a-242">Le montant de base de la taxe est un montant de transaction issu du champ **Origine dans la devise comptable**.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-242">The tax base amount is a transaction amount from the **Origin in Accounting currency** field.</span></span>
> -   <span data-ttu-id="9ce6a-243">Le montant de la taxe est un montant de transition issu du champ **Montant réel de la taxe dans la devise comptable**.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-243">The tax amount is a transition amount from the **Actual sales tax amount in Accounting currency** field.</span></span>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="9ce6a-244">Configurer le modèle et le format ER pour l'état</span><span class="sxs-lookup"><span data-stu-id="9ce6a-244">Configure the ER model and format for the report</span></span>

<span data-ttu-id="9ce6a-245">Vous pouvez utiliser les états électroniques pour configurer les déclarations et l'état, et pour exporter les données dans différents formats électroniques sans modifier le code X++.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-245">You can use Electronic Reporting (ER) to configure statements and report, and to export data different electronic formats without changing X++ code.</span></span> <span data-ttu-id="9ce6a-246">Pour des informations supplémentaires :</span><span class="sxs-lookup"><span data-stu-id="9ce6a-246">For additional information:</span></span>

-   [<span data-ttu-id="9ce6a-247">Vue d'ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="9ce6a-247">Electronic reporting overview</span></span>](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="9ce6a-248">Télécharger les configurations d'états électroniques à partir de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="9ce6a-248">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="9ce6a-249">Exigences de localisation – Créer une configuration GER</span><span class="sxs-lookup"><span data-stu-id="9ce6a-249">Localization requirements – Create a GER configuration</span></span>](../../dev-itpro/analytics/electronic-reporting-configuration.md)

## <a name="countryspecific-resources-for-vat-statements"></a><span data-ttu-id="9ce6a-250">Ressources spécifiques au pays pour les déclarations de TVA</span><span class="sxs-lookup"><span data-stu-id="9ce6a-250">Countryspecific resources for VAT statements</span></span>
<span data-ttu-id="9ce6a-251">La déclaration de TVA pour chaque pays doit répondre aux exigences de la législation du pays.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-251">The VAT statement for each country must meet the requirements of the country’s legislation.</span></span> <span data-ttu-id="9ce6a-252">Il existe des modèles et des formats généraux prédéfinis de déclarations de TVA pour les pays répertoriés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="9ce6a-252">There are predefined general models and formats of VAT statements for the countries listed in the following table.</span></span>


| <span data-ttu-id="9ce6a-253">Pays</span><span class="sxs-lookup"><span data-stu-id="9ce6a-253">Country</span></span>        | <span data-ttu-id="9ce6a-254">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9ce6a-254">Additional information</span></span>                                                          |
|----------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="9ce6a-255">Autriche</span><span class="sxs-lookup"><span data-stu-id="9ce6a-255">Austria</span></span>        |  [<span data-ttu-id="9ce6a-256">Détails de la déclaration de TVA pour l'Autriche</span><span class="sxs-lookup"><span data-stu-id="9ce6a-256">VAT statement details for Austria</span></span>](emea-aut-vat-statement-details.md)         |
| <span data-ttu-id="9ce6a-257">Belgique</span><span class="sxs-lookup"><span data-stu-id="9ce6a-257">Belgium</span></span>        |                                                                                 |
| <span data-ttu-id="9ce6a-258">République tchèque</span><span class="sxs-lookup"><span data-stu-id="9ce6a-258">Czech Republic</span></span> |  [<span data-ttu-id="9ce6a-259">Détails de la déclaration de TVA pour la République tchèque</span><span class="sxs-lookup"><span data-stu-id="9ce6a-259">VAT statement details for Czech Republic</span></span>](emea-cze-vat-statement-details.md)   |
| <span data-ttu-id="9ce6a-260">Estonie</span><span class="sxs-lookup"><span data-stu-id="9ce6a-260">Estonia</span></span>        |  [<span data-ttu-id="9ce6a-261">Détails de la déclaration de TVA pour l'Estonie</span><span class="sxs-lookup"><span data-stu-id="9ce6a-261">VAT statement details for Estonia</span></span>](emea-est-vat-statement-details.md) |
| <span data-ttu-id="9ce6a-262">Finlande</span><span class="sxs-lookup"><span data-stu-id="9ce6a-262">Finland</span></span>        |                                                                                 |
| <span data-ttu-id="9ce6a-263">Allemagne</span><span class="sxs-lookup"><span data-stu-id="9ce6a-263">Germany</span></span>        |                                                                                 |
| <span data-ttu-id="9ce6a-264">Italie</span><span class="sxs-lookup"><span data-stu-id="9ce6a-264">Italy</span></span>          | [<span data-ttu-id="9ce6a-265">Détails de la déclaration de TVA pour l'Italie</span><span class="sxs-lookup"><span data-stu-id="9ce6a-265">VAT statement details for Italy</span></span>](emea-ita-vat-statements-details.md)            |
| <span data-ttu-id="9ce6a-266">Lettonie</span><span class="sxs-lookup"><span data-stu-id="9ce6a-266">Latvia</span></span>         | [<span data-ttu-id="9ce6a-267">Détails de la déclaration de TVA pour la Lettonie</span><span class="sxs-lookup"><span data-stu-id="9ce6a-267">VAT statement details for Latvia</span></span>](emea-lva-vat-statement-details.md)           |
| <span data-ttu-id="9ce6a-268">Lituanie</span><span class="sxs-lookup"><span data-stu-id="9ce6a-268">Lithuania</span></span>      | [<span data-ttu-id="9ce6a-269">Détails de la déclaration de TVA pour la Lituanie</span><span class="sxs-lookup"><span data-stu-id="9ce6a-269">VAT statement details for Lithuania</span></span>](emea-ltu-vat-statement-details.md)         |
| <span data-ttu-id="9ce6a-270">Pays-Bas</span><span class="sxs-lookup"><span data-stu-id="9ce6a-270">Netherlands</span></span>    |                                                                                 |
| <span data-ttu-id="9ce6a-271">Suède</span><span class="sxs-lookup"><span data-stu-id="9ce6a-271">Sweden</span></span>         |                                                                                 |






