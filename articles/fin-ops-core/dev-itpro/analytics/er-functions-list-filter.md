---
title: Fonction FILTER ER
description: Cet article fournit des informations sur l’utilisation de la fonction FILTER États électroniques (ER).
author: NickSelin
ms.date: 12/14/2021
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
ms.openlocfilehash: dfa4afdcfad8c1855a10e1fa37c36cc5b20682ef
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884515"
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

## <a name="usage-notes"></a><a name="usage-notes"></a>Notes d’utilisation

Cette fonction diffère de la fonction [WHERE](er-functions-list-where.md), car la condition spécifiée est appliquée à toute source de données États électroniques (ER) du type *Enregistrements de table* au niveau de la base de données. La liste et la condition peuvent être définies à l’aide de tables et de relations.

Si l’un ou les deux arguments configurés pour cette fonction (`list` et `condition`) ne permettent pas de traduire cette demande en appel SQL direct, une exception est levée au moment de la conception. Cette exception informe l’utilisateur que `list` ou `condition` ne peut pas être utilisé pour interroger la base de données.

> [!NOTE]
> La fonction `FILTER` se comporte différemment de la fonction `WHERE` lorsque la fonction [`VALUEIN`](er-functions-logical-valuein.md) est utilisée pour spécifier les critères de sélection.
> 
> - Si la fonction `VALUEIN` est utilisée dans le cadre de la fonction `WHERE`, et que le deuxième argument de `VALUEIN` fait référence à une source de données qui ne renvoie aucun enregistrement, la valeur *[False](er-formula-supported-data-types-primitive.md#boolean)* booléenne que `VALUEIN` retourne sont pris en compte. Par conséquent, l’expression `WHERE(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` ne renvoie aucun enregistrement de fournisseur si la source de données **VendGroups** ne renvoie aucun enregistrement de groupe de fournisseurs.
> - Si la fonction `VALUEIN` est utilisée dans le cadre de la fonction `FILTER`, et que le deuxième argument de `VALUEIN` fait référence à une source de données qui ne renvoie aucun enregistrement, la valeur *[False](er-formula-supported-data-types-primitive.md#boolean)* booléenne que `VALUEIN` retourne sont ignorés. Par conséquent, l’expression `FILTER(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` renvoie tous les enregistrement de fournisseur de la source de données **Fournisseurs**, même si la source de données **VendGroups** ne renvoie aucun enregistrement de groupe de fournisseurs.

## <a name="example-1"></a>Exemple 1

Si **Fournisseur** est configuré comme source de données ER qui fait référence à la table VendTable, l’expression `FILTER (Vendors, Vendors.VendGroup = "40")` renvoie la liste des fournisseurs faisant partie uniquement du groupe de fournisseurs 40.

## <a name="example-2"></a>Exemple 2

Si **Fournisseur** est configuré comme source de données ER qui fait référence à la table VendTable et si **parmVendorBankGroup** est configuré comme source de données ER qui renvoie une valeur du type de données *Chaîne*, `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` renvoie la liste des comptes fournisseurs appartenant uniquement à un groupe bancaire spécifique.

## <a name="example-3"></a>Exemple 3

Vous entrez une source de données **DS** du type *Champ calculé* et elle contient l’expression `SPLIT ("A,B,C", ",")`. Vous entrez ensuite une autre expression, `FILTER( DS, DS.Value = "B")`. Lorsque vous essayez d’enregistrer cette expression dans le concepteur de formule ER, l’exception suivante est levée : « Erreur de validation : l’expression de liste de la fonction FILTER n’est pas interrogeable. »

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
