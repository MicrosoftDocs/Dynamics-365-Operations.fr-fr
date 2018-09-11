--- 
title: "Créer un mandat de débit direct pour un client"
description: "Ce guide de tâche montre comment créer un mandat de débit direct et l'utiliser dans une facture."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 4b3d9e10e176879a6c474ec0bff513c6008bc3a9
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="7dc2a-103">Créer un mandat de débit direct pour un client</span><span class="sxs-lookup"><span data-stu-id="7dc2a-103">Create a direct debit mandate for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7dc2a-104">Ce guide de tâche montre comment créer un mandat de débit direct et l'utiliser dans une facture.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="7dc2a-105">Créer un compte bancaire</span><span class="sxs-lookup"><span data-stu-id="7dc2a-105">Create a bank account</span></span>
1. <span data-ttu-id="7dc2a-106">Accédez à Comptabilité client > Clients > Tous les clients.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="7dc2a-107">Par exemple, sélectionnez US-001.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-107">For example, select US-001</span></span>
3. <span data-ttu-id="7dc2a-108">Cliquez sur Client dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-108">On the Action Pane, click Customer.</span></span>
4. <span data-ttu-id="7dc2a-109">Cliquez sur Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="7dc2a-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-110">Click New.</span></span>
6. <span data-ttu-id="7dc2a-111">Tapez une valeur dans le champ Compte en banque.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-111">In the Bank account field, type a value.</span></span>
7. <span data-ttu-id="7dc2a-112">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-112">In the Name field, type a value.</span></span>
8. <span data-ttu-id="7dc2a-113">Tapez une valeur dans le champ IBAN.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-113">In the IBAN field, type a value.</span></span>
9. <span data-ttu-id="7dc2a-114">Tapez une valeur dans le champ Devise.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-114">In the Currency field, type a value.</span></span>
10. <span data-ttu-id="7dc2a-115">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-115">Click Save.</span></span>
11. <span data-ttu-id="7dc2a-116">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-116">Close the page.</span></span>
12. <span data-ttu-id="7dc2a-117">Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-117">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
13. <span data-ttu-id="7dc2a-118">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-118">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="7dc2a-119">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-119">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="7dc2a-120">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-120">Click Edit.</span></span>
16. <span data-ttu-id="7dc2a-121">Développez la section Identification supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-121">Expand the Additional identification section.</span></span>
17. <span data-ttu-id="7dc2a-122">Dans le champ ID débit direct, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-122">In the Direct debit ID field, type a value.</span></span>
18. <span data-ttu-id="7dc2a-123">Tapez une valeur dans le champ IBAN.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-123">In the IBAN field, type a value.</span></span>
19. <span data-ttu-id="7dc2a-124">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-124">Close the page.</span></span>
20. <span data-ttu-id="7dc2a-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-125">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="7dc2a-126">Définir le mode de paiement électronique</span><span class="sxs-lookup"><span data-stu-id="7dc2a-126">Define the electronic payment method</span></span>
1. <span data-ttu-id="7dc2a-127">Accédez à Comptabilité client > Paramétrage des paiements > Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-127">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="7dc2a-128">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-128">Click New.</span></span>
3. <span data-ttu-id="7dc2a-129">Tapez une valeur dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-129">In the Method of payment field, type a value.</span></span>
4. <span data-ttu-id="7dc2a-130">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7dc2a-131">Le type de paiement doit être électronique pour un mode de paiement pour les mandats de débit direct.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-131">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="7dc2a-132">Sélectionnez Oui dans le champ Demander un mandat.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-132">Select Yes in the Require mandate field.</span></span>
7. <span data-ttu-id="7dc2a-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-133">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="7dc2a-134">Ajoutez un mandat de débit direct à un client.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-134">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="7dc2a-135">Accédez à Comptabilité client > Clients > Tous les clients.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-135">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="7dc2a-136">Par exemple, sélectionnez US-001.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-136">For example, select US-001</span></span>
3. <span data-ttu-id="7dc2a-137">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-137">Click Edit.</span></span>
4. <span data-ttu-id="7dc2a-138">Développez la section Valeurs par défaut du paiement.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-138">Expand the Payment defaults section.</span></span>
5. <span data-ttu-id="7dc2a-139">Entrez ou sélectionnez une valeur dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-139">In the Method of payment field, enter or select a value.</span></span>
6. <span data-ttu-id="7dc2a-140">Développez la section Valeurs par défaut du paiement.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-140">Expand the Payment defaults section.</span></span>
7. <span data-ttu-id="7dc2a-141">Développez la section Mandats de débit direct.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-141">Expand the Direct debit mandates section.</span></span>
8. <span data-ttu-id="7dc2a-142">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-142">Click Add.</span></span>
9. <span data-ttu-id="7dc2a-143">Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-143">In the Bank account field, enter or select a value.</span></span>
10. <span data-ttu-id="7dc2a-144">Dans le champ Compte bancaire du créditeur, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-144">In the Creditor bank account field, enter or select a value.</span></span>
11. <span data-ttu-id="7dc2a-145">Entrez le nombre de paiements que vous prévoyez de traiter pour ce mandat.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-145">Enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="7dc2a-146">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-146">Click OK.</span></span>
13. <span data-ttu-id="7dc2a-147">Cliquez sur Imprimer.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-147">Click Print.</span></span>
14. <span data-ttu-id="7dc2a-148">Cliquez sur État des mandats.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-148">Click Mandate report.</span></span>
15. <span data-ttu-id="7dc2a-149">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-149">Close the page.</span></span>
16. <span data-ttu-id="7dc2a-150">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-150">Click Edit.</span></span>
17. <span data-ttu-id="7dc2a-151">Entrez une date dans le champ Date de signature.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-151">In the Signature date field, enter a date.</span></span>
18. <span data-ttu-id="7dc2a-152">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-152">Click Yes.</span></span>
19. <span data-ttu-id="7dc2a-153">Entrez le lieu de signature du mandat.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-153">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="7dc2a-154">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-154">Click OK.</span></span>
21. <span data-ttu-id="7dc2a-155">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-155">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="7dc2a-156">Créez une facture financière avec mandat.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-156">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="7dc2a-157">Accédez à Comptabilité client > Factures > Toutes factures financières.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-157">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="7dc2a-158">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-158">Click New.</span></span>
3. <span data-ttu-id="7dc2a-159">Sélectionnez le client pour lequel vous avez ajouté le mandat.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-159">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="7dc2a-160">Dans le champ ID mandat de débit direct, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7dc2a-160">In the Direct debit mandate ID field, enter or select a value.</span></span>


