---
title: Paiements centralisés pour la comptabilité fournisseur
description: Les organisations qui comprennent plusieurs entités juridiques peuvent créer et gérer des paiements à l’aide d’une entité juridique unique qui assure la gestion de tous les paiements. Par conséquent, il n’est pas nécessaire d’entrer les mêmes paiements dans plusieurs entités juridiques. Cet article fournit des exemples décrivant la manière dont la validation des paiements centralisés est gérée dans divers scénarios.
author: abruer
manager: AnnBe
ms.date: 02/12/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14341
ms.assetid: 7bd02e32-2416-4ac6-8a60-85525267fdb7
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a4632056d6873cfeb748251c77becc410f5cf54
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443220"
---
# <a name="centralized-payments-for-accounts-payable"></a>Paiements centralisés pour la comptabilité fournisseur

[!include [banner](../includes/banner.md)]

Les organisations qui comprennent plusieurs entités juridiques peuvent créer et gérer des paiements à l’aide d’une entité juridique unique qui assure la gestion de tous les paiements. Par conséquent, il n’est pas nécessaire d’entrer les mêmes paiements dans plusieurs entités juridiques. Cet article fournit des exemples décrivant la manière dont la validation des paiements centralisés est gérée dans divers scénarios.

Les organisations qui comprennent plusieurs entités juridiques peuvent créer et gérer des paiements à l’aide d’une entité juridique qui assure la gestion de tous les paiements. Par conséquent, il n’est pas nécessaire d’entrer les mêmes paiements dans plusieurs entités juridiques. En outre, l’organisation gagne du temps, car le processus de paiement est simplifié.

Dans une organisation de paiements centralisés, il existe de nombreuses entités juridiques pour les opérations, et chaque entité juridique gère ses propres factures fournisseur. Les paiements pour toutes les entités juridiques en opération sont générés à partir d’une seule entité juridique appelée entité juridique du paiement. Au cours du processus de règlement, les transactions vostro et nostro applicables sont générées. Vous pouvez spécifier l’entité juridique de l’organisation qui reçoit les transactions de profits réalisés ou de pertes réalisées et la façon dont les transactions d’escompte de règlement associées à un paiement intersociétés sont gérées. Sur la ligne du journal des paiements centralisés, l’option **Type de compte** doit être définie sur Fournisseur. L’option **Type de compte de contrepartie** doit être définie sur Compte bancaire ou Compte général. Le compte bancaire doit être dans la société actuelle. 

Les exemples suivants montrent comment la validation est gérée dans différents scénarios. La configuration suivante est supposée pour tous ces exemples :

-   Les entités juridiques sont Fabrikam, Fabrikam East et Fabrikam West. Les paiements sont effectués à partir de Fabrikam.
-   Le champ **Valider l’escompte de règlement** de la page **Comptabilité intersociétés** est défini sur **Entité juridique de la facture**.
-   Le champ **Valider le bénéfice ou la perte du taux de change** de la page **Comptabilité intersociétés** est défini sur **Entité juridique du paiement**.
-   Le fournisseur Fourth Coffee est paramétré en tant que fournisseur dans chaque entité juridique. Les fournisseurs des différentes entités juridiques sont identifiés comme étant le même fournisseur, car ils partagent le même ID de carnet d’adresses global.

| ID registre | Compte fournisseur | Nom          | Entité juridique  |
|--------------|----------------|---------------|---------------|
| 1050         | 3004           | Fourth Coffee | Fabrikam      |
| 1050         | 100            | Fourth Coffee | Fabrikam East |
| 1050         | 3004           | Fourth Coffee | Fabrikam West |

## <a name="example-1-vendor-payment-of-invoice-from-another-legal-entity"></a>Exemple 1 : paiement fournisseur d’une facture d’une autre entité juridique
Fabrikam East a une facture en cours pour le compte fournisseur 100, Fourth Coffee. Fabrikam entre et valide un paiement sur le compte fournisseur Fabrikam 3004, Fourth Coffee. Le paiement est réglé avec la facture en cours.

### <a name="invoice-is-posted-in-fabrikam-east-for-vendor-100"></a>La facture est validée chez Fabrikam East pour le fournisseur 100

| Compte                          | Montant de débit | Montant de crédit |
|----------------------------------|--------------|---------------|
| Dépense (Fabrikam East)          | 600,00       |               |
| Achats (Fabrikam East) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>Le paiement est généré et validé chez Fabrikam pour le fournisseur 3004

