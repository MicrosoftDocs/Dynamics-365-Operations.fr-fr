---
title: Conflit de mise à jour lorsque la méthode d’évaluation du stock est Coût standard ou Moyenne mobile
description: Un conflit de mise à jour se produit lorsque la méthode d’évaluation du stock est Coût standard ou Moyenne mobile
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 920d20d19843ce0cac678c5426c00ec99aa61c61
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476366"
---
# <a name="an-update-conflict-occurs-when-the-inventory-valuation-method-is-either-standard-cost-or-moving-average"></a>Un conflit de mise à jour se produit lorsque la méthode d’évaluation du stock est Coût standard ou Moyenne mobile

## <a name="symptoms"></a>Symptômes

Lorsque vous validez des documents tels que des journaux de stock, des factures de commande fournisseur ou des factures de commande client en parallèle pour améliorer l’évolutivité et les performances, vous pouvez recevoir un message d’erreur concernant un conflit de mise à jour et certains documents peuvent ne pas être validés. Ce problème se produit lorsque la méthode d’évaluation du stock est *Coût standard* ou *Moyenne mobile*. Ces deux méthodes sont des méthodes d’évaluation des coûts perpétuelles. En d’autres termes, le coût final est déterminé au moment de la validation.

Si vous utilisez la méthode *Moyenne mobile*, le message d’erreur ressemble à cet exemple :

> La valeur de stock xx.xx n’est pas attendue après le calcul des dépenses proportionnelles

Si vous utilisez la méthode *Coût standard*, le message d’erreur ressemble à cet exemple :

> Le coût standard ne correspond pas à la valeur de stock financière après la mise à jour. Valeur = xx.xx, Qté = yy.yy, Coût standard = zz.zz

## <a name="workaround"></a>Solution de contournement

Jusqu’à ce que Microsoft publie une solution pour résoudre le problème, envisagez la possibilité d’utiliser les solutions de contournement suivantes pour éviter ou réduire ces erreurs :

- Republiez les documents en échec.
- Créez des documents comportant moins de lignes.
- Évitez les valeurs décimales dans le coût standard. Essayez de définir le coût standard afin que le champ **Quantité de prix** soit défini sur *1*. Si vous devez spécifier une valeur **Quantité de prix** supérieure à *1*, essayez de réduire le nombre de décimales dans le coût standard unitaire. (Idéalement, il devrait y avoir moins de deux décimales.) Par exemple, évitez de définir des paramètres de coût standard tels que **Prix** = *10* et **Quantité de prix** = *3*, car ils produiront un coût standard unitaire de 3,333333 (où la valeur décimale se répète).
- Dans la plupart des documents, évitez d’avoir plusieurs lignes contenant la même combinaison de dimensions de produit et de stock financier.
- Réduisez le degré de parallélisation. (Dans ce cas, votre système peut devenir plus rapide, car moins de conflits de mise à jour et de nouvelles tentatives se produisent.)
