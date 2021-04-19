---
title: Fonction ORDERBY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ORDERBY États électroniques (ER).
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
ms.openlocfilehash: 51da7f3766f5af901c8be6668bc2511cd8e2f9e9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753190"
---
# <a name="orderby-er-function"></a>Fonction ORDERBY ER

[!include [banner](../includes/banner.md)]

La fonction `ORDERBY` renvoie la liste spécifiée sous la forme d’une *Liste des enregistrements* après avoir été triée selon les arguments spécifiés. Ces arguments peuvent être définis comme expressions.

## <a name="syntax"></a>Syntaxe

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a>Arguments

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

`expression 1` : *Champ*

Chemin valide d’un champ de la source de données référencé par l’argument `list` de la fonction appelée. Le champ référencé doit être un champ du type de données primitif. Cet argument est obligatoire.

`expression N` : *Champ*

Chemin valide d’un champ de la source de données référencé par l’argument `list` de la fonction appelée. Le champ référencé doit être un champ du type de données primitif. Ces arguments supplémentaires sont facultatifs.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="example-1"></a>Exemple 1

Si vous entrez une source de données **DS** de type *Champ calculé*, et qu’elle contient l’expression `SPLIT ("C|B|A", "|")`, l’expression `FIRST( ORDERBY( DS, DS. Value)).Value` renvoie la valeur de texte **« A »**.

## <a name="example-2"></a>Exemple 2

Si **Fournisseur** est configuré comme source de données d’états électroniques qui fait référence à la table VendTable, l’expression `ORDERBY (Vendors, Vendors.'name()')` renvoie une liste de fournisseurs qui est triée par nom dans l’ordre croissant.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]