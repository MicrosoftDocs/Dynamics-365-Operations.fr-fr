---
title: Profils de validation fournisseur
description: "Les profils de validation fournisseur contrôlent la validation des transactions fournisseur pour la comptabilité."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPosting
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: ae019ebec2788fc499b0f2ef27a7eb2832ceaa9d
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="vendor-posting-profiles"></a><span data-ttu-id="e5308-103">Profils de validation fournisseur</span><span class="sxs-lookup"><span data-stu-id="e5308-103">Vendor posting profiles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e5308-104">Les profils de validation fournisseur contrôlent la validation des transactions fournisseur pour la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="e5308-104">Vendor posting profiles control the posting of vendor transactions to the general ledger.</span></span>

<a name="vendor-posting-profiles"></a><span data-ttu-id="e5308-105">Profils de validation fournisseur</span><span class="sxs-lookup"><span data-stu-id="e5308-105">Vendor posting profiles</span></span>
-----------------------

<span data-ttu-id="e5308-106">Les profils de validation fournisseur permettent d'affecter des comptes généraux et des paramètres de document à tous les fournisseurs, à un groupe de fournisseurs ou à un fournisseur unique.</span><span class="sxs-lookup"><span data-stu-id="e5308-106">Vendor posting profiles enable you to assign general ledger accounts and document settings to all vendors, a group of vendors or a single vendor.</span></span> <span data-ttu-id="e5308-107">Ces paramètres sont utilisés lorsque vous créez des commandes fournisseur, des factures fournisseur et des paiements en espèces.</span><span class="sxs-lookup"><span data-stu-id="e5308-107">These settings will be used when you create purchase orders, vendor invoices and cash payments.</span></span> <span data-ttu-id="e5308-108">Pour certaines transactions, vous pouvez sélectionner un profil de validation différent qui prime sur les profils de validation paramétrés pour les transactions dans cette page.</span><span class="sxs-lookup"><span data-stu-id="e5308-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> <span data-ttu-id="e5308-109">Le profil de validation par défaut est défini dans l'organisateur Comptabilité et Taxe dans la page de paramètres de la Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e5308-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts payable parameters page.</span></span> <span data-ttu-id="e5308-110">Le profil de validation par défaut est alors automatiquement inclus dans l'en-tête des nouveaux documents dans lesquels vous pouvez le modifier en un profil de validation différent, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e5308-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="e5308-111">Vous pouvez également associer des définitions de validation aux types de validation de transaction sur la page Définitions de validation de transaction.</span><span class="sxs-lookup"><span data-stu-id="e5308-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="e5308-112">Les définitions de validation contrôlent la validation des transactions fournisseur dans la comptabilité à la place des profils de validation.</span><span class="sxs-lookup"><span data-stu-id="e5308-112">Posting definitions control the posting of vendor transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="e5308-113">Création d'un profil de validation</span><span class="sxs-lookup"><span data-stu-id="e5308-113">Creating a posting profile</span></span>
### <a name="setup"></a><span data-ttu-id="e5308-114">**Paramétrage**</span><span class="sxs-lookup"><span data-stu-id="e5308-114">**Setup**</span></span>

