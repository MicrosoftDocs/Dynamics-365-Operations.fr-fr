---
title: Fonction DAYOFYEAR ER
description: Cet article fournit des informations sur l’utilisation de la fonction DAYOFYEAR États électroniques (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: fc4d1d3293c31b1b89a7390c8ac313e1407d433e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848778"
---
# <a name="dayofyear-er-function"></a>Fonction DAYOFYEAR ER

[!include [banner](../includes/banner.md)]

La fonction `DAYOFYEAR` renvoie une valeur *Entier* qui représente sous forme de nombre entier du nombre de jours entre le 1er janvier et la date spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a>Arguments

`date` : *Date*

Valeur de date qui représente la date à utiliser pour le calcul du nombre de jours.

## <a name="return-values"></a>Valeurs de retour

*Entier*

Valeur numérique résultante.

## <a name="example-1"></a>Exemple 1

`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` renvoie **61**.

## <a name="example-2"></a>Exemple 2

`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` renvoie **1**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]