---
title: "Chèques postdatés"
description: "Cet article fournit des informations sur la prise en charge des chèques postdatés dans Microsoft Dynamics 365 for Operations. Les chèques postdatés sont des chèques émis à des fins d&quot;émission ou de réception de paiements à une date future. Par conséquent, le chèque ne peut pas être encaissé avant la date spécifiée."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c3e59ae5126cd21e668459686133ba8bcf728df3
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="postdated-checks"></a>Chèques postdatés

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur la prise en charge des chèques postdatés dans Microsoft Dynamics 365 for Operations. Les chèques postdatés sont des chèques émis à des fins d'émission ou de réception de paiements à une date future. Par conséquent, le chèque ne peut pas être encaissé avant la date spécifiée.

Microsoft Dynamics 365 for Operations prend en charge le cycle de gestion complet pour les chèques postdatés dans Comptabilité client et Comptabilité fournisseur, comme indiqué dans le tableau suivant.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scénario</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Paramétrage de chèques postdatés</td>
<td>Vous devez paramétrer un nouveau mode de paiement, puis spécifier la routine de paiement sur des comptes de compensation pour les chèques émis, les chèques reçus, et la retenue à la source.</td>
</tr>
<tr class="even">
<td>Enregistrement et validation d'un chèque postdaté pour un fournisseur</td>
<td>Enregistrez les détails d'un chèque postdaté avant sa remise à un fournisseur. Lorsque le paiement est validé, le passif du fournisseur est identifié, mais le compte bancaire n'est pas encore crédité. Au lieu de cela, un compte de compensation est utilisé à cet effet.</td>
</tr>
<tr class="odd">
<td>Enregistrer et valider un chèque postdaté pour un client</td>
<td>Enregistrez les informations relatives à un chèque postdaté reçu d'un client. Lorsque le paiement est validé, le montant à recevoir du client est identifié, mais le compte bancaire n'est pas encore débité. Au lieu de cela, un compte de compensation est utilisé à cet effet.</td>
</tr>
<tr class="even">
<td>Enregistrement et validation d'un chèque postdaté de remplacement pour un client ou un fournisseur</td>
<td>
Si votre chèque d'origine à un fournisseur ou émis par un client est perdu ou endommagé, vous pouvez émettre un chèque postdaté de remplacement. Lorsque vous enregistrez les détails du chèque, fournissez une référence au chèque d'origine et indiquez que celui-ci est remplacé par ce nouveau chèque. Vous pouvez également valider le chèque de remplacement.</td>
</tr>
<tr class="odd">
<td>Transfert d'un chèque client postdaté à un fournisseur</td>
<td>Lorsque vous recevez un chèque postdaté d'un client, vous pouvez le transférer à un fournisseur en tant que paiement.</td>
</tr>
<tr class="even">
<td>Règlement d'un chèque postdaté pour un client ou un fournisseur</td>
<td>Réglez un chèque postdaté validé dans le compte d'attente d'un client ou d'un fournisseur lorsque le chèque est enfin échu. Lorsque le chèque est réglé, la banque débite ou crédite finalement le compte de compensation utilisé précédemment.</td>
</tr>
<tr class="odd">
<td>Annulation d'un chèque postdaté pour un fournisseur</td>
<td>Vous pouvez annuler un chèque postdaté validé dans les situations suivantes : - Le chèque est retourné par la banque.
- Le chèque est appliqué à une facture incorrecte.
- Le montant du chèque est réglé par un paiement en espèces.
</td>
</tr>
<tr class="even">
<td>Arrêt du paiement d'un chèque postdaté</td>
<td>Vous pouvez arrêter le paiement sur un chèque postdaté émis auprès d'un fournisseur pour diverses raisons (fonds insuffisants, modifications des conditions de l'accord avec le fournisseur, livraison de marchandises défectueuses par le fournisseur, retour de marchandises au fournisseur, etc.). Seul le paiement des chèques non compensés peut être arrêté.</td>
</tr>
</tbody>
</table>







