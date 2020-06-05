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
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 266844
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2a9b5bafb70883d9daf35a7d5a9107d7aee23469
ms.sourcegitcommit: 98ef9178b28cd548f08f8c32255636e6e09b25f2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/22/2020
ms.locfileid: "3395984"
---
# <a name="vat-reporting-for-europe"></a><span data-ttu-id="28b93-103">Déclaration de TVA pour l'Europe</span><span class="sxs-lookup"><span data-stu-id="28b93-103">VAT reporting for Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28b93-104">Cette rubrique fournit des informations générales sur le paramétrage et la génération de la déclaration de TVA pour certains pays européens.</span><span class="sxs-lookup"><span data-stu-id="28b93-104">This topic provides general information about setting up and generating the value-added tax (VAT) statement for some European countries.</span></span>

<span data-ttu-id="28b93-105">Cette rubrique fournit une approche générique du paramétrage et de la génération de la déclaration de TVA.</span><span class="sxs-lookup"><span data-stu-id="28b93-105">This topic provides a generic approach to setting up and generating the VAT statement.</span></span> <span data-ttu-id="28b93-106">Cette approche est commune pour les utilisateurs dans les entités juridiques des pays/régions suivants :</span><span class="sxs-lookup"><span data-stu-id="28b93-106">This approach is common for users in legal entities in the following countries/regions:</span></span>

-   <span data-ttu-id="28b93-107">Autriche</span><span class="sxs-lookup"><span data-stu-id="28b93-107">Austria</span></span>
-   <span data-ttu-id="28b93-108">Belgique</span><span class="sxs-lookup"><span data-stu-id="28b93-108">Belgium</span></span>
-   <span data-ttu-id="28b93-109">République tchèque</span><span class="sxs-lookup"><span data-stu-id="28b93-109">Czech Republic</span></span>
-   <span data-ttu-id="28b93-110">Estonie</span><span class="sxs-lookup"><span data-stu-id="28b93-110">Estonia</span></span>
-   <span data-ttu-id="28b93-111">Finlande</span><span class="sxs-lookup"><span data-stu-id="28b93-111">Finland</span></span>
-   <span data-ttu-id="28b93-112">Allemagne</span><span class="sxs-lookup"><span data-stu-id="28b93-112">Germany</span></span>
-   <span data-ttu-id="28b93-113">Lettonie</span><span class="sxs-lookup"><span data-stu-id="28b93-113">Latvia</span></span>
-   <span data-ttu-id="28b93-114">Lituanie</span><span class="sxs-lookup"><span data-stu-id="28b93-114">Lithuania</span></span>
-   <span data-ttu-id="28b93-115">Pays-Bas</span><span class="sxs-lookup"><span data-stu-id="28b93-115">Netherlands</span></span>
-   <span data-ttu-id="28b93-116">Suède</span><span class="sxs-lookup"><span data-stu-id="28b93-116">Sweden</span></span>

