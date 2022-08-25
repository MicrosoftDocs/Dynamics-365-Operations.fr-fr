---
title: Fonction STRINGJOIN ER
description: Cet article fournit des informations sur l’utilisation de la fonction STRINGJOIN États électroniques (ER).
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 6510c271ac5e01d841722fdf2c5fd8c7deaf8caf
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271641"
---
# <a name="stringjoin-er-function"></a>Fonction STRINGJOIN ER

[!include [banner](../includes/banner.md)]

La fonction `STRINGJOIN` renvoie une valeur de *Chaîne* composée des valeurs concaténées du champ spécifié dans la liste spécifiée. Les valeurs peuvent être séparées par le séparateur spécifié.

## <a name="syntax"></a>Syntaxe

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

`field` : *Champ*

Chemin d’accès valide d’un champ de type de données *Chaîne* dans la liste spécifiée.

`delimiter` : *Chaîne*

Délimiteur utilisé pour séparer les sous-chaînes.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

Si vous entrez `SPLIT("abc" , 1)` comme source de données **DS**, l’expression `STRINGJOIN (DS, DS.Value, "-")` renvoie **« abc »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
