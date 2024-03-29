---
title: Régler un paiement partiel client ayant des remises sur les avoirs
description: Cet article vous fait parcourir les étapes d’un scénario où un escompte de règlement est prélevé sur un avoir lorsque la facture d’origine a également bénéficié d’un escompte de règlement.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14564
ms.assetid: d9984cef-ddcf-46bd-816d-c01b8cc5cf48
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44f64b9b9cd4fa65d17ba30fb87a688411becd5a
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780494"
---
# <a name="settle-a-partial-customer-payment-that-has-discounts-on-credit-notes"></a>Régler un paiement partiel client ayant des remises sur les avoirs

[!include [banner](../includes/banner.md)]

Cet article vous fait parcourir les étapes d’un scénario où un escompte de règlement est prélevé sur un avoir lorsque la facture d’origine a également bénéficié d’un escompte de règlement. 

Fabrikam propose aux clients des escomptes de règlement sur les paiements partiels ainsi que sur les avoirs. Un escompte de règlement peut être appliqué à un avoir lorsque l’avoir est émis pour une facture sur laquelle le client a bénéficié d’un escompte de règlement. Au lieu d’accorder un crédit pour le montant total, vous pouvez créditer le solde du client pour un montant qui exclut le pourcentage d’escompte de règlement appliqué au client. Les paramètres de règlement se trouvent dans la page **Paramètres de la comptabilité client**.

## <a name="invoice-and-credit-note"></a>Facture et avoir
Le client 4035 a une facture de 1 000,00 et un avoir de 100,00. Pour chaque document, une remise de 1 % est appliquée s’il paie dans les 14 jours. Arnie peut afficher ces informations dans la page **Transactions client**.

| N° document    | Type de transaction | Date      | Facture  | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde  | Devise |
|------------|------------------|-----------|----------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10050  | Facture          | 28/06/2020 | 10050    | 1,000.00                             |                                       | 1,000.00 | EUR      |
| CCRN-10050 | Avoir      | 28/06/2020 | CR-10050 |                                      | 100.00                                | -100,00  | EUR      |

## <a name="settle-a-credit-note-with-an-invoice"></a>Régler un avoir avec une facture
Dans la page **Transactions client**, Arnie ouvre la page **Régler les transactions**. Arnie peut utiliser la page **Régler les transactions** pour régler la facture et l’avoir. Dans le cadre du processus de règlement, Arnie affiche les dates et les montants d’escompte de règlement. Arnie marque les deux documents, puis clique sur **Valider** pour régler les transactions. Il y a une remise de -1,00 sur l’avoir, car Fabrikam autorise les remises sur les avoirs.

| Marquer     | Utiliser un escompte de règlement | N° document    | Compte | Date      | Date d’échéance  | Facture  | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|------------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | FTI-10050  | 4035    | 28/06/2020 | 28/07/2020 | 10050    | 1,000.00                       | EUR      | 990.00           |
| Sélectionné | Standard            | CCRN-10050 | 4035    | 28/06/2020 | 28/07/2020 | CR-10050 | -100,00                        | EUR      | -99,00           |

Les informations de remise s’affichent au bas de la page **Règlement des transactions**.

- **Date d’escompte de règlement** : 12/07/2020 
- **Date d’escompte de règlement** : -1,00     
- **Utiliser un escompte de règlement** : Normal    
- **Escompte de règlement appliqué** : 0,00      
- **Montant de l’escompte de règlement à accepter** : -1,00     

Le règlement sera de 100,00, et inclura un paiement de 99,00 et une remise de 1,00.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