## <a name="vat-statement-overview"></a><span data-ttu-id="28b93-117">Vue d'ensemble de la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="28b93-117">VAT statement overview</span></span>
<span data-ttu-id="28b93-118">La déclaration de TVA est basée sur les montants des transactions de taxe.</span><span class="sxs-lookup"><span data-stu-id="28b93-118">The VAT statement is based on tax transactions’ amounts.</span></span> <span data-ttu-id="28b93-119">Le processus de génération d'une déclaration de TVA fait partie du processus de paiement de la taxe, qui est implémenté via la fonction Régler et valider la taxe.</span><span class="sxs-lookup"><span data-stu-id="28b93-119">The process of generating a VAT statement is part of the Sales tax payment process, which is implemented through the Settle and post sales tax function.</span></span> <span data-ttu-id="28b93-120">Cette fonction calcule la taxe due pour une période donnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-120">This function calculates the sales tax that is due for a given period.</span></span> <span data-ttu-id="28b93-121">Le calcul du règlement inclut la taxe validée pour la période de règlement sélectionnée pour les transactions de taxe.</span><span class="sxs-lookup"><span data-stu-id="28b93-121">The settlement calculation includes the posted sales tax for the selected settlement period for the tax transactions.</span></span> <span data-ttu-id="28b93-122">Le processus de calcul des données d'une déclaration de TVA est basé sur la relation entre les codes taxe et les codes déclaration de taxe, où les codes déclaration de taxe correspondent aux zones de déclaration de TVA (ou balises en XML).</span><span class="sxs-lookup"><span data-stu-id="28b93-122">The process for calculating data for a VAT statement is based on the relationship between sales tax codes and sales tax reporting codes, where sales tax reporting codes match the VAT statements boxes (or tags in XML).</span></span> <span data-ttu-id="28b93-123">Pour chaque code taxe, des codes déclaration de taxe doivent être définis pour chaque type de transaction, par exemple les ventes imposables, les achats imposables, les importations imposables.</span><span class="sxs-lookup"><span data-stu-id="28b93-123">For each sales tax code, sales tax reporting codes should be set up for each type of transaction, such as taxable sales, taxable purchases, taxable import.</span></span> <span data-ttu-id="28b93-124">Ces types de transactions sont décrits dans la section Codes taxe pour la déclaration de TVA plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="28b93-124">These type of transactions are described in the Sales tax codes for VAT reporting section later in this topic.</span></span>

<span data-ttu-id="28b93-125">Pour chaque code déclaration de taxe, une présentation d'état spécifique doit être déterminée.</span><span class="sxs-lookup"><span data-stu-id="28b93-125">For each sales tax reporting code, a specific report layout should be determined.</span></span> <span data-ttu-id="28b93-126">Les codes taxe sont également liés à une administration fiscale spécifique via des périodes de règlement de la taxe.</span><span class="sxs-lookup"><span data-stu-id="28b93-126">At the same time, sales tax codes are linked to a specific sales tax authority through sales tax settlement periods.</span></span> <span data-ttu-id="28b93-127">Pour chaque administration fiscale, une présentation d'état doit être déterminée.</span><span class="sxs-lookup"><span data-stu-id="28b93-127">For every sales tax authority, a report layout should be determined.</span></span> <span data-ttu-id="28b93-128">Ainsi, seuls les codes déclaration de taxe avec la même présentation d'état paramétrée pour une administration fiscale dans les périodes de règlement de la taxe pour le code taxe peuvent être sélectionnés dans le paramétrage d'état du code taxe.</span><span class="sxs-lookup"><span data-stu-id="28b93-128">Thus, only sales tax reporting codes with the same report layout that is set up for a sales tax authority in sales tax settlement periods for the sales tax code can be selected in the report setup of the sales tax code.</span></span> <span data-ttu-id="28b93-129">Une transaction de taxe générée lors de la validation d'une commande ou d'un journal, contient un code taxe, une source de taxe, une direction de taxe et des montants de transaction (montant de base de la taxe et montant de la taxe dans la devise comptable, la devise de taxe et la devise de la transaction).</span><span class="sxs-lookup"><span data-stu-id="28b93-129">A sales tax transaction generated upon posting an order or a journal, contains a sales tax code, sales tax source, sales tax direction, and transaction amounts (tax base amount and tax amount in accounting currency, sales-tax currency, and transaction currency).</span></span> <span data-ttu-id="28b93-130">Selon la combinaison d'attributs de transaction de taxe, les montants des transactions composent les montants totaux pour les codes déclaration de taxe spécifiés pour les codes taxe.</span><span class="sxs-lookup"><span data-stu-id="28b93-130">Based on the combination of tax transaction attributes, transaction amounts compose total amounts for sales tax reporting codes specified for sales tax codes.</span></span> <span data-ttu-id="28b93-131">La relation des données est illustrée dans le graphique ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="28b93-131">The following illustration shows the data relationship.</span></span>

![diagramme](./media/diagram4.jpg)

## <a name="vat-statement-setup"></a><span data-ttu-id="28b93-133">Paramétrage de la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="28b93-133">VAT statement setup</span></span>
<span data-ttu-id="28b93-134">Pour générer une déclaration de TVA, vous devez paramétrer les éléments suivants.</span><span class="sxs-lookup"><span data-stu-id="28b93-134">To generate a VAT statement you must set up the following.</span></span>