| Compte                     | Montant de débit | Montant de crédit |
|-----------------------------|--------------|---------------|
| Achats (Fabrikam) | 600,00       |               |
| Disponibilités (Fabrikam)             |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Le paiement Fabrikam est réglé avec la facture Fabrikam East

**Validation Fabrikam**

| Compte                           | Montant de débit | Montant de crédit |
|-----------------------------------|--------------|---------------|
| Dû par Fabrikam East (Fabrikam) | 600,00       |               |
| Achats (Fabrikam)       |              | 600,00        |

**Validation Fabrikam East**

| Compte                          | Montant de débit | Montant de crédit |
|----------------------------------|--------------|---------------|
| Achats (Fabrikam East) | 600,00       |               |
| Dû à Fabrikam (Fabrikam East)  |              | 600,00        |

## <a name="example-2-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>Exemple 2 : paiement fournisseur d’une facture d’une autre entité juridique avec escompte de règlement
Fabrikam East a une facture en cours pour le fournisseur 100, Fourth Coffee. La facture a un escompte de règlement disponible de 20,00. Fabrikam entre et valide un paiement de 580,00 pour le fournisseur Fabrikam 3004, Fourth Coffee. Le paiement est réglé avec les factures de Fabrikam East en cours. L’escompte de règlement est validé auprès de l’entité juridique de la facture, Fabrikam East.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>La facture est validée chez Fabrikam East pour le fournisseur Fabrikam East 100

| Compte                          | Montant de débit | Montant de crédit |
|----------------------------------|--------------|---------------|
| Dépense (Fabrikam East)          | 600,00       |               |
| Achats (Fabrikam East) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>Le paiement est généré et validé chez Fabrikam pour le fournisseur Fabrikam 3004

| Compte                     | Montant de débit | Montant de crédit |
|-----------------------------|--------------|---------------|
| Achats (Fabrikam) | 580,00       |               |
| Disponibilités (Fabrikam)             |              | 580,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Le paiement Fabrikam est réglé avec la facture Fabrikam East

**Validation Fabrikam**

| Compte                           | Montant de débit | Montant de crédit |
|-----------------------------------|--------------|---------------|
| Dû par Fabrikam East (Fabrikam) | 580,00       |               |
| Achats (Fabrikam)       |              | 580,00        |

**Validation Fabrikam East**

| Compte                          | Montant de débit | Montant de crédit |
|----------------------------------|--------------|---------------|
| Achats (Fabrikam East) | 580,00       |               |
| Dû à Fabrikam (Fabrikam East)  |              | 580,00        |
| Achats (Fabrikam East) | 20,00        |               |
| Escompte de règlement (Fabrikam East)    |              | 20,00         |

## <a name="example-3-vendor-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-loss"></a>Exemple 3 : paiement fournisseur d’une facture d’une autre entité juridique avec une perte de change réalisée
Fabrikam East a une facture en cours pour le fournisseur 100, Fourth Coffee. Fabrikam entre et valide un paiement pour le fournisseur Fabrikam 3004, Fourth Coffee. Le paiement est réglé avec une facture en cours Fabrikam East. Une transaction de perte de change est générée au cours du processus de règlement.

-   Taux de change entre l’euro (EUR) et le dollar américain (USD) à la date de la facture : 1,2062
-   Taux de change entre l’euro et le dollar américain à la date de paiement : 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>La facture est validée chez Fabrikam East pour le fournisseur Fabrikam East 100

| Compte                          | Montant de débit            | Montant de crédit           |
|----------------------------------|-------------------------|-------------------------|
| Dépense (Fabrikam East)          | 600,00 EUR / 723,72 USD |                         |
| Achats (Fabrikam East) |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>Le paiement est généré et validé chez Fabrikam pour le fournisseur Fabrikam 3004

| Compte                     | Montant de débit            | Montant de crédit           |
|-----------------------------|-------------------------|-------------------------|
| Achats (Fabrikam) | 600,00 EUR / 736,62 USD |                         |
| Disponibilités (Fabrikam)             |                         | 600,00 EUR / 736,62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Le paiement Fabrikam est réglé avec la facture Fabrikam East

**Validation Fabrikam**

