---
title: "Contraintes d&quot;expression et contraintes de table dans les modèles de configuration de produit"
description: "Cette rubrique décrit l&quot;utilisation des contraintes d&quot;expression et de table. Les contraintes permettent de contrôler les valeurs d&quot;attribut que vous pouvez sélectionner lorsque vous configurez des produits pour une commande client, un devis de vente, une commande fournisseur ou un ordre de fabrication. Vous pouvez utiliser des contraintes d&quot;expression ou des contraintes de table selon la façon dont vous préférez créer les contraintes."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-02-24 15 - 08 - 06
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 1fe8a0d90a3f707fa7b0fea0310c819ce5040a42
ms.lasthandoff: 03/30/2017


---

# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a>Contraintes d'expression et contraintes de table dans les modèles de configuration de produit

Cette rubrique décrit l'utilisation des contraintes d'expression et de table. Les contraintes permettent de contrôler les valeurs d'attribut que vous pouvez sélectionner lorsque vous configurez des produits pour une commande client, un devis de vente, une commande fournisseur ou un ordre de fabrication. Vous pouvez utiliser des contraintes d'expression ou des contraintes de table selon la façon dont vous préférez créer les contraintes. 

Les contraintes permettent de contrôler les valeurs d'attribut que vous pouvez sélectionner lorsque vous configurez des produits pour une commande client, un devis de vente, une commande fournisseur ou un ordre de fabrication. Vous pouvez utiliser des contraintes d'expression ou des contraintes de table selon la façon dont vous préférez créer les contraintes.

## <a name="what-are-expression-constraints"></a>Que sont les contraintes d'expression ?
Les contraintes d'expression sont caractérisées par une expression utilisant l'arithmétique, les opérateurs booléens et les fonctions. Une contrainte d'expression est entrée pour un composant spécifique dans un modèle de configuration de produit. Elle ne peuvent pas être réutilisées ni partagées avec un autre composant. Toutefois, les contraintes d'expression pour un composant peuvent référencer des attributs des sous-composants du composant.

## <a name="what-are-table-constraints"></a>Que sont les contraintes de table ?
Les contraintes de table répertorient les combinaisons de valeurs autorisées pour les attributs lorsque vous configurez un produit. Les définitions de contrainte de table peuvent être utilisées génériquement. Lorsque vous créez une contrainte de table pour un composant dans un modèle de configuration de produit, vous sélectionnez une définition de contrainte de table. Pour créer les combinaisons autorisées, vous ajoutez des attributs de types spécifiques aux composants. Chaque type d'attribut a une valeur spécifique.

### <a name="example-of-a-table-constraint"></a>Exemple de contrainte de table

Cet exemple décrit la manière dont vous pouvez limiter la configuration d'un haut-parleur à des finitions et des grilles avant spécifiques. Le premier tableau indique les finitions du meuble et les grilles avant qui sont généralement disponibles pour la configuration. Les valeurs sont définies pour ** fin de Module ** et ** gril avant ** les types d'attribut.

| Type d'attribut | Valeurs                      |
|----------------|-----------------------------|
| Finitions du meuble | Noir, chêne, bois de rose, blanc |
| Grille avant    | Noir, métal, blanc         |

Le tableau suivant indique les combinaisons définies par la contrainte de table **Couleur et finition**. Avec cette contrainte de table, vous pouvez configurer un haut-parleur avec une finition chêne et une grille noire, une finition bois de rose et une grille blanche, etc.

| Terminer         | Grille                       |
|----------------|-----------------------------|
| Chêne            | Noir                       |
| Bois de rose       | Blanc                       |
| Blanc          | Noir                       |
| Blanc          | Blanc                       |
| Noir          | Noir                       |
| Noir          | Métal                       | 

