---
title: Fonction NUMBERFORMAT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction NUMBERFORMAT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 392135abaf7db05d5ac591ab56312a0e0f6ae5ff
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916796"
---
# <a name="NUMBERFORMAT">Fonction NUMBERFORMAT ER</a>

[!include [banner](../includes/banner.md)]

La fonction `NUMBERFORMAT` renvoie une valeur de *Chaîne* qui présente le nombre spécifié dans le format spécifié et dans une [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) éventuellement spécifiée. Pour plus d'informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).

## <a name="syntax-1"></a>Syntaxe 1

```
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a>Syntaxe 2

```
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a>Arguments

`number` : *Entier* ou *Réel*

Valeur numérique qui spécifie le numéro qui doit être mis en forme.

`format` : *Chaîne*

Valeur *Chaîne* qui représente le format.

`culture` : *Chaîne*

Valeur de *Chaîne* qui représente la culture à utiliser pour la mise en forme.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d'utilisation

Si la culture n'est pas définie comme argument de la fonction appelée, le contexte dans lequel cette fonction est exécutée détermine la culture utilisée pour formater les nombres.

## <a name="example-1"></a>Exemple 1

Pour la culture **EN-US**, `NUMBERFORMAT (0.45, "p")` renvoie **"45,00 %"** et `NUMBERFORMAT (10.45, "#")` renvoie **"10"**.

## <a name="example-2"></a>Exemple 2

`NUMBERFORMAT (10/3, "F2", "de")` renvoie **3,33**, tandis que `NUMBERFORMAT (10/3, "F2", "en-us")` renvoie **3,33**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)
