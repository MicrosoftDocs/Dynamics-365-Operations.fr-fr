---
title: Fonction INTVALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction INTVALUE États électroniques (ER).
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
ms.openlocfilehash: c5c3e4c8bd918fa1154d2c111970d2f6d0e90e08
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743637"
---
# <a name="intvalue-er-function"></a>Fonction INTVALUE ER

[!include [banner](../includes/banner.md)]

La fonction `INTVALUE` renvoie une valeur *Int* qui représente la chaîne spécifiée.

## <a name="syntax-1"></a>Syntaxe 1

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a>Syntaxe 2

```vb
INTVALUE (number)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur de texte qui doit être convertie en nombre *Int*.

`number` : *Réel* ou *Entier*

Valeur *Réel* ou *Entier* numérique qui doit être convertie en nombre *Int*.

## <a name="return-values"></a>Valeurs de retour

*Int*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Les décimales sont tronquées.

## <a name="example-1"></a>Exemple 1

`INTVALUE ("100.77")` renvoie la valeur *Int* **100**.

## <a name="example-2"></a>Exemple 2

`INTVALUE (-100.77)` renvoie la valeur *Int* **-100**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de conversion des types](er-functions-category-type-conversion.md)
