---
title: Fonction ROUNDAMOUNT ER
description: Cet article fournit des informations sur l’utilisation de la fonction ROUNDAMOUNT États électroniques (ER).
author: kfend
ms.date: 12/17/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 0e4de43f865ca21822ab2c0c345026d2e9113ca2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286027"
---
# <a name="roundamount-er-function"></a>Fonction ROUNDAMOUNT ER

[!include [banner](../includes/banner.md)]

La fonction `ROUNDAMOUNT` renvoie une valeur *Réelle* comme résultat de l’arrondi du nombre spécifié au multiple le plus proche d’un autre nombre selon la règle d’arrondi spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a>Arguments

`number` : *Int* ou *Réel*

Valeur numérique qui doit être arrondie.

`decimals` : *Int* ou *Réel*

Nombre dont la valeur du paramètre `number` doit être arrondi à un multiple.

`round rule` : *Valeur de l’énumération*

Valeur d’énumération de l’énumération **RoundOffType** qui définit la règle d’arrondi. Cette énumération offre les valeurs suivantes :

- Normal (ordinaire)
- Arrondi au chiffre inférieur (RoundDown)
- Arrondi au chiffre supérieur (RoundUp)

## <a name="return-values"></a>Valeurs de retour

*Réel*

La valeur numérique résultante est un multiple de la valeur spécifiée par le paramètre `decimals` et se rapproche le plus de la valeur spécifiée par le paramètre `number`.

## <a name="usage-notes"></a>Notes d’utilisation

Quand le paramètre `number` est zéro, cette fonction renvoie toujours zéro.

Quand le paramètre `decimals` est égal à zéro, cette fonction arrondit à la valeur d’arrondi par défaut. Quand le paramètre `round rule` est défini sur **RoundOffType.Ordinary**, la valeur d’arrondi par défaut est **0,01**. Sinon, la valeur d’arrondi par défaut est **1,0**.

Quand le paramètre `round rule` est défini sur **RoundOffType.Ordinary**, cette fonction arrondit au montant d’arrondi le plus proche.

Quand le paramètre `round rule` est défini sur **RoundOffType.RoundDown**, cette fonction arrondit vers zéro au montant d’arrondi le plus proche.

Quand le paramètre `round rule` est défini sur **RoundOffType.RoundUp**, cette fonction arrondit en s’éloignant de zéro au montant d’arrondi le plus proche.

Quand le paramètre `round rule` est défini sur **RoundOffType.Ordinary**, cette fonction se comporte comme la fonction Excel [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) et la fonction X++ [ROUND](../dev-ref/xpp-math-run-time-functions.md#round).

## <a name="remarks"></a>Remarques

Pour arrondir une valeur numérique à un nombre spécifié de décimales, utilisez la fonction [ROUND](er-functions-mathematical-round.md).

## <a name="example"></a>Exemple

Si le paramètre **model.RoundOff** est défini sur **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` renvoie 7,35. 

Si le paramètre **model.RoundOff** est défini sur **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` renvoie 7,35. 

Si le paramètre **model.RoundOff** est défini sur **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` renvoie 8,4.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)

[Fonctions mathématiques](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
