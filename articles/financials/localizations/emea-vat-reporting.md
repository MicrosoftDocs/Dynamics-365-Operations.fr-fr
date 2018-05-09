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
ms.search.scope: Core, Operations
ms.custom: 266844
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 5c5cd61c45eb7cbc6f040f054a99d9a54e1ee854
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="vat-reporting-for-europe"></a><span data-ttu-id="cbb96-103">Déclaration de TVA pour l'Europe</span><span class="sxs-lookup"><span data-stu-id="cbb96-103">VAT reporting for Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cbb96-104">Cette rubrique fournit des informations générales sur le paramétrage et la génération de la déclaration de TVA pour certains pays européens.</span><span class="sxs-lookup"><span data-stu-id="cbb96-104">This topic provides general information about setting up and generating the value-added tax (VAT) statement for some European countries.</span></span>

<span data-ttu-id="cbb96-105">Cette rubrique fournit une approche générique du paramétrage et de la génération de la déclaration de TVA.</span><span class="sxs-lookup"><span data-stu-id="cbb96-105">This topic provides a generic approach to setting up and generating the VAT statement.</span></span> <span data-ttu-id="cbb96-106">Cette approche est commune pour les utilisateurs dans les entités juridiques des pays/régions suivants :</span><span class="sxs-lookup"><span data-stu-id="cbb96-106">This approach is common for users in legal entities in the following countries/regions:</span></span>

-   <span data-ttu-id="cbb96-107">Autriche</span><span class="sxs-lookup"><span data-stu-id="cbb96-107">Austria</span></span>
-   <span data-ttu-id="cbb96-108">Belgique</span><span class="sxs-lookup"><span data-stu-id="cbb96-108">Belgium</span></span>
-   <span data-ttu-id="cbb96-109">République tchèque</span><span class="sxs-lookup"><span data-stu-id="cbb96-109">Czech Republic</span></span>
-   <span data-ttu-id="cbb96-110">Estonie</span><span class="sxs-lookup"><span data-stu-id="cbb96-110">Estonia</span></span>
-   <span data-ttu-id="cbb96-111">Finlande</span><span class="sxs-lookup"><span data-stu-id="cbb96-111">Finland</span></span>
-   <span data-ttu-id="cbb96-112">Allemagne</span><span class="sxs-lookup"><span data-stu-id="cbb96-112">Germany</span></span>
-   <span data-ttu-id="cbb96-113">Lettonie</span><span class="sxs-lookup"><span data-stu-id="cbb96-113">Latvia</span></span>
-   <span data-ttu-id="cbb96-114">Lituanie</span><span class="sxs-lookup"><span data-stu-id="cbb96-114">Lithuania</span></span>
-   <span data-ttu-id="cbb96-115">Pays-Bas</span><span class="sxs-lookup"><span data-stu-id="cbb96-115">Netherlands</span></span>
-   <span data-ttu-id="cbb96-116">Suède</span><span class="sxs-lookup"><span data-stu-id="cbb96-116">Sweden</span></span>

## <a name="vat-statement-overview"></a><span data-ttu-id="cbb96-117">Vue d'ensemble de la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="cbb96-117">VAT statement overview</span></span>
<span data-ttu-id="cbb96-118">La déclaration de TVA est basée sur les montants des transactions de taxe.</span><span class="sxs-lookup"><span data-stu-id="cbb96-118">The VAT statement is based on tax transactions’ amounts.</span></span> <span data-ttu-id="cbb96-119">Le processus de génération d'une déclaration de TVA fait partie du processus de paiement de la taxe, qui est implémenté via la fonction Régler et valider la taxe.</span><span class="sxs-lookup"><span data-stu-id="cbb96-119">The process of generating a VAT statement is part of the Sales tax payment process, which is implemented through the Settle and post sales tax function.</span></span> <span data-ttu-id="cbb96-120">Cette fonction calcule la taxe due pour une période donnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-120">This function calculates the sales tax that is due for a given period.</span></span> <span data-ttu-id="cbb96-121">Le calcul du règlement inclut la taxe validée pour la période de règlement sélectionnée pour les transactions de taxe.</span><span class="sxs-lookup"><span data-stu-id="cbb96-121">The settlement calculation includes the posted sales tax for the selected settlement period for the tax transactions.</span></span> <span data-ttu-id="cbb96-122">Le processus de calcul des données d'une déclaration de TVA est basé sur la relation entre les codes taxe et les codes déclaration de taxe, où les codes déclaration de taxe correspondent aux zones de déclaration de TVA (ou balises en XML).</span><span class="sxs-lookup"><span data-stu-id="cbb96-122">The process for calculating data for a VAT statement is based on the relationship between sales tax codes and sales tax reporting codes, where sales tax reporting codes match the VAT statements boxes (or tags in XML).</span></span> <span data-ttu-id="cbb96-123">Pour chaque code taxe, des codes déclaration de taxe doivent être définis pour chaque type de transaction, par exemple les ventes imposables, les achats imposables, les importations imposables.</span><span class="sxs-lookup"><span data-stu-id="cbb96-123">For each sales tax code, sales tax reporting codes should be set up for each type of transaction, such as taxable sales, taxable purchases, taxable import.</span></span> <span data-ttu-id="cbb96-124">Ces types de transactions sont décrits dans la section Codes taxe pour la déclaration de TVA plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="cbb96-124">These type of transactions are described in the Sales tax codes for VAT reporting section later in this topic.</span></span>

