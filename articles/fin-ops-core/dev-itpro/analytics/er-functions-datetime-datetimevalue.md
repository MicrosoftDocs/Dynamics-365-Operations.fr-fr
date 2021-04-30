---
title: Fonction DATETIMEVALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction DATETIMEVALUE États électroniques (ER).
author: NickSelin
ms.date: 12/03/2019
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
ms.openlocfilehash: db5b2c56f0c6dcc019419801821d7a6eae8a0e91
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891279"
---
# <a name="datetimevalue-er-function"></a><span data-ttu-id="87e93-103">Fonction DATETIMEVALUE ER</span><span class="sxs-lookup"><span data-stu-id="87e93-103">DATETIMEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87e93-104">La fonction `DATETIMEVALUE` renvoie une valeur *DateTime* qui est convertie à partir d’une valeur de texte donnée dans le format spécifié et dans une [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) spécifiée en option sur une valeur de date/heure.</span><span class="sxs-lookup"><span data-stu-id="87e93-104">The `DATETIMEVALUE` function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date/time value.</span></span> <span data-ttu-id="87e93-105">Pour plus d’informations sur les formats pris en charge, consultez [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) et [personnalisé](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="87e93-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) and [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="87e93-106">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="87e93-106">Syntax 1</span></span>

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="87e93-107">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="87e93-107">Syntax 2</span></span>

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="87e93-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="87e93-108">Arguments</span></span>

<span data-ttu-id="87e93-109">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="87e93-109">`text`: *String*</span></span>

<span data-ttu-id="87e93-110">Texte qui représente la valeur à mettre en forme.</span><span class="sxs-lookup"><span data-stu-id="87e93-110">Text that represents the value to format.</span></span>

<span data-ttu-id="87e93-111">`format` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="87e93-111">`format`: *String*</span></span>

<span data-ttu-id="87e93-112">Format du texte donné.</span><span class="sxs-lookup"><span data-stu-id="87e93-112">The format of the given text.</span></span>

<span data-ttu-id="87e93-113">`culture` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="87e93-113">`culture`: *String*</span></span>

<span data-ttu-id="87e93-114">Culture utilisée pour la mise en forme du texte donné.</span><span class="sxs-lookup"><span data-stu-id="87e93-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="87e93-115">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="87e93-115">Return values</span></span>

<span data-ttu-id="87e93-116">*Date et heure*</span><span class="sxs-lookup"><span data-stu-id="87e93-116">*DateTime*</span></span>

<span data-ttu-id="87e93-117">Valeur de date/heure résultante.</span><span class="sxs-lookup"><span data-stu-id="87e93-117">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="87e93-118">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="87e93-118">Usage notes</span></span>

<span data-ttu-id="87e93-119">Lorsque la culture n’est pas définie comme un argument de la fonction appelée, la valeur de `culture` est définie par le contexte d’appel.</span><span class="sxs-lookup"><span data-stu-id="87e93-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="87e93-120">Par exemple, si la fonction `DATETIMEVALUE` est appelée en utilisant la syntaxe 1 dans un format d’états électroniques (ER) pour un élément **FILE** configuré pour utiliser la culture allemande, la conversion se fera en utilisant la culture allemande.</span><span class="sxs-lookup"><span data-stu-id="87e93-120">For example, if the `DATETIMEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="87e93-121">La valeur `culture` par défaut est **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="87e93-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="87e93-122">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="87e93-122">Example 1</span></span>

<span data-ttu-id="87e93-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` renvoie **2:55:00 AM le 21 décembre 2016**, en fonction du format personnalisé spécifié et de la culture **EN-US** de l’application par défaut.</span><span class="sxs-lookup"><span data-stu-id="87e93-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="87e93-124">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="87e93-124">Example 2</span></span>

<span data-ttu-id="87e93-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` renvoie **2:55:00 AM le 21 décembre 2016**, en fonction du format et de la culture personnalisés spécifiés.</span><span class="sxs-lookup"><span data-stu-id="87e93-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="87e93-126">Toutefois, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` lève une exception pour informer l’utilisateur que la chaîne spécifiée n’est pas identifiée comme une date/heure valide pour la culture spécifiée.</span><span class="sxs-lookup"><span data-stu-id="87e93-126">However, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date/time value for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="87e93-127">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="87e93-127">Additional resources</span></span>

[<span data-ttu-id="87e93-128">Fonctions de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="87e93-128">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]