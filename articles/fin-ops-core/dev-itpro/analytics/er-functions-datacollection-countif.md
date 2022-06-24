---
title: Fonction COUNTIF ER
description: Cet article fournit des informations sur l’utilisation de la fonction COUNTIF États électroniques (ER).
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
ms.openlocfilehash: 60a17d6a5e089cc6006a5fb3493654963de1b392
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906856"
---
# <a name="countif-er-function"></a>Fonction COUNTIF ER

[!include [banner](../includes/banner.md)]

La fonction `COUNTIF` renvoie une valeur *Entier* qui représente le nombre d’éléments de format collectés lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l’exécution du format, et qui remplit la condition spécifiée. La condition se compose d’une plage de clés et d’une valeur de clé.

## <a name="syntax"></a>Syntaxe

```vb
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a>Arguments

`condition range` : *Chaîne*

Valeur retournée par l’expression configurée dans la propriété **Nom de clé de données collectées** d’un composant au format d’états électroniques (ER).

`condition value` : *Chaîne*

Valeur retournée par l’expression configurée dans la propriété **Valeur de clé de données collectées** d’un composant au format ER.

## <a name="return-values"></a>Valeurs de retour

*Entier*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Les propriétés **Nom de clé de données collectées** et **Valeur de clé de données collectées** peuvent être configurées pour le composant **Séquence** ou le composant **Élément XML** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.

Cette fonction renvoie une valeur de **0** (zéro) lorsque l’option **Collecter les détails sur les sorties** du composant **Commun\\Fichier** actuel est désactivé.

Dans l’argument `condition range`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.

Dans l’argument `condition value`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.

## <a name="example"></a>Exemple

Pour plus d’informations sur l’utilisation de cette fonction, consultez le guide de tâche [ER Utiliser les données de la sortie du format pour compter et additionner](tasks/er-format-counting-summing-1.md), qui fait partie du processus d’entreprise **Acquérir/Développer des composants de services/solutions informatiques**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de collecte des données](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]