<span data-ttu-id="cbb96-125">Pour chaque code déclaration de taxe, une présentation d'état spécifique doit être déterminée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-125">For each sales tax reporting code, a specific report layout should be determined.</span></span> <span data-ttu-id="cbb96-126">Les codes taxe sont également liés à une administration fiscale spécifique via des périodes de règlement de la taxe.</span><span class="sxs-lookup"><span data-stu-id="cbb96-126">At the same time, sales tax codes are linked to a specific sales tax authority through sales tax settlement periods.</span></span> <span data-ttu-id="cbb96-127">Pour chaque administration fiscale, une présentation d'état doit être déterminée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-127">For every sales tax authority, a report layout should be determined.</span></span> <span data-ttu-id="cbb96-128">Ainsi, seuls les codes déclaration de taxe avec la même présentation d'état paramétrée pour une administration fiscale dans les périodes de règlement de la taxe pour le code taxe peuvent être sélectionnés dans le paramétrage d'état du code taxe.</span><span class="sxs-lookup"><span data-stu-id="cbb96-128">Thus, only sales tax reporting codes with the same report layout that is set up for a sales tax authority in sales tax settlement periods for the sales tax code can be selected in the report setup of the sales tax code.</span></span> <span data-ttu-id="cbb96-129">Une transaction de taxe générée lors de la validation d'une commande ou d'un journal, contient un code taxe, une source de taxe, une direction de taxe et des montants de transaction (montant de base de la taxe et montant de la taxe dans la devise comptable, la devise de taxe et la devise de la transaction).</span><span class="sxs-lookup"><span data-stu-id="cbb96-129">A sales tax transaction generated upon posting an order or a journal, contains a sales tax code, sales tax source, sales tax direction, and transaction amounts (tax base amount and tax amount in accounting currency, sales-tax currency, and transaction currency).</span></span> <span data-ttu-id="cbb96-130">Selon la combinaison d'attributs de transaction de taxe, les montants des transactions composent les montants totaux pour les codes déclaration de taxe spécifiés pour les codes taxe.</span><span class="sxs-lookup"><span data-stu-id="cbb96-130">Based on the combination of tax transaction attributes, transaction amounts compose total amounts for sales tax reporting codes specified for sales tax codes.</span></span> <span data-ttu-id="cbb96-131">La relation des données est illustrée dans le graphique ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="cbb96-131">The following illustration shows the data relationship.</span></span>

![diagramme](./media/diagram4.jpg)

## <a name="vat-statement-setup"></a><span data-ttu-id="cbb96-133">Paramétrage de la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="cbb96-133">VAT statement setup</span></span>
<span data-ttu-id="cbb96-134">Pour générer une déclaration de TVA, vous devez paramétrer les éléments suivants.</span><span class="sxs-lookup"><span data-stu-id="cbb96-134">To generate a VAT statement you must set up the following.</span></span>

### <a name="sales-tax-authorities-for-vat-reporting"></a><span data-ttu-id="cbb96-135">Administrations fiscales pour la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="cbb96-135">Sales tax authorities for VAT reporting</span></span>

