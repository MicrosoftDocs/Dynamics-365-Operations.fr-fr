---
title: Liste des fonctions ER dans la catégorie de conversion de type
description: Cette rubrique fournit des informations sur les fonctions de conversion prises en charge dans les États électroniques (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d160c02403bf067ed523fbd634e65c622b522b97
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686073"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a>Liste des fonctions ER dans la catégorie de conversion de type

[!include [banner](../includes/banner.md)]

Les fonctions de conversion de type d’état électronique (ER) peuvent être utilisées pour convertir des valeurs entre les types. Cette rubrique fournit un résumé de ces fonctions.

## <a name="type-conversion-functions"></a>Fonctions de conversion de type

| Fonction | Description |
|----------|-------------|
| [Int64Value](er-functions-conversion-int64value.md)   | Cette fonction renvoie une valeur *Int64* qui représente la chaîne spécifiée. |
| [IntValue](er-functions-conversion-intvalue.md)       | Cette fonction renvoie une valeur *Int* qui représente la chaîne spécifiée. |
| [NumberValue](er-functions-conversion-numbervalue.md) | Cette fonction renvoie une valeur de *Réel* convertie à partir de la valeur de *Chaîne* spécifiée. Lors de la conversion, les séparateurs de regroupements décimaux et numériques spécifiés sont pris en compte. |
| [Valeur](er-functions-conversion-value.md)             | Cette fonction renvoie une valeur de *Réel* convertie à partir de la valeur de *Chaîne* spécifiée. |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a>Fonctions de conversion de type dans la catégorie de date/heure

Le tableau suivant décrit les fonctions de conversion de type dans la [catégorie de date et d’heure](er-functions-category-datetime.md).

| Fonction | Description |
|----------|-------------|
| [DateTimeValue](er-functions-datetime-datetimevalue.md)   | Cette fonction renvoie une valeur *DateTime* qui est convertie à partir d’une valeur de *Chaîne* donnée dans le format spécifié et dans une culture spécifiée en option sur une valeur de date/heure. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Cette fonction renvoie une valeur de *DateTime* qui est convertie d’une valeur de *Date* donnée en une valeur de date/heure en temps universel coordonné (Heure de Greenwich, \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md)           | Cette fonction renvoie une valeur *Date* qui est convertie à partir d’une valeur de *Chaîne* donnée dans le format spécifié et dans une culture spécifiée en option sur une valeur de date. |

## <a name="type-conversion-functions-in-the-list-category"></a>Fonctions de conversion de type dans la catégorie de liste

Le tableau suivant décrit les fonctions de conversion de type dans la [catégorie de liste](er-functions-category-list.md).

| Fonction | Description |
|----------|-------------|
| [Liste](er-functions-list-list.md)                 | Cette fonction renvoie une valeur *Liste des enregistrements* comme nouvelle liste créée à partir des arguments spécifiés de type *Conteneur (enregistrement)*. |
| [ListOfFields](er-functions-list-listoffields.md) | Cette fonction renvoie une valeur *Liste des enregistrements* créée en fonction de la structure d’un argument donné du type *Énumération* ou *Conteneur (enregistrement)*. |
| [Fractionner](er-functions-list-split.md)               | Cette fonction fractionne la valeur de *Chaîne* spécifiée en sous-chaînes et renvoie le résultat sous la forme d’une nouvelle valeur de *Liste des enregistrements*. |
| [StringJoin](er-functions-list-stringjoin.md)     | Cette fonction renvoie une valeur de *Chaîne* composée des valeurs concaténées du champ spécifié dans la valeur *Liste des enregistrements* spécifiée. Les valeurs peuvent être séparées par le séparateur spécifié. |

## <a name="type-conversion-functions-in-the-text-category"></a>Fonctions de conversion de type dans la catégorie de texte

Le tableau suivant décrit les fonctions de conversion de type dans la [catégorie de texte](er-functions-category-text.md).

| Fonction | Description |
|----------|-------------|
| [Char](er-functions-text-char.md)                 | Cette fonction renvoie une valeur de *Chaîne* qui représente un seul caractère référencé par le numéro Unicode spécifié. |
| [GuidValue](er-functions-text-guidvalue.md)       | Cette fonction convertit l’entrée spécifiée du type *Chaîne* en un élément de données du type *GUID*. |
| [NumberFormat](er-functions-text-numberformat.md) | Cette fonction renvoie une valeur de *Chaîne* qui représente le nombre spécifié dans le format spécifié et dans une culture éventuellement spécifiée. |
| [QrCode](er-functions-text-qrcode.md)             | Cette fonction renvoie une valeur de *Conteneur* qui présente l’une image de code à réponse rapide (code QR) de la chaîne spécifiée au format binaire. |
| [Détails](er-functions-text-text.md)                 | Cette fonction renvoie une valeur de *Chaîne* qui représente le nombre spécifié une fois qu’elle a été convertie en une chaîne de texte qui est mise en forme en fonction des paramètres régionaux du serveur de l’instance d’application actuelle. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des États électroniques](general-electronic-reporting.md)

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Langage de formule dans la gestion des états électroniques](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]