---
title: Contraintes d’expression et contraintes de table dans les modèles de configuration de produit
description: Cette rubrique décrit l’utilisation des contraintes d’expression et de table. Les contraintes permettent de contrôler les valeurs d’attribut que vous pouvez sélectionner lorsque vous configurez des produits pour une commande client, un devis de vente, une commande fournisseur ou un ordre de fabrication. Vous pouvez utiliser des contraintes d’expression ou des contraintes de table selon la façon dont vous préférez créer les contraintes.
author: cvocph
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2480348147144cf3004c872ce90b416e0e5d83e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829448"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a><span data-ttu-id="73fce-105">Contraintes d’expression et contraintes de table dans les modèles de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="73fce-105">Expression constraints and table constraints in product configuration models</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="73fce-106">Cette rubrique décrit l’utilisation des contraintes d’expression et de table.</span><span class="sxs-lookup"><span data-stu-id="73fce-106">This topic describes the use of expression constraints and table constraints.</span></span> <span data-ttu-id="73fce-107">Les contraintes permettent de contrôler les valeurs d’attribut que vous pouvez sélectionner lorsque vous configurez des produits pour une commande client, un devis de vente, une commande fournisseur ou un ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="73fce-107">Constraints control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="73fce-108">Vous pouvez utiliser des contraintes d’expression ou des contraintes de table selon la façon dont vous préférez créer les contraintes.</span><span class="sxs-lookup"><span data-stu-id="73fce-108">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> 

<span data-ttu-id="73fce-109">Les contraintes permettent de contrôler les valeurs d’attribut que vous pouvez sélectionner lorsque vous configurez des produits pour une commande client, un devis de vente, une commande fournisseur ou un ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="73fce-109">Constraints are used to control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="73fce-110">Vous pouvez utiliser des contraintes d’expression ou des contraintes de table selon la façon dont vous préférez créer les contraintes.</span><span class="sxs-lookup"><span data-stu-id="73fce-110">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span>

## <a name="what-are-expression-constraints"></a><span data-ttu-id="73fce-111">Que sont les contraintes d’expression ?</span><span class="sxs-lookup"><span data-stu-id="73fce-111">What are expression constraints?</span></span>
<span data-ttu-id="73fce-112">Les contraintes d’expression sont caractérisées par une expression utilisant l’arithmétique, les opérateurs booléens et les fonctions.</span><span class="sxs-lookup"><span data-stu-id="73fce-112">Expression constraints are characterized by an expression that uses arithmetic and Boolean operators and functions.</span></span> <span data-ttu-id="73fce-113">Une contrainte d’expression est entrée pour un composant spécifique dans un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="73fce-113">An expression constraint is written for a specific component in a product configuration model.</span></span> <span data-ttu-id="73fce-114">Elle ne peuvent pas être réutilisées ni partagées avec un autre composant.</span><span class="sxs-lookup"><span data-stu-id="73fce-114">It can't be reused by or shared with another component.</span></span> <span data-ttu-id="73fce-115">Toutefois, les contraintes d’expression pour un composant peuvent référencer des attributs des sous-composants du composant.</span><span class="sxs-lookup"><span data-stu-id="73fce-115">However, the expression constraints for a component can reference attributes of the component's subcomponents.</span></span>

## <a name="what-are-table-constraints"></a><span data-ttu-id="73fce-116">Que sont les contraintes de table ?</span><span class="sxs-lookup"><span data-stu-id="73fce-116">What are table constraints?</span></span>
<span data-ttu-id="73fce-117">Les contraintes de table répertorient les combinaisons de valeurs autorisées pour les attributs lorsque vous configurez un produit.</span><span class="sxs-lookup"><span data-stu-id="73fce-117">Table constraints list the combinations of values that are allowed for attributes when you configure a product.</span></span> <span data-ttu-id="73fce-118">Les définitions de contrainte de table peuvent être utilisées génériquement.</span><span class="sxs-lookup"><span data-stu-id="73fce-118">Table constraint definitions can be used generically.</span></span> <span data-ttu-id="73fce-119">Lorsque vous créez une contrainte de table pour un composant dans un modèle de configuration de produit, vous sélectionnez une définition de contrainte de table.</span><span class="sxs-lookup"><span data-stu-id="73fce-119">When you create a table constraint for a component in a product configuration model, you select a table constraint definition.</span></span> <span data-ttu-id="73fce-120">Pour créer les combinaisons autorisées, vous ajoutez des attributs de types spécifiques aux composants.</span><span class="sxs-lookup"><span data-stu-id="73fce-120">To create the combinations that are allowed, you add attributes of specific types to the components.</span></span> <span data-ttu-id="73fce-121">Chaque type d’attribut a une valeur spécifique.</span><span class="sxs-lookup"><span data-stu-id="73fce-121">Each attribute type has a specific value.</span></span>

### <a name="example-of-a-table-constraint"></a><span data-ttu-id="73fce-122">Exemple de contrainte de table</span><span class="sxs-lookup"><span data-stu-id="73fce-122">Example of a table constraint</span></span>

