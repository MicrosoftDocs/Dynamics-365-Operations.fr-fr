---
title: Régler un paiement partiel avant la date de remise et règlement final après la date de remise
description: Cet article vous fait parcourir un scénario où plusieurs paiements partiels sont effectués, certains au cours de la période d’escompte de règlement et d’autres en dehors de la période d’escompte de règlement.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14411
ms.assetid: 302ad6ae-28ee-4899-9f6b-f74424a5f50c
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 828c82d88bef1d942af1219505af591d27043fa5
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780535"
---
# <a name="settle-partial-payment-before-discount-date-and-final-payment-after-discount-date"></a>Régler un paiement partiel avant la date de remise et règlement final après la date de remise

[!include [banner](../includes/banner.md)]

Cet article vous fait parcourir un scénario où plusieurs paiements partiels sont effectués, certains au cours de la période d’escompte de règlement et d’autres en dehors de la période d’escompte de règlement.

Fabrikam achète des marchandises au fournisseur 3057. Fabrikam reçoit un escompte de règlement de 1 % si la facture est payée sous 14 jours. Les factures doivent être réglées dans les 30 jours. Le fournisseur offre également à Fabrikam des escomptes de règlement en cas de paiements partiels. Les paramètres de règlement sont situés dans la page **Paramètres de la comptabilité fournisseur**.

## <a name="invoice-on-june-25"></a>Facture au 25 juin
Le 25 juin, April entre et valide une facture de 1 000,00 pour le fournisseur 3057. Elle peut consulter cette transaction sur la page **Transactions fournisseur**.

| N° document   | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde   | Devise |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10020 | Facture          | 25/06/2020 | 10020   |                                      | 1,000.00                              | -1 000,00 | EUR      |

## <a name="partial-payment-on-july-2"></a>Paiement partiel le 2 juillet
Le 2 juillet, April souhaite régler 300,00 de cette facture. Le paiement peut prétendre à une remise, car Fabrikam prend des remises pour les paiements partiels. Par conséquent, April paie 297,00 et bénéficie d’une remise de 3,00. Elle crée un journal de paiement et entre une ligne pour le fournisseur 3057. Elle ouvre ensuite la page **Régler les transactions**, afin de pouvoir marquer la facture pour règlement.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | Inv-10020 | 3057    | 25/06/2020 | 25/07/2020 | 10020   | -1 000,00                      | EUR      | -297,00          |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**.

| Champ                        | Valeur      |
|------------------------------|-----------|
| Date d’escompte de règlement           | 09/07/2020 |
| Montant de l’escompte de règlement         | -10,00    |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | -3,00.     |

April valide ensuite le paiement. Le solde de la facture est maintenant de 700,00. Elle peut consulter cette transaction sur la page **Transactions fournisseur**.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Facture          | 25/06/2020 | 10020   |                                      | 1,000.00                              | -700,00 | EUR      |
| APP-10020  | Paiement          | 01/07/2020  |         | 297,00                               |                                       | 0.00    | EUR      |
| DISC-10020 | Escompte de règlement    | 01/07/2020  |         | 3.00                                 |                                       | 0.00    | EUR      |

## <a name="remaining-payment-on-july-15-use-cash-discount--normal"></a>Paiement restant le 15 juillet, Utiliser un escompte de règlement = Normal
April paie le reste de la facture le 15 juillet, soit après la période de remise. Sur la page **Régler les transactions en cours**, aucun montant de remise n’est affiché dans le champ **Escompte de règlement estimé**, et la valeur du champ **Montant de l’escompte de règlement** est **0,00**. Lorsqu’elle paie le restant dû de 700,00, aucune remise supplémentaire n’est appliquée.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | Inv-10020 | 3057    | 25/06/2020 | 25/07/2020 | 10020   | -700,00                        | EUR      | -700,00          |

Les informations de remise s’affichent au bas de la page **Règlement des transactions**. April peut voir qu’elle a déjà bénéficié d’une remise de 3,00.

| Champ                        | Valeur      |
|------------------------------|-----------|
| Date d’escompte de règlement           | 09/07/2020 |
| Montant de l’escompte de règlement         | 0.00      |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | -3,00.     |
| Montant de l’escompte de règlement à accepter | 0,00      |

Elle valide ensuite le paiement. Lorsqu’elle ouvre la page **Transactions fournisseur**, elle peut voir que le solde de la facture est de 0,00. Elle constate également qu’il existe deux paiements. Un paiement de 297,00 avec une remise de 3,00, et un autre paiement de 700,00.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Facture          | 25/06/2020 | 10020   |                                      | 1,000.00                              | 0.00    | EUR      |
| APP-10020  | Paiement          | 01/07/2020  |         | 297,00                               |                                       | 0.00    | EUR      |
| DISC-10020 | Escompte de règlement    | 01/07/2020  |         | 3.00                                 |                                       | 0.00    | EUR      |
| APP-10021  | Paiement          | 15/07/2020 |         | 700.00                               |                                       | 0.00    | EUR      |

## <a name="remaining-payment-on-july-15-use-cash-discount--always"></a>Paiement restant le 15 juillet, Utiliser un escompte de règlement = Toujours
Si le fournisseur accorde à April une remise même si elle paie après la date de remise, elle peut modifier la valeur du champ **Utiliser un escompte de règlement** en **Toujours**. Le paramètre **Calculer les escomptes de règlement pour les paiements partiels** est remplacé et la remise est prise en compte. Le montant du paiement est de 693,00, et la remise est de 7,00, soit le montant restant.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Devise | Montant à régler |
|----------|----------|------|------|-----------|-----------|---------|-----------------------|---------------------------------------|----------|------------------|
| Sélectionné | Toujours            | Inv-10020 | 3057    | 25/06/2020 | 25/07/2020 | 10020   | 700.00                   |                   | EUR      | -693,00          |

Les informations de remise s’affichent au bas de la page **Règlement des transactions**.

| Champ                        | Valeur      |
|------------------------------|-----------|
| Date d’escompte de règlement           | 09/07/2020 |
| Montant de l’escompte de règlement         | 7.00      |
| Utiliser un escompte de règlement            | Toujours    |
| Escompte de règlement appliqué          | -3,00.     |
| Montant de l’escompte de règlement à accepter | -7,00.     |

Elle valide ensuite le paiement. Lorsqu’elle ouvre la page **Transactions fournisseur**, elle peut voir que le solde de la facture est de 0,00. Elle constate également qu’il existe deux paiements. Un paiement de 297,00 avec une remise de 3,00, et un autre paiement de 693,00 avec une remise de 7,00.

| N° document    | Type de transaction | Date      | Facture | Montant au débit dans la devise de transaction | Montant au crédit dans la devise de transaction | Solde | Devise |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Facture          | 25/06/2020 | 10020   |                                      | 1,000.00                              | 0.00    | EUR      |
| APP-10020  | Paiement          | 01/07/2020  |         | 297,00                               |                                       | 0.00    | EUR      |
| DISC-10020 | Escompte de règlement    | 01/07/2020  |         | 3.00                                 |                                       | 0.00    | EUR      |
| APP-10021  | Paiement          | 15/07/2020 |         | 693,00                               |                                       | 0.00    | EUR      |
| DISC-10021 | Escompte de règlement    | 15/07/2020 |         | 7.00                                 |                                       | 0.00    | EUR      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
