---
title: Fonction WEEKNUM ER
description: Cet article fournit des informations sur l’utilisation de la fonction WEEKNUM États électroniques (ER).
author: kfend
ms.date: 01/15/2022
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.custom: 58771
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 4658f88b7e353e651177fad0c8636c5403be1256
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268144"
---
# <a name="weeknum-er-function"></a>Fonction WEEKNUM ER

[!include [banner](../includes/banner.md)]

La fonction `WEEKNUM` renvoie une valeur *[Entier](er-formula-supported-data-types-primitive.md#integer)* qui représente la semaine de l’année qui contient une valeur *[Date](er-formula-supported-data-types-primitive.md#date)* spécifiée. Le calcul est basé sur des règles dépendantes de la culture qui définissent une semaine calendaire et le premier jour de la semaine.

## <a name="syntax"></a>Syntaxe

```vb
WEEKNUM (date, culture) as Integer
```

## <a name=""></a><a name="arguments">Arguments</a>

`date` : *Date*

Valeur de date qui représente la date à utiliser pour le calcul de la semaine de l’année.

`culture` : *[Chaîne](er-formula-supported-data-types-primitive.md#string)*

Culture à utiliser pour le calcul. Vous pouvez utiliser des codes de culture pris en charge conformément aux [normes](/dotnet/api/system.globalization.cultureinfo.getcultures?view=net-5.0) .NET.

## <a name="return-values"></a>Valeurs de retour

*Entier*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La semaine de l’année est calculée sur la base de la norme [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), si cette norme a été adoptée par un pays ou une région pour laquelle les paramètres régionaux sont fournis au moment de l’exécution. Sinon, le calcul est basé sur des normes nationales spécifiques au pays/à la région.

Si un code [culture](#arguments) non pris en charge est fourni comme argument de la fonction `WEEKNUM` au moment de l’exécution, une exception est levée. Si la chaîne vide est fournie en tant que code de culture, le calendrier anglais indépendant du pays est utilisé pour calculer le numéro de la semaine.

## <a name="examples"></a>Exemples

`WEEKNUM (DATEVALUE ("01-01-2020", "de"))` renvoie **1**.

`WEEKNUM (DATEVALUE ("01-01-2021", "de"))` renvoie **53**.

`WEEKNUM (DATEVALUE ("01-01-2022", "de"))` renvoie **52**.

`WEEKNUM (DATEVALUE ("01-01-2022", "ar"))` renvoie **21**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
