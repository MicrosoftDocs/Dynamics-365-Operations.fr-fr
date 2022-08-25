---
title: Fonction POWER ER
description: Cet article fournit des informations sur l’utilisation de la fonction POWER États électroniques (ER).
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 9b6693d7c1afebcf9c30d1bf8d72950053c305bd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273993"
---
# <a name="power-er-function"></a>Fonction POWER ER

[!include [banner](../includes/banner.md)]

La fonction `POWER` renvoie une valeur de *Réel* qui représente le résultat de l’augmentation du nombre positif spécifié à la puissance spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
