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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eb2d4ab3434a563e907f6540809888cd3f671c1a
ms.sourcegitcommit: fcc4596eeadac5dfe9a3242afa49b9b1c0c96575
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2020
ms.locfileid: "4740806"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a><span data-ttu-id="6d759-103">Liste des fonctions ER dans la catégorie de conversion de type</span><span class="sxs-lookup"><span data-stu-id="6d759-103">List of ER functions in the type conversion category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6d759-104">Les fonctions de conversion de type d’état électronique (ER) peuvent être utilisées pour convertir des valeurs entre les types.</span><span class="sxs-lookup"><span data-stu-id="6d759-104">Electronic reporting (ER) type conversion functions can be used to convert values between types.</span></span> <span data-ttu-id="6d759-105">Cette rubrique fournit un résumé de ces fonctions.</span><span class="sxs-lookup"><span data-stu-id="6d759-105">This topic provides a summary of these functions.</span></span>

## <a name="type-conversion-functions"></a><span data-ttu-id="6d759-106">Fonctions de conversion de type</span><span class="sxs-lookup"><span data-stu-id="6d759-106">Type conversion functions</span></span>

| <span data-ttu-id="6d759-107">Fonction</span><span class="sxs-lookup"><span data-stu-id="6d759-107">Function</span></span> | <span data-ttu-id="6d759-108">Description</span><span class="sxs-lookup"><span data-stu-id="6d759-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="6d759-109">Int64Value</span><span class="sxs-lookup"><span data-stu-id="6d759-109">Int64Value</span></span>](er-functions-conversion-int64value.md)   | <span data-ttu-id="6d759-110">Cette fonction renvoie une valeur *Int64* qui représente la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6d759-110">This function returns an *Int64* value that represents the specified string.</span></span> |
| [<span data-ttu-id="6d759-111">IntValue</span><span class="sxs-lookup"><span data-stu-id="6d759-111">IntValue</span></span>](er-functions-conversion-intvalue.md)       | <span data-ttu-id="6d759-112">Cette fonction renvoie une valeur *Int* qui représente la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6d759-112">This function returns an *Int* value that represents the specified string.</span></span> |
| [<span data-ttu-id="6d759-113">NumberValue</span><span class="sxs-lookup"><span data-stu-id="6d759-113">NumberValue</span></span>](er-functions-conversion-numbervalue.md) | <span data-ttu-id="6d759-114">Cette fonction renvoie une valeur de *Réel* convertie à partir de la valeur de *Chaîne* spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6d759-114">This function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="6d759-115">Lors de la conversion, les séparateurs de regroupements décimaux et numériques spécifiés sont pris en compte.</span><span class="sxs-lookup"><span data-stu-id="6d759-115">During the conversion, the specified decimal and digit grouping separators are considered.</span></span> |
| [<span data-ttu-id="6d759-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="6d759-116">Value</span></span>](er-functions-conversion-value.md)             | <span data-ttu-id="6d759-117">Cette fonction renvoie une valeur de *Réel* convertie à partir de la valeur de *Chaîne* spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6d759-117">This function returns a *Real* value that is converted from the specified *String* value.</span></span> |

## <a name="type-conversion-functions-in-the-container-category"></a><span data-ttu-id="6d759-118">Fonctions de conversion de type dans la catégorie Conteneur</span><span class="sxs-lookup"><span data-stu-id="6d759-118">Type conversion functions in the container category</span></span>

<span data-ttu-id="6d759-119">Le tableau suivant décrit les fonctions de conversion de type dans la catégorie [Conteneur](er-functions-category-container.md).</span><span class="sxs-lookup"><span data-stu-id="6d759-119">The following table describes the type conversion functions in the [container](er-functions-category-container.md) category.</span></span>

| <span data-ttu-id="6d759-120">Fonction</span><span class="sxs-lookup"><span data-stu-id="6d759-120">Function</span></span> | <span data-ttu-id="6d759-121">Description </span><span class="sxs-lookup"><span data-stu-id="6d759-121">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="6d759-122">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="6d759-122">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="6d759-123">Cette fonction convertit l’entrée spécifiée du type *Chaîne* en un élément de données du type *Conteneur*.</span><span class="sxs-lookup"><span data-stu-id="6d759-123">This function converts the specified input of the *String* type to a data item of the *Container* type.</span></span> |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a><span data-ttu-id="6d759-124">Fonctions de conversion de type dans la catégorie de date/heure</span><span class="sxs-lookup"><span data-stu-id="6d759-124">Type conversion functions in the date and time category</span></span>

<span data-ttu-id="6d759-125">Le tableau suivant décrit les fonctions de conversion de type dans la [catégorie de date et d’heure](er-functions-category-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="6d759-125">The following table describes the type conversion functions in the [date and time category](er-functions-category-datetime.md).</span></span>

| <span data-ttu-id="6d759-126">Fonction</span><span class="sxs-lookup"><span data-stu-id="6d759-126">Function</span></span> | <span data-ttu-id="6d759-127">Description</span><span class="sxs-lookup"><span data-stu-id="6d759-127">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="6d759-128">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="6d759-128">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md)   | <span data-ttu-id="6d759-129">Cette fonction renvoie une valeur *DateTime* qui est convertie à partir d’une valeur de *Chaîne* donnée dans le format spécifié et dans une culture spécifiée en option sur une valeur de date/heure.</span><span class="sxs-lookup"><span data-stu-id="6d759-129">This function returns a *DateTime* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="6d759-130">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="6d759-130">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="6d759-131">Cette fonction renvoie une valeur de *DateTime* qui est convertie d’une valeur de *Date* donnée en une valeur de date/heure en temps universel coordonné (Heure de Greenwich, \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="6d759-131">This function returns a *DateTime* value that is converted from a given *Date* value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="6d759-132">DateValue</span><span class="sxs-lookup"><span data-stu-id="6d759-132">DateValue</span></span>](er-functions-datetime-datevalue.md)           | <span data-ttu-id="6d759-133">Cette fonction renvoie une valeur *Date* qui est convertie à partir d’une valeur de *Chaîne* donnée dans le format spécifié et dans une culture spécifiée en option sur une valeur de date.</span><span class="sxs-lookup"><span data-stu-id="6d759-133">This function returns a *Date* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date value.</span></span> |

## <a name="type-conversion-functions-in-the-list-category"></a><span data-ttu-id="6d759-134">Fonctions de conversion de type dans la catégorie de liste</span><span class="sxs-lookup"><span data-stu-id="6d759-134">Type conversion functions in the list category</span></span>

<span data-ttu-id="6d759-135">Le tableau suivant décrit les fonctions de conversion de type dans la [catégorie de liste](er-functions-category-list.md).</span><span class="sxs-lookup"><span data-stu-id="6d759-135">The following table describes the type conversion functions in the [list category](er-functions-category-list.md).</span></span>

| <span data-ttu-id="6d759-136">Fonction</span><span class="sxs-lookup"><span data-stu-id="6d759-136">Function</span></span> | <span data-ttu-id="6d759-137">Description</span><span class="sxs-lookup"><span data-stu-id="6d759-137">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="6d759-138">Liste</span><span class="sxs-lookup"><span data-stu-id="6d759-138">List</span></span>](er-functions-list-list.md)                 | <span data-ttu-id="6d759-139">Cette fonction renvoie une valeur *Liste des enregistrements* comme nouvelle liste créée à partir des arguments spécifiés de type *Conteneur (enregistrement)*.</span><span class="sxs-lookup"><span data-stu-id="6d759-139">This function returns a *Record list* value as a new list that is created from specified arguments of the *Container (record)* type.</span></span> |
| [<span data-ttu-id="6d759-140">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="6d759-140">ListOfFields</span></span>](er-functions-list-listoffields.md) | <span data-ttu-id="6d759-141">Cette fonction renvoie une valeur *Liste des enregistrements* créée en fonction de la structure d’un argument donné du type *Énumération* ou *Conteneur (enregistrement)*.</span><span class="sxs-lookup"><span data-stu-id="6d759-141">This function returns a *Record list* value that is created based on the structure of a given argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="6d759-142">Fractionner</span><span class="sxs-lookup"><span data-stu-id="6d759-142">Split</span></span>](er-functions-list-split.md)               | <span data-ttu-id="6d759-143">Cette fonction fractionne la valeur de *Chaîne* spécifiée en sous-chaînes et renvoie le résultat sous la forme d’une nouvelle valeur de *Liste des enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="6d759-143">This function splits the specified *String* value into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="6d759-144">StringJoin</span><span class="sxs-lookup"><span data-stu-id="6d759-144">StringJoin</span></span>](er-functions-list-stringjoin.md)     | <span data-ttu-id="6d759-145">Cette fonction renvoie une valeur de *Chaîne* composée des valeurs concaténées du champ spécifié dans la valeur *Liste des enregistrements* spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6d759-145">This function returns a *String* value that consists of concatenated values of the specified field from the specified *Record list* value.</span></span> <span data-ttu-id="6d759-146">Les valeurs peuvent être séparées par le séparateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="6d759-146">The values can be separated by the specified delimiter.</span></span> |

