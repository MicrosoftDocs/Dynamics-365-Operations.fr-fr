---
title: Fonction AND ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction AND États électroniques (ER).
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
ms.openlocfilehash: dd9c0ed0238009f70ad7a9bf5a5e19ebfb95cccc
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917164"
---
# <a name="AND">Fonction AND ER</a>

[!include [banner](../includes/banner.md)]

La fonction `AND` renvoie une valeur *Booléenne* de **TRUE** si toutes les conditions spécifiées sont true. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.

## <a name="syntax"></a>Syntaxe

```
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

## <a name="usage-notes"></a>Notes d'utilisation

Dans les arguments des fonctions logiques, vous pouvez utiliser des références de sources de données, des valeurs numériques et texte, des valeurs booléennes, des opérateurs de comparaison et d'autres fonctions des états électroniques (ER). Cependant, tous les arguments doivent être évalués en valeur *Booléenne* de **TRUE** ou **FALSE**.

## <a name="example"></a>Exemple

`AND (1=1, "a"="a")` renvoie **TRUE**.

`AND (1=2, "a"="a")` renvoie **FALSE**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions logiques](er-functions-category-logical.md)
