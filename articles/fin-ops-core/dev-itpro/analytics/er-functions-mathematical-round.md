---
title: Fonction ROUND ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ROUND États électroniques (ER).
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
ms.openlocfilehash: 12af71a024a76fca98fc2e876da9b59e5762cf07
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744549"
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

Si la valeur de l’argument `decimals` est **0** (zéro), le numéro spécifié est arrondi à l’entier le plus proche.

Si la valeur de l’argument `decimals` est inférieure à 0 (zéro), le numéro spécifié est arrondi à gauche de la virgule.

## <a name="example-1"></a>Exemple 1

`ROUND (1200.767, 2)` arrondit à deux décimales et renvoie **1200,77**.

## <a name="example-2"></a>Exemple 2

`ROUND (1200.767, -3)` arrondit au multiple de 1 000 le plus proche et renvoie **1000**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions mathématiques](er-functions-category-mathematical.md)
