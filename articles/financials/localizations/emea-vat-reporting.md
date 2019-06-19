---
title: Déclaration de TVA pour l'Europe
description: Cette rubrique fournit des informations générales sur le paramétrage et la génération de la déclaration de TVA pour certains pays européens.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 266844
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5c5cd61c45eb7cbc6f040f054a99d9a54e1ee854
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569570"
---
# <a name="vat-reporting-for-europe"></a><span data-ttu-id="6443b-103">Déclaration de TVA pour l'Europe</span><span class="sxs-lookup"><span data-stu-id="6443b-103">VAT reporting for Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6443b-104">Cette rubrique fournit des informations générales sur le paramétrage et la génération de la déclaration de TVA pour certains pays européens.</span><span class="sxs-lookup"><span data-stu-id="6443b-104">This topic provides general information about setting up and generating the value-added tax (VAT) statement for some European countries.</span></span>

<span data-ttu-id="6443b-105">Cette rubrique fournit une approche générique du paramétrage et de la génération de la déclaration de TVA.</span><span class="sxs-lookup"><span data-stu-id="6443b-105">This topic provides a generic approach to setting up and generating the VAT statement.</span></span> <span data-ttu-id="6443b-106">Cette approche est commune pour les utilisateurs dans les entités juridiques des pays/régions suivants :</span><span class="sxs-lookup"><span data-stu-id="6443b-106">This approach is common for users in legal entities in the following countries/regions:</span></span>

-   <span data-ttu-id="6443b-107">Autriche</span><span class="sxs-lookup"><span data-stu-id="6443b-107">Austria</span></span>
-   <span data-ttu-id="6443b-108">Belgique</span><span class="sxs-lookup"><span data-stu-id="6443b-108">Belgium</span></span>
-   <span data-ttu-id="6443b-109">République tchèque</span><span class="sxs-lookup"><span data-stu-id="6443b-109">Czech Republic</span></span>
-   <span data-ttu-id="6443b-110">Estonie</span><span class="sxs-lookup"><span data-stu-id="6443b-110">Estonia</span></span>
-   <span data-ttu-id="6443b-111">Finlande</span><span class="sxs-lookup"><span data-stu-id="6443b-111">Finland</span></span>
-   <span data-ttu-id="6443b-112">Allemagne</span><span class="sxs-lookup"><span data-stu-id="6443b-112">Germany</span></span>
-   <span data-ttu-id="6443b-113">Lettonie</span><span class="sxs-lookup"><span data-stu-id="6443b-113">Latvia</span></span>
-   <span data-ttu-id="6443b-114">Lituanie</span><span class="sxs-lookup"><span data-stu-id="6443b-114">Lithuania</span></span>
-   <span data-ttu-id="6443b-115">Pays-Bas</span><span class="sxs-lookup"><span data-stu-id="6443b-115">Netherlands</span></span>
-   <span data-ttu-id="6443b-116">Suède</span><span class="sxs-lookup"><span data-stu-id="6443b-116">Sweden</span></span>

## <a name="vat-statement-overview"></a><span data-ttu-id="6443b-117">Vue d'ensemble de la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="6443b-117">VAT statement overview</span></span>
<span data-ttu-id="6443b-118">La déclaration de TVA est basée sur les montants des transactions de taxe.</span><span class="sxs-lookup"><span data-stu-id="6443b-118">The VAT statement is based on tax transactions’ amounts.</span></span> <span data-ttu-id="6443b-119">Le processus de génération d'une déclaration de TVA fait partie du processus de paiement de la taxe, qui est implémenté via la fonction Régler et valider la taxe.</span><span class="sxs-lookup"><span data-stu-id="6443b-119">The process of generating a VAT statement is part of the Sales tax payment process, which is implemented through the Settle and post sales tax function.</span></span> <span data-ttu-id="6443b-120">Cette fonction calcule la taxe due pour une période donnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-120">This function calculates the sales tax that is due for a given period.</span></span> <span data-ttu-id="6443b-121">Le calcul du règlement inclut la taxe validée pour la période de règlement sélectionnée pour les transactions de taxe.</span><span class="sxs-lookup"><span data-stu-id="6443b-121">The settlement calculation includes the posted sales tax for the selected settlement period for the tax transactions.</span></span> <span data-ttu-id="6443b-122">Le processus de calcul des données d'une déclaration de TVA est basé sur la relation entre les codes taxe et les codes déclaration de taxe, où les codes déclaration de taxe correspondent aux zones de déclaration de TVA (ou balises en XML).</span><span class="sxs-lookup"><span data-stu-id="6443b-122">The process for calculating data for a VAT statement is based on the relationship between sales tax codes and sales tax reporting codes, where sales tax reporting codes match the VAT statements boxes (or tags in XML).</span></span> <span data-ttu-id="6443b-123">Pour chaque code taxe, des codes déclaration de taxe doivent être définis pour chaque type de transaction, par exemple les ventes imposables, les achats imposables, les importations imposables.</span><span class="sxs-lookup"><span data-stu-id="6443b-123">For each sales tax code, sales tax reporting codes should be set up for each type of transaction, such as taxable sales, taxable purchases, taxable import.</span></span> <span data-ttu-id="6443b-124">Ces types de transactions sont décrits dans la section Codes taxe pour la déclaration de TVA plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="6443b-124">These type of transactions are described in the Sales tax codes for VAT reporting section later in this topic.</span></span>

