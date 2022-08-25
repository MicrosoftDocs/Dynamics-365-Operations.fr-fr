---
title: Fonction CHAR ER
description: Cet article fournit des informations sur l’utilisation de la fonction CHAR États électroniques (ER).
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
ms.openlocfilehash: 61e402718723325fc975d577ab76039e3e59691e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288046"
---
# <a name="char-er-function"></a>Fonction CHAR ER

[!include [banner](../includes/banner.md)]

La fonction `CHAR` renvoie une valeur de *Chaîne* qui présente un seul caractère référencé par le numéro Unicode spécifié.

## <a name="syntax"></a>Syntaxe

```vb
CHAR (number)
```

## <a name="arguments"></a>Arguments

`number` : *Entier*

Nombre qui correspond à un seul caractère attendu.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La chaîne retournée par cette fonction dépend de l’encodage sélectionné dans l’élément de format **FILE** parent. Pour obtenir une liste des codages pris en charge, consultez [Classe de codage](/dotnet/api/system.text.encoding).

## <a name="example"></a>Exemple

`CHAR (255)` renvoie **« ÿ »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
