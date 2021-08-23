---
title: Fonction SPLIT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction SPLIT États électroniques (ER).
author: NickSelin
ms.date: 04/01/2021
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
ms.openlocfilehash: 4a42b0c7cfa2a8d3dcb7448224c9e88a48276f7d8cdbcce484383a778b8275a5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757319"
---
# <a name="split-er-function"></a>Fonction SPLIT ER

[!include [banner](../includes/banner.md)]

La fonction `SPLIT` fractionne la chaîne d’entrée spécifiée en sous-chaînes et renvoie le résultat sous la forme d’une nouvelle valeur de *Liste des enregistrements*.

## <a name="syntax-1"></a>Syntaxe 1

```vb
SPLIT (input, length)
```

Cette syntaxe permet de fractionner la chaîne d’entrée spécifiée en sous-chaînes, dans la longueur spécifiée.

## <a name="syntax-2"></a>Syntaxe 2

```vb
SPLIT (input, delimiter)
```

Cette syntaxe permet de fractionner la chaîne d’entrée spécifiée en sous-chaînes, en fonction du délimiteur spécifié.

## <a name="arguments"></a>Arguments

`input` : *Chaîne*

Texte à fractionner.

`length` : *Entier*

Longueur maximale d’une seule sous-chaîne.

`delimiter` : *Chaîne*

Délimiteur utilisé pour séparer les sous-chaînes.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La structure d’enregistrement de la liste renvoyée se compose du champ **Valeur** de type *Chaîne*. Chaque enregistrement de la liste renvoyé contient des sous-chaînes générées dans ce champ.

Si l’argument `delimiter` est vide, la nouvelle liste qui est retournée est composée d’un enregistrement avec un champ **Valeur** de type *Chaîne*. Ce champ contient le texte saisi.

Si l’argument `input` est vide, une nouvelle liste vide est retournée. Si l’argument `input` ou `delimiter` n’est pas spécifié (null), une exception d’application est levée.

## <a name="example-1"></a>Exemple 1

`SPLIT ("abcd", 3)` renvoie une liste composée de deux enregistrements avec un champ **Valeur** de type *Chaîne*. Le champ **Valeur** du premier enregistrement contient le texte **"abc"**, et le champ **Valeur** du deuxième enregistrement contient le texte **"d"**.

## <a name="example-2"></a>Exemple 2

`SPLIT ("XAb aBy", "aB")` renvoie une liste composée de trois enregistrements avec un champ **Valeur** de type *Chaîne*. Le champ **Valeur** dans le premier enregistrement contient le texte **"X"**, le champ **Valeur** du deuxième enregistrement contient le texte **"&nbsp;"** et le champ **Valeur** dans le troisième enregistrement contient le texte **"y"**. 

## <a name="example-3"></a>Exemple 3

Vous pouvez utiliser la fonction [INDEX](er-functions-list-index.md) pour accéder aux éléments individuels de la chaîne d'entrée spécifiée. Si vous entrez la source de données **MyList** du type **Champ calculé** et configurez pour elle l'expression `SPLIT("abc", 1)`, l'expression `INDEX(MyList,2).Value` renvoie le texte **« b »**.

## <a name="example-4"></a>Exemple 4

La fonction [ENUMERATE](er-functions-list-enumerate.md) permet également d'accéder aux éléments individuels de la chaîne d'entrée spécifiée. Si vous entrez d'abord la source de données **MyList** du type **Champ calculé** et configurez pour elle l'expression `SPLIT("abc", 1)`, puis entrez la source de données **EnumeratedList** du type **Champ calculé** et configurez pour elle l'expression `ENUMERATE(MyList)`, l'expression `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` renvoie le texte **« b »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
