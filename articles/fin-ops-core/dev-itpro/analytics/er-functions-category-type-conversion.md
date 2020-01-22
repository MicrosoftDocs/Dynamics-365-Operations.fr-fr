---
title: Liste des fonctions ER dans la catégorie de conversion de type
description: Cette rubrique fournit des informations sur les fonctions de conversion prises en charge dans les États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 2cfa5deb3b2c00565759e4334a002bf112f888ac
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917647"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a><span data-ttu-id="001d7-103">Liste des fonctions ER dans la catégorie de conversion de type</span><span class="sxs-lookup"><span data-stu-id="001d7-103">List of ER functions in the type conversion category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="001d7-104">Les fonctions de conversion de type d'état électronique (ER) peuvent être utilisées pour convertir des valeurs entre les types.</span><span class="sxs-lookup"><span data-stu-id="001d7-104">Electronic reporting (ER) type conversion functions can be used to convert values between types.</span></span> <span data-ttu-id="001d7-105">Cette rubrique fournit un résumé de ces fonctions.</span><span class="sxs-lookup"><span data-stu-id="001d7-105">This topic provides a summary of these functions.</span></span>

## <a name="type-conversion-functions"></a><span data-ttu-id="001d7-106">Fonctions de conversion de type</span><span class="sxs-lookup"><span data-stu-id="001d7-106">Type conversion functions</span></span>

