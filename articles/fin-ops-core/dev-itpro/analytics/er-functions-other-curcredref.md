---
title: Fonction CURCREDREF ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction CURCREDREF États électroniques (ER).
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
ms.openlocfilehash: 5633541b1c7e25a0cfb837c4679691506806421b
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917003"
---
# <a name="CURCREDREF">Fonction CURCREDREF ER</a>

[!include [banner](../includes/banner.md)]

La fonction `CURCREDREF` renvoie une valeur *Chaîne* qui représente une référence de créancier, sur la base des chiffres du numéro de facture spécifié.

## <a name="syntax"></a>Syntaxe

```
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a>Arguments

`invoice number digits` : *Chaîne*

Valeur de texte qui représente les chiffres d'un numéro de facture.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

`CURCredRef ("VEND-200002")` renvoie **« 2200002 »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d'affaires)](er-functions-category-other.md)