### <a name="sales-tax-authorities-for-vat-reporting"></a><span data-ttu-id="28b93-135">Administrations fiscales pour la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="28b93-135">Sales tax authorities for VAT reporting</span></span>

<span data-ttu-id="28b93-136">Avant de paramétrer les codes déclaration de taxe, vous devez sélectionner la présentation d'état correcte pour l'administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="28b93-136">Before you can set up sales tax reporting codes, you must select the correct report layout for the sales tax authority.</span></span> <span data-ttu-id="28b93-137">Dans la page **Administrations fiscales**, dans la section **Général**, sélectionnez une **Présentation d'état**.</span><span class="sxs-lookup"><span data-stu-id="28b93-137">On the **Sales tax authorities** page, in the **General** section, select a **Report layout**.</span></span> <span data-ttu-id="28b93-138">Cette présentation sera utilisée lors du paramétrage des codes déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="28b93-138">This layout will be used when you set up sales tax reporting codes.</span></span>

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](../general-ledger/tasks/set-up-sales-tax-authorities.md). -->

### <a name="sales-tax-reporting-codes"></a><span data-ttu-id="28b93-139">Codes déclaration de taxe</span><span class="sxs-lookup"><span data-stu-id="28b93-139">Sales tax reporting codes</span></span>

<span data-ttu-id="28b93-140">Les codes déclaration de taxe sont des codes de zone dans la déclaration de TVA ou des noms de balise au format XML.</span><span class="sxs-lookup"><span data-stu-id="28b93-140">Sales tax reporting codes are box codes in the VAT statement or tag names in XML format.</span></span> <span data-ttu-id="28b93-141">Ces codes sont utilisés pour regrouper et préparer les montants pour l'état.</span><span class="sxs-lookup"><span data-stu-id="28b93-141">These codes are used to aggregate and prepare amounts for the report.</span></span> <span data-ttu-id="28b93-142">Lorsque vous configurez le format de génération d'états électroniques de la déclaration de TVA, les noms des montants de résultat sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="28b93-142">When you configure the electronic reporting format of the VAT statement, the names of the result amounts will be used.</span></span> <span data-ttu-id="28b93-143">Vous pouvez créer et tenir à jour les codes déclaration de taxe dans la page **Codes déclaration de taxe**.</span><span class="sxs-lookup"><span data-stu-id="28b93-143">You can create and maintain sales tax reporting codes on the **Sales tax reporting codes** page.</span></span> <span data-ttu-id="28b93-144">Vous devez affecter une présentation d'état à chaque code.</span><span class="sxs-lookup"><span data-stu-id="28b93-144">You must assign each code a report layout.</span></span> <span data-ttu-id="28b93-145">Après avoir créé les codes déclaration de taxe, vous pouvez choisir les codes dans la section **Paramétrage d'état** de la page **Codes taxe**.</span><span class="sxs-lookup"><span data-stu-id="28b93-145">After you create the sales tax reporting codes, you can choose the codes in the **Report setup** section on the **Sales tax codes** page.</span></span> <!---For more information, see [Set up sales tax reporting codes](../general-ledger/tasks/set-up-sales-tax-reporting-codes.md).-->

### <a name="sales-tax-codes-for-vat-reporting"></a><span data-ttu-id="28b93-146">Codes taxe pour la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="28b93-146">Sales tax codes for VAT reporting</span></span>

