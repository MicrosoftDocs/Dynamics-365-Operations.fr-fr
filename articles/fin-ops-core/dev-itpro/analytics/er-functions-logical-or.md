---
title: Fonction OR ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction OR États électroniques (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 9763cdbabfbaba1af433c1fd753b03982ecb550d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751714"
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