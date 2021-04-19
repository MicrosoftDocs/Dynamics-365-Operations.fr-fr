---
title: Fonction FIRSTORNULL ER
description: Cette rubrique explique l’utilisation de la fonction FIRSTORNULL États électroniques (ER)
author: NickSelin
ms.date: 11/29/2019
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
ms.openlocfilehash: 1ccc094fc468470ffc857c729b6d8402796785d7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753214"
---
# <a name="firstornull-er-function"></a>Fonction FIRSTORNULL ER

[!include [banner](../includes/banner.md)]

La fonction `FIRSTORNULL` renvoie le premier enregistrement de la liste spécifiée sous la forme d’une valeur de *Conteneur (enregistrement)*, si cet enregistrement n’est pas vide. Si l’enregistrement est vide, cette fonction renvoie une valeur de *Conteneur (enregistrement)* null.

## <a name="syntax"></a>Syntaxe

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

## <a name="return-values"></a>Valeurs de retour

*Conteneur (enregistrement)*

Valeur de l’enregistrement résultante.

## <a name="example"></a>Exemple

L’expression `FIRSTORNULL(SPLIT("",1)).Value` renvoie une chaîne vide (**""**).

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]