<!---For general information about setting up sales tax codes, see [Set up sales tax codes](../general-ledger/tasks/set-up-sales-tax-codes.md).--> <span data-ttu-id="28b93-147">Les montants de base et les montants de taxe des transactions de taxe peuvent être regroupés à l'aide de codes déclaration dans la déclaration de TVA (balises XML ou zones de déclaration).</span><span class="sxs-lookup"><span data-stu-id="28b93-147">Base amounts and tax amounts of sales tax transactions can be aggregated on reporting codes in the VAT statement (XML tags or declaration boxes).</span></span> <span data-ttu-id="28b93-148">Pour ce faire, associez les codes déclaration de taxe pour différents types de transaction aux codes taxe dans la page <strong>Codes taxe</strong>.</span><span class="sxs-lookup"><span data-stu-id="28b93-148">You can set this up by associating sales tax reporting codes for different transaction types for sales tax codes on the <strong>Sales tax codes</strong> page.</span></span> <span data-ttu-id="28b93-149">Le tableau suivant décrit les types de transaction dans le paramétrage d'état pour les codes taxe.</span><span class="sxs-lookup"><span data-stu-id="28b93-149">The following table describes the transaction types in the report setup for sales tax codes.</span></span> <span data-ttu-id="28b93-150">Le calcul comprend les transactions pour tous les types de sources à l'exception de la taxe.</span><span class="sxs-lookup"><span data-stu-id="28b93-150">The calculation includes transactions for all types of sources except sales tax.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="28b93-151"><strong>Type de transaction</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-151"><strong>Transaction type</strong></span></span></td>
<td><span data-ttu-id="28b93-152"><strong>Description des transactions et des montants à comptabiliser sur le type de transaction</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-152"><strong>Description of transactions and amounts to be counted on the transaction type</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28b93-153"><strong>Ventes soumises à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-153"><strong>Taxable Sales</strong></span></span></td>
<td><span data-ttu-id="28b93-154">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-154">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-155">La date de transaction se trouve dans la période sélectionnée/</span><span class="sxs-lookup"><span data-stu-id="28b93-155">Transaction date is in the selected period/</span></span></li>
<li><span data-ttu-id="28b93-156">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="28b93-156">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="28b93-157">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-157">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28b93-158"><strong>Vente détaxée</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-158"><strong>Tax-free sales</strong></span></span></td>
<td><span data-ttu-id="28b93-159">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-159">Sum of <strong>Tax base amounts</strong> of tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-160">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-160">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-161">La vente est de type exportation (la <strong>Direction de la taxe</strong> est <strong>Vente détaxée</strong>).</span><span class="sxs-lookup"><span data-stu-id="28b93-161">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="28b93-162">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-162">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28b93-163"><strong>Taxe collectée</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-163"><strong>Sales tax payable</strong></span></span></td>
<td><span data-ttu-id="28b93-164">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-164">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-165">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-165">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-166">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="28b93-166">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="28b93-167">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-167">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28b93-168"><strong>Avoir soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-168"><strong>Taxable sales credit note</strong></span></span></td>
<td><span data-ttu-id="28b93-169">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-169">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-170">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-170">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-171">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="28b93-171">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="28b93-172">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-172">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28b93-173"><strong>Avoir sur vente exonéré de taxe</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-173"><strong>Fax exempt sales credit note</strong></span></span></td>
<td><span data-ttu-id="28b93-174">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-174">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-175">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-175">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-176">La vente est de type exportation (la <strong>Direction de la taxe</strong> est <strong>Vente détaxée</strong>).</span><span class="sxs-lookup"><span data-stu-id="28b93-176">The sale is export (<strong>Tax direction</strong> is <strong>Tax-free sale</strong>).</span></span></li>
<li><span data-ttu-id="28b93-177">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-177">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28b93-178"><strong>Taxe sur avoir sur vente</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-178"><strong>Sales tax on sales credit note</strong></span></span></td>
<td><span data-ttu-id="28b93-179">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-179">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-180">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-180">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-181">La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</span><span class="sxs-lookup"><span data-stu-id="28b93-181">The sale is domestic (<strong>Tax direction</strong> is <strong>Sales tax payable</strong>).</span></span></li>
<li><span data-ttu-id="28b93-182">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-182">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28b93-183"><strong>Achats soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-183"><strong>Taxable purchases</strong></span></span></td>
<td><span data-ttu-id="28b93-184">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-184">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-185">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-185">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-186">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="28b93-186">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="28b93-187">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-187">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28b93-188"><strong>Achat détaxé</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-188"><strong>Tax-free purchase</strong></span></span></td>
<td><span data-ttu-id="28b93-189">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-189">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-190">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-190">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-191">L'achat est de type importation (la <strong>Direction de la taxe</strong> est <strong>Achat détaxé</strong>).</span><span class="sxs-lookup"><span data-stu-id="28b93-191">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="28b93-192">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-192">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28b93-193"><strong>Taxe déductible</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-193"><strong>Sales tax receivable</strong></span></span></td>
<td><span data-ttu-id="28b93-194">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-194">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-195">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-195">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-196">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="28b93-196">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="28b93-197">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-197">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28b93-198"><strong>Avoir sur achat soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-198"><strong>Taxable purchase credit note</strong></span></span></td>
<td><span data-ttu-id="28b93-199">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-199">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-200">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-200">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-201">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="28b93-201">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="28b93-202">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-202">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28b93-203"><strong>Avoir sur achat exonéré de taxe</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-203"><strong>Tax exempt purchase credit note</strong></span></span></td>
<td><span data-ttu-id="28b93-204">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-204">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-205">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-205">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-206">L'achat est de type importation (la <strong>Direction de la taxe</strong> est <strong>Achat détaxé</strong>).</span><span class="sxs-lookup"><span data-stu-id="28b93-206">The purchase is import (<strong>Tax direction</strong> is <strong>Tax-free purchase</strong>).</span></span></li>
<li><span data-ttu-id="28b93-207">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-207">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28b93-208"><strong>Taxe sur avoir sur achat</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-208"><strong>Sales tax on purchase credit note</strong></span></span></td>
<td><span data-ttu-id="28b93-209">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-209">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-210">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-210">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-211">L'achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</span><span class="sxs-lookup"><span data-stu-id="28b93-211">The purchase is domestic (<strong>Tax direction</strong> is <strong>Sales tax receivable</strong>).</span></span></li>
<li><span data-ttu-id="28b93-212">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-212">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28b93-213"><strong>Importation soumise à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-213"><strong>Taxable import</strong></span></span></td>
<td><span data-ttu-id="28b93-214">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-214">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-215">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-215">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-216">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-216"><strong>Tax direction</strong> is <strong>Use tax</strong></span></span></li>
<li><span data-ttu-id="28b93-217">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-217">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28b93-218"><strong>Contrepartie des importations soumises à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-218"><strong>Offset taxable import</strong></span></span></td>
<td><span data-ttu-id="28b93-219">Somme contrepassée des <strong>Montants de base de la taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-219">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-220">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-220">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-221">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="28b93-221"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="28b93-222">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-222">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28b93-223"><strong>Avoir sur importation soumis à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-223"><strong>Taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="28b93-224">Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-224">Sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-225">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-225">Transaction date is in the selected period.</span></span></li>
<span data-ttu-id="28b93-226">e</span><span class="sxs-lookup"><span data-stu-id="28b93-226">e</span></span><li><span data-ttu-id="28b93-227">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="28b93-227"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="28b93-228">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-228">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28b93-229"><strong>Contrepartie des avoirs sur importations soumises à taxe</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-229"><strong>Offset taxable import credit note</strong></span></span></td>
<td><span data-ttu-id="28b93-230">Somme contrepassée des <strong>Montants de base de la taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-230">Reversed sum of <strong>Tax base amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-231">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-231">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-232">La Direction de la taxe est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="28b93-232">Tax direction is <strong>Use tax</strong>.</span></span></li>
<span data-ttu-id="28b93-233">d</span><span class="sxs-lookup"><span data-stu-id="28b93-233">d</span></span><li><span data-ttu-id="28b93-234">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-234">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &lt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28b93-235"><strong>Taxe d'utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-235"><strong>Use tax</strong></span></span></td>
<td><span data-ttu-id="28b93-236">Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-236">Sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-237">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-237">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-238">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="28b93-238"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="28b93-239">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-239">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28b93-240"><strong>Contrepartie taxe d'utilisation</strong></span><span class="sxs-lookup"><span data-stu-id="28b93-240"><strong>Offset use tax</strong></span></span></td>
<td><span data-ttu-id="28b93-241">Somme contrepassée des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="28b93-241">Reversed sum of <strong>Tax amounts</strong> of the tax transactions which satisfy the following conditions:</span></span>
<ul>
<li><span data-ttu-id="28b93-242">La date de transaction se trouve dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28b93-242">Transaction date is in the selected period.</span></span></li>
<li><span data-ttu-id="28b93-243">La <strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</span><span class="sxs-lookup"><span data-stu-id="28b93-243"><strong>Tax direction</strong> is <strong>Use tax</strong>.</span></span></li>
<li><span data-ttu-id="28b93-244">Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</span><span class="sxs-lookup"><span data-stu-id="28b93-244">The transaction <strong>Tax base amount</strong> or <strong>Tax amount</strong> &gt; 0.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="28b93-245">Pour le tableau ci-dessus, on suppose que les critères suivants sont remplis :</span><span class="sxs-lookup"><span data-stu-id="28b93-245">For the table above, it is assumed that the following criteria are met:</span></span> 
> -   <span data-ttu-id="28b93-246">Le montant de base de la taxe est un montant de transaction issu du champ **Origine dans la devise comptable**.</span><span class="sxs-lookup"><span data-stu-id="28b93-246">The tax base amount is a transaction amount from the **Origin in Accounting currency** field.</span></span>
> -   <span data-ttu-id="28b93-247">Le montant de la taxe est un montant de transition issu du champ **Montant réel de la taxe dans la devise comptable**.</span><span class="sxs-lookup"><span data-stu-id="28b93-247">The tax amount is a transition amount from the **Actual sales tax amount in Accounting currency** field.</span></span>

