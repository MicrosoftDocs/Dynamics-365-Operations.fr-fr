---
title: Importation des paiements client ESR
description: Cette rubrique fournit des informations sur l’importation de paiements client au format ESR.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: kfend
ms.custom: 264584
ms.search.region: Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6259cd01ec6335731fccdedf84d5049593242036
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839890"
---
# <a name="esr-customer-payments-import"></a><span data-ttu-id="0b2e2-103">Importation des paiements client ESR</span><span class="sxs-lookup"><span data-stu-id="0b2e2-103">ESR customer payments import</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b2e2-104">Cette rubrique fournit des informations sur l’importation de paiements client au format ESR.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-104">This topic provides information about importing customer payments in the ESR format.</span></span>

<span data-ttu-id="0b2e2-105">ESR est un service de débit électronique qui utilise des bordereaux de paiement pour collecter de l’argent.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-105">ESR is an electronic debtor service that uses payment slips to collect money.</span></span> <span data-ttu-id="0b2e2-106">Il s’agit du système standard de paiement électronique créé par la Poste suisse.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-106">It is the standard electronic payment system created by the Swiss Post.</span></span> <span data-ttu-id="0b2e2-107">Vous pouvez recevoir les fichiers de paiement client au format ESR, qui peuvent inclure les transactions et les frais bancaires.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-107">You can receive customer payment files in the ESR format, which can include transactions and bank fees.</span></span> <span data-ttu-id="0b2e2-108">Cette fonctionnalité est destinée aux transactions client importées basées sur les références de paiement initialement générées dans Dynamics 365 Finance et imprimées sur le bordereau de paiement.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-108">This functionality is intended for imported customer transactions based on payment references that were originally generated in Dynamics 365 Finance and printed on the payment slip.</span></span>

## <a name="generate-payment-references"></a><span data-ttu-id="0b2e2-109">Générer les références de paiement</span><span class="sxs-lookup"><span data-stu-id="0b2e2-109">Generate payment references</span></span>
<span data-ttu-id="0b2e2-110">Les références de paiement doivent être imprimées sur le bordereau de paiement après validation.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-110">Payment references should be printed on the payment slip after posting.</span></span> <span data-ttu-id="0b2e2-111">Vous pouvez également vérifier les références de paiement dans la page **Journal des factures** pour la commande client sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-111">You can also verify payment references on the **Invoice journal** page for the selected sales order.</span></span> <span data-ttu-id="0b2e2-112">Pour générer les références de paiement, les paramètres suivants doivent être spécifiés.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-112">To generate payment references, the following settings must be specified.</span></span>

1.  <span data-ttu-id="0b2e2-113">Définissez les paramètres de compte bancaire sur **ESR**, **ID BESR** et **Numéro d’acheminement**.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-113">Set the bank account settings to **ESR**, **BESR ID,** and **Routing number**.</span></span>
2.  <span data-ttu-id="0b2e2-114">Définissez le champ **Nombre de caractères du compte de virement** sur la page **Paramètres de la comptabilité client** sur l’onglet **Comptabilité et taxe**. Cela définit combien de symboles du compte client doivent être inclus dans la référence de paiement.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-114">Set the **Number of characters for Giro account** field on the **Account Receivables parameters** page on the **Ledger and sales tax** tab. This defines how many symbols from the customer account should be included in the payment reference.</span></span>
3.  <span data-ttu-id="0b2e2-115">La souche de numéros de la facture client doit être au format approprié (elle ne doit pas comporter des symboles autres que des chiffres et elle ne doit pas contenir des zéros non significatifs).</span><span class="sxs-lookup"><span data-stu-id="0b2e2-115">The sales invoice number sequence should be in the correct format (it should not have symbols other than digits and it should not contain leading zeros).</span></span>
4.  <span data-ttu-id="0b2e2-116">Le format **Orange** doit être spécifié pour le compte client dans le champ **Sur une facture client** de l’onglet **Facture et livraison**.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-116">The **Orange** format should be specified for the customer account in the **On a customer invoice** field on the **Invoice and delivery** tab.</span></span>

<span data-ttu-id="0b2e2-117">Pour plus d’informations, voir [État du bordereau de paiement pour l’Europe](emea-eur-payment-slip-report-giro.md).</span><span class="sxs-lookup"><span data-stu-id="0b2e2-117">For more information, see [Payment slip report for Europe](emea-eur-payment-slip-report-giro.md).</span></span>

## <a name="import-a-payment-file"></a><span data-ttu-id="0b2e2-118">Importer un fichier de paiement</span><span class="sxs-lookup"><span data-stu-id="0b2e2-118">Import a payment file</span></span>
1. <span data-ttu-id="0b2e2-119">Accédez à la page **Journal des paiements**.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-119">Go to the **Payment journal** page</span></span>
2. <span data-ttu-id="0b2e2-120">Cliquez sur **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-120">Click **Lines**.</span></span>
3. <span data-ttu-id="0b2e2-121">Cliquez sur **Fonctions** &gt; **Importer les paiements**.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-121">Click **Functions** &gt; **Import payments**.</span></span>
4. <span data-ttu-id="0b2e2-122">Dans la boîte de dialogue, sélectionnez le mode de paiement, puis accédez à l’emplacement du fichier à importer.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-122">In the dialog box, select the method of payment, and then browse to the location of the file to import.</span></span> 
   > [!NOTE]
   >  <span data-ttu-id="0b2e2-123">Avant de pouvoir effectuer cette étape, vous devez avoir déjà importé les configurations **ESR (CH)** à partir de Lifecycle Services (LCS) et paramétré le mode de paiement ESR.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-123">Before you can complete this step, you must have already imported the **ESR (CH)** configurations from Lifecycle Services (LCS) and set up the ESR method of payment.</span></span> <span data-ttu-id="0b2e2-124">Pour plus d’informations, voir [Formats de fichier des modes de paiement](emea-select-file-formats-for-the-method-of-payments.md).</span><span class="sxs-lookup"><span data-stu-id="0b2e2-124">For more information, see [File formats for methods of payment](emea-select-file-formats-for-the-method-of-payments.md).</span></span>

<span data-ttu-id="0b2e2-125">Après avoir importé le fichier de paiement, les lignes du journal des paiements sont créées et marquées pour règlement avec les factures client basées sur la référence de paiement.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-125">After you import the payment file, payment journal lines are created and marked for settlement with customer invoices based on the payment reference.</span></span> <span data-ttu-id="0b2e2-126">Si des frais spécifiés pour le compte bancaire sont représentés dans le fichier, par exemple les transactions entre le compte principal et le compte de frais, ces frais seront ajoutés au journal.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-126">If there are any fees specified for the bank account that are represented in the file, such as transactions between the main account and fee account, these fees will be added to the journal.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]