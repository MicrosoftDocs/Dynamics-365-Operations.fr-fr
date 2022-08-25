---
title: Fonction EMPTYLIST ER
description: Cet article fournit des informations sur l’utilisation de la fonction EMPTYLIST États électroniques (ER).
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
ms.openlocfilehash: 5fd14456a615d5dc6fb565f4bed523db5432c871
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268114"
---
# <a name="emptylist-er-function"></a>Fonction EMPTYLIST ER

[!include [banner](../includes/banner.md)]

La fonction `EMPTYLIST` renvoie une valeur de *Liste d’enregistrements* à l’aide de la liste spécifiée comme source pour la structure de liste.

## <a name="syntax"></a>Syntaxe

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="example"></a>Exemple

`EMPTYLIST (SPLIT ("abc", 1))` renvoie une nouvelle liste vide ayant la même structure que la liste qui est renvoyée par la fonction `SPLIT` utilisée.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
