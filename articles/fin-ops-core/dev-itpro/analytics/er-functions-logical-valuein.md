---
title: Fonction VALUEIN ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction VALUEIN États électroniques (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: e5a0ac314a61abce610407550e65479cbf5a6b5b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565830"
---
# <a name="valuein-er-function"></a><span data-ttu-id="1b5d9-103">Fonction VALUEIN ER</span><span class="sxs-lookup"><span data-stu-id="1b5d9-103">VALUEIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1b5d9-104">La fonction `VALUEIN` détermine si l’entrée spécifiée correspond à une valeur quelconque d’un article donné dans la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-104">The `VALUEIN` function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="1b5d9-105">Elle renvoie une *Booléenne* de **TRUE** si l’entrée spécifiée correspond au résultat de l’exécution de l’expression spécifiée pour au moins un enregistrement de la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-105">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="1b5d9-106">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="1b5d9-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1b5d9-107">Syntax</span></span>

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="1b5d9-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="1b5d9-108">Arguments</span></span>

<span data-ttu-id="1b5d9-109">`input` : *Champ*</span><span class="sxs-lookup"><span data-stu-id="1b5d9-109">`input`: *Field*</span></span>

<span data-ttu-id="1b5d9-110">Chemin d’accès valide d’un élément d’une source de données du *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-110">The valid path of an item of a data source of the *Record list* type.</span></span> <span data-ttu-id="1b5d9-111">La valeur de cet article est mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-111">The value of this item will be matched.</span></span>

<span data-ttu-id="1b5d9-112">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="1b5d9-112">`list`: *Record list*</span></span>

<span data-ttu-id="1b5d9-113">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-113">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="1b5d9-114">`list item expression` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="1b5d9-114">`list item expression`: *Boolean*</span></span>

<span data-ttu-id="1b5d9-115">Expression conditionnelle valide qui indique ou contient un champ unique de la liste spécifiée à utiliser pour la mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-115">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="1b5d9-116">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="1b5d9-116">Return values</span></span>

<span data-ttu-id="1b5d9-117">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="1b5d9-117">*Boolean*</span></span>

<span data-ttu-id="1b5d9-118">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-118">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1b5d9-119">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="1b5d9-119">Usage notes</span></span>

<span data-ttu-id="1b5d9-120">En général la fonction `VALUEIN` est traduite en un ensemble de conditions **OR**.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-120">In general, the `VALUEIN` function is translated to a set of **OR** conditions.</span></span> <span data-ttu-id="1b5d9-121">Si la liste des conditions **OR** est grande et la longueur totale maximale d’une instruction SQL peut être dépassée, pensez à utiliser la fonction [`VALUEINLARGE`](er-functions-logical-valueinlarge.md).</span><span class="sxs-lookup"><span data-stu-id="1b5d9-121">If the list of **OR** conditions is large and the maximum total length of an SQL statement might be exceeded, consider using the [`VALUEINLARGE`](er-functions-logical-valueinlarge.md) function.</span></span>

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

<span data-ttu-id="1b5d9-122">Dans certains cas, elle peut être convertie en une instruction SQL de base de données à l’aide de l’opérateur `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-122">In some cases, it can be translated to a database SQL statement by using the `EXISTS JOIN` operator.</span></span>

## <a name="example-1"></a><span data-ttu-id="1b5d9-123">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="1b5d9-123">Example 1</span></span>

<span data-ttu-id="1b5d9-124">Dans votre modèle de mise en correspondance, vous définissez la source de données **Liste** de type *Champ calculé*.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-124">In your model mapping, you define the **List** data source of the *Calculated field* type.</span></span> <span data-ttu-id="1b5d9-125">Cette source de données contient l’expression `SPLIT ("a,b,c", ",")`.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-125">This data source contains the expression `SPLIT ("a,b,c", ",")`.</span></span>

<span data-ttu-id="1b5d9-126">Lorsqu’une source de données est appelée, si elle a été configurée comme l’expression `VALUEIN ("B", List, List.Value)`, elle renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-126">When a data source is called, if it has been configured as the `VALUEIN ("B", List, List.Value)` expression, it returns **TRUE**.</span></span> <span data-ttu-id="1b5d9-127">Dans ce cas, la fonction `VALUEIN` est traduite en l’ensemble de conditions suivant : `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, où `("B" = "b")` est égal à **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-127">In this case, the `VALUEIN` function is translated to the following set of conditions: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, where `("B" = "b")` equals **TRUE**.</span></span>

<span data-ttu-id="1b5d9-128">Lorsqu’une source de données est appelée, si elle a été configurée comme l’expression `VALUEIN ("B", List, LEFT(List.Value, 0))`, elle renvoie **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-128">When a data source is called, if it has been configured as the `VALUEIN ("B", List, LEFT(List.Value, 0))` expression, it returns **FALSE**.</span></span> <span data-ttu-id="1b5d9-129">Dans ce cas, la fonction `VALUEIN` est traduite en l’ensemble de conditions suivant : `("B" = "")`, qui n’est pas égal à **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-129">In this case, the `VALUEIN` function is translated to the following condition: `("B" = "")`, which doesn't equal **TRUE**.</span></span>

<span data-ttu-id="1b5d9-130">La limite supérieure du nombre de caractères dans le texte d’une telle condition est de 32 768 caractères.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-130">The upper limit for the number of characters in the text of such a condition is 32,768 characters.</span></span> <span data-ttu-id="1b5d9-131">Par conséquent, vous ne devez pas créer de sources de données susceptibles de dépasser cette limite au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-131">Therefore, you should not create data sources that might exceed this limit at runtime.</span></span> <span data-ttu-id="1b5d9-132">Si la limite est dépassée, l’application arrête de s’exécuter, et une exception est levée.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-132">If the limit is exceeded, the application stops running, and an exception is thrown.</span></span> <span data-ttu-id="1b5d9-133">Par exemple, cette situation peut se produire si la source de données est configurée comme `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, et les listes **List1** et **List2** contiennent un grand nombre d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-133">For example, this situation can occur if the data source is configured as `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, and the **List1** and **List2** lists contain a large volume of records.</span></span>

<span data-ttu-id="1b5d9-134">Dans certains cas, la fonction `VALUEIN` est traduite en une instruction de base de données à l’aide de l’opérateur `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-134">In some cases, the `VALUEIN` function is translated to a database statement by using the `EXISTS JOIN` operator.</span></span> <span data-ttu-id="1b5d9-135">Ce comportement se produit lorsque la fonction [`FILTER`](er-functions-list-filter.md) est utilisée et que les conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="1b5d9-135">This behavior occurs when the [`FILTER`](er-functions-list-filter.md) function is used and the following conditions are met:</span></span>

- <span data-ttu-id="1b5d9-136">L’option **DEMANDER UNE REQUÊTE** est désactivée pour la source de données de la fonction `VALUEIN` qui fait référence à la liste d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-136">The **ASK FOR QUERY** option is turned off for the data source of the `VALUEIN` function that refers to the list of records.</span></span> <span data-ttu-id="1b5d9-137">Aucune condition supplémentaire n’est appliquée à cette source de données au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-137">No additional conditions will be applied to this data source at runtime.</span></span>
- <span data-ttu-id="1b5d9-138">Aucune expression imbriquée n’est configurée pour la source de données de la fonction `VALUEIN` qui fait référence à la liste d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-138">No nested expressions are configured for the data source of the `VALUEIN` function that refers to the list of records.</span></span>
- <span data-ttu-id="1b5d9-139">Un élément de liste de la fonction `VALUEIN` fait référence à un champ, pas à une expression ou à une méthode de la source de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-139">A list item of the `VALUEIN` function refers to a field of the specified data source, not to an expression or method of that data source.</span></span>

<span data-ttu-id="1b5d9-140">Envisagez d’utiliser cette option au lieu de la fonction [`WHERE`](er-functions-list-where.md) comme décrit précédemment dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-140">Consider using this option instead of the [`WHERE`](er-functions-list-where.md) function that is described earlier in this example.</span></span>

## <a name="example-2"></a><span data-ttu-id="1b5d9-141">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="1b5d9-141">Example 2</span></span>

<span data-ttu-id="1b5d9-142">Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :</span><span class="sxs-lookup"><span data-stu-id="1b5d9-142">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="1b5d9-143">Source de données **In** du type *Enregistrements de la table*.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-143">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="1b5d9-144">Cette source de données fait référence à la table Intrastat.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-144">This data source refers to the Intrastat table.</span></span>
- <span data-ttu-id="1b5d9-145">Source de données **Port** du type *Enregistrements de la table*.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-145">The **Port** data source of the *Table records* type.</span></span> <span data-ttu-id="1b5d9-146">Cette source de données fait référence à la table IntrastatPort.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-146">This data source refers to the IntrastatPort table.</span></span>

<span data-ttu-id="1b5d9-147">Lorsqu’une source de données est appelée qui est configurée comme l’expression `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)`, l’instruction SQL suivante est générée pour retourner les enregistrements filtrés de la table Intrastat.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-147">When a data source is called that has been configured as the `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` expression, the following SQL statement is generated to return filtered records of the Intrastat table.</span></span>

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

<span data-ttu-id="1b5d9-148">Pour les champs **dataAreaId**, l’instruction SQL finale est générée en utilisant l’opérateur `IN`.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-148">For **dataAreaId** fields, the final SQL statement is generated by the using `IN` operator.</span></span>

## <a name="example-3"></a><span data-ttu-id="1b5d9-149">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="1b5d9-149">Example 3</span></span>

<span data-ttu-id="1b5d9-150">Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :</span><span class="sxs-lookup"><span data-stu-id="1b5d9-150">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="1b5d9-151">Source de données **Le** du type *Champ calculé*.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-151">The **Le** data source of the *Calculated field* type.</span></span> <span data-ttu-id="1b5d9-152">Cette source de données contient l’expression `SPLIT ("DEMF,GBSI,USMF", ",")`.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-152">This data source contains the expression `SPLIT ("DEMF,GBSI,USMF", ",")`.</span></span>
- <span data-ttu-id="1b5d9-153">Source de données **In** du type *Enregistrements de la table*.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-153">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="1b5d9-154">Cette source de données fait référence à la table Intrastat et l’option **Intersociétés** est activée pour cela.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-154">This data source refers to the Intrastat table, and the **Cross-company** option is turned on for it.</span></span>

<span data-ttu-id="1b5d9-155">Lorsqu’une source de données est appelée qui est configurée comme expression `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)`, l’instruction SQL finale contient la condition suivante.</span><span class="sxs-lookup"><span data-stu-id="1b5d9-155">When a data source is called that has been configured as the `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` expression, the final SQL statement contains the following condition.</span></span>

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a><span data-ttu-id="1b5d9-156">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1b5d9-156">Additional resources</span></span>

[<span data-ttu-id="1b5d9-157">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="1b5d9-157">Logical functions</span></span>](er-functions-category-logical.md)

[<span data-ttu-id="1b5d9-158">Fonctions VALUEINLARGE</span><span class="sxs-lookup"><span data-stu-id="1b5d9-158">VALUEINLARGE functions</span></span>](er-functions-logical-valueinlarge.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]