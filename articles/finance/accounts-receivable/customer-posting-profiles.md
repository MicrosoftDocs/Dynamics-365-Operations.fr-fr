---
title: Profils de validation client
description: Les profils de validation client contrôlent la validation des transactions client dans la comptabilité.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1bb2784d70e99c3c3443bed1b8cb040552b5b6f6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189060"
---
# <a name="customer-posting-profiles"></a><span data-ttu-id="43e81-103">Profils de validation client</span><span class="sxs-lookup"><span data-stu-id="43e81-103">Customer posting profiles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43e81-104">Les profils de validation client contrôlent la validation des transactions client dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="43e81-104">Customer posting profiles control the posting of customer transactions to the general ledger.</span></span>

<a name="customer-posting-profiles"></a><span data-ttu-id="43e81-105">Profils de validation client</span><span class="sxs-lookup"><span data-stu-id="43e81-105">Customer posting profiles</span></span>
-------------------------

<span data-ttu-id="43e81-106">Les profils de validation client permettent d'affecter des comptes généraux et des paramètres de document à tous les clients, à un groupe de clients ou à un client unique.</span><span class="sxs-lookup"><span data-stu-id="43e81-106">Customer posting profiles enable you to assign general ledger accounts and document settings to all customers, a group of customers or a single customer.</span></span> <span data-ttu-id="43e81-107">Ces paramètres sont utilisés lorsque vous créez des commandes client, des factures financières, des paiements en espèces, des lettres de relance et des notes d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="43e81-107">These settings will be used when you create sales orders, free text invoices, cash payments, collection letters, and interest notes.</span></span> <span data-ttu-id="43e81-108">Pour certaines transactions, vous pouvez sélectionner un profil de validation différent qui prime sur les profils de validation paramétrés pour les transactions dans cette page.</span><span class="sxs-lookup"><span data-stu-id="43e81-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> 

<span data-ttu-id="43e81-109">Le profil de validation par défaut est défini dans l'organisateur Comptabilité et taxe sur la page de paramètres de la Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="43e81-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts receivable parameters page.</span></span> <span data-ttu-id="43e81-110">Le profil de validation par défaut est alors automatiquement inclus dans l'en-tête des nouveaux documents dans lesquels vous pouvez le modifier en un profil de validation différent, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="43e81-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="43e81-111">Vous pouvez également associer des définitions de validation aux types de validation de transaction sur la page Définitions de validation de transaction.</span><span class="sxs-lookup"><span data-stu-id="43e81-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="43e81-112">Les définitions de validation contrôlent la validation des transactions client dans la comptabilité à la place des profils de validation.</span><span class="sxs-lookup"><span data-stu-id="43e81-112">Posting definitions control the posting of customer transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="43e81-113">Création d'un profil de validation</span><span class="sxs-lookup"><span data-stu-id="43e81-113">Creating a posting profile</span></span>
<span data-ttu-id="43e81-114">Permet de spécifier les comptes généraux utilisés dans la validation des transactions dont le profil de validation est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="43e81-114">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="43e81-115">Permet de sélectionner un code compte et, si possible, un numéro de compte ou de groupe pour le profil de validation sélectionné.</span><span class="sxs-lookup"><span data-stu-id="43e81-115">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="43e81-116">Lors de la validation, le profil de validation qui convient le mieux à chaque transaction est localisé en recherchant la combinaison code compte, numéro de compte ou groupe et numéro la plus spécifique selon la priorité suivante :</span><span class="sxs-lookup"><span data-stu-id="43e81-116">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="43e81-117">Valeur du champ **Code de compte**</span><span class="sxs-lookup"><span data-stu-id="43e81-117">**Account code** field value</span></span> | <span data-ttu-id="43e81-118">Valeur du champ **Numéro de compte/groupe**</span><span class="sxs-lookup"><span data-stu-id="43e81-118">**Account/Group number** field value</span></span>            | <span data-ttu-id="43e81-119">Priorité de recherche</span><span class="sxs-lookup"><span data-stu-id="43e81-119">Search priority</span></span> |
|------------------------------|-------------------------------------------------|-----------------|
| <span data-ttu-id="43e81-120">**Enregistrement**</span><span class="sxs-lookup"><span data-stu-id="43e81-120">**Table**</span></span>                    | <span data-ttu-id="43e81-121">Compte client spécifique</span><span class="sxs-lookup"><span data-stu-id="43e81-121">Specific customer account</span></span>                       | <span data-ttu-id="43e81-122">1</span><span class="sxs-lookup"><span data-stu-id="43e81-122">1</span></span>               |
| <span data-ttu-id="43e81-123">**Groupe**</span><span class="sxs-lookup"><span data-stu-id="43e81-123">**Group**</span></span>                    | <span data-ttu-id="43e81-124">Groupe de clients affecté au client</span><span class="sxs-lookup"><span data-stu-id="43e81-124">Customer group that is assigned to the customer</span></span> | <span data-ttu-id="43e81-125">2</span><span class="sxs-lookup"><span data-stu-id="43e81-125">2</span></span>               |
| <span data-ttu-id="43e81-126">**Tout**</span><span class="sxs-lookup"><span data-stu-id="43e81-126">**All**</span></span>                      | <span data-ttu-id="43e81-127">Blanc</span><span class="sxs-lookup"><span data-stu-id="43e81-127">Blank</span></span>                                           | <span data-ttu-id="43e81-128">3</span><span class="sxs-lookup"><span data-stu-id="43e81-128">3</span></span>               |

