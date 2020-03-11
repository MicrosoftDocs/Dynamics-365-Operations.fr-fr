---
title: Fonction ROUNDAMOUNT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction ROUNDAMOUNT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5903f562b5f266572f999756539fa7b9ef145023
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041329"
---
# <a name="ROUNDAMOUNT">Fonction ROUNDAMOUNT ER</a>

[!include [banner](../includes/banner.md)]

La fonction `ROUNDAMOUNT` renvoie une valeur *Réelle* comme résultat de l'arrondi du nombre spécifié au multiple le plus proche d'un autre nombre selon la règle d'arrondi spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a>Arguments

`number` : *Int* ou *Réel*

Valeur numérique qui doit être arrondie.

`decimals` : *Int* ou *Réel*

Nombre dont la valeur du paramètre `number` doit être arrondi à un multiple.

`round rule` : *Valeur de l'énumération*

Valeur d'énumération de l'énumération **RoundOffType** qui définit la règle d'arrondi. Cette énumération offre les valeurs suivantes :

- Normal (ordinaire)
- Arrondi au chiffre inférieur (RoundDown)
- Arrondi au chiffre supérieur (RoundUp)

## <a name="return-values"></a>Valeurs de retour

*Réel*

La valeur numérique résultante est un multiple de la valeur spécifiée par le paramètre `decimals` et se rapproche le plus de la valeur spécifiée par le paramètre `number`.

## <a name="usage-notes"></a>Notes d'utilisation

Quand le paramètre `number` est zéro, cette fonction renvoie toujours zéro.

Quand le paramètre `decimals` est égal à zéro, cette fonction arrondit à la valeur d'arrondi par défaut. Quand le paramètre `round rule` est défini sur **RoundOffType.Ordinary**, la valeur d'arrondi par défaut est **0,01**. Sinon, la valeur d'arrondi par défaut est **1,0**.

Quand le paramètre `round rule` est défini sur **RoundOffType.Ordinary**, cette fonction arrondit au montant d'arrondi le plus proche.

Quand le paramètre `round rule` est défini sur **RoundOffType.RoundDown**, cette fonction arrondit vers zéro au montant d'arrondi le plus proche.

Quand le paramètre `round rule` est défini sur **RoundOffType.RoundUp**, cette fonction arrondit en s'éloignant de zéro au montant d'arrondi le plus proche.

Quand le paramètre `round rule` est défini sur **RoundOffType.Ordinary**, cette fonction se comporte comme la fonction Excel [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) et la fonction X++ [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round).

## <a name="remarks"></a>Remarques

Pour arrondir une valeur numérique à un nombre spécifié de décimales, utilisez la fonction [ROUND](er-functions-mathematical-round.md).

## <a name="example"></a>Exemple

Si le paramètre **model.RoundOff** est défini sur **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` renvoie 7,35. 

Si le paramètre **model.RoundOff** est défini sur **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` renvoie 7,35. 

Si le paramètre **model.RoundOff** est défini sur **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` renvoie 8,4.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d'affaires)](er-functions-category-other.md)

[Fonctions mathématiques](er-functions-category-mathematical.md)
