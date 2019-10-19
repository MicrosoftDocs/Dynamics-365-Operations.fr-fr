---
title: Remboursements dans le secteur public
description: Cette rubrique répond aux questions courantes associées aux remboursements dans le secteur public.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustBillingClassification
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 27311
ms.assetid: 9d61d1d8-1672-4bd0-ae0d-605b09240890
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f098d9c10b9dec5a38feebe602f664fd1ba1c61
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183635"
---
# <a name="reimbursements-in-the-public-sector"></a><span data-ttu-id="a90b5-103">Remboursements dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="a90b5-103">Reimbursements in the public sector</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a90b5-104">Cette rubrique répond aux questions courantes associées aux remboursements dans le secteur public.</span><span class="sxs-lookup"><span data-stu-id="a90b5-104">This topic answers common questions related to reimbursements in the public sector.</span></span> 

<a name="what-happens-if-i-create-a-separate-reimbursement-transaction-for-each-billing-classification"></a><span data-ttu-id="a90b5-105">Que se passe-t-il si je crée une transaction de remboursement distincte pour chaque classification de facturation ?</span><span class="sxs-lookup"><span data-stu-id="a90b5-105">What happens if I create a separate reimbursement transaction for each billing classification?</span></span>
----------------------------------------------------------------------------------------------

<span data-ttu-id="a90b5-106">Lorsque vous créez une transaction de remboursement distincte pour chaque classification de facturation, les transactions d'avoir qui sont réparties vers le même compte général et dotées de la même classification de facturation sont combinées dans une transaction de remboursement unique.</span><span class="sxs-lookup"><span data-stu-id="a90b5-106">When you create a separate reimbursement transaction for each billing classification, the credit note transactions that are distributed to the same ledger account and that have the same billing classification will be combined into a single reimbursement transaction.</span></span> <span data-ttu-id="a90b5-107">Les transactions d'avoir qui sont réparties vers le même compte général et qui sont dotées de classifications de facturation différentes génèrent des transactions de remboursement distinctes.</span><span class="sxs-lookup"><span data-stu-id="a90b5-107">Credit note transactions that are distributed to the same ledger account and that have different billing classifications will generate separate reimbursement transactions.</span></span> <span data-ttu-id="a90b5-108">Supposons, par exemple, que vous traitiez les remboursements pour trois avoirs.</span><span class="sxs-lookup"><span data-stu-id="a90b5-108">For example, let’s say that you process reimbursements for three credit notes.</span></span> <span data-ttu-id="a90b5-109">Les trois avoirs sont d'un montant de 1 000 €.</span><span class="sxs-lookup"><span data-stu-id="a90b5-109">All three credit notes are for $1000.</span></span>

-   <span data-ttu-id="a90b5-110">Le premier avoir, doté de la classification de facturation UTL, est distribué vers trois comptes, avec 15 % vers le compte 1110, 30 % vers le compte 2210 et 55 % vers le compte 3210.</span><span class="sxs-lookup"><span data-stu-id="a90b5-110">The first credit note has billing classification UTL, is distributed to three accounts, with 15% going to account 1110, 30% to account 2210, and 55% to account 3210.</span></span>
-   <span data-ttu-id="a90b5-111">Le deuxième avoir est également doté de la classification de facturation UTL.</span><span class="sxs-lookup"><span data-stu-id="a90b5-111">The second credit note also has billing classification UTL.</span></span> <span data-ttu-id="a90b5-112">Il est distribué à 100 % vers le compte 3210.</span><span class="sxs-lookup"><span data-stu-id="a90b5-112">It is distributed 100% to account 3210.</span></span>
-   <span data-ttu-id="a90b5-113">Le troisième avoir, doté de la classification de facturation GEN, est distribué à 100 % vers le compte 1110.</span><span class="sxs-lookup"><span data-stu-id="a90b5-113">The third credit note, with billing classification GEN, is distributed 100% to account 1110.</span></span>

<span data-ttu-id="a90b5-114">Si vous créez une transaction de remboursement distincte pour chaque classification de facturation, quatre transactions de remboursement sont créées, de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="a90b5-114">If you create a separate reimbursement transaction for each billing classification, four reimbursement transactions will be created, as follows:</span></span>

-   <span data-ttu-id="a90b5-115">150 € vers le compte 1110</span><span class="sxs-lookup"><span data-stu-id="a90b5-115">$150 to account 1110</span></span>
-   <span data-ttu-id="a90b5-116">1 000 € vers le compte 1110</span><span class="sxs-lookup"><span data-stu-id="a90b5-116">$1000 to account 1110</span></span>
-   <span data-ttu-id="a90b5-117">300 € vers le compte 2210</span><span class="sxs-lookup"><span data-stu-id="a90b5-117">$300 to account 2210</span></span>
-   <span data-ttu-id="a90b5-118">1 550 € vers le compte 3210</span><span class="sxs-lookup"><span data-stu-id="a90b5-118">$1550 to account 3210</span></span>

