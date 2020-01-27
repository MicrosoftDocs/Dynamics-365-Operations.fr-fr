---
title: Fonction ISOCREDREF ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction ISOCREDREF États électroniques (ER).
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
ms.openlocfilehash: ea72d824d3a98d7685a965e981d057991f012a0e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916957"
---
# <a name="ISOCREDREF">Fonction ISOCREDREF ER</a>

[!include [banner](../includes/banner.md)]

La fonction `ISOCREDREF` renvoie une valeur de *Chaîne* qui représente une référence créditeur ISO (Organisation internationale de normalisation), en fonction des chiffres et des symboles alphabétiques du numéro de facture spécifié.

## <a name="syntax"></a>Syntaxe

```
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a>Arguments

`invoice number digits` : *Chaîne*

Valeur de texte qui représente les chiffres d'un numéro de facture.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d'utilisation

> [!NOTE] 
> Pour éliminer des symboles de l'alphabet qui ne sont pas conformes à la norme ISO, l'argument `invoice number digits` doit être traduit avant d'être transmis à cette fonction.

## <a name="example"></a>Exemple

`ISOCredRef ("VEND-200002")` renvoie **« RF23VEND-200002 »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d'affaires)](er-functions-category-other.md)
