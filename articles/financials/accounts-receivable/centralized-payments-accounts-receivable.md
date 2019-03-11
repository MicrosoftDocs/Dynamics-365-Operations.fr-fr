---
title: Paiements centralisés pour la comptabilité client
description: Les organisations qui comprennent plusieurs entités juridiques peuvent créer et gérer des paiements à l'aide d'une entité juridique unique qui assure la gestion de tous les paiements. Par conséquent, la même transaction ne doit pas être entrée dans plusieurs entités juridiques. Cet article fournit des exemples décrivant la manière dont la validation des paiements centralisés est gérée dans divers scénarios.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9eb935d32e61b2cf0ec8710f6c2cfb18ecfe034
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "330745"
---
# <a name="centralized-payments-for-accounts-receivable"></a>Paiements centralisés pour la comptabilité client

[!include [banner](../includes/banner.md)]

Les organisations qui comprennent plusieurs entités juridiques peuvent créer et gérer des paiements à l'aide d'une entité juridique unique qui assure la gestion de tous les paiements. Par conséquent, la même transaction ne doit pas être entrée dans plusieurs entités juridiques. Cet article fournit des exemples décrivant la manière dont la validation des paiements centralisés est gérée dans divers scénarios.

Les organisations qui comprennent plusieurs entités juridiques peuvent créer et gérer des paiements à l'aide d'une entité juridique qui assure la gestion de tous les paiements. Par conséquent, la même transaction ne doit pas être entrée dans plusieurs entités juridiques. En outre, l'organisation gagne ainsi du temps, car les processus pour les propositions de paiement, les règlements et la modification des transactions en cours et clôturées pour les paiements centralisés sont rationalisés. 

Dans une organisation de paiements centralisés, il existe de nombreuses entités juridiques pour les opérations, et chaque entité juridique d'exploitation gère ses propres informations de factures fournisseur. Les paiements pour toutes les entités juridiques d'exploitation sont reçus par une entité juridique unique, qui est appelée entité juridique du paiement. Au cours du processus de règlement, les transactions vostro et nostro applicables sont générées. Vous pouvez spécifier l'entité juridique de l'organisation qui reçoit les transactions de profit réalisé ou de perte réalisée et la façon dont les transactions d'escompte de règlement associées à un paiement centralisé sont gérées. 

Les exemples suivants montrent comment la validation est gérée dans différents scénarios. La configuration suivante est supposée pour tous ces exemples :

-   Les entités juridiques sont Fabrikam, Fabrikam East et Fabrikam West. Les paiements client sont entrés dans Fabrikam.
-   Le champ **Valider l'escompte de règlement** de la page **Comptabilité intersociétés** est défini sur **Entité juridique de la facture**.
-   Le champ **Valider le bénéfice ou la perte du taux de change** de la page **Comptabilité intersociétés** est défini sur **Entité juridique du paiement**.
-   Customer Northwind Traders est paramétré en tant que client dans chaque entité juridique. Les clients des diverses entités juridiques sont identifiés comme étant le même client, car ils partagent le même ID de carnet d'adresses global.

| ID carnet d'adresses | Compte client | Nom              | Entité juridique  |
|-----------------|------------------|-------------------|---------------|
| 4050            | 4 000             | Northwind Traders | Fabrikam      |
| 4050            | 4 000             | Northwind Traders | Fabrikam East |
| 4050            | 10 000            | Northwind Traders | Fabrikam West |

## <a name="example-1-customer-payment-of-invoice-from-another-legal-entity"></a>Exemple 1 : paiement client d'une facture d'une autre entité juridique
Fabrikam reçoit un paiement de 600,00 pour le compte client Fabrikam n° 4000, Northwind Traders. Le paiement est réglé avec une facture en cours pour le compte client 4000 dans Fabrikam East.

### <a name="invoice-is-posted-in-fabrikam-east-for-customer-4000"></a>La facture est validée chez Fabrikam East pour le client 4000

| Compte                             | Montant de débit | Montant de crédit |
|-------------------------------------|--------------|---------------|
| Ventes (Fabrikam East) | 600,00       |               |
| Ventes (Fabrikam East)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>Le paiement est reçu et validé chez Fabrikam pour le client 4000

