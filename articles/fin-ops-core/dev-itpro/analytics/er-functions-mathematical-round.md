---
title: Fonction ROUND ER
description: Cet article fournit des informations sur l’utilisation de la fonction ROUND États électroniques (ER).
author: kfend
ms.date: 10/21/2020
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
ms.openlocfilehash: 57d41ed92a5577fdc5fffeccef2834e9b6fb5197
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286057"
---
# <a name="round-er-function"></a>Fonction ROUND ER

[!include [banner](../includes/banner.md)]

La fonction `ROUND` renvoie le nombre spécifié comme valeur *Réelle* une fois qu’il a été arrondi au nombre de décimales spécifié.

## <a name="syntax"></a>Syntaxe

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a>Arguments

`number` : *Réel*

Valeur numérique qui doit être arrondie.

`decimals` : *Entier*

Valeur numérique qui représente les nombre de décimales.

## <a name="return-values"></a>Valeurs de retour

*Réel*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Si la valeur de l’argument `decimals` est supérieure à 0 (zéro), le numéro spécifié est arrondi au nombre de décimales.

Si la valeur de l’argument `decimals` est **0** (zéro), le numéro spécifié est arrondi à l’entier pair le plus proche.

Si la valeur de l’argument `decimals` est inférieure à 0 (zéro), le numéro spécifié est arrondi à gauche de la virgule.

## <a name="example-1"></a>Exemple 1

`ROUND (1200.767, 2)` arrondit à deux décimales et renvoie **1200,77**.

## <a name="example-2"></a>Exemple 2

`ROUND (1200.767, -3)` arrondit au multiple de 1 000 le plus proche et renvoie **1000**.

## <a name="example-3"></a>Exemple 3

`ROUND (1200.5, 0)` arrondit à l’entier pair le plus proche et renvoie **1200**, tandis que `ROUND (1201.5, 0)` fait de même et retourne **1202**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions mathématiques](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