<span data-ttu-id="6443b-125">Pour chaque code déclaration de taxe, une présentation d'état spécifique doit être déterminée.</span><span class="sxs-lookup"><span data-stu-id="6443b-125">For each sales tax reporting code, a specific report layout should be determined.</span></span> <span data-ttu-id="6443b-126">Les codes taxe sont également liés à une administration fiscale spécifique via des périodes de règlement de la taxe.</span><span class="sxs-lookup"><span data-stu-id="6443b-126">At the same time, sales tax codes are linked to a specific sales tax authority through sales tax settlement periods.</span></span> <span data-ttu-id="6443b-127">Pour chaque administration fiscale, une présentation d'état doit être déterminée.</span><span class="sxs-lookup"><span data-stu-id="6443b-127">For every sales tax authority, a report layout should be determined.</span></span> <span data-ttu-id="6443b-128">Ainsi, seuls les codes déclaration de taxe avec la même présentation d'état paramétrée pour une administration fiscale dans les périodes de règlement de la taxe pour le code taxe peuvent être sélectionnés dans le paramétrage d'état du code taxe.</span><span class="sxs-lookup"><span data-stu-id="6443b-128">Thus, only sales tax reporting codes with the same report layout that is set up for a sales tax authority in sales tax settlement periods for the sales tax code can be selected in the report setup of the sales tax code.</span></span> <span data-ttu-id="6443b-129">Une transaction de taxe générée lors de la validation d'une commande ou d'un journal, contient un code taxe, une source de taxe, une direction de taxe et des montants de transaction (montant de base de la taxe et montant de la taxe dans la devise comptable, la devise de taxe et la devise de la transaction).</span><span class="sxs-lookup"><span data-stu-id="6443b-129">A sales tax transaction generated upon posting an order or a journal, contains a sales tax code, sales tax source, sales tax direction, and transaction amounts (tax base amount and tax amount in accounting currency, sales-tax currency, and transaction currency).</span></span> <span data-ttu-id="6443b-130">Selon la combinaison d'attributs de transaction de taxe, les montants des transactions composent les montants totaux pour les codes déclaration de taxe spécifiés pour les codes taxe.</span><span class="sxs-lookup"><span data-stu-id="6443b-130">Based on the combination of tax transaction attributes, transaction amounts compose total amounts for sales tax reporting codes specified for sales tax codes.</span></span> <span data-ttu-id="6443b-131">La relation des données est illustrée dans le graphique ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="6443b-131">The following illustration shows the data relationship.</span></span>

![diagramme](./media/diagram4.jpg)

## <a name="vat-statement-setup"></a><span data-ttu-id="6443b-133">Paramétrage de la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="6443b-133">VAT statement setup</span></span>
<span data-ttu-id="6443b-134">Pour générer une déclaration de TVA, vous devez paramétrer les éléments suivants.</span><span class="sxs-lookup"><span data-stu-id="6443b-134">To generate a VAT statement you must set up the following.</span></span>

### <a name="sales-tax-authorities-for-vat-reporting"></a><span data-ttu-id="6443b-135">Administrations fiscales pour la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="6443b-135">Sales tax authorities for VAT reporting</span></span>

