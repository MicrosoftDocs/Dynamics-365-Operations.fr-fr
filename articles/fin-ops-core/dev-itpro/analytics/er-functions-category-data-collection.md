---
title: Liste des fonctions ER dans la catégorie de collecte de données
description: Cet article fournit des informations sur les fonctions de collecte de données prises en charge dans les États électroniques (ER).
author: kfend
ms.date: 12/04/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: e01bed49646ffe344004f9eb51e9013e1b4c5430
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286147"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a>Liste des fonctions ER dans la catégorie de collecte de données

[!include [banner](../includes/banner.md)]

Les fonctions de collecte de données d’états électroniques (ER) sont utilisées pour effectuer le comptage et la calcul de la somme dans un format ER en cours d’exécution, sur la base des données de la sortie déjà générées dans le format **Texte** ou **Xml**. Cette approche est utilisée pour améliorer les performances d’un format ER exécuté, pour saisir les valeurs des totaux cumulés dans les documents générés et à d’autres fins. Cet article fournit un résumé de ces fonctions.

## <a name="list-of-supported-functions"></a>Liste des fonctions prises en charge

| Fonction | Description |
|----------|-------------|
| [CollectedList](er-functions-datacollection-collectedlist.md) | Cette fonction renvoie une valeur de *Liste des enregistrements* qui contient la liste des valeurs qui ont été renvoyées par la propriété **Valeur de clé de données collectées** des éléments de format et collectée lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l’exécution du format, et qui remplissent les conditions spécifiées. Chaque condition se compose d’une plage de clés et d’une valeur de clé. |
| [CountIF](er-functions-datacollection-countif.md) | Cette fonction renvoie une valeur *Entier* qui représente le nombre d’éléments de format collectés lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l’exécution du format, et qui remplit la condition spécifiée. La condition se compose d’une plage de clés et d’une valeur de clé. |
| [CountIFs](er-functions-datacollection-countifs.md) | Cette fonction renvoie une valeur *Entier* qui représente le nombre d’éléments de format collectés lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l’exécution du format, et qui remplit les conditions spécifiées. Chaque condition se compose d’une plage de clés et d’une valeur de clé. |
| [FormatElementName](er-functions-datacollection-formatelementname.md) | Cette fonction renvoie une valeur de *Chaîne* qui représente le nom de l’élément du format ER actuel. |
| [SumIF](er-functions-datacollection-sumif.md) | Cette fonction renvoie une valeur *Réel* qui représente la somme des valeurs renvoyées par les liaisons d’éléments de format et collectées lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l’exécution du format, et qui remplit la condition spécifiée. La condition se compose d’une plage de clés et d’une valeur de clé. |
| [SumIFs](er-functions-datacollection-sumifs.md) | Cette fonction renvoie une valeur *Réel* qui représente la somme des valeurs renvoyées par les liaisons d’éléments de format et collectées lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l’exécution du format, et qui remplit les conditions spécifiées. Chaque condition se compose d’une plage de clés et d’une valeur de clé. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des États électroniques](general-electronic-reporting.md)

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Langage de formule dans la gestion des états électroniques](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
