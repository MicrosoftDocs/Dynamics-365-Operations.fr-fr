---
title: "Prélever un escompte de règlement en dehors de la période d'escompte de règlement"
description: "Cet article fournit deux scénarios qui indiquent comment un escompte de règlement peut être pris même si le paiement est effectué en dehors de la période d'escompte de règlement."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14301
ms.assetid: bad10b7f-e550-4742-9261-8a094c9c624d
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 15da62064521ec614764c42b57a20d32b110587a
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017

---

# <a name="take-a-cash-discount-outside-the-cash-discount-period"></a>Prélever un escompte de règlement en dehors de la période d'escompte de règlement

[!include[banner](../includes/banner.md)]


Cet article fournit deux scénarios qui indiquent comment un escompte de règlement peut être pris même si le paiement est effectué en dehors de la période d'escompte de règlement.

Le 28 juin, April crée une facture de 2 000,00 pour le fournisseur 3052. La facture comporte un escompte de règlement de 1 % si la facture est payée sous 14 jours.

## <a name="use-cash-discount-option--always"></a>Utiliser un escompte de règlement : Toujours
April crée un paiement de 500,00 le 1er juillet, à savoir après la date de remise. April ouvre la page **Régler les transactions** pour afficher les transactions qui peuvent être réglées. 

April marque la facture pour paiement. Aucune escompte de règlement n'est appliqué, car le paiement a lieu après la date de remise. Toutefois, le fournisseur a permis à April de prélever l'escompte de règlement dans tous les cas. Par conséquent, April modifie la valeur dans le champ **Utiliser un escompte de règlement** en **Toujours**.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date d'escompte de règlement | Date d'échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Toujours            | Inv-10030 | 3052    | 6/28/2015          | 7/12/2015 | 10030   | -2 000,00                      | USD      | -1 980,00        |

Les informations de remise s'affichent au bas de la page **Règlement des transactions**.

|                              |           |
|------------------------------|-----------|
| Date d'escompte de règlement           | 7/12/2015 |
| Montant de l'escompte de règlement         | -20,00    |
| Utiliser un escompte de règlement            | Toujours    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l'escompte de règlement à accepter | -20,00    |

## <a name="date-to-use-for-calculating-discounts--selected-date"></a>Date à utiliser pour calculer les remises : Date sélectionnée
Si la facture et le paiement ont été validés, l'escompte de règlement peut toujours être prélevé lorsque les transactions sont réglées sur la page **Régler les transactions**. April modifie la valeur du champ **Date à utiliser pour calculer les remises** sur **Date sélectionnée**. Elle entre ensuite la date du 28 juin, qui est comprise dans la période de l'escompte de règlement de la facture. Cette date est utilisée pour calculer un escompte de règlement pour la transaction. Sur la page **Régler les transactions en cours**, April constate que, par défaut, la remise totale de 20,00 s'affiche. La ligne de facture indique que le montant à régler est de 1 980,00.

| Marquer                     | Utiliser un escompte de règlement | N° document   | Compte | Date d'escompte de règlement | Date d'échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|--------------------------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné et mis en surbrillance | Standard            | Inv-10030 | 3052    | 6/28/2015          | 7/12/2015 | 10030   | -2 000,00                      | USD      | -1 980,00        |
| Activé                 | Standard            | APP-10030 | 3052    | 7/15/2015          | 7/15/2015 |         | 500,00                         | USD      | 500,00           |

Les informations de remise s'affichent au bas de la page **Régler les transactions en cours**. Le montant de la remise à prélever est de 20,00, étant donné que le montant à régler pour la facture est le montant par défaut, soit 1 980,00.

|                              |           |
|------------------------------|-----------|
| Date d'escompte de règlement           | 7/12/2015 |
| Montant de l'escompte de règlement         | -20,00    |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l'escompte de règlement à accepter | -20,00    |

April met à jour la valeur du champ **Montant à régler** sur **500,00**. La valeur du champ **Montant de l'escompte de règlement à accepter** est calculée comme **5,05**.

| Marquer                     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d'échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné et mis en surbrillance | Standard            | Inv-10030 | 3052    | 6/28/2015 | 7/12/2015 | 10030   | 2 000,00                       | USD      | -500,00          |
| Activé                 | Standard            | APP-10030 | 3052    | 7/15/2015 | 7/15/2015 |         | 500,00                         | USD      | 500,00           |

Les informations de remise s'affichent au bas de la page **Régler les transactions en cours**. La valeur du champ **Montant de l'escompte de règlement à accepter** est **5,05**, car le montant à régler pour la facture a été remplacé par le montant du paiement, soit 500,00.

|                              |           |
|------------------------------|-----------|
| Date d'escompte de règlement           | 7/12/2015 |
| Montant de l'escompte de règlement         | -20,00    |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l'escompte de règlement à accepter | -5,05.     |






