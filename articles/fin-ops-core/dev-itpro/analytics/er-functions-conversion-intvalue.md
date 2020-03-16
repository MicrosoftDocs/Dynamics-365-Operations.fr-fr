---
title: Fonction INTVALUE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction INTVALUE États électroniques (ER).
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
ms.openlocfilehash: 5e06236bf1d158a4cf579b8b89cc0a5f7d815c38
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042647"
---
# <a name="INTVALUE">Fonction INTVALUE ER</a>

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

## <a name="usage-notes"></a>Notes d'utilisation

Les décimales sont tronquées.

## <a name="example-1"></a>Exemple 1

`INTVALUE ("100.77")` renvoie la valeur *Int* **100**.

## <a name="example-2"></a>Exemple 2

`INTVALUE (-100.77)` renvoie la valeur *Int* **-100**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de conversion des types](er-functions-category-type-conversion.md)
