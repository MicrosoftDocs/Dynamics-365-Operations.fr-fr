---
title: Fonction NUMBERFORMAT ER
description: Cet article fournit des informations sur l’utilisation de la fonction NUMBERFORMAT États électroniques (ER).
author: kfend
ms.date: 12/10/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 5519f549c10ba5c02e249592d040582c3f8dc44f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274793"
---
# <a name="numberformat-er-function"></a>Fonction NUMBERFORMAT ER

[!include [banner](../includes/banner.md)]

La fonction `NUMBERFORMAT` renvoie une valeur de *Chaîne* qui présente le nombre spécifié dans le format spécifié et dans une [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) éventuellement spécifiée. Pour plus d’informations sur les formats pris en charge, consultez [standard](/dotnet/standard/base-types/standard-numeric-format-strings) et [personnalisé](/dotnet/standard/base-types/custom-numeric-format-strings).

## <a name="syntax-1"></a>Syntaxe 1

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a>Syntaxe 2

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a>Arguments

`number` : *Entier* ou *Réel*

Valeur numérique qui spécifie le numéro qui doit être mis en forme.

`format` : *Chaîne*

Valeur *Chaîne* qui représente le format.

`culture` : *Chaîne*

Valeur de *Chaîne* qui représente la culture à utiliser pour la mise en forme.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Si la culture n’est pas définie comme argument de la fonction appelée, le contexte dans lequel cette fonction est exécutée détermine la culture utilisée pour formater les nombres.

## <a name="example-1"></a>Exemple 1

Pour la culture **EN-US**, `NUMBERFORMAT (0.45, "p")` renvoie **"45,00 %"** et `NUMBERFORMAT (10.45, "#")` renvoie **"10"**.

## <a name="example-2"></a>Exemple 2

`NUMBERFORMAT (10/3, "F2", "de")` renvoie **3,33**, tandis que `NUMBERFORMAT (10/3, "F2", "en-us")` renvoie **3,33**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