<span data-ttu-id="6443b-136">Avant de paramétrer les codes déclaration de taxe, vous devez sélectionner la présentation d'état correcte pour l'administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="6443b-136">Before you can set up sales tax reporting codes, you must select the correct report layout for the sales tax authority.</span></span> <span data-ttu-id="6443b-137">Dans la page **Administrations fiscales**, dans la section **Général**, sélectionnez une **Présentation d'état**.</span><span class="sxs-lookup"><span data-stu-id="6443b-137">On the **Sales tax authorities** page, in the **General** section, select a **Report layout**.</span></span> <span data-ttu-id="6443b-138">Cette présentation sera utilisée lors du paramétrage des codes déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="6443b-138">This layout will be used when you set up sales tax reporting codes.</span></span>

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](../general-ledger/tasks/set-up-sales-tax-authorities.md). -->

### <a name="sales-tax-reporting-codes"></a><span data-ttu-id="6443b-139">Codes déclaration de taxe</span><span class="sxs-lookup"><span data-stu-id="6443b-139">Sales tax reporting codes</span></span>

<span data-ttu-id="6443b-140">Les codes déclaration de taxe sont des codes de zone dans la déclaration de TVA ou des noms de balise au format XML.</span><span class="sxs-lookup"><span data-stu-id="6443b-140">Sales tax reporting codes are box codes in the VAT statement or tag names in XML format.</span></span> <span data-ttu-id="6443b-141">Ces codes sont utilisés pour regrouper et préparer les montants pour l'état.</span><span class="sxs-lookup"><span data-stu-id="6443b-141">These codes are used to aggregate and prepare amounts for the report.</span></span> <span data-ttu-id="6443b-142">Lorsque vous configurez le format de génération d'états électroniques de la déclaration de TVA, les noms des montants de résultat sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="6443b-142">When you configure the electronic reporting format of the VAT statement, the names of the result amounts will be used.</span></span> <span data-ttu-id="6443b-143">Vous pouvez créer et tenir à jour les codes déclaration de taxe dans la page **Codes déclaration de taxe**.</span><span class="sxs-lookup"><span data-stu-id="6443b-143">You can create and maintain sales tax reporting codes on the **Sales tax reporting codes** page.</span></span> <span data-ttu-id="6443b-144">Vous devez affecter une présentation d'état à chaque code.</span><span class="sxs-lookup"><span data-stu-id="6443b-144">You must assign each code a report layout.</span></span> <span data-ttu-id="6443b-145">Après avoir créé les codes déclaration de taxe, vous pouvez choisir les codes dans la section **Paramétrage d'état** de la page **Codes taxe**.</span><span class="sxs-lookup"><span data-stu-id="6443b-145">After you create the sales tax reporting codes, you can choose the codes in the **Report setup** section on the **Sales tax codes** page.</span></span> <!---For more information, see [Set up sales tax reporting codes](../general-ledger/tasks/set-up-sales-tax-reporting-codes.md).-->

### <a name="sales-tax-codes-for-vat-reporting"></a><span data-ttu-id="6443b-146">Codes taxe pour la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="6443b-146">Sales tax codes for VAT reporting</span></span>