### <a name="configure-the-er-model-and-format-for-the-report"></a><span data-ttu-id="28b93-248">Configurer le modèle et le format ER pour l'état</span><span class="sxs-lookup"><span data-stu-id="28b93-248">Configure the ER model and format for the report</span></span>

<span data-ttu-id="28b93-249">Vous pouvez utiliser les états électroniques pour configurer les déclarations et l'état, et pour exporter les données dans différents formats électroniques sans modifier le code X++.</span><span class="sxs-lookup"><span data-stu-id="28b93-249">You can use Electronic Reporting (ER) to configure statements and report, and to export data different electronic formats without changing X++ code.</span></span> <span data-ttu-id="28b93-250">Pour des informations supplémentaires :</span><span class="sxs-lookup"><span data-stu-id="28b93-250">For additional information:</span></span>

-   [<span data-ttu-id="28b93-251">Vue d'ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="28b93-251">Electronic reporting overview</span></span>](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [<span data-ttu-id="28b93-252">Télécharger les configurations d'états électroniques à partir de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="28b93-252">Download Electronic reporting configurations from Lifecycle Services</span></span>](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [<span data-ttu-id="28b93-253">Exigences de localisation – Créer une configuration GER</span><span class="sxs-lookup"><span data-stu-id="28b93-253">Localization requirements – Create a GER configuration</span></span>](../../dev-itpro/analytics/electronic-reporting-configuration.md)

## <a name="countryspecific-resources-for-vat-statements"></a><span data-ttu-id="28b93-254">Ressources spécifiques au pays pour les déclarations de TVA</span><span class="sxs-lookup"><span data-stu-id="28b93-254">Countryspecific resources for VAT statements</span></span>
<span data-ttu-id="28b93-255">La déclaration de TVA pour chaque pays doit répondre aux exigences de la législation du pays.</span><span class="sxs-lookup"><span data-stu-id="28b93-255">The VAT statement for each country must meet the requirements of the country’s legislation.</span></span> <span data-ttu-id="28b93-256">Il existe des modèles et des formats généraux prédéfinis de déclarations de TVA pour les pays répertoriés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="28b93-256">There are predefined general models and formats of VAT statements for the countries listed in the following table.</span></span>


| <span data-ttu-id="28b93-257">Pays</span><span class="sxs-lookup"><span data-stu-id="28b93-257">Country</span></span>        | <span data-ttu-id="28b93-258">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="28b93-258">Additional information</span></span>                                                          |
|----------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="28b93-259">Autriche</span><span class="sxs-lookup"><span data-stu-id="28b93-259">Austria</span></span>        |  [<span data-ttu-id="28b93-260">Détails de la déclaration de TVA pour l'Autriche</span><span class="sxs-lookup"><span data-stu-id="28b93-260">VAT statement details for Austria</span></span>](emea-aut-vat-statement-details.md)         |
| <span data-ttu-id="28b93-261">Belgique</span><span class="sxs-lookup"><span data-stu-id="28b93-261">Belgium</span></span>        |                                                                                 |
| <span data-ttu-id="28b93-262">République tchèque</span><span class="sxs-lookup"><span data-stu-id="28b93-262">Czech Republic</span></span> |  [<span data-ttu-id="28b93-263">Relevé de TVA - République tchèque</span><span class="sxs-lookup"><span data-stu-id="28b93-263">VAT statement for the Czech Republic</span></span>](emea-cze-vat-statement-details.md)   |
| <span data-ttu-id="28b93-264">Estonie</span><span class="sxs-lookup"><span data-stu-id="28b93-264">Estonia</span></span>        |  [<span data-ttu-id="28b93-265">Détails de la déclaration de TVA pour l'Estonie</span><span class="sxs-lookup"><span data-stu-id="28b93-265">VAT statement details for Estonia</span></span>](emea-est-vat-statement-details.md) |
| <span data-ttu-id="28b93-266">Finlande</span><span class="sxs-lookup"><span data-stu-id="28b93-266">Finland</span></span>        | [<span data-ttu-id="28b93-267">Déclaration de taxe pour la Finlande</span><span class="sxs-lookup"><span data-stu-id="28b93-267">Sales tax report for Finland</span></span>](emea-fin-sales-tax-payment-report-finland.md)          |
| <span data-ttu-id="28b93-268">Allemagne</span><span class="sxs-lookup"><span data-stu-id="28b93-268">Germany</span></span>        | [<span data-ttu-id="28b93-269">Déclaration de TVA pour l'Allemagne</span><span class="sxs-lookup"><span data-stu-id="28b93-269">VAT declaration for Germany</span></span>](emea-de-vat-declaration.md)                       |
| <span data-ttu-id="28b93-270">Italie</span><span class="sxs-lookup"><span data-stu-id="28b93-270">Italy</span></span>          | [<span data-ttu-id="28b93-271">Détails de la déclaration de TVA pour l'Italie</span><span class="sxs-lookup"><span data-stu-id="28b93-271">VAT statements details for Italy</span></span>](emea-ita-vat-statements-details.md)            |
| <span data-ttu-id="28b93-272">Lettonie</span><span class="sxs-lookup"><span data-stu-id="28b93-272">Latvia</span></span>         | [<span data-ttu-id="28b93-273">Détails de la déclaration de TVA pour la Lettonie</span><span class="sxs-lookup"><span data-stu-id="28b93-273">VAT statement details for Latvia</span></span>](emea-lva-vat-statement-details.md)           |
| <span data-ttu-id="28b93-274">Lituanie</span><span class="sxs-lookup"><span data-stu-id="28b93-274">Lithuania</span></span>      | [<span data-ttu-id="28b93-275">Détails de la déclaration de TVA pour la Lituanie</span><span class="sxs-lookup"><span data-stu-id="28b93-275">VAT statement details for Lithuania</span></span>](emea-ltu-vat-statement-details.md)         |
| <span data-ttu-id="28b93-276">Pays-Bas</span><span class="sxs-lookup"><span data-stu-id="28b93-276">Netherlands</span></span>    | [<span data-ttu-id="28b93-277">Déclaration de TVA pour les Pays-Bas</span><span class="sxs-lookup"><span data-stu-id="28b93-277">VAT declaration for the Netherlands</span></span>](emea-nl-vat-declaration.md)           |
| <span data-ttu-id="28b93-278">Suède</span><span class="sxs-lookup"><span data-stu-id="28b93-278">Sweden</span></span>         | [<span data-ttu-id="28b93-279">Déclaration de taxe pour la Suède</span><span class="sxs-lookup"><span data-stu-id="28b93-279">Sales tax report for Sweden</span></span>](emea-swe-sales-tax-payment-report-sweden.md)          |