<span data-ttu-id="e5308-115">Permet de spécifier les comptes généraux utilisés dans la validation des transactions dont le profil de validation est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e5308-115">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="e5308-116">Permet de sélectionner un code compte et, si possible, un numéro de compte ou de groupe pour le profil de validation sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e5308-116">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="e5308-117">Lors de la validation, le profil de validation qui convient le mieux à chaque transaction est localisé en recherchant la combinaison code compte, numéro de compte ou groupe et numéro la plus spécifique selon la priorité suivante :</span><span class="sxs-lookup"><span data-stu-id="e5308-117">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="e5308-118">Valeur du champ **Code de compte**</span><span class="sxs-lookup"><span data-stu-id="e5308-118">**Account code** field value</span></span> | <span data-ttu-id="e5308-119">Valeur du champ **Numéro de compte/groupe**</span><span class="sxs-lookup"><span data-stu-id="e5308-119">**Account/Group number** field value</span></span>        | <span data-ttu-id="e5308-120">Priorité de recherche</span><span class="sxs-lookup"><span data-stu-id="e5308-120">Search priority</span></span> |
|------------------------------|---------------------------------------------|-----------------|
| <span data-ttu-id="e5308-121">**Enregistrement**</span><span class="sxs-lookup"><span data-stu-id="e5308-121">**Table**</span></span>                    | <span data-ttu-id="e5308-122">Compte fournisseur spécifique</span><span class="sxs-lookup"><span data-stu-id="e5308-122">Specific vendor account</span></span>                     | <span data-ttu-id="e5308-123">1</span><span class="sxs-lookup"><span data-stu-id="e5308-123">1</span></span>               |
| <span data-ttu-id="e5308-124">**Groupe**</span><span class="sxs-lookup"><span data-stu-id="e5308-124">**Group**</span></span>                    | <span data-ttu-id="e5308-125">groupe de fournisseurs assigné au fournisseur</span><span class="sxs-lookup"><span data-stu-id="e5308-125">vendor group that is assigned to the vendor</span></span> | <span data-ttu-id="e5308-126">2</span><span class="sxs-lookup"><span data-stu-id="e5308-126">2</span></span>               |
| <span data-ttu-id="e5308-127">**Tout**</span><span class="sxs-lookup"><span data-stu-id="e5308-127">**All**</span></span>                      | <span data-ttu-id="e5308-128">Blanc</span><span class="sxs-lookup"><span data-stu-id="e5308-128">Blank</span></span>                                       | <span data-ttu-id="e5308-129">3</span><span class="sxs-lookup"><span data-stu-id="e5308-129">3</span></span>               |

