---
title: Fonction DAYS ER
description: Cet article fournit des informations sur l’utilisation de la fonction DAYS États électroniques (ER).
author: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: a0c50e36bbf0c2bd999a17631e3e00d2feb162fd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268723"
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
