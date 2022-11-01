---
title: Options de calcul Montant entier et Intervalle pour les codes taxe
description: Cet article décrit les options du champ Mode de calcul sous codes taxe et comment la taxe est calculée pour les intervalles et les montants entiers.
author: kailiang
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b81780e60825021ad7a700d85257ba0f5a2447a
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715239"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a>Options de calcul Montant entier et Intervalle pour les codes taxe

[!include [banner](../includes/banner.md)]

Cet article décrit les options du champ **Mode de calcul** sous codes taxe et comment la taxe est calculée pour les intervalles et les montants entiers.

Vous pouvez paramétrer un code taxe à calculer en fonction d’un montant entier ou d’un intervalle. Dans la page **Codes taxe**, utilisez le champ **Mode de calcul** du raccourci **Calcul** pour sélectionner le mode de calcul du code taxe.
- Montant entier – Le taux de taxe est appliqué au montant imposable entier.
- Intervalle – Le montant imposable est divisé en plusieurs parts s’inscrivant chacune dans une plage associée à un taux de taxe spécifique. La part du montant s’inscrivant dans un intervalle donné est taxée au taux correspondant. La taxe est égale à la somme des montants de taxe calculés pour chaque intervalle.
  > [!NOTE]                                                                                                                              
  > L’option Intervalle est disponible uniquement si vous sélectionnez Ligne dans le champ Mode de calcul de la zone Taxe de la page Paramètres de comptabilité. 

Les intervalles sont paramétrés dans la page Valeurs de code taxe en entrant les montants limites minimal et maximal par taux de taxe. Pour que les taxes soient calculées sur tous les montants imposables (quelle que soit la méthode de calcul sélectionnée), les intervalles doivent être conformes aux règles suivantes :
-   La limite minimale du premier intervalle doit être de zéro.
-   La limite maximale du dernier intervalle doit être de zéro, valeur correspondant à l’infini.
-   La limite maximale d’un intervalle doit également être la limite minimale de l’intervalle suivant.

Si un montant est égal à la limite maximale de l’intervalle précédent et à la limite minimale de l’intervalle suivant, le taux de taxe du premier intervalle s’applique. Si un montant ne s’inscrit dans aucun des intervalles définis par les limites supérieure et inférieure, un taux de taxe nul est appliqué.

## <a name="example-whole-amount-method-of-calculation"></a>Exemple : mode de calcul Montant entier
Dans la page Valeurs de code taxe, les taux de taxe sont paramétrés dans les intervalles suivants :

| Limite inférieure     | Limite maximale     | Taux de taxe     |
|-------------------|-------------------|--------------|
| 0,00              | 50,00             | 30 %          |
| 50,00             | 100,00            | 20 %          |
| 100,00            | 0,00              | 10 %          |

La taxe est calculée sur le montant imposable entier.

| Montant imposable (prix) | Calcul    | Taxe |
|------------------------|----------------|-----------|
| 35,00                  | 35,00 \* 0,30  | 10,50     |
| 50,00                  | 50,00 \* 0,30  | 15,00     |
| 85,00                  | 85,00 \* 0,20  | 17,00     |
| 305,00                 | 305,00 \* 0,10 | 30,50     |

## <a name="example-interval-method-of-calculation"></a>Exemple de méthode de calcul Intervalle
Dans la page Valeurs, les taux de taxe sont paramétrés dans les intervalles suivants :

| Limite inférieure     | Limite maximale     | Taux de taxe     |
|-------------------|-------------------|--------------|
| 0,00              | 50,00             | 30 %          |
| 50,00             | 100,00            | 20 %          |
| 100,00            | 0,00              | 10 %          |

La taxe est égale à la somme des montants de taxe calculés pour chaque intervalle.

| Montant imposable (prix) | Calcul                                                               | Taxe |
|------------------------|---------------------------------------------------------------------------|-----------|
| 35,00                  | 35,00 \* 0,30                                                             | 10,50     |
| 50,00                  | 50,00 \* 0,30                                                             | 15,00     |
| 85,00                  | (50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)                          | 22,00     |
| 305,00                 | (50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50) | 45.50     |



Pour plus d’informations, voir [Taux de taxe en fonction des champs Base marginale et Modes de calcul](marginal-base-field.md).







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
