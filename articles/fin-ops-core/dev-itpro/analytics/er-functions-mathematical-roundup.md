---
title: Fonction ROUNDUP ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction ROUNDUP États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 84a62639b49db17fef1abcda75bc5ad7f08d1005
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917049"
---
# <a name="ROUNDUP">Fonction ROUNDUP ER</a>

[!include [banner](../includes/banner.md)]

La fonction `ROUNDUP` renvoie le nombre spécifié comme valeur *Réelle* une fois qu'il a été arrondi au nombre supérieur de décimales spécifié.

## <a name="syntax"></a>Syntaxe

```
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Arguments

`number` : *Réel*

Valeur numérique qui doit être arrondie.

`decimals` : *Entier*

Valeur numérique qui représente les nombre de décimales.

## <a name="return-values"></a>Valeurs de retour

*Réel*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d'utilisation

Cette fonction se comporte comme [ROUND](er-functions-mathematical-round.md), mais elle arrondit toujours le nombre spécifié vers le haut (loin de zéro).

## <a name="example-1"></a>Exemple 1

`ROUNDUP (1200.763, 2)` arrondit vers le haut à deux décimales et renvoie **1200,77**.

## <a name="example-2"></a>Exemple 2

`ROUNDUP (1200.767, -3)` arrondit vers le haut au multiple de 1 000 le plus proche et renvoie **2 000**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions mathématiques](er-functions-category-mathematical.md)
