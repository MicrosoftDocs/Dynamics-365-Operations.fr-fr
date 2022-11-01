---
title: Règlement d’un paiement fournisseur partiel avec plusieurs périodes de remise
description: Cet article vous fait parcourir les étapes d’un scénario dans lequel plusieurs paiements partiels sont effectués pour un fournisseur qui offre plusieurs escomptes de règlement.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14262
ms.assetid: af95c48a-afd1-476c-978d-e34995100be4
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 45643ed6c8c9d34dc0b2e31fd04f224823157890
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715989"
---
# <a name="settle-a-partial-vendor-payment-that-has-multiple-discount-periods"></a>Règlement d’un paiement fournisseur partiel avec plusieurs périodes de remise

[!include [banner](../includes/banner.md)]

Cet article vous fait parcourir les étapes d’un scénario dans lequel plusieurs paiements partiels sont effectués pour un fournisseur qui offre plusieurs escomptes de règlement. 

Le fournisseur 3054 offre à Fabrikam un escompte de règlement de 2 % si la facture est payée dans les cinq jours, et un escompte de règlement de 1 % si la facture est payée dans les 14 jours.

## <a name="invoice"></a>Facture
Le 28 juin, April crée une facture de 1 000,00 pour le fournisseur 3054. Elle peut consulter cette transaction sur la page **Transactions fournisseur**.

| N° document   | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde   | Devise |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10060 | 6/28/2015 | 10060   |                                      | 1 000,00                              | -1 000,00 | USD      |

Les dates et montants d’escompte de règlement suivants sont applicables à cette facture.

| Date d’escompte de règlement | Montant de l’escompte de règlement | Montant dans la devise de transaction |
|--------------------|----------------------|--------------------------------|
| 7/3/2015           | 20,00                | 980,00                         |
| 7/12/2015          | 10,00                | 990,00                         |
| 7/25/2015          | 0,00                 | 1 000,00                       |

## <a name="payment-on-july-2"></a>Paiement le 2 juillet
Le 2 juillet, April souhaite régler 300,00 de cette facture. Elle crée un paiement unique à l’aide de la page **Journal des paiements** dans la comptabilité fournisseur. Elle ajoute une ligne pour le fournisseur 3054 et entre un montant de paiement de **300,00**. April ouvre ensuite la page **Régler les transactions**, afin de pouvoir marquer la facture qui est réglée. Elle met à jour la valeur du champ **Montant à régler** avec **300,00** et observe que la valeur du champ **Montant de l’escompte de règlement à accepter** est passée à **6,12**. Ce paiement étant effectué dans la première période de remise, une remise de 2 % est prélevée.

| Marquer | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Standard            | Inv-10060 | 3054    | 6/28/2015 | 7/28/2015 | 10060   | 1 000,00                       | USD      | 300,00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**.

| Champ                        | Valeur     |
|------------------------------|-----------|
| Date d’escompte de règlement           | 7/02/2015 |
| Montant de l’escompte de règlement         | -20,00    |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | -6,12     |

Parce qu’un escompte de règlement est disponible, April souhaite modifier le montant du paiement de telle sorte que le montant total réglé est de 300,00 (paiement et escompte de règlement inclus). Elle change la valeur du champ **Montant à régler** avec **294,00** et observe que la valeur du champ **Montant de l’escompte de règlement à accepter** est passée à **6,00**.

| Marquer | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Standard            | Inv-10060 | 3054    | 6/28/2015 | 7/28/2015 | 10060   | 1 000,00                       | USD      | 294,00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**.

| Champ                        | Valeur     |
|------------------------------|-----------|
| Date d’escompte de règlement           | 7/02/2015 |
| Montant de l’escompte de règlement         | -20,00    |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | -6,00     |

April valide le paiement. Elle peut consulter les transactions sur la page **Transactions fournisseur**. Elle constate que 300,00 a été appliqué à la facture. Ce montant inclut une remise de 6,00. Par conséquent, le solde est de 700,00.

| N° document    | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 6/28/2015 | 10060   |                                      | 1 000,00                              | -700,00 | USD      |
| APP-10060  | 7/2/2015  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 7/2/2015  |         | 6,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-8"></a>Paiement le 8 juillet
Le 8 juillet, April effectue un paiement supplémentaire avec la facture. Pour entrer le montant, elle ouvre la page **Régler les transactions**, puis clique sur l’onglet **Escompte de règlement** . Elle voit les dates et les montants pour les deux escomptes de règlement disponibles. Ce paiement étant effectué dans la seconde période de remise, une remise de 1 %, ou 5,00 est disponible. Le montant calculé représente la moitié de la remise de 1 % accordée sur 1 000,00, ou la moitié de 10,00.

| Date d’escompte de règlement | Montant de l’escompte de règlement | Montant dans la devise de transaction |
|--------------------|----------------------|--------------------------------|
| 7/3/2015           | 20,00                | 680,00                         |
| 7/12/2015          | 10,00                | 690,00                         |
| 7/25/2015          | 0,00                 | 700,00                         |

April décide de payer 495,00 et d’accepter l’escompte de règlement s’élevant à 5,00. Par conséquent le montant total qui est réglé est à présent de 500,00.

| Marquer | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Standard            | Inv-10060 | 3054    | 6/28/2015 | 7/28/2015 | 10060   | 1 000,00                       | USD      | 495,00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**.

| Champ                        | Valeur     |
|------------------------------|-----------|
| Date d’escompte de règlement           | 7/12/2015 |
| Montant de l’escompte de règlement         | -10,00    |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | -6,00     |
| Montant de l’escompte de règlement à accepter | -5,00     |

Sur la page **Transactions fournisseur**, April constate que le nouveau solde est de 200,00.

| N° document    | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 6/28/2015 | 10060   |                                      | 1 000,00                              | -200,00 | USD      |
| APP-10060  | 7/2/2015  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 7/2/2015  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 7/12/2015 |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10061 | 7/12/2015 |         | 5,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-20"></a>Paiement le 20 juillet
Le 20 juillet, April crée un paiement final de 200,00. Aucune escompte de règlement n’est appliqué, car le paiement a lieu après les deux périodes de remise. Le solde de la facture est de 0,00.

| N° document    | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 6/28/2015 | 10060   |                                      | 1 000,00                              | -200,00 | USD      |
| APP-10060  | 7/2/2015  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 7/2/2015  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 7/12/2015 |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10061 | 7/12/2015 |         | 5,00                                 |                                       | 0,00    | USD      |
| APP-10062  | 20/7/2015 |         | 200,00                               |                                       | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
