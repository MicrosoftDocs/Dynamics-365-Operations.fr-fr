---
title: Fonction SESSIONTODAY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction SESSIONTODAY États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: e6ad28e642fcfae3cfa2692a4e41b99fae7fc9df
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561347"
---
# <a name="sessiontoday-er-function"></a>Fonction SESSIONTODAY ER

[!include [banner](../includes/banner.md)]

La fonction `SESSIONTODAY` renvoie une valeur *Date* qui représente la date actuelle de la session de l’application.

## <a name="syntax"></a>Syntaxe

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a>Valeurs de retour

*Date*

Valeur de date résultante.

## <a name="example"></a>Exemple

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` renvoie la date de la session de l’application actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction de la culture allemande et du format sélectionnés spécifiés.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]