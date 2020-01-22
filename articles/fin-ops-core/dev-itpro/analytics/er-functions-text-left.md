---
title: Fonction LEFT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction LEFT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 8280a05ea180d9de499d87efa53eca8ca912b0e3
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915646"
---
# <a name="LEFT">Fonction LEFT ER</a>

[!include [banner](../includes/banner.md)]

La fonction `LEFT` renvoie une valeur de *Chaîne* qui présente le nombre de caractères spécifié à partir du début de la chaîne spécifiée.

## <a name="syntax"></a>Syntaxe

```
LEFT (text, number)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur *Chaîne* qui représente le texte d'origine.

`number` : *Entier*

Nombre de caractères qui doivent être renvoyés à partir du début du texte d'origine.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

`LEFT ("Sample", 3)` renvoie **« Sam »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)