| <span data-ttu-id="001d7-107">Fonction</span><span class="sxs-lookup"><span data-stu-id="001d7-107">Function</span></span> | <span data-ttu-id="001d7-108">Description</span><span class="sxs-lookup"><span data-stu-id="001d7-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="001d7-109">Int64Value</span><span class="sxs-lookup"><span data-stu-id="001d7-109">Int64Value</span></span>](er-functions-conversion-int64value.md)   | <span data-ttu-id="001d7-110">Cette fonction renvoie une valeur *Int64* qui représente la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="001d7-110">This function returns an *Int64* value that represents the specified string.</span></span> |
| [<span data-ttu-id="001d7-111">IntValue</span><span class="sxs-lookup"><span data-stu-id="001d7-111">IntValue</span></span>](er-functions-conversion-intvalue.md)       | <span data-ttu-id="001d7-112">Cette fonction renvoie une valeur *Int* qui représente la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="001d7-112">This function returns an *Int* value that represents the specified string.</span></span> |
| [<span data-ttu-id="001d7-113">NumberValue</span><span class="sxs-lookup"><span data-stu-id="001d7-113">NumberValue</span></span>](er-functions-conversion-numbervalue.md) | <span data-ttu-id="001d7-114">Cette fonction renvoie une valeur de *Réel* convertie à partir de la valeur de *Chaîne* spécifiée.</span><span class="sxs-lookup"><span data-stu-id="001d7-114">This function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="001d7-115">Lors de la conversion, les séparateurs de regroupements décimaux et numériques spécifiés sont pris en compte.</span><span class="sxs-lookup"><span data-stu-id="001d7-115">During the conversion, the specified decimal and digit grouping separators are considered.</span></span> |
| [<span data-ttu-id="001d7-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="001d7-116">Value</span></span>](er-functions-conversion-value.md)             | <span data-ttu-id="001d7-117">Cette fonction renvoie une valeur de *Réel* convertie à partir de la valeur de *Chaîne* spécifiée.</span><span class="sxs-lookup"><span data-stu-id="001d7-117">This function returns a *Real* value that is converted from the specified *String* value.</span></span> |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a><span data-ttu-id="001d7-118">Fonctions de conversion de type dans la catégorie de date/heure</span><span class="sxs-lookup"><span data-stu-id="001d7-118">Type conversion functions in the date and time category</span></span>

<span data-ttu-id="001d7-119">Le tableau suivant décrit les fonctions de conversion de type dans la [catégorie de date et d'heure](er-functions-category-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="001d7-119">The following table describes the type conversion functions in the [date and time category](er-functions-category-datetime.md).</span></span>

| <span data-ttu-id="001d7-120">Fonction</span><span class="sxs-lookup"><span data-stu-id="001d7-120">Function</span></span> | <span data-ttu-id="001d7-121">Description</span><span class="sxs-lookup"><span data-stu-id="001d7-121">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="001d7-122">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="001d7-122">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md)   | <span data-ttu-id="001d7-123">Cette fonction renvoie une valeur *DateTime* qui est convertie à partir d'une valeur de *Chaîne* donnée dans le format spécifié et dans une culture spécifiée en option sur une valeur de date/heure.</span><span class="sxs-lookup"><span data-stu-id="001d7-123">This function returns a *DateTime* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="001d7-124">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="001d7-124">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="001d7-125">Cette fonction renvoie une valeur de *DateTime* qui est convertie d'une valeur de *Date* donnée en une valeur de date/heure en temps universel coordonné (Heure de Greenwich, \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="001d7-125">This function returns a *DateTime* value that is converted from a given *Date* value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="001d7-126">DateValue</span><span class="sxs-lookup"><span data-stu-id="001d7-126">DateValue</span></span>](er-functions-datetime-datevalue.md)           | <span data-ttu-id="001d7-127">Cette fonction renvoie une valeur *Date* qui est convertie à partir d'une valeur de *Chaîne* donnée dans le format spécifié et dans une culture spécifiée en option sur une valeur de date.</span><span class="sxs-lookup"><span data-stu-id="001d7-127">This function returns a *Date* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date value.</span></span> |

## <a name="type-conversion-functions-in-the-list-category"></a><span data-ttu-id="001d7-128">Fonctions de conversion de type dans la catégorie de liste</span><span class="sxs-lookup"><span data-stu-id="001d7-128">Type conversion functions in the list category</span></span>

<span data-ttu-id="001d7-129">Le tableau suivant décrit les fonctions de conversion de type dans la [catégorie de liste](er-functions-category-list.md).</span><span class="sxs-lookup"><span data-stu-id="001d7-129">The following table describes the type conversion functions in the [list category](er-functions-category-list.md).</span></span>

| <span data-ttu-id="001d7-130">Fonction</span><span class="sxs-lookup"><span data-stu-id="001d7-130">Function</span></span> | <span data-ttu-id="001d7-131">Description</span><span class="sxs-lookup"><span data-stu-id="001d7-131">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="001d7-132">Liste</span><span class="sxs-lookup"><span data-stu-id="001d7-132">List</span></span>](er-functions-list-list.md)                 | <span data-ttu-id="001d7-133">Cette fonction renvoie une valeur *Liste des enregistrements* comme nouvelle liste créée à partir des arguments spécifiés de type *Conteneur (enregistrement)*.</span><span class="sxs-lookup"><span data-stu-id="001d7-133">This function returns a *Record list* value as a new list that is created from specified arguments of the *Container (record)* type.</span></span> |
| [<span data-ttu-id="001d7-134">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="001d7-134">ListOfFields</span></span>](er-functions-list-listoffields.md) | <span data-ttu-id="001d7-135">Cette fonction renvoie une valeur *Liste des enregistrements* créée en fonction de la structure d'un argument donné du type *Énumération* ou *Conteneur (enregistrement)*.</span><span class="sxs-lookup"><span data-stu-id="001d7-135">This function returns a *Record list* value that is created based on the structure of a given argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="001d7-136">Fractionner</span><span class="sxs-lookup"><span data-stu-id="001d7-136">Split</span></span>](er-functions-list-split.md)               | <span data-ttu-id="001d7-137">Cette fonction fractionne la valeur de *Chaîne* spécifiée en sous-chaînes et renvoie le résultat sous la forme d'une nouvelle valeur de *Liste des enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="001d7-137">This function splits the specified *String* value into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="001d7-138">StringJoin</span><span class="sxs-lookup"><span data-stu-id="001d7-138">StringJoin</span></span>](er-functions-list-stringjoin.md)     | <span data-ttu-id="001d7-139">Cette fonction renvoie une valeur de *Chaîne* composée des valeurs concaténées du champ spécifié dans la valeur *Liste des enregistrements* spécifiée.</span><span class="sxs-lookup"><span data-stu-id="001d7-139">This function returns a *String* value that consists of concatenated values of the specified field from the specified *Record list* value.</span></span> <span data-ttu-id="001d7-140">Les valeurs peuvent être séparées par le séparateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="001d7-140">The values can be separated by the specified delimiter.</span></span> |

