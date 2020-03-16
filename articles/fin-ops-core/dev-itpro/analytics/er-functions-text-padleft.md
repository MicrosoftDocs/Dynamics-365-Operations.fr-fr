---
title: Fonction PADLEFT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction PADLEFT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: d11e2d8b46614085156228ab1001d1f9340a05b0
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040961"
---
# <a name="PADLEFT">Fonction PADLEFT ER</a>

[!include [banner](../includes/banner.md)]

La fonction `PADLEFT` renvoie une valeur de *Chaîne* de longueur spécifique, où le début de la chaîne spécifiée est entouré par les caractères spécifiés.

## <a name="syntax"></a>Syntaxe

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur *Chaîne* qui représente le texte d'origine.

`length` : *Entier*

Valeur *Entier* qui représente le nombre final de caractères dans la chaîne entourée.

`padding chars` : *Chaîne*

Les caractères à utiliser pour entourer.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

`PADLEFT ("1234", 10, "`&nbsp;`")` renvoie la chaîne de texte **« &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234 »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)
