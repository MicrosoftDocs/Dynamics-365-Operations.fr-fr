---
title: Fonction POWER ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction POWER États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: cb768b400e3ddb99e7c8b05905d7a2dd9e4392de
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915899"
---
# <a name="POWER">Fonction POWER ER</a>

[!include [banner](../includes/banner.md)]

La fonction `POWER` renvoie une valeur de *Réel* qui représente le résultat de l'augmentation du nombre positif spécifié à la puissance spécifiée.

## <a name="syntax"></a>Syntaxe

```
POWER (number, power)
```

## <a name="arguments"></a>Arguments

`number` : *Réel* ou *Entier*

Valeur numérique qui doit être élevée à la puissance spécifiée.

`power` : *Réel* ou *Entier*

Valeur numérique qui représente la puissance spécifique.

## <a name="return-values"></a>Valeurs de retour

*Réel*

Valeur numérique résultante.

## <a name="example-1"></a>Exemple 1

`POWER (10, 2)` renvoie **100**.

## <a name="example-2"></a>Exemple 2

`POWER (4, 0.5)` renvoie **2**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions mathématiques](er-functions-category-mathematical.md)
