---
title: "Relevé bancaire CODA"
description: "Cette rubrique contient des informations sur CODA, qui est un format d'état utilisé par le système d'opérations bancaires électroniques belge."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, BankCodaAccountStatement, BankCodaAccountStatementLines, BankCodaParameters, BankCodaTrans, BankCodaTransCategory, BankCodaTransDefTable, BankCodaTransFamily
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 262534
ms.search.region: Belgium
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: e7fe8a818be231ef54b1d2ffdb65b0269aaf027c
ms.contentlocale: fr-fr
ms.lasthandoff: 06/29/2017


---

# <a name="coda-bank-statement"></a><span data-ttu-id="fd5d1-103">Relevé bancaire CODA</span><span class="sxs-lookup"><span data-stu-id="fd5d1-103">CODA bank statement</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="fd5d1-104">Cette rubrique contient des informations sur CODA, qui est un format d'état utilisé par le système d'opérations bancaires électroniques belge.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-104">This topic includes information about CODA, which is a report format used in the Belgian electronic banking system.</span></span> 

<span data-ttu-id="fd5d1-105">Pour les importations de relevés bancaires belges, vous utiliserez le format de fichier CODA.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-105">For Belgian bank statement imports, you'll use the CODA file format.</span></span> <span data-ttu-id="fd5d1-106">Cette fonctionnalité permet de vérifier les soldes d'ouverture et de clôture d'un compte bancaire de société, et de rapprocher des transactions importées basées sur des règles de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-106">This feature lets you verify company bank account opening and ending balances, and reconcile imported transactions based on reconciliation rules.</span></span>

## <a name="import-transactions-from-a-bank-statement"></a><span data-ttu-id="fd5d1-107">Importer des transactions à partir d'un relevé bancaire</span><span class="sxs-lookup"><span data-stu-id="fd5d1-107">Import transactions from a bank statement</span></span>
<span data-ttu-id="fd5d1-108">Pour importer un fichier de relevé bancaire pour un compte bancaire, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-108">To import a bank statement file for a bank account, complete the following steps.</span></span> <span data-ttu-id="fd5d1-109">**Remarque** : avant d'importer un fichier de relevé bancaire, vous devez avoir déjà effectué les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fd5d1-109">**Note**: Before you import a bank statement file, you must have already completed the following:</span></span>

-   <span data-ttu-id="fd5d1-110">Importer les configurations CODA à partir de Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="fd5d1-110">Import the CODA configurations from Lifecycle Services (LCS).</span></span> <span data-ttu-id="fd5d1-111">Pour plus d'informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)</span><span class="sxs-lookup"><span data-stu-id="fd5d1-111">For more information, see [Download Electronic reporting configurations from Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).</span></span>
-   <span data-ttu-id="fd5d1-112">Sélectionner la configuration CODA importée dans la page **Paramètres CODA**.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-112">Select the imported CODA configuration on the **CODA parameters** page.</span></span>

1.  <span data-ttu-id="fd5d1-113">Accédez à la page **Comptes bancaires**.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-113">Go to the **Bank accounts** page.</span></span>
2.  <span data-ttu-id="fd5d1-114">Cliquez sur **Rapprocher** &gt; **CODA**.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-114">Click **Reconcile** &gt; **CODA**.</span></span>
3.  <span data-ttu-id="fd5d1-115">Cliquez sur **CODA** &gt; **Importer depuis le fichier**, puis sélectionnez le chemin d'accès au fichier de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-115">Click **CODA** &gt; **Import from file**, and then select the path to the bank statement file.</span></span>

<span data-ttu-id="fd5d1-116">Après avoir importé les transactions, vous pouvez effectuer les actions suivantes dans la page **Relevé bancaire**.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-116">After you import transactions, you can do the following on the **Bank statement** page.</span></span>

-   <span data-ttu-id="fd5d1-117">Vérifier les soldes d'ouverture et de clôture.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-117">Verify the opening and ending balances.</span></span>
-   <span data-ttu-id="fd5d1-118">Afficher les transactions importées en tant qu'état de relevé bancaire que vous pouvez imprimer.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-118">View the imported transactions as a bank statement report that you can print.</span></span>
-   <span data-ttu-id="fd5d1-119">Afficher les transactions importées contenant des lignes supplémentaires, telles que les lignes dont le type de compte est « Aucun ».</span><span class="sxs-lookup"><span data-stu-id="fd5d1-119">View imported transactions with additional lines, such as lines with an Account type of "None".</span></span> <span data-ttu-id="fd5d1-120">Cliquez sur **CODA &gt; Détails**.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-120">Click **CODA &gt; Details**.</span></span>

