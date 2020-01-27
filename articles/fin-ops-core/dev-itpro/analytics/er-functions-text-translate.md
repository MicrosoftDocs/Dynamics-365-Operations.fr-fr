---
title: Fonction TRANSLATE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction TRANSLATE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 11954f3e48d8dc2257b3a0bc8768df47af3c5c0c
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916704"
---
# <a name="TRANSLATE">Fonction TRANSLATE ER</a>

[!include [banner](../includes/banner.md)]

La fonction `TRANSLATE` renvoie la chaîne de texte spécifiée sous la forme d'une valeur de *Chaîne* après que tout ou partie de celui-ci a été remplacé par une autre chaîne.

## <a name="syntax"></a>Syntaxe

```
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Chemin d'accès valide d'une source de données du type *Chaîne*.

`pattern` : *Chaîne*

Texte qui doit être remplacé.

`replacement` : *Chaîne*

Texte à utiliser en remplacement.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

`TRANSLATE ("abcdef", "cd", "GH")` remplace le modèle **cd** par la chaîne **« GH »** et renvoie **abGHef**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)
