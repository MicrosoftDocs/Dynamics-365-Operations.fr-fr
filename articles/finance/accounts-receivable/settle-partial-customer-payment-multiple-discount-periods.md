---
title: Règlement d’un paiement client partiel avec plusieurs périodes de remise
description: Cet article décrit la manière dont les paiements client partiels sont réglés lorsqu’il existe plusieurs périodes de remise.
author: ShivamPandey-msft
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14471
ms.assetid: b633a7c4-c18d-42e7-91cc-adcdc8a3ba98
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62defda8831d2915050fc6822f60a905f067fe88
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778437"
---
# <a name="settle-a-partial-customer-payment-that-has-multiple-discount-periods"></a>Règlement d’un paiement client partiel avec plusieurs périodes de remise

[!include [banner](../includes/banner.md)]

Cet article décrit la manière dont les paiements client partiels sont réglés lorsqu’il existe plusieurs périodes de remise.

Fabrikam propose à son client 4031 deux périodes d’escompte de règlement. Le client bénéficie d’un escompte de règlement de 2 % si la facture est payée dans les cinq jours et d’un escompte de règlement de 1 % si la facture est payée dans les 14 jours. Fabrikam propose également des escomptes de règlement sur des paiements partiels. Les paramètres de règlement se trouvent dans la page **Paramètres de la comptabilité client**.

## <a name="invoice"></a>Facture
Le 25 juin, Arnie entre et valide une facture de 1 000,00 pour le client 4031. Lorsque Arnie vérifie les escomptes de règlement pour la facture, il constate que le client 4031 reçoit une remise de 20,00 % si la facture est payée avant le 30 juin. Si la facture est payée avant le 9 juillet, le client reçoit une remise de 10,00 %.

| Date d’escompte de règlement | Montant de l’escompte de règlement | Montant dans la devise de transaction |
|--------------------|----------------------|--------------------------------|
| 30/06/2020          | 20.00                | 980.00                         |
| 09/07/2020           | 10.00                | 990.00                         |
| 25/07/2020          | 0.00                 | 1,000.00                       |

Arnie peut afficher cette transaction sur la page **Transactions client**.

| N° document   | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde  | Devise |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10030 | Facture          | 25/06/2020 | 10030   | 1,000.00                             |                                       | 1,000.00 | EUR      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Paiement partiel avant la date de l’escompte de règlement
Le 28 juin, le client 4031 fait un paiement partiel à hauteur de 294,00. Comme le 28 juin se situe durant la première période d’escompte de règlement, le client bénéficie d’une remise de 6,00. Sur la page **Régler les transactions**, la valeur du **Montant de l’escompte de règlement** est 20,00 et la valeur du **Montant de l’escompte de règlement à accepter** est 6,00.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | FTI-10030 | 4031    | 25/06/2020 | 25/07/2020 | 10030   | 1,000.00                       | EUR      | 294,00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**. Si vous ne modifiez pas la valeur du **Montant à régler** par **294,00**, les valeurs du **Montant de l’escompte de règlement** qui s’affichent seront différentes. Toutefois, 6,00 seront prélevés comme escompte de règlement une fois le paiement validé, car le règlement ajuste automatiquement pour vous la valeur du **Montant à régler**.

| &nbsp;                       | &nbsp;    |
|------------------------------|-----------|
| Date d’escompte de règlement           | 30/06/2020 |
| Montant de l’escompte de règlement         | 20.00     |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | 6,00      |

Après qu’Arnie a validé le paiement, le solde de la facture est de 700,00 €.

## <a name="partial-payment-before-the-second-cash-discount-date"></a>Paiement partiel avant la seconde date de l’escompte de règlement
Le 8 juillet, le client paie le reste du montant de la facture. Une remise de 7,00 (1 %) est prélevée, le paiement étant effectué durant la seconde période de l’escompte de règlement.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------|-----------------------|----------|------------------|
| Sélectionné | Standard            | FTI-10030 | 4031    | 25/06/2020 | 25/07/2020 | 10030   | 700.00       |            | EUR      | 693,00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**.

| &nbsp;                       | &nbsp;    |
|------------------------------|-----------|
| Date d’escompte de règlement           | 09/07/2020 |
| Montant de l’escompte de règlement         | 30.00     |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 6,00      |
| Montant de l’escompte de règlement à accepter | 7h00      |

Le solde de la facture est désormais de 0,00. Arnie visualise les informations sur la page **Transactions client**.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10030  | Facture          | 25/06/2020 | 10030   | 1,000.00                             |                                       | 0.00    | EUR      |
| ARP-10030  |  Paiement         | 28/06/2020 |         |                                      | 294,00                                | 0.00    | EUR      |
| DISC-10030 |  Escompte de règlement   | 28/06/2020 |         |                                      | 6,00                                  | 0.00    | EUR      |
| ARP-10031  |  Paiement         | 08/07/2020  |         |                                      | 693,00                                | 0.00    | EUR      |
| DISC-1031  |  Escompte de règlement   | 08/07/2020  |         |                                      | 7.00                                  | 0.00    | EUR      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
