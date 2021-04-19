---
title: Créer un mandat de débit direct pour un client
description: Ce guide de tâche montre comment créer un mandat de débit direct et l’utiliser dans une facture.
author: ShivamPandey-msft
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3bbf3703941255dfd82b8fb501ba8a9d1f3a2ec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835074"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="df08d-103">Créer un mandat de débit direct pour un client</span><span class="sxs-lookup"><span data-stu-id="df08d-103">Create a direct debit mandate for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="df08d-104">Ce guide de tâche montre comment créer un mandat de débit direct et l’utiliser dans une facture.</span><span class="sxs-lookup"><span data-stu-id="df08d-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="df08d-105">Créer un compte bancaire</span><span class="sxs-lookup"><span data-stu-id="df08d-105">Create a bank account</span></span>
1. <span data-ttu-id="df08d-106">Dans le **volet de navigation**, allez dans **Modules > Comptabilité client > Clients > Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="df08d-106">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="df08d-107">Sélectionnez un enregistrement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="df08d-107">In the list, select a record.</span></span> <span data-ttu-id="df08d-108">Par exemple, sélectionnez US-001.</span><span class="sxs-lookup"><span data-stu-id="df08d-108">For example, select US-001</span></span>
3. <span data-ttu-id="df08d-109">Cliquez sur **Client** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="df08d-109">On the Action Pane, click **Customer**.</span></span>
4. <span data-ttu-id="df08d-110">Cliquez sur **Comptes bancaires**.</span><span class="sxs-lookup"><span data-stu-id="df08d-110">Click **Bank accounts**.</span></span>
5. <span data-ttu-id="df08d-111">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="df08d-111">Click **New**.</span></span>
6. <span data-ttu-id="df08d-112">Tapez une valeur dans le champ **Compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="df08d-112">In the **Bank account** field, type a value.</span></span>
7. <span data-ttu-id="df08d-113">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="df08d-113">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="df08d-114">Tapez une valeur dans le champ **IBAN**.</span><span class="sxs-lookup"><span data-stu-id="df08d-114">In the **IBAN** field, type a value.</span></span>
9. <span data-ttu-id="df08d-115">Tapez une valeur dans le champ **Devise**.</span><span class="sxs-lookup"><span data-stu-id="df08d-115">In the **Currency** field, type a value.</span></span>
10. <span data-ttu-id="df08d-116">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="df08d-116">Click **Save**.</span></span>
11. <span data-ttu-id="df08d-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="df08d-117">Close the page.</span></span>
12. <span data-ttu-id="df08d-118">Dans le **Volet de navigation**, allez dans **Modules > Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires**.</span><span class="sxs-lookup"><span data-stu-id="df08d-118">In the **Navigation pane**, go to **Modules > Cash and bank management > Bank accounts > Bank accounts**.</span></span>
13. <span data-ttu-id="df08d-119">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="df08d-119">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="df08d-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="df08d-120">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="df08d-121">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="df08d-121">Click **Edit**.</span></span>
16. <span data-ttu-id="df08d-122">Développez le raccourci **Identification supplémentaire**.</span><span class="sxs-lookup"><span data-stu-id="df08d-122">Expand the **Additional identification** fastTab.</span></span>
17. <span data-ttu-id="df08d-123">Tapez une valeur dans le champ **ID débit direct**.</span><span class="sxs-lookup"><span data-stu-id="df08d-123">In the **Direct debit ID** field, type a value.</span></span>
18. <span data-ttu-id="df08d-124">Tapez une valeur dans le champ **IBAN**.</span><span class="sxs-lookup"><span data-stu-id="df08d-124">In the **IBAN** field, type a value.</span></span>
19. <span data-ttu-id="df08d-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="df08d-125">Close the page.</span></span>
20. <span data-ttu-id="df08d-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="df08d-126">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="df08d-127">Définir le mode de paiement électronique</span><span class="sxs-lookup"><span data-stu-id="df08d-127">Define the electronic payment method</span></span>
1. <span data-ttu-id="df08d-128">Dans le **Volet de navigation**, allez dans **Modules > Comptabilité client > Paramétrage des paiements > Modes de paiement**.</span><span class="sxs-lookup"><span data-stu-id="df08d-128">In the **Navigation pane**, go to **Modules > Accounts receivable > Payments setup > Methods of payment**.</span></span>
2. <span data-ttu-id="df08d-129">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="df08d-129">Click **New**.</span></span>
3. <span data-ttu-id="df08d-130">Tapez une valeur dans le champ **Mode de paiement**.</span><span class="sxs-lookup"><span data-stu-id="df08d-130">In the **Method of payment** field, type a value.</span></span>
4. <span data-ttu-id="df08d-131">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="df08d-131">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="df08d-132">Entrez « Paiement électronique » dans le champ **Type de paiement**.</span><span class="sxs-lookup"><span data-stu-id="df08d-132">In the **Payment type** field, enter 'Electronic payment'.</span></span> <span data-ttu-id="df08d-133">Le type de paiement doit être électronique pour un mode de paiement pour les mandats de débit direct.</span><span class="sxs-lookup"><span data-stu-id="df08d-133">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="df08d-134">Sélectionnez Oui dans le champ **Demander un mandat**.</span><span class="sxs-lookup"><span data-stu-id="df08d-134">Select Yes in the **Require mandate** field.</span></span>
7. <span data-ttu-id="df08d-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="df08d-135">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="df08d-136">Ajoutez un mandat de débit direct à un client.</span><span class="sxs-lookup"><span data-stu-id="df08d-136">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="df08d-137">Dans le **volet de navigation**, allez dans **Modules > Comptabilité client > Clients > Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="df08d-137">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="df08d-138">Sélectionnez un enregistrement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="df08d-138">In the list, select a record.</span></span> <span data-ttu-id="df08d-139">Par exemple, sélectionnez US-001.</span><span class="sxs-lookup"><span data-stu-id="df08d-139">For example, select US-001</span></span>
3. <span data-ttu-id="df08d-140">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="df08d-140">Click **Edit**.</span></span>
4. <span data-ttu-id="df08d-141">Développez le raccourci **Valeurs par défaut de paiement**.</span><span class="sxs-lookup"><span data-stu-id="df08d-141">Expand the **Payment defaults** fastTab.</span></span>
5. <span data-ttu-id="df08d-142">Dans le champ **Mode de paiement**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="df08d-142">In the **Method of payment** field, enter or select a value.</span></span>
6. <span data-ttu-id="df08d-143">Développez le raccourci **Valeurs par défaut de paiement**.</span><span class="sxs-lookup"><span data-stu-id="df08d-143">Expand the **Payment defaults** fastTab.</span></span>
7. <span data-ttu-id="df08d-144">Développez le raccourci **Mandats de débit direct**.</span><span class="sxs-lookup"><span data-stu-id="df08d-144">Expand the **Direct debit mandates** fastTab.</span></span>
8. <span data-ttu-id="df08d-145">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="df08d-145">Click **Add**.</span></span>
9. <span data-ttu-id="df08d-146">Dans le champ **Compte en banque**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="df08d-146">In the **Bank account** field, enter or select a value.</span></span>
10. <span data-ttu-id="df08d-147">Entrez ou sélectionnez une valeur dans le champ **Compte bancaire du créditeur**.</span><span class="sxs-lookup"><span data-stu-id="df08d-147">In the **Creditor bank account** field, enter or select a value.</span></span>
11. <span data-ttu-id="df08d-148">Entrez le nombre de paiements que vous prévoyez de traiter pour ce mandat dans le champ **Fréquence de paiement**.</span><span class="sxs-lookup"><span data-stu-id="df08d-148">In the **Payment frequency** field, enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="df08d-149">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="df08d-149">Click **OK**.</span></span>
13. <span data-ttu-id="df08d-150">Cliquez sur **Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="df08d-150">Click **Print**.</span></span>
14. <span data-ttu-id="df08d-151">Cliquez sur **État des mandats**.</span><span class="sxs-lookup"><span data-stu-id="df08d-151">Click **Mandate report**.</span></span>
15. <span data-ttu-id="df08d-152">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="df08d-152">Close the page.</span></span>
16. <span data-ttu-id="df08d-153">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="df08d-153">Click **Edit**.</span></span>
17. <span data-ttu-id="df08d-154">Entrez une date dans le champ **Date de signature**.</span><span class="sxs-lookup"><span data-stu-id="df08d-154">In the **Signature date** field, enter a date.</span></span>
18. <span data-ttu-id="df08d-155">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="df08d-155">Click **Yes**.</span></span>
19. <span data-ttu-id="df08d-156">Entrez le lieu de signature du mandat.</span><span class="sxs-lookup"><span data-stu-id="df08d-156">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="df08d-157">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="df08d-157">Click **OK**.</span></span>
21. <span data-ttu-id="df08d-158">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="df08d-158">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="df08d-159">Créez une facture financière avec mandat.</span><span class="sxs-lookup"><span data-stu-id="df08d-159">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="df08d-160">Dans le **volet de navigation**, allez dans **Modules > Comptabilité client > Factures > Toutes factures financières**.</span><span class="sxs-lookup"><span data-stu-id="df08d-160">In the **Navigation pane**, go to **Modules > Accounts receivable > Invoices > All free text invoices**.</span></span>
2. <span data-ttu-id="df08d-161">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="df08d-161">Click **New**.</span></span>
3. <span data-ttu-id="df08d-162">Sélectionnez le client pour lequel vous avez ajouté le mandat.</span><span class="sxs-lookup"><span data-stu-id="df08d-162">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="df08d-163">Entrez ou sélectionnez une valeur dans le champ **ID mandat de débit direct**.</span><span class="sxs-lookup"><span data-stu-id="df08d-163">In the **Direct debit mandate ID** field, enter or select a value.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]