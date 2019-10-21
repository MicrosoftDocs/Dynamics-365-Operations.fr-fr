---
title: Paiements fournisseur pour un montant partiel
description: Il se peut que vous deviez effectuer auprès d'un fournisseur un paiement inférieur au montant de la facture. Cet article décrit les différentes options pour gérer cette situation.
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
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 89e025977a0dcd40e35f17448a7b0ebde08cb6c8
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177784"
---
# <a name="vendor-payments-for-a-partial-amount"></a>Paiements fournisseur pour un montant partiel

[!include [banner](../includes/banner.md)]

Il se peut que vous deviez effectuer auprès d'un fournisseur un paiement inférieur au montant de la facture. Cet article décrit les différentes options pour gérer cette situation. Leur disponibilité dépend de vos exigences métier et de votre configuration. 

<a name="cash-discount-amounts"></a>Montants de l'escompte de règlement
---------------------

Un fournisseur peut vous accorder un escompte de règlement si vous payez une facture avant sa date d'échéance. Par exemple, vous saisissez une facture d'une valeur de 100,00 qui indique un escompte de règlement de 2 % si la facture est payée au cours des 10 jours suivant sa date d'émission. Les conditions de date d'échéance sont de 30 jours. Si une proposition de paiement utilise l'escompte de règlement comme critère pour sélectionner une facture, et si la proposition est effectuée à la date ou avant la date d'escompte de règlement, la facture est activée pour le paiement, et le paiement est créé pour 98,00. Un escompte de règlement peut être également appliqué à un paiement unique créé manuellement.

## <a name="partial-payments-with-cash-discounts"></a>Paiements partiels avec escomptes de règlement
Si vous faites un paiement partiel, vous pouvez souhaiter effectuer un paiement partiel supplémentaire afin de régler complètement la facture. Pour appliquer une escompte de règlement à un paiement partiel, vous devez définir l'option **Calcule les escomptes de règlement pour les paiements partiels** sur **Oui** sur la page **Paramètres des achats**. 

Par exemple, vous bénéficiez d'un escompte de règlement de 2 % si la facture est payée au cours des 10 jours suivant sa date d'émission. Une facture d'un montant de 100,00 est validée. Si vous effectuez un paiement de 49,00 dans les 10 jours, vous entrez un débit de 49,00 dans un journal des paiements. Lorsque vous réglez le paiement partiel sur la page **Régler les transactions en cours**, **1,00** apparaît dans le champ **Montant de l'escompte de règlement à accepter**. 

> [!NOTE] 
> Si vous entrez un paiement partiel et si vous laissez l'intégralité du montant de la facture dans le champ **Montant à régler**, le champ **Montant de l'escompte de règlement à accepter** est recalculé automatiquement lorsque vous validez les transactions.

## <a name="credit-notes-with-cash-discounts"></a>Avoirs avec escomptes de règlement
Vous pouvez renvoyer certains articles d'une facture et recevoir un avoir. Si un escompte de règlement a été appliqué à la facture d'origine, vous pouvez soustraire la valeur de la remise et recevoir un remboursement pour le montant correct. Si l'option **Calcule les escomptes de règlement pour les avoirs** est définie sur **Oui** sur la page **Paramètres des achats**, la remise est calculée automatiquement pour l'avoir. 

Par exemple, vous bénéficiez d'un escompte de règlement de 2 % si la facture est payée au cours des 10 jours suivant sa date d'émission. Une facture d'un montant de 100,00 est validée. Si vous retournez des marchandises et recevez un avoir, vous pouvez entrer l'avoir pour le montant total de la facture d'origine, 100,00, avec l'escompte de règlement de 2 % qui est également défini sur l'avoir.  Si vous affichez l'avoir sur la page **Régler les transactions**, **98,00** s'affiche dans le champ **Montant à régler**, puis **-2,00** s'affiche dans le champ **Montant de l'escompte de règlement**. Le montant de la remise est validé dans un compte d'escompte de règlement.

## <a name="overpaymentunderpayment-amounts"></a>Montants des trop-perçus/moins-perçus
Vous pouvez effectuer un paiement partiel lorsqu'il y a encore un très petit montant à régler. Par exemple, la facture fournisseur est de 1 000,00, et vous réglez 999,90. Si le montant restant est inférieur au montant indiqué sur la page **Paramètres des achats** pour les trop-perçus ou les moins-perçus, la différence est validée dans un compte des trop-perçus/moins-perçus.


Pour plus d'informations, voir [Vue d'ensemble des paiements fournisseurs](../cash-bank-management/tasks/vendor-payment-overview.md).
