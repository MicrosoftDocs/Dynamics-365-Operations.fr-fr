---
title: Fonction NOT ER
description: Cet article fournit des informations sur l’utilisation de la fonction NOT États électroniques (ER).
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
ms.openlocfilehash: 032cdaa2c71f6fab8c15780594d5a26d73600e74
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278974"
---
# <a name="not-er-function"></a>Fonction NOT ER

[!include [banner](../includes/banner.md)]

La fonction `NOT` renvoie la valeur logique inversée de la condition spécifiée en tant que valeur *Booléenne*.

## <a name="syntax"></a>Syntaxe

```vb
NOT (condition)
```

## <a name="arguments"></a>Arguments

`condition` : *Booléen*

Expression conditionnelle valide qui doit être inversée.

## <a name="return-values"></a>Valeurs de retour

*Booléen*

Valeur *Booléenne* résultante.

## <a name="example"></a>Exemple

`NOT (TRUE)` renvoie **FALSE**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions logiques](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