<!---For general information about setting up sales tax codes, see [Set up sales tax codes](../general-ledger/tasks/set-up-sales-tax-codes.md).--> <span data-ttu-id="6443b-147"> Les montants de base et les montants de taxe des transactions de taxe peuvent être regroupés à l'aide de codes déclaration dans la déclaration de TVA (balises XML ou zones de déclaration).</span><span class="sxs-lookup"><span data-stu-id="6443b-147">Base amounts and tax amounts of sales tax transactions can be aggregated on reporting codes in the VAT statement (XML tags or declaration boxes).</span></span> <span data-ttu-id="6443b-148">Pour ce faire, associez les codes déclaration de taxe pour différents types de transaction aux codes taxe dans la page <strong>Codes taxe</strong>.</span><span class="sxs-lookup"><span data-stu-id="6443b-148">You can set this up by associating sales tax reporting codes for different transaction types for sales tax codes on the <strong>Sales tax codes</strong> page.</span></span> <span data-ttu-id="6443b-149">Le tableau suivant décrit les types de transaction dans le paramétrage d'état pour les codes taxe.</span><span class="sxs-lookup"><span data-stu-id="6443b-149">The following table describes the transaction types in the report setup for sales tax codes.</span></span> <span data-ttu-id="6443b-150">Le calcul comprend les transactions pour tous les types de sources à l'exception de la taxe.</span><span class="sxs-lookup"><span data-stu-id="6443b-150">The calculation includes transactions for all types of sources except sales tax.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6443b-151"><strong>Type de transaction</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-151"><strong>Transaction type</strong></span></span></td>
<td><span data-ttu-id="6443b-152"><strong>Description des transactions et des montants à comptabiliser sur le type de transaction</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-152"><strong>Description of transactions and amounts to be counted on the transaction type</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6443b-153"><strong>Ventes soumises à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-153"><strong>Taxable Sales</strong></span></span></td>
<td><span data-ttu-id="6443b-154">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-154">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-155">La date de transaction se trouve dans la période sélectionnée/</span><span class="sxs-lookup"><span data-stu-id="6443b-155">Transaction date is in the selected period/</span></span></li>
<li><span data-ttu-id="6443b-156">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="6443b-156">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="6443b-157">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-157">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6443b-158"><strong>Vente détaxée</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-158"><strong>Tax-free sales</strong></span></span></td>
<td><span data-ttu-id="6443b-159">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-159">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-160">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-160">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-161">La vente est de type exportation (la <strong>Direction de la taxe</strong> est <strong>Vente détaxée</strong>).</span><span class="sxs-lookup"><span data-stu-id="6443b-161">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="6443b-162">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-162">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6443b-163"><strong>Taxe collectée</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-163"><strong>Sales tax payable</strong></span></span></td>
<td><span data-ttu-id="6443b-164">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-164">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-165">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-165">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-166">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="6443b-166">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="6443b-167">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-167">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6443b-168"><strong>Avoir soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-168"><strong>Taxable sales credit note</strong></span></span></td>
<td><span data-ttu-id="6443b-169">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-169">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-170">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-170">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-171">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="6443b-171">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="6443b-172">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-172">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6443b-173"><strong>Avoir sur vente exonéré de taxe</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-173"><strong>Fax exempt sales credit note</strong></span></span></td>
<td><span data-ttu-id="6443b-174">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-174">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-175">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-175">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-176">La vente est de type exportation (la <strong>Direction de la taxe</strong> est <strong>Vente détaxée</strong>).</span><span class="sxs-lookup"><span data-stu-id="6443b-176">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="6443b-177">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-177">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6443b-178"><strong>Taxe sur avoir sur vente</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-178"><strong>Sales tax on sales credit note</strong></span></span></td>
<td><span data-ttu-id="6443b-179">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-179">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-180">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-180">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-181">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="6443b-181">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="6443b-182">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-182">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6443b-183"><strong>Achats soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-183"><strong>Taxable purchases</strong></span></span></td>
<td><span data-ttu-id="6443b-184">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-184">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-185">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-185">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-186">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="6443b-186">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="6443b-187">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-187">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6443b-188"><strong>Achat détaxé</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-188"><strong>Tax-free purchase</strong></span></span></td>
<td><span data-ttu-id="6443b-189">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-189">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-190">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-190">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-191">L'achat est de type importation (la <strong>Direction de la taxe</strong> est <strong>Achat détaxé</strong>).</span><span class="sxs-lookup"><span data-stu-id="6443b-191">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="6443b-192">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-192">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6443b-193"><strong>Taxe déductible</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-193"><strong>Sales tax receivable</strong></span></span></td>
<td><span data-ttu-id="6443b-194">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-194">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-195">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-195">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-196">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="6443b-196">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="6443b-197">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-197">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6443b-198"><strong>Avoir sur achat soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-198"><strong>Taxable purchase credit note</strong></span></span></td>
<td><span data-ttu-id="6443b-199">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-199">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-200">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-200">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-201">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="6443b-201">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="6443b-202">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-202">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6443b-203"><strong>Avoir sur achat exonéré de taxe</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-203"><strong>Tax exempt purchase credit note</strong></span></span></td>
<td><span data-ttu-id="6443b-204">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-204">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-205">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-205">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-206">L'achat est de type importation (la <strong>Direction de la taxe</strong> est <strong>Achat détaxé</strong>).</span><span class="sxs-lookup"><span data-stu-id="6443b-206">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="6443b-207">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-207">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6443b-208"><strong>Taxe sur avoir sur achat</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-208"><strong>Sales tax on purchase credit note</strong></span></span></td>
<td><span data-ttu-id="6443b-209">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-209">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-210">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-210">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-211">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="6443b-211">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="6443b-212">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-212">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6443b-213"><strong>Importation soumise à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-213"><strong>Taxable import</strong></span></span></td>
<td><span data-ttu-id="6443b-214">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-214">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-215">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-215">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-216">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-216"><strong>Tax direction</strong> is <strong>Use tax</strong></span></span></li>
<li><span data-ttu-id="6443b-217">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-217">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6443b-218"><strong>Contrepartie des importations soumises à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-218"><strong>Offset taxable import</strong></span></span></td>
<td><span data-ttu-id="6443b-219">Somme contrepassée des <strong>Montants de base de la taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-219">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-220">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-220">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-221">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="6443b-221"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="6443b-222">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-222">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6443b-223"><strong>Avoir sur importation soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-223"><strong>Taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="6443b-224">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-224">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-225">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-225">Transaction date is in the selected period.</span></span></li>
<span data-ttu-id="6443b-226">e</span><span class="sxs-lookup"><span data-stu-id="6443b-226">e</span></span><li><span data-ttu-id="6443b-227">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="6443b-227"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="6443b-228">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-228">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6443b-229"><strong>Contrepartie des avoirs sur importations soumises à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-229"><strong>Offset taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="6443b-230">Somme contrepassée des <strong>Montants de base de la taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-230">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-231">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-231">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-232">La Direction de la taxe est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="6443b-232">Tax direction is <strong>Use tax</strong>.</span></span></li>
<span data-ttu-id="6443b-233">d</span><span class="sxs-lookup"><span data-stu-id="6443b-233">d</span></span><li><span data-ttu-id="6443b-234">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-234">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6443b-235"><strong>Taxe d'utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-235"><strong>Use tax</strong></span></span></td>
<td><span data-ttu-id="6443b-236">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-236">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-237">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-237">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-238">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="6443b-238"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="6443b-239">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-239">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6443b-240"><strong>Contrepartie taxe d'utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="6443b-240"><strong>Offset use tax</strong></span></span></td>
<td><span data-ttu-id="6443b-241">Somme contrepassée des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6443b-241">Reversed sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6443b-242">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6443b-242">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="6443b-243">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="6443b-243"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="6443b-244">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="6443b-244">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="6443b-245">Pour le tableau ci-dessus, on suppose que les critères suivants sont remplis :</span><span class="sxs-lookup"><span data-stu-id="6443b-245">For the table above, it is assumed that the following criteria are met:</span></span> 
> -   <span data-ttu-id="6443b-246">Le montant de base de la taxe est un montant de transaction issu du champ **Origine dans la devise comptable**.</span><span class="sxs-lookup"><span data-stu-id="6443b-246">The tax base amount is a transaction amount from the **Origin in Accounting currency** field.</span></span>
> -   <span data-ttu-id="6443b-247">Le montant de la taxe est un montant de transition issu du champ **Montant réel de la taxe dans la devise comptable**.</span><span class="sxs-lookup"><span data-stu-id="6443b-247">The tax amount is a transition amount from the **Actual sales tax amount in Accounting currency** field.</span></span>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="6443b-248">Configurer le modèle et le format ER pour l'état</span><span class="sxs-lookup"><span data-stu-id="6443b-248">Configure the ER model and format for the report</span></span>