| Compte                        | Montant de débit | Montant de crédit |
|--------------------------------|--------------|---------------|
| Disponibilités (Fabrikam)                | 600,00       |               |
| Ventes (Fabrikam) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Le paiement Fabrikam est réglé avec la facture Fabrikam East

**Validation Fabrikam**

| Compte                         | Montant de débit | Montant de crédit |
|---------------------------------|--------------|---------------|
| Ventes (Fabrikam)  | 600,00       |               |
| Dû à Fabrikam East (Fabrikam) |              | 600,00        |

**Validation Fabrikam East**

| Compte                             | Montant de débit | Montant de crédit |
|-------------------------------------|--------------|---------------|
| Dû par Fabrikam (Fabrikam East)   | 600,00       |               |
| Ventes (Fabrikam East) |              | 600,00        |

## <a name="example-2-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>Exemple 2 : paiement client d'une facture d'une autre entité juridique avec escompte de règlement
Fabrikam reçoit un paiement de 580,00 pour le client Fabrikam n° 4000, Northwind Traders. Fabrikam East a une facture en cours pour le client 4000. Un escompte de règlement de 20,00 est disponible sur la facture. Le paiement est réglé avec les factures de Fabrikam East en cours. L'escompte de règlement est validé auprès de l'entité juridique de la facture, Fabrikam East.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>La facture est validée chez Fabrikam East pour le client Fabrikam East 4000

| Compte                             | Montant de débit | Montant de crédit |
|-------------------------------------|--------------|---------------|
| Ventes (Fabrikam East) | 600,00       |               |
| Ventes (Fabrikam East)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>Le paiement est reçu et validé chez Fabrikam pour le client 4000 Fabrikam

| Compte                        | Montant de débit | Montant de crédit |
|--------------------------------|--------------|---------------|
| Disponibilités (Fabrikam)                | 600,00       |               |
| Ventes (Fabrikam) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Le paiement Fabrikam est réglé avec la facture Fabrikam East

**Validation Fabrikam**

| Compte                         | Montant de débit | Montant de crédit |
|---------------------------------|--------------|---------------|
| Ventes (Fabrikam)  | 580,00       |               |
| Dû à Fabrikam East (Fabrikam) |              | 580,00        |

**Validation Fabrikam East**

| Compte                             | Montant de débit | Montant de crédit |
|-------------------------------------|--------------|---------------|
| Dû par Fabrikam (Fabrikam East)   | 580,00       |               |
| Ventes (Fabrikam East) |              | 580,00        |
| Escompte de règlement (Fabrikam East)       | 20,00        |               |
| Ventes (Fabrikam East) |              | 20,00         |

## <a name="example-3-customer-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-gain"></a>Exemple 3 : paiement client d'une facture d'une autre entité juridique avec un bénéfice de change réalisé
Fabrikam reçoit un paiement de 600,00 euros (EUR) pour le client Fabrikam n° 4000, Northwind Traders. Le paiement est réglé avec une facture en cours pour le client n° 4000 dans Fabrikam East. Une transaction de gain de taux de change est générée lors du processus de règlement.

-   Taux de change entre l'euro (EUR) et le dollar américain (USD) à la date de la facture : 1,2062
-   Taux de change entre l'euro et le dollar américain à la date de paiement : 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>La facture est validée chez Fabrikam East pour le client Fabrikam East 4000

| Compte                             | Montant de débit            | Montant de crédit           |
|-------------------------------------|-------------------------|-------------------------|
| Ventes (Fabrikam East) | 600,00 EUR / 723,72 USD |                         |
| Ventes (Fabrikam East)               |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>Le paiement est reçu et validé chez Fabrikam pour le client 4000 Fabrikam

| Compte                        | Montant de débit            | Montant de crédit           |
|--------------------------------|-------------------------|-------------------------|
| Disponibilités (Fabrikam)                | 600,00 EUR / 736,62 USD |                         |
| Ventes (Fabrikam) |                         | 600,00 EUR / 736,62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Le paiement Fabrikam est réglé avec la facture Fabrikam East

**Validation Fabrikam**

| Compte                         | Montant de débit            | Montant de crédit           |
|---------------------------------|-------------------------|-------------------------|
| Ventes (Fabrikam)  | 600,00 EUR / 736,62 USD |                         |
| Dû à Fabrikam East (Fabrikam) |                         | 600,00 EUR / 736,62 USD |
| Dû à Fabrikam East (Fabrikam) | 0,00 EUR / 12,90 USD    |                         |
| Bénéfice réalisé (Fabrikam)        |                         | 0,00 EUR / 12,90 USD    |

