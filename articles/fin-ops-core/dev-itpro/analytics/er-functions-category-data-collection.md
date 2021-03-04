---
title: Liste des fonctions ER dans la catégorie de collecte de données
description: Cette rubrique fournit des informations sur les fonctions de collecte de données prises en charge dans les États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 0ec6092f2992df91433bb8aaa4212fca2a0abf7c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686291"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a>Liste des fonctions ER dans la catégorie de collecte de données

[!include [banner](../includes/banner.md)]

Les fonctions de collecte de données d’états électroniques (ER) sont utilisées pour effectuer le comptage et la calcul de la somme dans un format ER en cours d’exécution, sur la base des données de la sortie déjà générées dans le format **Texte** ou **Xml**. Cette approche est utilisée pour améliorer les performances d’un format ER exécuté, pour saisir les valeurs des totaux cumulés dans les documents générés et à d’autres fins. Cette rubrique fournit un résumé de ces fonctions.

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