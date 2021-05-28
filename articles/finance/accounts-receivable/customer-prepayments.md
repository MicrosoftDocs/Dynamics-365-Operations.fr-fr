---
title: Acomptes client
description: Cette rubrique explique comment configurer et traiter les acomptes clients (également appelés dépôts clients).
author: roschlom
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3314803b994aed40e5b04d8546a45bd305d48b6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019418"
---
# <a name="customer-prepayments"></a><span data-ttu-id="081af-103">Acomptes client</span><span class="sxs-lookup"><span data-stu-id="081af-103">Customer prepayments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="081af-104">Les acomptes clients sont utilisés lorsque vous recevez un paiement d'un client, mais il n'y a pas de facture contre laquelle le paiement peut être réglé.</span><span class="sxs-lookup"><span data-stu-id="081af-104">Customer prepayments are used when you receive a payment from a customer, but there is no invoice that the payment can be settled against.</span></span> <span data-ttu-id="081af-105">Ces types de paiements sont également appelés dépôts de clients.</span><span class="sxs-lookup"><span data-stu-id="081af-105">These types of payments are also referred to as customer deposits.</span></span>

<span data-ttu-id="081af-106">Le processus de configuration et d'utilisation des acomptes clients comprend les étapes de base suivantes.</span><span class="sxs-lookup"><span data-stu-id="081af-106">The process of setting up and working with customer prepayments consists of the following basic steps.</span></span>

1. <span data-ttu-id="081af-107">Créez un profil de validation client pour les acomptes.</span><span class="sxs-lookup"><span data-stu-id="081af-107">Create a customer posting profile for prepayments.</span></span>
2. <span data-ttu-id="081af-108">Définissez le paramètre **Profil de validation avec N° document du journal des acomptes**.</span><span class="sxs-lookup"><span data-stu-id="081af-108">Set the **Posting profile with prepayment journal voucher** parameter.</span></span>
3. <span data-ttu-id="081af-109">Créez un journal de paiement client et sélectionnez la case à cocher **N° document du journal des acomptes** sur chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="081af-109">Create a customer payment journal, and select the **Prepayment journal voucher** check box on each line.</span></span>
4. <span data-ttu-id="081af-110">Valider le journal des paiements du client.</span><span class="sxs-lookup"><span data-stu-id="081af-110">Post the customer payment journal.</span></span>
5. <span data-ttu-id="081af-111">Une fois la facture générée, réglez l'acompte avec celle-ci en utilisant la page **Régler les transactions en cours**.</span><span class="sxs-lookup"><span data-stu-id="081af-111">After an invoice is generated, settle the prepayment with it by using the **Settle open transactions** page.</span></span>

## <a name="create-a-customer-posting-profile-for-prepayments"></a><span data-ttu-id="081af-112">Créer un profil de validation client pour les acomptes</span><span class="sxs-lookup"><span data-stu-id="081af-112">Create a customer posting profile for prepayments</span></span>

<span data-ttu-id="081af-113">En règle générale, lorsque vous acceptez des acomptes ou des dépôts de vos clients avant que des biens ou des services ne soient livrés, ou avant qu'une facture n'existe dans votre système, vous souhaiterez enregistrer la trésorerie comme un passif au lieu d'un actif dans votre plan comptable.</span><span class="sxs-lookup"><span data-stu-id="081af-113">Typically, when you accept prepayments or deposits from your customers before goods or services are delivered, or before an invoice exists in your system, you will want to record the cash as a liability instead of an asset in your chart of accounts.</span></span> <span data-ttu-id="081af-114">Cependant, les conditions d'enregistrement de ces montants dans votre compte général peuvent différer selon votre pays ou votre région.</span><span class="sxs-lookup"><span data-stu-id="081af-114">However, the requirements for recording these amounts in your general ledger might differ, depending on your country or region.</span></span> <span data-ttu-id="081af-115">Par conséquent, assurez-vous de consulter vos comptables sur les réglementations locales applicables.</span><span class="sxs-lookup"><span data-stu-id="081af-115">Therefore, be sure to consult your accountants about any local regulations that apply.</span></span>

<span data-ttu-id="081af-116">En général, le processus de création d'un profil de validation pouvant être utilisé pour les acomptes est le même que le processus de création d'autres profils de validation.</span><span class="sxs-lookup"><span data-stu-id="081af-116">In general, the process for creating a posting profile that can be used for prepayments is the same as the process for creating other posting profiles.</span></span> <span data-ttu-id="081af-117">La principale différence est le compte principal que vous sélectionnez dans le champ **Compte collectif**.</span><span class="sxs-lookup"><span data-stu-id="081af-117">The primary difference is the main account that you select in the **Summary account** field.</span></span> <span data-ttu-id="081af-118">Pour plus d'informations, voir [Profils de validation client](customer-posting-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="081af-118">For more information, see [Customer posting profiles](customer-posting-profiles.md).</span></span>

