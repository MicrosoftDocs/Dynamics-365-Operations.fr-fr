---
title: Fonction AND ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction AND États électroniques (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 4d327f0f961a11fecdbc055ffbb1f3d8bc15bcfdd732e2565d0a5e9e2c0a31ca
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756427"
---
# <a name="and-er-function"></a>Fonction AND ER

[!include [banner](../includes/banner.md)]

La fonction `AND` renvoie une valeur *Booléenne* de **TRUE** si toutes les conditions spécifiées sont true. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.

## <a name="syntax"></a>Syntaxe

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Arguments

`condition 1` : *Booléen*

Expression conditionnelle valide qui doit être testée. Cet argument est obligatoire.

`condition N` : *Booléen*

Expression conditionnelle valide qui doit être testée. Ces arguments supplémentaires sont facultatifs.

## <a name="return-values"></a>Valeurs de retour

*Booléen*

Valeur *Booléenne* résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Dans les arguments des fonctions logiques, vous pouvez utiliser des références de sources de données, des valeurs numériques et texte, des valeurs booléennes, des opérateurs de comparaison et d’autres fonctions des états électroniques (ER). Cependant, tous les arguments doivent être évalués en valeur *Booléenne* de **TRUE** ou **FALSE**.

## <a name="example"></a>Exemple

`AND (1=1, "a"="a")` renvoie **TRUE**.

`AND (1=2, "a"="a")` renvoie **FALSE**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions logiques](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]