<span data-ttu-id="73fce-123">Cet exemple décrit la manière dont vous pouvez limiter la configuration d’un haut-parleur à des finitions et des grilles avant spécifiques.</span><span class="sxs-lookup"><span data-stu-id="73fce-123">This example shows how you can limit the configuration of a speaker to specific cabinet finishes and fronts.</span></span> <span data-ttu-id="73fce-124">Le premier tableau indique les finitions du meuble et les grilles avant qui sont généralement disponibles pour la configuration.</span><span class="sxs-lookup"><span data-stu-id="73fce-124">The first table shows the cabinet finishes and fronts that are generally available for configuration.</span></span> <span data-ttu-id="73fce-125">Les valeurs sont définies pour les types d’attribut **Finitions du meuble** et **Grille avant**.</span><span class="sxs-lookup"><span data-stu-id="73fce-125">The values are defined for the **Cabinet finish** and **Front grill** attribute types.</span></span>

| <span data-ttu-id="73fce-126">Type d’attribut</span><span class="sxs-lookup"><span data-stu-id="73fce-126">Attribute type</span></span> | <span data-ttu-id="73fce-127">Valeurs</span><span class="sxs-lookup"><span data-stu-id="73fce-127">Values</span></span>                      |
|----------------|-----------------------------|
| <span data-ttu-id="73fce-128">Finitions du meuble</span><span class="sxs-lookup"><span data-stu-id="73fce-128">Cabinet finish</span></span> | <span data-ttu-id="73fce-129">Noir, chêne, bois de rose, blanc</span><span class="sxs-lookup"><span data-stu-id="73fce-129">Black, Oak, Rosewood, White</span></span> |
| <span data-ttu-id="73fce-130">Grille avant</span><span class="sxs-lookup"><span data-stu-id="73fce-130">Front grill</span></span>    | <span data-ttu-id="73fce-131">Noir, métal, blanc</span><span class="sxs-lookup"><span data-stu-id="73fce-131">Black, Metal, White</span></span>         |

<span data-ttu-id="73fce-132">Le tableau suivant indique les combinaisons définies par la contrainte de table **Couleur et finition**.</span><span class="sxs-lookup"><span data-stu-id="73fce-132">The next table shows the combinations that are defined by the **Color and finish** table constraint.</span></span> <span data-ttu-id="73fce-133">Avec cette contrainte de table, vous pouvez configurer un haut-parleur avec une finition chêne et une grille noire, une finition bois de rose et une grille blanche, etc.</span><span class="sxs-lookup"><span data-stu-id="73fce-133">By using this table constraint, you can configure a speaker that has an oak finish and a black grill, a Rosewood finish and a white grill, and so on.</span></span>

| <span data-ttu-id="73fce-134">Terminer</span><span class="sxs-lookup"><span data-stu-id="73fce-134">Finish</span></span>         | <span data-ttu-id="73fce-135">Grille</span><span class="sxs-lookup"><span data-stu-id="73fce-135">Grill</span></span>                       |
|----------------|-----------------------------|
| <span data-ttu-id="73fce-136">Chêne</span><span class="sxs-lookup"><span data-stu-id="73fce-136">Oak</span></span>            | <span data-ttu-id="73fce-137">Noir</span><span class="sxs-lookup"><span data-stu-id="73fce-137">Black</span></span>                       |
| <span data-ttu-id="73fce-138">Bois de rose</span><span class="sxs-lookup"><span data-stu-id="73fce-138">Rosewood</span></span>       | <span data-ttu-id="73fce-139">Blanc</span><span class="sxs-lookup"><span data-stu-id="73fce-139">White</span></span>                       |
| <span data-ttu-id="73fce-140">Blanc</span><span class="sxs-lookup"><span data-stu-id="73fce-140">White</span></span>          | <span data-ttu-id="73fce-141">Noir</span><span class="sxs-lookup"><span data-stu-id="73fce-141">Black</span></span>                       |
| <span data-ttu-id="73fce-142">Blanc</span><span class="sxs-lookup"><span data-stu-id="73fce-142">White</span></span>          | <span data-ttu-id="73fce-143">Blanc</span><span class="sxs-lookup"><span data-stu-id="73fce-143">White</span></span>                       |
| <span data-ttu-id="73fce-144">Noir</span><span class="sxs-lookup"><span data-stu-id="73fce-144">Black</span></span>          | <span data-ttu-id="73fce-145">Noir</span><span class="sxs-lookup"><span data-stu-id="73fce-145">Black</span></span>                       |
| <span data-ttu-id="73fce-146">Noir</span><span class="sxs-lookup"><span data-stu-id="73fce-146">Black</span></span>          | <span data-ttu-id="73fce-147">Métal</span><span class="sxs-lookup"><span data-stu-id="73fce-147">Metal</span></span>                       | 

