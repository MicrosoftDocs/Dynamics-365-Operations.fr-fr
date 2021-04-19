---
title: Fonction PADLEFT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction PADLEFT États électroniques (ER).
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 806b1d318f18b0ade01f7b03909c90b1e4fd29b1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746241"
---
# <a name="padleft-er-function"></a>Fonction PADLEFT ER

[!include [banner](../includes/banner.md)]

La fonction `PADLEFT` renvoie une valeur de *Chaîne* de longueur spécifique, où le début de la chaîne spécifiée est entouré par les caractères spécifiés.

## <a name="syntax"></a>Syntaxe

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur *Chaîne* qui représente le texte d’origine.

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]