---
title: Régler un paiement partiel fournisseur avant la date de remise avec un paiement final après la date de remise
description: Cet article vous fait parcourir un scénario où plusieurs paiements partiels sont effectués, certains au cours de la période d’escompte de règlement et d’autres en dehors de la période d’escompte de règlement.
author: abruer
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14411
ms.assetid: 302ad6ae-28ee-4899-9f6b-f74424a5f50c
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 731d0a1ad0af47d98455ba2e609a48e092a67d3f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443017"
---
# <a name="settle-a-partial-vendor-payment-before-the-discount-date-with-a-final-payment-after-the-discount-date"></a>Régler un paiement partiel fournisseur avant la date de remise avec un paiement final après la date de remise

[!include [banner](../includes/banner.md)]

Cet article vous fait parcourir un scénario où plusieurs paiements partiels sont effectués, certains au cours de la période d’escompte de règlement et d’autres en dehors de la période d’escompte de règlement.

Fabrikam achète des marchandises au fournisseur 3057. Fabrikam reçoit un escompte de règlement de 1 % si la facture est payée sous 14 jours. Les factures doivent être réglées dans les 30 jours. Le fournisseur offre également à Fabrikam des escomptes de règlement en cas de paiements partiels. Les paramètres de règlement sont situés dans la page **Paramètres de la comptabilité fournisseur**.

## <a name="invoice-on-june-25"></a>Facture au 25 juin
Le 25 juin, April entre et valide une facture de 1 000,00 pour le fournisseur 3057. Elle peut consulter cette transaction sur la page **Transactions fournisseur**.

| N° document   | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde   | Devise |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10020 | Facture          | 6/25/2015 | 10020   |                                      | 1 000,00                              | -1 000,00 | USD      |

## <a name="partial-payment-on-july-2"></a>Paiement partiel le 2 juillet
Le 2 juillet, April souhaite régler 300,00 de cette facture. Le paiement peut prétendre à une remise, car Fabrikam prend des remises pour les paiements partiels. Par conséquent, April paie 297,00 et bénéficie d’une remise de 3,00. Elle crée un journal de paiement et entre une ligne pour le fournisseur 3057. Elle ouvre ensuite la page **Régler les transactions**, afin de pouvoir marquer la facture pour règlement.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | Inv-10020 | 3057    | 6/25/2015 | 7/25/2015 | 10020   | -1 000,00                      | USD      | -297,00          |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**.

|                              |           |
|------------------------------|-----------|
| Date d’escompte de règlement           | 7/09/2015 |
| Montant de l’escompte de règlement         | -10,00    |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | -3,00.     |

April valide ensuite le paiement. Le solde de la facture est maintenant de 700,00. Elle peut consulter cette transaction sur la page **Transactions fournisseur**.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Facture          | 6/25/2015 | 10020   |                                      | 1 000,00                              | -700,00 | USD      |
| APP-10020  | Paiement          | 7/1/2015  |         | 297,00                               |                                       | 0,00    | USD      |
| DISC-10020 | Escompte de règlement    | 7/1/2015  |         | 3,00                                 |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--normal"></a>Paiement restant le 15 juillet, Utiliser un escompte de règlement = Normal
April paie le reste de la facture le 15 juillet, soit après la période de remise. Sur la page **Régler les transactions en cours**, aucun montant de remise n’est affiché dans le champ **Escompte de règlement estimé**, et la valeur du champ **Montant de l’escompte de règlement** est **0,00**. Lorsqu’elle paie le restant dû de 700,00, aucune remise supplémentaire n’est appliquée.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | Inv-10020 | 3057    | 6/25/2015 | 7/25/2015 | 10020   | -700,00                        | USD      | -700,00          |

Les informations de remise s’affichent au bas de la page **Règlement des transactions**. April peut voir qu’elle a déjà bénéficié d’une remise de 3,00.

|                              |           |
|------------------------------|-----------|
| Date d’escompte de règlement           | 7/09/2015 |
| Montant de l’escompte de règlement         | 0,00      |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | -3,00.     |
| Montant de l’escompte de règlement à accepter | 0,00      |

Elle valide ensuite le paiement. Lorsqu’elle ouvre la page **Transactions fournisseur**, elle peut voir que le solde de la facture est de 0,00. Elle constate également qu’il existe deux paiements. Un paiement de 297,00 avec une remise de 3,00, et un autre paiement de 700,00.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Facture          | 6/25/2015 | 10020   |                                      | 1 000,00                              | 0,00    | USD      |
| APP-10020  | Paiement          | 7/1/2015  |         | 297,00                               |                                       | 0,00    | USD      |
| DISC-10020 | Escompte de règlement    | 7/1/2015  |         | 3,00                                 |                                       | 0,00    | USD      |
| APP-10021  | Paiement          | 7/15/2015 |         | 700,00                               |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--always"></a>Paiement restant le 15 juillet, Utiliser un escompte de règlement = Toujours
Si le fournisseur accorde à April une remise même si elle paie après la date de remise, elle peut modifier la valeur du champ **Utiliser un escompte de règlement** en **Toujours**. Le paramètre **Calculer les escomptes de règlement pour les paiements partiels** est remplacé et la remise est prise en compte. Le montant du paiement est de 693,00, et la remise est de 7,00, soit le montant restant.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Sélectionné | Toujours            | Inv-10020 | 3057    | 6/25/2015 | 7/25/2015 | 10020   | 700,00                               |                                       | USD      | -693,00          |

Les informations de remise s’affichent au bas de la page **Règlement des transactions**.

|                              |           |
|------------------------------|-----------|
| Date d’escompte de règlement           | 7/09/2015 |
| Montant de l’escompte de règlement         | 7,00      |
| Utiliser un escompte de règlement            | Toujours    |
| Escompte de règlement appliqué          | -3,00.     |
| Montant de l’escompte de règlement à accepter | -7,00.     |

Elle valide ensuite le paiement. Lorsqu’elle ouvre la page **Transactions fournisseur**, elle peut voir que le solde de la facture est de 0,00. Elle constate également qu’il existe deux paiements. Un paiement de 297,00 avec une remise de 3,00, et un autre paiement de 693,00 avec une remise de 7,00.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Facture          | 6/25/2015 | 10020   |                                      | 1 000,00                              | 0,00    | USD      |
| APP-10020  | Paiement          | 7/1/2015  |         | 297,00                               |                                       | 0,00    | USD      |
| DISC-10020 | Escompte de règlement    | 7/1/2015  |         | 3,00                                 |                                       | 0,00    | USD      |
| APP-10021  | Paiement          | 7/15/2015 |         | 693,00                               |                                       | 0,00    | USD      |
| DISC-10021 | Escompte de règlement    | 7/15/2015 |         | 7,00                                 |                                       | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]