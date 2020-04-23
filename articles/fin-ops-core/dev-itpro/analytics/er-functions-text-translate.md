---
title: Fonction TRANSLATE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction TRANSLATE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: 415444bda097c00522155d1b37988a79da836902
ms.sourcegitcommit: fb8ad8e2b142441a6530b364f3258bbcc0c724d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201110"
---
# <a name=""></a><span data-ttu-id="5c5f2-103"><a name="TRANSLATE">Fonction TRANSLATE ER</a></span><span class="sxs-lookup"><span data-stu-id="5c5f2-103"><a name="TRANSLATE">TRANSLATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5c5f2-104">La fonction `TRANSLATE` renvoie une valeur *Chaîne* qui contient le résultat du remplacement du caractère du texte spécifié en caractères pour un autre jeu fourni.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-104">The `TRANSLATE` function returns a *String* value that contains the result of the character replacement of specified text in characters of another provided set.</span></span>

## <a name="syntax"></a><span data-ttu-id="5c5f2-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5c5f2-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="5c5f2-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="5c5f2-106">Arguments</span></span>

<span data-ttu-id="5c5f2-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="5c5f2-107">`text`: *String*</span></span>

<span data-ttu-id="5c5f2-108">Chemin d'accès valide d'une source de données du type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="5c5f2-109">`pattern` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="5c5f2-109">`pattern`: *String*</span></span>

<span data-ttu-id="5c5f2-110">Texte qui doit être remplacé.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-110">The text that must be replaced.</span></span>

<span data-ttu-id="5c5f2-111">`replacement` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="5c5f2-111">`replacement`: *String*</span></span>

<span data-ttu-id="5c5f2-112">Texte à utiliser en remplacement.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="5c5f2-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="5c5f2-113">Return values</span></span>

<span data-ttu-id="5c5f2-114">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="5c5f2-114">*String*</span></span>

<span data-ttu-id="5c5f2-115">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5c5f2-116">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="5c5f2-116">Usage notes</span></span>

<span data-ttu-id="5c5f2-117">La fonction `TRANSLATE` remplace un caractère à la fois.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-117">The `TRANSLATE` function replaces one character at a time.</span></span> <span data-ttu-id="5c5f2-118">La fonction remplace le premier caractère de l'argument `text` avec le premier caractère de l'argument `pattern`, puis le deuxième caractère et suit le même flux jusqu'à sa fin.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-118">The function replaces the first character of the `text` argument with the first character of the `pattern` argument and then the second character and follows the same flow until finished.</span></span> <span data-ttu-id="5c5f2-119">Lorsqu'un caractère issu des arguments `text` et `pattern` correspond, il est remplacé par un caractère de l'argument `replacement` qui se trouve dans la même position que le caractère de l'argument `pattern`.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-119">When a character from the `text` and `pattern` arguments match, it is replaced by a character from the `replacement` argument that is located in the same position as the character from the `pattern` argument.</span></span> <span data-ttu-id="5c5f2-120">Si un caractère apparaît plusieurs fois dans l'argument `pattern`, le mappage d'argument `replacement` qui correspond à la première occurrence de ce caractère est utilisé.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-120">If a character appears multiple times in the `pattern` argument, the `replacement` argument mapping that corresponds to the first occurrence of this character is used.</span></span>

## <a name="example-1"></a><span data-ttu-id="5c5f2-121">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="5c5f2-121">Example 1</span></span>

<span data-ttu-id="5c5f2-122">`TRANSLATE ("abcdef", "cd", "GH")` remplace le caractère **« c »** du texte **« abcdef »** avec le caractère **« G »** du texte `replacement` pour les raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="5c5f2-122">`TRANSLATE ("abcdef", "cd", "GH")` replaces the **"c"** character of the specified  **“abcdef”** text with the **"G"** character of the `replacement` text due to the following:</span></span>
-   <span data-ttu-id="5c5f2-123">Le caractère **« c »** est présenté dans le texte `pattern` en première position.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-123">The **"c"** character is presented in the `pattern` text in the first position.</span></span>
-   <span data-ttu-id="5c5f2-124">La première position du texte `replacement` contient le caractère **« G »**.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-124">The first position of the `replacement` text contains the **"G"** character.</span></span>

## <a name="example-2"></a><span data-ttu-id="5c5f2-125">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="5c5f2-125">Example 2</span></span>

<span data-ttu-id="5c5f2-126">`TRANSLATE ("abcdef", "ccd", "GH")` renvoie **« abGdef »**.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-126">`TRANSLATE ("abcdef", "ccd", "GH")` returns **"abGdef"**.</span></span>

## <a name="example-3"></a><span data-ttu-id="5c5f2-127">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="5c5f2-127">Example 3</span></span>

<span data-ttu-id="5c5f2-128">`TRANSLATE ("abccba", "abc", "123")` renvoie **« 123321 »**.</span><span class="sxs-lookup"><span data-stu-id="5c5f2-128">`TRANSLATE ("abccba", "abc", "123")` returns **"123321"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5c5f2-129">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5c5f2-129">Additional resources</span></span>

[<span data-ttu-id="5c5f2-130">Fonctions de texte</span><span class="sxs-lookup"><span data-stu-id="5c5f2-130">Text functions</span></span>](er-functions-category-text.md)
