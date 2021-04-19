---
title: Fonction CHAR ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CHAR États électroniques (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: a621328817171be7df0622507c84f5c6f6fe90a1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746433"
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

La chaîne retournée par cette fonction dépend de l’encodage sélectionné dans l’élément de format **FILE** parent. Pour obtenir une liste des codages pris en charge, consultez [Classe de codage](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).

## <a name="example"></a>Exemple

`CHAR (255)` renvoie **« ÿ »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]