---
title: Liste des fonctions ER dans la catégorie de texte
description: Cette rubrique fournit des informations sur les fonction de texte prises en charge dans les États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: bd4dd7e9a3e1aa448adea5abd0c21b8133f34e3b
ms.sourcegitcommit: fb8ad8e2b142441a6530b364f3258bbcc0c724d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201087"
---
# <a name="list-of-er-functions-of-the-text-category"></a>Liste des fonctions ER dans la catégorie de texte

[!include [banner](../includes/banner.md)]

Les fonctions de texte des états électroniques (ER) peuvent être utilisées pour effectuer des opérations sur les sources de données du type de données *Chaîne*. Cette rubrique fournit un résumé de ces fonctions.

## <a name="list-of-supported-functions"></a>Liste des fonctions prises en charge

| Fonction | Description |
|----------|-------------|
| [Char](er-functions-text-char.md) | Cette fonction renvoie une valeur de *Chaîne* qui présente un seul caractère référencé par le numéro Unicode spécifié. |
| [Concaténer](er-functions-text-concatenate.md) | Cette fonction renvoie toutes les chaînes de texte spécifiées en tant que valeur de *Chaîne* après avoir été jointes en une seule chaîne. |
| [Format](er-functions-text-format.md) | Cette fonction renvoie à la chaîne spécifiée une valeur de *Chaîne* une fois qu'elle a été mise en forme en substituant toutes les occurrences de **%N** par le *N*ième argument. |
| [GetEnumValueByName](er-functions-text-getenumvaluebyname.md) | Cette fonction recherche une valeur *Enum* spécifique dans la source de données d'énumération spécifiée à l'aide du nom d'énumération spécifié en tant que valeur de *Chaîne*. Si la valeur *Enum*, la fonction la renvoie. |
| [GuidValue](er-functions-text-guidvalue.md) | Cette fonction convertit l'entrée spécifiée du type *Chaîne* en un élément de données du type *GUID*. |
| [JsonValue](er-functions-text-jsonvalue.md) | Cette fonction analyse les données au format JavaScript Object Notation (JSON) qui sont accessibles au chemin d'accès spécifié et extrait une valeur scalaire basée sur l'ID spécifié. Elle renvoie ensuite la valeur scalaire extraite sous forme de valeur de *Chaîne*. |
| [Gauche](er-functions-text-left.md) | Cette fonction renvoie une valeur de *Chaîne* qui présente le nombre de caractères spécifié à partir du début de la chaîne spécifiée. |
| [Len](er-functions-text-len.md) | Cette fonction renvoie une valeur *Entier* qui représente le nombre de caractères de la chaîne spécifiée. |
| [Lower](er-functions-text-lower.md) | Cette fonction renvoie la chaîne de texte spécifiée sous la forme *Chaîne* après avoir été convertie en lettres minuscules. |
| [Mid](er-functions-text-mid.md) | Cette fonction renvoie une valeur de *Chaîne* qui présente le nombre de caractères spécifié à partir de la chaîne spécifiée, à partir de la position donnée. |
| [NumberFormat](er-functions-text-numberformat.md) | Cette fonction renvoie une valeur de *Chaîne* qui présente le nombre spécifié dans le format spécifié et dans une culture éventuellement spécifiée. |
| [NumeralsToText](er-functions-text-numeralstotext.md) | Cette fonction renvoie le nombre spécifié sous la forme *Chaîne* après avoir été épelée (c'est-à-dire convertie en chaînes de texte) dans la langue spécifiée. |
| [PadLeft](er-functions-text-padleft.md) | Cette fonction renvoie une valeur de *Chaîne* de longueur spécifique, où le début de la chaîne spécifiée est entouré par une ou plusieurs instances des caractères spécifiés. |
| [QrCode](er-functions-text-qrcode.md) | Cette fonction renvoie une valeur de *Conteneur* qui présente l'une image de code à réponse rapide (code QR) de la chaîne spécifiée au format binaire. |
| [Remplacer](er-functions-text-replace.md) | Cette fonction renvoie la chaîne de texte spécifiée sous la forme d'une valeur de *Chaîne* après que tout ou partie de celui-ci a été remplacé par une autre chaîne. |
| [Droite](er-functions-text-right.md) | Cette fonction renvoie une valeur de *Chaîne* qui présente le nombre de caractères spécifié à partir de la fin de la chaîne spécifiée. |
| [Détails](er-functions-text-text.md) | Cette fonction renvoie le nombre spécifié comme valeur de *Chaîne* une fois qu'elle a été convertie en une chaîne de texte qui est mise en forme en fonction des paramètres régionaux du serveur de l'instance d'application actuelle. |
| [Traduire](er-functions-text-translate.md) | Cette fonction renvoie une valeur *Chaîne* qui contient le résultat du remplacement du texte spécifié en caractères pour un autre jeu de caractères fourni. |
| [Trim](er-functions-text-trim.md) | Cette fonction renvoie la chaîne de texte spécifiée en tant que valeur de *Chaîne* une fois que les espaces de début et de fin ont été tronqués, et une fois que plusieurs espaces entre les mots ont été supprimés. |
| [Upper](er-functions-text-upper.md) | Cette fonction renvoie la chaîne de texte spécifiée sous la forme *Chaîne* après avoir été convertie en lettres majuscules. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des États électroniques](general-electronic-reporting.md)

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Langage de formule dans la gestion des états électroniques](er-formula-language.md)
