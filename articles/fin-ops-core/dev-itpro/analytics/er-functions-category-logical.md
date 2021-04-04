---
title: Liste des fonctions ER dans la catégorie logique
description: Cette rubrique fournit des informations sur les fonctions logiques prises en charge dans les États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 02/11/2021
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
ms.openlocfilehash: 7310c2b269c3f4be03102160aebe0ed164a23a5c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561660"
---
# <a name="list-of-er-functions-in-the-logical-category"></a>Liste des fonctions ER dans la catégorie logique

[!include [banner](../includes/banner.md)]

Les fonctions logiques d’états électronique (ER) peuvent être utilisées pour utiliser des valeurs logiques afin d’effectuer plusieurs comparaisons en une seule expression ou de tester plusieurs conditions. Cette rubrique fournit un résumé de ces fonctions.

## <a name="list-of-supported-functions"></a>Liste des fonctions prises en charge

| Fonction | Description |
|----------|-------------|
| [Et](er-functions-logical-and.md)                       | Cette fonction renvoie une valeur *Booléenne* de **TRUE** si toutes les conditions spécifiées sont true. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**. |
| [Dossier](er-functions-logical-case.md)                     | Cette fonction évalue la valeur de l’expression spécifiée par rapport aux options alternatives spécifiées et renvoie le résultat de la première option qui est égale à la valeur de l’expression spécifiée. Sinon, elle renvoie un résultat par défaut facultatif, si un résultat par défaut est spécifié comme dernier argument de la fonction appelée qui n’est pas précédé d’une option. La valeur renvoyée peut être une valeur de n’importe quel type de données pris en charge. |
| [Contient](er-functions-logical-contains.md)             | Cette fonction détermine si l’entrée spécifiée contient le texte spécifié. Elle renvoie une valeur *Booléenne* **TRUE** si l’entrée spécifiée ne contient pas le texte spécifié. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**. |
| [EndsWith](er-functions-logical-endswith.md)             | Cette fonction détermine si l’entrée spécifiée se termine par le texte spécifié. Elle renvoie une valeur *Booléenne* **TRUE** si l’entrée spécifiée se termine par le texte spécifié. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**. |
| [Si](er-functions-logical-if.md)                         | Cette fonction renvoie la première valeur spécifiée si la condition spécifiée est remplie. Sinon, elle renvoie la deuxième valeur spécifiée. La valeur renvoyée peut être une valeur de n’importe quel type de données pris en charge. |
| [Non](er-functions-logical-not.md)                       | Cette fonction renvoie la valeur logique inversée de la condition spécifiée en tant que valeur *Booléenne*. |
| [Or](er-functions-logical-or.md)                         | Cette fonction renvoie une valeur *Booléenne* de **FALSE** si toutes les conditions spécifiées sont false. Si toutes les conditions spécifiées sont true, la fonction renvoie une valeur *Booléenne* de **TRUE**. |
| [StartsWith](er-functions-logical-startswith.md)         | Cette fonction détermine si l’entrée spécifiée commence par le texte spécifié. Elle renvoie une valeur *Booléenne* **TRUE** si l’entrée spécifiée commence par le texte spécifié. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**. |
| [ValueIn](er-functions-logical-valuein.md)               | Cette fonction détermine si l’entrée spécifiée correspond à une valeur quelconque d’un article donné dans la liste spécifiée. Elle renvoie une *Booléenne* de **TRUE** si l’entrée spécifiée correspond au résultat de l’exécution de l’expression spécifiée pour au moins un enregistrement de la liste spécifiée. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**. |
| [ValueInLarge](er-functions-logical-valueinlarge.md)     | Cette fonction détermine si l’entrée spécifiée de type *Int64* ou *Entier* correspond à une valeur quelconque d’un article donné dans la liste spécifiée. Elle renvoie une *Booléenne* de **TRUE** si l’entrée spécifiée correspond au résultat de l’exécution de l’expression spécifiée pour au moins un enregistrement de la liste spécifiée. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**. |


## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des États électroniques](general-electronic-reporting.md)

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Langage de formule dans la gestion des états électroniques](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]