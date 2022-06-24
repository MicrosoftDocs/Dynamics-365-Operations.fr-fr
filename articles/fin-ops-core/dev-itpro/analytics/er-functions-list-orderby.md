---
title: Fonction ORDERBY ER
description: Cet article fournit des informations sur l’utilisation de la fonction ORDERBY États électroniques (ER).
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
ms.openlocfilehash: 1a922405ea23d2b1ff5ac062785e68626edbc8f0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883757"
---
# <a name="orderby-er-function"></a>Fonction ORDERBY ER

[!include [banner](../includes/banner.md)]

La fonction `ORDERBY` renvoie la liste spécifiée sous la forme d’une *Liste des enregistrements* après avoir été triée selon les arguments spécifiés. Ces arguments peuvent être définis comme expressions.

## <a name="syntax-1"></a><a name="syntax-1"></a>Syntaxe 1

```vb
ORDERBY (list, expression 1[, expression 2, …, expression N])
```

## <a name="syntax-2"></a><a name="syntax-2"></a>Syntaxe 2

```vb
ORDERBY (location, list, expression 1[, expression 2, …, expression N])
```

> [!NOTE]
> Cette syntaxe est prise en charge pour Microsoft Dynamics 365 Finance version 10.0.25 et ultérieures.

## <a name="arguments"></a>Arguments

