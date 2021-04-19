---
title: Fonction NUMBERVALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction NUMBERVALUE États électroniques (ER).
author: NickSelin
ms.date: 12/05/2019
ms.topic: article
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
ms.openlocfilehash: 84d7f17f37a83547522cf09047b72100f6f5b859
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755346"
---
# <a name="numbervalue-er-function"></a>Fonction NUMBERVALUE ER

[!include [banner](../includes/banner.md)]

La fonction `NUMBERVALUE` renvoie une valeur de *Réel* convertie à partir de la valeur de *Chaîne* spécifiée. Lors de la conversion, les séparateurs de regroupements décimaux et numériques spécifiés sont pris en compte.

## <a name="syntax"></a>Syntaxe

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur de texte qui doit être convertie en nombre *Réel*.

`decimal separator` : Chaîne

Séparateur décimal. Il est utilisé pour séparer les parties entières et fractionnaires d’un nombre décimal.

`digit grouping separator` : *Chaîne*

Séparateur de regroupement de chiffres. Il est utilisé comme séparateur de milliers.

## <a name="return-values"></a>Valeurs de retour

*Réel*

Valeur numérique résultante.

## <a name="example"></a>Exemple

`NUMBERVALUE( "1 234,56", ",", " ")` renvoie **1234,56**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de conversion des types](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]