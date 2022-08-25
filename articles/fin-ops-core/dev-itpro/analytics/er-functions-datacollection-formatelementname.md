---
title: Fonction FORMATELEMENTNAME ER
description: Cet article fournit des informations sur l’utilisation de la fonction FORMATELEMENTNAME États électroniques (ER).
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 1c8c319075f8f39bec963df2c88d2d8d3beace43
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275423"
---
# <a name="formatelementname-er-function"></a>Fonction FORMATELEMENTNAME ER

[!include [banner](../includes/banner.md)]

La fonction `FORMATELEMENTNAME` renvoie une valeur de *Chaîne* qui représente le nom de l’élément du format des états électroniques (ER) actuel.

## <a name="syntax"></a>Syntaxe

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Cette fonction peut être appelée dans des expressions ER configurées pour les propriétés **Nom de clé de données collectées** et **Valeur de clé de données collectées** d’un composant de format ER à partir du groupe **Texte** qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.

## <a name="example"></a>Exemple

Pour plus d’informations sur l’utilisation de cette fonction, consultez le guide de tâche [ER Utiliser les données de la sortie du format pour compter et additionner](tasks/er-format-counting-summing-1.md), qui fait partie du processus d’entreprise **Acquérir/Développer des composants de services/solutions informatiques**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de collecte des données](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