**Validation Fabrikam East**

| Compte                             | Montant de débit            | Montant de crédit           |
|-------------------------------------|-------------------------|-------------------------|
| Dû par Fabrikam (Fabrikam East)   | 600,00 EUR / 736,62 USD |                         |
| Ventes (Fabrikam East) |                         | 600,00 EUR / 736,62 USD |
| Ventes (Fabrikam East) | 0,00 EUR / 12,90 USD    |                         |
| Dû par Fabrikam (Fabrikam East)   |                         | 0,00 EUR / 12,90 USD    |

## <a name="example-4-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-gain"></a>Exemple 4 : paiement client d'une facture d'une autre entité juridique avec un escompte de règlement et un bénéfice de change réalisé
Fabrikam valide un paiement pour le client Fabrikam n° 4000, Northwind Traders, correspondant à une facture en cours dans Fabrikam East. Un escompte de règlement est disponible pour la facture et une transaction de taxe est générée. Le paiement est réglé avec la facture de Fabrikam East en cours. Une transaction de gain de taux de change est générée lors du processus de règlement. L'escompte de règlement est validé auprès de l'entité juridique de la facture (Fabrikam East), et le bénéfice de taux de change est validé auprès de l'entité juridique du paiement (Fabrikam).

-   Taux de change entre l'euro et le dollar américain à la date de la facture : 1,2062
-   Taux de change entre l'euro et le dollar américain à la date de paiement : 1,2277

### <a name="free-text-invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-customer-4000"></a>Une facture financière est validée et une transaction de taxe est générée pour le client 4000 dans Fabrikam East

| Compte                             | Montant de débit            | Montant de crédit           |
|-------------------------------------|-------------------------|-------------------------|
| Ventes (Fabrikam East) | 638,22 EUR / 769,82 USD |                         |
| Ventes (Fabrikam East)               |                         | 600,00 EUR / 723,72 USD |
| Taxes (Fabrikam East)           |                         | 38,22 EUR / 46,10 USD   |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>Le paiement est reçu et validé chez Fabrikam pour le client 4000

| Compte                        | Montant de débit            | Montant de crédit           |
|--------------------------------|-------------------------|-------------------------|
| Disponibilités (Fabrikam)                | 626,22 EUR / 768,81 USD |                         |
| Ventes (Fabrikam) |                         | 626,22 EUR / 768,81 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Le paiement Fabrikam est réglé avec la facture Fabrikam East

**Validation Fabrikam**

| Compte                         | Montant de débit            | Montant de crédit           |
|---------------------------------|-------------------------|-------------------------|
| Ventes (Fabrikam)  | 626,22 EUR / 768,81 USD |                         |
| Dû à Fabrikam East (Fabrikam) |                         | 626,22 EUR / 768,81 USD |
| Dû à Fabrikam East (Fabrikam) | 0,00 EUR / 13,46 USD    |                         |
| Bénéfice réalisé (Fabrikam)        |                         | 0,00 EUR / 13,46 USD    |

**Validation Fabrikam East**

| Compte                             | Montant de débit            | Montant de crédit           |
|-------------------------------------|-------------------------|-------------------------|
| Dû par Fabrikam (Fabrikam East)   | 626,22 EUR / 768,81 USD |                         |
| Ventes (Fabrikam East) |                         | 626,22 EUR / 768,81 USD |
| Ventes (Fabrikam East)  | 0,00 EUR / 13,46 USD    |                         |
| Dû par Fabrikam (Fabrikam East)   |                         | 0,00 EUR / 13,46 USD    |
| Escompte de règlement (Fabrikam East)       | 12,00 EUR / 14,47 USD   |                         |
| Ventes (Fabrikam East) |                         | 12,00 EUR / 14,47 USD   |

## <a name="example-5-customer-credit-note-with-primary-payment"></a>Exemple 5 : avoir client avec paiement principal
Fabrikam reçoit un paiement de 75,00 de la part du client Fabrikam n° 4000, Northwind Traders. Le paiement est réglé avec une facture en cours pour le client n° 10000 de Fabrikam West et avec un avoir en cours pour le client n° 4000 de Fabrikam East. Le paiement est sélectionné comme paiement principal dans la page **Régler les transactions**.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>La facture est validée auprès de Fabrikam West pour le client n° 10000

