---
title: Relevé bancaire CODA
description: Cette rubrique contient des informations sur CODA, qui est un format d’état utilisé par le système d’opérations bancaires électroniques belge.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, BankCodaAccountStatement, BankCodaAccountStatementLines, BankCodaParameters, BankCodaTrans, BankCodaTransCategory, BankCodaTransDefTable, BankCodaTransFamily
audience: Application User
ms.reviewer: kfend
ms.custom: 262534
ms.search.region: Belgium
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ae014541bebc253d529665fcd841c571e142d783
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209874"
---
# <a name="coda-bank-statement"></a><span data-ttu-id="dbcde-103">Relevé bancaire CODA</span><span class="sxs-lookup"><span data-stu-id="dbcde-103">CODA bank statement</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dbcde-104">Cette rubrique contient des informations sur CODA, qui est un format d’état utilisé par le système d’opérations bancaires électroniques belge.</span><span class="sxs-lookup"><span data-stu-id="dbcde-104">This topic includes information about CODA, which is a report format used in the Belgian electronic banking system.</span></span> 

<span data-ttu-id="dbcde-105">Pour les importations de relevés bancaires belges, vous utiliserez le format de fichier CODA.</span><span class="sxs-lookup"><span data-stu-id="dbcde-105">For Belgian bank statement imports, you'll use the CODA file format.</span></span> <span data-ttu-id="dbcde-106">Cette fonctionnalité permet de vérifier les soldes d’ouverture et de clôture d’un compte bancaire de société, et de rapprocher des transactions importées basées sur des règles de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="dbcde-106">This feature lets you verify company bank account opening and ending balances, and reconcile imported transactions based on reconciliation rules.</span></span>

## <a name="import-transactions-from-a-bank-statement"></a><span data-ttu-id="dbcde-107">Importer des transactions à partir d’un relevé bancaire</span><span class="sxs-lookup"><span data-stu-id="dbcde-107">Import transactions from a bank statement</span></span>
<span data-ttu-id="dbcde-108">Pour importer un fichier de relevé bancaire pour un compte bancaire, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="dbcde-108">To import a bank statement file for a bank account, complete the following steps.</span></span> <span data-ttu-id="dbcde-109">**Remarque** : avant d’importer un fichier de relevé bancaire, vous devez avoir déjà effectué les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dbcde-109">**Note**: Before you import a bank statement file, you must have already completed the following:</span></span>

-   <span data-ttu-id="dbcde-110">Importer les configurations CODA à partir de Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="dbcde-110">Import the CODA configurations from Lifecycle Services (LCS).</span></span> <span data-ttu-id="dbcde-111">Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)</span><span class="sxs-lookup"><span data-stu-id="dbcde-111">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>
-   <span data-ttu-id="dbcde-112">Sélectionner la configuration CODA importée dans la page **Paramètres CODA**.</span><span class="sxs-lookup"><span data-stu-id="dbcde-112">Select the imported CODA configuration on the **CODA parameters** page.</span></span>

1.  <span data-ttu-id="dbcde-113">Accédez à la page **Comptes bancaires**.</span><span class="sxs-lookup"><span data-stu-id="dbcde-113">Go to the **Bank accounts** page.</span></span>
2.  <span data-ttu-id="dbcde-114">Cliquez sur **Rapprocher** &gt; **CODA**.</span><span class="sxs-lookup"><span data-stu-id="dbcde-114">Click **Reconcile** &gt; **CODA**.</span></span>
3.  <span data-ttu-id="dbcde-115">Cliquez sur **CODA** &gt; **Importer depuis le fichier**, puis sélectionnez le chemin d’accès au fichier de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="dbcde-115">Click **CODA** &gt; **Import from file**, and then select the path to the bank statement file.</span></span>

<span data-ttu-id="dbcde-116">Après avoir importé les transactions, vous pouvez effectuer les actions suivantes dans la page **Relevé bancaire**.</span><span class="sxs-lookup"><span data-stu-id="dbcde-116">After you import transactions, you can do the following on the **Bank statement** page.</span></span>

-   <span data-ttu-id="dbcde-117">Vérifier les soldes d’ouverture et de clôture.</span><span class="sxs-lookup"><span data-stu-id="dbcde-117">Verify the opening and ending balances.</span></span>
-   <span data-ttu-id="dbcde-118">Afficher les transactions importées en tant qu’état de relevé bancaire que vous pouvez imprimer.</span><span class="sxs-lookup"><span data-stu-id="dbcde-118">View the imported transactions as a bank statement report that you can print.</span></span>
-   <span data-ttu-id="dbcde-119">Afficher les transactions importées contenant des lignes supplémentaires, telles que les lignes dont le type de compte est « Aucun ».</span><span class="sxs-lookup"><span data-stu-id="dbcde-119">View imported transactions with additional lines, such as lines with an Account type of "None".</span></span> <span data-ttu-id="dbcde-120">Cliquez sur **CODA &gt; Détails**.</span><span class="sxs-lookup"><span data-stu-id="dbcde-120">Click **CODA &gt; Details**.</span></span>

