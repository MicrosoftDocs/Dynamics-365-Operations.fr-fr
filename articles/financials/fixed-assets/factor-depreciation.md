---
title: Amortissement paramétrable
description: Cet article donne une vue d'ensemble de la méthode d'amortissement paramétrable.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa8bc4566def9dd770a97facb459e6b977bfaffb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "338795"
---
# <a name="factor-depreciation"></a>Amortissement paramétrable

[!include [banner](../includes/banner.md)]

Cet article donne une vue d'ensemble de la méthode d'amortissement paramétrable.

Les facteurs sont les pourcentages utilisés pour l'amortissement des immobilisations. Lorsque vous paramétrez un profil d'amortissement d'immobilisations et sélectionnez **Facteur** dans le champ **Méthode** de la page **Profils d'amortissement**, vous pouvez paramétrer un amortissement progressif, dégressif ou linéaire :

-   Dans l'amortissement progressif, le montant d'amortissement augmente avec chaque période d'amortissement.
-   Dans l'amortissement dégressif, le montant d'amortissement par période diminue dans le temps.
-   Dans l'amortissement linéaire, l'amortissement est identique pour chaque période.

Les règles et exemples suivants indiquent la procédure de paramétrage de facteurs pour chaque type d'amortissement. 

> [!NOTE] 
> Lorsque vous sélectionnez **Facteur** dans le champ **Méthode**, le champ **Facteur** et le champ **Intervalle** s'affichent.

## <a name="progressive-depreciation"></a>Amortissement progressif
La valeur du champ **Facteur** est supérieure à **50**.

### <a name="example"></a>Exemple

Le prix d'acquisition s'élève à 10 000, le facteur est de 70, la durée de vie est de 10 ans et l'amortissement débute le 1er janvier. Les montants d'amortissement et de valeur comptable nette sont uniquement affichés pour les six premières années de la durée de vie.

| Année | Période      | Montant d'amortissement | Valeur comptable nette |
|------|-------------|---------------------|-----------------------|
| 1    | 31 décembre | 307,69              | 99 692,31             |
| 2    | 31 décembre | 1 447,21            | 98 245,10             |
| 3    | 31 décembre | 3 104,50            | 95 140,60             |
| 4    | 31 décembre | 5 150,21            | 89 990,39             |
| 5    | 31 décembre | 7 522,95            | 82 467,44             |
| 6    | 31 décembre | 10 184,06           | 72 283,38             |

## <a name="digressive-depreciation"></a>Amortissement dégressif
La valeur du champ **Facteur** est inférieure à **50**.

### <a name="example"></a>Exemple

Le prix d'acquisition s'élève à 10 000, le facteur est de 20, la durée de vie est de 10 ans et l'amortissement débute le 1er janvier. Les montants d'amortissement et de valeur comptable nette sont uniquement affichés pour les six premières années de la durée de vie.

| Année | Période      | Montant d'amortissement | Valeur comptable nette |
|------|-------------|---------------------|-----------------------|
| 1    | 31 décembre | 56 080,43           | 43 919,57             |
| 2    | 31 décembre | 10 665,70           | 33 253,87             |
| 3    | 31 décembre | 7 156,22            | 26 097,65             |
| 4    | 31 décembre | 5 538,06            | 20 559,59             |
| 5    | 31 décembre | 4 579,89            | 15 979,70             |
| 6    | 31 décembre | 3 937,36            | 12 042,34             |

## <a name="straight-line-depreciation"></a>Amortissement linéaire
La valeur du champ **Facteur** est égale à **50**. Dans ce cas, l'amortissement est identique pour chaque période, et vous devez prendre en compte les implications des valeurs que vous avez spécifiées dans d'autres champs, comme décrit dans [Amortissement linéaire sur la durée de vie](straight-line-service-life-depreciation.md).



