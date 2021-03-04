---
title: Utiliser un paiement client pour régler plusieurs factures qui couvrent plusieurs périodes de remise
description: Cette rubrique montre comment plusieurs factures sont payées lorsque chaque facture est qualifiée pour un escompte de règlement. Les scénarios dans cet article illustrent la variation des escomptes de règlement qui sont pris, en fonction de la manière dont le paiement est effectué.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14511
ms.assetid: 3e42ccb5-b9d7-4a70-8db9-4206d10fd433
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7ae0bdc8245db1391103ca0f214fb3120f93f5b
ms.sourcegitcommit: e544c51a68ad5daf748c0e877bdbde094ad40bd2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4443396"
---
# <a name="use-a-customer-payment-to-settle-multiple-invoices-that-span-multiple-discount-periods"></a>Utiliser un paiement client pour régler plusieurs factures qui couvrent plusieurs périodes de remise

[!include [banner](../includes/banner.md)]

Cette rubrique montre comment plusieurs factures sont payées lorsque chaque facture est qualifiée pour un escompte de règlement. Les scénarios dans cet article illustrent la variation des escomptes de règlement qui sont pris, en fonction de la manière dont le paiement est effectué.

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

| Marquer                     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Devise | Montant à régler |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Sélectionné                 | Standard            | FTI-10040 | 4032    | 5/15/2015 | 6/15/2015 | 10040   | 1 000,00                             |                                       | USD      | 1 000,00         |
| Activé                 | Standard            | FTI-10041 | 4032    | 6/25/2015 | 7/25/2015 | 10041   | 1 000,00                             |                                       | USD      | 990,00           |
| Sélectionné et mis en surbrillance | Standard            | FTI-10042 | 4032    | 6/25/2015 | 7/25/2015 | 10042   | 1 000,00                             |                                       | USD      | 980,00           |

Une fois le paiement validé, le solde client est de 0,00.

## <a name="settle-all-invoices-on-july-1"></a>Régler toutes les factures le 1er juillet
Si Arnie crée un journal des paiements afin de régler l’intégralité de ces factures le 1er juillet, le paiement doit être de 2 980,00. Arnie crée un paiement pour le client 4032, puis ouvre la page **Régler les transactions**. Sur la page **Régler les transactions**, Arnie marque les trois lignes de facture pour règlement :

-   Le paiement pour la facture FTI-10040 est de 1 000,00. Aucun escompte de règlement n’est appliqué.
-   Le paiement pour la facture FTI-10041 est de 990,00. Un escompte de règlement de 1 %, soit 10,00, est prélevé.
-   Le paiement pour la facture FTI-10042 est de 990,00. Un escompte de règlement de 1 %, soit 10,00, est prélevé. Bien que le 1er juillet soit après la période de 2 % de remise, il se situe toujours dans la période de 1 % de remise.

| Marquer                     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Devise | Montant à régler |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Sélectionné                 | Standard            | FTI-10040 | 4032    | 5/15/2015 | 6/15/2015 | 10040   | 1 000,00                             |                                       | USD      | 1 000,00         |
| Activé                 | Standard            | FTI-10041 | 4032    | 6/25/2015 | 7/25/2015 | 10041   | 1 000,00                             |                                       | USD      | 990,00           |
| Sélectionné et mis en surbrillance | Standard            | FTI-10042 | 4032    | 6/25/2015 | 7/25/2015 | 10042   | 1 000,00                             |                                       | USD      | 990,00           |

## <a name="partial-settlement-on-june-29"></a>Règlement partiel le 29 juin
Le client 4032 peut effectuer un payement partiel, de la moitié de chaque facture. Arnie crée un paiement pour le client 4032, puis ouvre la page **Régler les transactions**. Sur la page **Régler les transactions**, Arnie marque les trois lignes de facture pour règlement. Sur chaque ligne, il entre le montant à régler, selon les instructions que le client a fournies. Lorsqu’Arnie sélectionne une ligne, il peut consulter le montant de la remise pour cette ligne et le montant de l’escompte de règlement qui est extrait. Étant donné que le client paie la moitié de la facture, Arnie constate que la valeur du champ **Montant de l’escompte de règlement** pour la facture FTI-10042 est de **20,00**, mais la valeur du champ **Escompte de règlement appliqué** est de **10,00**. Le montant du paiement est 1 485,00.

| Marquer                     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Devise | Montant à régler |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Sélectionné                 | Standard            | FTI-10040 | 4032    | 5/15/2015 | 6/15/2015 | 10040   | 1 000,00                             |                                       | USD      | 500,00           |
| Activé                 | Standard            | FTI-10041 | 4032    | 6/25/2015 | 7/25/2015 | 10041   | 1 000,00                             |                                       | USD      | 495,00           |
| Sélectionné et mis en surbrillance | Standard            | FTI-10042 | 4032    | 6/25/2015 | 7/25/2015 | 10042   | 1 000,00                             |                                       | USD      | 490,00           |

Arnie peut également saisir manuellement le montant du paiement de 1 485,00 avant d’ouvrir la page **Régler les transactions**. Si Arnie saisit manuellement le montant du paiement, puis marque les trois transactions, mais n’ajuste pas la valeur du champ **Montant à régler** pour chaque transaction, il reçoit le message suivant lorsqu’il ferme la page :

> Le montant total des transactions marquées est différent du montant du journal. Modifier le montant du journal ?

Si Arnie souhaite que le montant du paiement soit uniquement de 1 485,00, il doit cliquer sur **Non**, puis valider cette entrée dans le journal. Les transactions sont réglées de la façon suivante :

1.  La facture FTI-10040 est entièrement réglée pour 1 000,00, car elle a été entrée le 15 mai, et il s’agit de la facture la plus ancienne. Aucun escompte de règlement n’est appliqué. Le montant restant sur la transaction de paiement est de 485,00.
2.  La facture FTI-10041 n’est pas réglée du tout. Les factures FTI-10041 et FTI-10042 ont été entrées à la même date. Toutefois, une remise de 1 % est accordée pour la facture FTI-10041, et une remise de 2 % est accordée pour la facture FTI-10042. Étant donné qu’une meilleure remise est accordée pour la facture FTI-10042, le montant restant de 485,00 est réglé avec la facture FTI-10042.
3.  La facture FTI-10042 est réglée avec le montant restant de 485,00. Fabrikam offre des remises partielles. Dans ce cas, la remise est de 9,90 (= 485,00 ÷ 0,98 × 0,02). Le montant (485,00) est divisé par 0,98, car il y a une remise de 2 %, le client paie donc 98 % de la facture. Le résultat est ensuite multiplié par le pourcentage de remise, soit 2 %. Le paiement de 485,00 plus la remise de 9,90, est de 494,90. Le montant de la facture d’origine était de 1 000,00. Par conséquent, la transaction a un solde de 505,10, soit 1 000,00 – 494,90.

Arnie visualise les informations sur la page **Transactions client**.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde  | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10040  | Facture          | 5/15/2015 | 10040   | 1 000,00                             |                                       | 0,00     | USD      |
| FTI-10041  | Facture          | 6/25/2015 | 10041   | 1 000,00                             |                                       | 1 000,00 | USD      |
| FTI-10042  | Facture          | 6/25/2015 | 10042   | 1 000,00                             |                                       | 505,10   | USD      |
| ARP-10040  | Paiement          | 6/29/2015 |         |                                      | 1 485,00                              | 0,00     | USD      |
| DISC-10040 | Escompte de règlement    | 6/29/2015 |         |                                      | 9,90                                  | 0,00     | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]