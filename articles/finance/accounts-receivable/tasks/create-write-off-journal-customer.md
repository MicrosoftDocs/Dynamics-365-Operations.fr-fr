---
title: Créer un journal d'annulation pour un client
description: Ce guide de tâche vous indique comment définir les paramètres pour les annulations, puis pour les transactions d'annulation à partir de la page Recouvrement, de la page Factures client en cours et de la page Client.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2422f0a9d168daa76d105099c8b7455c97f92125
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188830"
---
# <a name="create-a-write-off-journal-for-a-customer"></a><span data-ttu-id="fda78-103">Créer un journal d'annulation pour un client</span><span class="sxs-lookup"><span data-stu-id="fda78-103">Create a write-off journal for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fda78-104">Ce guide de tâche vous indique comment définir les paramètres pour les annulations, puis pour les transactions d'annulation à partir de la page Recouvrement, de la page Factures client en cours et de la page Client.</span><span class="sxs-lookup"><span data-stu-id="fda78-104">This task guide will show you how to set up the parameters for write-offs and then write off transactions from the Collections page, the Open customer invoices page, and the Customer page.</span></span> <span data-ttu-id="fda78-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="fda78-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-the-write-off-parameters"></a><span data-ttu-id="fda78-106">Définir les paramètres d'annulation</span><span class="sxs-lookup"><span data-stu-id="fda78-106">Set up the write off parameters</span></span>
1. <span data-ttu-id="fda78-107">Allez dans **Volet de navigation > Modules > Crédit et recouvrements > Paramétrage > Paramètres de la comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="fda78-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="fda78-108">Cliquez sur l'onglet **Recouvrement**.</span><span class="sxs-lookup"><span data-stu-id="fda78-108">Click the **Collections** tab.</span></span>
3. <span data-ttu-id="fda78-109">Développez ou réduisez la section **Annulation**.</span><span class="sxs-lookup"><span data-stu-id="fda78-109">Expand or collapse the **Write-off** section.</span></span>
    - <span data-ttu-id="fda78-110">Le **journal d'annulation** est le journal des opérations diverses qui va contenir les transactions d'annulation que vous créez.</span><span class="sxs-lookup"><span data-stu-id="fda78-110">The **Write-off journal** is the general journal that will hold the write-off transactions that you create.</span></span>  
    - <span data-ttu-id="fda78-111">Vous pouvez associer un code motif à chaque annulation.</span><span class="sxs-lookup"><span data-stu-id="fda78-111">You can attach a reason code to every write-off.</span></span> <span data-ttu-id="fda78-112">Vous pouvez remplacer ce paramétrage par défaut au moment de l'annulation.</span><span class="sxs-lookup"><span data-stu-id="fda78-112">You can override this default at the time of the write-off.</span></span>  
    - <span data-ttu-id="fda78-113">Définissez **Taxe distincte** sur Oui si vous souhaitez fractionner la taxe de la transaction d'origine dans l'annulation.</span><span class="sxs-lookup"><span data-stu-id="fda78-113">Set the **Separate sales tax** to Yes if you want to separate the sales tax from the original transaction in the write-off.</span></span>  
