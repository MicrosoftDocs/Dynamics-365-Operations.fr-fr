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
ms.openlocfilehash: be5e8e7625d0226c9eb59efd3217fce7b8eba086
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915692"
---
# <a name="GUIDVALUE">Fonction GUIDVALUE ER</a>

[!include [banner](../includes/banner.md)]

La fonction `GUIDVALUE` convertit l'entrée spécifiée du type *Chaîne* en un élément de données du type *GUID*.

## <a name="syntax"></a>Syntaxe

```
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
