---
title: Fonction REVERSE ER
description: Cet article fournit des informations sur l’utilisation de la fonction REVERSE États électroniques (ER).
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 360878319bfa29395ae5deabec2e25e52d9e0fdc
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284146"
---
# <a name="reverse-er-function"></a>Fonction REVERSE ER

[!include [banner](../includes/banner.md)]

La fonction `REVERSE` renvoie la liste spécifiée en tant que valeur de *Liste des enregistrements* dans l’ordre de tri inversé.

## <a name="syntax"></a>Syntaxe

```vb
REVERSE (list)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="example-1"></a>Exemple 1

Si vous entrez une source de données **DS** de type *Champ calculé*, et qu’elle contient l’expression `SPLIT ("C|B|A", "|")`, l’expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` renvoie la valeur de texte **« C »**.

## <a name="example-2"></a>Exemple 2

Si **Fournisseur** est configuré comme source de données d’états électroniques qui fait référence à la table VendTable, l’expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` renvoie une liste de fournisseurs qui est triée par nom dans l’ordre décroissant.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
