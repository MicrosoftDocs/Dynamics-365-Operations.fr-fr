---
title: Fonction DATEVALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction DATEVALUE États électroniques (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: d760c3f874bfebad11b9497b136cb67df4e9ea61
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746937"
---
# <a name="datevalue-er-function"></a><span data-ttu-id="74a1f-103">Fonction DATEVALUE ER</span><span class="sxs-lookup"><span data-stu-id="74a1f-103">DATEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="74a1f-104">La fonction `DATEVALUE` renvoie une valeur *Date* qui est convertie à partir d’une valeur de texte donnée dans le format spécifié et dans une [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) spécifiée en option sur une valeur de date.</span><span class="sxs-lookup"><span data-stu-id="74a1f-104">The `DATEVALUE` function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date value.</span></span> <span data-ttu-id="74a1f-105">Pour plus d’informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="74a1f-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="74a1f-106">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="74a1f-106">Syntax 1</span></span>

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="74a1f-107">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="74a1f-107">Syntax 2</span></span>

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="74a1f-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="74a1f-108">Arguments</span></span>

<span data-ttu-id="74a1f-109">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="74a1f-109">`text`: *String*</span></span>

<span data-ttu-id="74a1f-110">Texte qui représente la valeur à mettre en forme.</span><span class="sxs-lookup"><span data-stu-id="74a1f-110">Text that represents the value to format.</span></span>

<span data-ttu-id="74a1f-111">`format` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="74a1f-111">`format`: *String*</span></span>

<span data-ttu-id="74a1f-112">Format du texte donné.</span><span class="sxs-lookup"><span data-stu-id="74a1f-112">The format of the given text.</span></span>

<span data-ttu-id="74a1f-113">`culture` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="74a1f-113">`culture`: *String*</span></span>

<span data-ttu-id="74a1f-114">Culture utilisée pour la mise en forme du texte donné.</span><span class="sxs-lookup"><span data-stu-id="74a1f-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="74a1f-115">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="74a1f-115">Return values</span></span>

<span data-ttu-id="74a1f-116">*date ;*</span><span class="sxs-lookup"><span data-stu-id="74a1f-116">*Date*</span></span>

<span data-ttu-id="74a1f-117">Valeur de date résultante.</span><span class="sxs-lookup"><span data-stu-id="74a1f-117">The resulting date value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="74a1f-118">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="74a1f-118">Usage notes</span></span>

<span data-ttu-id="74a1f-119">Lorsque la culture n’est pas définie comme un argument de la fonction appelée, la valeur de `culture` est définie par le contexte d’appel.</span><span class="sxs-lookup"><span data-stu-id="74a1f-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="74a1f-120">Par exemple, si la fonction `DATEVALUE` est appelée en utilisant la syntaxe 1 dans un format d’états électroniques (ER) pour un élément **FILE** configuré pour utiliser la culture allemande, la conversion se fera en utilisant la culture allemande.</span><span class="sxs-lookup"><span data-stu-id="74a1f-120">For example, if the `DATEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="74a1f-121">La valeur `culture` par défaut est **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="74a1f-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="74a1f-122">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="74a1f-122">Example 1</span></span>

<span data-ttu-id="74a1f-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` renvoie la date de valeur **21 décembre 2016**, en fonction du format personnalisé spécifié et de la culture **EN-US** de l’application par défaut.</span><span class="sxs-lookup"><span data-stu-id="74a1f-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returns the date value **December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="74a1f-124">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="74a1f-124">Example 2</span></span>

<span data-ttu-id="74a1f-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` renvoie la valeur de date **21 janvier 2016**, en fonction du format et de la culture personnalisés spécifiés.</span><span class="sxs-lookup"><span data-stu-id="74a1f-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returns the date value **January 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="74a1f-126">Toutefois, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` lève une exception pour informer l’utilisateur que la chaîne spécifiée n’est pas identifiée comme une date valide pour la culture spécifiée.</span><span class="sxs-lookup"><span data-stu-id="74a1f-126">However, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="74a1f-127">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="74a1f-127">Additional resources</span></span>

[<span data-ttu-id="74a1f-128">Fonctions de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="74a1f-128">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]