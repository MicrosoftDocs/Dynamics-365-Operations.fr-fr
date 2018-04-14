---
title: "Rapprochement des relevés bancaires et des paiements pour l'UE"
description: "Cette rubrique donne une vue d'ensemble de la fonctionnalité permettant de rapprocher les informations de paiement des banques dans les formats utilisés par les pays européens."
author: neserovleo
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 267994
ms.search.region: Belgium, Norway, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fcae9bf8068913f8cda61e3fd3063f0a6122ae4d
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="bank-statement-and-payment-reconciliation-for-the-eu"></a><span data-ttu-id="98a2e-103">Rapprochement des relevés bancaires et des paiements pour l'UE</span><span class="sxs-lookup"><span data-stu-id="98a2e-103">Bank statement and payment reconciliation for the EU</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="98a2e-104">Cette rubrique donne une vue d'ensemble de la fonctionnalité permettant de rapprocher les informations de paiement des banques dans les formats utilisés par les pays européens.</span><span class="sxs-lookup"><span data-stu-id="98a2e-104">This topic provides an overview of the functionality that you can use to reconcile payment information from banks in formats that are used by European countries.</span></span>

<span data-ttu-id="98a2e-105">Dans Microsoft Dynamics 365 for Finance and Operations, vous pouvez importer des transactions bancaires et régler ces transactions avec les transactions existantes.</span><span class="sxs-lookup"><span data-stu-id="98a2e-105">In Microsoft Dynamics 365 for Finance and Operations, you can import transactions from banks and settle these transactions against existing transactions.</span></span> <span data-ttu-id="98a2e-106">En Europe, vous pouvez le faire pour les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="98a2e-106">In Europe, you can do this for the following scenarios:</span></span>

-   <span data-ttu-id="98a2e-107">Importation des relevés bancaires</span><span class="sxs-lookup"><span data-stu-id="98a2e-107">Importing bank statements</span></span>
-   <span data-ttu-id="98a2e-108">Importation des paiements</span><span class="sxs-lookup"><span data-stu-id="98a2e-108">Importing payments</span></span>
-   <span data-ttu-id="98a2e-109">Importation des fichiers de retour</span><span class="sxs-lookup"><span data-stu-id="98a2e-109">Importing return files</span></span>

## <a name="bank-statements"></a><span data-ttu-id="98a2e-110">Relevés bancaires</span><span class="sxs-lookup"><span data-stu-id="98a2e-110">Bank statements</span></span>
<span data-ttu-id="98a2e-111">Un *relevé bancaire* ou *relevé de compte* est une synthèse des transactions financières effectuées sur une période donnée sur un compte bancaire détenu par une société avec une institution financière.</span><span class="sxs-lookup"><span data-stu-id="98a2e-111">A *bank statement* or *account statement* is a summary of financial transactions that have occurred over a given period on a bank account held by a company with a financial institution.</span></span> <span data-ttu-id="98a2e-112">Dans Finance and Operations, vous pouvez importer un relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="98a2e-112">In Finance and Operations you can import a bank statement.</span></span> <span data-ttu-id="98a2e-113">Il est important de régler les transactions importées avec les transactions existantes et de vérifier le solde d'ouverture et de fin des comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="98a2e-113">It is important to settle imported transactions with existing transactions as well as verify the opening and ending balance of the bank accounts.</span></span> <span data-ttu-id="98a2e-114">La liste suivante présente les formats européens pris en charge.</span><span class="sxs-lookup"><span data-stu-id="98a2e-114">The following list includes the supported European formats.</span></span>

