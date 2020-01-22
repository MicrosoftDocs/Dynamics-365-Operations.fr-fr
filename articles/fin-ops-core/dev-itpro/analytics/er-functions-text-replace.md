---
title: Fonction REPLACE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction REPLACE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: d9c66f4c96f35e3ad5fc92e7925b5cd07c956aac
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916865"
---
# <span data-ttu-id="c2b96-103"><a name="REPLACE">Fonction REPLACE ER</a></span><span class="sxs-lookup"><span data-stu-id="c2b96-103"><a name="REPLACE">REPLACE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c2b96-104">La fonction `REPLACE` renvoie la chaîne de texte spécifiée sous la forme d'une valeur de *Chaîne* après que tout ou partie de celui-ci a été remplacé par une autre chaîne.</span><span class="sxs-lookup"><span data-stu-id="c2b96-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="c2b96-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c2b96-105">Syntax</span></span>

```
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="c2b96-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="c2b96-106">Arguments</span></span>

<span data-ttu-id="c2b96-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="c2b96-107">`text`: *String*</span></span>

<span data-ttu-id="c2b96-108">Chemin d'accès valide d'une source de données du type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="c2b96-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="c2b96-109">`pattern` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="c2b96-109">`pattern`: *String*</span></span>

<span data-ttu-id="c2b96-110">Si l'argument `regular expression flag` est **FALSE**, cet argument contient le texte qui doit être remplacé.</span><span class="sxs-lookup"><span data-stu-id="c2b96-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="c2b96-111">Si l'argument `regular expression flag` est **TRUE**, cet argument contient une expression régulière qui définit à la fois un modèle de recherche et le texte de remplacement.</span><span class="sxs-lookup"><span data-stu-id="c2b96-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="c2b96-112">`replacement` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="c2b96-112">`replacement`: *String*</span></span>

<span data-ttu-id="c2b96-113">Si l'argument `regular expression flag` est **FALSE**, cet argument contient le texte à utiliser comme remplacement.</span><span class="sxs-lookup"><span data-stu-id="c2b96-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="c2b96-114">Si l'argument `regular expression flag` est **TRUE**, cet argument n'est pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="c2b96-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="c2b96-115">`regular expression flag` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="c2b96-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="c2b96-116">Valeur *Booléenne* qui indique si une expression régulière est utilisée pour effectuer le remplacement.</span><span class="sxs-lookup"><span data-stu-id="c2b96-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="c2b96-117">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="c2b96-117">Return values</span></span>

<span data-ttu-id="c2b96-118">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="c2b96-118">*String*</span></span>

<span data-ttu-id="c2b96-119">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="c2b96-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c2b96-120">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="c2b96-120">Usage notes</span></span>

<span data-ttu-id="c2b96-121">Si l'argument `regular expression flag` est **TRUE**, cette fonction renvoie la chaîne spécifiée après sa modification en appliquant l'expression régulière spécifiée par l'argument `pattern`.</span><span class="sxs-lookup"><span data-stu-id="c2b96-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="c2b96-122">L'expression régulière est utilisée pour rechercher les caractères qui doivent être remplacés.</span><span class="sxs-lookup"><span data-stu-id="c2b96-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="c2b96-123">Si l'argument `regular expression flag` est **FALSE**, cette fonction se comporte comme [TRANSLATE](er-functions-text-translate.md).</span><span class="sxs-lookup"><span data-stu-id="c2b96-123">If the `regular expression flag` argument is **FALSE**, this function behaves like [TRANSLATE](er-functions-text-translate.md).</span></span> <span data-ttu-id="c2b96-124">Les caractères spécifiés par l'argument `replacement` sont utilisés pour remplacer les caractères qui sont recherchés.</span><span class="sxs-lookup"><span data-stu-id="c2b96-124">The characters that are specified by the `replacement` argument are used to replace the characters that are found.</span></span> 

## <a name="example-1"></a><span data-ttu-id="c2b96-125">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="c2b96-125">Example 1</span></span>

<span data-ttu-id="c2b96-126">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applique une expression régulière qui supprime tous les symboles non-numériques, et renvoie **"19234564971"**.</span><span class="sxs-lookup"><span data-stu-id="c2b96-126">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="c2b96-127">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="c2b96-127">Example 2</span></span>

<span data-ttu-id="c2b96-128">`REPLACE ("abcdef", "cd", "GH", false)` remplace le modèle **cd** par la chaîne **« GH »** et renvoie **abGHef**.</span><span class="sxs-lookup"><span data-stu-id="c2b96-128">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c2b96-129">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c2b96-129">Additional resources</span></span>

[<span data-ttu-id="c2b96-130">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="c2b96-130">Text functions</span></span>](er-functions-category-text.md)
