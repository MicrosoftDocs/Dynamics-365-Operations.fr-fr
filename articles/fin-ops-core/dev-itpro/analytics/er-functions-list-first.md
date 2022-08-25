---
title: Fonction FIRST ER
description: Cet article fournit des informations sur l’utilisation de la fonction FIRST États électroniques (ER).
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: b06f07c4cfef5c74c22f60dfa37986ee88c544cf
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275477"
---
# <a name="first-er-function"></a>Fonction FIRST ER

[!include [banner](../includes/banner.md)]

La fonction `FIRST` renvoie le premier enregistrement de la liste spécifiée sous la forme d’une valeur de *Conteneur (enregistrement)*, si cette liste n’est pas vide. Si la liste est vide, cette fonction lève une exception.

## <a name="syntax"></a>Syntaxe

```vb
FIRST (list)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

## <a name="return-values"></a>Valeurs de retour

*Conteneur (enregistrement)*

Valeur de l’enregistrement résultante.

## <a name="example-1"></a>Exemple 1

L’expression `FIRST(SPLIT("ABC",1)).Value` renvoie la valeur texte **« A »**.

## <a name="example-2"></a>Exemple 2

L’expression `FIRST(SPLIT("",1)).Value` lève une exception lors de l’exécution.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
