---
title: Paiements client pour un montant partiel
description: "Il se peut que des clients effectuent un paiement inférieur au montant de la facture. Cet article décrit les différentes options pour gérer cette situation. Leur disponibilité dépend de vos exigences métier et de votre configuration."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13011
ms.assetid: 20423a2d-6997-4e1c-a596-a77016600071
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: 7025072cd29aac4ceb13b5594c3e321350777cf1
ms.lasthandoff: 03/31/2017


---

# <a name="customer-payments-for-a-partial-amount"></a>Paiements client pour un montant partiel

Il se peut que des clients effectuent un paiement inférieur au montant de la facture. Cet article décrit les différentes options pour gérer cette situation. Leur disponibilité dépend de vos exigences métier et de votre configuration.

<a name="partial-payment-with-no-discount"></a>Paiement partiel sans remise
--------------------------------

Les clients peuvent effectuer un paiement partiel, parce qu'ils n'ont pas assez d'espèces à disposition pour payer la facture entièrement ou en raison d'un litige à propos d'un article figurant sur la facture. Dans ce cas, la facture peut être partiellement réglée avec le paiement. La facture demeurera ouverte et affichera un solde.

## <a name="discount-amounts"></a>Montants de remise
Vous pouvez offrir aux clients un escompte de règlement pour le paiement d'une facture avant la date d'échéance. Par exemple, vous saisissez une facture d'une valeur de 100,00 qui indique un escompte de règlement de 2 % si la facture est payée au cours des 10 jours suivant sa date d'émission. Les conditions de date d'échéance sont de 30 jours. Si vous recevez un paiement de 98,00 d'ici 10 jours, vous entrez le paiement de 98,00. Puis, lorsque la facture est marquée pour règlement, l'escompte de règlement est prélevé automatiquement.

## <a name="partial-payments-with-cash-discounts"></a>Paiements partiels avec escomptes de règlement
Si les clients font un paiement partiel, ils peuvent souhaiter faire un paiement partiel supplémentaire afin de régler complètement la facture. Pour prendre un escompte de règlement pour un paiement partiel, vous devez définir ** calculez les escomptes de règlement pour les paiements partiels ** l'option ** Oui ** sur ** des paramètres des ventes ** la page. 

Par exemple, vous offrez un escompte de règlement de 2 % si la facture est payée au cours des 10 jours suivant sa date d'émission. Une facture d'un montant de 100,00 est validée. Si vous recevez un paiement de 49,00 dans les 10 jours, vous entrez un crédit de 49,00 dans un journal des paiements. Lorsque vous réglez le paiement partiel sur la page **Régler les transactions**, **1,00** apparaît dans le champ **Montant de l'escompte de règlement à accepter**. Le montant de la remise est validé dans un compte d'escompte de règlement. 

> [!NOTE] 
> Si vous entrez un paiement partiel et laissez intégralité du montant de la facture dans ** montant à régler ** le champ, ** montant de l'escompte de règlement à entreprendre ** le champ est recalculé automatiquement lorsque vous validez les transactions.

## <a name="credit-notes-with-discounts"></a>Avoirs avec remises
Si les clients retournent certains articles figurant sur une facture, vous pouvez émettre un avoir. Si un escompte de règlement a été accepté sur la facture d'origine, l'avoir au client doit être net de l'escompte de règlement accepté par le client. Si l'option **Calcule les escomptes de règlement pour les avoirs** est définie sur **Oui** sur la page **Paramètres des ventes**, la remise est calculée automatiquement pour l'avoir. 

Par exemple, vous avez proposé des conditions de paiement indiquant un escompte de règlement de 2 % si la facture est payée au cours des 10 jours suivant son émission. Une facture de 100,00 a été validée, et le client a accepté l'escompte de règlement. Si le client retourne les marchandises et si vous émettez un avoir, vous pouvez saisir ce dernier en créant un avoir de -100,00. Si vous affichez l'avoir sur la page **Régler les transactions en cours**,** 98,00** s'affiche dans le champ **Montant à régler**, puis **-2,00** s'affiche dans le champ **Montant de l'escompte de règlement**. Le montant de la remise est validé dans un compte d'escompte de règlement.

## <a name="overpaymentunderpayment-amounts"></a>Montants des trop-perçus/moins-perçus
Lorsque les clients effectuent un paiement, il se peut qu'il y ait encore un très petit montant à régler. Par exemple, vous adressez une facture de 1 000,00 au client, et celui-ci paie 999,90. Si le montant restant est inférieur au montant indiqué sur la page** Paramètres des ventes** pour les trop-perçus ou les moins-perçus, la différence est automatiquement validée dans un compte des trop-perçus/moins-perçus.

## <a name="full-settlement"></a>Règlement complet
Les clients peuvent effectuer un paiement partiel dans lequel le montant restant ne sera pas payé mais sont plus importants que le montant de moins-perçu qui est spécifié sur ** des paramètres d'achat ** la page. Si vous souhaitez marquer la facture comme entièrement réglée, vous pouvez utiliser ** règlement complet ** l'option sous ** transaction de règlement ** la page. (Vous pouvez activer la fonctionnalité de règlement complet à l'aide d'une clé de configuration). Par exemple, une facture est validée pour un montant de 1 000,00 et le client effectue un paiement de 990,00. Vous avez convenu que le client ne doit pas payer les autres 10,00. Une fois que vous avez marqué la facture pour règlement, vous pouvez également marquer sélectionnez ** règlement complet **. La facture sera ensuite considérée comme réglée. La différence de 10,00 est validée dans un compte d'escompte de règlement en tant que montant d'escompte de règlement supplémentaire.