<span data-ttu-id="cbb96-136">Avant de paramétrer les codes déclaration de taxe, vous devez sélectionner la présentation d'état correcte pour l'administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="cbb96-136">Before you can set up sales tax reporting codes, you must select the correct report layout for the sales tax authority.</span></span> <span data-ttu-id="cbb96-137">Dans la page **Administrations fiscales**, dans la section **Général**, sélectionnez une **Présentation d'état**.</span><span class="sxs-lookup"><span data-stu-id="cbb96-137">On the **Sales tax authorities** page, in the **General** section, select a **Report layout**.</span></span> <span data-ttu-id="cbb96-138">Cette présentation sera utilisée lors du paramétrage des codes déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="cbb96-138">This layout will be used when you set up sales tax reporting codes.</span></span>

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](../general-ledger/tasks/set-up-sales-tax-authorities.md). -->

### <a name="sales-tax-reporting-codes"></a><span data-ttu-id="cbb96-139">Codes déclaration de taxe</span><span class="sxs-lookup"><span data-stu-id="cbb96-139">Sales tax reporting codes</span></span>

<span data-ttu-id="cbb96-140">Les codes déclaration de taxe sont des codes de zone dans la déclaration de TVA ou des noms de balise au format XML.</span><span class="sxs-lookup"><span data-stu-id="cbb96-140">Sales tax reporting codes are box codes in the VAT statement or tag names in XML format.</span></span> <span data-ttu-id="cbb96-141">Ces codes sont utilisés pour regrouper et préparer les montants pour l'état.</span><span class="sxs-lookup"><span data-stu-id="cbb96-141">These codes are used to aggregate and prepare amounts for the report.</span></span> <span data-ttu-id="cbb96-142">Lorsque vous configurez le format de génération d'états électroniques de la déclaration de TVA, les noms des montants de résultat sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="cbb96-142">When you configure the electronic reporting format of the VAT statement, the names of the result amounts will be used.</span></span> <span data-ttu-id="cbb96-143">Vous pouvez créer et tenir à jour les codes déclaration de taxe dans la page **Codes déclaration de taxe**.</span><span class="sxs-lookup"><span data-stu-id="cbb96-143">You can create and maintain sales tax reporting codes on the **Sales tax reporting codes** page.</span></span> <span data-ttu-id="cbb96-144">Vous devez affecter une présentation d'état à chaque code.</span><span class="sxs-lookup"><span data-stu-id="cbb96-144">You must assign each code a report layout.</span></span> <span data-ttu-id="cbb96-145">Après avoir créé les codes déclaration de taxe, vous pouvez choisir les codes dans la section **Paramétrage d'état** de la page **Codes taxe**.</span><span class="sxs-lookup"><span data-stu-id="cbb96-145">After you create the sales tax reporting codes, you can choose the codes in the **Report setup** section on the **Sales tax codes** page.</span></span> <!---For more information, see [Set up sales tax reporting codes](../general-ledger/tasks/set-up-sales-tax-reporting-codes.md).-->

### <a name="sales-tax-codes-for-vat-reporting"></a><span data-ttu-id="cbb96-146">Codes taxe pour la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="cbb96-146">Sales tax codes for VAT reporting</span></span>

