---
title: Prendre plus que la remise calculée pour un paiement fournisseur
description: Cet article vous fait parcourir un scénario où un escompte de règlement est pris pour un montant qui est supérieur à la remise qui était initialement disponible sur la facture. Ce scénario peut se produire si une organisation parvient à un accord avec le fournisseur pour payer un montant plus bas sur la facture.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd74c6677f80a9075449908411350f1c81b95b02
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778355"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a>Prendre plus que la remise calculée pour un paiement fournisseur

[!include [banner](../includes/banner.md)]

Cet article vous fait parcourir un scénario où un escompte de règlement est pris pour un montant qui est supérieur à la remise qui était initialement disponible sur la facture. Ce scénario peut se produire si une organisation parvient à un accord avec le fournisseur pour payer un montant plus bas sur la facture. 

Le fournisseur 3051 accorde à Fabrikam un escompte de règlement de 4 % si la facture est payée sous sept jours. Le 29 juin, April entre une facture d’un montant de 1 000,00. Le fournisseur permet à April de bénéficier d’une remise de 60,00 au lieu de la remise par défaut de 40,00 disponible pour la facture. April enregistre un paiement unique à l’aide du journal des paiements Achats. Elle entre le fournisseur pour le paiement puis ouvre la page **Régler les transactions**. Elle marque la facture et remplace la valeur du champ **Montant de l’escompte de règlement** par **60,00**.

| Marquer     | Utiliser un escompte de règlement | N° document   | Compte | Date      | Date d’échéance  | Facture | Montant dans la devise de transaction | Devise | Montant à régler |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Sélectionné | Standard            | Inv-10040 | 3051    | 29/06/2020 | 29/07/2020 | 10040   | 1,000.00                       | EUR      | 940,00           |

Les informations de remise s’affichent au bas de la page **Règlement des transactions**.

| Champ                        | Valeur      |
|------------------------------|-----------|
| Date d’escompte de règlement           | 12/07/2020 |
| Montant de l’escompte de règlement         | 60.00     |
| Utiliser un escompte de règlement            | Standard    |
| Escompte de règlement appliqué          | 0,00      |
| Montant de l’escompte de règlement à accepter | 60,00     |

Elle valide ensuite le journal des paiements. La facture est entièrement réglée avec un paiement de 940,00 et une remise de 60,00.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