4. <span data-ttu-id="fda78-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fda78-114">Close the page.</span></span>
5. <span data-ttu-id="fda78-115">Accédez à **Crédit et relances > Paramétrage > Profils de validation client**.</span><span class="sxs-lookup"><span data-stu-id="fda78-115">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span> <span data-ttu-id="fda78-116">Le compte d'annulation est utilisé comme compte de dépenses ou ajustement de réserve dans le journal des opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="fda78-116">The write-off account will be used as the expense account or reserve adjustment in the general journal.</span></span>
6. <span data-ttu-id="fda78-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fda78-117">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a><span data-ttu-id="fda78-118">Annuler le solde d'un client à partir de la page des balances âgées</span><span class="sxs-lookup"><span data-stu-id="fda78-118">Write off a customer balance from the aged balances page</span></span>
1. <span data-ttu-id="fda78-119">Accédez à **Crédit et relances > Collections > Soldes chronologiques**.</span><span class="sxs-lookup"><span data-stu-id="fda78-119">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="fda78-120">Marquez la ligne pour le client à annuler.</span><span class="sxs-lookup"><span data-stu-id="fda78-120">Mark the row for the customer that you want to write off.</span></span> <span data-ttu-id="fda78-121">Par exemple, marquez la ligne contenant la société Birch.</span><span class="sxs-lookup"><span data-stu-id="fda78-121">For example, mark the line with Birch Company on it.</span></span>
3. <span data-ttu-id="fda78-122">Cliquez sur **Collecter** dans le volet **Actions**.</span><span class="sxs-lookup"><span data-stu-id="fda78-122">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="fda78-123">Cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="fda78-123">Click **Write off**.</span></span>
5. <span data-ttu-id="fda78-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fda78-124">Click **OK**.</span></span>
6. <span data-ttu-id="fda78-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fda78-125">Close the page.</span></span>
7. <span data-ttu-id="fda78-126">Allez dans le **Volet de navigation > Modules > Comptabilité > Entrées de journal > Journaux des opérations diverses**.</span><span class="sxs-lookup"><span data-stu-id="fda78-126">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
8. <span data-ttu-id="fda78-127">Sélectionnez le numéro de lot du journal pour le journal contenant votre annulation.</span><span class="sxs-lookup"><span data-stu-id="fda78-127">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="fda78-128">Une ligne est créée pour contrepasser le solde du client.</span><span class="sxs-lookup"><span data-stu-id="fda78-128">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="fda78-129">Une ou plusieurs lignes sont créées pour valider l'annulation du compte d'annulation.</span><span class="sxs-lookup"><span data-stu-id="fda78-129">One or more lines are created to post the write-off to the write-off account.</span></span>  
9. <span data-ttu-id="fda78-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fda78-130">Close the page.</span></span>
10. <span data-ttu-id="fda78-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fda78-131">Close the page.</span></span>

