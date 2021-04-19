---
title: Liste des fonctions ER dans la catégorie de date et d’heure
description: Cette rubrique fournit des informations sur les fonctions de date et d’heure prises en charge dans les États électroniques (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 2dd8524c9cd368f0fe64347e3212b419bb0902b4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744559"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a><span data-ttu-id="ae90c-103">Liste des fonctions ER dans la catégorie de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="ae90c-103">List of ER functions in the Date and time category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ae90c-104">Les fonctions de date et d’heure d’états électroniques (ER) peuvent être utilisées pour extraire des informations des valeurs de date et d’heure et pour effectuer des opérations sur celles-ci.</span><span class="sxs-lookup"><span data-stu-id="ae90c-104">Electronic reporting (ER) date and time functions can be used to extract information from date and time values, and to perform operations on them.</span></span> <span data-ttu-id="ae90c-105">Cette rubrique fournit un résumé de ces fonctions.</span><span class="sxs-lookup"><span data-stu-id="ae90c-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="ae90c-106">Liste des fonctions prises en charge</span><span class="sxs-lookup"><span data-stu-id="ae90c-106">List of supported functions</span></span>

| <span data-ttu-id="ae90c-107">Fonction</span><span class="sxs-lookup"><span data-stu-id="ae90c-107">Function</span></span> | <span data-ttu-id="ae90c-108">Description</span><span class="sxs-lookup"><span data-stu-id="ae90c-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="ae90c-109">AddDays</span><span class="sxs-lookup"><span data-stu-id="ae90c-109">AddDays</span></span>](er-functions-datetime-adddays.md) | <span data-ttu-id="ae90c-110">Cette fonction renvoie une valeur de *DateTime* qui est le nombre de jours spécifié avant ou après une date de début spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ae90c-110">This function returns a *DateTime* value that is the specified number of days before or after a specified start date.</span></span> |
| [<span data-ttu-id="ae90c-111">DateFormat</span><span class="sxs-lookup"><span data-stu-id="ae90c-111">DateFormat</span></span>](er-functions-datetime-dateformat.md) | <span data-ttu-id="ae90c-112">Cette fonction renvoie une valeur de *Chaîne* qui présente une valeur de date donnée dans le format spécifié et dans une culture éventuellement spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ae90c-112">This function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="ae90c-113">DateTimeFormat</span><span class="sxs-lookup"><span data-stu-id="ae90c-113">DateTimeFormat</span></span>](er-functions-datetime-datetimeformat.md) | <span data-ttu-id="ae90c-114">Cette fonction renvoie une valeur de *Chaîne* qui présente une valeur de date/heure donnée dans le format spécifié et dans une culture éventuellement spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ae90c-114">This function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="ae90c-115">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="ae90c-115">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md) | <span data-ttu-id="ae90c-116">Cette fonction renvoie une valeur *DateTime* qui est convertie à partir d’une valeur de texte donnée dans le format spécifié et dans une culture spécifiée en option sur une valeur de date/heure.</span><span class="sxs-lookup"><span data-stu-id="ae90c-116">This function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="ae90c-117">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="ae90c-117">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="ae90c-118">Cette fonction renvoie une valeur de *DateTime* qui est convertie d’une valeur de date donnée en une valeur de date/heure en temps universel coordonné (Heure de Greenwich, \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="ae90c-118">This function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="ae90c-119">DateValue</span><span class="sxs-lookup"><span data-stu-id="ae90c-119">DateValue</span></span>](er-functions-datetime-datevalue.md) | <span data-ttu-id="ae90c-120">Cette fonction renvoie une valeur *Date* qui est convertie à partir d’une valeur de texte donnée dans le format spécifié et dans une culture spécifiée en option sur une valeur de date.</span><span class="sxs-lookup"><span data-stu-id="ae90c-120">This function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified culture to a date value.</span></span> |
| [<span data-ttu-id="ae90c-121">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="ae90c-121">DayOfYear</span></span>](er-functions-datetime-dayofyear.md) | <span data-ttu-id="ae90c-122">Cette fonction renvoie une valeur *Entier* qui représente sous forme de nombre entier du nombre de jours entre le 1er janvier et la date spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ae90c-122">This function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span> |
| [<span data-ttu-id="ae90c-123">Jours</span><span class="sxs-lookup"><span data-stu-id="ae90c-123">Days</span></span>](er-functions-datetime-days.md) | <span data-ttu-id="ae90c-124">Cette fonction renvoie une valeur *Entier* qui représente sous forme de nombre entier du nombre de jours entre une date spécifiée et une autre date donnée.</span><span class="sxs-lookup"><span data-stu-id="ae90c-124">This function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span> |
| [<span data-ttu-id="ae90c-125">Now</span><span class="sxs-lookup"><span data-stu-id="ae90c-125">Now</span></span>](er-functions-datetime-now.md) | <span data-ttu-id="ae90c-126">Cette fonction renvoie une valeur *DateTime* qui représente la date et l’heure actuelles du serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="ae90c-126">This function returns a *DateTime* value that represents the current application server date and time.</span></span> |
| [<span data-ttu-id="ae90c-127">NullDate</span><span class="sxs-lookup"><span data-stu-id="ae90c-127">NullDate</span></span>](er-functions-datetime-nulldate.md) | <span data-ttu-id="ae90c-128">Cette fonction renvoie une valeur *Date* qui représente la date **null** (1er janvier 1900).</span><span class="sxs-lookup"><span data-stu-id="ae90c-128">This function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span> |
| [<span data-ttu-id="ae90c-129">NullDateTime</span><span class="sxs-lookup"><span data-stu-id="ae90c-129">NullDateTime</span></span>](er-functions-datetime-nulldatetime.md) | <span data-ttu-id="ae90c-130">Cette fonction renvoie une valeur de *DateTime* qui représente la valeur de date/heure **null** (1er janvier 1900) en temps universel coordonné.</span><span class="sxs-lookup"><span data-stu-id="ae90c-130">This function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time.</span></span> |
| [<span data-ttu-id="ae90c-131">SessionNow</span><span class="sxs-lookup"><span data-stu-id="ae90c-131">SessionNow</span></span>](er-functions-datetime-sessionnow.md) | <span data-ttu-id="ae90c-132">Cette fonction renvoie une valeur *DateTime* qui représente la date et l’heure actuelles de la session de l’application.</span><span class="sxs-lookup"><span data-stu-id="ae90c-132">This function returns a *DateTime* value that represents the current application session date and time.</span></span> |
| [<span data-ttu-id="ae90c-133">SessionToday</span><span class="sxs-lookup"><span data-stu-id="ae90c-133">SessionToday</span></span>](er-functions-datetime-sessiontoday.md) | <span data-ttu-id="ae90c-134">Cette fonction renvoie une valeur *Date* qui représente la date actuelle de la session de l’application.</span><span class="sxs-lookup"><span data-stu-id="ae90c-134">This function returns a *Date* value that represents the current application session date.</span></span> |
| [<span data-ttu-id="ae90c-135">Aujourd’hui</span><span class="sxs-lookup"><span data-stu-id="ae90c-135">Today</span></span>](er-functions-datetime-today.md) | <span data-ttu-id="ae90c-136">Cette fonction renvoie une valeur *Date* qui représente la date actuelle du serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="ae90c-136">This function returns a *Date* value that represents the current application server date.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="ae90c-137">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ae90c-137">Additional resources</span></span>

[<span data-ttu-id="ae90c-138">Vue d’ensemble des États électroniques</span><span class="sxs-lookup"><span data-stu-id="ae90c-138">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="ae90c-139">Concepteur de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="ae90c-139">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="ae90c-140">Langage de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="ae90c-140">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]