<span data-ttu-id="6443b-249">Vous pouvez utiliser les états électroniques pour configurer les déclarations et l'état, et pour exporter les données dans différents formats électroniques sans modifier le code X++.</span><span class="sxs-lookup"><span data-stu-id="6443b-249">You can use Electronic Reporting (ER) to configure statements and report, and to export data different electronic formats without changing X++ code.</span></span> <span data-ttu-id="6443b-250">Pour des informations supplémentaires :</span><span class="sxs-lookup"><span data-stu-id="6443b-250">For additional information:</span></span>

-   [<span data-ttu-id="6443b-251">Vue d'ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="6443b-251">Electronic reporting overview</span></span>](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="6443b-252">Télécharger les configurations d'états électroniques à partir de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="6443b-252">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="6443b-253">Exigences de localisation – Créer une configuration GER</span><span class="sxs-lookup"><span data-stu-id="6443b-253">Localization requirements – Create a GER configuration</span></span>](../../dev-itpro/analytics/electronic-reporting-configuration.md)

## <a name="countryspecific-resources-for-vat-statements"></a><span data-ttu-id="6443b-254">Ressources spécifiques au pays pour les déclarations de TVA</span><span class="sxs-lookup"><span data-stu-id="6443b-254">Countryspecific resources for VAT statements</span></span>
<span data-ttu-id="6443b-255">La déclaration de TVA pour chaque pays doit répondre aux exigences de la législation du pays.</span><span class="sxs-lookup"><span data-stu-id="6443b-255">The VAT statement for each country must meet the requirements of the country’s legislation.</span></span> <span data-ttu-id="6443b-256">Il existe des modèles et des formats généraux prédéfinis de déclarations de TVA pour les pays répertoriés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="6443b-256">There are predefined general models and formats of VAT statements for the countries listed in the following table.</span></span>