<span data-ttu-id="43e81-129">Si vous souhaitez que toutes les transactions client aient le même profil de validation, paramétrez un seul profil de validation à l'aide de la valeur Tous du champ Code de compte.</span><span class="sxs-lookup"><span data-stu-id="43e81-129">If you want all customer transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="43e81-130">Spécifiez les valeurs suivantes pour paramétrer votre profil de validation :</span><span class="sxs-lookup"><span data-stu-id="43e81-130">Specify the following values to set up your posting profile:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="43e81-131">Champ</span><span class="sxs-lookup"><span data-stu-id="43e81-131">Field</span></span></th>
<th><span data-ttu-id="43e81-132">Description</span><span class="sxs-lookup"><span data-stu-id="43e81-132">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="43e81-133"><strong>Profil de validation</strong></span><span class="sxs-lookup"><span data-stu-id="43e81-133"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="43e81-134">Permet d'entrer un code pour le profil de validation.</span><span class="sxs-lookup"><span data-stu-id="43e81-134">Enter a code for the posting profile.</span></span> <span data-ttu-id="43e81-135">Par exemple, vous pouvez créer deux profils de validation afin d'obtenir un compte pour les soldes client dans la devise nationale et un autre dans une devise étrangère.</span><span class="sxs-lookup"><span data-stu-id="43e81-135">For example, you could create two posting profiles to obtain one account for customer balances in the national currency and another for customer balances in a foreign currency.</span></span> <span data-ttu-id="43e81-136">Vous pouvez appeler un compte National et l'autre Étranger.</span><span class="sxs-lookup"><span data-stu-id="43e81-136">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="43e81-137"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="43e81-137"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="43e81-138">Permet d'entrer la description du profil de validation.</span><span class="sxs-lookup"><span data-stu-id="43e81-138">Enter a description of the posting profile.</span></span> <span data-ttu-id="43e81-139">Cela est uniquement utilisé pour mieux identifier le profil de validation lorsque vous l'affichez sur cette page.</span><span class="sxs-lookup"><span data-stu-id="43e81-139">This is only used to better identify the posting profile when you view it in this page.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="43e81-140"><strong>Code de compte</strong></span><span class="sxs-lookup"><span data-stu-id="43e81-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="43e81-141">Permet de spécifier si le profil de validation s'applique à un seul client, à un groupe de clients ou à tous les clients :</span><span class="sxs-lookup"><span data-stu-id="43e81-141">Specify whether the posting profile applies to a single customer, a group of customers, or all customers:</span></span>
<ul>
<li><span data-ttu-id="43e81-142"><strong>Table</strong> – Le profil de validation s'applique à un seul client.</span><span class="sxs-lookup"><span data-stu-id="43e81-142"><strong>Table</strong> – The posting profile applies to a single customer.</span></span> <span data-ttu-id="43e81-143">Sélectionnez le compte client dans le champ Numéro de compte/groupe.</span><span class="sxs-lookup"><span data-stu-id="43e81-143">Select the customer account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="43e81-144"><strong>Group</strong> – Le profil de validation s'applique à un groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="43e81-144"><strong>Group</strong> – The posting profile applies to a customer group.</span></span> <span data-ttu-id="43e81-145">Sélectionnez le groupe de clients dans le champ Numéro de compte/groupe.</span><span class="sxs-lookup"><span data-stu-id="43e81-145">Select the customer group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="43e81-146"><strong>Tous</strong> – Le profil de validation s'applique à tous les clients.</span><span class="sxs-lookup"><span data-stu-id="43e81-146"><strong>All</strong> – The posting profile applies to all customers.</span></span> <span data-ttu-id="43e81-147">Laissez vide le champ Numéro de compte/groupe.</span><span class="sxs-lookup"><span data-stu-id="43e81-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="43e81-148"><strong>Numéro de compte/groupe</strong></span><span class="sxs-lookup"><span data-stu-id="43e81-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="43e81-149">Si l'option Table est sélectionnée dans le champ Code de compte, sélectionnez le numéro de compte du client associé au profil de validation.</span><span class="sxs-lookup"><span data-stu-id="43e81-149">If Table is selected in the Account code field, select the account number of the customer who is associated with the posting profile.</span></span> <span data-ttu-id="43e81-150">Si l'option Groupe est sélectionnée, sélectionnez le groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="43e81-150">If Group is selected, select the customer group.</span></span> <span data-ttu-id="43e81-151">Si l'option Tous est sélectionnée, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="43e81-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="43e81-152"><strong>Compte collectif</strong></span><span class="sxs-lookup"><span data-stu-id="43e81-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="43e81-153">Permet de sélectionner le compte général qui sera utilisé comme compte collectif client pour les clients associés au profil de validation.</span><span class="sxs-lookup"><span data-stu-id="43e81-153">Select the ledger account that will be used as the customer summary account for the customers who are associated with the posting profile.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="43e81-154"><strong>Compte de règlement</strong></span><span class="sxs-lookup"><span data-stu-id="43e81-154"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="43e81-155">Permet de sélectionner le compte général de liquidités utilisé pour les prévisions de flux de trésorerie.</span><span class="sxs-lookup"><span data-stu-id="43e81-155">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="43e81-156">Ce champ s'affiche uniquement si les prévisions de flux de trésorerie sont activées.</span><span class="sxs-lookup"><span data-stu-id="43e81-156">This field will only appear if cash flow forecasts are enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="43e81-157"><strong>Acomptes de taxe</strong></span><span class="sxs-lookup"><span data-stu-id="43e81-157"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="43e81-158">Permet de sélectionner le compte pour les paiements en avance des taxes.</span><span class="sxs-lookup"><span data-stu-id="43e81-158">Select the account for sales tax for payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Remarque" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="43e81-160"><strong>Remarque</strong></span><span class="sxs-lookup"><span data-stu-id="43e81-160"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="43e81-161">La page Paramètres de la comptabilité client permet de spécifier le profil de validation à utiliser lorsqu'un paiement est marqué comme acompte.</span><span class="sxs-lookup"><span data-stu-id="43e81-161">Use the Accounts receivable parameters page to specify the posting profile to use when a payment is marked as a prepayment.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="43e81-162"><strong>Passif du compte de remise</strong></span><span class="sxs-lookup"><span data-stu-id="43e81-162"><strong>Liabilities for discount account</strong></span></span></td>
<td><span data-ttu-id="43e81-163">Permet de sélectionner le compte général des engagements de remise.</span><span class="sxs-lookup"><span data-stu-id="43e81-163">Select the ledger account for liabilities of discount.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="43e81-164"><strong>Série de lettres de relance</strong></span><span class="sxs-lookup"><span data-stu-id="43e81-164"><strong>Collection letter sequence</strong></span></span></td>
<td><span data-ttu-id="43e81-165">Permet de sélectionner l'identificateur de la série de lettres de relance à utiliser pour les clients auxquels le profil de validation est affecté.</span><span class="sxs-lookup"><span data-stu-id="43e81-165">Select the identifier of the collection letter sequence to use for customers to whom the posting profile is assigned.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="43e81-166"><strong>Code intérêt</strong></span><span class="sxs-lookup"><span data-stu-id="43e81-166"><strong>Interest code</strong></span></span></td>
<td><span data-ttu-id="43e81-167">Permet de sélectionner le code intérêt à utiliser pour le calcul des intérêts des clients auxquels le profil de validation est affecté.</span><span class="sxs-lookup"><span data-stu-id="43e81-167">Select the interest code to use for the calculation of interest for customers to whom the posting profile is assigned.</span></span></td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a><span data-ttu-id="43e81-168">**Restrictions de table**</span><span class="sxs-lookup"><span data-stu-id="43e81-168">**Table restrictions**</span></span>

