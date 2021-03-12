---
title: Fonction DATEFORMAT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction DATEFORMAT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: cdc1671f818bc2c4d8a78d0a35337298e83c5060
ms.sourcegitcommit: 7cfe8931dd454e811a691f5118a4ecae7ba4b478
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/04/2021
ms.locfileid: "4826009"
---
# <a name="dateformat-er-function"></a>Fonction DATEFORMAT ER

[!include [banner](../includes/banner.md)]

La fonction `DATEFORMAT` renvoie une valeur de *Chaîne* qui présente une valeur de date donnée dans le format spécifié et dans une [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) éventuellement spécifiée. Pour plus d’informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Syntaxe 1

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a>Syntaxe 2

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a>Arguments

`date` : *Date*

Valeur de date qui représente la date à mettre en forme.

`format` : *Chaîne*

Format de la chaîne de sortie.

> [!NOTE]
> La chaîne de format est sensible à la casse lorsque vous utilisez un format standard ou un format personnalisé. Par exemple, le spécificateur de format [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) « d »renvoie la date à l’aide du schéma de date courte, tandis que le spécificateur de format standard « D » renvoie la date à l’aide du schéma de date longue. De plus, le spécificateur de format [personnalisé](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) « M » renvoie le mois de 1 à 12, tandis que le spécificateur de format personnalisé « m » renvoie les minutes de 0 à 59.

`culture` : *Chaîne*

Culture à utiliser pour la mise en forme.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de la chaîne résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Si la culture n’est pas définie comme un argument de la fonction appelée, la valeur de `culture` est définie par le contexte d’appel. Par exemple, si la fonction `DATEFORMAT` est appelée en utilisant la syntaxe 1 dans un format d’états électroniques (ER) pour un élément **FILE** configuré pour utiliser la culture allemande, la conversion se fera en utilisant la culture allemande. La valeur `culture` par défaut est **EN-US**.

## <a name="example-1"></a>Exemple 1

`DATEFORMAT (TODAY (), "dd-MM-yyyy")` renvoie la date du serveur d’applications actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction du format personnalisé spécifié.

## <a name="example-2"></a>Exemple 2

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` renvoie la date de la session de l’application actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction de la culture allemande et du format sélectionnés spécifiés.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)
