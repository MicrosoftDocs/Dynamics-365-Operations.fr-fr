---
title: Fonction ROUNDDOWN ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ROUNDDOWN États électroniques (ER).
author: NickSelin
ms.date: 12/17/2019
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77186dc4d607f419149e4001a7404afba9e80fc7ec2528b840261a329a1e7872
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747295"
---
# <a name="rounddown-er-function"></a>Fonction ROUNDDOWN ER

[!include [banner](../includes/banner.md)]

La fonction `ROUNDDOWN` renvoie le nombre spécifié comme valeur *Réelle* une fois qu’il a été arrondi au nombre inférieur de décimales spécifié.

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

Cette fonction se comporte comme [ROUND](er-functions-mathematical-round.md), mais elle arrondit toujours le nombre spécifié vers le bas (vers zéro).

## <a name="example-1"></a>Exemple 1

`ROUNDDOWN (1200.767, 2)` arrondit vers le bas à deux décimales et renvoie **1200,76**. 

## <a name="example-2"></a>Exemple 2

`ROUNDDOWN (1700.767, -3)` arrondit vers le bas au multiple de 1 000 le plus proche et renvoie **2 000**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions mathématiques](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]