| Compte                           | Montant de débit            | Montant de crédit           |
|-----------------------------------|-------------------------|-------------------------|
| Dû par Fabrikam East (Fabrikam) | 600,00 EUR / 736,62 USD |                         |
| Achats (Fabrikam)       |                         | 600,00 EUR / 736,62 USD |
| Perte réalisée (Fabrikam)          | 0,00 EUR / 12,90 USD    |                         |
| Dû par Fabrikam East (Fabrikam) |                         | 0,00 EUR / 12,90 USD    |

**Validation Fabrikam East**

| Compte                          | Montant de débit            | Montant de crédit           |
|----------------------------------|-------------------------|-------------------------|
| Achats (Fabrikam East) | 600,00 EUR / 736,62 USD |                         |
| Dû à Fabrikam (Fabrikam East)  |                         | 600,00 EUR / 736,62 USD |
| Dû à Fabrikam (Fabrikam East)  | 0,00 EUR / 12,90 USD    |                         |
| Achats (Fabrikam East) |                         | 0,00 EUR / 12,90 USD    |

## <a name="example-4-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-loss"></a>Exemple 4 : paiement fournisseur d’une facture d’une autre entité juridique avec un escompte de règlement et une perte de change réalisée
Fabrikam East a une facture en cours pour le fournisseur 100, Fourth Coffee. Un escompte de règlement est disponible pour la facture et une transaction de taxe est générée. Fabrikam valide un paiement pour le fournisseur Fabrikam 3004, Fourth Coffee. Le paiement est réglé avec une facture en cours Fabrikam East. Une transaction de perte de change est générée au cours du processus de règlement. L’escompte de règlement est validé dans l’entité juridique de la facture (Fabrikam East) et la perte de change est validée dans l’entité juridique du paiement (Fabrikam).

-   Taux de change entre l’euro et le dollar américain à la date de la facture : 1,2062
-   Taux de change entre l’euro et le dollar américain à la date de paiement : 1,2277

### <a name="invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-vendor-100"></a>La facture est validée et une transaction est générée chez Fabrikam East pour le fournisseur 100

| Compte                          | Montant de débit            | Montant de crédit           |
|----------------------------------|-------------------------|-------------------------|
| Dépense (Fabrikam East)          | 564,07 EUR / 680,38 USD |                         |
| Taxes (Fabrikam East)        | 35,93 EUR / 43,34 USD   |                         |
| Achats (Fabrikam East) |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>Le paiement est généré et validé chez Fabrikam pour le fournisseur 3004

| Compte                     | Montant de débit            | Montant de crédit           |
|-----------------------------|-------------------------|-------------------------|
| Achats (Fabrikam) | 588,72 EUR / 722,77 USD |                         |
| Disponibilités (Fabrikam East)        |                         | 588,72 EUR / 722,77 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Le paiement Fabrikam est réglé avec la facture Fabrikam East

**Validation Fabrikam**

| Compte                           | Montant de débit            | Montant de crédit           |
|-----------------------------------|-------------------------|-------------------------|
| Dû par Fabrikam East (Fabrikam) | 588,72 EUR / 722,77 USD |                         |
| Achats (Fabrikam)       |                         | 588,72 EUR / 722,77 USD |
| Perte réalisée (Fabrikam)          | 0,00 EUR / 12,66 USD    |                         |
| Dû par Fabrikam East (Fabrikam) |                         | 0,00 EUR / 12,66 USD    |

**Validation Fabrikam East**

| Compte                          | Montant de débit            | Montant de crédit           |
|----------------------------------|-------------------------|-------------------------|
| Achats (Fabrikam East) | 588,72 EUR / 722,77 USD |                         |
| Dû à Fabrikam (Fabrikam East)  |                         | 588,72 EUR / 722,77 USD |
| Dû à Fabrikam (Fabrikam East)   | 0,00 EUR / 12,66 USD    |                         |
| Achats (Fabrikam East) |                         | 0,00 EUR / 12,66 USD    |
| Achats (Fabrikam East) | 11,28 EUR / 13,61 USD   |                         |
| Escompte de règlement (Fabrikam East)    |                         | 11,28 EUR / 13,61 USD   |

## <a name="example-5-vendor-credit-note-with-primary-payment"></a>Exemple 5 : avoir fournisseur avec paiement principal
Fabrikam génère un paiement de 75,00 pour le fournisseur 3004, Fourth Coffee. Le paiement est réglé avec une facture en cours pour le fournisseur Fabrikam West 3004 et un avoir en cours pour le fournisseur Fabrikam East 100. Le paiement est sélectionné comme paiement principal dans la page **Régler les transactions**.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>La facture est validée chez Fabrikam West pour le fournisseur 3004

