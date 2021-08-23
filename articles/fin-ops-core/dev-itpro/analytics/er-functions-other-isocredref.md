---
title: Fonction ISOCREDREF ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ISOCREDREF États électroniques (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: e13b9bacc642917e6a520968630fc75fb30bc9dc3fd02b2d9aa3cfb2ceb33790
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737925"
---
# <a name="isocredref-er-function"></a>Fonction ISOCREDREF ER

[!include [banner](../includes/banner.md)]

La fonction `ISOCREDREF` renvoie une valeur de *Chaîne* qui représente une référence créditeur ISO (Organisation internationale de normalisation), en fonction des chiffres et des symboles alphabétiques du numéro de facture spécifié.

## <a name="syntax"></a>Syntaxe

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a>Arguments

`invoice number digits` : *Chaîne*

Valeur de texte qui représente les chiffres d’un numéro de facture.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d’utilisation

> [!NOTE] 
> Pour éliminer des symboles de l’alphabet qui ne sont pas conformes à la norme ISO, l’argument `invoice number digits` doit être traduit avant d’être transmis à cette fonction.

## <a name="example"></a>Exemple

`ISOCredRef ("VEND-200002")` renvoie **« RF23VEND-200002 »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]