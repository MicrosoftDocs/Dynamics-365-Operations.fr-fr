---
title: Fonction ROUNDUP ER
description: Cet article fournit des informations sur l’utilisation de la fonction ROUNDUP États électroniques (ER).
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
ms.openlocfilehash: 5266b0f74f348d936bde8948770e48dbbf9bb4f5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268024"
---
# <a name="roundup-er-function"></a>Fonction ROUNDUP ER

[!include [banner](../includes/banner.md)]

La fonction `ROUNDUP` renvoie le nombre spécifié comme valeur *Réelle* une fois qu’il a été arrondi au nombre supérieur de décimales spécifié.

## <a name="syntax"></a>Syntaxe

```vb
ROUNDDOWN (number, decimals)
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

Cette fonction se comporte comme [ROUND](er-functions-mathematical-round.md), mais elle arrondit toujours le nombre spécifié vers le haut (loin de zéro).

## <a name="example-1"></a>Exemple 1

`ROUNDUP (1200.763, 2)` arrondit vers le haut à deux décimales et renvoie **1200,77**.

## <a name="example-2"></a>Exemple 2

`ROUNDUP (1200.767, -3)` arrondit vers le haut au multiple de 1 000 le plus proche et renvoie **2 000**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions mathématiques](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