## <a name="define-parameters-for-customer-prepayments"></a><span data-ttu-id="081af-119">Définir les paramètres des acomptes clients</span><span class="sxs-lookup"><span data-stu-id="081af-119">Define parameters for customer prepayments</span></span>

<span data-ttu-id="081af-120">Vous devez prendre en compte deux principaux paramètres des comptes clients lorsque vous configurez le système pour les acomptes clients.</span><span class="sxs-lookup"><span data-stu-id="081af-120">There are two main Accounts receivable parameters that you must consider when you configure the system for customer prepayments.</span></span> <span data-ttu-id="081af-121">Procédez comme suit pour configurer les paramètres.</span><span class="sxs-lookup"><span data-stu-id="081af-121">Follow these steps to configure the parameters.</span></span>

1. <span data-ttu-id="081af-122">Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="081af-122">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="081af-123">Facultatif : Dans l'onglet **Comptabilité et taxe**, dans le raccourci **Paiement**, définissez l'option **Taxe sur N° document du journal des acomptes** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="081af-123">Optional: On the **Ledger and sales tax** tab, on the **Payment** FastTab, set the **Sales tax on prepayment journal voucher** option to **Yes**.</span></span>
3. <span data-ttu-id="081af-124">Dans le champ **Profil de validation avec N° document du journal des acomptes**, sélectionnez le profil de validation client à utiliser lorsque les acomptes clients sont validés.</span><span class="sxs-lookup"><span data-stu-id="081af-124">In the **Posting profile with prepayment journal voucher** field, select the customer posting profile to use when customer prepayments are posted.</span></span>
4. <span data-ttu-id="081af-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="081af-125">Close the page.</span></span>

## <a name="create-customer-prepayment-vouchers"></a><span data-ttu-id="081af-126">Créer des bons d'acompte client</span><span class="sxs-lookup"><span data-stu-id="081af-126">Create customer prepayment vouchers</span></span>

<span data-ttu-id="081af-127">Lorsque vous créez le journal des paiements client, pour chaque acompte, vous devez définir l'option **N° document du journal des acomptes** sur **Oui** sur la page **Journal de paiement client**.</span><span class="sxs-lookup"><span data-stu-id="081af-127">When you create the customer payment journal, for every prepayment, you must set the **Prepayment journal voucher** option to **Yes** on the **Customer payment journal** page.</span></span> <span data-ttu-id="081af-128">Suivez cette procédure pour créer un acompte client.</span><span class="sxs-lookup"><span data-stu-id="081af-128">Follow these steps to create a customer prepayment.</span></span>

1. <span data-ttu-id="081af-129">Accédez à **Comptabilité client \> Paiements \> Journal des paiements client**.</span><span class="sxs-lookup"><span data-stu-id="081af-129">Go to **Accounts receivable \> Payments \> Customer payment journal**.</span></span>
2. <span data-ttu-id="081af-130">Sélectionnez **Nouveau** pour créer un journal.</span><span class="sxs-lookup"><span data-stu-id="081af-130">Select **New** to create a journal.</span></span>
3. <span data-ttu-id="081af-131">Dans le champ **Nom**, sélectionnez le nom du journal à utiliser.</span><span class="sxs-lookup"><span data-stu-id="081af-131">In the **Name** field, select the journal name to use.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="081af-132">Si vous définissez l'option **Taxe sur N° document du journal des acomptes** sur **Oui** dans la procédure précédente, vous devez sélectionner un nom de journal où le paramètre **Le montant comprend les taxes** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="081af-132">If you set the **Sales tax on prepayment journal voucher** option to **Yes** in the previous procedure, you must select a journal name where the **Amount includes sales tax** parameter is selected.</span></span> 

