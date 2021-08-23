---
title: Fonction STRINGJOIN ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction STRINGJOIN États électroniques (ER).
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
ms.openlocfilehash: 651cc261e6a33b1a824feb94afa767e439196e249bb13b0fc4886dc72bfdd184
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776096"
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