<span data-ttu-id="cbb96-147"><!---For general information about setting up sales tax codes, see [Set up sales tax codes](../general-ledger/tasks/set-up-sales-tax-codes.md).--> Base amounts and tax amounts of sales tax transactions can be aggregated on reporting codes in the VAT statement (XML tags or declaration boxes). You can set this up by associating sales tax reporting codes for different transaction types for sales tax codes on the <strong>page Codes taxe</strong>.</span><span class="sxs-lookup"><span data-stu-id="cbb96-147"><!---For general information about setting up sales tax codes, see [Set up sales tax codes](../general-ledger/tasks/set-up-sales-tax-codes.md).--> Base amounts and tax amounts of sales tax transactions can be aggregated on reporting codes in the VAT statement (XML tags or declaration boxes). You can set this up by associating sales tax reporting codes for different transaction types for sales tax codes on the <strong>Sales tax codes</strong> page.</span></span> <span data-ttu-id="cbb96-148">Le tableau suivant décrit les types de transaction dans le paramétrage d'état pour les codes taxe.</span><span class="sxs-lookup"><span data-stu-id="cbb96-148">The following table describes the transaction types in the report setup for sales tax codes.</span></span> <span data-ttu-id="cbb96-149">Le calcul comprend les transactions pour tous les types de sources à l'exception de la taxe.</span><span class="sxs-lookup"><span data-stu-id="cbb96-149">The calculation includes transactions for all types of sources except sales tax.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cbb96-150"><strong>Type de transaction</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-150"><strong>Transaction type</strong></span></span></td>
<td><span data-ttu-id="cbb96-151"><strong>Description des transactions et des montants à comptabiliser sur le type de transaction</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-151"><strong>Description of transactions and amounts to be counted on the transaction type</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cbb96-152"><strong>Ventes soumises à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-152"><strong>Taxable Sales</strong></span></span></td>
<td><span data-ttu-id="cbb96-153">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-153">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-154">La date de transaction se trouve dans la période sélectionnée/</span><span class="sxs-lookup"><span data-stu-id="cbb96-154">Transaction date is in the selected period/</span></span></li>
<li><span data-ttu-id="cbb96-155">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="cbb96-155">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="cbb96-156">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-156">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cbb96-157"><strong>Vente détaxée</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-157"><strong>Tax-free sales</strong></span></span></td>
<td><span data-ttu-id="cbb96-158">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-158">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-159">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-159">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-160">La vente est de type exportation (la <strong>Direction de la taxe</strong> est <strong>Vente détaxée</strong>).</span><span class="sxs-lookup"><span data-stu-id="cbb96-160">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="cbb96-161">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-161">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cbb96-162"><strong>Taxe collectée</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-162"><strong>Sales tax payable</strong></span></span></td>
<td><span data-ttu-id="cbb96-163">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-163">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-164">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-164">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-165">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="cbb96-165">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="cbb96-166">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-166">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cbb96-167"><strong>Avoir soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-167"><strong>Taxable sales credit note</strong></span></span></td>
<td><span data-ttu-id="cbb96-168">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-168">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-169">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-169">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-170">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="cbb96-170">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="cbb96-171">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-171">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cbb96-172"><strong>Avoir sur vente exonéré de taxe</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-172"><strong>Fax exempt sales credit note</strong></span></span></td>
<td><span data-ttu-id="cbb96-173">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-173">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-174">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-174">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-175">La vente est de type exportation (la <strong>Direction de la taxe</strong> est <strong>Vente détaxée</strong>).</span><span class="sxs-lookup"><span data-stu-id="cbb96-175">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="cbb96-176">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-176">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cbb96-177"><strong>Taxe sur avoir sur vente</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-177"><strong>Sales tax on sales credit note</strong></span></span></td>
<td><span data-ttu-id="cbb96-178">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-178">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-179">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-179">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-180">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="cbb96-180">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="cbb96-181">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-181">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cbb96-182"><strong>Achats soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-182"><strong>Taxable purchases</strong></span></span></td>
<td><span data-ttu-id="cbb96-183">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-183">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-184">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-184">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-185">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="cbb96-185">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="cbb96-186">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-186">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cbb96-187"><strong>Achat détaxé</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-187"><strong>Tax-free purchase</strong></span></span></td>
<td><span data-ttu-id="cbb96-188">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-188">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-189">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-189">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-190">L'achat est de type importation (la <strong>Direction de la taxe</strong> est <strong>Achat détaxé</strong>).</span><span class="sxs-lookup"><span data-stu-id="cbb96-190">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="cbb96-191">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-191">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cbb96-192"><strong>Taxe déductible</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-192"><strong>Sales tax receivable</strong></span></span></td>
<td><span data-ttu-id="cbb96-193">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-193">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-194">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-194">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-195">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="cbb96-195">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="cbb96-196">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-196">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cbb96-197"><strong>Avoir sur achat soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-197"><strong>Taxable purchase credit note</strong></span></span></td>
<td><span data-ttu-id="cbb96-198">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-198">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-199">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-199">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-200">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="cbb96-200">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="cbb96-201">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-201">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cbb96-202"><strong>Avoir sur achat exonéré de taxe</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-202"><strong>Tax exempt purchase credit note</strong></span></span></td>
<td><span data-ttu-id="cbb96-203">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-203">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-204">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-204">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-205">L'achat est de type importation (la <strong>Direction de la taxe</strong> est <strong>Achat détaxé</strong>).</span><span class="sxs-lookup"><span data-stu-id="cbb96-205">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="cbb96-206">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-206">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cbb96-207"><strong>Taxe sur avoir sur achat</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-207"><strong>Sales tax on purchase credit note</strong></span></span></td>
<td><span data-ttu-id="cbb96-208">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-208">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-209">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-209">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-210">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="cbb96-210">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="cbb96-211">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-211">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cbb96-212"><strong>Importation soumise à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-212"><strong>Taxable import</strong></span></span></td>
<td><span data-ttu-id="cbb96-213">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-213">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-214">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-214">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-215">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-215"><strong>Tax direction</strong> is <strong>Use tax</strong></span></span></li>
<li><span data-ttu-id="cbb96-216">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-216">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cbb96-217"><strong>Contrepartie des importations soumises à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-217"><strong>Offset taxable import</strong></span></span></td>
<td><span data-ttu-id="cbb96-218">Somme contrepassée des <strong>Montants de base de la taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-218">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-219">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-219">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-220">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="cbb96-220"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="cbb96-221">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-221">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cbb96-222"><strong>Avoir sur importation soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-222"><strong>Taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="cbb96-223">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-223">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-224">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-224">Transaction date is in the selected period.</span></span></li>
<span data-ttu-id="cbb96-225">e</span><span class="sxs-lookup"><span data-stu-id="cbb96-225">e</span></span><li><span data-ttu-id="cbb96-226">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="cbb96-226"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="cbb96-227">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-227">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cbb96-228"><strong>Contrepartie des avoirs sur importations soumises à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-228"><strong>Offset taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="cbb96-229">Somme contrepassée des <strong>Montants de base de la taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-229">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-230">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-230">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-231">La Direction de la taxe est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="cbb96-231">Tax direction is <strong>Use tax</strong>.</span></span></li>
<span data-ttu-id="cbb96-232">d</span><span class="sxs-lookup"><span data-stu-id="cbb96-232">d</span></span><li><span data-ttu-id="cbb96-233">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-233">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cbb96-234"><strong>Taxe d'utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-234"><strong>Use tax</strong></span></span></td>
<td><span data-ttu-id="cbb96-235">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-235">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-236">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-236">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-237">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="cbb96-237"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="cbb96-238">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-238">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cbb96-239"><strong>Contrepartie taxe d'utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="cbb96-239"><strong>Offset use tax</strong></span></span></td>
<td><span data-ttu-id="cbb96-240">Somme contrepassée des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb96-240">Reversed sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="cbb96-241">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbb96-241">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="cbb96-242">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="cbb96-242"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="cbb96-243">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="cbb96-243">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="cbb96-244">Pour le tableau ci-dessus, on suppose que les critères suivants sont remplis :</span><span class="sxs-lookup"><span data-stu-id="cbb96-244">For the table above, it is assumed that the following criteria are met:</span></span> 
> -   <span data-ttu-id="cbb96-245">Le montant de base de la taxe est un montant de transaction issu du champ **Origine dans la devise comptable**.</span><span class="sxs-lookup"><span data-stu-id="cbb96-245">The tax base amount is a transaction amount from the **Origin in Accounting currency** field.</span></span>
> -   <span data-ttu-id="cbb96-246">Le montant de la taxe est un montant de transition issu du champ **Montant réel de la taxe dans la devise comptable**.</span><span class="sxs-lookup"><span data-stu-id="cbb96-246">The tax amount is a transition amount from the **Actual sales tax amount in Accounting currency** field.</span></span>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="cbb96-247">Configurer le modèle et le format ER pour l'état</span><span class="sxs-lookup"><span data-stu-id="cbb96-247">Configure the ER model and format for the report</span></span>

