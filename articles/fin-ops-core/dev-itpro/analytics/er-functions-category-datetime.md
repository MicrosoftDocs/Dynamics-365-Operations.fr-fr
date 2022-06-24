---
title: Liste des fonctions ER dans la catégorie de date et d’heure
description: Cet article fournit des informations sur les fonctions de date et d’heure prises en charge dans les États électroniques (ER).
author: NickSelin
ms.date: 09/09/2021
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
ms.openlocfilehash: e6e15d143bad016883f03ecf0125ce9429215a71
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880237"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>Liste des fonctions ER dans la catégorie de date et d’heure

[!include [banner](../includes/banner.md)]

Les fonctions de date et d’heure d’états électroniques (ER) peuvent être utilisées pour extraire des informations des valeurs de date et d’heure et pour effectuer des opérations sur celles-ci. Cet article fournit un résumé de ces fonctions.

## <a name="list-of-supported-functions"></a>Liste des fonctions prises en charge

| Fonction | Description |
|----------|-------------|
| [AddDays](er-functions-datetime-adddays.md) | Cette fonction renvoie une valeur *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* qui est le nombre de jours spécifié avant ou après une date de début spécifiée. |
| [ChangeTimeZone](er-functions-datetime-changetimezone.md) | Cette fonction renvoie une valeur *DateTime* qui est convertie d’une valeur de date/heure donnée en une valeur de date/heure dans un autre fuseau horaire. |
| [DateFormat](er-functions-datetime-dateformat.md) | Cette fonction renvoie une valeur *[Chaîne](er-formula-supported-data-types-primitive.md#string)* qui présente une valeur de date donnée dans le format spécifié et dans une culture éventuellement spécifiée. |
| [DateTimeFormat](er-functions-datetime-datetimeformat.md) | Cette fonction renvoie une valeur de *Chaîne* qui présente une valeur de date/heure donnée dans le format spécifié et dans une culture éventuellement spécifiée. |
| [DateTimeValue](er-functions-datetime-datetimevalue.md) | Cette fonction renvoie une valeur *DateTime* qui est convertie à partir d’une valeur de texte donnée dans le format spécifié et dans une culture spécifiée en option sur une valeur de date/heure. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Cette fonction renvoie une valeur de *DateTime* qui est convertie d’une valeur de date donnée en une valeur de date/heure en temps universel coordonné (Heure de Greenwich, \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md) | Cette fonction renvoie une valeur *[Date](er-formula-supported-data-types-primitive.md#date)* qui est convertie à partir d’une valeur de texte donnée dans le format spécifié et dans une culture spécifiée en option sur une valeur de date. |
| [DayOfYear](er-functions-datetime-dayofyear.md) | Cette fonction renvoie une valeur *[Entier](er-formula-supported-data-types-primitive.md#integer)* qui représente le nombre de jours entre le 1er janvier et la date spécifiée. |
| [Jours](er-functions-datetime-days.md) | Cette fonction renvoie une valeur *Entier* qui représente sous forme de nombre entier du nombre de jours entre une date spécifiée et une autre date donnée. |
| [Now](er-functions-datetime-now.md) | Cette fonction renvoie une valeur *DateTime* qui représente la date et l’heure actuelles du serveur d’applications. |
| [NullDate](er-functions-datetime-nulldate.md) | Cette fonction renvoie une valeur *Date* qui représente la date **null** (1er janvier 1900). |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | Cette fonction renvoie une valeur de *DateTime* qui représente la valeur de date/heure **null** (1er janvier 1900) en temps universel coordonné. |
| [SessionNow](er-functions-datetime-sessionnow.md) | Cette fonction renvoie une valeur *DateTime* qui représente la date et l’heure actuelles de la session de l’application. |
| [SessionToday](er-functions-datetime-sessiontoday.md) | Cette fonction renvoie une valeur *Date* qui représente la date actuelle de la session de l’application. |
| [Aujourd’hui](er-functions-datetime-today.md) | Cette fonction renvoie une valeur *Date* qui représente la date actuelle du serveur d’applications. |
| [WeekNum](er-functions-datetime-weeknum.md) | Cette fonction renvoie une valeur *Entier* qui représente la semaine de l’année. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des États électroniques](general-electronic-reporting.md)

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Langage de formule dans la gestion des états électroniques](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
