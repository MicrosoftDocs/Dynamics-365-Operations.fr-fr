---
title: Utiliser un paiement pour régler les factures qui couvrent plusieurs périodes de remise
description: Cet article montre comment plusieurs factures sont payées lorsque chaque facture est qualifiée pour un escompte de règlement. Les scénarios dans cet article illustrent la variation des escomptes de règlement qui sont pris, en fonction de la manière dont le paiement est effectué.
author: ShivamPandey-msft
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14511
ms.assetid: 3e42ccb5-b9d7-4a70-8db9-4206d10fd433
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6bf321a5b0511295f2500f10cdffa9ff6f043bff
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780546"
---
# <a name="use-one-payment-to-settle-invoices-that-span-multiple-discount-periods"></a>Utiliser un paiement pour régler les factures qui couvrent plusieurs périodes de remise

[!include [banner](../includes/banner.md)]

Cet article montre comment plusieurs factures sont payées lorsque chaque facture est qualifiée pour un escompte de règlement. Les scénarios dans cet article illustrent la variation des escomptes de règlement qui sont pris, en fonction de la manière dont le paiement est effectué.

Fabrikam vend des marchandises au client 4032. Fabrikam offre un escompte de règlement de 1 % si la facture est payée sous 14 jours. Fabrikam propose également des escomptes de règlement sur des paiements partiels. Les paramètres de règlement se trouvent dans la page **Paramètres de la comptabilité client**.

## <a name="invoices"></a>Factures
Le client 4032 a trois factures pour un total de 3 000,00 :

-   La facture FTI-10040, de 1 000,00, a été entrée le 15 mai. Cette facture est éligible pour un escompte de règlement de 1 % si elle est payée dans les 14 jours.
-   La facture FTI-10041, de 1 000,00, a été entrée le 25 juin. Cette facture est éligible pour un escompte de règlement de 1 % si elle est payée dans les 14 jours.
-   La facture FTI-10042, de 1 000,00, a été entrée le 25 juin. Cette facture est éligible pour un escompte de règlement de 2 % si elle est payée dans les cinq jours, et de 1 % si elle est payée dans les 14 jours.

## <a name="settle-all-invoices-on-june-29"></a>Régler toutes les factures le 29 juin
Si Arnie crée un journal des paiements afin de régler l’intégralité de ces factures le 29 juin, le paiement doit être de 2 970,00. Le montant total de la remise s’élève à 30,00. Arnie crée un paiement pour le client 4032, puis ouvre la page **Régler les transactions**. Sur la page **Régler les transactions**, Arnie marque les trois lignes de facture pour règlement :

-   Le paiement pour la facture FTI-10040 est de 1 000,00. Aucun escompte de règlement n’est appliqué.
-   Le paiement pour la facture FTI-10041 est de 990,00. Un escompte de règlement de 1 %, soit 10,00, est prélevé.
-   Le paiement pour la facture FTI-10042 est de 980,00. Un escompte de règlement de 2 %, soit 20,00, est prélevé.

| Marquer | Utiliser un escompte de règlement | N° document   | Compte | Date   | Date d’échéance  | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Devise | Montant à régler |
|------|----------|-----------|---------|-----------|-----------|---------|---------------------|---------------------|----------|------------------|
| Sélectionné     | Standard      | FTI-10040 | 4032    | 15/05/2020 | 15/06/2020 | 10040   | 1,000.00  |                    | EUR      | 1,000.00         |
| Sélectionné     | Standard      | FTI-10041 | 4032    | 25/06/2020 | 25/07/2020 | 10041   | 1,000.00  |                    | EUR      | 990.00           |
| Sélectionné et mis en surbrillance | Standard      | FTI-10042 | 4032    | 25/06/2020 | 25/07/2020 | 10042   | 1,000.00    |              | EUR      | 980.00           |

Une fois le paiement validé, le solde client est de 0,00.

## <a name="settle-all-invoices-on-july-1"></a>Régler toutes les factures le 1er juillet
Si Arnie crée un journal des paiements afin de régler l’intégralité de ces factures le 1er juillet, le paiement doit être de 2 980,00. Arnie crée un paiement pour le client 4032, puis ouvre la page **Régler les transactions**. Sur la page **Régler les transactions**, Arnie marque les trois lignes de facture pour règlement :

-   Le paiement pour la facture FTI-10040 est de 1 000,00. Aucun escompte de règlement n’est appliqué.
-   Le paiement pour la facture FTI-10041 est de 990,00. Un escompte de règlement de 1 %, soit 10,00, est prélevé.
-   Le paiement pour la facture FTI-10042 est de 990,00. Un escompte de règlement de 1 %, soit 10,00, est prélevé. Bien que le 1er juillet soit après la période de 2 % de remise, il se situe toujours dans la période de 1 % de remise.

