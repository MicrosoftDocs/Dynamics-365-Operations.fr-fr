---
title: CN_GBT_ADDITIONALDIMENSIONID ER, fonction
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CN_GBT_ADDITIONALDIMENSIONID États électroniques (ER).
author: NickSelin
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
ms.openlocfilehash: ac0b54476265171b3826e43600f99097701231e1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744389"
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