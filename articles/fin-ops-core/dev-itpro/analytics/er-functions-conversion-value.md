---
title: Fonction VALUE ER
description: Cet article fournit des informations sur l’utilisation de la fonction VALUE États électroniques (ER).
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 0a47637c47ca6c947451efa1230191779401b4e1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277660"
---
# <a name="value-er-function"></a>Fonction VALUE ER

[!include [banner](../includes/banner.md)]

La fonction `VALUE` renvoie une valeur de *Réel* convertie à partir de la chaîne spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
VALUE (text)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur de chaîne à convertir en valeur numérique.

## <a name="return-values"></a>Valeurs de retour

*Réel*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Les virgules et les points (.) sont considérés comme des séparateurs de nombres décimaux, et un trait d’union (-) est utilisé comme signe moins. Une exception est levée à l’exécution si la chaîne spécifiée contient d’autres caractères non numériques.

## <a name="example-1"></a>Exemple 1

`VALUE ("1 234,56")` lève une exception.

## <a name="example-2"></a>Exemple 2

`VALUE ("1234,56")` renvoie **1234,56**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de conversion des types](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