<span data-ttu-id="cbb96-248">Vous pouvez utiliser les états électroniques pour configurer les déclarations et l'état, et pour exporter les données dans différents formats électroniques sans modifier le code X++.</span><span class="sxs-lookup"><span data-stu-id="cbb96-248">You can use Electronic Reporting (ER) to configure statements and report, and to export data different electronic formats without changing X++ code.</span></span> <span data-ttu-id="cbb96-249">Pour des informations supplémentaires :</span><span class="sxs-lookup"><span data-stu-id="cbb96-249">For additional information:</span></span>

-   [<span data-ttu-id="cbb96-250">Vue d'ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="cbb96-250">Electronic reporting overview</span></span>](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="cbb96-251">Télécharger les configurations d'états électroniques à partir de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="cbb96-251">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="cbb96-252">Exigences de localisation – Créer une configuration GER</span><span class="sxs-lookup"><span data-stu-id="cbb96-252">Localization requirements – Create a GER configuration</span></span>](../../dev-itpro/analytics/electronic-reporting-configuration.md)

## <a name="countryspecific-resources-for-vat-statements"></a><span data-ttu-id="cbb96-253">Ressources spécifiques au pays pour les déclarations de TVA</span><span class="sxs-lookup"><span data-stu-id="cbb96-253">Countryspecific resources for VAT statements</span></span>
<span data-ttu-id="cbb96-254">La déclaration de TVA pour chaque pays doit répondre aux exigences de la législation du pays.</span><span class="sxs-lookup"><span data-stu-id="cbb96-254">The VAT statement for each country must meet the requirements of the country’s legislation.</span></span> <span data-ttu-id="cbb96-255">Il existe des modèles et des formats généraux prédéfinis de déclarations de TVA pour les pays répertoriés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="cbb96-255">There are predefined general models and formats of VAT statements for the countries listed in the following table.</span></span>


