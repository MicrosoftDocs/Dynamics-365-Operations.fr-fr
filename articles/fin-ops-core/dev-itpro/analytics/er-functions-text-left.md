---
title: Fonction LEFT ER
description: Cet article fournit des informations sur l’utilisation de la fonction LEFT États électroniques (ER).
author: NickSelin
ms.date: 12/11/2019
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
ms.openlocfilehash: 51842c56053f9de8ea7f65bcda71d606f42f8bf1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852631"
---
# <a name="left-er-function"></a>Fonction LEFT ER

[!include [banner](../includes/banner.md)]

La fonction `LEFT` renvoie une valeur de *Chaîne* qui présente le nombre de caractères spécifié à partir du début de la chaîne spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
LEFT (text, number)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur *Chaîne* qui représente le texte d’origine.

`number` : *Entier*

Nombre de caractères qui doivent être renvoyés à partir du début du texte d’origine.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

`LEFT ("Sample", 3)` renvoie **« Sam »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]