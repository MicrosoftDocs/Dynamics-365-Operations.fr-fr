---
title: Régler un paiement partiel fournisseur ayant des remises sur les avoirs
description: Cet article vous fait parcourir les étapes d’un scénario dans lequel un avoir est réglé grâce à une facture.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14222
ms.assetid: 2b19f7fd-9ff9-4ee4-bddf-f582946d008e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e634796c7143c14a872c721f298f3ab28cbddd6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827840"
---
# <a name="settle-a-partial-vendor-payment-that-has-discounts-on-credit-notes"></a>Régler un paiement partiel fournisseur ayant des remises sur les avoirs

[!include [banner](../includes/banner.md)]

Cet article vous fait parcourir les étapes d’un scénario dans lequel un avoir est réglé grâce à une facture.

Les fournisseurs de Fabrikam appliquent des escomptes de règlement sur les avoirs. Le fournisseur 3050 accorde à Fabrikam un escompte de règlement de 1 % si la facture est payée sous 14 jours.

## <a name="invoice-and-credit-memo"></a>Facture et avoir
Le 29 juin, April crée une facture de 1 000,00 pour le fournisseur 3050. Le 2 juillet, elle crée un avoir pour 200,00. Dans la page **Fournisseurs**, April ouvre la page **Règlement des transactions**. Elle peut utiliser la page **Règlement des transactions** pour marquer l’avoir et la facture pour le règlement. Une remise de 2,00 % est calculée sur l’avoir. Par conséquent, la valeur totale de l’avoir est réduite à 198,00.

| Marquer                     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné                 | Standard            | Inv-10070 | 3050    | 6/29/2015 | 7/29/2015 | 10070   | -1 000,00                      | USD      | -990,00          |
| Sélectionné et mis en surbrillance | Standard            | CR-10070  | 3050    | 7/2/2015  | 7/29/2015 |         | 200,00                         | USD      | 198,00           |

Les informations de remise pour l’avoir s’affichent au bas de la page **Régler les transactions en cours**.

| Champ                        | Valeur     |
|------------------------------|-----------|
| Date d’escompte de règlement           | 13/7/2015 |
| Montant de l’escompte de règlement         | 2.00      |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | 2,00      |

April clique sur **Valider**. Elle consulte le règlement complet. Elle constate qu’un avoir de 198,00 a été appliqué, et qu’une remise de 2,00 a été appliquée. Par conséquent, le total est 200,00.

| Marquer                     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture  | Montant dans la devise de transaction | Devise | Montant à régler |
|--------------------------|-------------------|-----------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Sélectionné et mis en surbrillance | Standard            | Inv-10070 | 3050    | 6/29/2015 | 7/29/2015 | 10070    | -1 000,00                      | USD      | -200,00          |
| Activé                 | Standard            | CR-10070  | 3050    | 7/2/2015  | 7/29/2015 | CR-10070 | 200,00                         | USD      | 198,00           |

Elle peut revoir les transactions fournisseur dans la page **Transactions fournisseur** en sélectionnant un fournisseur dans la page **Tous les fournisseurs** puis en cliquant sur **Transactions** dans le volet Actions. Sur cette page, April constate que la facture a un solde de 800,00. Elle constate également un avoir de 198,00 et une remise de 2,00.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10070  | Facture          | 6/29/2015 | 10070   |                                      | 1 000,00                              | -800,00 | USD      |
| Inv-10071  |                  | 7/2/2015  | CR10071 | 200,00                               |                                       | 0,00    | USD      |
| DISC-10071 |  Escompte de règlement   | 7/2/2015  |         | 2,00                                 |                                       | 0,00    | USD      |
| DISC-10071 |  Escompte de règlement   | 7/2/2015  |         |                                      | 2,00                                  | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]