## <a name="process-imported-bank-statement-transactions"></a><span data-ttu-id="fd5d1-121">Traiter les transactions de relevé bancaire importées</span><span class="sxs-lookup"><span data-stu-id="fd5d1-121">Process imported bank statement transactions</span></span>
<span data-ttu-id="fd5d1-122">Effectuez les étapes suivantes pour traiter les transactions de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-122">Complete the following steps to process the bank statement transactions.</span></span>

1.  <span data-ttu-id="fd5d1-123">Traitez les lignes de détail (**CODA** &gt; **Traiter les lignes de détails**).</span><span class="sxs-lookup"><span data-stu-id="fd5d1-123">Process details lines (**CODA** &gt; **Process detail lines**).</span></span> <span data-ttu-id="fd5d1-124">Démarrez la mise en correspondance automatique en fonction des **Définitions CODA**.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-124">Start automatic matching based on **CODA definitions**.</span></span> <span data-ttu-id="fd5d1-125">Ces règles déterminent le compte général, client ou fournisseur qui doit être utilisé pour cette transaction.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-125">These rules determine which ledger, customer, or vendor account should be used for this transaction.</span></span> <span data-ttu-id="fd5d1-126">La comparaison est basée sur le code du groupe de transactions, le code de transaction et le code de catégorie de transaction spécifiés dans le fichier CODA pour chaque transaction.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-126">Comparison is based on which Transaction group code, Transaction code, and Transaction category code are specified in CODA file for each transaction.</span></span>
2.  <span data-ttu-id="fd5d1-127">Les transactions avec un type de compte client et fournisseur peuvent être mises en correspondance avec les factures.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-127">Transactions with a customer and vendor account type can be matched with the invoices.</span></span> <span data-ttu-id="fd5d1-128">Si nécessaire, les transactions importées peuvent être modifiées manuellement à tout moment après le traitement, avant de les transférer vers la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-128">If necessary, imported transactions can be manually changed at any time after processing, before transferring to the ledger.</span></span>
3.  <span data-ttu-id="fd5d1-129">Si des transactions comportent des erreurs (en général, si aucune règle n'est paramétrée), celles-ci peuvent être mentionnées dans le compte général spécial, spécifié sur la page **Paramètres CODA **(** CODA** &gt; **Effacer les erreurs**).</span><span class="sxs-lookup"><span data-stu-id="fd5d1-129">If there are any transactions with errors (generally, if there are no rules set up), these can be referred to the special ledger account, specified on the **CODA parameters **page (** CODA** &gt; **Clear errors**).</span></span>
4.  <span data-ttu-id="fd5d1-130">Une fois que toutes les transactions du relevé bancaire sont réglées, elles sont prêtes à être transférées vers le journal de comptabilité (**CODA** &gt;**Transfert vers la comptabilité**).</span><span class="sxs-lookup"><span data-stu-id="fd5d1-130">After all transactions in the bank statement are settled, they are ready to be transferred to the general ledger journal (**CODA** &gt;**Transfer to ledger**).</span></span> <span data-ttu-id="fd5d1-131">Les paramètres du journal doivent être spécifiés pour le compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-131">Journal settings should be specified for the bank account.</span></span> <span data-ttu-id="fd5d1-132">Les journaux peuvent être ouverts sur la page **Comptes bancaires** pour l'enregistrement sélectionné en cliquant sur **Paramétrage** &gt; **Journal CODA**.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-132">Journals can be opened on the **Bank accounts **page for the selected record by clicking **Set up** &gt; **CODA journal**.</span></span>

<span data-ttu-id="fd5d1-133">Une fois que le traitement des transactions de relevé bancaire est terminé, un journal de comptabilité est créé et prêt à être validé.</span><span class="sxs-lookup"><span data-stu-id="fd5d1-133">After processing bank statement transactions is complete, a new general ledger journal is created and ready for posting.</span></span>




