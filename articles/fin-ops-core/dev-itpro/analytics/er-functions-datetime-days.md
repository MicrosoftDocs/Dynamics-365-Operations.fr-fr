---
title: Fonction DAYS ER
description: Cet article fournit des informations sur l’utilisation de la fonction DAYS États électroniques (ER).
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
ms.openlocfilehash: 41a324ca93497f8b297c8c944f622b7829f1ceff
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881216"
---
# <a name="days-er-function"></a>Fonction DAYS ER

[!include [banner](../includes/banner.md)]

La fonction `DAYS` renvoie une valeur *Entier* qui représente sous forme de nombre entier du nombre de jours entre une date spécifiée et une autre date donnée.

## <a name="syntax"></a>Syntaxe

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a>Arguments

`date 1` : *Date*

Valeur de date qui représente la date de début pour le calcul du nombre de jours.

`date 2` : *Date*

Valeur de date qui représente la date de fin pour le calcul du nombre de jours.

## <a name="return-values"></a>Valeurs de retour

*Entier*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La fonction `DAYS` renvoie une valeur positive lorsque la première date est postérieure à la deuxième date ; renvoie **0** (zéro) lorsque la première date est égale à la deuxième date ; sinon, renvoie une valeur négative lorsque la première date est antérieure à la deuxième date.

## <a name="example"></a>Exemple

`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` renvoie **-1**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]