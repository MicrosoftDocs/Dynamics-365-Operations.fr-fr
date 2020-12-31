---
title: Fonction REPLACE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction REPLACE États électroniques (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3c9d3b6748ecb1680586a2d47a425b5ef98551f1
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682916"
---
# <a name="replace-er-function"></a><span data-ttu-id="b78a0-103">Fonction REPLACE ER</span><span class="sxs-lookup"><span data-stu-id="b78a0-103">REPLACE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b78a0-104">La fonction `REPLACE` renvoie la chaîne de texte spécifiée sous la forme d’une valeur de *Chaîne* après que tout ou partie de celui-ci a été remplacé par une autre chaîne.</span><span class="sxs-lookup"><span data-stu-id="b78a0-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="b78a0-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b78a0-105">Syntax</span></span>

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="b78a0-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="b78a0-106">Arguments</span></span>

<span data-ttu-id="b78a0-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b78a0-107">`text`: *String*</span></span>

<span data-ttu-id="b78a0-108">Chemin d’accès valide d’une source de données du type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="b78a0-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="b78a0-109">`pattern` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b78a0-109">`pattern`: *String*</span></span>

<span data-ttu-id="b78a0-110">Si l’argument `regular expression flag` est **FALSE**, cet argument contient le texte qui doit être remplacé.</span><span class="sxs-lookup"><span data-stu-id="b78a0-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="b78a0-111">Si l’argument `regular expression flag` est **TRUE**, cet argument contient une expression régulière qui définit à la fois un modèle de recherche et le texte de remplacement.</span><span class="sxs-lookup"><span data-stu-id="b78a0-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="b78a0-112">`replacement` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b78a0-112">`replacement`: *String*</span></span>

<span data-ttu-id="b78a0-113">Si l’argument `regular expression flag` est **FALSE**, cet argument contient le texte à utiliser comme remplacement.</span><span class="sxs-lookup"><span data-stu-id="b78a0-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="b78a0-114">Si l’argument `regular expression flag` est **TRUE**, cet argument n’est pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="b78a0-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="b78a0-115">`regular expression flag` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="b78a0-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="b78a0-116">Valeur *Booléenne* qui indique si une expression régulière est utilisée pour effectuer le remplacement.</span><span class="sxs-lookup"><span data-stu-id="b78a0-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="b78a0-117">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="b78a0-117">Return values</span></span>

<span data-ttu-id="b78a0-118">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b78a0-118">*String*</span></span>

<span data-ttu-id="b78a0-119">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="b78a0-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b78a0-120">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="b78a0-120">Usage notes</span></span>

<span data-ttu-id="b78a0-121">Si l’argument `regular expression flag` est **TRUE**, cette fonction renvoie la chaîne spécifiée après sa modification en appliquant l’expression régulière spécifiée par l’argument `pattern`.</span><span class="sxs-lookup"><span data-stu-id="b78a0-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="b78a0-122">L’expression régulière est utilisée pour rechercher les caractères qui doivent être remplacés.</span><span class="sxs-lookup"><span data-stu-id="b78a0-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="b78a0-123">Si l’argument `regular expression flag` est **FALSE**, cette fonction renvoie une chaîne spécifique après que l’ensemble de caractères définis dans l’argument `pattern` ait été remplacé par les caractères de l’argument `replacement`.</span><span class="sxs-lookup"><span data-stu-id="b78a0-123">If the `regular expression flag` argument is **FALSE**, this function returns the specified string after the set of characters that are defined in the `pattern` argument have been replaced by characters of the `replacement` argument.</span></span> 

## <a name="example-1"></a><span data-ttu-id="b78a0-124">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="b78a0-124">Example 1</span></span>

<span data-ttu-id="b78a0-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applique une expression régulière qui supprime tous les symboles non-numériques, et renvoie **"19234564971"**.</span><span class="sxs-lookup"><span data-stu-id="b78a0-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="b78a0-126">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="b78a0-126">Example 2</span></span>

<span data-ttu-id="b78a0-127">`REPLACE ("abcdef", "cd", "GH", false)` remplace le modèle **cd** par la chaîne **« GH »** et renvoie **abGHef**.</span><span class="sxs-lookup"><span data-stu-id="b78a0-127">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b78a0-128">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b78a0-128">Additional resources</span></span>

[<span data-ttu-id="b78a0-129">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="b78a0-129">Text functions</span></span>](er-functions-category-text.md)