| <span data-ttu-id="cbb96-256">Pays</span><span class="sxs-lookup"><span data-stu-id="cbb96-256">Country</span></span>        | <span data-ttu-id="cbb96-257">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="cbb96-257">Additional information</span></span>                                                          |
|----------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="cbb96-258">Autriche</span><span class="sxs-lookup"><span data-stu-id="cbb96-258">Austria</span></span>        |  [<span data-ttu-id="cbb96-259">Détails de la déclaration de TVA pour l'Autriche</span><span class="sxs-lookup"><span data-stu-id="cbb96-259">VAT statement details for Austria</span></span>](emea-aut-vat-statement-details.md)         |
| <span data-ttu-id="cbb96-260">Belgique</span><span class="sxs-lookup"><span data-stu-id="cbb96-260">Belgium</span></span>        |                                                                                 |
| <span data-ttu-id="cbb96-261">République tchèque</span><span class="sxs-lookup"><span data-stu-id="cbb96-261">Czech Republic</span></span> |  [<span data-ttu-id="cbb96-262">Détails de la déclaration de TVA pour la République tchèque</span><span class="sxs-lookup"><span data-stu-id="cbb96-262">VAT statement details for Czech Republic</span></span>](emea-cze-vat-statement-details.md)   |
| <span data-ttu-id="cbb96-263">Estonie</span><span class="sxs-lookup"><span data-stu-id="cbb96-263">Estonia</span></span>        |  [<span data-ttu-id="cbb96-264">Détails de la déclaration de TVA pour l'Estonie</span><span class="sxs-lookup"><span data-stu-id="cbb96-264">VAT statement details for Estonia</span></span>](emea-est-vat-statement-details.md) |
| <span data-ttu-id="cbb96-265">Finlande</span><span class="sxs-lookup"><span data-stu-id="cbb96-265">Finland</span></span>        |                                                                                 |
| <span data-ttu-id="cbb96-266">Allemagne</span><span class="sxs-lookup"><span data-stu-id="cbb96-266">Germany</span></span>        |                                                                                 |
| <span data-ttu-id="cbb96-267">Italie</span><span class="sxs-lookup"><span data-stu-id="cbb96-267">Italy</span></span>          | [<span data-ttu-id="cbb96-268">Détails de la déclaration de TVA pour l'Italie</span><span class="sxs-lookup"><span data-stu-id="cbb96-268">VAT statement details for Italy</span></span>](emea-ita-vat-statements-details.md)            |
| <span data-ttu-id="cbb96-269">Lettonie</span><span class="sxs-lookup"><span data-stu-id="cbb96-269">Latvia</span></span>         | [<span data-ttu-id="cbb96-270">Détails de la déclaration de TVA pour la Lettonie</span><span class="sxs-lookup"><span data-stu-id="cbb96-270">VAT statement details for Latvia</span></span>](emea-lva-vat-statement-details.md)           |
| <span data-ttu-id="cbb96-271">Lituanie</span><span class="sxs-lookup"><span data-stu-id="cbb96-271">Lithuania</span></span>      | [<span data-ttu-id="cbb96-272">Détails de la déclaration de TVA pour la Lituanie</span><span class="sxs-lookup"><span data-stu-id="cbb96-272">VAT statement details for Lithuania</span></span>](emea-ltu-vat-statement-details.md)         |
| <span data-ttu-id="cbb96-273">Pays-Bas</span><span class="sxs-lookup"><span data-stu-id="cbb96-273">Netherlands</span></span>    |                                                                                 |
| <span data-ttu-id="cbb96-274">Suède</span><span class="sxs-lookup"><span data-stu-id="cbb96-274">Sweden</span></span>         |                                                                                 |






