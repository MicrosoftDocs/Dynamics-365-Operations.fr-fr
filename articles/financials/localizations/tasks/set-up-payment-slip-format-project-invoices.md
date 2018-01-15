--- 
title: "Paramétrer un format de bordereau de paiement pour les factures de projet"
description: "Les entreprises associent généralement les bordereaux de paiement imprimés aux factures pour aider leurs clients et fournir une référence de paiement pour la validation et le règlement."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 02/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 9700571110a1b488e250dd8ee7b8c5c8f15cbc01
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-payment-slip-format-for-project-invoices"></a><span data-ttu-id="74f0f-103">Paramétrer un format de bordereau de paiement pour les factures de projet</span><span class="sxs-lookup"><span data-stu-id="74f0f-103">Set up payment slip format for project invoices</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="74f0f-104">Les entreprises associent généralement les bordereaux de paiement imprimés aux factures pour aider leurs clients et fournir une référence de paiement pour la validation et le règlement.</span><span class="sxs-lookup"><span data-stu-id="74f0f-104">Businesses commonly attach printed payment slips to invoices to assist customers and provide a payment reference for posting and settlement.</span></span> <span data-ttu-id="74f0f-105">Les bordereaux de paiement peuvent être utilisés pour les factures de projet ou de service, les lettres de relance, les notes d'intérêt et les relevés de compte, en plus des factures client et des factures financières.</span><span class="sxs-lookup"><span data-stu-id="74f0f-105">The payment slip can be used for project or service invoices, collection letters, interest notes, and account statements, in addition to sales invoices and free text invoices.</span></span> <span data-ttu-id="74f0f-106">Pour traiter les bordereaux de paiement, commencez par paramétrer votre ID créditeur et les formats de bordereau de paiement associé.</span><span class="sxs-lookup"><span data-stu-id="74f0f-106">To process payment slips, first set up your creditor identification number and payment slip attachment formats.</span></span>

<span data-ttu-id="74f0f-107">La société fictive DEMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="74f0f-107">This procedure uses the DEMF demo company.</span></span> 

<span data-ttu-id="74f0f-108">Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est au Danemark.</span><span class="sxs-lookup"><span data-stu-id="74f0f-108">This functionality is available for legal entities whose primary address is in Denmark.</span></span>


## <a name="set-up-a-creditor-id-number"></a><span data-ttu-id="74f0f-109">Paramétrage d'un ID créditeur</span><span class="sxs-lookup"><span data-stu-id="74f0f-109">Set up a creditor ID number</span></span>
1. <span data-ttu-id="74f0f-110">Accédez à Administration d'organisation > Organisations > Entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="74f0f-110">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="74f0f-111">Développez ou réduisez la section la section Informations sur le compte en banque.</span><span class="sxs-lookup"><span data-stu-id="74f0f-111">Expand or collapse the Bank account information section.</span></span>
3. <span data-ttu-id="74f0f-112">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="74f0f-112">Click Edit.</span></span>
4. <span data-ttu-id="74f0f-113">Dans le champ ID créditeur financier, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="74f0f-113">In the FI-Creditor ID field, type a value.</span></span>
5. <span data-ttu-id="74f0f-114">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="74f0f-114">Click Save.</span></span>
6. <span data-ttu-id="74f0f-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="74f0f-115">Close the page.</span></span>

