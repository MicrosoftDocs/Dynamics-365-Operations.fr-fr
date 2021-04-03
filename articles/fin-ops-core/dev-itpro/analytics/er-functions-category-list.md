---
title: Liste des fonctions ER dans la catégorie de liste
description: Cette rubrique fournit des informations sur les fonction de liste prises en charge dans les États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 04/01/2020
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
ms.openlocfilehash: b98ad6c2c7eb2881ede83b9bd2d02aac71efc4c9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561684"
---
# <a name="list-of-er-functions-in-the-list-category"></a>Liste des fonctions ER dans la catégorie de liste

[!include [banner](../includes/banner.md)]

Les fonctions de liste des états électroniques (ER) peuvent être utilisées pour extraire des informations et effectuer des opérations sur les sources de données des types de données *Liste d’enregistrements* et *Conteneur (enregistrement)*. Cette rubrique fournit un résumé de ces fonctions.

## <a name="list-of-supported-functions"></a>Liste des fonctions prises en charge

| Fonction | Description |
|----------|-------------|
| [AllItems](er-functions-list-allitems.md)                 | Cette fonction s’exécute en tant que sélection en mémoire. Elle renvoie une nouvelle valeur de *Liste des enregistrements* aplatie qui consiste en une liste d’enregistrements qui représente tous les éléments qui correspondent au chemin spécifié. |
| [AllItemsQuery](er-functions-list-allitemsquery.md)       | Cette fonction s’exécute en tant que requête SQL jointe. Elle renvoie une nouvelle valeur de *Liste des enregistrements* aplatie qui consiste en une liste d’enregistrements qui représente tous les éléments qui correspondent au chemin spécifié. |
| [Nombre](er-functions-list-count.md)                       | Cette fonction renvoie une valeur *Entier* qui représente le nombre d’enregistrements dans la liste spécifiée, si la liste n’est pas vide. Si la liste est vide, cette fonction renvoie **0** (zéro). |
| [EmptyList](er-functions-list-emptylist.md)               | Cette fonction renvoie une valeur de *Liste d’enregistrements* à l’aide de la liste spécifiée comme source pour la structure de liste.|
| [Enumerate](er-functions-list-enumerate.md)               | Cette fonction renvoie une nouvelle valeur *Liste des enregistrements* constituée d’enregistrements énumérés de la liste spécifiée. |
| [Filtrer](er-functions-list-filter.md)                     | Cette fonction renvoie la liste spécifiée sous la forme d’une valeur de *Liste des enregistrements* après que la requête a été modifiée afin qu’elle filtre pour la condition spécifiée. |
| [Premier](er-functions-list-first.md)                       | Cette fonction renvoie le premier enregistrement de la liste spécifiée sous la forme d’une valeur de *Conteneur (enregistrement)*, si cette liste n’est pas vide. Si la liste est vide, cette fonction lève une exception. |
| [FirstOrNull](er-functions-list-firstornull.md)           | Cette fonction renvoie le premier enregistrement de la liste spécifiée sous la forme d’une valeur de *Conteneur (enregistrement)*, si cet enregistrement n’est pas vide. Si l’enregistrement est vide, cette fonction renvoie une valeur de *Conteneur (enregistrement)* null. |
| [Index :](er-functions-list-index.md)                       | Cette fonction renvoie une valeur de *Conteneur (enregistrement)* sélectionnée à l’aide de l’index numérique spécifié dans la liste spécifiée. Si l’index est hors des limites des enregistrements dans la liste spécifiée, cette fonction lève une exception. |
| [IsEmpty](er-functions-list-isempty.md)                   | Cette fonction renvoie une valeur *Booléenne* de **TRUE** si la liste spécifiée ne contient aucun enregistrement. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**. |
| [Liste](er-functions-list-list.md)                         | Cette fonction renvoie une valeur *Liste des enregistrements* constituée d’une nouvelle liste créée à partir des arguments spécifiés.|
| [ListDistinct](er-functions-list-listdistinct.md)         | Cette fonction calcule l’expression spécifiée comme un sélecteur pour chaque enregistrement de la liste spécifiée. Elle renvoie une nouvelle valeur *Liste des enregistrements* qui contient un seul enregistrement pour chaque valeur de sélecteur unique.|
| [ListJoin](er-functions-list-listjoin.md)                 | Cette fonction renvoie une valeur *Liste des enregistrements* qui représente une nouvelle liste jointe créée à partir des arguments spécifiés.|
| [ListOfFields](er-functions-list-listoffields.md)         | Cette fonction renvoie une valeur *Liste des enregistrements* créée en fonction de la structure de l’argument spécifié du type *Énumération* ou *Conteneur (enregistrement)*. |
| [ListOfFirstItem](er-functions-list-listoffirstitem.md)   | Cette fonction renvoie une valeur *Liste des enregistrements* constituée uniquement du premier enregistrement de la liste spécifiée.|
| [OrderBy](er-functions-list-orderby.md)                   | Cette fonction renvoie la liste spécifiée sous la forme d’une *Liste des enregistrements* après avoir été triée selon les arguments spécifiés. Ces arguments peuvent être définis comme expressions. |
| [Contrepasser](er-functions-list-reverse.md)                   | Cette fonction renvoie la liste spécifiée en tant que valeur de *Liste des enregistrements* dans l’ordre de tri inversé. |
| [Fractionner](er-functions-list-split.md)                       | Cette fonction fractionne la chaîne d’entrée spécifiée en sous-chaînes et renvoie le résultat sous la forme d’une nouvelle valeur de *Liste des enregistrements*. |
| [SplitList](er-functions-list-splitlist.md)               | Cette fonction fractionne la liste spécifiée en sous-listes (ou lots), dont chacun contient le nombre d’enregistrements spécifié. Elle renvoie ensuite le résultat en tant que nouvelle valeur de *Liste des enregistrements* constituée des lots. |
| [SplitListByLimit](er-functions-list-splitlistbylimit.md) | Cette fonction fractionne la liste spécifiée en une nouvelle liste de sous-listes (lots). Le nombre d’enregistrements dans chaque lot est calculé dynamiquement. La fonction renvoie ensuite le résultat en tant que nouvelle valeur de *Liste des enregistrements* constituée des lots. |
| [StringJoin](er-functions-list-stringjoin.md)             | Cette fonction renvoie une valeur de *Chaîne* composée des valeurs concaténées du champ spécifié dans la liste spécifiée. Les valeurs peuvent être séparées par le séparateur spécifié. |
| [Port](er-functions-list-where.md)                       | Cette fonction renvoie la liste spécifiée sous la forme d’une *Liste des enregistrements* après avoir été filtrée selon la condition spécifiée. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des États électroniques](general-electronic-reporting.md)

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Langage de formule dans la gestion des états électroniques](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]