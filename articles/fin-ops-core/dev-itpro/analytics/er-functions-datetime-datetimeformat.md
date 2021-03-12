---
title: Fonction DATETIMEFORMAT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction DATETIMEFORMAT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 01/04/2021
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
ms.openlocfilehash: 90bd2900434b1be509f72ec82375e52ea32bc424
ms.sourcegitcommit: 7cfe8931dd454e811a691f5118a4ecae7ba4b478
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/04/2021
ms.locfileid: "4825371"
---
# <a name="datetimeformat-er-function"></a><span data-ttu-id="f98de-103">Fonction DATETIMEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="f98de-103">DATETIMEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f98de-104">La fonction `DATETIMEFORMAT` renvoie une valeur de *Chaîne* qui présente une valeur de date/heure donnée dans le format spécifié et dans une [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) éventuellement spécifiée.</span><span class="sxs-lookup"><span data-stu-id="f98de-104">The `DATETIMEFORMAT` function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="f98de-105">Pour plus d’informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="f98de-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="f98de-106">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="f98de-106">Syntax 1</span></span>

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a><span data-ttu-id="f98de-107">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="f98de-107">Syntax 2</span></span>

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="f98de-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="f98de-108">Arguments</span></span>

<span data-ttu-id="f98de-109">`datetime` : *DateTime*</span><span class="sxs-lookup"><span data-stu-id="f98de-109">`datetime`: *DateTime*</span></span>

<span data-ttu-id="f98de-110">Valeur de date/heure qui représente la date et l’heure à mettre en forme.</span><span class="sxs-lookup"><span data-stu-id="f98de-110">A date/time value that represents the date and time to format.</span></span>

<span data-ttu-id="f98de-111">`format` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="f98de-111">`format`: *String*</span></span>

<span data-ttu-id="f98de-112">Format de la chaîne de sortie.</span><span class="sxs-lookup"><span data-stu-id="f98de-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="f98de-113">La chaîne de format est sensible à la casse lorsque vous utilisez un format standard ou un format personnalisé.</span><span class="sxs-lookup"><span data-stu-id="f98de-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="f98de-114">Par exemple, le spécificateur de format [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) « d »renvoie la date à l’aide du schéma de date courte, tandis que le spécificateur de format standard « D » renvoie la date à l’aide du schéma de date longue.</span><span class="sxs-lookup"><span data-stu-id="f98de-114">For example, the [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="f98de-115">De plus, le spécificateur de format [personnalisé](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) « M » renvoie le mois de 1 à 12, tandis que le spécificateur de format personnalisé « m » renvoie les minutes de 0 à 59.</span><span class="sxs-lookup"><span data-stu-id="f98de-115">Additionally, the [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="f98de-116">`culture` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="f98de-116">`culture`: *String*</span></span>

<span data-ttu-id="f98de-117">Culture à utiliser pour la mise en forme.</span><span class="sxs-lookup"><span data-stu-id="f98de-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="f98de-118">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="f98de-118">Return values</span></span>

<span data-ttu-id="f98de-119">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="f98de-119">*String*</span></span>

<span data-ttu-id="f98de-120">Valeur de la chaîne résultante.</span><span class="sxs-lookup"><span data-stu-id="f98de-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f98de-121">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="f98de-121">Usage notes</span></span>

<span data-ttu-id="f98de-122">Si la culture n’est pas définie comme un argument de la fonction appelée, la valeur de `culture` est définie par le contexte d’appel.</span><span class="sxs-lookup"><span data-stu-id="f98de-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="f98de-123">Par exemple, si la fonction `DATETIMEFORMAT` est appelée en utilisant la syntaxe 1 dans un format d’états électroniques (ER) pour un élément **FILE** configuré pour utiliser la culture allemande, la conversion se fera en utilisant la culture allemande.</span><span class="sxs-lookup"><span data-stu-id="f98de-123">For example, if the `DATETIMEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="f98de-124">La valeur `culture` par défaut est **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="f98de-124">The default `culture` value is **EN-US**.</span></span>

<span data-ttu-id="f98de-125">Quand la fonction `DATETIMEFORMAT` convertit une valeur de date/heure donnée, elle considère le paramètre de fuseau horaire de l’utilisateur de l’application qui exécute le format ER que la fonction est appelée dans le contexte.</span><span class="sxs-lookup"><span data-stu-id="f98de-125">When the `DATETIMEFORMAT` function converts a given date/time value, it considers the time zone setting of the application user who is running the ER format that the function is called in the context of.</span></span>

## <a name="example-1"></a><span data-ttu-id="f98de-126">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="f98de-126">Example 1</span></span>

<span data-ttu-id="f98de-127">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` renvoie la valeur de date/heure du serveur d’applications actuelle, 24 décembre 2015, sous la forme **« 24-12-2015 »**, en fonction du format personnalisé spécifié.</span><span class="sxs-lookup"><span data-stu-id="f98de-127">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="f98de-128">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="f98de-128">Example 2</span></span>

<span data-ttu-id="f98de-129">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` renvoie la valeur de date/heure de la session de l’application actuelle, 24 décembre 2015, sous la forme de **« 24.12.2015 »**, en fonction de la culture allemande et du format sélectionnés spécifiés.</span><span class="sxs-lookup"><span data-stu-id="f98de-129">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="example-3"></a><span data-ttu-id="f98de-130">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="f98de-130">Example 3</span></span>

<span data-ttu-id="f98de-131">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` renvoie la valeur de chaîne **2019-11-12T08:00:00.0000000-08:00** lorsqu’il est appelé lors d’un processus qui a été lancé par un utilisateur d’application qui a la valeur de fuseau horaire **(GMT-08:00) Heure du Pacifique (États-Unis et Canada)** dans la section **Préférences de langue et paramètres locaux**.</span><span class="sxs-lookup"><span data-stu-id="f98de-131">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returns the string value **2019-11-12T08:00:00.0000000-08:00** when the function is called during a process that was initiated by an application user who has the time zone value **(GMT-08:00) Pacific Time (US & Canada)** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f98de-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f98de-132">Additional resources</span></span>

[<span data-ttu-id="f98de-133">Fonctions de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="f98de-133">Date and time functions</span></span>](er-functions-category-datetime.md)
