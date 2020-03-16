---
title: Fonction NUMBERVALUE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction NUMBERVALUE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 6eeb66f4206eb39141a5b2573fcb9d15428ae52a
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042651"
---
# <a name="NUMBERVALUE">Fonction NUMBERVALUE ER</a>

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

Séparateur décimal. Il est utilisé pour séparer les parties entières et fractionnaires d'un nombre décimal.

`digit grouping separator` : *Chaîne*

Séparateur de regroupement de chiffres. Il est utilisé comme séparateur de milliers.

## <a name="return-values"></a>Valeurs de retour

*Réel*

Valeur numérique résultante.

## <a name="example"></a>Exemple

`NUMBERVALUE( "1 234,56", ",", " ")` renvoie **1234,56**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de conversion des types](er-functions-category-type-conversion.md)