| Compte                             | Montant de débit | Montant de crédit |
|-------------------------------------|--------------|---------------|
| Ventes (Fabrikam West) | 100,00       |               |
| Ventes (Fabrikam West)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>L'avoir est validé chez Fabrikam East pour le client 4000

| Compte                             | Montant de débit | Montant de crédit |
|-------------------------------------|--------------|---------------|
| Retours de ventes (Fabrikam East)       | 25,00        |               |
| Ventes (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>Le paiement est validé chez Fabrikam pour le client 4000

| Compte                        | Montant de débit | Montant de crédit |
|--------------------------------|--------------|---------------|
| Disponibilités (Fabrikam)                | 75,00        |               |
| Ventes (Fabrikam) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Le paiement Fabrikam est réglé avec une facture Fabrikam West et un avoir Fabrikam East

**Validation Fabrikam**

| Compte                           | Montant de débit | Montant de crédit |
|-----------------------------------|--------------|---------------|
| Dû par Fabrikam East (Fabrikam) | 25,00        |               |
| Ventes (Fabrikam)    |              | 25,00         |
| Ventes (Fabrikam)    | 100,00       |               |
| Dû à Fabrikam West (Fabrikam)   |              | 100,00        |

**Validation Fabrikam East**

| Compte                             | Montant de débit | Montant de crédit |
|-------------------------------------|--------------|---------------|
| Ventes (Fabrikam East) | 25,00        |               |
| Dû à Fabrikam (Fabrikam East)     |              | 25,00         |

**Validation Fabrikam West**

| Compte                             | Montant de débit | Montant de crédit |
|-------------------------------------|--------------|---------------|
| Dû par Fabrikam (Fabrikam West)   | 100,00       |               |
| Ventes (Fabrikam West) |              | 100,00        |

## <a name="example-6-customer-credit-note-without-primary-payment"></a>Exemple 6 : avoir client sans paiement principal
Fabrikam reçoit un paiement de 75,00 de la part du client Fabrikam n° 4000, Northwind Traders. Le paiement est réglé avec une facture en cours pour le client n° 10000 de Fabrikam West et avec un avoir en cours pour le client n° 4000 de Fabrikam East. Le paiement n'est pas sélectionné comme paiement principal dans la page **Régler les transactions**.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>La facture est validée auprès de Fabrikam West pour le client n° 10000

| Compte                             | Montant de débit | Montant de crédit |
|-------------------------------------|--------------|---------------|
| Ventes (Fabrikam West) | 100,00       |               |
| Ventes (Fabrikam West)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>L'avoir est validé chez Fabrikam East pour le client 4000

| Compte                             | Montant de débit | Montant de crédit |
|-------------------------------------|--------------|---------------|
| Retours de ventes (Fabrikam East)       | 25,00        |               |
| Ventes (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>Le paiement est validé chez Fabrikam pour le client 4000

| Compte                        | Montant de débit | Montant de crédit |
|--------------------------------|--------------|---------------|
| Disponibilités (Fabrikam)                | 75,00        |               |
| Ventes (Fabrikam) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Le paiement Fabrikam est réglé avec une facture Fabrikam West et un avoir Fabrikam East

**Validation Fabrikam**

| Compte                         | Montant de débit | Montant de crédit |
|---------------------------------|--------------|---------------|
| Ventes (Fabrikam)  | 75,00        |               |
| Dû à Fabrikam West (Fabrikam) |              | 75,00         |

**Validation Fabrikam East**

| Compte                              | Montant de débit | Montant de crédit |
|--------------------------------------|--------------|---------------|
| Ventes (Fabrikam East)  | 25,00        |               |
| Dû à Fabrikam West (Fabrikam East) |              | 25,00         |

**Validation Fabrikam West**

| Compte                                | Montant de débit | Montant de crédit |
|----------------------------------------|--------------|---------------|
| Dû par Fabrikam (Fabrikam West)      | 75,00        |               |
| Ventes (Fabrikam West)    |              | 75,00         |
| Dû par Fabrikam East (Fabrikam West) | 25,00        |               |
| Ventes (Fabrikam West)    |              | 25,00         |