<span data-ttu-id="73fce-148">Vous pouvez créer des contraintes de table définies par le système et par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="73fce-148">You can create system-defined and user-defined table constraints.</span></span> <span data-ttu-id="73fce-149">Pour plus d’informations, voir [Contraintes de table définies par l’utilisateur et par le système](system-defined-user-defined-table-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="73fce-149">For more information, see [System-defined and user-defined table constraints](system-defined-user-defined-table-constraints.md).</span></span>

## <a name="what-syntax-should-be-used-to-write-constraints"></a><span data-ttu-id="73fce-150">Quelle syntaxe doit être utilisée pour écrire des contraintes ?</span><span class="sxs-lookup"><span data-stu-id="73fce-150">What syntax should be used to write constraints?</span></span>
<span data-ttu-id="73fce-151">Vous devez utiliser la syntaxe du langage de modélisation d’optimisation (OML, Optimization Modeling Language) lorsque vous entrez des contraintes.</span><span class="sxs-lookup"><span data-stu-id="73fce-151">You must use Optimization Modeling Language (OML) syntax when you write constraints.</span></span> <span data-ttu-id="73fce-152">Le système utilise le solveur de contrainte Microsoft Solver Foundation pour résoudre les contraintes.</span><span class="sxs-lookup"><span data-stu-id="73fce-152">The system uses Microsoft Solver Foundation constraint solver to solve the constraints.</span></span>

## <a name="should-i-use-table-constraints-or-expression-constraints"></a><span data-ttu-id="73fce-153">Dois-je utiliser des contraintes de table ou des contraintes d’expression ?</span><span class="sxs-lookup"><span data-stu-id="73fce-153">Should I use table constraints or expression constraints?</span></span>
<span data-ttu-id="73fce-154">Vous pouvez utiliser des contraintes d’expression ou des contraintes de table selon la façon dont vous préférez créer les contraintes.</span><span class="sxs-lookup"><span data-stu-id="73fce-154">You can use either expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> <span data-ttu-id="73fce-155">Vous créez une contrainte de table comme une matrice, alors qu’une contrainte d’expression est un relevé individuel.</span><span class="sxs-lookup"><span data-stu-id="73fce-155">You build a table constraint as a matrix, whereas an expression constraint is an individual statement.</span></span> <span data-ttu-id="73fce-156">Lorsque vous configurez un produit, la contrainte utilisée n’a pas d’importance.</span><span class="sxs-lookup"><span data-stu-id="73fce-156">When you configure a product, it doesn't matter what kind of constraint is used.</span></span> <span data-ttu-id="73fce-157">L’exemple suivant montre comment les deux méthodes diffèrent.</span><span class="sxs-lookup"><span data-stu-id="73fce-157">The following example shows how the two methods differ.</span></span>  

<span data-ttu-id="73fce-158">Lorsque vous configurez un produit à l’aide des paramétrages de contrainte suivants, les combinaisons ci-dessous sont autorisées :</span><span class="sxs-lookup"><span data-stu-id="73fce-158">When you configure a product by using the following constraint setups, these combinations are allowed:</span></span>

-   <span data-ttu-id="73fce-159">Un produit de couleur noire et en taille 30 ou 50</span><span class="sxs-lookup"><span data-stu-id="73fce-159">A product in the color Black, and in size 30 or 50</span></span>
-   <span data-ttu-id="73fce-160">Un produit de couleur rouge et en taille 20</span><span class="sxs-lookup"><span data-stu-id="73fce-160">A product in the color Red and in size 20</span></span>

### <a name="table-constraint-setup"></a><span data-ttu-id="73fce-161">Paramétrage de contraintes de table</span><span class="sxs-lookup"><span data-stu-id="73fce-161">Table constraint setup</span></span>

| <span data-ttu-id="73fce-162">Couleur</span><span class="sxs-lookup"><span data-stu-id="73fce-162">Color</span></span> | <span data-ttu-id="73fce-163">Taille</span><span class="sxs-lookup"><span data-stu-id="73fce-163">Size</span></span> |
|-------|------|
| <span data-ttu-id="73fce-164">Noir</span><span class="sxs-lookup"><span data-stu-id="73fce-164">Black</span></span> | <span data-ttu-id="73fce-165">30</span><span class="sxs-lookup"><span data-stu-id="73fce-165">30</span></span>   |
| <span data-ttu-id="73fce-166">Noir</span><span class="sxs-lookup"><span data-stu-id="73fce-166">Black</span></span> | <span data-ttu-id="73fce-167">50</span><span class="sxs-lookup"><span data-stu-id="73fce-167">50</span></span>   |
| <span data-ttu-id="73fce-168">Rouge</span><span class="sxs-lookup"><span data-stu-id="73fce-168">Red</span></span>   | <span data-ttu-id="73fce-169">20</span><span class="sxs-lookup"><span data-stu-id="73fce-169">20</span></span>   |

### <a name="expression-constraint-setup"></a><span data-ttu-id="73fce-170">Paramétrage de contraintes d’expression</span><span class="sxs-lookup"><span data-stu-id="73fce-170">Expression constraint setup</span></span>

<span data-ttu-id="73fce-171">(Color == "Noir" & (size == "30" | size == "50")) | (color == "Rouge" & size = "20")</span><span class="sxs-lookup"><span data-stu-id="73fce-171">(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")</span></span>

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a><span data-ttu-id="73fce-172">Dois-je utiliser des opérateurs ou la notation d’infixe lorsque j’écris des contraintes d’expression ?</span><span class="sxs-lookup"><span data-stu-id="73fce-172">Should I use operators or infix notation when I write expression constraints?</span></span>
<span data-ttu-id="73fce-173">Vous pouvez entrer une contrainte d’expression à l’aide des opérateurs de préfixe disponibles ou de la notation d’infixe.</span><span class="sxs-lookup"><span data-stu-id="73fce-173">You can write an expression constraint by using either the available prefix operators or infix notation.</span></span> <span data-ttu-id="73fce-174">Pour les opérateurs **Min**, **Max** et **ABS**, vous ne pouvez pas utiliser de notation d’infixe.</span><span class="sxs-lookup"><span data-stu-id="73fce-174">For the **Min**, **Max**, and **Abs** operators, you can't use infix notation.</span></span> <span data-ttu-id="73fce-175">Ces opérateurs sont inclus comme opérateurs standard dans la plupart des langages de programmation.</span><span class="sxs-lookup"><span data-stu-id="73fce-175">These operators are included as standard operators in most programming languages.</span></span>

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a><span data-ttu-id="73fce-176">Quels opérateurs ou quelle notation d’infixe dois-je utiliser lorsque j’écris des contraintes d’expression ?</span><span class="sxs-lookup"><span data-stu-id="73fce-176">What operators and infix notation can I use when I write expression constraints?</span></span>
<span data-ttu-id="73fce-177">Les tableaux suivants répertorient les opérateurs et la notation d’infixe que vous pouvez utiliser lorsque vous entrez une contrainte d’expression pour un composant dans un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="73fce-177">The following tables list the operators and infix notation that you can use when you write an expression constraint for a component in a product configuration model.</span></span> <span data-ttu-id="73fce-178">Les exemples du premier tableau montrent comment écrire une expression à l’aide de la notation d’infixe ou d’opérateurs.</span><span class="sxs-lookup"><span data-stu-id="73fce-178">The examples in the first table show how to write an expression by using either infix notation or operators.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73fce-179">Opérateur</span><span class="sxs-lookup"><span data-stu-id="73fce-179">Operator</span></span></th>
<th><span data-ttu-id="73fce-180">Description</span><span class="sxs-lookup"><span data-stu-id="73fce-180">Description</span></span></th>
<th><span data-ttu-id="73fce-181">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="73fce-181">Syntax</span></span></th>
<th><span data-ttu-id="73fce-182">Exemples</span><span class="sxs-lookup"><span data-stu-id="73fce-182">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="73fce-183">Implique</span><span class="sxs-lookup"><span data-stu-id="73fce-183">Implies</span></span></td>
<td><span data-ttu-id="73fce-184">Est vrai si la première condition est fausse, la deuxième condition est remplie, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="73fce-184">This is true if the first condition is false, the second condition is true, or both.</span></span></td>
<td><span data-ttu-id="73fce-185">Implies[a, b], infix: a -: b</span><span class="sxs-lookup"><span data-stu-id="73fce-185">Implies[a, b], infix: a -: b</span></span></td>
<td><ul>
<li><span data-ttu-id="73fce-186"><strong>Opérateur :</strong> Implies[x != 0, y &gt;= 0]</span><span class="sxs-lookup"><span data-stu-id="73fce-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span></span></li>
<li><span data-ttu-id="73fce-187"><strong>Notation d’infixe :</strong> x != 0 -: y &gt;= 0</span><span class="sxs-lookup"><span data-stu-id="73fce-187"><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="73fce-188">Et</span><span class="sxs-lookup"><span data-stu-id="73fce-188">And</span></span></td>
<td><span data-ttu-id="73fce-189">Est vrai uniquement si toutes les conditions sont remplies.</span><span class="sxs-lookup"><span data-stu-id="73fce-189">This is true only if all conditions are true.</span></span> <span data-ttu-id="73fce-190">Si le nombre de conditions est 0 (zéro), le résultat est <strong>True</strong>.</span><span class="sxs-lookup"><span data-stu-id="73fce-190">If the number of conditions is 0 (zero), it produces <strong>True</strong>.</span></span></td>
<td><span data-ttu-id="73fce-191">And[args], infix: a &amp; b &amp; ... &amp; z</span><span class="sxs-lookup"><span data-stu-id="73fce-191">And[args], infix: a &amp; b &amp; ... &amp; z</span></span></td>
<td><ul>
<li><span data-ttu-id="73fce-192"><strong>Opérateur :</strong> And[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="73fce-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="73fce-193"><strong>Notation d’infixe :</strong> x == 2 &amp; y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="73fce-193"><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="73fce-194">Ou</span><span class="sxs-lookup"><span data-stu-id="73fce-194">Or</span></span></td>
<td><span data-ttu-id="73fce-195">Est vrai si n’importe quelle condition est remplie.</span><span class="sxs-lookup"><span data-stu-id="73fce-195">This is true if any condition is true.</span></span> <span data-ttu-id="73fce-196">Si le nombre de conditions est 0 (zéro), le résultat est <strong>False</strong>.</span><span class="sxs-lookup"><span data-stu-id="73fce-196">If the number of conditions is 0 (zero), it produces <strong>False</strong>.</span></span></td>
<td><span data-ttu-id="73fce-197">Or[args], infix: a | b | ... | z</span><span class="sxs-lookup"><span data-stu-id="73fce-197">Or[args], infix: a | b | ... | z</span></span></td>
<td><ul>
<li><span data-ttu-id="73fce-198"><strong>Opérateur :</strong> Or[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="73fce-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="73fce-199"><strong>Notation d’infixe :</strong> x == 2 -| y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="73fce-199"><strong>Infix notation:</strong> x == 2 | y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="73fce-200">Plus</span><span class="sxs-lookup"><span data-stu-id="73fce-200">Plus</span></span></td>
<td><span data-ttu-id="73fce-201">Additionne ses conditions.</span><span class="sxs-lookup"><span data-stu-id="73fce-201">This sums its conditions.</span></span> <span data-ttu-id="73fce-202">Si le nombre de conditions est 0 (zéro), le résultat est <strong>0</strong>.</span><span class="sxs-lookup"><span data-stu-id="73fce-202">If the number of conditions is 0 (zero), it produces <strong>0</strong>.</span></span></td>
<td><span data-ttu-id="73fce-203">Plus[args], infix: a + b + ... + z</span><span class="sxs-lookup"><span data-stu-id="73fce-203">Plus[args], infix: a + b + ... + z</span></span></td>
<td><ul>
<li><span data-ttu-id="73fce-204"><strong>Opérateur :</strong> Plus[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="73fce-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="73fce-205"><strong>Notation d’infixe :</strong> x + y + 2 == z</span><span class="sxs-lookup"><span data-stu-id="73fce-205"><strong>Infix notation:</strong> x + y + 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="73fce-206">Moins</span><span class="sxs-lookup"><span data-stu-id="73fce-206">Minus</span></span></td>
<td><span data-ttu-id="73fce-207">Rend son argument négatif.</span><span class="sxs-lookup"><span data-stu-id="73fce-207">This negates its argument.</span></span> <span data-ttu-id="73fce-208">Il doit avoir précisément une condition.</span><span class="sxs-lookup"><span data-stu-id="73fce-208">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="73fce-209">Minus[expr], infix: -expr</span><span class="sxs-lookup"><span data-stu-id="73fce-209">Minus[expr], infix: -expr</span></span></td>
<td><ul>
<li><span data-ttu-id="73fce-210"><strong>Opérateur :</strong> Minus[x] == y</span><span class="sxs-lookup"><span data-stu-id="73fce-210"><strong>Operator:</strong> Minus[x] == y</span></span></li>
<li><span data-ttu-id="73fce-211"><strong>Notation d’infixe :</strong> -x == y</span><span class="sxs-lookup"><span data-stu-id="73fce-211"><strong>Infix notation:</strong> -x == y</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="73fce-212">Abs</span><span class="sxs-lookup"><span data-stu-id="73fce-212">Abs</span></span></td>
<td><span data-ttu-id="73fce-213">Prend la valeur absolue de sa condition.</span><span class="sxs-lookup"><span data-stu-id="73fce-213">This takes the absolute value of its condition.</span></span> <span data-ttu-id="73fce-214">Il doit avoir précisément une condition.</span><span class="sxs-lookup"><span data-stu-id="73fce-214">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="73fce-215">Abs[expr]</span><span class="sxs-lookup"><span data-stu-id="73fce-215">Abs[expr]</span></span></td>
<td><span data-ttu-id="73fce-216"><strong>Opérateur :</strong> Abs[x]</span><span class="sxs-lookup"><span data-stu-id="73fce-216"><strong>Operator:</strong> Abs[x]</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="73fce-217">Heures</span><span class="sxs-lookup"><span data-stu-id="73fce-217">Times</span></span></td>
<td><span data-ttu-id="73fce-218">Prend le produit de ses conditions.</span><span class="sxs-lookup"><span data-stu-id="73fce-218">This takes the product of its conditions.</span></span> <span data-ttu-id="73fce-219">Si le nombre de conditions est 0 (zéro), le résultat est <strong>1</strong>.</span><span class="sxs-lookup"><span data-stu-id="73fce-219">If the number of conditions is 0 (zero), it produces <strong>1</strong>.</span></span></td>
<td><span data-ttu-id="73fce-220">Times[args], infix: a \* b \* ... \* z</span><span class="sxs-lookup"><span data-stu-id="73fce-220">Times[args], infix: a \* b \* ... \* z</span></span></td>
<td><ul>
<li><span data-ttu-id="73fce-221"><strong>Opérateur :</strong> Times[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="73fce-221"><strong>Operator:</strong> Times[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="73fce-222"><strong>Notation d’infixe :</strong> x \* y \* 2 == z</span><span class="sxs-lookup"><span data-stu-id="73fce-222"><strong>Infix notation:</strong> x \* y \* 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="73fce-223">Puissance</span><span class="sxs-lookup"><span data-stu-id="73fce-223">Power</span></span></td>
<td><span data-ttu-id="73fce-224">Prend un exponentiel.</span><span class="sxs-lookup"><span data-stu-id="73fce-224">This takes an exponential.</span></span> <span data-ttu-id="73fce-225">L’exponentiation est appliquée de droite à gauche.</span><span class="sxs-lookup"><span data-stu-id="73fce-225">It applies exponentiation from right to left.</span></span> <span data-ttu-id="73fce-226">Autrement dit, elle est associative à droite. Par conséquent, <strong>Power[a, b, c]</strong> est équivalent à <strong>Power[a, Power[b, c]]</strong>.</span><span class="sxs-lookup"><span data-stu-id="73fce-226">(In other words, it&#39;s right-associative.) Therefore, <strong>Power[a, b, c]</strong> is equivalent to <strong>Power[a, Power[b, c]]</strong>.</span></span> <span data-ttu-id="73fce-227"><strong>Power</strong> peut être utilisé uniquement si l’exposant est une constante positive.</span><span class="sxs-lookup"><span data-stu-id="73fce-227"><strong>Power</strong> can be used only if the exponent is a positive constant.</span></span></td>
<td><span data-ttu-id="73fce-228">Power[args], infix: a ^ b ^ ... ^ z</span><span class="sxs-lookup"><span data-stu-id="73fce-228">Power[args], infix: a ^ b ^ ... ^ z</span></span></td>
<td><ul>
<li><span data-ttu-id="73fce-229"><strong>Opérateur :</strong> Power[x, 2] == y</span><span class="sxs-lookup"><span data-stu-id="73fce-229"><strong>Operator:</strong> Power[x, 2] == y</span></span></li>
<li><span data-ttu-id="73fce-230"><strong>Notation d’infixe :</strong> x ^ 2 == y</span><span class="sxs-lookup"><span data-stu-id="73fce-230"><strong>Infix notation:</strong> x ^ 2 == y</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="73fce-231">Max.</span><span class="sxs-lookup"><span data-stu-id="73fce-231">Max</span></span></td>
<td><span data-ttu-id="73fce-232">Produit la plus grande condition.</span><span class="sxs-lookup"><span data-stu-id="73fce-232">This produces the largest condition.</span></span> <span data-ttu-id="73fce-233">Si le nombre de conditions est 0 (zéro), le résultat est <strong>Infinity</strong>.</span><span class="sxs-lookup"><span data-stu-id="73fce-233">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="73fce-234">Max[args]</span><span class="sxs-lookup"><span data-stu-id="73fce-234">Max[args]</span></span></td>
<td><span data-ttu-id="73fce-235"><strong>Opérateur :</strong> Max[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="73fce-235"><strong>Operator:</strong> Max[x, y, 2] == z</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="73fce-236">Min.</span><span class="sxs-lookup"><span data-stu-id="73fce-236">Min</span></span></td>
<td><span data-ttu-id="73fce-237">Produit la plus petite condition.</span><span class="sxs-lookup"><span data-stu-id="73fce-237">This produces the smallest condition.</span></span> <span data-ttu-id="73fce-238">Si le nombre de conditions est 0 (zéro), le résultat est <strong>Infinity</strong>.</span><span class="sxs-lookup"><span data-stu-id="73fce-238">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="73fce-239">Min[args]</span><span class="sxs-lookup"><span data-stu-id="73fce-239">Min[args]</span></span></td>
<td><span data-ttu-id="73fce-240"><strong>Opérateur :</strong> Min[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="73fce-240"><strong>Operator:</strong> Min[x, y, 2] == z</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="73fce-241">Non</span><span class="sxs-lookup"><span data-stu-id="73fce-241">Not</span></span></td>
<td><span data-ttu-id="73fce-242">Produit l’inverse logique de sa condition.</span><span class="sxs-lookup"><span data-stu-id="73fce-242">This produces the logical inverse of its condition.</span></span> <span data-ttu-id="73fce-243">Il doit avoir précisément une condition.</span><span class="sxs-lookup"><span data-stu-id="73fce-243">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="73fce-244">Not[expr], infix: !expr</span><span class="sxs-lookup"><span data-stu-id="73fce-244">Not[expr], infix: !expr</span></span></td>
<td><ul>
<li><span data-ttu-id="73fce-245"><strong>Opérateur :</strong> Not[x] &amp; Not[y == 3]</span><span class="sxs-lookup"><span data-stu-id="73fce-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span></span></li>
<li><span data-ttu-id="73fce-246"><strong>Notation d’infixe :</strong> !x!(y == 3)</span><span class="sxs-lookup"><span data-stu-id="73fce-246"><strong>Infix notation:</strong> !x!(y == 3)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="73fce-247">Les exemples du tableau suivant indiquent comment entrer une notation d’infixe.</span><span class="sxs-lookup"><span data-stu-id="73fce-247">The examples in the next table show how to write infix notation.</span></span>


|  <span data-ttu-id="73fce-248">Notation d’infixe</span><span class="sxs-lookup"><span data-stu-id="73fce-248">Infix notation</span></span>   |                                          <span data-ttu-id="73fce-249">description ;</span><span class="sxs-lookup"><span data-stu-id="73fce-249">Description</span></span>                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     <span data-ttu-id="73fce-250">x + y + z</span><span class="sxs-lookup"><span data-stu-id="73fce-250">x + y + z</span></span>     |                                           <span data-ttu-id="73fce-251">Addition</span><span class="sxs-lookup"><span data-stu-id="73fce-251">Addition</span></span>                                            |
|    <span data-ttu-id="73fce-252">x \* y \* z</span><span class="sxs-lookup"><span data-stu-id="73fce-252">x \* y \* z</span></span>    |                                        <span data-ttu-id="73fce-253">Multiplication</span><span class="sxs-lookup"><span data-stu-id="73fce-253">Multiplication</span></span>                                         |
|       <span data-ttu-id="73fce-254">x - y</span><span class="sxs-lookup"><span data-stu-id="73fce-254">x - y</span></span>       | <span data-ttu-id="73fce-255">La soustraction binaire est traduite de la même façon que l’addition binaire avec un second négatif.</span><span class="sxs-lookup"><span data-stu-id="73fce-255">Binary subtraction is translated the same as binary addition where there is a negated second.</span></span> |
|     <span data-ttu-id="73fce-256">x ^ y ^ z</span><span class="sxs-lookup"><span data-stu-id="73fce-256">x ^ y ^ z</span></span>     |                          <span data-ttu-id="73fce-257">Exponentiation avec associativité à droite</span><span class="sxs-lookup"><span data-stu-id="73fce-257">Exponentiation that has right associativity</span></span>                          |
|        <span data-ttu-id="73fce-258">!x</span><span class="sxs-lookup"><span data-stu-id="73fce-258">!x</span></span>         |                                          <span data-ttu-id="73fce-259">Non booléen</span><span class="sxs-lookup"><span data-stu-id="73fce-259">Boolean not</span></span>                                          |
|      <span data-ttu-id="73fce-260">x -: y</span><span class="sxs-lookup"><span data-stu-id="73fce-260">x -: y</span></span>       |                                      <span data-ttu-id="73fce-261">Implication booléenne</span><span class="sxs-lookup"><span data-stu-id="73fce-261">Boolean implication</span></span>                                      |
|         <span data-ttu-id="73fce-262">x</span><span class="sxs-lookup"><span data-stu-id="73fce-262">x</span></span>         |                                               <span data-ttu-id="73fce-263">y</span><span class="sxs-lookup"><span data-stu-id="73fce-263">y</span></span>                                               |
|     <span data-ttu-id="73fce-264">x & y & z</span><span class="sxs-lookup"><span data-stu-id="73fce-264">x & y & z</span></span>     |                                          <span data-ttu-id="73fce-265">Et booléen</span><span class="sxs-lookup"><span data-stu-id="73fce-265">Boolean and</span></span>                                          |
|    <span data-ttu-id="73fce-266">x == y == z</span><span class="sxs-lookup"><span data-stu-id="73fce-266">x == y == z</span></span>    |                                           <span data-ttu-id="73fce-267">Égalité</span><span class="sxs-lookup"><span data-stu-id="73fce-267">Equality</span></span>                                            |
|    <span data-ttu-id="73fce-268">x != y != z</span><span class="sxs-lookup"><span data-stu-id="73fce-268">x != y != z</span></span>    |                                           <span data-ttu-id="73fce-269">Distinct</span><span class="sxs-lookup"><span data-stu-id="73fce-269">Distinct</span></span>                                            |
|  <span data-ttu-id="73fce-270">x &lt; y &lt; z</span><span class="sxs-lookup"><span data-stu-id="73fce-270">x &lt; y &lt; z</span></span>  |                                           <span data-ttu-id="73fce-271">Inférieur à</span><span class="sxs-lookup"><span data-stu-id="73fce-271">Less than</span></span>                                           |
|  <span data-ttu-id="73fce-272">x &gt; y &gt; z</span><span class="sxs-lookup"><span data-stu-id="73fce-272">x &gt; y &gt; z</span></span>  |                                         <span data-ttu-id="73fce-273">Supérieur</span><span class="sxs-lookup"><span data-stu-id="73fce-273">Greater than</span></span>                                          |
| <span data-ttu-id="73fce-274">x &lt;= y &lt;= z</span><span class="sxs-lookup"><span data-stu-id="73fce-274">x &lt;= y &lt;= z</span></span> |                                     <span data-ttu-id="73fce-275">Inférieur ou égal à</span><span class="sxs-lookup"><span data-stu-id="73fce-275">Less than or equal to</span></span>                                     |
| <span data-ttu-id="73fce-276">x &gt;= y &gt;= z</span><span class="sxs-lookup"><span data-stu-id="73fce-276">x &gt;= y &gt;= z</span></span> |                                   <span data-ttu-id="73fce-277">Supérieur ou égal à</span><span class="sxs-lookup"><span data-stu-id="73fce-277">Greater than or equal to</span></span>                                    |
|        <span data-ttu-id="73fce-278">(x)</span><span class="sxs-lookup"><span data-stu-id="73fce-278">(x)</span></span>        |                           <span data-ttu-id="73fce-279">Les parenthèses remplacent la priorité par défaut.</span><span class="sxs-lookup"><span data-stu-id="73fce-279">Parentheses override default precedence.</span></span>                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a><span data-ttu-id="73fce-280">Pourquoi mes contraintes d’expression ne sont-elle pas validées correctement ?</span><span class="sxs-lookup"><span data-stu-id="73fce-280">Why aren't my expression constraints validated correctly?</span></span>
<span data-ttu-id="73fce-281">Vous ne pouvez pas utiliser de mots clés réservés comme nom de solveur pour les attributs, les composants ou les sous-composants dans un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="73fce-281">You can't use reserved keywords as solver names for attributes, components, or subcomponents in a product configuration model.</span></span> <span data-ttu-id="73fce-282">Voici la liste des mots clés réservés que vous n’avez pas le droit d’utiliser :</span><span class="sxs-lookup"><span data-stu-id="73fce-282">Here is a list of the reserved keywords that you can't use:</span></span>

-   <span data-ttu-id="73fce-283">Plafond</span><span class="sxs-lookup"><span data-stu-id="73fce-283">Ceiling</span></span>
-   <span data-ttu-id="73fce-284">Elément</span><span class="sxs-lookup"><span data-stu-id="73fce-284">Element</span></span>
-   <span data-ttu-id="73fce-285">Égal à</span><span class="sxs-lookup"><span data-stu-id="73fce-285">Equal</span></span>
-   <span data-ttu-id="73fce-286">Sol</span><span class="sxs-lookup"><span data-stu-id="73fce-286">Floor</span></span>
-   <span data-ttu-id="73fce-287">Si</span><span class="sxs-lookup"><span data-stu-id="73fce-287">If</span></span>
-   <span data-ttu-id="73fce-288">Inférieur</span><span class="sxs-lookup"><span data-stu-id="73fce-288">Less</span></span>
-   <span data-ttu-id="73fce-289">Supérieur</span><span class="sxs-lookup"><span data-stu-id="73fce-289">Greater</span></span>
-   <span data-ttu-id="73fce-290">Implique</span><span class="sxs-lookup"><span data-stu-id="73fce-290">Implies</span></span>
-   <span data-ttu-id="73fce-291">Journal</span><span class="sxs-lookup"><span data-stu-id="73fce-291">Log</span></span>
-   <span data-ttu-id="73fce-292">Max.</span><span class="sxs-lookup"><span data-stu-id="73fce-292">Max</span></span>
-   <span data-ttu-id="73fce-293">Min</span><span class="sxs-lookup"><span data-stu-id="73fce-293">Min</span></span>
-   <span data-ttu-id="73fce-294">Moins</span><span class="sxs-lookup"><span data-stu-id="73fce-294">Minus</span></span>
-   <span data-ttu-id="73fce-295">Plus</span><span class="sxs-lookup"><span data-stu-id="73fce-295">Plus</span></span>
-   <span data-ttu-id="73fce-296">Puissance</span><span class="sxs-lookup"><span data-stu-id="73fce-296">Power</span></span>
-   <span data-ttu-id="73fce-297">Temps</span><span class="sxs-lookup"><span data-stu-id="73fce-297">Times</span></span>
-   <span data-ttu-id="73fce-298">Emplacement</span><span class="sxs-lookup"><span data-stu-id="73fce-298">Slot</span></span>
-   <span data-ttu-id="73fce-299">Modèle</span><span class="sxs-lookup"><span data-stu-id="73fce-299">Model</span></span>
-   <span data-ttu-id="73fce-300">Décision</span><span class="sxs-lookup"><span data-stu-id="73fce-300">Decision</span></span>
-   <span data-ttu-id="73fce-301">Objectif</span><span class="sxs-lookup"><span data-stu-id="73fce-301">Goal</span></span>


<a name="additional-resources"></a><span data-ttu-id="73fce-302">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="73fce-302">Additional resources</span></span>
--------

[<span data-ttu-id="73fce-303">Création d’un contrainte d’expression</span><span class="sxs-lookup"><span data-stu-id="73fce-303">Create an expression constraint</span></span>](tasks/add-expression-constraint-product-configuration-model.md)

[<span data-ttu-id="73fce-304">Ajouter un calcul à un modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="73fce-304">Add a calculation to a product configuration model</span></span>](tasks/add-calculation-product-configuration-model.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]