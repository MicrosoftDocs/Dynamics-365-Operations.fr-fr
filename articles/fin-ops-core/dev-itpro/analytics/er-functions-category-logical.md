---
title: Liste des fonctions ER dans la catégorie logique
description: Cette rubrique fournit des informations sur les fonctions logiques prises en charge dans les États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 08/19/2020
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
ms.openlocfilehash: e622778c60646e5cc84cd6e23a5d4954a0fe0bb3
ms.sourcegitcommit: 38ad6f791c3d5688a5dc201a234ba89f155f7f03
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2020
ms.locfileid: "3705093"
---
# <a name="list-of-er-functions-in-the-logical-category"></a>Liste des fonctions ER dans la catégorie logique

[!include [banner](../includes/banner.md)]

Les fonctions logiques d’états électronique (ER) peuvent être utilisées pour utiliser des valeurs logiques afin d’effectuer plusieurs comparaisons en une seule expression ou de tester plusieurs conditions. Cette rubrique fournit un résumé de ces fonctions.

## <a name="list-of-supported-functions"></a>Liste des fonctions prises en charge

| Fonction | Description |
|----------|-------------|
| [Et](er-functions-logical-and.md)                       | Cette fonction renvoie une valeur *Booléenne* de **TRUE** si toutes les conditions spécifiées sont true. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**. |
| [Dossier](er-functions-logical-case.md)                     | Cette fonction évalue la valeur de l’expression spécifiée par rapport aux options alternatives spécifiées et renvoie le résultat de la première option qui est égale à la valeur de l’expression spécifiée. Sinon, elle renvoie un résultat par défaut facultatif, si un résultat par défaut est spécifié comme dernier argument de la fonction appelée qui n’est pas précédé d’une option. La valeur renvoyée peut être une valeur de n’importe quel type de données pris en charge. |
| [Si](er-functions-logical-if.md)                         | Cette fonction renvoie la première valeur spécifiée si la condition spécifiée est remplie. Sinon, elle renvoie la deuxième valeur spécifiée. La valeur renvoyée peut être une valeur de n’importe quel type de données pris en charge. |
| [Non](er-functions-logical-not.md)                       | Cette fonction renvoie la valeur logique inversée de la condition spécifiée en tant que valeur *Booléenne*. |
| [Or](er-functions-logical-or.md)                         | Cette fonction renvoie une valeur *Booléenne* de **FALSE** si toutes les conditions spécifiées sont false. Si toutes les conditions spécifiées sont true, la fonction renvoie une valeur *Booléenne* de **TRUE**. |
| [ValueIn](er-functions-logical-valuein.md)               | Cette fonction détermine si l’entrée spécifiée correspond à une valeur quelconque d’un article donné dans la liste spécifiée. Elle renvoie une *Booléenne* de **TRUE** si l’entrée spécifiée correspond au résultat de l’exécution de l’expression spécifiée pour au moins un enregistrement de la liste spécifiée. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**. |
| [ValueInLarge](er-functions-logical-valueinlarge.md)     | Cette fonction détermine si l’entrée spécifiée de type *Int64* ou *Entier* correspond à une valeur quelconque d’un article donné dans la liste spécifiée. Elle renvoie une *Booléenne* de **TRUE** si l’entrée spécifiée correspond au résultat de l’exécution de l’expression spécifiée pour au moins un enregistrement de la liste spécifiée. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**. |


## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des États électroniques](general-electronic-reporting.md)

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Langage de formule dans la gestion des états électroniques](er-formula-language.md)