-   <span data-ttu-id="98a2e-115">Formats du fichier européen de rapprochement bancaire avancé.</span><span class="sxs-lookup"><span data-stu-id="98a2e-115">Advanced bank reconciliation European file formats.</span></span> <span data-ttu-id="98a2e-116">Pour plus d'informations, voir [Vue d'ensemble du rapprochement bancaire avancé](../cash-bank-management/advanced-bank-reconciliation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98a2e-116">For more information, see [Advanced bank reconciliation overview](../cash-bank-management/advanced-bank-reconciliation-overview.md).</span></span>
-   <span data-ttu-id="98a2e-117">Format du fichier de message de relevé bancaire ISO 20022 camt.053</span><span class="sxs-lookup"><span data-stu-id="98a2e-117">ISO 20022 camt.053 bank statement message file format.</span></span>
-   <span data-ttu-id="98a2e-118">Format du fichier de relevé bancaire CODA.</span><span class="sxs-lookup"><span data-stu-id="98a2e-118">CODA bank statement file format.</span></span> <span data-ttu-id="98a2e-119">Pour plus d'informations, voir [Relevé bancaire CODA](emea-bel-coda-bank-statement-import.md).</span><span class="sxs-lookup"><span data-stu-id="98a2e-119">For more information, see [CODA bank statement](emea-bel-coda-bank-statement-import.md).</span></span>

## <a name="customer-and-vendor-payments-import-and-return-messages"></a><span data-ttu-id="98a2e-120">Messages d'importation et de retour des paiements client et fournisseur</span><span class="sxs-lookup"><span data-stu-id="98a2e-120">Customer and vendor payments import and return messages</span></span>
<span data-ttu-id="98a2e-121">Outre un relevé bancaire, les banques peuvent fournir des messages spécifiques, contenant des informations sur les paiements client ou fournisseur, qui peuvent être importés dans Finance and Operations et rapprochés avec les transactions client et fournisseur.</span><span class="sxs-lookup"><span data-stu-id="98a2e-121">In addition to a bank statement, banks can provide specific messages, containing information about customer and vendor payments, which can be imported into Finance and Operations and reconciled with customer and vendor transactions.</span></span> <span data-ttu-id="98a2e-122">Lorsqu'une société doit recevoir des informations sur les transactions de paiements client entrants de la banque, les formats d'importation peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="98a2e-122">When a company needs to receive information about incoming customer payments transactions from the bank, the import formats can be used.</span></span> <span data-ttu-id="98a2e-123">Pour les sociétés qui utilisent le transfert de débit et de crédit direct, les messages de retour peuvent être reçus pour mettre à jour le statut des paiements qui ont été précédemment exportés.</span><span class="sxs-lookup"><span data-stu-id="98a2e-123">For companies that use direct debit and credit transfer, the return messages can be received to update the status of payments that were previously exported.</span></span> <span data-ttu-id="98a2e-124">La différence entre les formats d'importation et les formats de retour est que les retours visent principalement à mettre à jour les lignes de journal des paiements déjà créées (elles peuvent être créées lors du lancement du transfert de débit ou de crédit direct) au lieu de créer de nouvelles lignes.</span><span class="sxs-lookup"><span data-stu-id="98a2e-124">The difference between import formats and return formats is that returns are targeted mostly to update already created payment journal lines (they can be created when direct debit or credit transfer were initiated) instead of creating new lines.</span></span> <span data-ttu-id="98a2e-125">Certains formats d'importation complexes peuvent également inclure des scénarios de retour.</span><span class="sxs-lookup"><span data-stu-id="98a2e-125">Some complex import formats can also include return scenarios.</span></span> <span data-ttu-id="98a2e-126">L'exemple suivant montre comment cette division doit être implémentée.</span><span class="sxs-lookup"><span data-stu-id="98a2e-126">The following example shows how this division should be implemented.</span></span>

### <a name="import-formats"></a><span data-ttu-id="98a2e-127">Formats d'importation</span><span class="sxs-lookup"><span data-stu-id="98a2e-127">Import formats</span></span>

-   <span data-ttu-id="98a2e-128">Message de notification bancaire ISO 20022 [camt.054](emea-ISO20022-file-formats.md)</span><span class="sxs-lookup"><span data-stu-id="98a2e-128">ISO 20022 [camt.054](emea-ISO20022-file-formats.md) bank notification message</span></span>
-   <span data-ttu-id="98a2e-129">[Format d'importation Nets](emea-nor-nets-import-format.md) - Fonction complexe pour les formats de paiement norvégiens</span><span class="sxs-lookup"><span data-stu-id="98a2e-129">[Nets import format](emea-nor-nets-import-format.md) - Complex feature for Norwegian payment formats</span></span>
-   <span data-ttu-id="98a2e-130">Paiements d'importation client [ESR](emea-che-esr-customer-payments-import.md)</span><span class="sxs-lookup"><span data-stu-id="98a2e-130">[ESR](emea-che-esr-customer-payments-import.md) customer payments import</span></span>
-   <span data-ttu-id="98a2e-131">Formats de paiement d'importation pour la Suède - Formats OCR BankGirot Max et BankGirot</span><span class="sxs-lookup"><span data-stu-id="98a2e-131">Import payment formats for Sweden - BankGirot Max and BankGirot OCR formats</span></span>

### <a name="return-formats"></a><span data-ttu-id="98a2e-132">Formats de retour</span><span class="sxs-lookup"><span data-stu-id="98a2e-132">Return formats</span></span>

-   <span data-ttu-id="98a2e-133">État du statut de paiement ISO 20022 [pain.002](emea-ISO20022-file-formats.md)</span><span class="sxs-lookup"><span data-stu-id="98a2e-133">ISO 20022 [pain.002](emea-ISO20022-file-formats.md) payment status report</span></span>
-   <span data-ttu-id="98a2e-134">(DNK) BetalingsserviceBasis-returformat – Format de retour pour le format d'exportation Betalingsservice client</span><span class="sxs-lookup"><span data-stu-id="98a2e-134">(DNK) BetalingsserviceBasis-returformat – Return format for customer Betalingsservice export format</span></span>
-   <span data-ttu-id="98a2e-135">[Formats de paiement d'importation pour la Suède](emea-swe-payment-formats-import.md) - Retours Bankgirot Autogiro</span><span class="sxs-lookup"><span data-stu-id="98a2e-135">[Import payment formats for Sweden](emea-swe-payment-formats-import.md) - Bankgirot Autogiro returns</span></span>
-   <span data-ttu-id="98a2e-136">(SWE) Retour BankGirot – Format de retour des paiements fournisseur, qui correspond au format d'exportation Bankgirot</span><span class="sxs-lookup"><span data-stu-id="98a2e-136">(SWE) BankGirot return – Vendor payments return format, which corresponds to Bankgirot export format</span></span>



