---
title: Fonction SESSIONNOW ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction SESSIONNOW États électroniques (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 47b88a1ca0ea9fd09c2a82963901d9ace78891bb
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746792"
---
# <a name="sessionnow-er-function"></a>Fonction SESSIONNOW ER

[!include [banner](../includes/banner.md)]

La fonction `SESSIONNOW` renvoie une valeur *DateTime* qui représente la date et l’heure actuelles de la session de l’application.

## <a name="syntax"></a>Syntaxe

```vb
SESSIONNOW ()
```

## <a name="return-values"></a>Valeurs de retour

*Date et heure*

Valeur de date/heure résultante.

## <a name="example"></a>Exemple

`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` renvoie la valeur de date/heure de la session de l’application actuelle, 24 décembre 2015, sous la forme de **« 24.12.2015 »**, en fonction de la culture allemande et du format sélectionnés spécifiés.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]