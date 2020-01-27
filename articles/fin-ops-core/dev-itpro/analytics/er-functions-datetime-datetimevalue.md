---
title: Fonction DATETIMEVALUE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction DATETIMEVALUE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: de601ad08b85797a4241ef74ecb3eba37eda37ca
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917532"
---
# <a name="DATETIMEVALUE">Fonction DATETIMEVALUE ER</a>

[!include [banner](../includes/banner.md)]

La fonction `DATETIMEVALUE` renvoie une valeur *DateTime* qui est convertie à partir d'une valeur de texte donnée dans le format spécifié et dans une [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) spécifiée en option sur une valeur de date/heure. Pour plus d'informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Syntaxe 1

```
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a>Syntaxe 2

```
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Texte qui représente la valeur à mettre en forme.

`format` : *Chaîne*

Format du texte donné.

`culture` : *Chaîne*

Culture utilisée pour la mise en forme du texte donné.

## <a name="return-values"></a>Valeurs de retour

*Date et heure*

Valeur de date/heure résultante.

## <a name="usage-notes"></a>Notes d'utilisation

Lorsque la culture n'est pas définie comme un argument de la fonction appelée, la valeur de `culture` est définie par le contexte d'appel. Par exemple, si la fonction `DATETIMEVALUE` est appelée en utilisant la syntaxe 1 dans un format d'états électroniques (ER) pour un élément **FILE** configuré pour utiliser la culture allemande, la conversion se fera en utilisant la culture allemande. La valeur `culture` par défaut est **EN-US**.

## <a name="example-1"></a>Exemple 1

`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` renvoie **2:55:00 AM le 21 décembre 2016**, en fonction du format personnalisé spécifié et de la culture **EN-US** de l'application par défaut.

## <a name="example-2"></a>Exemple 2

`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` renvoie **2:55:00 AM le 21 décembre 2016**, en fonction du format et de la culture personnalisés spécifiés.

Toutefois, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` lève une exception pour informer l'utilisateur que la chaîne spécifiée n'est pas identifiée comme une date/heure valide pour la culture spécifiée.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d'heure](er-functions-category-datetime.md)