<span data-ttu-id="e5308-130">Si vous souhaitez que toutes les transactions fournisseur aient le même profil de validation, paramétrez un seul profil de validation à l'aide de la valeur Tous du champ Code de compte.</span><span class="sxs-lookup"><span data-stu-id="e5308-130">If you want all vendor transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="e5308-131">Spécifiez les valeurs suivantes pour paramétrer votre profil de validation :</span><span class="sxs-lookup"><span data-stu-id="e5308-131">Specify the following values to set up your posting profile:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="e5308-132">Champ</span><span class="sxs-lookup"><span data-stu-id="e5308-132">Field</span></span></th>
<th><span data-ttu-id="e5308-133">Description</span><span class="sxs-lookup"><span data-stu-id="e5308-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e5308-134"><strong>Profil de validation</strong></span><span class="sxs-lookup"><span data-stu-id="e5308-134"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="e5308-135">Permet d'entrer un code pour le profil de validation.</span><span class="sxs-lookup"><span data-stu-id="e5308-135">Enter a code for the posting profile.</span></span> <span data-ttu-id="e5308-136">Par exemple, vous pouvez créer deux profils de validation afin d'obtenir un compte pour les soldes fournisseur dans la devise nationale et un autre dans une devise étrangère.</span><span class="sxs-lookup"><span data-stu-id="e5308-136">For example, you could create two posting profiles to obtain one account for vendor balances in the national currency and another for vendor balances in a foreign currency.</span></span> <span data-ttu-id="e5308-137">Vous pouvez appeler un compte National et l'autre Étranger.</span><span class="sxs-lookup"><span data-stu-id="e5308-137">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e5308-138"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="e5308-138"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="e5308-139">Permet d'entrer la description du profil de validation.</span><span class="sxs-lookup"><span data-stu-id="e5308-139">Enter a description of the posting profile.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e5308-140"><strong>Code de compte</strong></span><span class="sxs-lookup"><span data-stu-id="e5308-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="e5308-141">Permet de spécifier si le profil de validation s'applique à un fournisseur spécifique, à un groupe de fournisseurs ou à tous les fournisseurs :</span><span class="sxs-lookup"><span data-stu-id="e5308-141">Specify whether the posting profile applies to a specific vendor, a group of vendors, or all vendors:</span></span>
<ul>
<li><span data-ttu-id="e5308-142"><strong>Table</strong> – Le profil de validation s'applique à un seul fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e5308-142"><strong>Table</strong> – The posting profile applies to a single vendor.</span></span> <span data-ttu-id="e5308-143">Sélectionnez le compte fournisseur dans le champ Numéro de compte/groupe.</span><span class="sxs-lookup"><span data-stu-id="e5308-143">Select the vendor account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="e5308-144"><strong>Groupe</strong> – Le profil de validation s'applique à un groupe de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="e5308-144"><strong>Group</strong> – The posting profile applies to a vendor group.</span></span> <span data-ttu-id="e5308-145">Sélectionnez le groupe de fournisseurs dans le champ Numéro de compte/groupe.</span><span class="sxs-lookup"><span data-stu-id="e5308-145">Select the vendor group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="e5308-146"><strong>Tous</strong> – Le profil de validation s'applique à tous les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="e5308-146"><strong>All</strong> – The posting profile applies to all vendors.</span></span> <span data-ttu-id="e5308-147">Laissez vide le champ Numéro de compte/groupe.</span><span class="sxs-lookup"><span data-stu-id="e5308-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e5308-148"><strong>Numéro de compte/groupe</strong></span><span class="sxs-lookup"><span data-stu-id="e5308-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="e5308-149">Si Table est sélectionné dans le champ Code de compte, sélectionnez le numéro de compte du fournisseur associé au profil de validation.</span><span class="sxs-lookup"><span data-stu-id="e5308-149">If Table is selected in the Account code field, select the account number of the vendor that is associated with the posting profile.</span></span> <span data-ttu-id="e5308-150">Si Groupe est sélectionné, sélectionnez un groupe de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="e5308-150">If Group is selected, select a vendor group.</span></span> <span data-ttu-id="e5308-151">Si l'option Tous est sélectionnée, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="e5308-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e5308-152"><strong>Compte collectif</strong></span><span class="sxs-lookup"><span data-stu-id="e5308-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="e5308-153">Permet de sélectionner le compte général qui sera utilisé comme compte collectif pour les fournisseurs auxquels se rapporte le profil de validation.</span><span class="sxs-lookup"><span data-stu-id="e5308-153">Select the ledger account that will be used as the summary account for the vendors that the posting profile relates to.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Remarque" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="e5308-155"><strong>Remarque</strong></span><span class="sxs-lookup"><span data-stu-id="e5308-155"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e5308-156">Si l'option Utiliser les définitions de validation est activée dans la page Paramètres de comptabilité, la définition de validation de transaction pour les factures fournisseur est utilisée à la place du compte collectif.</span><span class="sxs-lookup"><span data-stu-id="e5308-156">If the Use posting definitions toggle is selected in the General ledger parameters page, the transaction posting definition for vendor invoices is used instead of the summary account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e5308-157"><strong>Compte de règlement</strong></span><span class="sxs-lookup"><span data-stu-id="e5308-157"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="e5308-158">Permet de sélectionner le compte général de liquidités utilisé pour les prévisions de flux de trésorerie.</span><span class="sxs-lookup"><span data-stu-id="e5308-158">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="e5308-159">Ce champ n'est disponible que lorsque la prévision du flux de trésorerie est activée.</span><span class="sxs-lookup"><span data-stu-id="e5308-159">This fields is only available when cash flow forecasting is enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e5308-160"><strong>Acomptes de taxe</strong></span><span class="sxs-lookup"><span data-stu-id="e5308-160"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="e5308-161">Permet de sélectionner le compte pour les paiements de taxe reçus en avance.</span><span class="sxs-lookup"><span data-stu-id="e5308-161">Select the account for sales tax payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Remarque" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="e5308-163"><strong>Remarque</strong></span><span class="sxs-lookup"><span data-stu-id="e5308-163"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e5308-164">Le profil de validation utilisé lorsque le paiement est marqué comme acompte est sélectionné dans le champ Profil de validation avec N° document du journal des acomptes dans la zone Comptabilité et Taxe de la page de paramètres de la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e5308-164">The posting profile that is used when the payment is marked as a prepayment is selected in the Posting profile with prepayment journal voucher field in the Ledger and sales tax area of the Accounts payable parameters page.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e5308-165"><strong>Arrivée</strong></span><span class="sxs-lookup"><span data-stu-id="e5308-165"><strong>Arrival</strong></span></span></td>
<td><span data-ttu-id="e5308-166">Permet de sélectionner le compte général sur lequel les informations relatives aux factures fournisseur non approuvées sont validées.</span><span class="sxs-lookup"><span data-stu-id="e5308-166">Select the ledger account that information about unapproved vendor invoices is posted to.</span></span> <span data-ttu-id="e5308-167">Les informations sont entrées dans le journal du registre des factures.</span><span class="sxs-lookup"><span data-stu-id="e5308-167">The information is entered in the Invoice register journal.</span></span> <span data-ttu-id="e5308-168">Par exemple, un utilisateur entre des informations très élémentaires sur des factures fournisseur lors de leur réception dans le registre des factures.</span><span class="sxs-lookup"><span data-stu-id="e5308-168">For example, a user enters very basic information about vendor invoices when they are received in the invoice register.</span></span> <span data-ttu-id="e5308-169">Lors de la validation du registre des factures, les transactions sont validées sur le compte entré ici et dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="e5308-169">When the invoice register is posted, the transactions are posted to the account that is entered here and in the Offset account field.</span></span> <span data-ttu-id="e5308-170">Lors de l'approbation des factures, la dette est transférée du compte Arrivée vers le compte collectif fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e5308-170">When the invoices are approved, the debt is transferred from the Arrival account to the vendor summary account.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e5308-171"><strong>Compte de contrepartie</strong></span><span class="sxs-lookup"><span data-stu-id="e5308-171"><strong>Offset account</strong></span></span></td>
<td><span data-ttu-id="e5308-172">Permet de sélectionner le compte général utilisé pour compenser les factures fournisseur non approuvées qui sont mises à jour à l'aide du registre des factures.</span><span class="sxs-lookup"><span data-stu-id="e5308-172">Select the ledger account that is used for offsetting unapproved vendor invoices that are updated by using the invoice register.</span></span> <span data-ttu-id="e5308-173">Le compte de contrepartie agit comme le compte de contrepartie pour les transactions qui sont validées sur les comptes d'arrivée.</span><span class="sxs-lookup"><span data-stu-id="e5308-173">The offset account acts as the offset account for transactions that are posted to arrival accounts.</span></span> <span data-ttu-id="e5308-174">Par conséquent, le compte contient les achats fournisseur qui n'ont pas encore été approuvés.</span><span class="sxs-lookup"><span data-stu-id="e5308-174">Therefore, the account contains vendor purchases that have not yet been approved.</span></span></td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a><span data-ttu-id="e5308-175">**Restrictions de table**</span><span class="sxs-lookup"><span data-stu-id="e5308-175">**Table restrictions**</span></span>