## <a name="process-imported-bank-statement-transactions"></a><span data-ttu-id="dbcde-121">Traiter les transactions de relevé bancaire importées</span><span class="sxs-lookup"><span data-stu-id="dbcde-121">Process imported bank statement transactions</span></span>
<span data-ttu-id="dbcde-122">Effectuez les étapes suivantes pour traiter les transactions de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="dbcde-122">Complete the following steps to process the bank statement transactions.</span></span>

1. <span data-ttu-id="dbcde-123">Traitez les lignes de détail (**CODA** &gt; **Traiter les lignes de détails**).</span><span class="sxs-lookup"><span data-stu-id="dbcde-123">Process details lines (**CODA** &gt; **Process detail lines**).</span></span> <span data-ttu-id="dbcde-124">Démarrez la mise en correspondance automatique en fonction des **Définitions CODA**.</span><span class="sxs-lookup"><span data-stu-id="dbcde-124">Start automatic matching based on **CODA definitions**.</span></span> <span data-ttu-id="dbcde-125">Ces règles déterminent le compte général, client ou fournisseur qui doit être utilisé pour cette transaction.</span><span class="sxs-lookup"><span data-stu-id="dbcde-125">These rules determine which ledger, customer, or vendor account should be used for this transaction.</span></span> <span data-ttu-id="dbcde-126">La comparaison est basée sur le code du groupe de transactions, le code de transaction et le code de catégorie de transaction spécifiés dans le fichier CODA pour chaque transaction.</span><span class="sxs-lookup"><span data-stu-id="dbcde-126">Comparison is based on which Transaction group code, Transaction code, and Transaction category code are specified in CODA file for each transaction.</span></span>
2. <span data-ttu-id="dbcde-127">Les transactions avec un type de compte client et fournisseur peuvent être mises en correspondance avec les factures.</span><span class="sxs-lookup"><span data-stu-id="dbcde-127">Transactions with a customer and vendor account type can be matched with the invoices.</span></span> <span data-ttu-id="dbcde-128">Si nécessaire, les transactions importées peuvent être modifiées manuellement à tout moment après le traitement, avant de les transférer vers la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="dbcde-128">If necessary, imported transactions can be manually changed at any time after processing, before transferring to the ledger.</span></span>
3. <span data-ttu-id="dbcde-129">Si des transactions comportent des erreurs (en général, si aucune règle n’est paramétrée), celles-ci peuvent être mentionnées dans le compte général spécial, spécifié sur la page <strong>Paramètres CODA **(</strong>CODA** &gt; <strong>Effacer les erreurs</strong>).</span><span class="sxs-lookup"><span data-stu-id="dbcde-129">If there are any transactions with errors (generally, if there are no rules set up), these can be referred to the special ledger account, specified on the <strong>CODA parameters **page (</strong>CODA** &gt; <strong>Clear errors</strong>).</span></span>
4. <span data-ttu-id="dbcde-130">Une fois que toutes les transactions du relevé bancaire sont réglées, elles sont prêtes à être transférées vers le journal de comptabilité (<strong>CODA</strong> &gt;<strong>Transfert vers la comptabilité</strong>).</span><span class="sxs-lookup"><span data-stu-id="dbcde-130">After all transactions in the bank statement are settled, they are ready to be transferred to the general ledger journal (<strong>CODA</strong> &gt;<strong>Transfer to ledger</strong>).</span></span> <span data-ttu-id="dbcde-131">Les paramètres du journal doivent être spécifiés pour le compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="dbcde-131">Journal settings should be specified for the bank account.</span></span> <span data-ttu-id="dbcde-132">Les journaux peuvent être ouverts sur la page <strong>Comptes bancaires\*\* pour l’enregistrement sélectionné en cliquant sur \*\*Paramétrage</strong> &gt; <strong>Journal CODA</strong>.</span><span class="sxs-lookup"><span data-stu-id="dbcde-132">Journals can be opened on the <strong>Bank accounts \*\*page for the selected record by clicking \*\*Set up</strong> &gt; <strong>CODA journal</strong>.</span></span>

<span data-ttu-id="dbcde-133">Une fois que le traitement des transactions de relevé bancaire est terminé, un journal de comptabilité est créé et prêt à être validé.</span><span class="sxs-lookup"><span data-stu-id="dbcde-133">After processing bank statement transactions is complete, a new general ledger journal is created and ready for posting.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]