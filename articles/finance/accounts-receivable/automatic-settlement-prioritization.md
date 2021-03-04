---
title: Règlement automatique et attribution de priorités
description: Cette rubrique décrit la manière dont les transactions sont réglées si vous sélectionnez le Règlement automatique dans la page de paramètres de la Comptabilité client. Il décrit également comment le règlement automatique peut être utilisé en combinaison avec la priorité de paiement.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14531
ms.assetid: e7837cf6-ec69-44b4-8d47-eba38d5c7b1f
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b596557e80035e8d62d01f156a6678c75e4ae573
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443144"
---
# <a name="automatic-settlement-and-prioritization"></a>Règlement automatique et attribution de priorités

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la manière dont les transactions sont réglées si vous sélectionnez le Règlement automatique dans la page de paramètres de la Comptabilité client. Il décrit également comment le règlement automatique peut être utilisé en combinaison avec la priorité de paiement.

Vous avez deux options lorsque vous réglez des paiements avec des factures et d’autres transactions. Vous pouvez sélectionner manuellement les transactions à régler ou le système peut sélectionner les transactions automatiquement à l’aide de la fonctionnalité de règlement automatique. Vous pouvez également personnaliser la manière dont les règlements automatiques sont traités à l’aide de l’option **Classer le règlement par ordre de priorité**. Toutes ces options font partie des paramètres de règlement définis dans la page **Paramètres de la comptabilité client**. La manière dont les transactions sont réglées automatiquement peut varier, en fonction de la méthode que vous utilisez pour le règlement automatique. Les méthodes disponibles sont les suivantes :

-   Priorité de règlement définie par l’utilisateur
-   Règlement automatique par défaut

Les sections suivantes décrivent comment les transactions sont réglées pour chaque méthode.

## <a name="example-transactions"></a>Exemples de transactions
Les exemples de règlements présentés plus loin dans cet article sont basés sur les transactions suivantes. Toutes les transactions sont effectuées pour le client 2050.

| Transaction   | date ;        | Montant | Conditions d’escompte de règlement | Date d’escompte de règlement | Commentaires                                                                                                                                                                                      |
|---------------|-------------|--------|---------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Facture 1     | 15 août   | 100,00 | 2%14, Net 30        | 29 août          |                                                                                                                                                                                               |
| Facture 2     | 1 septembre | 250,00 | 2%14, Net 30        | 15 septembre       |                                                                                                                                                                                               |
| Facture 3     | Octobre 15  | 500,00 | 2% 14/Net 30        | 29 octobre         |                                                                                                                                                                                               |
| Note d’intérêt | 15 octobre  | 7h00   |                     |                    | Cette note d’intérêt concerne la facture 1 et la facture 2. Le montant calculé représente 2 % d’intérêts sur les montants qui sont en souffrance depuis 30 jours ou plus. Par exemple, 0,02 × (100,00 + 250,00) = 7,00. |

## <a name="user-defined-settlement-priority"></a>Priorité de règlement définie par l’utilisateur
Si vous définissez **Utiliser la priorité pour les règlements automatiques** sur **Oui** dans la page **Paramètres de la comptabilité client**, la priorité de règlement définie dans la page **Priorité de règlement** est utilisée lorsque des transactions sont sélectionnées pour le règlement automatique. Pour cet exemple, la priorité de règlement suivante est définie :

1.  Type de transaction
    -   Commissions de paiement
    -   Lettres de relance
    -   Notes d’intérêt
    -   Factures

2.  Date de la transaction, croissant
3.  N° document

Si vous validez un paiement de 700,00 le 25 octobre, le paiement est réglé pour les transactions dans l’ordre suivant.

| N° document       | Date       | Facture | Montant dans la devise de transaction | Montant à régler | Solde | Devise |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Note d’intérêt | 10/15/2015 |         | 7h00                           | 7h00             | 0,00    | USD      |
| Facture 1     | 8/15/2015  | 10001   | 100,00                         | 100,00           | 0,00    | USD      |
| Facture 2     | 9/1/2015   | 10002   | 250,00                         | 250,00           | 0,00    | USD      |
| Facture 3     | 10/15/2015 |         | 500,00                         | 343,00           | 157,00  | USD      |

## <a name="default-automatic-settlement"></a>Règlement automatique par défaut
En l’absence de priorité de règlement définie par l’utilisateur, les transactions sont automatiquement sélectionnées pour le règlement en fonction de la date d’échéance. Les transactions réglées doivent avoir la même devise que la transaction avec laquelle elles sont réglées. Si vous validez un paiement de 700,00 le 25 octobre, les transactions suivantes sont sélectionnées pour le règlement.

| N° document       | Date       | Facture | Montant dans la devise de transaction | Montant à régler | Solde | Devise |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Facture 1     | 8/15/2015  | 10001   | 100,00                         | 100,00           | 0,00    | USD      |
| Facture 2     | 9/1/2015   | 10002   | 250,00                         | 250,00           | 0,00    | USD      |
| Facture 3     | 10/15/2015 |         | 500.00                         | 350.00           | 150.00  | USD      |
| Note d’intérêt | 10/15/2015 |         | 7.00                           | 0,00             | 7.00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]