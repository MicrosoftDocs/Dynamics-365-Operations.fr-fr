---
title: État Balance comptable avec le détail des transactions
description: Cette rubrique décrit l’état par défaut des balances comptables. Elle décrit également les blocs élémentaires associés à cet état et comment il est possible de modifier l’état pour l’adapter à vos exigences métier.
author: v-kiarnd
manager: AnnBe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-kiarnd
ms.search.validFrom: 2019-10-24
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 29208cea6dbcf01d9a4c4fc6937dc872ec534661
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258145"
---
# <a name="trial-balance-with-transactional-detail-report"></a><span data-ttu-id="83521-104">État Balance comptable avec le détail des transactions</span><span class="sxs-lookup"><span data-stu-id="83521-104">Trial balance with transactional detail report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83521-105">Cette rubrique décrit l’état par défaut des balances comptables.</span><span class="sxs-lookup"><span data-stu-id="83521-105">This topic describes the default report for trial balances.</span></span> <span data-ttu-id="83521-106">Elle décrit également les blocs élémentaires associés à cet état et comment il est possible de modifier l’état pour l’adapter à vos exigences métier.</span><span class="sxs-lookup"><span data-stu-id="83521-106">It also describes the building blocks that are associated with this report and how you can modify the report to fit your business requirements.</span></span>

<span data-ttu-id="83521-107">Vous pouvez utiliser l’état **Balance comptable avec le détail des transactions** pour afficher les détails de chaque transaction pour les comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="83521-107">You can use the **Trial balance with transactional detail** report to show the details of each transaction for ledger accounts.</span></span> <span data-ttu-id="83521-108">L’état couvre les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="83521-108">The report includes the following information:</span></span> 

- <span data-ttu-id="83521-109">Soldes d’ouverture</span><span class="sxs-lookup"><span data-stu-id="83521-109">Opening balances</span></span>
- <span data-ttu-id="83521-110">Débits et crédits</span><span class="sxs-lookup"><span data-stu-id="83521-110">Debits and credits</span></span> 
- <span data-ttu-id="83521-111">Soldes qui en résultent pour une plage de dates de 31 jours ou moins</span><span class="sxs-lookup"><span data-stu-id="83521-111">The resulting balances for a date range of 31 days or less</span></span>

<span data-ttu-id="83521-112">Pour les transactions, l’état comprend les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="83521-112">For transactions, the report includes the following information:</span></span> 

- <span data-ttu-id="83521-113">Date de transaction</span><span class="sxs-lookup"><span data-stu-id="83521-113">Transaction date</span></span>
- <span data-ttu-id="83521-114">N° document</span><span class="sxs-lookup"><span data-stu-id="83521-114">Voucher number</span></span>
- <span data-ttu-id="83521-115">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="83521-115">Account number</span></span>
- <span data-ttu-id="83521-116">Numéro de référence</span><span class="sxs-lookup"><span data-stu-id="83521-116">Document number</span></span>
- <span data-ttu-id="83521-117">Dimension comptable</span><span class="sxs-lookup"><span data-stu-id="83521-117">Ledger dimension</span></span>
- <span data-ttu-id="83521-118">Nom de dimension comptable</span><span class="sxs-lookup"><span data-stu-id="83521-118">Ledger dimension name</span></span>
- <span data-ttu-id="83521-119">Description de la transaction</span><span class="sxs-lookup"><span data-stu-id="83521-119">Transaction description</span></span>
- <span data-ttu-id="83521-120">Débits ou crédits</span><span class="sxs-lookup"><span data-stu-id="83521-120">Debits or credits</span></span>
- <span data-ttu-id="83521-121">Solde courant pour l’année en cours, basé sur l’exercice fiscal en cours</span><span class="sxs-lookup"><span data-stu-id="83521-121">A running balance for the year to date, based on the current fiscal year</span></span>