## <a name="write-off-transactions-from-the-collections-form"></a><span data-ttu-id="fda78-132">Annuler des transactions à partir de l'écran de recouvrement.</span><span class="sxs-lookup"><span data-stu-id="fda78-132">Write off transactions from the collections form.</span></span>
1. <span data-ttu-id="fda78-133">Accédez à **Crédit et relances > Collections > Soldes chronologiques**.</span><span class="sxs-lookup"><span data-stu-id="fda78-133">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="fda78-134">Sélectionnez le nom du client ayant les transactions que vous souhaitez annuler.</span><span class="sxs-lookup"><span data-stu-id="fda78-134">Select the name of the customer that has the transactions that you want to write off.</span></span> <span data-ttu-id="fda78-135">Sélectionnez par exemple Cave Wholesales (US-004).</span><span class="sxs-lookup"><span data-stu-id="fda78-135">For example, select Cave Wholesales (US-004).</span></span>
3. <span data-ttu-id="fda78-136">Marquez la ligne de la première transaction.</span><span class="sxs-lookup"><span data-stu-id="fda78-136">Mark the row for the first transaction.</span></span>
4. <span data-ttu-id="fda78-137">Marquez la ligne de la deuxième transaction.</span><span class="sxs-lookup"><span data-stu-id="fda78-137">Mark the row for the second transaction.</span></span>
5. <span data-ttu-id="fda78-138">Cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="fda78-138">Click **Write off**.</span></span>
6. <span data-ttu-id="fda78-139">Dans le champ **Commentaire du motif**, entrez « Créances irrécouvrables ».</span><span class="sxs-lookup"><span data-stu-id="fda78-139">In the **Reason comment** field, type 'Bad debts'.</span></span>
7. <span data-ttu-id="fda78-140">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fda78-140">Click **OK**.</span></span>
8. <span data-ttu-id="fda78-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fda78-141">Close the page.</span></span>
9. <span data-ttu-id="fda78-142">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fda78-142">Close the page.</span></span>
10. <span data-ttu-id="fda78-143">Accédez à **Comptabilité > Entrées de journal > Journaux des opérations diverses.**.</span><span class="sxs-lookup"><span data-stu-id="fda78-143">Go to **General ledger > Journal entries > General journals**.</span></span>
11. <span data-ttu-id="fda78-144">Sélectionnez le numéro de lot du journal pour le journal contenant votre annulation.</span><span class="sxs-lookup"><span data-stu-id="fda78-144">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="fda78-145">Une ligne est créée pour contrepasser le solde du client.</span><span class="sxs-lookup"><span data-stu-id="fda78-145">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="fda78-146">Une ou plusieurs lignes sont créées pour valider l'annulation du compte d'annulation.</span><span class="sxs-lookup"><span data-stu-id="fda78-146">One or more lines are created to post the write-off to the write-off account.</span></span>  
12. <span data-ttu-id="fda78-147">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fda78-147">Close the page.</span></span>
13. <span data-ttu-id="fda78-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fda78-148">Close the page.</span></span>

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a><span data-ttu-id="fda78-149">Annuler une facture à partir de la page Ouvrir les factures des clients</span><span class="sxs-lookup"><span data-stu-id="fda78-149">Write off an invoice from the Open customers invoices page</span></span>
1. <span data-ttu-id="fda78-150">Accédez à **Volet de navigation > Modules > Comptabilité client > Factures > Factures client en cours**.</span><span class="sxs-lookup"><span data-stu-id="fda78-150">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Open customer invoices**.</span></span>
2. <span data-ttu-id="fda78-151">Marquez le ligne d'une facture.</span><span class="sxs-lookup"><span data-stu-id="fda78-151">Mark the line for an invoice.</span></span> <span data-ttu-id="fda78-152">Par exemple, marquez la ligne pour CIV-000667.</span><span class="sxs-lookup"><span data-stu-id="fda78-152">For example, mark the line for CIV-000667.</span></span>
3. <span data-ttu-id="fda78-153">Cliquez sur **Facture** dans le volet **Actions**.</span><span class="sxs-lookup"><span data-stu-id="fda78-153">On the **Action Pane**, click **Invoice**.</span></span>
4. <span data-ttu-id="fda78-154">Cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="fda78-154">Click **Write off**.</span></span>
5. <span data-ttu-id="fda78-155">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fda78-155">Click **OK**.</span></span>
6. <span data-ttu-id="fda78-156">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fda78-156">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-customer-page"></a><span data-ttu-id="fda78-157">Annuler le solde d'un client à partir de la page client</span><span class="sxs-lookup"><span data-stu-id="fda78-157">Write off a customer balance from the customer page</span></span>
1. <span data-ttu-id="fda78-158">Allez dans **Comptabilité client > Clients > Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="fda78-158">Go to **Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="fda78-159">Permet de sélectionner un compte client.</span><span class="sxs-lookup"><span data-stu-id="fda78-159">Select a customer account.</span></span> <span data-ttu-id="fda78-160">Par exemple, sélectionnez US-001 (Contoso Retail San Diego).</span><span class="sxs-lookup"><span data-stu-id="fda78-160">For example, select US-001 (Contoso Retail San Diego).</span></span>
3. <span data-ttu-id="fda78-161">Cliquez sur **Collecter** dans le volet **Actions**.</span><span class="sxs-lookup"><span data-stu-id="fda78-161">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="fda78-162">Cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="fda78-162">Click **Write off**.</span></span>
5. <span data-ttu-id="fda78-163">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fda78-163">Click **OK**.</span></span>
6. <span data-ttu-id="fda78-164">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fda78-164">Close the page.</span></span>

