---
title: Fonction FILTER ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction FILTER États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: d281fe710381b0ecb075a0d9281d46bd6edf987d
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745295"
---
# <a name="filter-er-function"></a>Fonction FILTER ER

[!include [banner](../includes/banner.md)]

La fonction `FILTER` renvoie la liste spécifiée sous la forme d’une valeur de *Liste des enregistrements* après que la requête a été modifiée afin qu’elle filtre pour la condition spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
FILTER (list, condition)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

`condition` : *Booléen*

Expression conditionnelle valide utilisée pour filtrer les enregistrements de la liste spécifiée.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Cette fonction diffère de la fonction [WHERE](er-functions-list-where.md), car la condition spécifiée est appliquée à toute source de données États électroniques (ER) du type *Enregistrements de table* au niveau de la base de données. La liste et la condition peuvent être définies à l’aide de tables et de relations.

Si l’un ou les deux arguments configurés pour cette fonction (`list` et `condition`) ne permettent pas de traduire cette demande en appel SQL direct, une exception est levée au moment de la conception. Cette exception informe l’utilisateur que `list` ou `condition` ne peut pas être utilisé pour interroger la base de données.

## <a name="example-1"></a>Exemple 1

Si **Fournisseur** est configuré comme source de données ER qui fait référence à la table VendTable, l’expression `FILTER (Vendors, Vendors.VendGroup = "40")` renvoie la liste des fournisseurs faisant partie uniquement du groupe de fournisseurs 40.

## <a name="example-2"></a>Exemple 2

Si **Fournisseur** est configuré comme source de données ER qui fait référence à la table VendTable et si **parmVendorBankGroup** est configuré comme source de données ER qui renvoie une valeur du type de données *Chaîne*, `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` renvoie la liste des comptes fournisseurs appartenant uniquement à un groupe bancaire spécifique.

## <a name="example-3"></a>Exemple 3

Vous entrez une source de données **DS** du type *Champ calculé* et elle contient l’expression `SPLIT ("A,B,C", ",")`. Vous entrez ensuite une autre expression, `FILTER( DS, DS.Value = "B")`. Lorsque vous essayez d’enregistrer cette expression dans le concepteur de formule ER, l’exception suivante est levée : « Erreur de validation : l’expression de liste de la fonction FILTER n’est pas interrogeable. »

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)