<span data-ttu-id="83521-122">Vous pouvez utiliser la balance comptable pour identifier les erreurs des soldes de compte.</span><span class="sxs-lookup"><span data-stu-id="83521-122">You can use the trial balance to identify errors for account balances.</span></span> <span data-ttu-id="83521-123">Tous les comptes avec des soldes débiteurs doivent être égaux à tous les comptes avec des soldes créditeurs.</span><span class="sxs-lookup"><span data-stu-id="83521-123">All accounts that have debit balances should equal all accounts that have credit balances.</span></span> <span data-ttu-id="83521-124">L’état comprend les informations des écritures comptables du journal des opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="83521-124">The report includes information from the general journal accounting entries.</span></span>

<span data-ttu-id="83521-125">Vous pouvez filtrer les données selon l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="83521-125">You can filter the data by any of the following items:</span></span>

- <span data-ttu-id="83521-126">Transactions validées</span><span class="sxs-lookup"><span data-stu-id="83521-126">Posted transactions</span></span>
- <span data-ttu-id="83521-127">Transactions en attente (Ces transactions comprennent toutes les transactions qui ne sont pas validées.)</span><span class="sxs-lookup"><span data-stu-id="83521-127">Pending transactions (These transactions include all transactions that aren't posted.)</span></span> 
- <span data-ttu-id="83521-128">Toutes les transactions</span><span class="sxs-lookup"><span data-stu-id="83521-128">All transactions</span></span> 

<span data-ttu-id="83521-129">Si les transactions comprennent des dimensions financières, l’état affiche ces informations dans un compte général.</span><span class="sxs-lookup"><span data-stu-id="83521-129">If the transactions include financial dimensions, the report shows that information under a ledger account.</span></span> <span data-ttu-id="83521-130">Sinon, les informations des dimensions financières sont regroupées en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="83521-130">Otherwise, information for financial dimensions is grouped at the top of the page.</span></span> 

<span data-ttu-id="83521-131">Actuellement, l’état est exporté directement vers Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="83521-131">Currently, the report is exported directly to Microsoft Excel.</span></span> 

## <a name="transaction-information-on-the-report"></a><span data-ttu-id="83521-132">Informations de transaction de l’état</span><span class="sxs-lookup"><span data-stu-id="83521-132">Transaction information on the report</span></span>

<span data-ttu-id="83521-133">Selon le type de transaction, comme une écriture comptable avancée (ALE) ou une commande fournisseur, les informations supplémentaires suivantes s’affichent sur l’état.</span><span class="sxs-lookup"><span data-stu-id="83521-133">Depending on the type of transaction, such as an advanced ledger entry (ALE) or purchase order, the following additional information appears on the report.</span></span>

<table> 
<thead>
<tr>
<th><span data-ttu-id="83521-134">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="83521-134">Transaction type</span></span></th>
<th><span data-ttu-id="83521-135">Informations supplémentaires sur le document</span><span class="sxs-lookup"><span data-stu-id="83521-135">Additional document information</span></span></th>
<th><span data-ttu-id="83521-136">Informations supplémentaires sur la description</span><span class="sxs-lookup"><span data-stu-id="83521-136">Additional description information</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<ul>
<li><span data-ttu-id="83521-137">N° document ALE</span><span class="sxs-lookup"><span data-stu-id="83521-137">ALE voucher</span></span></li>
<li><span data-ttu-id="83521-138">Règle de répartition</span><span class="sxs-lookup"><span data-stu-id="83521-138">Allocation rule</span></span></li>
<li><span data-ttu-id="83521-139">Transfert d’un journal des opérations diverses</span><span class="sxs-lookup"><span data-stu-id="83521-139">General journal transfer</span></span></li>
<li><span data-ttu-id="83521-140">Journal</span><span class="sxs-lookup"><span data-stu-id="83521-140">Journal</span></span></li>
</ul>
</td>
<td><span data-ttu-id="83521-141">Numéro ALE ou numéro du journal des opérations diverses</span><span class="sxs-lookup"><span data-stu-id="83521-141">ALE number or general journal number</span></span></td>
<td><span data-ttu-id="83521-142">Description de la ligne</span><span class="sxs-lookup"><span data-stu-id="83521-142">Line item description</span></span></td>
</tr>
<tr>
<td></td>
<td><span data-ttu-id="83521-143">Pas de données</span><span class="sxs-lookup"><span data-stu-id="83521-143">No data</span></span></td>
<td><span data-ttu-id="83521-144">Description de l’en-tête du journal ALE ou des opérations diverses</span><span class="sxs-lookup"><span data-stu-id="83521-144">ALE or general journal header description</span></span></td>
</tr>
<tr>
<td>
<ul>
<li><span data-ttu-id="83521-145">N° document de facture</span><span class="sxs-lookup"><span data-stu-id="83521-145">Invoice voucher</span></span></li>
<li><span data-ttu-id="83521-146">N° document d’avoir</span><span class="sxs-lookup"><span data-stu-id="83521-146">Credit note voucher</span></span></li>
</ul>
</td>
<td><span data-ttu-id="83521-147">Numéro de facture</span><span class="sxs-lookup"><span data-stu-id="83521-147">Invoice number</span></span></td>
<td><span data-ttu-id="83521-148">Numéro de fournisseur et nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="83521-148">Vendor number and Vendor name</span></span></td>
</tr>
<tr>
<td></td>
<td><span data-ttu-id="83521-149">Date de la facture</span><span class="sxs-lookup"><span data-stu-id="83521-149">Invoice date</span></span></td>
<td><span data-ttu-id="83521-150">Description de la ligne</span><span class="sxs-lookup"><span data-stu-id="83521-150">Line item description</span></span></td>
</tr>
<tr>
<td></td>
<td><span data-ttu-id="83521-151">Pas de données</span><span class="sxs-lookup"><span data-stu-id="83521-151">No data</span></span></td>
<td><span data-ttu-id="83521-152">Numéro de commande fournisseur et/ou numéro PA</span><span class="sxs-lookup"><span data-stu-id="83521-152">Purchase order number and/or PA number</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83521-153">N° document de paiement de la comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="83521-153">Accounts payable (AP) payment voucher</span></span></td>
<td><span data-ttu-id="83521-154">Numéro de chèque ou numéro de transfert électronique de fonds (TEF)</span><span class="sxs-lookup"><span data-stu-id="83521-154">Check number or electronic funds transfer (EFT) number</span></span></td>
<td><span data-ttu-id="83521-155">Numéro de fournisseur – Nom du fournisseur pour le compte de paiement ou de facturation</span><span class="sxs-lookup"><span data-stu-id="83521-155">Vendor number – Vendor name for the "pay to" or invoice account</span></span></td>
</tr>
<tr>
<td></td>
<td><span data-ttu-id="83521-156">Date du chèque, date du TEF ou date du règlement</span><span class="sxs-lookup"><span data-stu-id="83521-156">Check date, EFT date, or settlement date</span></span></td>
<td><span data-ttu-id="83521-157">Numéro de fournisseur et nom du fournisseur pour le compte commande d’origine</span><span class="sxs-lookup"><span data-stu-id="83521-157">Vendor number and Vendor name for the original order account</span></span></td>
</tr>
<tr>
<td>
<ul>
<li><span data-ttu-id="83521-158">Avoir financier</span><span class="sxs-lookup"><span data-stu-id="83521-158">Free text credit note</span></span></li>
<li><span data-ttu-id="83521-159">N° document de facture financière</span><span class="sxs-lookup"><span data-stu-id="83521-159">Free text invoice voucher</span></span></li>
</ul>
</td>
<td><span data-ttu-id="83521-160">Numéro de facture financière</span><span class="sxs-lookup"><span data-stu-id="83521-160">Free text invoice number</span></span></td>
<td><span data-ttu-id="83521-161">Numéro de client et nom du client</span><span class="sxs-lookup"><span data-stu-id="83521-161">Customer number and Customer name</span></span></td>
</tr>
<tr>
<td></td>
<td><span data-ttu-id="83521-162">Code facturation</span><span class="sxs-lookup"><span data-stu-id="83521-162">Billing code</span></span></td>
<td><span data-ttu-id="83521-163">Description de la ligne de facture financière</span><span class="sxs-lookup"><span data-stu-id="83521-163">Free text invoice line item description</span></span><br>
<span data-ttu-id="83521-164">(Champ <strong>Description</strong> de l’organisateur <strong>Lignes de facture</strong> de la page <strong>Factures financières</strong>)</span><span class="sxs-lookup"><span data-stu-id="83521-164">(<strong>Description</strong> field on the <strong>Invoice lines</strong> FastTab of the <strong>Free text invoices</strong> page)</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83521-165">N° document de paiement de la comptabilité client</span><span class="sxs-lookup"><span data-stu-id="83521-165">Accounts receivable (AR) payment voucher</span></span></td>
<td><span data-ttu-id="83521-166">Numéro de lot du journal</span><span class="sxs-lookup"><span data-stu-id="83521-166">Journal batch number</span></span><br>
<span data-ttu-id="83521-167">(Champ <strong>Numéro de lot du journal</strong> de l’onglet <strong>Vue d’ensemble</strong> de la page <strong>Journal des paiements</strong>)</span><span class="sxs-lookup"><span data-stu-id="83521-167">(<strong>Journal batch number</strong> field on the <strong>Overview</strong> tab of the <strong>Payment journal</strong> page)</span></span></td>
<td><span data-ttu-id="83521-168">Numéro de client – Nom du client</span><span class="sxs-lookup"><span data-stu-id="83521-168">Customer number – Customer name</span></span><br>
<span data-ttu-id="83521-169">(Champs <strong>Compte</strong> et <strong>Nom du compte</strong> de l’onglet <strong>Vue d’ensemble</strong> de la page <strong>N° document de journal</strong>)</span><span class="sxs-lookup"><span data-stu-id="83521-169">(<strong>Account</strong> and <strong>Account name</strong> fields on the <strong>Overview</strong> tab of the <strong>Journal voucher</strong> page)</span></span></td>
</tr>
<tr>
<td></td>
<td><span data-ttu-id="83521-170">Référence de paiement</span><span class="sxs-lookup"><span data-stu-id="83521-170">Payment reference</span></span></td>
<td><span data-ttu-id="83521-171">Description de la ligne</span><span class="sxs-lookup"><span data-stu-id="83521-171">Line description</span></span><br>
<span data-ttu-id="83521-172">(Champ <strong>Description</strong> de l’onglet <strong>Vue d’ensemble</strong> de la page <strong>N° document de journal</strong>)</span><span class="sxs-lookup"><span data-stu-id="83521-172">(<strong>Description</strong> field on the <strong>Overview</strong> tab of the <strong>Journal voucher</strong> page)</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83521-173">Écritures de registre budgétaires</span><span class="sxs-lookup"><span data-stu-id="83521-173">Budget register entries</span></span></td>
<td><span data-ttu-id="83521-174">Numéro d’écriture de registre budgétaire</span><span class="sxs-lookup"><span data-stu-id="83521-174">Budget register entry number</span></span></td>
<td><span data-ttu-id="83521-175">Description de l’écriture de registre budgétaire</span><span class="sxs-lookup"><span data-stu-id="83521-175">Budget register entry description</span></span></td>
</tr>
<tr>
<td></td>
<td><span data-ttu-id="83521-176">Code budgétaire</span><span class="sxs-lookup"><span data-stu-id="83521-176">Budget code</span></span></td>
<td><span data-ttu-id="83521-177">Code motif – Description de l’en-tête de l’écriture de registre budgétaire</span><span class="sxs-lookup"><span data-stu-id="83521-177">Reason code – Budget register entry header description</span></span><br>
<span data-ttu-id="83521-178">(Champ <strong>Commentaire</strong> de l’organisateur <strong>Détails sur l’écriture de compte budgétaire</strong> de la page <strong>Écriture budgétaire</strong> ou de la page <strong>Écriture de registre budgétaire</strong>)</span><span class="sxs-lookup"><span data-stu-id="83521-178">(<strong>Comment</strong> field on the <strong>Budget account entry details</strong> FastTab on the <strong>Budget entry</strong> page or the <strong>Budget register entry</strong> page)</span></span></td>
</tr>
<tr>
<td>
<ul>
<li><span data-ttu-id="83521-179">Confirmation de la commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="83521-179">Purchase order confirmation</span></span></li>
<li><span data-ttu-id="83521-180">N° document de la confirmation de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="83521-180">Purchase order confirmation voucher</span></span></li>
</ul>
</td>
<td><span data-ttu-id="83521-181">Numéro de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="83521-181">Purchase order number</span></span></td>
<td><span data-ttu-id="83521-182">Description de la ligne</span><span class="sxs-lookup"><span data-stu-id="83521-182">Line item description</span></span><br>
<span data-ttu-id="83521-183">(Champ <strong>Texte</strong> de l’organisateur <strong>Détails de la ligne</strong> de la page <strong>Commande fournisseur</strong>).</span><span class="sxs-lookup"><span data-stu-id="83521-183">(<strong>Text</strong> field on the <strong>Line details</strong> FastTab of the <strong>Purchase order</strong> page)</span></span></td>
</tr>
<tr>
<td></td>
<td><span data-ttu-id="83521-184">Numéro de ligne de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="83521-184">Purchase order line number</span></span></td>
<td><span data-ttu-id="83521-185">Catégorie d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="83521-185">Procurement category</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="83521-186">N° document de la demande d’achat</span><span class="sxs-lookup"><span data-stu-id="83521-186">Purchase requisition voucher</span></span></td>
<td><span data-ttu-id="83521-187">Numéro de demande d’achat</span><span class="sxs-lookup"><span data-stu-id="83521-187">Purchase requisition number</span></span></td>
<td><span data-ttu-id="83521-188">Nom de demande d’achat</span><span class="sxs-lookup"><span data-stu-id="83521-188">Purchase requisition name</span></span></td>
</tr>
<tr>
<td></td>
<td><span data-ttu-id="83521-189">Numéro de ligne de la demande d’achat</span><span class="sxs-lookup"><span data-stu-id="83521-189">Purchase requisition line number</span></span></td>
<td><span data-ttu-id="83521-190">Description de la ligne de demande d’achat</span><span class="sxs-lookup"><span data-stu-id="83521-190">Purchase requisition line description</span></span><br>
<span data-ttu-id="83521-191">(Champ <strong>Nom du produit</strong> de l’organisateur <strong>Lignes de demande d’achat</strong> de la page <strong>Demande d’achat</strong>).</span><span class="sxs-lookup"><span data-stu-id="83521-191">(<strong>Product name</strong> field on the <strong>Purchase requisition lines</strong> FastTab of the <strong>Purchase requisition</strong> page)</span></span></td>
</tr>
<tr>
<td>
<ul>
<li><span data-ttu-id="83521-192">N° document de facture de projet</span><span class="sxs-lookup"><span data-stu-id="83521-192">Project invoice voucher</span></span></li>
<li><span data-ttu-id="83521-193">Facture de projet</span><span class="sxs-lookup"><span data-stu-id="83521-193">Project invoice</span></span></li>
</ul>
</td>
<td><span data-ttu-id="83521-194">Numéro de facture du projet</span><span class="sxs-lookup"><span data-stu-id="83521-194">Project invoice number</span></span></td>
<td><span data-ttu-id="83521-195">Compte de facturation et nom du compte</span><span class="sxs-lookup"><span data-stu-id="83521-195">Invoice account and Account name</span></span></td>
</tr>
<tr>
<td></td>
<td><span data-ttu-id="83521-196">Source de financement</span><span class="sxs-lookup"><span data-stu-id="83521-196">Funding source</span></span></td>
<td><span data-ttu-id="83521-197">ID projet et nom du projet</span><span class="sxs-lookup"><span data-stu-id="83521-197">Project ID and Project name</span></span></td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]