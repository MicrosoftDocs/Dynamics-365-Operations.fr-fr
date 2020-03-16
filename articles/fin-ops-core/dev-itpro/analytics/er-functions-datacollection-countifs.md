---
title: Fonction COUNTIFS ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction COUNTIFS États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 9627c7835c8f3f1b6aedc1f691470dc29a11d6b5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042548"
---
# <a name="COUNTIFS">Fonction COUNTIFS ER</a>

[!include [banner](../includes/banner.md)]

La fonction `COUNTIFS` renvoie une valeur *Entier* qui représente le nombre d'éléments de format collectés lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l'exécution du format, et qui remplit les conditions spécifiées. Chaque condition se compose d'une plage de clés et d'une valeur de clé.

## <a name="syntax"></a>Syntaxe

```vb
COUNTIFS (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a>Arguments

`condition 1 range` : *Chaîne*

Valeur retournée par l'expression configurée dans la propriété **Nom de clé de données collectées** d'un composant au format d'états électroniques (ER). Cet argument est obligatoire.

`condition 1 value` : *Chaîne*

Valeur retournée par l'expression configurée dans la propriété **Valeur de clé de données collectées** d'un composant au format ER. Cet argument est obligatoire.

`condition N range` : *Chaîne*

Valeur retournée par l'expression configurée dans la propriété **Nom de clé de données collectées** d'un composant au format ER. Ces arguments supplémentaires sont facultatifs.

`condition N value` : *Chaîne*

Valeur retournée par l'expression configurée dans la propriété **Valeur de clé de données collectées** d'un composant au format ER. Ces arguments supplémentaires sont facultatifs.

## <a name="return-values"></a>Valeurs de retour

*Entier*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d'utilisation

Les propriétés **Nom de clé de données collectées** et **Valeur de clé de données collectées** peuvent être configurées pour le composant **Séquence** ou le composant **Élément XML** d'un composant de format ER qui réside sous le composant **Commun\\Fichier** où l'option **Collecter les détails de sortie** est activée.

Cette fonction renvoie une valeur de **0** (zéro) lorsque l'option **Collecter les détails sur les sorties** du composant **Commun\\Fichier** actuel est désactivé.

Dans les arguments `condition range`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.

Dans les arguments `condition value`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.

## <a name="example"></a>Exemple

Pour plus d'informations sur l'utilisation de cette fonction, consultez le guide de tâche [ER Utiliser les données de la sortie du format pour compter et additionner](tasks/er-format-counting-summing-1.md), qui fait partie du processus d'entreprise **Acquérir/Développer des composants de services/solutions informatiques**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de collecte des données](er-functions-category-data-collection.md)