<span data-ttu-id="e5308-176">Pour les transactions dont le profil de validation est sélectionné, spécifiez si les transactions seront réglées automatiquement, si des intérêts seront calculés et si des lettres de relance seront émises.</span><span class="sxs-lookup"><span data-stu-id="e5308-176">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="e5308-177">Vous pouvez également sélectionner le compte utilisé lorsque des transactions dont le profil de validation est sélectionné sont clôturées.</span><span class="sxs-lookup"><span data-stu-id="e5308-177">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="e5308-178">Spécifiez les valeurs suivantes pour paramétrer votre profil de validation :</span><span class="sxs-lookup"><span data-stu-id="e5308-178">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="e5308-179">Champ</span><span class="sxs-lookup"><span data-stu-id="e5308-179">Field</span></span>          | <span data-ttu-id="e5308-180">Description</span><span class="sxs-lookup"><span data-stu-id="e5308-180">Description</span></span>                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e5308-181">**Règlement**</span><span class="sxs-lookup"><span data-stu-id="e5308-181">**Settlement**</span></span> | <span data-ttu-id="e5308-182">Sélectionnez cette option pour activer le règlement automatique des transactions bénéficiant de ce profil de validation.</span><span class="sxs-lookup"><span data-stu-id="e5308-182">Select this option to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="e5308-183">Si cette option est désactivée, vous devez régler manuellement les transactions à l'aide de la page Régler les transactions en cours.</span><span class="sxs-lookup"><span data-stu-id="e5308-183">If this option is cleared, you must manually settle transactions by using the Settle open transactions page.</span></span> |
| <span data-ttu-id="e5308-184">**Annuler**</span><span class="sxs-lookup"><span data-stu-id="e5308-184">**Cancel**</span></span>     | <span data-ttu-id="e5308-185">Sélectionnez cette option pour pouvoir annuler les transactions associées à ce profil de validation.</span><span class="sxs-lookup"><span data-stu-id="e5308-185">Select this option if you want to be able to cancel transactions that have this posting profile.</span></span>                                                                                                               |
| <span data-ttu-id="e5308-186">**Clôture**</span><span class="sxs-lookup"><span data-stu-id="e5308-186">**Close**</span></span>      | <span data-ttu-id="e5308-187">Permet de sélectionner un autre profil de validation à utiliser lors de la clôture des transactions présentant ce profil de validation.</span><span class="sxs-lookup"><span data-stu-id="e5308-187">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="e5308-188">Une transaction est considérée comme clôturée si elle a été totalement réglée.</span><span class="sxs-lookup"><span data-stu-id="e5308-188">A transaction is regarded as closed when it has been settled in full.</span></span>                                       |






