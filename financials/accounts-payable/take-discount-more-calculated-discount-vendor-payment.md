---
title: "Utilisation d&quot;une remise supérieure à la remise calculée pour un paiement fournisseur"
description: "Cet article vous fait parcourir un scénario où un escompte de règlement est pris pour un montant qui est supérieur à la remise qui était initialement disponible sur la facture. Ce scénario peut se produire si une organisation parvient à un accord avec le fournisseur pour payer un montant plus bas sur la facture."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 08d7c4981aba7e7c092a6f21d3b63635e76437bf
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a>Utilisation d'une remise supérieure à la remise calculée pour un paiement fournisseur

[!include[banner](../includes/banner.md)]


Cet article vous fait parcourir un scénario où un escompte de règlement est pris pour un montant qui est supérieur à la remise qui était initialement disponible sur la facture. Ce scénario peut se produire si une organisation parvient à un accord avec le fournisseur pour payer un montant plus bas sur la facture. 

Le fournisseur 3051 accorde à Fabrikam un escompte de règlement de 4 % si la facture est payée sous sept jours. Le 29 juin, April entre une facture d'un montant de 1 000,00. Le fournisseur permet à April de bénéficier d'une remise de 60,00 au lieu de la remise par défaut de 40,00 disponible pour la facture. April enregistre un paiement unique à l'aide du journal des paiements Achats. Elle entre le fournisseur pour le paiement puis ouvre la page **Régler les transactions**. Elle marque la facture et remplace la valeur du champ **Montant de l'escompte de règlement** par **60,00**.
| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d'échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | Inv-10040 | 3051    | 6/29/2015 | 7/29/2015 | 10040   | 1 000,00                       | USD      | 940,00           |

Les informations de remise s'affichent au bas de la page **Règlement des transactions**.
|                              |           |
|------------------------------|-----------|
| Date d'escompte de règlement           | 7/12/2015 |
| Montant de l'escompte de règlement         | 60,00     |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l'escompte de règlement à accepter | 60,00     |

Elle valide ensuite le journal des paiements. La facture est entièrement réglée avec un paiement de 940,00 et une remise de 60,00.




