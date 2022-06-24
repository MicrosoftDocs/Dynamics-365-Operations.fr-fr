---
title: Fonction CONCATENATE ER
description: Cet article fournit des informations sur l’utilisation de la fonction CONCATENATE États électroniques (ER)
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
ms.openlocfilehash: 926c3acf92fc8017c3c4a7814855a6871c1cacc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863262"
---
# <a name="concatenate-er-function"></a>Fonction CONCATENATE ER

[!include [banner](../includes/banner.md)]

La fonction `CONCATENATE` renvoie toutes les chaînes de texte spécifiées en tant que valeur de *Chaîne* après avoir été jointes en une seule chaîne.

## <a name="syntax"></a>Syntaxe

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>Arguments

`text 1` : *Chaîne*

Référence à une source de données du type de données *Chaîne*. Cet argument est obligatoire.

`text N` : *Chaîne*

Référence à une source de données du type de données *Chaîne*. Ces arguments supplémentaires sont facultatifs.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

`CONCATENATE ("abc", "def")` renvoie **« abcdef »**.

## <a name="usage-notes"></a>Notes d’utilisation

L’expression `"abc" & "def"` renvoie également **« abcdef »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]