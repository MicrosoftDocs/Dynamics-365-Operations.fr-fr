---
title: Fonction GETCURRENTCOMPANY ER
description: Cet article fournit des informations sur l’utilisation de la fonction GETCURRENTCOMPANY États électroniques (ER).
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
ms.openlocfilehash: 06d552a0e8241d416fc49c4377b02f90fdf63d29
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872740"
---
# <a name="getcurrentcompany-er-function"></a>Fonction GETCURRENTCOMPANY ER

[!include [banner](../includes/banner.md)]

La fonction `GETCURRENTCOMPANY` renvoie une valeur de *Chaîne* qui représente le code de l’entité juridique (société) à laquelle un utilisateur est actuellement connecté.

## <a name="syntax"></a>Syntaxe

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

`GETCURRENTCOMPANY ()` renvoie **USMF** pour un utilisateur connecté à la société **Contoso Entertainment System USA**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]