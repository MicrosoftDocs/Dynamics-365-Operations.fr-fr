---
title: Fonction VALUEIN ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction VALUEIN États électroniques (ER).
author: NickSelin
ms.date: 08/18/2020
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
ms.openlocfilehash: 909aef5e52817a67e400f3132cb5d6ecc8a18906
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751742"
---
# <a name="valuein-er-function"></a>Fonction VALUEIN ER

[!include [banner](../includes/banner.md)]

La fonction `VALUEIN` détermine si l’entrée spécifiée correspond à une valeur quelconque d’un article donné dans la liste spécifiée. Elle renvoie une *Booléenne* de **TRUE** si l’entrée spécifiée correspond au résultat de l’exécution de l’expression spécifiée pour au moins un enregistrement de la liste spécifiée. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.

## <a name="syntax"></a>Syntaxe

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a>Arguments

`input` : *Champ*

Chemin d’accès valide d’un élément d’une source de données du *Liste d’enregistrements*. La valeur de cet article est mise en correspondance.

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

`list item expression` : *Booléen*

Expression conditionnelle valide qui indique ou contient un champ unique de la liste spécifiée à utiliser pour la mise en correspondance.

## <a name="return-values"></a>Valeurs de retour

*Booléen*

Valeur *Booléenne* résultante.

## <a name="usage-notes"></a>Notes d’utilisation

En général la fonction `VALUEIN` est traduite en un ensemble de conditions **OR**. Si la liste des conditions **OR** est grande et la longueur totale maximale d’une instruction SQL peut être dépassée, pensez à utiliser la fonction [`VALUEINLARGE`](er-functions-logical-valueinlarge.md).

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

Dans certains cas, elle peut être convertie en une instruction SQL de base de données à l’aide de l’opérateur `EXISTS JOIN`.

## <a name="example-1"></a>Exemple 1

Dans votre modèle de mise en correspondance, vous définissez la source de données **Liste** de type *Champ calculé*. Cette source de données contient l’expression `SPLIT ("a,b,c", ",")`.

Lorsqu’une source de données est appelée, si elle a été configurée comme l’expression `VALUEIN ("B", List, List.Value)`, elle renvoie **TRUE**. Dans ce cas, la fonction `VALUEIN` est traduite en l’ensemble de conditions suivant : `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, où `("B" = "b")` est égal à **TRUE**.

Lorsqu’une source de données est appelée, si elle a été configurée comme l’expression `VALUEIN ("B", List, LEFT(List.Value, 0))`, elle renvoie **FALSE**. Dans ce cas, la fonction `VALUEIN` est traduite en l’ensemble de conditions suivant : `("B" = "")`, qui n’est pas égal à **TRUE**.

La limite supérieure du nombre de caractères dans le texte d’une telle condition est de 32 768 caractères. Par conséquent, vous ne devez pas créer de sources de données susceptibles de dépasser cette limite au moment de l’exécution. Si la limite est dépassée, l’application arrête de s’exécuter, et une exception est levée. Par exemple, cette situation peut se produire si la source de données est configurée comme `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, et les listes **List1** et **List2** contiennent un grand nombre d’enregistrements.

Dans certains cas, la fonction `VALUEIN` est traduite en une instruction de base de données à l’aide de l’opérateur `EXISTS JOIN`. Ce comportement se produit lorsque la fonction [`FILTER`](er-functions-list-filter.md) est utilisée et que les conditions suivantes sont remplies :

- L’option **DEMANDER UNE REQUÊTE** est désactivée pour la source de données de la fonction `VALUEIN` qui fait référence à la liste d’enregistrements. Aucune condition supplémentaire n’est appliquée à cette source de données au moment de l’exécution.
- Aucune expression imbriquée n’est configurée pour la source de données de la fonction `VALUEIN` qui fait référence à la liste d’enregistrements.
- Un élément de liste de la fonction `VALUEIN` fait référence à un champ, pas à une expression ou à une méthode de la source de données spécifiée.

Envisagez d’utiliser cette option au lieu de la fonction [`WHERE`](er-functions-list-where.md) comme décrit précédemment dans cet exemple.

## <a name="example-2"></a>Exemple 2

Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :

- Source de données **In** du type *Enregistrements de la table*. Cette source de données fait référence à la table Intrastat.
- Source de données **Port** du type *Enregistrements de la table*. Cette source de données fait référence à la table IntrastatPort.

Lorsqu’une source de données est appelée qui est configurée comme l’expression `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)`, l’instruction SQL suivante est générée pour retourner les enregistrements filtrés de la table Intrastat.

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

Pour les champs **dataAreaId**, l’instruction SQL finale est générée en utilisant l’opérateur `IN`.

## <a name="example-3"></a>Exemple 3

Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :

- Source de données **Le** du type *Champ calculé*. Cette source de données contient l’expression `SPLIT ("DEMF,GBSI,USMF", ",")`.
- Source de données **In** du type *Enregistrements de la table*. Cette source de données fait référence à la table Intrastat et l’option **Intersociétés** est activée pour cela.

Lorsqu’une source de données est appelée qui est configurée comme expression `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)`, l’instruction SQL finale contient la condition suivante.

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions logiques](er-functions-category-logical.md)

[Fonctions VALUEINLARGE](er-functions-logical-valueinlarge.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]