## <a name="type-conversion-functions-in-the-text-category"></a><span data-ttu-id="001d7-141">Fonctions de conversion de type dans la catégorie de texte</span><span class="sxs-lookup"><span data-stu-id="001d7-141">Type conversion functions in the text category</span></span>

<span data-ttu-id="001d7-142">Le tableau suivant décrit les fonctions de conversion de type dans la [catégorie de texte](er-functions-category-text.md).</span><span class="sxs-lookup"><span data-stu-id="001d7-142">The following table describes the type conversion functions in the [text category](er-functions-category-text.md).</span></span>

| <span data-ttu-id="001d7-143">Fonction</span><span class="sxs-lookup"><span data-stu-id="001d7-143">Function</span></span> | <span data-ttu-id="001d7-144">Description</span><span class="sxs-lookup"><span data-stu-id="001d7-144">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="001d7-145">Char</span><span class="sxs-lookup"><span data-stu-id="001d7-145">Char</span></span>](er-functions-text-char.md)                 | <span data-ttu-id="001d7-146">Cette fonction renvoie une valeur de *Chaîne* qui représente un seul caractère référencé par le numéro Unicode spécifié.</span><span class="sxs-lookup"><span data-stu-id="001d7-146">This function returns a *String* value that represents a single character that is referenced by the specified Unicode number.</span></span> |
| [<span data-ttu-id="001d7-147">GuidValue</span><span class="sxs-lookup"><span data-stu-id="001d7-147">GuidValue</span></span>](er-functions-text-guidvalue.md)       | <span data-ttu-id="001d7-148">Cette fonction convertit l'entrée spécifiée du type *Chaîne* en un élément de données du type *GUID*.</span><span class="sxs-lookup"><span data-stu-id="001d7-148">This function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span> |
| [<span data-ttu-id="001d7-149">NumberFormat</span><span class="sxs-lookup"><span data-stu-id="001d7-149">NumberFormat</span></span>](er-functions-text-numberformat.md) | <span data-ttu-id="001d7-150">Cette fonction renvoie une valeur de *Chaîne* qui représente le nombre spécifié dans le format spécifié et dans une culture éventuellement spécifiée.</span><span class="sxs-lookup"><span data-stu-id="001d7-150">This function returns a *String* value that represents the specified number in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="001d7-151">QrCode</span><span class="sxs-lookup"><span data-stu-id="001d7-151">QrCode</span></span>](er-functions-text-qrcode.md)             | <span data-ttu-id="001d7-152">Cette fonction renvoie une valeur de *Conteneur* qui présente l'une image de code à réponse rapide (code QR) de la chaîne spécifiée au format binaire.</span><span class="sxs-lookup"><span data-stu-id="001d7-152">This function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span> |
| [<span data-ttu-id="001d7-153">Détails</span><span class="sxs-lookup"><span data-stu-id="001d7-153">Text</span></span>](er-functions-text-text.md)                 | <span data-ttu-id="001d7-154">Cette fonction renvoie une valeur de *Chaîne* qui représente le nombre spécifié une fois qu'elle a été convertie en une chaîne de texte qui est mise en forme en fonction des paramètres régionaux du serveur de l'instance d'application actuelle.</span><span class="sxs-lookup"><span data-stu-id="001d7-154">This function returns a *String* value that represents the specified number after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="001d7-155">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="001d7-155">Additional resources</span></span>

[<span data-ttu-id="001d7-156">Vue d'ensemble des États électroniques</span><span class="sxs-lookup"><span data-stu-id="001d7-156">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="001d7-157">Concepteur de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="001d7-157">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="001d7-158">Langage de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="001d7-158">Electronic reporting formula language</span></span>](er-formula-language.md)