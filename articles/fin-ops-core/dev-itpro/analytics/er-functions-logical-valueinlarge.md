---
title: Fonctions VALUEINLARGE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction VALUEINLARGE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 08/17/2020
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
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 1e35c695d697e0d0f42baeaf568548273f9d205b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565806"
---
# <a name="valueinlarge-er-function"></a><span data-ttu-id="44b8c-103">Fonctions VALUEINLARGE ER</span><span class="sxs-lookup"><span data-stu-id="44b8c-103">VALUEINLARGE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="44b8c-104">La fonction `VALUEINLARGE` détermine si l’entrée spécifiée de type *Int64* ou *Entier* correspond à une valeur quelconque d’un article donné dans la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="44b8c-104">The `VALUEINLARGE` function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="44b8c-105">La fonction renvoie une *Booléenne* de **TRUE** si l’entrée spécifiée correspond au résultat de l’exécution de l’expression spécifiée pour au moins un enregistrement de la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="44b8c-105">The function returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="44b8c-106">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="44b8c-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> <span data-ttu-id="44b8c-107">Pour comprendre la différence avec la fonction `VALUEIN`, voir la section [Note d’utilisation](#usage_note) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="44b8c-107">To understand the difference with the `VALUEIN` function, see the [Usage note](#usage_note) section later in this topic.</span></span>

## <a name="syntax"></a><span data-ttu-id="44b8c-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="44b8c-108">Syntax</span></span>

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="44b8c-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="44b8c-109">Arguments</span></span>

<span data-ttu-id="44b8c-110">`input` : *Champ*</span><span class="sxs-lookup"><span data-stu-id="44b8c-110">`input`: *Field*</span></span>

<span data-ttu-id="44b8c-111">Chemin d’accès valide d’un élément de la source de données du type *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="44b8c-111">The valid path of a data source item of the *Record list* type.</span></span> <span data-ttu-id="44b8c-112">La valeur de cet article est mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="44b8c-112">The value of this item will be matched.</span></span>

<span data-ttu-id="44b8c-113">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="44b8c-113">`list`: *Record list*</span></span>

<span data-ttu-id="44b8c-114">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="44b8c-114">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="44b8c-115">`list item expression` : *Expression*</span><span class="sxs-lookup"><span data-stu-id="44b8c-115">`list item expression`: *Expression*</span></span>

<span data-ttu-id="44b8c-116">Expression conditionnelle valide qui indique ou contient un champ unique de la liste spécifiée à utiliser pour la mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="44b8c-116">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="44b8c-117">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="44b8c-117">Return values</span></span>

<span data-ttu-id="44b8c-118">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="44b8c-118">*Boolean*</span></span>

<span data-ttu-id="44b8c-119">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="44b8c-119">The resulting *Boolean* value.</span></span>

## <a name=""></a><span data-ttu-id="44b8c-120"><a name="usage_note">Notes d’utilisation</a></span><span class="sxs-lookup"><span data-stu-id="44b8c-120"><a name="usage_note">Usage notes</a></span></span>

