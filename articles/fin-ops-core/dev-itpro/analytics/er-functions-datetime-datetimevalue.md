---
title: Fonction DATETIMEVALUE ER
description: Cet article fournit des informations sur l’utilisation de la fonction DATETIMEVALUE États électroniques (ER).
author: NickSelin
ms.date: 09/08/2021
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
ms.openlocfilehash: 7e3af6a279163183546255908730ba32d790a22b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870433"
---
# <a name="datetimevalue-er-function"></a>Fonction DATETIMEVALUE ER

[!include [banner](../includes/banner.md)]

La fonction `DATETIMEVALUE` renvoie une valeur *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* qui est convertie à partir d’une valeur de texte donnée dans le format spécifié et dans une [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) spécifiée en option sur une valeur de date/heure. Pour plus d’informations sur les formats pris en charge, consultez [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) et [personnalisé](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Syntaxe 1

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a>Syntaxe 2

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a>Arguments

`text` : *[Chaîne](er-formula-supported-data-types-primitive.md#string)*

Texte qui représente la valeur à mettre en forme.

`format` : *Chaîne*

Format du texte donné. Pour plus d’informations sur les formats pris en charge, consultez [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) et [personnalisé](/dotnet/standard/base-types/custom-date-and-time-format-strings).

`culture` : *Chaîne*

Culture utilisée pour la mise en forme du texte donné. Pour plus d’informations sur les cultures prises en charge, voir [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Valeurs de retour

*Date et heure*

Valeur de date/heure résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Lorsque la culture n’est pas définie comme un argument de la fonction appelée, la valeur de `culture` est définie par le contexte d’appel. Par exemple, si la fonction `DATETIMEVALUE` est appelée en utilisant la syntaxe 1 dans un format d’états électroniques (ER) pour un élément **FILE** configuré pour utiliser la culture allemande, la conversion se fera en utilisant la culture allemande. La valeur `culture` par défaut est **EN-US**.

## <a name="example-1"></a>Exemple 1

`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` renvoie **2:55:00 AM le 21 décembre 2016**, en fonction du format personnalisé spécifié et de la culture **EN-US** de l’application par défaut.

## <a name="example-2"></a>Exemple 2

`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` renvoie **2:55:00 AM le 21 décembre 2016**, en fonction du format et de la culture personnalisés spécifiés.

Toutefois, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` lève une exception pour informer l’utilisateur que la chaîne spécifiée n’est pas identifiée comme une date/heure valide pour la culture spécifiée.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