| <span data-ttu-id="6443b-257">Pays</span><span class="sxs-lookup"><span data-stu-id="6443b-257">Country</span></span>        | <span data-ttu-id="6443b-258">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6443b-258">Additional information</span></span>                                                          |
|----------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="6443b-259">Autriche</span><span class="sxs-lookup"><span data-stu-id="6443b-259">Austria</span></span>        |  [<span data-ttu-id="6443b-260">Détails de la déclaration de TVA pour l'Autriche</span><span class="sxs-lookup"><span data-stu-id="6443b-260">VAT statement details for Austria</span></span>](emea-aut-vat-statement-details.md)         |
| <span data-ttu-id="6443b-261">Belgique</span><span class="sxs-lookup"><span data-stu-id="6443b-261">Belgium</span></span>        |                                                                                 |
| <span data-ttu-id="6443b-262">République tchèque</span><span class="sxs-lookup"><span data-stu-id="6443b-262">Czech Republic</span></span> |  [<span data-ttu-id="6443b-263">Détails de la déclaration de TVA pour la République tchèque</span><span class="sxs-lookup"><span data-stu-id="6443b-263">VAT statement details for Czech Republic</span></span>](emea-cze-vat-statement-details.md)   |
| <span data-ttu-id="6443b-264">Estonie</span><span class="sxs-lookup"><span data-stu-id="6443b-264">Estonia</span></span>        |  [<span data-ttu-id="6443b-265">Détails de la déclaration de TVA pour l'Estonie</span><span class="sxs-lookup"><span data-stu-id="6443b-265">VAT statement details for Estonia</span></span>](emea-est-vat-statement-details.md) |
| <span data-ttu-id="6443b-266">Finlande</span><span class="sxs-lookup"><span data-stu-id="6443b-266">Finland</span></span>        |                                                                                 |
| <span data-ttu-id="6443b-267">Allemagne</span><span class="sxs-lookup"><span data-stu-id="6443b-267">Germany</span></span>        |                                                                                 |
| <span data-ttu-id="6443b-268">Italie</span><span class="sxs-lookup"><span data-stu-id="6443b-268">Italy</span></span>          | [<span data-ttu-id="6443b-269">Détails de la déclaration de TVA pour l'Italie</span><span class="sxs-lookup"><span data-stu-id="6443b-269">VAT statement details for Italy</span></span>](emea-ita-vat-statements-details.md)            |
| <span data-ttu-id="6443b-270">Lettonie</span><span class="sxs-lookup"><span data-stu-id="6443b-270">Latvia</span></span>         | [<span data-ttu-id="6443b-271">Détails de la déclaration de TVA pour la Lettonie</span><span class="sxs-lookup"><span data-stu-id="6443b-271">VAT statement details for Latvia</span></span>](emea-lva-vat-statement-details.md)           |
| <span data-ttu-id="6443b-272">Lituanie</span><span class="sxs-lookup"><span data-stu-id="6443b-272">Lithuania</span></span>      | [<span data-ttu-id="6443b-273">Détails de la déclaration de TVA pour la Lituanie</span><span class="sxs-lookup"><span data-stu-id="6443b-273">VAT statement details for Lithuania</span></span>](emea-ltu-vat-statement-details.md)         |
| <span data-ttu-id="6443b-274">Pays-Bas</span><span class="sxs-lookup"><span data-stu-id="6443b-274">Netherlands</span></span>    |                                                                                 |
| <span data-ttu-id="6443b-275">Suède</span><span class="sxs-lookup"><span data-stu-id="6443b-275">Sweden</span></span>         |                                                                                 |