<span data-ttu-id="44b8c-121">Lorsque l’entrée spécifiée représente un type d’un élément de la source de données *Int64* ou *Entier* dont l’appel est traduisible en instruction SQL directe, la liste spécifiée est convertie en table SQL temporaire et la mise en correspondance est effectuée dans la base de données en exécutant une seule requête `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="44b8c-121">When the specified input represents an *Int64* or *Integer* type of a data source item, the call to which is translatable to a direct SQL statement, the specified list is converted to a temporary SQL table and matching is performed in the database by executing a single `EXISTS JOIN` query.</span></span> <span data-ttu-id="44b8c-122">Sinon, cette fonction fonctionne comme la fonction [`VALUEIN`](er-functions-logical-valuein.md).</span><span class="sxs-lookup"><span data-stu-id="44b8c-122">Otherwise, this function works as the [`VALUEIN`](er-functions-logical-valuein.md) function.</span></span>

<span data-ttu-id="44b8c-123">Lorsque l’entrée spécifiée représente un élément de source de données conçu comme un élément autre que de type *Int64* et *Entier*, une erreur se produit au moment de la conception pour vous informer que la fonction `VALUEINLARGE` n’est pas applicable pour l’expression ER configurée.</span><span class="sxs-lookup"><span data-stu-id="44b8c-123">When the specified input represents a data source item that is designed as an item other than *Int64* and *Integer* type, an error occurs at design time informing you that the `VALUEINLARGE` function is not applicable for the configured ER expression.</span></span>

<span data-ttu-id="44b8c-124">Quand l’expression de la fonction `VALUEINLARGE` est exécutée et que plus d’une table temporaire est utilisée dans le cadre de cette exécution, une erreur d’exécution se produit.</span><span class="sxs-lookup"><span data-stu-id="44b8c-124">When the `VALUEINLARGE` function expression is executed and more than one temporary table is used in scope of this execution, a runtime error occurs.</span></span>

## <a name="example"></a><span data-ttu-id="44b8c-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="44b8c-125">Example</span></span>

<span data-ttu-id="44b8c-126">Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :</span><span class="sxs-lookup"><span data-stu-id="44b8c-126">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="44b8c-127">Source de données **In** du type *Enregistrements de la table*.</span><span class="sxs-lookup"><span data-stu-id="44b8c-127">The **In** data source of the *Table records* type.</span></span>
    - <span data-ttu-id="44b8c-128">Cette source de données fait référence à la table **Déclaration d’échanges de biens**.</span><span class="sxs-lookup"><span data-stu-id="44b8c-128">This data source refers to the **Intrastat** table.</span></span>
    - <span data-ttu-id="44b8c-129">L’option **Intersociétés** est définie sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="44b8c-129">The **Cross-company** option is set to **No**.</span></span>
- <span data-ttu-id="44b8c-130">Source de données **InMemory** du type *Champ calculé*.</span><span class="sxs-lookup"><span data-stu-id="44b8c-130">The **InMemory** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="44b8c-131">Cette source de données contient l’expression `WHERE (In, In.Port <> "")`.</span><span class="sxs-lookup"><span data-stu-id="44b8c-131">This data source contains the expression `WHERE (In, In.Port <> "")`.</span></span>
- <span data-ttu-id="44b8c-132">Source de données **InFiltered** du type *Champ calculé*.</span><span class="sxs-lookup"><span data-stu-id="44b8c-132">The **InFiltered** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="44b8c-133">Cette source de données contient l’expression `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span><span class="sxs-lookup"><span data-stu-id="44b8c-133">This data source contains the expression `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span></span>

<span data-ttu-id="44b8c-134">Lorsque la source de données **InFiltered** est appelée dans le contexte de l’entreprise **DEMF**, une table temporaire est créée dans la base de données de l’application, la liste des codes d’identification d’enregistrement collectée en mémoire est insérée dans cette table et l’instruction SQL suivante est générée pour renvoyer les enregistrements filtrés de la table **Déclaration d’échanges de biens**.</span><span class="sxs-lookup"><span data-stu-id="44b8c-134">When the data source **InFiltered** is called under the context of the company **DEMF**, a new temporary table is created in the application database, the collected in memory list of record identification codes are inserted to this table, and the following SQL statement is generated to return filtered records of the **Intrastat** table.</span></span>

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a><span data-ttu-id="44b8c-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="44b8c-135">Additional resources</span></span>

[<span data-ttu-id="44b8c-136">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="44b8c-136">Logical functions</span></span>](er-functions-category-logical.md)

[<span data-ttu-id="44b8c-137">Fonction VALUEIN</span><span class="sxs-lookup"><span data-stu-id="44b8c-137">VALUEIN functions</span></span>](er-functions-logical-valuein.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]