4. <span data-ttu-id="081af-133">Facultatif : Dans le champ **Description**, entrez une description détaillée.</span><span class="sxs-lookup"><span data-stu-id="081af-133">Optional: In the **Description** field, enter a detailed description.</span></span>
5. <span data-ttu-id="081af-134">Sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="081af-134">Select **Lines**.</span></span>
6. <span data-ttu-id="081af-135">S'il n'y a pas de ligne vide, sélectionnez **Nouveau** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="081af-135">If a blank line doesn't exist, select **New** to create a line.</span></span>
7. <span data-ttu-id="081af-136">Dans le champ **Date**, entrez la date à laquelle l'acompte doit être enregistré.</span><span class="sxs-lookup"><span data-stu-id="081af-136">In the **Date** field, enter the date when the prepayment should be posted.</span></span>
8. <span data-ttu-id="081af-137">Dans le champ **Compte**, sélectionnez le client pour l'acompte suivant.</span><span class="sxs-lookup"><span data-stu-id="081af-137">In the **Account** field, select the customer for the prepayment.</span></span>
9. <span data-ttu-id="081af-138">Facultatif : Dans le champ **Description**, entrez une description détaillée de la transaction.</span><span class="sxs-lookup"><span data-stu-id="081af-138">Optional: In the **Description** field, enter a detailed description of the transaction.</span></span>
10. <span data-ttu-id="081af-139">Dans le champ **Crédit**, entrez le montant de l'acompte.</span><span class="sxs-lookup"><span data-stu-id="081af-139">In the **Credit** field, enter the amount of the prepayment.</span></span>
11. <span data-ttu-id="081af-140">Dans le champ **Compte de contrepartie**, sélectionnez le compte sur lequel compenser le paiement.</span><span class="sxs-lookup"><span data-stu-id="081af-140">In the **Offset account** field, select the account to offset the payment to.</span></span> <span data-ttu-id="081af-141">Par exemple, sélectionnez la banque ou le compte principal sur lequel valider le paiement.</span><span class="sxs-lookup"><span data-stu-id="081af-141">For example, select the bank or main account to post the payment to.</span></span>
12. <span data-ttu-id="081af-142">Dans le champ **Mode de paiement**, sélectionnez le mode de paiement du client.</span><span class="sxs-lookup"><span data-stu-id="081af-142">In the **Method of payment** field, select the customer's method of payment.</span></span>
13. <span data-ttu-id="081af-143">Dans l'onglet **Paiement**, définissez l'option **N° document du journal des acomptes** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="081af-143">On the **Payment** tab, set the **Prepayment journal voucher** option to **Yes**.</span></span>
14. <span data-ttu-id="081af-144">Répétez les étapes 7 à 13 pour chaque acompte supplémentaire qui doit être comptabilisé.</span><span class="sxs-lookup"><span data-stu-id="081af-144">Repeat steps 7 through 13 for each additional prepayment that must be posted.</span></span>
15. <span data-ttu-id="081af-145">Sélectionnez **Valider** pour finaliser le journal.</span><span class="sxs-lookup"><span data-stu-id="081af-145">Select **Post** to finalize the journal.</span></span>

## <a name="settle-prepayments-with-invoices"></a><span data-ttu-id="081af-146">Régler les factures avec les acomptes</span><span class="sxs-lookup"><span data-stu-id="081af-146">Settle prepayments with invoices</span></span>

<span data-ttu-id="081af-147">Vous pouvez utiliser l'espace de travail **Paiements clients** pour trouver et régler facilement les paiements qui n'ont pas été entièrement réglés.</span><span class="sxs-lookup"><span data-stu-id="081af-147">You can use the **Customer payments** workspace to easily find and settle payments that haven't been fully settled.</span></span>

1. <span data-ttu-id="081af-148">Dans le tableau de bord **Accueil**, sélectionnez la mosaïque **Paiements clients**.</span><span class="sxs-lookup"><span data-stu-id="081af-148">On the **Home** dashboard, select the **Customer payments** tile.</span></span>
2. <span data-ttu-id="081af-149">Dans la section **Transactions clients**, dans l'onglet **Paiements non réglés**, recherchez et sélectionnez le paiement à régler.</span><span class="sxs-lookup"><span data-stu-id="081af-149">In the **Customer transactions** section, on the **Payments not settled** tab, search for and select the payment to settle.</span></span>
3. <span data-ttu-id="081af-150">Sélectionnez **Régler des transactions**.</span><span class="sxs-lookup"><span data-stu-id="081af-150">Select **Settle transactions**.</span></span>
4. <span data-ttu-id="081af-151">Cochez la case **Marquer** pour la facture et le paiement qui sera réglé.</span><span class="sxs-lookup"><span data-stu-id="081af-151">Select the **Mark** check box for the invoice and the payment that will be settled.</span></span>
5. <span data-ttu-id="081af-152">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="081af-152">Select **Post**.</span></span>

<span data-ttu-id="081af-153">Pour plus d'informations sur le règlement des transactions en cours, voir [Aperçu du règlement](/cash-bank-management/settlement-overview.md).</span><span class="sxs-lookup"><span data-stu-id="081af-153">For more information about how to settle open transactions, see [Settlement overview](/cash-bank-management/settlement-overview.md).</span></span>
