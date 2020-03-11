---
title: Fonction GUIDVALUE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction GUIDVALUE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: a7b8c782aff488a433c40a49ab7f4fe2d0e944e4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041165"
---
# <a name="GUIDVALUE">Fonction GUIDVALUE ER</a>

[!include [banner](../includes/banner.md)]

La fonction `GUIDVALUE` convertit l'entrée spécifiée du type *Chaîne* en un élément de données du type *GUID*.

## <a name="syntax"></a>Syntaxe

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a>Arguments

`input` : *Chaîne*

Chemin d'accès valide d'une source de données du type *Chaîne*.

## <a name="return-values"></a>Valeurs de retour

*GUID*

Valeur de l'identificateur global unique (GUID) résultant.

## <a name="usage-notes"></a>Notes d'utilisation

Pour créer une conversion dans la direction opposée (c'est-à-dire, pour convertir l'entrée spécifiée du type de données *GUID* en un élément de données de type de données *Chaîne*), vous pouvez utiliser la fonction [TEXT](er-functions-text-text.md).

## <a name="example"></a>Exemple

Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :

- Source de données **myID** du type *Champ calculé* qui contient l'expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`
- Source de données **Users** de type *Enregistrements de la table* qui fait référence à la table UserInfo

Vous pouvez ensuite utiliser une expression telle que `FILTER (Users, Users.objectId = myID)` pour filtrer la table UserInfo selon le champ **objectId** du type de données *GUID*.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)
