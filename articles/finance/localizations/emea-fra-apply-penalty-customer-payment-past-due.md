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
ms.openlocfilehash: 1e6efb8b081d6050d6c68a6f3896aa45ce59281e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260171"
---
# <a name="penalties-for-past-due-customer-payments-in-france"></a>Pénalités pour les paiements client en retard en France

[!include [banner](../includes/banner.md)]

En France, vous pouvez appliquer une pénalité lorsqu’un paiement client est en retard et vous pouvez imprimer le texte de récupération de la somme forfaitaire qui affiche le montant de pénalité qui doit être payé sur la facture ainsi que la date d’échéance du paiement. 

<a name="what-is-lump-sum-recovery-text"></a>Qu’est-ce que le texte récupéré du montant forfaitaire ?
-------------------------------

Le texte récupéré du montant forfaitaire affiche le montant de pénalité et la date d’échéance du paiement. Le montant de pénalité est appliqué si le paiement a lieu après la date d’échéance. Le texte récupéré du montant forfaitaire est imprimé sur la facture client. Vous pouvez spécifier le montant de pénalité et la devise avec toute instruction dans le champ Texte récupéré du montant forfaitaire de la zone Facture de l’écran Paramétrage d’écran.

## <a name="how-do-i-print-lump-sum-recovery-text-on-a-customer-invoice"></a>Comment imprimer le texte récupéré du montant forfaitaire sur une facture client ?
Vous pouvez déjà utiliser l’écran Paramétrage d’écran pour définir les paramètres d’impression du texte récupéré du montant forfaitaire. Ensuite, vous pouvez utiliser la page Validation de la facture ou la page Journal des factures pour imprimer le texte récupéré du montant forfaitaire sur une facture client. Pour plus d’informations voir [Imprimer un texte récupéré de montant forfaitaire sur une facture client](emea-fra-print-lump-sum-recovery-text.md).

## <a name="when-do-i-apply-a-penalty-to-a-customer-payment"></a>Quand appliquer une pénalité à un paiement client ?
Vous pouvez appliquer une pénalité sur un paiement client lorsque le paiement n’est pas reçu et que la date d’échéance est passée.

## <a name="what-documents-is-lump-sum-recovery-text-printed-on"></a>Sur quels documents le texte récupéré du montant forfaitaire est-il imprimé ?
Lorsque vous avez paramétré l’impression du texte récupéré du montant forfaitaire, le texte est imprimé sur les documents client suivants :

-   Factures client
-   Factures financières
-   Factures pro forma client
-   Avoirs du client






[!INCLUDE[footer-include](../../includes/footer-banner.md)]