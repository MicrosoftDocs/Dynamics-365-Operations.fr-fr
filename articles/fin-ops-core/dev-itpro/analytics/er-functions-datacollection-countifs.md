---
title: Fonction COUNTIFS ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction COUNTIFS États électroniques (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 23da226fe1ef95ad037c33a5b423968531557896e300c6223b36bc44b0a8a015
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734838"
---
# <a name="countifs-er-function"></a>Fonction COUNTIFS ER

[!include [banner](../includes/banner.md)]

La fonction `COUNTIFS` renvoie une valeur *Entier* qui représente le nombre d’éléments de format collectés lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l’exécution du format, et qui remplit les conditions spécifiées. Chaque condition se compose d’une plage de clés et d’une valeur de clé.

## <a name="syntax"></a>Syntaxe

```vb
COUNTIFS (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a>Arguments

`condition 1 range` : *Chaîne*

Valeur retournée par l’expression configurée dans la propriété **Nom de clé de données collectées** d’un composant au format d’états électroniques (ER). Cet argument est obligatoire.

`condition 1 value` : *Chaîne*

Valeur retournée par l’expression configurée dans la propriété **Valeur de clé de données collectées** d’un composant au format ER. Cet argument est obligatoire.

`condition N range` : *Chaîne*

Valeur retournée par l’expression configurée dans la propriété **Nom de clé de données collectées** d’un composant au format ER. Ces arguments supplémentaires sont facultatifs.

`condition N value` : *Chaîne*

Valeur retournée par l’expression configurée dans la propriété **Valeur de clé de données collectées** d’un composant au format ER. Ces arguments supplémentaires sont facultatifs.

## <a name="return-values"></a>Valeurs de retour

*Entier*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Les propriétés **Nom de clé de données collectées** et **Valeur de clé de données collectées** peuvent être configurées pour le composant **Séquence** ou le composant **Élément XML** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.

Cette fonction renvoie une valeur de **0** (zéro) lorsque l’option **Collecter les détails sur les sorties** du composant **Commun\\Fichier** actuel est désactivé.

Dans les arguments `condition range`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.

Dans les arguments `condition value`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.

## <a name="example"></a>Exemple

Pour plus d’informations sur l’utilisation de cette fonction, consultez le guide de tâche [ER Utiliser les données de la sortie du format pour compter et additionner](tasks/er-format-counting-summing-1.md), qui fait partie du processus d’entreprise **Acquérir/Développer des composants de services/solutions informatiques**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de collecte des données](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]