<span data-ttu-id="43e81-169">Pour les transactions dont le profil de validation est sélectionné, spécifiez si les transactions seront réglées automatiquement, si des intérêts seront calculés et si des lettres de relance seront émises.</span><span class="sxs-lookup"><span data-stu-id="43e81-169">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="43e81-170">Vous pouvez également sélectionner le compte utilisé lorsque des transactions dont le profil de validation est sélectionné sont clôturées.</span><span class="sxs-lookup"><span data-stu-id="43e81-170">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="43e81-171">Spécifiez les valeurs suivantes pour paramétrer votre profil de validation :</span><span class="sxs-lookup"><span data-stu-id="43e81-171">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="43e81-172">Champ</span><span class="sxs-lookup"><span data-stu-id="43e81-172">Field</span></span>                 | <span data-ttu-id="43e81-173">Description</span><span class="sxs-lookup"><span data-stu-id="43e81-173">Description</span></span>                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="43e81-174">**Règlement**</span><span class="sxs-lookup"><span data-stu-id="43e81-174">**Settlement**</span></span>        | <span data-ttu-id="43e81-175">Sélectionnez cette bascule pour activer le règlement automatique des transactions dotées de ce profil de validation.</span><span class="sxs-lookup"><span data-stu-id="43e81-175">Select this toggle to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="43e81-176">Si cette bascule est désactivée, vous devez régler manuellement les transactions par l'intermédiaire de la page Régler les transactions en cours ou de la page Entrer les paiements client.</span><span class="sxs-lookup"><span data-stu-id="43e81-176">If this toggle is cleared, you must manually settle transactions by using the Settle open transactions page or the Enter customer payments page.</span></span> |
| <span data-ttu-id="43e81-177">**Intérêts**</span><span class="sxs-lookup"><span data-stu-id="43e81-177">**Interest**</span></span>          | <span data-ttu-id="43e81-178">Sélectionnez cette bascule si des intérêts doivent être calculés sur les soldes restants pour les comptes client qui utilisent ce profil.</span><span class="sxs-lookup"><span data-stu-id="43e81-178">Select this toggle if interest should be calculated on outstanding balances for customer accounts that use this profile.</span></span> <span data-ttu-id="43e81-179">Si elle est désactivée, les intérêts ne seront pas calculés pour ces clients.</span><span class="sxs-lookup"><span data-stu-id="43e81-179">If this toggle is cleared, interest will not be calculated for these customers.</span></span>                                           |
| <span data-ttu-id="43e81-180">**Lettre de relance**</span><span class="sxs-lookup"><span data-stu-id="43e81-180">**Collection letter**</span></span> | <span data-ttu-id="43e81-181">Sélectionnez cette bascule si des lettres de relance doivent être générées pour les comptes client qui utilisent ce profil.</span><span class="sxs-lookup"><span data-stu-id="43e81-181">Select this toggle if collection letters should be generated for customer accounts that use this profile.</span></span> <span data-ttu-id="43e81-182">Si elle est désactivée, les lettres de relance ne seront pas générées pour ces clients.</span><span class="sxs-lookup"><span data-stu-id="43e81-182">If this toggle is cleared, collection letters will not be generated for these customers.</span></span>                                                 |
| <span data-ttu-id="43e81-183">**Clôture**</span><span class="sxs-lookup"><span data-stu-id="43e81-183">**Close**</span></span>             | <span data-ttu-id="43e81-184">Permet de sélectionner un autre profil de validation à utiliser lors de la clôture des transactions présentant ce profil de validation.</span><span class="sxs-lookup"><span data-stu-id="43e81-184">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="43e81-185">Une transaction est considérée comme clôturée si elle a été totalement réglée.</span><span class="sxs-lookup"><span data-stu-id="43e81-185">A transaction is regarded as closed when it has been settled in full.</span></span>                                                                           |



<span data-ttu-id="43e81-186">Pour plus d'informations, voir [Vue d'ensemble des paiements client](../cash-bank-management/tasks/customer-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="43e81-186">For more information, see [Customer payment overview](../cash-bank-management/tasks/customer-payment-overview.md).</span></span>

