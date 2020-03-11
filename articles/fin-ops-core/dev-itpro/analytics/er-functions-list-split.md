---
title: Fonction SPLIT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction SPLIT États électroniques (ER).
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
ms.openlocfilehash: 52a89f744cd37c543294522cc706ae7f47660e75
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070619"
---
# <span data-ttu-id="03848-103"><a name="SPLIT">Fonction SPLIT ER</a></span><span class="sxs-lookup"><span data-stu-id="03848-103"><a name="SPLIT">SPLIT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03848-104">La fonction `SPLIT` fractionne la chaîne d'entrée spécifiée en sous-chaînes et renvoie le résultat sous la forme d'une nouvelle valeur de *Liste des enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="03848-104">The `SPLIT` function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="03848-105">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="03848-105">Syntax 1</span></span>

```vb
SPLIT (input, length)
```

<span data-ttu-id="03848-106">Cette syntaxe permet de fractionner la chaîne d'entrée spécifiée en sous-chaînes, dans la longueur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="03848-106">This syntax is used to split the specified input string into substrings, each of which has the specified length.</span></span>

## <a name="syntax-2"></a><span data-ttu-id="03848-107">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="03848-107">Syntax 2</span></span>

```vb
SPLIT (input, delimiter)
```

<span data-ttu-id="03848-108">Cette syntaxe permet de fractionner la chaîne d'entrée spécifiée en sous-chaînes, en fonction du délimiteur spécifié.</span><span class="sxs-lookup"><span data-stu-id="03848-108">This syntax is used to split the specified input string into substrings, based on the specified delimiter.</span></span>

## <a name="arguments"></a><span data-ttu-id="03848-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="03848-109">Arguments</span></span>

<span data-ttu-id="03848-110">`input` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="03848-110">`input`: *String*</span></span>

<span data-ttu-id="03848-111">Texte à fractionner.</span><span class="sxs-lookup"><span data-stu-id="03848-111">The text to split.</span></span>

<span data-ttu-id="03848-112">`length` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="03848-112">`length`: *Integer*</span></span>

<span data-ttu-id="03848-113">Longueur maximale d'une seule sous-chaîne.</span><span class="sxs-lookup"><span data-stu-id="03848-113">The maximum length of a single substring.</span></span>

<span data-ttu-id="03848-114">`delimiter` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="03848-114">`delimiter`: *String*</span></span>

<span data-ttu-id="03848-115">Délimiteur utilisé pour séparer les sous-chaînes.</span><span class="sxs-lookup"><span data-stu-id="03848-115">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="03848-116">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="03848-116">Return values</span></span>

<span data-ttu-id="03848-117">*Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="03848-117">*Record list*</span></span>

<span data-ttu-id="03848-118">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="03848-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="03848-119">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="03848-119">Usage notes</span></span>

<span data-ttu-id="03848-120">La structure d'enregistrement de la liste renvoyée se compose du champ **Valeur** de type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="03848-120">The record structure of the list that is returned consists of the **Value** field of the *String* type.</span></span> <span data-ttu-id="03848-121">Chaque enregistrement de la liste renvoyé contient des sous-chaînes générées dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="03848-121">Every record of the list that is returned contains generated substrings in this field.</span></span>

<span data-ttu-id="03848-122">Si l'argument `delimiter` est vide, la nouvelle liste qui est retournée est composée d'un enregistrement avec un champ **Valeur** de type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="03848-122">If the `delimiter` argument is empty, the new list that is returned consists of one record that has the **Value** field of the *String* type.</span></span> <span data-ttu-id="03848-123">Ce champ contient le texte saisi.</span><span class="sxs-lookup"><span data-stu-id="03848-123">This field contains the input text.</span></span>

<span data-ttu-id="03848-124">Si l'argument `input` est vide, une nouvelle liste vide est retournée.</span><span class="sxs-lookup"><span data-stu-id="03848-124">If the `input` argument is empty, a new empty list is returned.</span></span> <span data-ttu-id="03848-125">Si l'argument `input` ou `delimiter` n'est pas spécifié (null), une exception d'application est levée.</span><span class="sxs-lookup"><span data-stu-id="03848-125">If either the `input` or `delimiter` argument is unspecified (null), an application exception is thrown.</span></span>

## <a name="example-1"></a><span data-ttu-id="03848-126">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="03848-126">Example 1</span></span>

<span data-ttu-id="03848-127">`SPLIT ("abcd", 3)` renvoie une liste composée de deux enregistrements avec un champ **Valeur** de type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="03848-127">`SPLIT ("abcd", 3)` returns a new list that consists of two records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="03848-128">Le champ **Valeur** du premier enregistrement contient le texte **"abc"**, et le champ **Valeur** du deuxième enregistrement contient le texte **"d"**.</span><span class="sxs-lookup"><span data-stu-id="03848-128">The **Value** field in the first record contains the text **"abc"**, and the **Value** field in the second record contains the text **"d"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="03848-129">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="03848-129">Example 2</span></span>

<span data-ttu-id="03848-130">`SPLIT ("XAb aBy", "aB")` renvoie une liste composée de trois enregistrements avec un champ **Valeur** de type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="03848-130">`SPLIT ("XAb aBy", "aB")` returns a new list that consists of three records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="03848-131">Le champ **Valeur** dans le premier enregistrement contient le texte **"X"**, le champ **Valeur** du deuxième enregistrement contient le texte **"&nbsp;"** et le champ **Valeur** dans le troisième enregistrement contient le texte **"y"**.</span><span class="sxs-lookup"><span data-stu-id="03848-131">The **Value** field in the first record contains the text **"X"**, the **Value** field in the second record contains the text **"&nbsp;"**, and the **Value** field in the third record contains the text **"y"**.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="03848-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="03848-132">Additional resources</span></span>

[<span data-ttu-id="03848-133">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="03848-133">List functions</span></span>](er-functions-category-list.md)