Vous pouvez créer des contraintes de table définies par le système et par l'utilisateur. Pour plus d'informations, voir [Contraintes de table définies par l'utilisateur et par le système](system-defined-user-defined-table-constraints.md).

## <a name="what-syntax-should-be-used-to-write-constraints"></a>Quelle syntaxe doit être utilisée pour écrire des contraintes ?
Vous devez utiliser la syntaxe du langage de modélisation d'optimisation (OML, Optimization Modeling Language) lorsque vous entrez des contraintes. Le système utilise le solveur de contrainte de base de solveur de Microsoft pour résoudre les contraintes.

## <a name="should-i-use-table-constraints-or-expression-constraints"></a>Dois-je utiliser des contraintes de table ou des contraintes d'expression ?
Vous pouvez utiliser des contraintes d'expression ou des contraintes de table selon la façon dont vous préférez créer les contraintes. Vous créez une contrainte de table comme une matrice, alors qu'une contrainte d'expression est un relevé individuel. Lorsque vous configurez un produit, la contrainte utilisée n'a pas d'importance. L'exemple suivant montre comment les deux méthodes diffèrent.  

Lorsque vous configurez un produit à l'aide des paramétrages de contrainte suivants, les combinaisons ci-dessous sont autorisées :

-   Un produit de couleur noire et en taille 30 ou 50
-   Un produit de couleur rouge et en taille 20

### <a name="table-constraint-setup"></a>Paramétrage de contraintes de table

| Couleur | Taille |
|-------|------|
| Noir | 30   |
| Noir | 50   |
| Rouge   | 20   |

### <a name="expression-constraint-setup"></a>Paramétrage de contraintes d'expression

(Color == "Noir" & (size == "30" | size == "50")) | (color == "Rouge" & size = "20")

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a>Dois-je utiliser des opérateurs ou la notation d'infixe lorsque j'écris des contraintes d'expression ?
Vous pouvez entrer une contrainte d'expression à l'aide des opérateurs de préfixe disponibles ou de la notation d'infixe. Pour les opérateurs **Min**, **Max** et **ABS**, vous ne pouvez pas utiliser de notation d'infixe. Ces opérateurs sont inclus comme opérateurs standard dans la plupart des langages de programmation.

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a>Quels opérateurs ou quelle notation d'infixe dois-je utiliser lorsque j'écris des contraintes d'expression ?
Les tableaux suivants répertorient les opérateurs et la notation d'infixe que vous pouvez utiliser lorsque vous entrez une contrainte d'expression pour un composant dans un modèle de configuration de produit. Les exemples du premier tableau montrent comment écrire une expression à l'aide de la notation d'infixe ou d'opérateurs.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Opérateur</th>
<th>Description</th>
<th>Syntaxe</th>
<th>Exemples</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implique</td>
<td>Est vrai si la première condition est fausse, la deuxième condition est remplie, ou les deux.</td>
<td>Implies[a, b], infix: a -: b</td>
<td><ul>
<li><strong>Opérateur :</strong> Implique [x ! = 0, y &gt;= 0]</li>
<li><strong>Notation d'infixe :</strong> X ! = 0 - : y &gt;= 0</li>
</ul></td>
</tr>
<tr class="even">
<td>Et</td>
<td>Est vrai uniquement si toutes les conditions sont remplies. Si le nombre de conditions est 0 (zéro), le résultat est <strong>True</strong>.</td>
<td>Les args [], infixe : &amp; un " &amp; … &amp; z</td>
<td><ul>
<li><strong>Opérateur :</strong> Les [== 2, y de x &lt;= 2]</li>
<li><strong>Notation d'infixe :</strong> X == y &lt;2 &amp; = 2</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ou</td>
<td>Est vrai si n'importe quelle condition est remplie. Si le nombre de conditions est 0 (zéro), le résultat est <strong>False</strong>.</td>
<td>Ou args [], infixe : a ~ b ~ … ~ z</td>
<td><ul>
<li><strong>Opérateur :</strong> Ou [== 2, y de x &lt;= 2]</li>
<li><strong>Notation d'infixe :</strong> X == 2 ~ y &lt;= 2</li>
</ul></td>
</tr>
<tr class="even">
<td>Plus</td>
<td>Additionne ses conditions. Si le nombre de conditions est 0 (zéro), le résultat est <strong>0</strong>.</td>
<td>Plus args [], infixe : a + B + + z…</td>
<td><ul>
<li><strong>Opérateur :</strong> Plus[x, y, 2] == z</li>
<li><strong>Notation d'infixe :</strong> x + y + 2 == z</li>
</ul></td>
</tr>
<tr class="odd">
<td>Moins</td>
<td>Rend son argument négatif. Il doit avoir précisément une condition.</td>
<td>Minus[expr], infix: -expr</td>
<td><ul>
<li><strong>Opérateur :</strong> Minus[x] == y</li>
<li><strong>Notation d'infixe :</strong> -x == y</li>
</ul></td>
</tr>
<tr class="even">
<td>Abs</td>
<td>Prend la valeur absolue de sa condition. Il doit avoir précisément une condition.</td>
<td>Abs[expr]</td>
<td><strong>Opérateur :</strong> Abs[x]</td>
</tr>
<tr class="odd">
<td>Heures</td>
<td>Prend le produit de ses conditions. Si le nombre de conditions est 0 (zéro), le résultat est <strong>1</strong>.</td>
<td>Périodes args [], infixe : a B * * * z…</td>
<td><ul>
<li><strong>Opérateur :</strong> Times[x, y, 2] == z</li>
<li><strong>Notation d'infixe :</strong> x * y * 2 == z</li>
</ul></td>
</tr>
<tr class="even">
<td>Puissance</td>
<td>Prend un exponentiel. L'exponentiation est appliquée de droite à gauche. (Autrement dit, elle est droite- associative.) Le <strong>Alimentation [un, B, c']</strong> est, par conséquent équivalent sur <strong>Alimentation [un, alimentation [B, c']]</strong>. <strong>Power</strong> peut être utilisé uniquement si l'exposant est une constante positive.</td>
<td>Alimentation args [], infixe : un ^ z de ^ du ^ B…</td>
<td><ul>
<li><strong>Opérateur :</strong> Power[x, 2] == y</li>
<li><strong>Notation d'infixe :</strong> x ^ 2 == y</li>
</ul></td>
</tr>
<tr class="odd">
<td>Max.</td>
<td>Produit la plus grande condition. Si le nombre de conditions est 0 (zéro), le résultat est <strong>Infinity</strong>.</td>
<td>Max[args]</td>
<td><strong>Opérateur :</strong> Max[x, y, 2] == z</td>
</tr>
<tr class="even">
<td>Min.</td>
<td>Produit la plus petite condition. Si le nombre de conditions est 0 (zéro), le résultat est <strong>Infinity</strong>.</td>
<td>Min[args]</td>
<td><strong>Opérateur :</strong> Min[x, y, 2] == z</td>
</tr>
<tr class="odd">
<td>Non</td>
<td>Produit l'inverse logique de sa condition. Il doit avoir précisément une condition.</td>
<td>Not[expr], infix: !expr</td>
<td><ul>
<li><strong>Opérateur :</strong> Pas x [] &amp; pas [== 3 de y]</li>
<li><strong>Notation d'infixe :</strong> !x!(y == 3)</li>
</ul></td>
</tr>
</tbody>
</table>

Les exemples du tableau suivant indiquent comment entrer une notation d'infixe.

| Notation d'infixe    | description ;                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| x + y + z         | Addition                                                                                      |
| X \* y \* z       | Multiplication                                                                                |
| x - y             | La soustraction binaire est traduite de la même façon que l'addition binaire avec un second négatif. |
| x ^ y ^ z         | Exponentiation avec associativité à droite                                                   |
| !x                | Non booléen                                                                                   |
| x -: y            | Implication booléenne                                                                           |
| x | y | z         | Ou booléen                                                                                    |
| x & y & z         | Et booléen                                                                                   |
| x == y == z       | Égalité                                                                                      |
| x != y != z       | Distinct                                                                                      |
| X &lt; y &lt; z   | Inférieur à                                                                                     |
| X &gt; y &gt; z   | Supérieur                                                                                  |
| X &lt;= y &lt;= z | Inférieur ou égal à                                                                         |
| X &gt;= y &gt;= z | Supérieur ou égal à                                                                      |
| (x)               | Les parenthèses remplacent la priorité par défaut.                                                      |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a>Pourquoi mes contraintes d'expression ne sont-elle pas validées correctement ?
Vous ne pouvez pas utiliser de mots clés réservés comme nom de solveur pour les attributs, les composants ou les sous-composants dans un modèle de configuration de produit. Voici une liste des mots clés réservés que vous ne pouvez pas utiliser :

-   Plafond
-   Elément
-   Égal à
-   Sol
-   Si
-   Inférieur
-   Supérieur
-   Implique
-   Journal
-   Max.
-   Min.
-   Moins
-   Plus
-   Puissance
-   Temps
-   Emplacement
-   Modèle
-   Décision
-   Objectif


<a name="see-also"></a>Voir également :
--------

[Créez une Expression (Guide de tâche)](http://ax.help.dynamics.com/en/wiki/create-an-expression-constraint/)

[Ajout d'un calcul à un modèle de configuration de produit (Guide de tâche)](http://ax.help.dynamics.com/en/wiki/add-a-calculation-to-a-product-configuration-model/)


