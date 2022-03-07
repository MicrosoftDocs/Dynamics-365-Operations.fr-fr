---
title: Fonction WEEKNUM ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction WEEKNUM États électroniques (ER).
author: NickSelin
ms.date: 12/03/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: fe36d4142b6e4922e2cbca09bb0ca9f68f6680a0
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891341"
---
# <a name="weeknum-er-function"></a>Fonction WEEKNUM ER

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

La fonction `WEEKNUM` renvoie une valeur *[Entier](er-formula-supported-data-types-primitive.md#integer)* qui représente la semaine de l'année qui contient une valeur *[Date](er-formula-supported-data-types-primitive.md#date)* spécifiée. Le calcul est basé sur des règles dépendantes de la culture qui définissent une semaine calendaire et le premier jour de la semaine.

## <a name="syntax"></a>Syntaxe

```vb
WEEKNUM (date, culture) as Integer
```

## <a name=""></a><a name="arguments">Arguments</a>

`date` : *Date*

Valeur de date qui représente la date à utiliser pour le calcul de la semaine de l'année.

`culture` : *[Chaîne](er-formula-supported-data-types-primitive.md#string)*

Culture à utiliser pour le calcul. Vous pouvez utiliser des codes de culture pris en charge conformément aux [normes](/dotnet/api/system.globalization.cultureinfo.getcultures?view=net-5.0) .NET.

## <a name="return-values"></a>Valeurs de retour

*Entier*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La semaine de l'année est calculée sur la base de la norme [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), si cette norme a été adoptée par un pays ou une région pour laquelle les paramètres régionaux sont fournis au moment de l'exécution. Sinon, le calcul est basé sur des normes nationales spécifiques au pays/à la région.

Si un code [culture](#arguments) non pris en charge est fourni comme argument de la fonction `WEEKNUM` au moment de l'exécution, une exception est levée. Si la chaîne vide est fournie en tant que code de culture, le calendrier anglais indépendant du pays est utilisé pour calculer le numéro de la semaine.

## <a name="examples"></a>Exemples

`WEEKNUM (DATEVALUE ("01-01-2020", "de"))` renvoie **1**.

`WEEKNUM (DATEVALUE ("01-01-2021", "de"))` renvoie **53**.

`WEEKNUM (DATEVALUE ("01-01-2022", "de"))` renvoie **52**.

`WEEKNUM (DATEVALUE ("01-01-2022", "ar"))` renvoie **21**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
