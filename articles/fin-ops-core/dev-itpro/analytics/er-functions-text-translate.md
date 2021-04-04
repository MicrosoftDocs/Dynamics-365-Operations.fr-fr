---
title: Fonction TRANSLATE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction TRANSLATE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: f17d3439870710766906013e74452c2e76fec4ce
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560011"
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