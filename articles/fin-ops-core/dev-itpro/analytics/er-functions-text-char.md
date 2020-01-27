---
title: Fonction CHAR ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction CHAR États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d42afcf97690351763138fd9e16265aa104a6bc4
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915738"
---
# <a name="CHAR">Fonction CHAR ER</a>

[!include [banner](../includes/banner.md)]

La fonction `CHAR` renvoie une valeur de *Chaîne* qui présente un seul caractère référencé par le numéro Unicode spécifié.

## <a name="syntax"></a>Syntaxe

```
CHAR (number)
```

## <a name="arguments"></a>Arguments

`number` : *Entier*

Nombre qui correspond à un seul caractère attendu.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d'utilisation

La chaîne retournée par cette fonction dépend de l'encodage sélectionné dans l'élément de format **FILE** parent. Pour obtenir une liste des codages pris en charge, consultez [Classe de codage](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).

## <a name="example"></a>Exemple

`CHAR (255)` renvoie **« ÿ »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)
