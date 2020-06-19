---
title: Fonction TODAY ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction TODAY États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 94ef15d1971287e8bf13944bc8f693b567950031
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411435"
---
# <a name=""></a><a name="TODAY">Fonction TODAY ER</a>

[!include [banner](../includes/banner.md)]

La fonction `TODAY` renvoie une valeur *Date* qui représente la date actuelle du serveur d'applications.

## <a name="syntax"></a>Syntaxe

```xpp
TODAY ()
```

## <a name="return-values"></a>Valeurs de retour

*date ;*

Valeur de date résultante.

## <a name="example"></a>Exemple

`DATEFORMAT (TODAY (), "dd-MM-yyyy")` renvoie la date du serveur d'applications actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction du format personnalisé spécifié.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d'heure](er-functions-category-datetime.md)
