---
title: Fonction OR ER
description: Cet article fournit des informations sur l’utilisation de la fonction OR États électroniques (ER).
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
ms.openlocfilehash: 99b5ee37af1ea1a69985fb79b762b31561334fd6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268084"
---
# <a name="or-er-function"></a>Fonction OR ER

[!include [banner](../includes/banner.md)]

La fonction `OR` renvoie une valeur *Booléenne* de **FALSE** si toutes les conditions spécifiées sont false. Si toutes les conditions spécifiées sont true, la fonction renvoie une valeur *Booléenne* de **TRUE**.

## <a name="syntax"></a>Syntaxe

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Arguments

`condition 1` : *Booléen*

Expression conditionnelle valide qui doit être testée. Cet argument est obligatoire.

`condition N` : *Booléen*

Expression conditionnelle valide qui doit être testée. Ces arguments supplémentaires sont facultatifs.

## <a name="return-values"></a>Valeurs de retour

*Booléen*

Valeur *Booléenne* résultante.

## <a name="example"></a>Exemple

`OR (1=2, "a"="a")` renvoie **TRUE**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions logiques](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
