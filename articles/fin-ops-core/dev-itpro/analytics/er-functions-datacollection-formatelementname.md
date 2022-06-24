---
title: Fonction FORMATELEMENTNAME ER
description: Cet article fournit des informations sur l’utilisation de la fonction FORMATELEMENTNAME États électroniques (ER).
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
ms.openlocfilehash: 0a733c3c70cede6395b3d7454d82ce4d999e7e9b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851978"
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