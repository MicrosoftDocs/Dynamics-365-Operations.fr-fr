---
title: Fonction SUMIFS ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction SUMIFS États électroniques (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: a3adfe62d9fd7bdc23784cf7311f65a4d2e88960
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747081"
---
# <a name="sumifs-er-function"></a>Fonction SUMIFS ER

[!include [banner](../includes/banner.md)]

La fonction `SUMIFS` renvoie une valeur *Réel* qui représente la somme des valeurs renvoyées par les liaisons d’éléments de format et collectées lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l’exécution du format, et qui remplit les conditions spécifiées. Chaque condition se compose d’une plage de clés et d’une valeur de clé.

## <a name="syntax"></a>Syntaxe

```vb
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a>Arguments

`key name for summing` : *Chaîne*

Valeur retournée par l’expression configurée dans la propriété **Nom de clé de données collectées** du composant de format d’états électroniques (ER) pour lequel la valeur de la liaison doit être utilisée à des fins de calcul de somme.

La propriété **Nom de clé de données collectées** peut être configurée pour un composant **Numérique** ou un composant **Chaîne** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.

`condition 1 range` : *Chaîne*

Valeur retournée par l’expression configurée dans la propriété **Nom de clé de données collectées** d’un composant au format ER. Cet argument est obligatoire.

La propriété **Nom de clé de données collectées** peut être configurée pour un composant **Séquence** ou un composant **Élément XML** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.

`condition 1 value` : *Chaîne*

Valeur retournée par l’expression configurée dans la propriété **Valeur de clé de données collectées** d’un composant au format ER. Cet argument est obligatoire.

La propriété **Valeur de clé de données collectées** peut être configurée pour un composant **Séquence** ou un composant **Élément XML** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.

`condition N range` : *Chaîne*

Valeur retournée par l’expression configurée dans la propriété **Nom de clé de données collectées** d’un composant au format ER. Ces arguments supplémentaires sont facultatifs.

La propriété **Nom de clé de données collectées** peut être configurée pour un composant **Séquence** ou un composant **Élément XML** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.

`condition N value` : *Chaîne*

Valeur retournée par l’expression configurée dans la propriété **Valeur de clé de données collectées** d’un composant au format ER. Ces arguments supplémentaires sont facultatifs.

La propriété **Valeur de clé de données collectées** peut être configurée pour un composant **Séquence** ou un composant **Élément XML** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.

## <a name="return-values"></a>Valeurs de retour

*Réel*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Cette fonction renvoie une valeur de **0** (zéro) lorsque l’option **Collecter les détails sur les sorties** du composant **Commun\\Fichier** actuel est désactivé.

Dans les arguments `condition range`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.

Dans les arguments `condition value`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.

## <a name="example"></a>Exemple

Pour plus d’informations sur l’utilisation de cette fonction, consultez le guide de tâche [ER Utiliser les données de la sortie du format pour compter et additionner](tasks/er-format-counting-summing-1.md), qui fait partie du processus d’entreprise **Acquérir/Développer des composants de services/solutions informatiques**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de collecte des données](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]