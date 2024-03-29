---
title: Prélever un escompte de règlement en dehors de la période d’escompte de règlement
description: Cet article fournit deux scénarios qui indiquent comment un escompte de règlement peut être pris même si le paiement est effectué en dehors de la période d’escompte de règlement.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14301
ms.assetid: bad10b7f-e550-4742-9261-8a094c9c624d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26b1eb5e542acf7496d1a0cf7196716a5de75e4e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780534"
---
# <a name="take-a-cash-discount-outside-the-cash-discount-period"></a>Prélever un escompte de règlement en dehors de la période d’escompte de règlement

[!include [banner](../includes/banner.md)]

Cet article fournit deux scénarios qui indiquent comment un escompte de règlement peut être pris même si le paiement est effectué en dehors de la période d’escompte de règlement.

Le 28 juin, April crée une facture de 2 000,00 pour le fournisseur 3052. La facture comporte un escompte de règlement de 1 % si la facture est payée sous 14 jours.

## <a name="use-cash-discount-option--always"></a>Utiliser un escompte de règlement : Toujours
April crée un paiement de 500,00 le 1er juillet, à savoir après la date de remise. April ouvre la page **Régler les transactions** pour afficher les transactions qui peuvent être réglées. 

April marque la facture pour paiement. Aucune escompte de règlement n’est appliqué, car le paiement a lieu après la date de remise. Toutefois, le fournisseur a permis à April de prélever l’escompte de règlement dans tous les cas. Par conséquent, April modifie la valeur dans le champ **Utiliser un escompte de règlement** en **Toujours**.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date d’escompte de règlement | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Toujours            | Inv-10030 | 3052    | 28/06/2020          | 12/07/2020 | 10030   | -2 000,00                      | EUR      | -1 980,00        |

Les informations de remise s’affichent au bas de la page **Règlement des transactions**.

| Champ                        | Valeur      |
|------------------------------|-----------|
| Date d’escompte de règlement           | 12/07/2020 |
| Montant de l’escompte de règlement         | -20,00    |
| Utiliser un escompte de règlement            | Toujours    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | -20,00    |

## <a name="date-to-use-for-calculating-discounts--selected-date"></a>Date à utiliser pour calculer les remises : Date sélectionnée
Si la facture et le paiement ont été validés, l’escompte de règlement peut toujours être prélevé lorsque les transactions sont réglées sur la page **Régler les transactions**. April modifie la valeur du champ **Date à utiliser pour calculer les remises** sur **Date sélectionnée**. Elle entre ensuite la date du 28 juin, qui est comprise dans la période de l’escompte de règlement de la facture. Cette date est utilisée pour calculer un escompte de règlement pour la transaction. Sur la page **Régler les transactions en cours**, April constate que, par défaut, la remise totale de 20,00 s’affiche. La ligne de facture indique que le montant à régler est de 1 980,00.

| Marquer          | Utiliser un escompte de règlement | N° document   | Compte | Date d’escompte de règlement | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|--------------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné et mis en surbrillance | Standard    | Inv-10030 | 3052    | 28/06/2020         | 12/07/2020 | 10030   | -2 000,00                      | EUR      | -1 980,00        |
| Sélectionné                 | Standard    | APP-10030 | 3052    | 15/07/2020          | 15/07/2020 |         | 500.00                         | EUR      | 500.00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**. Le montant de la remise à prélever est de 20,00, étant donné que le montant à régler pour la facture est le montant par défaut, soit 1 980,00.

| Champ                        | Valeur      |
|------------------------------|-----------|
| Date d’escompte de règlement           | 12/07/2020 |
| Montant de l’escompte de règlement         | -20,00    |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | -20,00    |

April met à jour la valeur du champ **Montant à régler** sur **500,00**. La valeur du champ **Montant de l’escompte de règlement à accepter** est calculée comme **5,05**.

| Marquer                     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné et mis en surbrillance | Standard            | Inv-10030 | 3052    | 28/06/2020 | 12/07/2020 | 10030   | 2,000.00                       | EUR      | -500,00          |
| Sélectionné                 | Standard            | APP-10030 | 3052    | 15/07/2020 | 15/07/2020 |         | 500.00                         | EUR      | 500.00           |

Les informations de remise s’affichent au bas de la page **Régler les transactions en cours**. La valeur du champ **Montant de l’escompte de règlement à accepter** est **5,05**, car le montant à régler pour la facture a été remplacé par le montant du paiement, soit 500,00.

| Champ                        | Valeur      |
|------------------------------|-----------|
| Date d’escompte de règlement           | 12/07/2020 |
| Montant de l’escompte de règlement         | -20,00    |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | -5,05.     |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
