---
title: Fonction DATEFORMAT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction DATEFORMAT États électroniques (ER).
author: NickSelin
ms.date: 01/04/2021
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
ms.openlocfilehash: 1b3a0a2608328b233004034f7ab2ccfa833c17e3
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890908"
---
# <a name="dateformat-er-function"></a><span data-ttu-id="62e98-103">Fonction DATEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="62e98-103">DATEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62e98-104">La fonction `DATEFORMAT` renvoie une valeur de *Chaîne* qui présente une valeur de date donnée dans le format spécifié et dans une [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) éventuellement spécifiée.</span><span class="sxs-lookup"><span data-stu-id="62e98-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="62e98-105">Pour plus d’informations sur les formats pris en charge, consultez [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) et [personnalisé](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="62e98-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) and [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="62e98-106">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="62e98-106">Syntax 1</span></span>

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="62e98-107">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="62e98-107">Syntax 2</span></span>

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="62e98-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="62e98-108">Arguments</span></span>

<span data-ttu-id="62e98-109">`date` : *Date*</span><span class="sxs-lookup"><span data-stu-id="62e98-109">`date`: *Date*</span></span>

<span data-ttu-id="62e98-110">Valeur de date qui représente la date à mettre en forme.</span><span class="sxs-lookup"><span data-stu-id="62e98-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="62e98-111">`format` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="62e98-111">`format`: *String*</span></span>

<span data-ttu-id="62e98-112">Format de la chaîne de sortie.</span><span class="sxs-lookup"><span data-stu-id="62e98-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="62e98-113">La chaîne de format est sensible à la casse lorsque vous utilisez un format standard ou un format personnalisé.</span><span class="sxs-lookup"><span data-stu-id="62e98-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="62e98-114">Par exemple, le spécificateur de format [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) « d »renvoie la date à l’aide du schéma de date courte, tandis que le spécificateur de format standard « D » renvoie la date à l’aide du schéma de date longue.</span><span class="sxs-lookup"><span data-stu-id="62e98-114">For example, the [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="62e98-115">De plus, le spécificateur de format [personnalisé](/dotnet/standard/base-types/custom-date-and-time-format-strings) « M » renvoie le mois de 1 à 12, tandis que le spécificateur de format personnalisé « m » renvoie les minutes de 0 à 59.</span><span class="sxs-lookup"><span data-stu-id="62e98-115">Additionally, the [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="62e98-116">`culture` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="62e98-116">`culture`: *String*</span></span>

<span data-ttu-id="62e98-117">Culture à utiliser pour la mise en forme.</span><span class="sxs-lookup"><span data-stu-id="62e98-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="62e98-118">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="62e98-118">Return values</span></span>

<span data-ttu-id="62e98-119">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="62e98-119">*String*</span></span>

<span data-ttu-id="62e98-120">Valeur de la chaîne résultante.</span><span class="sxs-lookup"><span data-stu-id="62e98-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="62e98-121">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="62e98-121">Usage notes</span></span>

<span data-ttu-id="62e98-122">Si la culture n’est pas définie comme un argument de la fonction appelée, la valeur de `culture` est définie par le contexte d’appel.</span><span class="sxs-lookup"><span data-stu-id="62e98-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="62e98-123">Par exemple, si la fonction `DATEFORMAT` est appelée en utilisant la syntaxe 1 dans un format d’états électroniques (ER) pour un élément **FILE** configuré pour utiliser la culture allemande, la conversion se fera en utilisant la culture allemande.</span><span class="sxs-lookup"><span data-stu-id="62e98-123">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="62e98-124">La valeur `culture` par défaut est **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="62e98-124">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="62e98-125">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="62e98-125">Example 1</span></span>

<span data-ttu-id="62e98-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` renvoie la date du serveur d’applications actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction du format personnalisé spécifié.</span><span class="sxs-lookup"><span data-stu-id="62e98-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="62e98-127">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="62e98-127">Example 2</span></span>

<span data-ttu-id="62e98-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` renvoie la date de la session de l’application actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction de la culture allemande et du format sélectionnés spécifiés.</span><span class="sxs-lookup"><span data-stu-id="62e98-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="62e98-129">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="62e98-129">Additional resources</span></span>

[<span data-ttu-id="62e98-130">Fonctions de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="62e98-130">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]