---
title: Pénalités pour les paiements client en retard en France
description: En France, vous pouvez appliquer une pénalité lorsqu’un paiement client est en retard et vous pouvez imprimer le texte de récupération de la somme forfaitaire qui affiche le montant de pénalité qui doit être payé sur la facture ainsi que la date d’échéance du paiement.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustInvoiceJournal, CustFormletterParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 31221
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b51074e7db4c1ac322a2222e99a85ce935b07dc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5002959"
---
# <a name="penalties-for-past-due-customer-payments-in-france"></a><span data-ttu-id="b91dc-103">Pénalités pour les paiements client en retard en France</span><span class="sxs-lookup"><span data-stu-id="b91dc-103">Penalties for past due customer payments in France</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b91dc-104">En France, vous pouvez appliquer une pénalité lorsqu’un paiement client est en retard et vous pouvez imprimer le texte de récupération de la somme forfaitaire qui affiche le montant de pénalité qui doit être payé sur la facture ainsi que la date d’échéance du paiement.</span><span class="sxs-lookup"><span data-stu-id="b91dc-104">In France, you can apply a penalty when a customer payment is past due and you can print the lump sum recovery text that displays the penalty amount that must be paid on the invoice, and the due date of the payment.</span></span> 

<a name="what-is-lump-sum-recovery-text"></a><span data-ttu-id="b91dc-105">Qu’est-ce que le texte récupéré du montant forfaitaire ?</span><span class="sxs-lookup"><span data-stu-id="b91dc-105">What is lump sum recovery text?</span></span>
-------------------------------

<span data-ttu-id="b91dc-106">Le texte récupéré du montant forfaitaire affiche le montant de pénalité et la date d’échéance du paiement.</span><span class="sxs-lookup"><span data-stu-id="b91dc-106">Lump sum recovery text shows the penalty amount and the due date for the payment.</span></span> <span data-ttu-id="b91dc-107">Le montant de pénalité est appliqué si le paiement a lieu après la date d’échéance.</span><span class="sxs-lookup"><span data-stu-id="b91dc-107">The penalty amount is applied if the payment is past the due date.</span></span> <span data-ttu-id="b91dc-108">Le texte récupéré du montant forfaitaire est imprimé sur la facture client.</span><span class="sxs-lookup"><span data-stu-id="b91dc-108">Lump sum recovery text is printed on the customer invoice.</span></span> <span data-ttu-id="b91dc-109">Vous pouvez spécifier le montant de pénalité et la devise avec toute instruction dans le champ Texte récupéré du montant forfaitaire de la zone Facture de l’écran Paramétrage d’écran.</span><span class="sxs-lookup"><span data-stu-id="b91dc-109">You can specify the penalty amount and the currency along with any instructions in the Lump sum recovery text field in the Invoice area on the Form setup form.</span></span>

## <a name="how-do-i-print-lump-sum-recovery-text-on-a-customer-invoice"></a><span data-ttu-id="b91dc-110">Comment imprimer le texte récupéré du montant forfaitaire sur une facture client ?</span><span class="sxs-lookup"><span data-stu-id="b91dc-110">How do I print lump sum recovery text on a customer invoice?</span></span>
<span data-ttu-id="b91dc-111">Vous pouvez déjà utiliser l’écran Paramétrage d’écran pour définir les paramètres d’impression du texte récupéré du montant forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="b91dc-111">First, you can use the Form setup page to set up the parameters to print lump sum recovery text.</span></span> <span data-ttu-id="b91dc-112">Ensuite, vous pouvez utiliser la page Validation de la facture ou la page Journal des factures pour imprimer le texte récupéré du montant forfaitaire sur une facture client.</span><span class="sxs-lookup"><span data-stu-id="b91dc-112">Next, you can use the Posting invoice page or the Invoice journal page to print the lump sum recovery text on a customer invoice.</span></span> <span data-ttu-id="b91dc-113">Pour plus d’informations voir [Imprimer un texte récupéré de montant forfaitaire sur une facture client](emea-fra-print-lump-sum-recovery-text.md).</span><span class="sxs-lookup"><span data-stu-id="b91dc-113">For more information, see [Print lump sum recovery text on a customer invoice](emea-fra-print-lump-sum-recovery-text.md).</span></span>

## <a name="when-do-i-apply-a-penalty-to-a-customer-payment"></a><span data-ttu-id="b91dc-114">Quand appliquer une pénalité à un paiement client ?</span><span class="sxs-lookup"><span data-stu-id="b91dc-114">When do I apply a penalty to a customer payment?</span></span>
<span data-ttu-id="b91dc-115">Vous pouvez appliquer une pénalité sur un paiement client lorsque le paiement n’est pas reçu et que la date d’échéance est passée.</span><span class="sxs-lookup"><span data-stu-id="b91dc-115">You can apply a penalty on a customer payment when the payment is not received, and it is past the due date.</span></span>

## <a name="what-documents-is-lump-sum-recovery-text-printed-on"></a><span data-ttu-id="b91dc-116">Sur quels documents le texte récupéré du montant forfaitaire est-il imprimé ?</span><span class="sxs-lookup"><span data-stu-id="b91dc-116">What documents is lump sum recovery text printed on?</span></span>
<span data-ttu-id="b91dc-117">Lorsque vous avez paramétré l’impression du texte récupéré du montant forfaitaire, le texte est imprimé sur les documents client suivants :</span><span class="sxs-lookup"><span data-stu-id="b91dc-117">After you set up the parameter to print lump sum recovery text, it is printed on the following customer documents:</span></span>

-   <span data-ttu-id="b91dc-118">Factures client</span><span class="sxs-lookup"><span data-stu-id="b91dc-118">Customer invoices</span></span>
-   <span data-ttu-id="b91dc-119">Factures financières</span><span class="sxs-lookup"><span data-stu-id="b91dc-119">Free text invoices</span></span>
-   <span data-ttu-id="b91dc-120">Factures pro forma client</span><span class="sxs-lookup"><span data-stu-id="b91dc-120">Customer proforma invoices</span></span>
-   <span data-ttu-id="b91dc-121">Avoirs du client</span><span class="sxs-lookup"><span data-stu-id="b91dc-121">Customer credit notes</span></span>




