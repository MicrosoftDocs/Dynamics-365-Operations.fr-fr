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
ms.openlocfilehash: 304609e065389d4f56913ae3f2f7fc562de2eadc9f0885ddbe2c8f4747081c66
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722173"
---
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a>La régularisation des achats dont le montant est nul est validée pour un reçu de produit de valeur nulle

Numéro de la base de connaissances : 4612588

## <a name="symptoms"></a>Symptômes

Lorsqu'une entrée de produit dont la valeur est nulle est validée, le système crée une écriture à la régularisation des achats où le montant est 0 (zéro).

## <a name="resolution"></a>Résolution

Par défaut, pour les écritures comptables du type *Achat, régularisation*, le champ `IsTransferredIndetail` est toujours défini sur *Résumé* dans les transactions de livres auxiliaires. Par conséquent, le système crée une écriture de pièce justificative associée même si le montant est 0 (zéro).

Pour ignorer ce type d'écriture lorsque le montant est égal à 0 (zéro), étendez la méthode `subledgerJournalizer.markDoNotTransferEntries` de manière à inclure `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, comme illustré dans l'exemple suivant.

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
