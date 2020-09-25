---
title: Fonction FORMATELEMENTNAME ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction FORMATELEMENTNAME États électroniques (ER).
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
ms.openlocfilehash: e8be55d9a90e841d64288b0c618c0012912ddbab
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745631"
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
