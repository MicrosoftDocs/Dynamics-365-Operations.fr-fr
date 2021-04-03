---
title: CN_GBT_ADDITIONALDIMENSIONID ER, fonction
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CN_GBT_ADDITIONALDIMENSIONID États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 5774bb6928ae321af923819d6b2cc609dbf35b99
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564140"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a>CN_GBT_ADDITIONALDIMENSIONID ER, fonction

[!include [banner](../includes/banner.md)]

La fonction `CN_GBT_ADDITIONALDIMENSIONID` renvoie une valeur de *Chaîne* qui représente un ID de dimension financière unique extrait de la chaîne spécifiée. La chaîne spécifiée présente toutes les dimensions sous la forme d’une liste d’ID séparés par des virgules.

## <a name="syntax"></a>Syntaxe

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur de *Chaîne* qui présente toutes les dimensions sous la forme d’une liste d’ID séparés par des virgules.

`number` : Entier

Valeur *Entier* qui définit le code souche de la dimension demandée dans la chaîne spécifiée.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` renvoie **« CC »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]