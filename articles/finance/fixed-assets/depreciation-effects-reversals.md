---
title: Effets d’amortissement avec contrepassations
description: Cet article traite des conséquences potentielles de la contrepassation d’une transaction d’immobilisation.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: kfend
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f0eeaafe7538b6aeeadfc804096ecee11e714da
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714199"
---
# <a name="depreciation-effects-with-reversals"></a>Effets d’amortissement avec contrepassations

[!include [banner](../includes/banner.md)]

Cet article traite des conséquences potentielles de la contrepassation d’une transaction d’immobilisation. 

Vous pouvez contrepasser des transactions d’immobilisation et les transactions associées à une immobilisation. Vous pouvez également annuler une transaction contrepassée. 

Vous pouvez contrepasser ou annuler une transaction qui n’était pas la dernière validée dans le registre des immobilisations. Commencez par déterminer si des transactions d’amortissement ont été validées après la transaction en cours de contrepassation. Cette étape est nécessaire car l’amortissement n’est pas recalculé lors de la contrepassation d’une transaction. Par conséquent, il est souvent surévalué ou sous-évalué après la contrepassation, comme illustré dans les exemples. 

Pour garantir l’exactitude de l’amortissement lors de la contrepassation d’une transaction, ne poursuivez pas la contrepassation si un message indiquant que l’amortissement ne sera pas recalculé s’affiche. Contrepassez d’abord la transaction d’amortissement validée après la transaction que vous tentez de contrepasser, puis poursuivez la contrepassation. Aucun message sur les nouveaux calculs d’amortissement ne s’affiche et vous pouvez poursuivre la contrepassation. 

Les exemples suivants indiquent les calculs qui interviennent si vous ignorez le message d’avertissement en ne contrepassant pas préalablement les transactions d’amortissement.

## <a name="example-1-depreciation-is-overstated"></a>Exemple 1 : l’amortissement est surévalué
Une immobilisation est paramétrée avec une durée de vie utile de 5 ans et un amortissement linéaire (60 périodes d’amortissement). Dans cet exemple, l’amortissement est surévalué.
#### <a name="asset-transaction-history"></a>Historique de la transaction d’immobilisation

| Date       | Type de transaction                                                          | Montant                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| 1er janvier  | Acquisition                                                               | 59 000,00                                 |
| 1er janvier  | Ajustement d’acquisition                                                    | 1 000,00                                  |
| 31 janvier | Amortissement (créé à l’aide d’une proposition pour une période d’amortissement) | 1 000,00Calcul : valeur comptable (59 000 + 1 000) / nombre de périodes d’amortissement restantes (60) |

#### <a name="reversal-action"></a>Action de contrepassation

| Date      | Type de transaction                | Montant    |
|-----------|---------------------------------|-----------|
| 1er janvier | Contrepassation d’ajustement d’acquisition | –1 000,00 |

#### <a name="depreciation-effect"></a>Effet d’amortissement

| Date        | Type de transaction        | Montant                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| 28 février | Amortissement (proposition) | 983,05Calcul : valeur comptable (59 000 – 1 000 amortissements) / nombre de périodes d’amortissement restantes (59) |

L’amortissement est surévalué de 16,95 (1 000 – 983,05).

## <a name="example-2-depreciation-is-understated"></a>Exemple 2 : l’amortissement est sous-évalué
Une immobilisation est paramétrée avec une durée de vie utile de 5 ans et un amortissement linéaire (60 périodes d’amortissement). Dans cet exemple, l’amortissement est sous-évalué.
#### <a name="asset-transaction-history"></a>Historique de la transaction d’immobilisation

| Date       | Type de transaction                                                          | Montant                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| 1er janvier  | Acquisition                                                               | 59 000,00                                   |
| 1er janvier  | Diminution                                                     | 1 000,00                                    |
| 31 janvier | Amortissement (créé à l’aide d’une proposition pour une période d’amortissement) | 966,67Calcul : valeur comptable (59 000 – 1 000) / nombre de périodes d’amortissement restantes (60) |

#### <a name="reversal-action"></a>Action de contrepassation

| Date      | Type de transaction               | Montant    |
|-----------|--------------------------------|-----------|
| 1er janvier | Contrepassation de diminutions | –1 000,00 |

#### <a name="depreciation-effect"></a>Effet d’amortissement

| Date        | Type de transaction        | Montant                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| 28 février | Amortissement (proposition) | 983,62Calcul : valeur comptable (59 000 – 966,67 amortissements) / nombre de périodes d’amortissement restantes (59) |

L’amortissement est sous-évalué de 16,95 (983,62 – 966,67).



## <a name="additional-resources"></a>Ressources supplémentaires

[Amortissement des immobilisations](fixed-asset-depreciation.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
