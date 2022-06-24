---
title: Fonction ENUMERATE ER
description: Cet article fournit des informations sur l’utilisation de la fonction ENUMERATE États électroniques (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 2ba0ab6ed3c1625904665d87f56745d9810ac782
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891841"
---
# <a name="enumerate-er-function"></a>Fonction ENUMERATE ER

[!include [banner](../includes/banner.md)]

La fonction `ENUMERATE` renvoie une nouvelle valeur *Liste des enregistrements* constituée d’enregistrements énumérés de la liste spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
ENUMERATE (list)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La liste des enregistrements énumérés qui est renvoyée expose les éléments supplémentaires suivants :

- L’enregistrement de champs (composant **Valeur**)
- L’index des enregistrements actuels (composant **Numéro**)

## <a name="example"></a>Exemple

Dans l’illustration suivante, une source de données **Énumérée** est créée sous la forme d’une liste énumérée des enregistrements fournisseurs de la source de données **Fournisseurs** qui fait référence à la table VendTable.

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

L’illustration suivante présente le format des états électroniques (ER). Dans ce format, des liaisons de données sont créées pour générer la sortie au format XML. Cette sortie répertorie des fournisseurs individuels comme nœuds énumérés.

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

L’illustration suivante présente le résultat de l’exécution du format conçu.

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]