## <a name="set-up-a-payment-slip-format-for-invoices-notes-letters-and-statements"></a><span data-ttu-id="74f0f-116">Paramétrage d'un format de bordereau de paiement pour les factures, les notes, les lettres et les relevés</span><span class="sxs-lookup"><span data-stu-id="74f0f-116">Set up a payment slip format for invoices, notes, letters, and statements</span></span>
1. <span data-ttu-id="74f0f-117">Accédez à Comptabilité client > Paramétrage > Écrans > Paramétrage d'écran.</span><span class="sxs-lookup"><span data-stu-id="74f0f-117">Go to Accounts receivable > Setup > Forms > Form setup.</span></span>
2. <span data-ttu-id="74f0f-118">Cliquez sur l'onglet Facture.</span><span class="sxs-lookup"><span data-stu-id="74f0f-118">Click the Invoice tab.</span></span>
3. <span data-ttu-id="74f0f-119">Dans le champ Document de paiement associé de facture client, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="74f0f-119">In the Associated payment attachment on customer invoice field, select an option.</span></span>
    * <span data-ttu-id="74f0f-120">Aucun(e) – N'imprimez pas de bordereau de paiement.</span><span class="sxs-lookup"><span data-stu-id="74f0f-120">None – Do not print a payment slip.</span></span> <span data-ttu-id="74f0f-121">Sélectionnez cette option si le montant du paiement est exprimé dans une devise autre que la couronne danoise (DKK).</span><span class="sxs-lookup"><span data-stu-id="74f0f-121">Choose this option if the payment amount is in a currency other than Danish kroner (DKK).</span></span>   <span data-ttu-id="74f0f-122">FIK 751 : imprimez un bordereau de paiement FIK 751 si vous souhaitez reporter manuellement le montant du paiement et la date d'échéance sur le bordereau de paiement.</span><span class="sxs-lookup"><span data-stu-id="74f0f-122">FIK 751 – Print an FIK 751 payment slip if you intend to manually write the payment amount and due date on the payment slip.</span></span>   <span data-ttu-id="74f0f-123">FIK 752 : imprimez un bordereau de paiement FIK 752 si vous souhaitez utiliser un bordereau de paiement généré par ordinateur avec un montant de paiement et une date d'échéance préimprimés.</span><span class="sxs-lookup"><span data-stu-id="74f0f-123">FIK 752 – Print an FIK 752 payment slip if you intend to use a computer-generated payment slip with a preprinted payment amount and due date.</span></span>  
4. <span data-ttu-id="74f0f-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="74f0f-124">Click Save.</span></span>
5. <span data-ttu-id="74f0f-125">Cliquez sur l'onglet Facture financière.</span><span class="sxs-lookup"><span data-stu-id="74f0f-125">Click the Free text invoice tab.</span></span>
6. <span data-ttu-id="74f0f-126">Dans le champ Document de paiement associé de facture financière, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="74f0f-126">In the Associated payment attachment on free text invoice field, select an option.</span></span>
    * <span data-ttu-id="74f0f-127">Aucun(e) – N'imprimez pas de bordereau de paiement.</span><span class="sxs-lookup"><span data-stu-id="74f0f-127">None – Do not print a payment slip.</span></span> <span data-ttu-id="74f0f-128">Sélectionnez cette option si le montant du paiement est exprimé dans une devise autre que la couronne danoise (DKK).</span><span class="sxs-lookup"><span data-stu-id="74f0f-128">Choose this option if the payment amount is in a currency other than Danish kroner (DKK).</span></span>   <span data-ttu-id="74f0f-129">FIK 751 : imprimez un bordereau de paiement FIK 751 si vous souhaitez reporter manuellement le montant du paiement et la date d'échéance sur le bordereau de paiement.</span><span class="sxs-lookup"><span data-stu-id="74f0f-129">FIK 751 – Print an FIK 751 payment slip if you intend to write the payment amount and due date on the payment slip manually.</span></span>   <span data-ttu-id="74f0f-130">FIK 752 : imprimez un bordereau de paiement FIK 752 si vous souhaitez utiliser un bordereau de paiement généré par ordinateur avec un montant de paiement et une date d'échéance préimprimés.</span><span class="sxs-lookup"><span data-stu-id="74f0f-130">FIK 752 – Print an FIK 752 payment slip if you intend to use a computer-generated payment slip with a preprinted payment amount and due date.</span></span>  
7. <span data-ttu-id="74f0f-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="74f0f-131">Click Save.</span></span>
8. <span data-ttu-id="74f0f-132">Cliquez sur l'onglet Note d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="74f0f-132">Click the Interest note tab.</span></span>
9. <span data-ttu-id="74f0f-133">Dans le champ Document de paiement associé de note d'intérêt, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="74f0f-133">In the Associated payment attachment on interest note field, select an option.</span></span>
    * <span data-ttu-id="74f0f-134">Aucun(e) – N'imprimez pas de bordereau de paiement.</span><span class="sxs-lookup"><span data-stu-id="74f0f-134">None – Do not print a payment slip.</span></span> <span data-ttu-id="74f0f-135">Sélectionnez cette option si le montant du paiement est exprimé dans une devise autre que la couronne danoise (DKK).</span><span class="sxs-lookup"><span data-stu-id="74f0f-135">Choose this option if the payment amount is in a currency other than Danish kroner (DKK).</span></span>   <span data-ttu-id="74f0f-136">FIK 751 : imprimez un bordereau de paiement FIK 751 si vous souhaitez reporter manuellement le montant du paiement et la date d'échéance sur le bordereau de paiement.</span><span class="sxs-lookup"><span data-stu-id="74f0f-136">FIK 751 – Print an FIK 751 payment slip if you intend to write the payment amount and due date on the payment slip manually.</span></span>   <span data-ttu-id="74f0f-137">FIK 752 : imprimez un bordereau de paiement FIK 752 si vous souhaitez utiliser un bordereau de paiement généré par ordinateur avec un montant de paiement et une date d'échéance préimprimés.</span><span class="sxs-lookup"><span data-stu-id="74f0f-137">FIK 752 – Print an FIK 752 payment slip if you intend to use a computer-generated payment slip with a preprinted payment amount and due date.</span></span>  