<span data-ttu-id="a90b5-119">Les montants dirigés vers le compte 3210 sont combinés, car ils utilisent tous deux la même classification de facturation.</span><span class="sxs-lookup"><span data-stu-id="a90b5-119">The amounts going to account 3210 are combined, because they both use the same billing classification.</span></span> <span data-ttu-id="a90b5-120">Les montants dirigés vers le compte 1110 ne sont pas combinés, car ils n'utilisent pas la même classification de facturation.</span><span class="sxs-lookup"><span data-stu-id="a90b5-120">The amounts going to account 1110 are not combined, because they do not use the same billing classification.</span></span> <span data-ttu-id="a90b5-121">Si vous ne créez pas un remboursement distinct pour chaque classification de facturation, les transactions associées au compte 1110 seraient combinées, et seulement trois transactions de remboursement seraient créées.</span><span class="sxs-lookup"><span data-stu-id="a90b5-121">If you do not create a separate reimbursement for each billing classification, the transactions for account 1110 would be combined, and only three reimbursement transactions would be created.</span></span>

## <a name="how-do-billing-classifications-affect-reimbursements-for-overpayments"></a><span data-ttu-id="a90b5-122">Comment les classifications de facturation affectent-elles les remboursements des trop-perçus ?</span><span class="sxs-lookup"><span data-stu-id="a90b5-122">How do billing classifications affect reimbursements for overpayments?</span></span>
<span data-ttu-id="a90b5-123">Elle ne les affectent pas.</span><span class="sxs-lookup"><span data-stu-id="a90b5-123">They don’t.</span></span> <span data-ttu-id="a90b5-124">Les classifications de facturation ne sont jamais appliquées aux paiements client, et elles ne sont donc pas utilisées lors du traitement des remboursements des trop-perçus.</span><span class="sxs-lookup"><span data-stu-id="a90b5-124">Billing classifications are never applied to customer payments, so they aren’t used when processing reimbursements for overpayments.</span></span>

## <a name="can-i-process-a-reimbursement-for-a-customer-who-has-outstanding-debit-transactions"></a><span data-ttu-id="a90b5-125">Puis-je traiter un remboursement pour un client ayant des transactions débitrices en attente ?</span><span class="sxs-lookup"><span data-stu-id="a90b5-125">Can I process a reimbursement for a customer who has outstanding debit transactions?</span></span>
<span data-ttu-id="a90b5-126">Oui.</span><span class="sxs-lookup"><span data-stu-id="a90b5-126">Yes.</span></span> <span data-ttu-id="a90b5-127">Si vous devez traiter un remboursement pour un client ayant des transactions débitrices en attente, utilisez les filtres sur la page de remboursement afin de sélectionner le client, puis sélectionnez l'option permettant d'inclure les clients avec des transactions débitrices en attente.</span><span class="sxs-lookup"><span data-stu-id="a90b5-127">If you need to process a reimbursement for a customer with outstanding debit transactions, use the filters on the reimbursement page to select the customer, and select the option to include customers with outstanding debit transactions.</span></span> <span data-ttu-id="a90b5-128">Lorsque vous procédez ainsi, les transactions de remboursement sont créées pour le montant total de toutes les transactions créditrices du client.</span><span class="sxs-lookup"><span data-stu-id="a90b5-128">When you do this, reimbursement transactions are created for the full amount of all of the customer’s credit transactions.</span></span> <span data-ttu-id="a90b5-129">Les montants débiteurs impayés ne sont pas déduits des montants créditeurs.</span><span class="sxs-lookup"><span data-stu-id="a90b5-129">The outstanding debit amounts are not deducted from the credit amounts.</span></span>

## <a name="can-i-process-reimbursements-for-customers-who-have-pending-settlements"></a><span data-ttu-id="a90b5-130">Puis-je traiter les remboursements pour les clients ayant des règlements en attente ?</span><span class="sxs-lookup"><span data-stu-id="a90b5-130">Can I process reimbursements for customers who have pending settlements?</span></span>
<span data-ttu-id="a90b5-131">N°</span><span class="sxs-lookup"><span data-stu-id="a90b5-131">No.</span></span> <span data-ttu-id="a90b5-132">Les remboursements ne sont traités pour aucun client qui possède des règlements en attente non validés au journal.</span><span class="sxs-lookup"><span data-stu-id="a90b5-132">Reimbursements are not processed for any customer who has pending settlements that have not been posted to the journal.</span></span>

## <a name="can-i-reverse-reimbursement-settlements"></a><span data-ttu-id="a90b5-133">Puis-je contrepasser des règlements de remboursement ?</span><span class="sxs-lookup"><span data-stu-id="a90b5-133">Can I reverse reimbursement settlements?</span></span>
<span data-ttu-id="a90b5-134">Non, pas directement.</span><span class="sxs-lookup"><span data-stu-id="a90b5-134">No, not directly.</span></span> <span data-ttu-id="a90b5-135">Toutefois, vous pouvez utiliser les entrées du journal des opérations diverses pour créer les transactions qui auraient l'effet de contrepasser les écritures comptables.</span><span class="sxs-lookup"><span data-stu-id="a90b5-135">However, you could use general journal entries to create transactions that would have the effect of reversing the general ledger entries.</span></span>