| Compte                          | Montant de débit | Montant de crédit |
|----------------------------------|--------------|---------------|
| Dépense (Fabrikam West)          | 100,00       |               |
| Achats (Fabrikam West) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>L’avoir est validé chez Fabrikam East pour le fournisseur 100

| Compte                          | Montant de débit | Montant de crédit |
|----------------------------------|--------------|---------------|
| Achats (Fabrikam East) | 25,00        |               |
| Retours fournisseur (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>Le paiement est validé chez Fabrikam pour le fournisseur 3004

| Compte                     | Montant de débit | Montant de crédit |
|-----------------------------|--------------|---------------|
| Achats (Fabrikam) | 75,00        |               |
| Disponibilités (Fabrikam)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Le paiement Fabrikam est réglé avec une facture Fabrikam West et un avoir Fabrikam East

**Validation Fabrikam**

| Compte                           | Montant de débit | Montant de crédit |
|-----------------------------------|--------------|---------------|
| Achats (Fabrikam)       | 25,00        |               |
| Dû à Fabrikam East (Fabrikam)   |              | 25,00         |
| Dû par Fabrikam West (Fabrikam) | 100,00       |               |
| Achats (Fabrikam)       |              | 100,00        |

**Validation Fabrikam East**

| Compte                           | Montant de débit | Montant de crédit |
|-----------------------------------|--------------|---------------|
| Dû par Fabrikam (Fabrikam East) | 25,00        |               |
| Achats (Fabrikam East)  |              | 25,00         |

**Validation Fabrikam West**

| Compte                          | Montant de débit | Montant de crédit |
|----------------------------------|--------------|---------------|
| Achats (Fabrikam West) | 100,00       |               |
| Dû à Fabrikam (Fabrikam West)  |              | 100,00        |

## <a name="example-6-vendor-credit-note-without-primary-payment"></a>Exemple 6 : avoir fournisseur sans paiement principal
Fabrikam génère un paiement de 75,00 pour le fournisseur 3004, Fourth Coffee. Le paiement est réglé avec une facture en cours pour le fournisseur Fabrikam West 3004 et un avoir en cours pour le fournisseur Fabrikam East 100. Le paiement n’est pas sélectionné comme paiement principal dans la page **Régler les transactions**.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>La facture est validée chez Fabrikam West pour le fournisseur 3004

| Compte                          | Montant de débit | Montant de crédit |
|----------------------------------|--------------|---------------|
| Dépense (Fabrikam West)          | 100,00       |               |
| Achats (Fabrikam West) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>L’avoir est validé chez Fabrikam East pour le fournisseur 100

| Compte                          | Montant de débit | Montant de crédit |
|----------------------------------|--------------|---------------|
| Achats (Fabrikam East) | 25,00        |               |
| Retours fournisseur (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>Le paiement est validé chez Fabrikam pour le fournisseur 3004

| Compte                     | Montant de débit | Montant de crédit |
|-----------------------------|--------------|---------------|
| Achats (Fabrikam) | 75,00        |               |
| Disponibilités (Fabrikam)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Le paiement Fabrikam est réglé avec une facture Fabrikam West et un avoir Fabrikam East

**Validation Fabrikam**

| Compte                           | Montant de débit | Montant de crédit |
|-----------------------------------|--------------|---------------|
| Dû par Fabrikam West (Fabrikam) | 75,00        |               |
| Achats (Fabrikam)       |              | 75,00         |

**Validation Fabrikam East**

| Compte                                | Montant de débit | Montant de crédit |
|----------------------------------------|--------------|---------------|
| Dû par Fabrikam West (Fabrikam East) | 25,00        |               |
| Achats (Fabrikam East)       |              | 25,00         |

**Validation Fabrikam West**

| Compte                              | Montant de débit | Montant de crédit |
|--------------------------------------|--------------|---------------|
| Achats (Fabrikam West)     | 75,00        |               |
| Dû à Fabrikam (Fabrikam West)      |              | 75,00         |
| Achats (Fabrikam West)     | 25,00        |               |
| Dû à Fabrikam East (Fabrikam West) |              | 25,00         |





