---
title: "Traitement de l'escompte de règlement pour les trop-perçus"
description: "Cet article fournit des scénarios qui indiquent comment un paiement est assuré lorsque le client bénéficie d'un escompte de règlement tout en payant un montant supérieur."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14171
ms.assetid: a94d0fd0-57ba-4054-93c8-519d01d50e19
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5604f806eed81c60dfcae7cb7b1a22bba25aa454
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="handling-cash-discounts-for-overpayments"></a>Traitement de l'escompte de règlement pour les trop-perçus

[!include [banner](../includes/banner.md)]

Cet article fournit des scénarios qui indiquent comment un paiement est assuré lorsque le client bénéficie d'un escompte de règlement tout en payant un montant supérieur. 

Une facture est considérée comme surpayée lorsque le montant du paiement est supérieur au montant de la facture moins l'escompte de règlement. Pour spécifier la façon dont une différence d'escompte de règlement possible est traitée lorsqu'une facture est surpayée, utilisez les champs **Administration d'escompte de règlement** et **Trop-perçu ou moins-perçu maximal** sur la page **Paramètres de la comptabilité client**. Dans l'exemple suivant, le client a surpayé la facture de 0,5 %.

| Total de la facture | Escompte de règlement possible | Montant à payer (escompte de règlement compris) | Montant réel payé par le client |
|---------------|-------------------------|-----------------------------------------------------|-----------------------------------|
| 105,00        | 10,50                   | 94,50                                               | 95,00                             |

## <a name="cash-discount-administration--specific"></a>Option d'administration des escomptes de règlement : Spécifique
Si le champ **Spécifique** est sélectionné dans le champ **Administration d'escompte de règlement** sur la page **Comptes pour transactions automatiques**, l'escompte de règlement complet est appliqué. Le montant du trop-perçu est validé dans le compte général des différences d'escompte de règlement ou reste un solde dans le compte du client. Cela dépend si le montant du trop-perçu est compris entre 0,00 et le montant entré dans le champ **Trop-perçu ou moins-perçu maximal**, ou si le montant du trop-perçu est supérieur au montant **Trop-perçu ou moins-perçu maximal**.

### <a name="scenario-1"></a>Scénario 1

Dans ce scénario 1, le montant du trop-perçu est compris entre 0,00 et le montant maximal de trop-perçu ou de moins-perçu. Une facture est entrée pour 105,00 avec un escompte de règlement disponible si elle est payée sous sept jours.

| Total de la facture | Escompte de règlement possible | Montant à payer (escompte de règlement compris) |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

Le client envoie un paiement de 95,00 pendant la période d'escompte de règlement. Le paiement est réglé avec la facture de 105,00. Une fois la facture et le paiement réglés, les transactions suivantes sont créées pour le client dans la comptabilité client.

| Transaction   | Montant | Solde |
|---------------|--------|---------|
| Facture       | 105,00 | 0,00    |
| Paiement       | -95,00 | 0,00    |
| Escompte de règlement | -10,50 | 0,00    |

Les écritures comptables suivantes sont générées pour le paiement et le règlement. **Paiement**

| Compte             | Montant de débit | Montant de crédit |
|---------------------|--------------|---------------|
| Espèces                | 95,00        |               |
| Module Comptabilité client |              | 95,00         |

**Règlement**

| Compte                                                                                                          | Montant de débit | Montant de crédit |
|------------------------------------------------------------------------------------------------------------------|--------------|---------------|
| Escompte de règlement (le champ **Compte principal pour les remises client** sur la page **Escomptes de règlement**)                 | 10,50        |               |
| Module Comptabilité client                                                                                              |              | 10,50         |
| Escompte de règlement client  (le champ **Client - Escompte de règlement** sur la page **Comptes pour transactions automatiques**) |              | 0,50          |
| Module Comptabilité client                                                                                              | 0,50         |               |

### <a name="scenario-2"></a>Scénario 2

Dans ce scénario, le montant du trop-perçu dépasse le montant maximal de trop-perçu ou de moins-perçu. Une facture est entrée pour 105,00 avec un escompte de règlement disponible si elle est payée sous sept jours.

| Total de la facture | Escompte de règlement possible | Montant à payer (escompte de règlement compris) |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

Le client envoie un paiement de 95,00 pendant la période d'escompte de règlement. Le paiement est réglé avec la facture de 105,00. Une fois la facture et le paiement réglés, les transactions suivantes sont créées pour le client dans la comptabilité client.

| Transaction   | Montant | Solde |
|---------------|--------|---------|
| Facture       | 105,00 | 0,00    |
| Paiement       | -95,00 | -0,50   |
| Escompte de règlement | -10,50 | 0,00    |

Le montant de trop-perçu de 0,50 restera comme solde en cours sur le paiement et peut être réglé avec une autre facture. Les écritures comptables suivantes sont générées pour le paiement et le règlement. **Paiement**

| Compte             | Montant de débit | Montant de crédit |
|---------------------|--------------|---------------|
| Espèces                | 95,00        |               |
| Module Comptabilité client |              | 95,00         |

**Règlement**

| Compte                                                                                          | Montant de débit | Montant de crédit |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Escompte de règlement (le champ **Compte principal pour les remises client** sur la page **Escomptes de règlement**) | 10,50        |               |
| Module Comptabilité client                                                                              |              | 10,50         |

## <a name="cash-discount-administration--unspecific"></a>Option d'administration des escomptes de règlement : Non spécifique
Si **Non spécifique** est sélectionné dans le champ **Administration d'escompte de règlement** sur la page **Comptes pour transactions automatiques**, le montant de l'escompte de règlement est réduit du montant du trop-perçu. Cela est vrai, que montant du trop-perçu soit supérieur ou inférieur au montant entré dans le champ **Trop-perçu ou moins-perçu maximal**.

### <a name="scenario-3"></a>Scénario 3

Dans ce scénario, une facture est entrée pour 105,00 avec un escompte de règlement disponible si elle est payée sous sept jours.

| Total de la facture | Escompte de règlement possible | Montant à payer (escompte de règlement compris) |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

Le client envoie un paiement de 95,00 pendant la période d'escompte de règlement. Le paiement est réglé avec la facture de 105,00. Une fois la facture et le paiement réglés, les transactions suivantes sont créées pour le client dans la comptabilité client.

| Transaction   | Montant | Solde |
|---------------|--------|---------|
| Facture       | 105,00 | 0,00    |
| Paiement       | -95,00 | -0,00   |
| Escompte de règlement | -10,00 | 0,00    |

Le montant de l'escompte de règlement est réduit de 10,50 à 10,00. Le paiement et la facture sont considérés comme réglés. **Paiement**

| Compte             | Montant de débit | Montant de crédit |
|---------------------|--------------|---------------|
| Espèces                | 95,00        |               |
| Module Comptabilité client |              | 95,00         |

**Règlement**

| Compte                                                                                          | Montant de débit | Montant de crédit |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Escompte de règlement (le champ **Compte principal pour les remises client** sur la page **Escomptes de règlement**) | 10,50        |               |
| Module Comptabilité client                                                                              |              | 10,50         |