`location` : *[Chaine](er-formula-supported-data-types-primitive.md#string)*

L’emplacement où le tri doit être exécuté. Les options suivantes sont valides :

- « Requête »
- « InMemory »

`list` : *[Liste d’enregistrements](er-formula-supported-data-types-composite.md#record-list)*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

`expression 1` : *Champ*

Chemin valide d’un champ de la source de données référencé par l’argument `list` de la fonction appelée. Le champ référencé doit être un champ du type de données primitif. Cet argument est obligatoire.

`expression N` : *Champ*

Chemin valide d’un champ de la source de données référencé par l’argument `list` de la fonction appelée. Le champ référencé doit être un champ du type de données primitif. Ces arguments supplémentaires sont facultatifs.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d’utilisation

### <a name="syntax-1"></a>Syntaxe 1

Le tri des données se fait toujours dans la mémoire du serveur d’application. Pour plus d’informations, voir [exemple 1](#example-1).

### <a name="syntax-2"></a>Syntaxe 2

### <a name="sorting-in-memory"></a>Tri en mémoire

Quand l’argument `location` est spécifié comme **InMemory**, le tri des données est effectué dans la mémoire d’un serveur d’application. Pour plus d’informations, voir [exemple 2](#example-2).

### <a name="sorting-in-database"></a>Tri dans la base de données

Quand l’argument `location` est spécifié comme **Requete**, le tri des données est effectué au niveau de la base de données. Dans ce cas, l’argument `list` doit pointer vers l’une des sources de données [Gestion des états électroniques](general-electronic-reporting.md) suivantes qui spécifie la source d’application pour laquelle une requête directe de base de données peut être établie :

- Source de données du type *Enregistrements de la table*
- Relation d’une source de données du type *Enregistrements de la table*
- Source de données du type *Champ de calcul*

Les arguments `expression 1` et `expression N` doivent pointer vers les champs d’une source de données Gestion des états électronique qui spécifie les champs pertinents de la source d’application pour laquelle une requête directe de base de données peut être également établie.

Si une requête de base de données directe ne peut pas être établie, une [erreur](er-components-inspections.md#i18) de validation se produit dans le concepteur de modèle de mappage de gestion des états électroniques. Le message que vous recevez indique que l’expression ER qui inclut la fonction `ORDERBY` ne peut pas être exécutée au moment de l’exécution.

Pour de meilleures performances, nous vous recommandons d’utiliser l’option **Requete** lorsque le tri est configuré pour les sources de données d’application susceptibles de contenir un grand nombre d’enregistrements (par exemple, pour les tables d’application transactionnelles).

> [!NOTE]
> La fonction `ORDEBY` elle-même ne peut pas être traduite en une requête directe de base de données. Par conséquent, une source de données de gestion des états électroniques qui contient cette fonction n’est pas interrogeable. Elle ne peut pas non plus être utilisée dans le cadre de fonctions de gestion des états électroniques telles que [FILTER](er-functions-list-filter.md) et [ALLITEMSQUERY](er-functions-list-allitemsquery.md), où seules les sources de données interrogeables peuvent être utilisées.

Pour plus de détails, voir [exemple 3](#example-3) et [exemple 4](#example-4).

### <a name="comparability"></a>Comparabilité

Puisque le moteur de base de données SQL et le serveur d’applications Finance peuvent utiliser une valeur de classement différente pour un seul caractère, le résultat du tri de la même liste d’enregistrements peut différer lorsqu’un champ [Chaîne](er-formula-supported-data-types-primitive.md#string) est utilisé pour le tri. Pour plus d’informations, voir [exemple 5](#example-5).

## <a name="example-1-in-memory-default-execution"></a><a name="example-1"></a>Exemple 1 : exécution par défaut en mémoire

Si vous entrez une source de données **DS** de type *Champ calculé*, et qu’elle contient l’expression `SPLIT ("C|B|A", "|")`, l’expression `FIRST( ORDERBY( DS, DS. Value)).Value` renvoie la valeur de texte **« A »**.

## <a name="example-2-in-memory-explicit-execution"></a><a name="example-2"></a>Exemple 2 : exécution explicite en mémoire

Si **Fournisseur** est configuré comme source de données d’états électroniques de type *Enregistrements de table* qui fait référence à la table **VendTable**, l’expression `ORDERBY (Vendor, Vendor.'name()')` et l’expression `ORDERBY ("InMemory", Vendor, Vendor.'name()')` renvoient une liste de fournisseurs qui est triée par nom dans l’ordre croissant.

Lorsque vous configurez l’expression `ORDERBY ("Query", Vendor, Vendor.'name()')` dans le concepteur de mappage du modèle de gestion des états électroniques, une [erreur](er-components-inspections.md#i8) de validation se produit au moment de la conception, car le chemin `Vendor.'name()'` fait référence à une méthode d’application dont la logique ne peut pas être traduite en une requête de base de données directe.

## <a name="example-3-database-query"></a><a name="example-3"></a>Exemple 3 : requête de base de données

Si **TaxTransaction** est configuré comme une source de données de gestion des états électroniques de type *Enregistrements de table* qui fait référence à la table **TaxTrans**, l’expression `ORDERBY ("Query", TaxTransaction, TaxTransaction.TaxCode)` trie les enregistrements au niveau de la base de données de l’application et renvoie une liste des transactions fiscales qui est triée par code fiscal dans l’ordre croissant.

## <a name="example-4-queryable-data-sources"></a><a name="example-4"></a>Exemple 4 : Sources de données interrogeables

Si **TaxTransaction** est configuré comme source de données de gestion des états électroniques de type *Enregistrements de table* qui fait référence à la table **TaxTrans**, la source de données de gestion des états électroniques **TaxTransactionFiltered** peut être configurée de sorte qu’elle contienne l’expression `FILTER(TaxTransaction, TaxCode="VAT19")` qui récupérera les transactions pour un code fiscal spécifié. Parce que la source de données de gestion des états électroniques configurée **TaxTransactionFiltered** est interrogeable, l’expression `ORDERBY ("Query", TaxTransactionFiltered, TaxTransactionFiltered.TransDate)` peut être configurée pour renvoyer la liste des transactions fiscales filtrées qui est triée par date de transaction dans l’ordre croissant.

Si vous configurez **TaxTransactionOrdered** en tant que source de données de gestion des états électroniques du type *Champ calculé* qui contient l’expression `ORDERBY ("Query", TaxTransaction, TaxTransaction.TransDate)` et une source de données de gestion des états électroniques de type *Champ calculé* qui contient l’expression `FILTER(TaxTransactionOrdered, TaxCode="VAT19")`, une [erreur](er-components-inspections.md#i18) de validation se produit au moment de la conception dans le concepteur de mappage de modèle de gestion des états électroniques. Cette erreur se produit, car le premier argument de la fonction [FILTER](er-functions-list-filter.md#usage-notes) doit faire référence à une source de données de gestion des états électroniques interrogeable, mais la source de données **TaxTransactionOrdered** qui contient la fonction `ORDERBY` n’est pas interrogeable.

## <a name="example-5-comparability"></a><a name="example-5"></a>Exemple 5 : Comparabilité

### <a name="prerequisites"></a>Conditions préalables

1. Saisissez la source de données **DS1** du type *Champ calculé* qui contient l’expression `SPLIT ("D1|_D2|D3", "|")`.
2. Ouvrez la page **[Valeurs des dimensions financières](../../../finance/general-ledger/financial-dimensions.md)** et sélectionnez la dimension **CostCenter**.
3. Saisissez les valeurs de dimension suivantes : **D1**, **\_D2** et **D3**.

### <a name="sorting-in-memory"></a>Tri en mémoire

1. Configurez la source de données **DS2** du type *Champ calculé* qui contient l’expression `ORDERBY("InMemory", DS1, DS1.Value)`.
2. Remarquez que l’expression `FIRST(DS2).Value` renvoie la valeur du texte **« D1 »**, l’expression `INDEX(DS2, COUNT(DS2)).Value` renvoie la valeur du texte **« \_D2 »**, et l’expression `STRINGJOIN(DS2, DS2.Value, "|")` renvoie la valeur du texte **« D1\|D3\|\_D2 »**.

### <a name="sorting-in-database"></a>Tri dans la base de données

1. Saisissez la source de données **DS3** du type *Enregistrements de la table* qui fait référence à l’entité **FinancialDimensionValueEntity**.
2. Configurez la source de données **DS4** du type *Champ calculé* qui contient l’expression `FILTER(DS3, DS3.FinancialDimension="CostCenter")`.
3. Configurez la source de données **DS5** du type *Champ calculé* qui contient l’expression `ORDERBY(DS4, DS4.DimensionValue)`.
4. Remarquez que l’expression `FIRST(DS5).Value` renvoie la valeur du texte **« \_D2 »**, l’expression `INDEX(DS5, COUNT(DS5)).Value` renvoie la valeur du texte **« D3 »**, et l’expression `STRINGJOIN(DS5, DS5.Value, "|")` renvoie la valeur du texte **« \_D2\|D1\|D3 »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
