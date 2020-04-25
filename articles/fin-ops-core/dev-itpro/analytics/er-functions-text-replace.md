---
title: Fonction REPLACE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction REPLACE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: 83d5095620a938f1ac4b8428fff9209fda7a7831
ms.sourcegitcommit: fb8ad8e2b142441a6530b364f3258bbcc0c724d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201064"
---
# <a name=""></a><a name="REPLACE">Fonction REPLACE ER</a>

[!include [banner](../includes/banner.md)]

La fonction `REPLACE` renvoie la chaîne de texte spécifiée sous la forme d'une valeur de *Chaîne* après que tout ou partie de celui-ci a été remplacé par une autre chaîne.

## <a name="syntax"></a>Syntaxe

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Chemin d'accès valide d'une source de données du type *Chaîne*.

`pattern` : *Chaîne*

Si l'argument `regular expression flag` est **FALSE**, cet argument contient le texte qui doit être remplacé.

Si l'argument `regular expression flag` est **TRUE**, cet argument contient une expression régulière qui définit à la fois un modèle de recherche et le texte de remplacement.

`replacement` : *Chaîne*

Si l'argument `regular expression flag` est **FALSE**, cet argument contient le texte à utiliser comme remplacement.

Si l'argument `regular expression flag` est **TRUE**, cet argument n'est pas utilisé.

`regular expression flag` : *Booléen*

Valeur *Booléenne* qui indique si une expression régulière est utilisée pour effectuer le remplacement.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d'utilisation

Si l'argument `regular expression flag` est **TRUE**, cette fonction renvoie la chaîne spécifiée après sa modification en appliquant l'expression régulière spécifiée par l'argument `pattern`. L'expression régulière est utilisée pour rechercher les caractères qui doivent être remplacés.

Si l'argument `regular expression flag` est **FALSE**, cette fonction renvoie une chaîne spécifique après que l'ensemble de caractères définis dans l'argument `pattern` ait été remplacé par les caractères de l'argument `replacement`. 

## <a name="example-1"></a>Exemple 1

`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applique une expression régulière qui supprime tous les symboles non-numériques, et renvoie **"19234564971"**. 

## <a name="example-2"></a>Exemple 2

`REPLACE ("abcdef", "cd", "GH", false)` remplace le modèle **cd** par la chaîne **« GH »** et renvoie **abGHef**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)
