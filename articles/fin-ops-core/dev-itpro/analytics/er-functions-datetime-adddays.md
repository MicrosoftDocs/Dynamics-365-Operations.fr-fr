---
title: Fonction ADDDAYS ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ADDDAYS États électroniques (ER).
author: NickSelin
ms.date: 12/03/2019
ms.topic: article
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
ms.openlocfilehash: 0c420daa04b8e22504d25d317c75826f1d1914b7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747057"
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