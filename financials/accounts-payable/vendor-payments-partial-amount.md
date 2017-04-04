---
title: Paiements fournisseur pour un montant partiel
description: "Il se peut que vous deviez effectuer auprès d&quot;un fournisseur un paiement inférieur au montant de la facture. Cet article décrit les différentes options pour gérer cette situation. Leur disponibilité dépend de vos exigences métier et de votre configuration."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 4d243e6a9a68b69a6b32748344fc606ff3f2d965
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-payments-for-a-partial-amount"></a>Paiements fournisseur pour un montant partiel

Il se peut que vous deviez effectuer auprès d'un fournisseur un paiement inférieur au montant de la facture. Cet article décrit les différentes options pour gérer cette situation. Leur disponibilité dépend de vos exigences métier et de votre configuration. 

<a name="cash-discount-amounts"></a>Montants de l'escompte de règlement
---------------------

Un fournisseur peut vous accorder un escompte de règlement si vous payez une facture avant sa date d'échéance. Par exemple, vous saisissez une facture d'une valeur de 100,00 qui indique un escompte de règlement de 2 % si la facture est payée au cours des 10 jours suivant sa date d'émission. Les conditions de date d'échéance sont de 30 jours. Si une proposition de paiement utilise l'escompte de règlement comme critère pour sélectionner une facture, et si la proposition est effectuée ou avant la date d'escompte de règlement, la facture est activée pour le paiement, puis le paiement est créé pour 98,00. Un escompte de règlement peut également être prise pour un paiement unique qui a été créé manuellement.

## <a name="partial-payments-with-cash-discounts"></a>Paiements partiels avec escomptes de règlement
Si vous faites un paiement partiel, vous pouvez souhaiter effectuer un paiement partiel supplémentaire afin de régler complètement la facture. Pour prendre un escompte de règlement pour un paiement partiel, vous devez définir ** calculez les escomptes de règlement pour les paiements partiels ** l'option ** Oui ** sur ** des paramètres d'achat ** la page. 

Par exemple, vous bénéficiez d'un escompte de règlement de 2 % si la facture est payée au cours des 10 jours suivant sa date d'émission. Une facture d'un montant de 100,00 est validée. Si vous effectuez un paiement de 49,00 dans les 10 jours, vous entrez un débit de 49,00 dans un journal des paiements. Lorsque vous réglez le paiement partiel sur ** des transactions en cours de règlement ** la page, ** 1,00 ** apparaît dans ** montant de l'escompte de règlement à entreprendre ** le champ. 

> [!NOTE] 
> Si vous entrez un paiement partiel et laissez intégralité du montant de la facture dans ** montant à régler ** le champ, ** montant de l'escompte de règlement à entreprendre ** le champ est recalculé automatiquement lorsque vous validez les transactions.

## <a name="credit-notes-with-cash-discounts"></a>Avoirs avec escomptes de règlement
Vous pouvez renvoyer certains articles d'une facture et recevoir un avoir. Si un escompte de règlement a été appliqué à la facture d'origine, vous pouvez soustraire la valeur de la remise et recevoir un remboursement pour le montant correct. Si ** calculez les escomptes de règlement pour les avoirs ** l'option est définie ** Oui ** sur ** des paramètres des achats ** la page, la remise est calculée automatiquement pour l'avoir. 

Par exemple, vous bénéficiez d'un escompte de règlement de 2 % si la facture est payée au cours des 10 jours suivant sa date d'émission. Une facture d'un montant de 100,00 est validée. Si vous retournez les marchandises et recevez un avoir, vous pouvez entrer un avoir pour le montant total de la facture d'origine, 100,00, avec l'escompte de règlement de 2 % qui est également défini sur avoir.  Lorsque vous affichez les avoirs sur ** des transactions de règlement ** la page, ** 98,00 ** apparaît dans ** montant à régler ** le champ, puis ** - 2,00 ** apparaît dans ** montants d'escompte de règlement ** champ. Le montant de la remise est validé dans un compte d'escompte de règlement.

## <a name="overpaymentunderpayment-amounts"></a>Montants des trop-perçus/moins-perçus
Vous pouvez effectuer un paiement partiel lorsqu'il y a encore un très petit montant à régler. Par exemple, la facture fournisseur est de 1 000,00, et vous réglez 999,90. Si le montant restant est inférieur au montant indiqué sur la page **Paramètres des achats** pour les trop-perçus ou les moins-perçus, la différence est validée dans un compte des trop-perçus/moins-perçus.


