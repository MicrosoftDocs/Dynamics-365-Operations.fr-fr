---
title: Fonction AND ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction AND États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 068b9a3b2cf2e5bffe895bc4e8a7cbb2d8025ad7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560083"
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