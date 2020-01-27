---
title: Fonction ADDDAYS ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction ADDDAYS États électroniques (ER).
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
ms.openlocfilehash: dd1290538c506cd0db6eb21a304ff9812c808f17
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916451"
---
# <a name="ADDDAYS">Fonction ADDDAYS ER</a>

[!include [banner](../includes/banner.md)]

La fonction `ADDDAYS` calcule une valeur de *DateTime* qui est le nombre de jours spécifié avant ou après une date de début spécifiée.

## <a name="syntax"></a>Syntaxe

```
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

## <a name="usage-notes"></a>Notes d'utilisation

Une valeur positive pour `days` donne une date future. Une valeur négative donne une date passée.

## <a name="example-1"></a>Exemple 1

`ADDDAYS (NOW(), 7)` renvoie la date et l'heure, sept jours dans le futur.

## <a name="example-2"></a>Exemple 2

`ADDDAYS (NOW(), -3)` renvoie la date et l'heure, trois jours dans le passé.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d'heure](er-functions-category-datetime.md)
