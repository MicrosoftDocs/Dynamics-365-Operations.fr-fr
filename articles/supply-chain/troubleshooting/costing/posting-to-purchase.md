---
title: La régularisation des achats dont le montant est nul est validée pour un reçu de produit de valeur nulle
description: Lorsqu'une entrée de produit dont la valeur est nulle est validée, le système crée une écriture à la régularisation des achats où le montant est 0 (zéro).
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f8d9d857590dc788d16b01edf77600d8fd8c8444
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026523"
---
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a><span data-ttu-id="096eb-103">La régularisation des achats dont le montant est nul est validée pour un reçu de produit de valeur nulle</span><span class="sxs-lookup"><span data-stu-id="096eb-103">Purchase accrual that has a zero amount is posted for a zero-value product receipt</span></span>

<span data-ttu-id="096eb-104">Numéro de la base de connaissances : 4612588</span><span class="sxs-lookup"><span data-stu-id="096eb-104">KB number: 4612588</span></span>

## <a name="symptoms"></a><span data-ttu-id="096eb-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="096eb-105">Symptoms</span></span>

<span data-ttu-id="096eb-106">Lorsqu'une entrée de produit dont la valeur est nulle est validée, le système crée une écriture à la régularisation des achats où le montant est 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="096eb-106">When a product receipt that has zero value is posted, the system creates a posting to purchase accrual where the amount is 0 (zero).</span></span>

## <a name="resolution"></a><span data-ttu-id="096eb-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="096eb-107">Resolution</span></span>

<span data-ttu-id="096eb-108">Par défaut, pour les écritures comptables du type *Achat, régularisation*, le champ `IsTransferredIndetail` est toujours défini sur *Résumé* dans les transactions de livres auxiliaires.</span><span class="sxs-lookup"><span data-stu-id="096eb-108">By default, for ledger postings of the *Purchase, accrual* type, the `IsTransferredIndetail` field is always set to *Summary* in subledger transactions.</span></span> <span data-ttu-id="096eb-109">Par conséquent, le système crée une écriture de pièce justificative associée même si le montant est 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="096eb-109">Therefore, the system creates a related voucher entry even if the amount is 0 (zero).</span></span>

<span data-ttu-id="096eb-110">Pour ignorer ce type d'écriture lorsque le montant est égal à 0 (zéro), étendez la méthode `subledgerJournalizer.markDoNotTransferEntries` de manière à inclure `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, comme illustré dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="096eb-110">To skip this posting type when the amount is 0 (zero), extend the `subledgerJournalizer.markDoNotTransferEntries` method so that it includes `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, as shown in the following example.</span></span>

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
