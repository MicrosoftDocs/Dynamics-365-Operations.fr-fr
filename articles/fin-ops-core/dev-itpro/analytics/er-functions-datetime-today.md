---
title: Fonction TODAY ER
description: Cet article fournit des informations sur l’utilisation de la fonction TODAY États électroniques (ER).
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 66797bedd50abace4aab0a2b87b99ad6470233c0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271701"
---
# <a name="today-er-function"></a>Fonction TODAY ER

[!include [banner](../includes/banner.md)]

La fonction `TODAY` renvoie une valeur *Date* qui représente la date actuelle du serveur d’applications.

## <a name="syntax"></a>Syntaxe

```xpp
TODAY ()
```

## <a name="return-values"></a>Valeurs de retour

*date ;*

Valeur de date résultante.

## <a name="example"></a>Exemple

`DATEFORMAT (TODAY (), "dd-MM-yyyy")` renvoie la date du serveur d’applications actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction du format personnalisé spécifié.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
