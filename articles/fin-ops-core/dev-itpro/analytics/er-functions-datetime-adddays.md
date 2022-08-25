---
title: Fonction ADDDAYS ER
description: Cet article fournit des informations sur l’utilisation de la fonction ADDDAYS États électroniques (ER).
author: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 69273794def0dc52dc8e31615c319ccf5067fa77
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274137"
---
# <a name="adddays-er-function"></a>Fonction ADDDAYS ER

[!include [banner](../includes/banner.md)]

La fonction `ADDDAYS` calcule une valeur de *DateTime* qui est le nombre de jours spécifié avant ou après une date de début spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a>Arguments

`datetime` : *DateTime*

Valeur de date/heure qui représente la date de début.

`days` : *Entier*

Nombre de jours avant ou après `datetime`.

## <a name="return-values"></a>Valeurs de retour

*Date et heure*

Valeur de date/heure résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Une valeur positive pour `days` donne une date future. Une valeur négative donne une date passée.

## <a name="example-1"></a>Exemple 1

`ADDDAYS (NOW(), 7)` renvoie la date et l’heure, sept jours dans le futur.

## <a name="example-2"></a>Exemple 2

`ADDDAYS (NOW(), -3)` renvoie la date et l’heure, trois jours dans le passé.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
