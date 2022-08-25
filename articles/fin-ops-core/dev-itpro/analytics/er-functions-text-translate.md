---
title: Fonction TRANSLATE ER
description: Cet article fournit des informations sur l’utilisation de la fonction TRANSLATE États électroniques (ER).
author: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: 7a15a28f6efa5333b54aa34938d22a9d6e404cec
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278439"
---
# <a name="translate-er-function"></a>Fonction TRANSLATE ER

[!include [banner](../includes/banner.md)]

La fonction `TRANSLATE` renvoie une valeur *Chaîne* qui contient le résultat du remplacement du caractère du texte spécifié en caractères pour un autre jeu fourni.

## <a name="syntax"></a>Syntaxe

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Chemin d’accès valide d’une source de données du type *Chaîne*.

`pattern` : *Chaîne*

Texte qui doit être remplacé.

`replacement` : *Chaîne*

Texte à utiliser en remplacement.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La fonction `TRANSLATE` remplace un caractère à la fois. La fonction remplace le premier caractère de l’argument `text` avec le premier caractère de l’argument `pattern`, puis le deuxième caractère et suit le même flux jusqu’à sa fin. Lorsqu’un caractère issu des arguments `text` et `pattern` correspond, il est remplacé par un caractère de l’argument `replacement` qui se trouve dans la même position que le caractère de l’argument `pattern`. Si un caractère apparaît plusieurs fois dans l’argument `pattern`, le mappage d’argument `replacement` qui correspond à la première occurrence de ce caractère est utilisé.

## <a name="example-1"></a>Exemple 1

`TRANSLATE ("abcdef", "cd", "GH")` remplace le caractère **« c »** du texte **« abcdef »** avec le caractère **« G »** du texte `replacement` pour les raisons suivantes :
-   Le caractère **« c »** est présenté dans le texte `pattern` en première position.
-   La première position du texte `replacement` contient le caractère **« G »**.

## <a name="example-2"></a>Exemple 2

`TRANSLATE ("abcdef", "ccd", "GH")` renvoie **« abGdef »**.

## <a name="example-3"></a>Exemple 3

`TRANSLATE ("abccba", "abc", "123")` renvoie **« 123321 »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de texte](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
