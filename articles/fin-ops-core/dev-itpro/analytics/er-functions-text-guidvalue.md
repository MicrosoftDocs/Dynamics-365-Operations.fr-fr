---
title: Fonction GUIDVALUE ER
description: Cet article fournit des informations sur l’utilisation de la fonction GUIDVALUE États électroniques (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: f3899d983f7c790ff2e3dc74dd91c44fc54e44d3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898738"
---
# <a name="guidvalue-er-function"></a>Fonction GUIDVALUE ER

[!include [banner](../includes/banner.md)]

La fonction `GUIDVALUE` convertit l’entrée spécifiée du type *Chaîne* en un élément de données du type *GUID*.

## <a name="syntax"></a>Syntaxe

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a>Arguments

`input` : *Chaîne*

Chemin d’accès valide d’une source de données du type *Chaîne*.

## <a name="return-values"></a>Valeurs de retour

*GUID*

Valeur de l’identificateur global unique (GUID) résultant.

## <a name="usage-notes"></a>Notes d’utilisation

Pour créer une conversion dans la direction opposée (c’est-à-dire, pour convertir l’entrée spécifiée du type de données *GUID* en un élément de données de type de données *Chaîne*), vous pouvez utiliser la fonction [TEXT](er-functions-text-text.md).

## <a name="example"></a>Exemple

Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :

- Source de données **myID** du type *Champ calculé* qui contient l’expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`
- Source de données **Users** de type *Enregistrements de la table* qui fait référence à la table UserInfo

Vous pouvez ensuite utiliser une expression telle que `FILTER (Users, Users.objectId = myID)` pour filtrer la table UserInfo selon le champ **objectId** du type de données *GUID*.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]