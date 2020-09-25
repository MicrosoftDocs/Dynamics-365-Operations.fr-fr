---
title: Fonction DATEVALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction DATEVALUE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 1970682db9a2278464aeff572599f0bfa6533e7d
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743589"
---
# <a name="datevalue-er-function"></a>Fonction DATEVALUE ER

[!include [banner](../includes/banner.md)]

La fonction `DATEVALUE` renvoie une valeur *Date* qui est convertie à partir d’une valeur de texte donnée dans le format spécifié et dans une [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) spécifiée en option sur une valeur de date. Pour plus d’informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Syntaxe 1

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a>Syntaxe 2

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Texte qui représente la valeur à mettre en forme.

`format` : *Chaîne*

Format du texte donné.

`culture` : *Chaîne*

Culture utilisée pour la mise en forme du texte donné.

## <a name="return-values"></a>Valeurs de retour

*date ;*

Valeur de date résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Lorsque la culture n’est pas définie comme un argument de la fonction appelée, la valeur de `culture` est définie par le contexte d’appel. Par exemple, si la fonction `DATEVALUE` est appelée en utilisant la syntaxe 1 dans un format d’états électroniques (ER) pour un élément **FILE** configuré pour utiliser la culture allemande, la conversion se fera en utilisant la culture allemande. La valeur `culture` par défaut est **EN-US**.

## <a name="example-1"></a>Exemple 1

`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` renvoie la date de valeur **21 décembre 2016**, en fonction du format personnalisé spécifié et de la culture **EN-US** de l’application par défaut.

## <a name="example-2"></a>Exemple 2

`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` renvoie la valeur de date **21 janvier 2016**, en fonction du format et de la culture personnalisés spécifiés.

Toutefois, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` lève une exception pour informer l’utilisateur que la chaîne spécifiée n’est pas identifiée comme une date valide pour la culture spécifiée.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)
