---
title: Fonction MID ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction MID États électroniques (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: e0520bc54465f00d36e88787933b291847dee852
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562731"
---
# <a name="mid-er-function"></a>Fonction MID ER

[!include [banner](../includes/banner.md)]

La fonction `MID` renvoie une valeur de *Chaîne* qui présente le nombre de caractères spécifié à partir de la chaîne spécifiée, à partir de la position donnée.

## <a name="syntax"></a>Syntaxe

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur de *Chaîne* qui spécifie le texte à partir duquel retourner les caractères.

`starting position` : *Entier*

Valeur *Entier* qui spécifie la position du premier caractère qui doit être renvoyé à partir du texte spécifié.

`number of characters` : *Entier*

Valeur *Entier* qui spécifie le nombre de caractères qui doit être renvoyé, à partir de la position de début spécifiée.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Si la valeur de l’argument `starting position` est inférieure à 0 (zéro), les caractères renvoyés sont comptés à partir de la première position de la chaîne spécifiée.

Si la valeur de l’argument `starting position` dépasse la longueur de la chaîne spécifiée, une chaîne vide est renvoyée.

## <a name="example"></a>Exemple

`MID ("Sample", 2, 3)` renvoie **"amp"**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]