10. <span data-ttu-id="74f0f-138">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="74f0f-138">Click Save.</span></span>
11. <span data-ttu-id="74f0f-139">Cliquez sur l'onglet Lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="74f0f-139">Click the Collection letter tab.</span></span>
12. <span data-ttu-id="74f0f-140">Dans le champ Document de paiement associé de lettre de relance, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="74f0f-140">In the Associated payment attachment on collection letter field, select an option.</span></span>
    * <span data-ttu-id="74f0f-141">Aucun(e) – N'imprimez pas de bordereau de paiement.</span><span class="sxs-lookup"><span data-stu-id="74f0f-141">None – Do not print a payment slip.</span></span> <span data-ttu-id="74f0f-142">Sélectionnez cette option si le montant du paiement est exprimé dans une devise autre que la couronne danoise (DKK).</span><span class="sxs-lookup"><span data-stu-id="74f0f-142">Choose this option if the payment amount is in a currency other than Danish kroner (DKK).</span></span>   <span data-ttu-id="74f0f-143">FIK 751 : imprimez un bordereau de paiement FIK 751 si vous souhaitez reporter manuellement le montant du paiement et la date d'échéance sur le bordereau de paiement.</span><span class="sxs-lookup"><span data-stu-id="74f0f-143">FIK 751 – Print an FIK 751 payment slip if you intend to write the payment amount and due date on the payment slip manually.</span></span>   <span data-ttu-id="74f0f-144">FIK 752 : imprimez un bordereau de paiement FIK 752 si vous souhaitez utiliser un bordereau de paiement généré par ordinateur avec un montant de paiement et une date d'échéance préimprimés.</span><span class="sxs-lookup"><span data-stu-id="74f0f-144">FIK 752 – Print an FIK 752 payment slip if you intend to use a computer-generated payment slip with a preprinted payment amount and due date.</span></span>  
13. <span data-ttu-id="74f0f-145">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="74f0f-145">Click Save.</span></span>
14. <span data-ttu-id="74f0f-146">Cliquez sur l'onglet Relevé de compte.</span><span class="sxs-lookup"><span data-stu-id="74f0f-146">Click the Account statement tab.</span></span>
15. <span data-ttu-id="74f0f-147">Dans le champ Document de paiement associé de relevé d'échéances, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="74f0f-147">In the Associated payment attachment on account statement field, select an option.</span></span>
    * <span data-ttu-id="74f0f-148">Aucun(e) – N'imprimez pas de bordereau de paiement.</span><span class="sxs-lookup"><span data-stu-id="74f0f-148">None – Do not print a payment slip.</span></span> <span data-ttu-id="74f0f-149">Sélectionnez cette option si le montant du paiement est exprimé dans une devise autre que la couronne danoise (DKK).</span><span class="sxs-lookup"><span data-stu-id="74f0f-149">Choose this option if the payment amount is in a currency other than Danish kroner (DKK).</span></span>   <span data-ttu-id="74f0f-150">FIK 751 : imprimez un bordereau de paiement FIK 751 si vous souhaitez reporter manuellement le montant du paiement et la date d'échéance sur le bordereau de paiement.</span><span class="sxs-lookup"><span data-stu-id="74f0f-150">FIK 751 – Print an FIK 751 payment slip if you intend to write the payment amount and due date on the payment slip manually.</span></span>   <span data-ttu-id="74f0f-151">FIK 752 : imprimez un bordereau de paiement FIK 752 si vous souhaitez utiliser un bordereau de paiement généré par ordinateur avec un montant de paiement et une date d'échéance préimprimés.</span><span class="sxs-lookup"><span data-stu-id="74f0f-151">FIK 752 – Print an FIK 752 payment slip if you intend to use a computer-generated payment slip with a preprinted payment amount and due date.</span></span>  
16. <span data-ttu-id="74f0f-152">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="74f0f-152">Click Save.</span></span>
17. <span data-ttu-id="74f0f-153">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="74f0f-153">Close the page.</span></span>

