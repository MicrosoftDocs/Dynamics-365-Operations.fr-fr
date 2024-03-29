---
title: Règlement d’un paiement partiel et règlement total du paiement final avant la date de remise
description: Cet article fournit des scénarios qui indiquent comment enregistrer des paiements partiels pour un client et prendre des escomptes de règlement pendant la période d’escompte de règlement.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 14491
ms.assetid: 0f07d3ce-a439-43ed-a22e-957ccd36a37b
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
ms.openlocfilehash: a8da366b1e770ea649603ae85d4acc5e377ed9fb
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780495"
---
# <a name="settle-partial-and-final-payments-in-full-before-the-discount-date"></a>Règlement d’un paiement partiel et règlement total du paiement final avant la date de remise

[!include [banner](../includes/banner.md)]

Cet article fournit des scénarios qui indiquent comment enregistrer des paiements partiels pour un client et prendre des escomptes de règlement pendant la période d’escompte de règlement.

Fabrikam vend des marchandises au client 4028. Fabrikam offre un escompte de règlement de 1 % si la facture est payée sous 14 jours. Les factures doivent être réglées dans les 30 jours. Fabrikam propose également des escomptes de règlement sur des paiements partiels. Les paramètres de règlement se trouvent dans la page **Paramètres de la comptabilité client**.

## <a name="customer-invoice"></a>Facture client
Le 25 juin, Arnie entre et valide une facture de 1 000,00 pour le client 4028. Arnie peut afficher cette transaction sur la page **Transactions client**.

| N° document   | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde  | Devise |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10010 | Facture          | 25/06/2020 | 10010   | 1,000.00                             |                                       | 1,000.00 | EUR      |

Depuis la page **Client** ou **Transactions client**, Arnie peut ouvrir la page **Régler les transactions** pour afficher les dates et les montants des escomptes de règlement disponibles pour la facture. La date d’échéance est le 25 juillet, et un escompte de règlement de 10,00 est disponible si la facture est payée avant le 9 juillet.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | FTI-10010 | 4028    | 25/06/2020 | 25/07/2020 | 10010   | 1,000.00                       | EUR      | 990.00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions** pour la facture marquée.

|    &nbsp;                    |  &nbsp;   |
|------------------------------|-----------|
| Date d’escompte de règlement           | 09/07/2020 |
| Montant de l’escompte de règlement         | 10.00     |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | 10,00     |

Arnie clique sur l’onglet **Escompte de règlement** pour afficher le montant de la remise.

| Date d’escompte de règlement | Montant de l’escompte de règlement | Montant dans la devise de transaction |
|--------------------|----------------------|--------------------------------|
| 09/07/2020           | 10.00                | 990.00                         |
| 25/07/2020          | 0.00                 | 1,000.00                       |

## <a name="partial-payment-by-using-the-enter-customer-payments-page"></a>Paiement partiel de 500,00 le 1er juillet à l’aide de la page Entrer les paiements client
Le client 4028 envoie un paiement de 500,00 le 1er juillet. Pour entrer ce paiement, Arnie ne clique pas sur **Lignes**. Au lieu de cela, Arnie enregistre le paiement en créant un journal des paiements, puis en ouvrant la page **Entrer les paiements client**. Arnie entre les informations de paiement et marque la facture qu’il a entrée. Lorsque Arnie entre **500,00** comme montant, il entre également **500,00** dans le champ **Montant à payer** de la grille. Puisque Fabrikam accorde un escompte de règlement pour les paiements partiels, Arnie constate qu’un escompte de règlement partiel de 5,05 sera également prélevé. Le calcul de cette remise est de 500,00 ÷ 0,99 × 0,01 = 5,05. (Dans ce calcul, 500,00 est divisé par 0,99 %, car il y a une remise de 1 %. Par conséquent, le client paie 99 % de la facture. Le résultat est ensuite multiplié par le pourcentage de remise, soit 1 % ou 0,01. Si le client prend la remise totale de 10,00, le montant qui doit être réglé est 990,00.) Les informations de remise s’affichent dans la grille en bas de la page **Entrer les paiements client**.

| Montant de l’escompte de règlement à accepter | Escompte de règlement appliqué | Montant à payer |
|------------------------------|---------------------|---------------|
| 5,05                         | 0,00                | 500,00        |

