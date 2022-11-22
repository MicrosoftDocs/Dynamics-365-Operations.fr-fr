---
title: Réévaluer une devise dans une société de consolidation
description: Cet article décrit la procédure de réévaluation de la devise dans une société de consolidation.
author: aprilolson
ms.date: 10/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: twheeloc
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c05ef0d4d05d5113d3b858dafe49ee9c1c7211d9
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779660"
---
# <a name="currency-revaluation-in-a-consolidation-company"></a>Réévaluer une devise dans une société de consolidation

[!include [banner](../includes/banner.md)]

Lorsque vous consolidez des données d’une devise comptable vers une autre, vous devez toujours exécuter la réévaluation de devise en cas de changement dans les taux de change, de sorte que les soldes de compte soient correctement réévalués. Lorsque vous consolidez initialement des données, utilisez l’onglet **Conversion de devises** pour sélectionner les taux de change initiaux pour la traduction lors du processus de consolidation. Une fois qu’un nouveau taux de change est entré (par exemple, le mois prochain), vous devez réévaluer les soldes de compte. Les profits non réalisés ou les pertes sont alors mis à jour, selon le nouveau taux de change et la date. L’exemple suivant illustre les écritures comptables créées lors du processus.

## <a name="company-setup"></a>Paramétrage de la société
-   **Source/société d’exploitation (USMF)**  : Les dollars US (USD) sont utilisés comme devise comptable et devise de reporting.
-   **Société consolidée (CON)** : Les Euros (EUR) sont utilisés comme devise comptable et devise de reporting.
    -   **Profit réalisé** : Compte général 801500
    -   **Perte réalisée** : Compte général 801600
    -   **Profit non réalisé** : Compte général 801600
    -   **Perte non réalisée** : Compte général 801400

## <a name="original-transactions"></a>Transactions d’origine
### <a name="cash-receipt-transactions-in-usmf"></a>Transactions de rentrée de fonds dans USMF

| Date       | Compte général               | Devise | Montant |
|------------|------------------------------|----------|--------|
| 11/10/2020 | 110110 – Disponibilités                | EUR      | 500    |
| 11/10/2020 | 130100 – Comptabilité client | EUR      | -500   |

## <a name="exchange-rates"></a>Taux de change

| Devise de départ | Devise d’arrivée | Date de début | Taux de change |
|---------------|-------------|------------|---------------|
| EUR           | EUR         | 01/10/2020  | 200           |
| EUR           | EUR         | 01/11/2020  | 150           |
| EUR           | EUR         | 01/12/2017  | 100           |

## <a name="perform-the-consolidation-for-october-2020"></a>Effectuer la consolidation pour octobre 2020
### <a name="balances-in-the-consolidation-company"></a>Soldes dans la société de consolidation

| Compte général | Devise | Montant | Calcul    |
|----------------|----------|--------|----------------|
| 110110         | EUR      | 250    | 500 USD × 50 %  |
| 130100         | EUR      | -250   | -500 USD × 50 % |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2020-through-november-30-2020"></a>Effectuer la réévaluation des devises pour les comptes du 1er octobre 2020 au 30 novembre 2020
### <a name="balances-in-the-consolidation-company"></a>Soldes dans la société de consolidation

| Compte général | Devise | Montant  | Calcul                        |
|----------------|----------|---------|------------------------------------|
| 110110         | EUR      | 333,33  | Montant d’origine de 500 × 66,6667 %  |
| 130100         | EUR      | -333,33 | Montant d’origine de -500 × 66,6667 % |
| 801400         | EUR      | 83,33   | 333,33 – 250                       |
| 801600         | EUR      | -83,33  | -333,33 – (-250)                   |

Vous verrez des transactions supplémentaires pour les montants de devise de déclaration.

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2020-through-december-31-2020"></a>Effectuer la réévaluation des devises pour les comptes du 1er octobre 2020 au 31 décembre 2020
### <a name="balances-in-the-consolidation-company"></a>Soldes dans la société de consolidation

| Compte général | Devise | Montant  | Calcul                                          |
|----------------|----------|---------|------------------------------------------------------|
| 110110         | EUR      | 500,00  | Montant d’origine de 500 × 1                           |
| 130100         | EUR      | -500,00 | Montant d’origine de -500 × 1                          |
| 801400         | EUR      | 250     | 500 – 333,33 = 166,67 166,67 + 83,33 = 250           |
| 801600         | EUR      | -250    | -500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
