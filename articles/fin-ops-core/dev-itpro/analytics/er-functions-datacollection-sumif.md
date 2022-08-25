---
title: Fonction SUMIF ER
description: Cet article fournit des informations sur l’utilisation de la fonction SUMIF États électroniques (ER).
author: kfend
ms.date: 04/27/2020
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
ms.openlocfilehash: 66f8f60714f403c9e4ce5c798f08d9566a3e334d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285333"
---
# <a name="sumif-er-function"></a>Fonction SUMIF ER

[!include [banner](../includes/banner.md)]

La fonction `SUMIF` renvoie une valeur *Réel* qui représente la somme des valeurs renvoyées par les liaisons d’éléments de format et collectées lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l’exécution du format, et qui remplit la condition spécifiée. La condition se compose d’une plage de clés et d’une valeur de clé.

## <a name="syntax"></a>Syntaxe

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a>Arguments

`key name for summing` : *Chaîne*

Valeur retournée par l’expression configurée dans la propriété **Nom de clé de données collectées** du composant de format d’états électroniques (ER) pour lequel la valeur de la liaison doit être utilisée à des fins de calcul de somme.

La propriété **Valeur de clé de données collectées** peut être configurée pour un composant **Séquence** ou un composant **Élément XML** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.

## <a name="return-values"></a>Valeurs de retour

*Réel*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Cette fonction renvoie une valeur de **0** (zéro) lorsque l’option **Collecter les détails sur les sorties** du composant **Commun\\Fichier** actuel est désactivé.

Dans l’argument `condition range`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.

Dans l’argument `condition value`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.

## <a name="example"></a>Exemple

Pour plus d’informations sur l’utilisation de cette fonction, consultez le guide de tâche [ER Utiliser les données de la sortie du format pour compter et additionner](tasks/er-format-counting-summing-1.md), qui fait partie du processus d’entreprise **Acquérir/Développer des composants de services/solutions informatiques**.

Pour plus d’informations et d’exemples sur l’utilisation de cette fonction, consultez [Différer l’exécution des éléments de séquence aux formats ER ](er-defer-sequence-element.md#Example) et [Différer l’exécution des éléments XML aux formats ER](er-defer-xml-element.md#Example).

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de collecte des données](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