## <a name="partial-payment-by-using-the-journal-lines"></a>Paiement partiel à l’aide des lignes de journal
Au lieu d’ouvrir la page **Entrer les paiements client** dans le journal des paiements, Arnie peut cliquer sur **Lignes** pour entrer un paiement. Le journal des paiements s’affiche, dans lequel Arnie peut entrer une ligne pour le client 4028. Arnie ouvre ensuite la page **Régler les transactions** pour pouvoir marquer la facture pour règlement. Arnie marque la facture et remplace la valeur du champ **Montant à régler** par **500,00**. Arnie constate à nouveau que la valeur du champ **Montant de l’escompte de règlement** est de **10,00** pour la facture complète, et que la valeur du champ **Montant de l’escompte de règlement à accepter** est de **5,05**. Par conséquent, il règle 505,05 de cette facture.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | FTI-10010 | 4028    | 25/06/2020 | 25/07/2020 | 10010   | 1,000.00                       | EUR      | 500.00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**.

|        &nbsp;                | &nbsp;    |
|------------------------------|-----------|
| Date d’escompte de règlement           | 09/07/2020 |
| Montant de l’escompte de règlement         | 10.00     |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | 5,05      |

Si le client souhaite régler précisément la moitié de la facture, il effectue un paiement de 495,00. Dans ce cas, Arnie entre **495,00** dans le champ **Montant à régler**. L’escompte de règlement de 5,00 sera également appliqué, de sorte que le montant total réglé s’élève à 500,00.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | FTI-10010 | 4028    | 25/06/2020 | 25/07/2020 | 10010   | 1,000.00                       | EUR      | 495,00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**.

|     &nbsp;                   | &nbsp;    |
|------------------------------|-----------|
| Date d’escompte de règlement           | 09/07/2020 |
| Montant de l’escompte de règlement         | 10.00     |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | 5,00      |

Arnie ferme la page **Régler les transactions**. Une ligne de paiement pour 495,00 est créée dans le journal, puis Arnie valide le journal. Arnie peut consulter les transactions client sur la page **Transactions client**. Sur cette page, Arnie constate que la facture a un solde de 500,00. Arnie voit également un paiement de 495,00 et une remise de 5,00.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Facture          | 25/06/2020 | 10010   | 1,000.00                             |                                       | 500.00  | EUR      |
| ARP-10010  |  Paiement         | 01/07/2020  |         |                                      | 495,00                                | 0.00    | EUR      |
| DISC-10010 |  Escompte de règlement   | 01/07/2020  |         |                                      | 5.00                                  | 0.00    | EUR      |

## <a name="payment-for-the-remaining-amount"></a>Paiement pour le montant restant
Le client 4028 paie le solde de 495,00 le 8 juillet, soit au cours de la période d’escompte de règlement. Arnie crée le journal des paiements le 8 juillet et marque la transaction pour règlement. Arnie constate que le montant à régler est 495,00. La valeur du champ **Escompte de règlement estimé** est **5,00**, car la remise de 5,00 a été prélevée précédemment.

|   &nbsp;                | &nbsp; |
|-------------------------|--------|
| Total marqué            | 495,00 |
| Escompte de règlement estimé | 5,00   |

Des informations sur la transaction marquée sont affichées dans la grille sur la page **Régler les transactions en cours**.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | FTI-10010 | 4028    | 25/06/2020 | 25/07/2020 | 10010   | 1,000.00                       | EUR      | 495,00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**.

|  &nbsp;                      |  &nbsp;   |
|------------------------------|-----------|
| Date d’escompte de règlement           | 09/07/2020 |
| Montant de l’escompte de règlement         | 10.00     |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 5,00      |
| Montant de l’escompte de règlement à accepter | 5,00      |

Arnie valide ce journal et consulte les transactions client sur la page **Transactions client**. Le solde de la facture est à présent de 0,00, et il voit les deux paiements et les deux escomptes de règlement.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Facture          | 25/06/2020 | 10010   | 1,000.00                             |                                       | 0.00    | EUR      |
| ARP-10010  | Paiement          | 01/07/2020  |         |                                      | 495,00                                | 0.00    | EUR      |
| DISC-10010 | Escompte de règlement    | 01/07/2020  |         |                                      | 5.00                                  | 0.00    | EUR      |
| ARP-10011  | Paiement          | 08/07/2020  |         |                                      | 495,00                                | 0.00    | EUR      |
| DISC-10011 | Escompte de règlement    | 08/07/2020  |         |                                      | 5.00                                  | 0.00    | EUR      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
