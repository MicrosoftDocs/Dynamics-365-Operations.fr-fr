---
title: Fonction VALUE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction VALUE États électroniques (ER).
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
ms.openlocfilehash: 160dd81baa43702b2deea1e3eea20080fca122ca
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917624"
---
# <a name="VALUE">Fonction VALUE ER</a>

[!include [banner](../includes/banner.md)]

La fonction `VALUE` renvoie une valeur de *Réel* convertie à partir de la chaîne spécifiée.

## <a name="syntax"></a>Syntaxe

```
VALUE (text)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur de chaîne à convertir en valeur numérique.

## <a name="return-values"></a>Valeurs de retour

*Réel*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d'utilisation

Les virgules et les points (.) sont considérés comme des séparateurs de nombres décimaux, et un trait d'union (-) est utilisé comme signe moins. Une exception est levée à l'exécution si la chaîne spécifiée contient d'autres caractères non numériques.

## <a name="example-1"></a>Exemple 1

`VALUE ("1 234,56")` lève une exception.

## <a name="example-2"></a>Exemple 2

`VALUE ("1234,56")` renvoie **1234,56**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de conversion des types](er-functions-category-type-conversion.md)
