---
title: Fonction COUNT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction COUNT États électroniques (ER).
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
ms.openlocfilehash: 0fc122dafd6be90d090ba3b79a8c2eccab74d77441f82db71cb5e08d13d13518
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6753644"
---
# <a name="count-er-function"></a>Fonction COUNT ER

[!include [banner](../includes/banner.md)]

La fonction `COUNT` renvoie une valeur *Entier* qui représente le nombre d’enregistrements dans la liste spécifiée, si la liste n’est pas vide. Si la liste est vide, cette fonction renvoie **0** (zéro).

## <a name="syntax"></a>Syntaxe

```vb
COUNT (list)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

## <a name="return-values"></a>Valeurs de retour

*Entier*

Valeur numérique résultante.

## <a name="example"></a>Exemple

`COUNT (SPLIT("abcd" , 3))` renvoie **2**, parce que la fonction `SPLIT` utilisée dans cet exemple crée une liste composée de deux enregistrements.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]