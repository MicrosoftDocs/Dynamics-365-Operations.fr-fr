---
title: "Réévaluation de devise dans une société de consolidation"
description: 
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 109f8e008b9865188c1c2cae3855884739d9d57d
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="currency-revaluation-in-a-consolidation-company"></a>Réévaluation de devise dans une société de consolidation

[!include[banner](../includes/banner.md)]




Lorsque vous consolidez des données d'une devise comptable vers une autre, vous devez toujours exécuter la réévaluation de devise en cas de changement dans les taux de change, de sorte que les soldes de compte soient correctement réévalués. Lorsque vous consolidez initialement des données, utilisez l'onglet **Conversion de devises** pour sélectionner les taux de change initiaux pour la traduction lors du processus de consolidation. Une fois qu'un nouveau taux de change est entré (par exemple, le mois prochain), vous devez réévaluer les soldes de compte. Les profits non réalisés ou les pertes sont alors mis à jour, selon le nouveau taux de change et la date. L'exemple suivant illustre les écritures comptables créées lors du processus.

## <a name="company-setup"></a>Paramétrage de la société
-   **Source/société d'exploitation (USMF)**  : Les dollars US (USD) sont utilisés comme devise comptable et devise de reporting.
-   **Société consolidée (CON)** : Les Euros (EUR) sont utilisés comme devise comptable et devise de reporting.
    -   **Profit réalisé** : Compte général 801500
    -   **Perte réalisée** : Compte général 801600
    -   **Profit non réalisé** : Compte général 801600
    -   **Perte non réalisée** : Compte général 801400

## <a name="original-transactions"></a>Transactions d'origine
### <a name="cash-receipt-transactions-in-usmf"></a>Transactions de rentrée de fonds dans USMF

| Date       | Compte général               | Devise | Montant |
|------------|------------------------------|----------|--------|
| 10/11/2015 | 110110 – Disponibilités                | USD      | 500    |
| 10/11/2015 | 130100 – Comptabilité client | USD      | -500   |

## <a name="exchange-rates"></a>Taux de change
| Devise de départ | Devise d'arrivée | Date de début | Taux de change |
|---------------|-------------|------------|---------------|
| EUR           | USD         | 10/1/2015  | 200           |
| EUR           | USD         | 11/1/2015  | 150           |
| EUR           | USD         | 12/1/2012  | 100           |

## <a name="perform-the-consolidation-for-october-2015"></a>Effectuer la consolidation pour octobre 2015
### <a name="balances-in-the-consolidation-company"></a>Soldes dans la société de consolidation

| Compte général | Devise | Montant | Calcul    |
|----------------|----------|--------|----------------|
| 110110         | EUR      | 250    | 500 USD × 50 %  |
| 130100         | EUR      | -250   | -500 USD × 50 % |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a>Effectuer la réévaluation de devise des comptes à partir du 1er octobre 2015, jusqu'au 30 novembre 2015
### <a name="balances-in-the-consolidation-company"></a>Soldes dans la société de consolidation

| Compte général | Devise | Montant  | Calcul                        |
|----------------|----------|---------|------------------------------------|
| 110110         | EUR      | 333,33  | Montant d'origine de 500 × 66,6667 %  |
| 130100         | EUR      | -333,33 | Montant d'origine de -500 × 66,6667 % |
| 801400         | EUR      | 83,33   | 333,33 – 250                       |
| 801600         | EUR      | -83,33  | -333,33 – (-250)                   |

Vous verrez des transactions supplémentaires pour les montants de devise de déclaration.

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a>Effectuer la réévaluation de devise des comptes à partir du 1er octobre 2015, jusqu'au 31 décembre 2015
### <a name="balances-in-the-consolidation-company"></a>Soldes dans la société de consolidation

| Compte général | Devise | Montant  | Calcul                                          |
|----------------|----------|---------|------------------------------------------------------|
| 110110         | EUR      | 500,00  | Montant d'origine de 500 × 1                           |
| 130100         | EUR      | -500,00 | Montant d'origine de -500 × 1                          |
| 801400         | EUR      | 250     | 500 – 333,33 = 166,67 166,67 + 83,33 = 250           |
| 801600         | EUR      | -250    | -500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250 |






