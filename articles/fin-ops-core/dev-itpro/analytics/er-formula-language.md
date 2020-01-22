---
title: Langage de formule dans la gestion des états électroniques
description: Cette rubrique fournit des informations sur l'utilisation du langage de formule dans les États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/18/2019
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
ms.openlocfilehash: 3b1c6a3f3fd5b55012d89a6c9f0bf2ed5dddd13c
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916658"
---
# <a name="electronic-reporting-formula-language"></a>Langage de formule dans la gestion des états électroniques

[!include [banner](../includes/banner.md)]

Les états électroniques (ER) offrent une puissante expérience de transformation des données. Le langage utilisé pour exprimer les manipulations de données requises dans le concepteur de formule ER ressemble au langage de formule dans Microsoft Excel.

## <a name="basic-syntax"></a>Syntaxe de base

Les expressions de génération d'états électroniques peuvent contenir le tout ou partie des éléments suivants :

- [Constantes](#Constants)
- [Opérateurs](#Operators)
- [Références](#References)
- [Chemins d'accès](#Paths)
- [Fonctions](#Functions)

## <a name="Constants">Constantes</a>

Lorsque vous concevez des expressions, vous pouvez utiliser les constantes de texte et numériques, c'est-à-dire les valeurs qui ne sont pas calculées. Par exemple, l'expression `VALUE ("100") + 20` utilise la constante **20** et la constante de chaîne **« 100 »** et renvoie la valeur numérique **120**.

Le concepteur de formule de génération d'états électroniques prend en charge les séquences d'échappement. Par conséquent, vous pouvez spécifier une chaîne d'expression qui doit être traitée différemment. Par exemple, l'expression `"Leo Tolstoy ""War and Peace"" Volume 1"` renvoie la chaîne de texte **Léon Tolstoï « Guerre et paix » Tome 1**.

## <a name="Operators">Opérateurs</a>

Le tableau suivant indique les opérateurs arithmétiques que vous pouvez utiliser pour effectuer des opérations mathématiques de base, telles que l'addition, la soustraction, la multiplication et la division.

| Opérateur | Signifie               | Exemple     |
|----------|-----------------------|-------------|
| +        | Addition              | `1+2`       |
| -        | Soustraction, négation | `5-2`, `-1` |
| \*       | Multiplication        | `7\*8`      |
| /        | Service              | `9/3`       |

Le tableau suivant décrit les opérateurs de comparaison pris en charge. Vous pouvez utiliser ces opérateurs pour comparer deux valeurs.

| Opérateur | Signifie                  | Exemple      |
|----------|--------------------------|--------------|
| =        | Egal                    | `X=Y`        |
| &gt;     | Supérieur             | `X>Y`        |
| &lt;     | Inférieur à                | `X<Y`        |
| &gt;=    | Supérieur ou égal à | `X>=Y`       |
| &lt;=    | Inférieur ou égal à    | `X<=Y`       |
| &lt;&gt; | Différent de             | `X<>Y`       |

En outre, vous pouvez utiliser une esperluette (&) comme opérateur de concaténation de texte. De cette manière, vous pouvez lier ou concaténer une ou plusieurs chaînes de texte en un bloc de texte unique.

| Opérateur | Signifie     | Exemple                                               |
|----------|-------------|-------------------------------------------------------|
| &        | Concaténer | `"Nothing to print:" & " " & "no records found"`      |

### <a name="operator-precedence"></a>Priorité des opérateurs

L'ordre dans lequel les parties d'une expression de composant sont évaluées est important. Par exemple, le résultat de l'expression `1 + 4 / 2` varie selon que l'addition ou la division est effectuée en premier. Vous pouvez utiliser des parenthèses pour définir explicitement la manière dont une expression est évaluée. Par exemple, pour indiquer que l'addition doit être exécutée en premier, vous pouvez modifier l'expression précédente comme suit : `(1 + 4) / 2`. Si vous n'indiquez pas explicitement l'ordre des opérations à effectuer dans une expression, l'ordre est basé sur la priorité par défaut attribuée aux opérateurs pris en charge. Le tableau suivant indique la priorité affectée à chaque opérateur. Les opérateurs qui ont la priorité la plus élevée (par exemple, 7) sont évalués avant les opérateurs ayant une priorité inférieure (par exemple, 1).

| Priorité | Opérateurs      | Syntaxe                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Regroupement       | ( … )                                                                   |
| 6          | Accès des membres  | … . …                                                                   |
| 5          | Appel de fonction  | … ( … )                                                                 |
| 4          | Multiplicateur | … \* …<br>… / …                                                         |
| 3          | Supplémentaire       | … + …<br>… - …                                                          |
| 2          | Comparaison     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Séparation     | … , …                                                                   |

Si une expression comprend plusieurs opérateurs consécutifs qui ont la même priorité, ces opérations sont évaluées de gauche à droite. Par exemple, l'expression `1 + 6 / 2 \* 3 > 5` renvoie la valeur **true**. Il est recommandé d'utiliser des parenthèses pour indiquer explicitement l'ordre des opérations dans les expressions, afin de faciliter la lecture et la mise à jour des expressions.

## <a name="References">Références</a>

Toutes les sources de données du composant de génération d'états électroniques actuel qui sont disponibles lors de la création d'une expression peuvent servir de références nommées. Le composant ER actuel peut être un mappage de modèle ou un format. Par exemple, le mappage de modèles de génération d'états électroniques actuel contient la source de données **ReportingDate** qui renvoie une valeur du type de données *DateTime*. Pour formater correctement cette valeur dans le document de génération, vous pouvez référencer la source de données dans l'expression comme suit : `DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")`.

Tous les caractères du nom d'une source de données de référencement qui ne représentent pas une lettre de l'alphabet doivent être précédés d'un guillemet simple ('). Si le nom d'une source de données de référencement contient au moins un symbole qui ne représente pas une lettre de l'alphabet, le nom doit être placé entre guillemets simples ('). Par exemple, ces symboles non alphabétiques peuvent être les signes de ponctuation ou tous les autres symboles écrits. Voici quelques exemples :

- La source de données **Date & heure d'aujourd'hui** doit être utilisée dans une expression de génération d'états électroniques comme suit : `'Today''s date & time'`.
- La méthode **name()** de la source de données **Clients** doit être référencée dans l'expression de génération d'états électroniques comme suit : `Customers.'name()'`.

Si les méthodes des sources de données de l'application ont des paramètres, la syntaxe suivante est utilisée pour appeler ces méthodes :

- Si la méthode **isLanguageRTL** de la source de données **Système** a un paramètre **EN-US** du type de données *Chaîne*, cette méthode doit être mentionnée dans une expression ER comme suit : `System.isLanguageRTL("EN-US")`.
- Les guillemets ne sont pas obligatoires lorsqu'un nom de méthode ne contient que des symboles alphanumériques. Toutefois, ils sont obligatoires pour une méthode de table si le nom inclut des parenthèses.

Lorsque la source de données **System** est ajoutée à une mise en correspondance ER qui fait référence à la classe d'application **Global** de l'application, l'expression `System.isLanguageRTL("EN-US ")` retourne la valeur *booléenne*, **FALSE**. L'expression modifiée `System.isLanguageRTL("AR")` renvoie la valeur *Booléenne* **TRUE**.

Vous pouvez limiter la façon dont les valeurs sont transférées aux paramètres de ce type de méthode :

- Seules les constantes peuvent être transférées aux méthodes de ce type. Les valeurs des constantes sont définies au moment de la conception.
- Seuls les types de données (de base) primitifs sont pris en charge pour les paramètres de ce type. Les types de données primitifs inclut *Entier*, *Réel*, *Booléen* et *Chaîne*.

## <a name="Paths">Chemins d'accès</a>

Lorsqu'une expression fait référence à une source de données structurée, vous pouvez utiliser la définition de chemin d'accès pour sélectionner un élément primitif spécifique de cette source de données. Un point (.) est utilisé pour séparer les éléments distincts d'une source de données structurée. Par exemple, le mappage de modèles de génération d'états électroniques actuel contient la source de données **InvoiceTransactions** qui renvoie une liste des enregistrements. La structure d'enregistrement **InvoiceTransactions** contient les champs **AmountDebit** et **AmountCredit** qui renvoient tous les deux des valeurs numériques. Par conséquent, vous pouvez concevoir l'expression suivante pour calculer le montant facturé : `InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit`. La construction `InvoiceTransactions.AmountDebit` dans cette expression est le chemin d'accès utilisé pour accéder au champ **AmountDebit** de la source de données **InvoiceTransactions** du type *Liste des enregistrements*.

### <a name="relative-path"></a>Chemin d'accès relatif

Si le chemin d'une source de données structurée commence par un signe arobase (@), il s'agit d'un chemin relatif. Le signe arobase est affiché à la place de la partie restante du chemin absolu de l'arborescence hiérarchique utilisée. L'illustration suivante présente un exemple. Ici, le chemin absolu `Ledger.'accountingCurrency()'` indique que la valeur de la devise comptable de la source de données **Comptabilité** est entrée dans le champ **AccountingCurrency** du modèle de données.

![Exemple de chemin absolu sur la page du concepteur de mappage de modèles ER](./media/ER-FormulaLanguage-AbsolutePath.png)

L'exemple de l'illustration suivante montre comment un chemin relatif est utilisé. Le chemin relatif `@.AccountNum` indique que le champ **AccountNum** de la source de données **Déclaration d'échanges de biens** (qui apparaît un niveau au-dessus du champ **AccountNum** dans l'arborescence hiérarchique du modèle de données) est utilisé pour saisir le numéro de compte client ou fournisseur dans le champ **AccountNum** du modèle de données.

![Exemple de chemin relatif sur la page du concepteur de mappage de modèles ER](./media/ER-FormulaLanguage-RelativePath1.png)

La partie restante du chemin absolu est également indiquée dans l'[Éditeur de formule ER](general-electronic-reporting-formula-designer.md).

![Partie restante du chemin absolu sur la page du concepteur de formule ER](./media/ER-FormulaLanguage-RelativePath2.png)

## <a name="Functions">Fonctions</a>

Les fonctions intégrées ER peuvent être utilisées dans les expressions ER. Toutes les sources de données du contexte d'expression (c.-à-d. le mappage de modèles ou format de génération d'états électroniques actuel) peuvent être utilisées en tant que paramètres des fonctions d'appel en accord avec la liste des arguments des fonctions d'appel. Les constantes peuvent également être utilisées comme paramètres des fonctions d'appel. Par exemple, le mappage de modèles de génération d'états électroniques actuel contient la source de données **InvoiceTransactions** qui renvoie une liste des enregistrements. La structure d'enregistrement **InvoiceTransactions** contient les champs **AmountDebit** et **AmountCredit** qui renvoient tous les deux des valeurs numériques. Par conséquent, pour calculer le montant facturé, vous pouvez concevoir l'expression suivante qui utilise la fonction d'arrondi de génération d'états électroniques intégrée : `ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)`.

Lorsque vous concevez des mappages de modèles ER et des états ER, vous pouvez utiliser les fonctions ER dans les catégories suivantes :

- [Fonctions de date et d'heure](er-functions-category-datetime.md)
- [Fonctions de liste](er-functions-category-list.md)
- [Fonctions logiques](er-functions-category-logical.md)
- [Fonctions mathématiques](er-functions-category-mathematical.md)
- [Fonctions d'enregistrement](er-functions-category-record.md)
- [Fonctions texte](er-functions-category-text.md)
- [Fonctions de collecte des données](er-functions-category-data-collection.md)
- [Autre fonctions (spécifiques au domaine d'affaires)](er-functions-category-other.md)
- [Fonctions de conversion de type](er-functions-category-type-conversion.md)

## <a name="functions-list-extension"></a>Extension de la liste des fonctions

La génération d'état électroniques prend en charge une capacité d'extension de la liste des fonctions utilisées dans les expressions de génération d'états électroniques. Pour cela, certaines opérations d'ingénierie sont requises. Pour obtenir des informations détaillées, consultez [Étendre la liste des fonctions de génération d'états électroniques (ER)](general-electronic-reporting-formulas-list-extension.md).

## <a name="compound-expressions"></a>Expressions composées

Vous pouvez créer des expressions composées qui utilisent des fonctions de différentes catégories, à condition que les types de données correspondent. Lorsque vous utilisez des fonctions ensemble, faites correspondre le type de données de la sortie d'une fonction au type de données d'entrée requis par une autre fonction. Par exemple, pour éviter une éventuelle erreur « liste-vide » dans la liaison d'un champ à un élément de format ER, combinez les fonctions de la catégorie [Liste](er-functions-category-list.md) à une fonction de la catégorie [Logique](er-functions-category-logical.md) comme le montre l'exemple suivant. Ici, la formule utilise la fonction [IF](er-functions-logical-if.md) pour tester si la liste **IntrastatTotals** est vide avant de renvoyer la valeur de l'agrégation requise à partir de cette liste. Si la liste **IntrastatTotals** est vide, la formule retourne **0** (zéro).

```
IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="multiple-solutions"></a>Solutions multiples

Souvent, vous pouvez obtenir le même résultat de transformation de données de plusieurs manières, en utilisant des fonctions de différentes catégories ou différentes fonctions de la même catégorie. Par exemple, l'expression précédente peut également être configurée à l'aide de la fonction [COUNT](er-functions-list-count.md) de la catégorie [Liste](er-functions-category-list.md).

```
IF(COUNT (IntrastatTotals)=0, 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des États électroniques](general-electronic-reporting.md)

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Étendre la liste des fonctions de gestion des états électroniques](general-electronic-reporting-formulas-list-extension.md)