| Marquer                     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Devise | Montant à régler |
|----------|---------|-----------|---------|-----------|-----------|---------|--------------------|------------------|----------|------------------|
| Sélectionné         | Standard            | FTI-10040 | 4032    | 15/05/2020 | 15/06/2020 | 10040   | 1,000.00         |                | EUR      | 1,000.00         |
| Sélectionné                 | Standard            | FTI-10041 | 4032    | 25/06/2020 | 25/07/2020 | 10041   | 1,000.00  |               | EUR      | 990.00           |
| Sélectionné et mis en surbrillance | Standard            | FTI-10042 | 4032    | 25/06/2020 | 25/07/2020 | 10042   | 1,000.00  |             | EUR      | 990.00           |

## <a name="partial-settlement-on-june-29"></a>Règlement partiel le 29 juin
Le client 4032 peut effectuer un payement partiel, de la moitié de chaque facture. Arnie crée un paiement pour le client 4032, puis ouvre la page **Régler les transactions**. Sur la page **Régler les transactions**, Arnie marque les trois lignes de facture pour règlement. Sur chaque ligne, Arnie entre le montant à régler, selon les instructions que le client a fournies. Lorsqu’Arnie sélectionne une ligne, Arnie peut consulter le montant de la remise pour cette ligne et le montant de l’escompte de règlement qui est extrait. Étant donné que le client paie la moitié de la facture, Arnie constate que la valeur du champ **Montant de l’escompte de règlement** pour la facture FTI-10042 est de **20,00**, mais la valeur du champ **Escompte de règlement appliqué** est de **10,00**. Le montant du paiement est 1 485,00.

| Marquer   | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Devise | Montant à régler |
|-------------|-------------------|-----------|---------|-----------|-----------|---------|-----------|------------------|----------|------------------|
| Sélectionné   | Standard       | FTI-10040 | 4032    | 15/05/2020 | 15/06/2020 | 10040   | 1,000.00        |               | EUR      | 500.00           |
| Sélectionné                 | Standard            | FTI-10041 | 4032    | 25/06/2020 | 25/07/2020 | 10041   | 1,000.00     |     | EUR      | 495,00           |
| Sélectionné et mis en surbrillance | Standard            | FTI-10042 | 4032    | 25/06/2020 | 25/07/2020 | 10042   | 1,000.00     |         | EUR      | 490,00           |

Arnie peut également entrer manuellement le montant du paiement de 1 485,00 avant l’ouverture de la page **Régler les transactions**. Si Arnie saisit manuellement le montant du paiement, puis marque les trois transactions, mais n’ajuste pas la valeur du champ **Montant à régler** pour chaque transaction, Arnie reçoit le message suivant lorsque la page se ferme :

> Le montant total des transactions marquées est différent du montant du journal. Modifier le montant du journal ?

Si Arnie souhaite que le montant du paiement soit uniquement de 1 485,00, Arnie clique sur **Non**, puis valider cette entrée dans le journal. Les transactions sont réglées de la façon suivante :

1.  La facture FTI-10040 est entièrement réglée pour 1 000,00, car elle a été entrée le 15 mai, et il s’agit de la facture la plus ancienne. Aucun escompte de règlement n’est appliqué. Le montant restant sur la transaction de paiement est de 485,00.
2.  La facture FTI-10041 n’est pas réglée du tout. Les factures FTI-10041 et FTI-10042 ont été entrées à la même date. Toutefois, une remise de 1 % est accordée pour la facture FTI-10041, et une remise de 2 % est accordée pour la facture FTI-10042. Étant donné qu’une meilleure remise est accordée pour la facture FTI-10042, le montant restant de 485,00 est réglé avec la facture FTI-10042.
3.  La facture FTI-10042 est réglée avec le montant restant de 485,00. Fabrikam offre des remises partielles. Dans ce cas, la remise est de 9,90 (= 485,00 ÷ 0,98 × 0,02). Le montant (485,00) est divisé par 0,98, car il y a une remise de 2 %, le client paie donc 98 % de la facture. Le résultat est ensuite multiplié par le pourcentage de remise, soit 2 %. Le paiement de 485,00 plus la remise de 9,90, est de 494,90. Le montant de la facture d’origine était de 1 000,00. Par conséquent, la transaction a un solde de 505,10, soit 1 000,00 – 494,90.

Arnie visualise les informations sur la page **Transactions client**.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde  | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10040  | Facture          | 15/05/2020 | 10040   | 1,000.00                             |                                       | 0.00     | EUR      |
| FTI-10041  | Facture          | 25/06/2020 | 10041   | 1,000.00                             |                                       | 1,000.00 | EUR      |
| FTI-10042  | Facture          | 25/06/2020 | 10042   | 1,000.00                             |                                       | 505,10   | EUR      |
| ARP-10040  | Paiement          | 29/06/2020 |         |                                      | 1 485,00                              | 0.00     | EUR      |
| DISC-10040 | Escompte de règlement    | 29/06/2020 |         |                                      | 9,90                                  | 0.00     | EUR      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
