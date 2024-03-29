---
title: Régler un paiement partiel avant la date de remise avec un paiement final après la date de remise
description: Cet article détaille l’effet de la réception des paiements sur les factures pour les clients. Le scénario se concentre sur les effets dans la comptabilité auxiliaire et non dans la comptabilité.
author: ShivamPandey-msft
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14584
ms.assetid: e54936f5-053b-4ed3-b778-42c7e9aeb7cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f6b4527a9f176857e0cc6ba4665688dc8721ac1
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780483"
---
# <a name="settle-partial-payment-before-discount-date-with-final-payment-after-discount-date"></a>Régler un paiement partiel avant la date de remise avec un paiement final après la date de remise

[!include [banner](../includes/banner.md)]

Cet article détaille l’effet de la réception des paiements sur les factures pour les clients. Le scénario se concentre sur les effets dans la comptabilité auxiliaire et non dans la comptabilité.

Fabrikam vend des marchandises au client 4027. Fabrikam offre un escompte de règlement de 1 % si la facture est payée sous 14 jours. Les factures doivent être réglées dans les 30 jours. Fabrikam propose également des escomptes de règlement sur des paiements partiels. Les paramètres de règlement se trouvent dans la page **Paramètres de la comptabilité client**.

## <a name="invoice"></a>Facture
Le 25 juin, Arnie entre et valide une facture de 1 000,00 pour le client 4027. Il peut afficher cette facture en utilisant le bouton **Transactions** de la page **Clients**.

| N° document   | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde  | Devise |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10020 | Facture          | 25/06/2020 | 10020   | 1,000.00                             |                                       | 1,000.00 | EUR      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Paiement partiel avant la date de l’escompte de règlement
Le 2 juillet, le client 4027 effectue un paiement partiel de 297,00 pour la facture. Le paiement peut prétendre à un escompte de règlement, car Fabrikam propose des escomptes de règlement sur les paiements partiels, et le paiement partiel est effectué avant la date d’escompte de règlement. Par conséquent, le client 4027 bénéficie d’un escompte de règlement de 3,00. Arnie enregistre le paiement pour le client 4027 en utilisant le journal des paiements. Arnie ouvre ensuite la page **Régler les transactions** pour pouvoir marquer la facture pour règlement.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant au débit dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Sélectionné | Standard            | FTI-10020 | 4027    | 25/06/2020 | 25/07/2020 | 10020   | 1,000.00                             | EUR      | 297,00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**. Si vous ne remplacez pas la valeur du **Montant à régler** par 297,00, les valeurs du **Montant de l’escompte de règlement** qui s’affichent sont différentes. Toutefois, 3,00 sont prélevés comme escompte de règlement une fois le paiement validé, car le règlement ajuste automatiquement pour vous la valeur du **Montant à régler**.

| Champ                        | Valeur      |
|------------------------------|-----------|
| Date d’escompte de règlement           | 09/07/2020 |
| Montant de l’escompte de règlement         | 10.00     |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | 3,00      |

Arnie valide ce paiement. Le solde de la facture est maintenant de 700,00. Les transactions suivantes peuvent être affichées pour le client.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Facture          | 25/06/2020 | 10020   | 1,000.00                             |                                       | 700.00  | EUR      |
| ARP-10020  |  Paiement         | 01/07/2020  |         |                                      | 297,00                                | 0.00    | EUR      |
| DISC-10020 |  Escompte de règlement   | 01/07/2020  |         |                                      | 3.00                                  | 0.00    | EUR      |

## <a name="remaining-payment-after-the-cash-discount-date"></a>Paiement restant après la date d’escompte de règlement
Le 11 juillet, soit après la période de remise, le client 4027 paie le reste de cette facture. Dans la page **Régler les transactions**, un montant de remise ne s’affiche pas dans le champ **Escompte de règlement estimé**, et la valeur du champ **Montant de l’escompte de règlement** est **0,00**. Lorsque le client 4027 paie le restant dû de 700,00, aucune remise supplémentaire n’est appliquée.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant au débit dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Sélectionné | Standard            | FTI-10020 | 4027    | 25/06/2020 | 25/07/2020 | 10020   | 700.00                               | EUR      | 700.00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**.

| Champ                        | Valeur      |
|------------------------------|-----------|
| Date d’escompte de règlement           | 09/07/2020 |
| Montant de l’escompte de règlement         | 0.00      |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 3,00      |
| Montant de l’escompte de règlement à accepter | 0,00      |

Si Arnie remplace la valeur du champ **Utiliser un escompte de règlement** par **Toujours**, le paramètre **Calcule les escomptes de règlement pour les paiements partiels** est remplacé, et l’escompte de règlement est appliqué. Le montant du paiement passe à 693,00, et l’escompte de règlement est de 7,00, soit le montant restant.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|---------------|---------------------|----------|------------------|
| Sélectionné | Toujours            | FTI-10020 | 4027    | 25/06/2020 | 25/07/2020 | 10020   | 700.00        |                        | EUR      | 693,00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**.

| Champ                        | Valeur      |
|------------------------------|-----------|
| Date d’escompte de règlement           | 09/07/2020 |
| Montant de l’escompte de règlement         | 7.00      |
| Utiliser un escompte de règlement            | Toujours    |
| Escompte de règlement appliqué          | 3,00      |
| Montant de l’escompte de règlement à accepter | 7h00      |

Arnie rétablit la valeur du champ **Utiliser un escompte de règlement** sur **Normal**, car Arnie n’autorise pas ce client à bénéficier de l’escompte de règlement restant de 7,00. Arnie valide ensuite le paiement. Lorsqu’Arnie ouvre la page **Transactions client**, le solde de la facture est de 0,00. Deux paiements sont disponibles. Un paiement de 297,00 avec un escompte de règlement de 3,00, et un autre paiement de 700,00.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Facture          | 25/06/2020 | 10020   | 1,000.00                             |                                       | 0.00    | EUR      |
| ARP-10020  |                  | 01/07/2020  |         |                                      | 297,00                                | 0.00    | EUR      |
| DISC-10020 |                  | 01/07/2020  |         |                                      | 3.00                                  | 0.00    | EUR      |
| ARP-10021  |                  | 11/07/2020 |         |                                      | 700.00                                | 0.00    | EUR      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
