---
title: Fonction REVERSE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction REVERSE États électroniques (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 746a736c8797c1c1c5bd71d7d803be4212984595
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755202"
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