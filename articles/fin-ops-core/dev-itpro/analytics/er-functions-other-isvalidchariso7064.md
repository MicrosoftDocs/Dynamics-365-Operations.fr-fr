---
title: Fonction ISVALIDCHARACTERISO7064 ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ISVALIDCHARACTERISO7064 États électroniques (ER).
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
ms.openlocfilehash: 26300adce5f9a8a567510885577c6cfb9b1c859a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563364"
---
# <a name="isvalidcharacteriso7064-er-function"></a>Fonction ISVALIDCHARACTERISO7064 ER

[!include [banner](../includes/banner.md)]

La fonction `ISVALIDCHARACTERISO7064` renvoie une valeur *Booléenne* de **TRUE** si la chaîne donnée représente un numéro de compte bancaire international (IBAN) valide. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.

## <a name="syntax"></a>Syntaxe

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur de texte qui représente un IBAN.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` renvoie **TRUE**. 

`ISVALIDCHARACTERISO7064 ("AT61")` renvoie **FALSE**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]