---
title: Fonction IF ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction IF États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 87e252a2751beeecb51e512cae38b271c1456fae
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744693"
---
# <a name="if-er-function"></a>Fonction IF ER

[!include [banner](../includes/banner.md)]

La fonction `IF` renvoie la première valeur spécifiée si la condition spécifiée est remplie. Sinon, elle renvoie la deuxième valeur spécifiée. La valeur renvoyée peut être une valeur de n’importe quel type de données pris en charge.

## <a name="syntax"></a>Syntaxe

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a>Arguments

`condition` : *Booléen*

Expression conditionnelle valide qui doit être testée.

`first value` : *N’importe lequel des types de données pris en charge*

Résultat renvoyé si la condition est remplie.

`second value` : *N’importe lequel des types de données pris en charge*

Résultat renvoyé si la condition n’est pas remplie.

## <a name="return-values"></a>Valeurs de retour

*N’importe lequel des types de données pris en charge*

Valeur résultante de l’un des types de données pris en charge.

## <a name="usage-notes"></a>Notes d’utilisation

Les arguments `first value` et `second value` doivent être spécifiés en utilisant le même type de données. Une exception est levée au moment de la conception si les types de données des valeurs configurées ne correspondent pas.

Si la première valeur et la seconde valeur sont des valeurs de type de données *Conteneur (enregistrement)* ou *Liste des enregistrements*, le résultat n’a que les champs qui existent dans les deux valeurs.

## <a name="example"></a>Exemple

`IF (1=2, "condition is met", "condition is not met")` renvoie la chaîne **la condition n’est pas remplie**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions logiques](er-functions-category-logical.md)