## <a name="type-conversion-functions-in-the-text-category"></a><span data-ttu-id="6d759-147">Fonctions de conversion de type dans la catégorie de texte</span><span class="sxs-lookup"><span data-stu-id="6d759-147">Type conversion functions in the text category</span></span>

<span data-ttu-id="6d759-148">Le tableau suivant décrit les fonctions de conversion de type dans la [catégorie de texte](er-functions-category-text.md).</span><span class="sxs-lookup"><span data-stu-id="6d759-148">The following table describes the type conversion functions in the [text category](er-functions-category-text.md).</span></span>

| <span data-ttu-id="6d759-149">Fonction</span><span class="sxs-lookup"><span data-stu-id="6d759-149">Function</span></span> | <span data-ttu-id="6d759-150">Description</span><span class="sxs-lookup"><span data-stu-id="6d759-150">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="6d759-151">Char</span><span class="sxs-lookup"><span data-stu-id="6d759-151">Char</span></span>](er-functions-text-char.md)                 | <span data-ttu-id="6d759-152">Cette fonction renvoie une valeur de *Chaîne* qui représente un seul caractère référencé par le numéro Unicode spécifié.</span><span class="sxs-lookup"><span data-stu-id="6d759-152">This function returns a *String* value that represents a single character that is referenced by the specified Unicode number.</span></span> |
| [<span data-ttu-id="6d759-153">GuidValue</span><span class="sxs-lookup"><span data-stu-id="6d759-153">GuidValue</span></span>](er-functions-text-guidvalue.md)       | <span data-ttu-id="6d759-154">Cette fonction convertit l’entrée spécifiée du type *Chaîne* en un élément de données du type *GUID*.</span><span class="sxs-lookup"><span data-stu-id="6d759-154">This function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span> |
| [<span data-ttu-id="6d759-155">NumberFormat</span><span class="sxs-lookup"><span data-stu-id="6d759-155">NumberFormat</span></span>](er-functions-text-numberformat.md) | <span data-ttu-id="6d759-156">Cette fonction renvoie une valeur de *Chaîne* qui représente le nombre spécifié dans le format spécifié et dans une culture éventuellement spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6d759-156">This function returns a *String* value that represents the specified number in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="6d759-157">QrCode</span><span class="sxs-lookup"><span data-stu-id="6d759-157">QrCode</span></span>](er-functions-text-qrcode.md)             | <span data-ttu-id="6d759-158">Cette fonction renvoie une valeur de *Conteneur* qui présente l’une image de code à réponse rapide (code QR) de la chaîne spécifiée au format binaire.</span><span class="sxs-lookup"><span data-stu-id="6d759-158">This function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span> |
| [<span data-ttu-id="6d759-159">Détails</span><span class="sxs-lookup"><span data-stu-id="6d759-159">Text</span></span>](er-functions-text-text.md)                 | <span data-ttu-id="6d759-160">Cette fonction renvoie une valeur de *Chaîne* qui représente le nombre spécifié une fois qu’elle a été convertie en une chaîne de texte qui est mise en forme en fonction des paramètres régionaux du serveur de l’instance d’application actuelle.</span><span class="sxs-lookup"><span data-stu-id="6d759-160">This function returns a *String* value that represents the specified number after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="6d759-161">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6d759-161">Additional resources</span></span>

[<span data-ttu-id="6d759-162">Vue d’ensemble des États électroniques</span><span class="sxs-lookup"><span data-stu-id="6d759-162">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="6d759-163">Concepteur de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="6d759-163">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="6d759-164">Langage de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="6d759-164">Electronic reporting formula language</span></span>](er-formula-language.md)
