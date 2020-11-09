---
title: Règlement d'un paiement fournisseur partiel et règlement total du paiement final avant la date de remise
description: Cet article vous fait parcourir les étapes d'un scénario dans lequel des paiements partiels sont effectués pour une facture fournisseur et un escompte de règlement est prélevé.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14431
ms.assetid: 6b8e3420-b4c9-4e02-9588-598fe6d3df0d
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 202d6e8b0933522c2faf5fb49291f11200e4754f
ms.sourcegitcommit: d61c43b6bc04bb8786aa3c47932be0ccd84ebaeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/14/2020
ms.locfileid: "4006139"
---
# <a name="settle-a-partial-vendor-payment-and-the-final-payment-in-full-before-the-discount-date"></a>Règlement d'un paiement fournisseur partiel et règlement total du paiement final avant la date de remise

[!include [banner](../includes/banner.md)]

Cet article vous fait parcourir les étapes d'un scénario dans lequel des paiements partiels sont effectués pour une facture fournisseur et un escompte de règlement est prélevé.

Fabrikam achète des marchandises au fournisseur 3064. Le fournisseur accorde à Fabrikam un escompte de règlement de 1 % si la facture est payée sous 14 jours. Les factures doivent être réglées dans les 30 jours. Le fournisseur offre également à Fabrikam des escomptes de règlement en cas de paiements partiels. Les paramètres de règlement sont situés dans la page **Paramètres de la comptabilité fournisseur**. Le 25 juin, April entre une facture de 1 000,00 pour le fournisseur 3064.

## <a name="vendor-invoice-on-june-25"></a>Facture fournisseur du 25 juin
Le 25 juin, April entre et valide une facture de 1 000,00 pour le fournisseur 3064. Elle peut consulter cette transaction sur la page **Transactions fournisseur**.

| N° document   | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde   | Devise |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10010 | 6/25/2015 | 10010   |                                      | 1 000,00                              | -1 000,00 | USD      |

Dans la page **Fournisseurs** , April ouvre la page **Règlement des transactions**. Elle peut utiliser la page **Régler les transactions** pour afficher les dates et les montants des escomptes de règlement. La date d'échéance est le 25 juillet, et un escompte de règlement de -10,00 peut être appliqué si la facture est payée avant le 9 juillet.

| Marquer | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d'échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Standard            | Inv-10010 | 3064    | 6/25/2015 | 7/25/2015 | 10010   | 1 000,00                       | USD      | 990,00           |

Les informations sur la remise sont affichées au bas de la page **Régler les transactions en cours**.

|       &nbsp;                 | &nbsp;    |
|------------------------------|-----------|
| Date d'escompte de règlement           | 7/09/2015 |
| Montant de l'escompte de règlement         | -10,00    |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l'escompte de règlement à accepter | -10,00    |

April clique sur l'onglet **Escompte de règlement** pour afficher le montant de la remise.

| Date d'escompte de règlement | Montant de l'escompte de règlement | Montant dans la devise de transaction |
|--------------------|----------------------|--------------------------------|
| 7/9/2015           | 10,00                | 990,00                         |
| 7/25/2015          | 0,00                 | 1 000,00                       |

## <a name="partial-payment-on-july-1-by-using-the-settle-transactions-page"></a>Paiement partiel le 1er juillet à l'aide de la page Régler les transactions
April peut créer un journal des paiements pour ce paiement en ouvrant la page **Journal des paiements** du module Achats. Elle crée un journal de paiement et entre une ligne pour le fournisseur 3064. Elle ouvre ensuite la page **Régler les transactions** , afin de pouvoir marquer la facture pour règlement. April marque la facture et remplace la valeur du champ **Montant à régler** par **-500,00**. Elle constate que la valeur du champ **Montant de l'escompte de règlement** est **-10,00** pour la facture complète, et que la valeur du champ **Montant de l'escompte de règlement à accepter** est **-5,05**. Par conséquent, April règle -505,05 de cette facture.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d'échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1 000,00                       | USD      | -500,00          |

Les informations de remise s'affichent au bas de la page **Régler les transactions en cours**.

|  &nbsp;                      |  &nbsp;   |
|------------------------------|-----------|
| Date d'escompte de règlement           | 7/09/2015 |
| Montant de l'escompte de règlement         | -10,00    |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l'escompte de règlement à accepter | -5,05     |

April souhaite régler précisément la moitié de la facture. Par conséquent, elle modifie la valeur du champ **Montant à régler** par **-495,00**. Le montant total qui est réglé est désormais 500,00. Ce montant inclut l'escompte de règlement de -5,00.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d'échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1 000,00                       | USD      | -495,00          |

Les informations de remise s'affichent au bas de la page **Régler les transactions en cours**.

|  &nbsp;                      |  &nbsp;   |
|------------------------------|-----------|
| Date d'escompte de règlement           | 7/09/2015 |
| Montant de l'escompte de règlement         | -10,00    |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l'escompte de règlement à accepter | -5,00     |

April ferme la page **Régler les transactions**. Une ligne de paiement pour 495,00 est créée dans le journal, puis April valide le journal. Elle peut consulter les transactions fournisseur dans la page **Transactions fournisseur**. Elle constate que la facture a un solde de -500,00. Elle voit également un paiement de 495,00 et un escompte de règlement de 5,00.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | Facture          | 6/25/2015 | 10010   |                                      | 1 000,00                              | -500,00 | USD      |
| APP-10010  | Paiement          | 7/1/2015  |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10010 | Escompte de règlement    | 7/1/2015  |         | 5,00                                 |                                       | 0,00    | USD      |

## <a name="remaining-amount-paid-on-july-8"></a>Montant restant payé le 8 juillet
April paie le reste de la facture au fournisseur 3064 le 8 juillet, soit au cours de la période d'escompte de règlement. April crée le journal des paiements le 8 juillet et marque la transaction pour règlement. Elle constate que le montant à régler est 495,00. La valeur du champ **Escompte de règlement estimé** est **-5,00** , car la remise de 5,00 a été prélevée précédemment.

|  &nbsp;                 |  &nbsp; |
|-------------------------|--------|
| Total marqué            | 495,00 |
| Escompte de règlement estimé | -5,00  |

Des informations sur la transaction marquée sont affichées dans la grille sur la page **Régler les transactions en cours**.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d'échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1 000,00                       | USD      | 495,00           |

Les informations de remise s'affichent au bas de la page **Régler les transactions en cours**.

|  &nbsp;                      | &nbsp;    |
|------------------------------|-----------|
| Date d'escompte de règlement           | 7/09/2015 |
| Montant de l'escompte de règlement         | 10,00     |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 5,00      |
| Montant de l'escompte de règlement à accepter | 5,00      |

April valide le journal des paiements et consulte les transactions fournisseur sur la page **Transactions fournisseur**. Le solde de la facture est à présent de 0,00, et April voit les deux paiements et les deux escomptes de règlement.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | Facture          | 6/25/2015 | 10010   |                                      | 1 000,00                              | 0,00    | USD      |
| APP-10010  |  Paiement         | 7/1/2015  |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10010 | Escompte de règlement    | 7/1/2015  |         | 5,00                                 |                                       | 0,00    | USD      |
| APP-10011  | Paiement          | 7/8/2015  |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10011 | Escompte de règlement    | 7/8/2015  |         | 5,00                                 |                                       | 0,00    | USD      |





