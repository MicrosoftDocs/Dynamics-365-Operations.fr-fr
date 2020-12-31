---
title: Fonction DATEFORMAT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction DATEFORMAT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 1fa6bdef2168112aeb17e0edb9f9a6d1b3bd45c0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684929"
---
# <a name="dateformat-er-function"></a><span data-ttu-id="7ce1e-103">Fonction DATEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="7ce1e-103">DATEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ce1e-104">La fonction `DATEFORMAT` renvoie une valeur de *Chaîne* qui présente une valeur de date donnée dans le format spécifié et dans une [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) éventuellement spécifiée.</span><span class="sxs-lookup"><span data-stu-id="7ce1e-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="7ce1e-105">Pour plus d’informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="7ce1e-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="7ce1e-106">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="7ce1e-106">Syntax 1</span></span>

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="7ce1e-107">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="7ce1e-107">Syntax 2</span></span>

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="7ce1e-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="7ce1e-108">Arguments</span></span>

<span data-ttu-id="7ce1e-109">`date` : *Date*</span><span class="sxs-lookup"><span data-stu-id="7ce1e-109">`date`: *Date*</span></span>

<span data-ttu-id="7ce1e-110">Valeur de date qui représente la date à mettre en forme.</span><span class="sxs-lookup"><span data-stu-id="7ce1e-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="7ce1e-111">`format` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="7ce1e-111">`format`: *String*</span></span>

<span data-ttu-id="7ce1e-112">Format de la chaîne de sortie.</span><span class="sxs-lookup"><span data-stu-id="7ce1e-112">The format of the output string.</span></span>

<span data-ttu-id="7ce1e-113">`culture` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="7ce1e-113">`culture`: *String*</span></span>

<span data-ttu-id="7ce1e-114">Culture à utiliser pour la mise en forme.</span><span class="sxs-lookup"><span data-stu-id="7ce1e-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="7ce1e-115">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="7ce1e-115">Return values</span></span>

<span data-ttu-id="7ce1e-116">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="7ce1e-116">*String*</span></span>

<span data-ttu-id="7ce1e-117">Valeur de la chaîne résultante.</span><span class="sxs-lookup"><span data-stu-id="7ce1e-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7ce1e-118">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="7ce1e-118">Usage notes</span></span>

<span data-ttu-id="7ce1e-119">Lorsque la culture n’est pas définie comme un argument de la fonction appelée, la valeur de `culture` est définie par le contexte d’appel.</span><span class="sxs-lookup"><span data-stu-id="7ce1e-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="7ce1e-120">Par exemple, si la fonction `DATEFORMAT` est appelée en utilisant la syntaxe 1 dans un format d’états électroniques (ER) pour un élément **FILE** configuré pour utiliser la culture allemande, la conversion se fera en utilisant la culture allemande.</span><span class="sxs-lookup"><span data-stu-id="7ce1e-120">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="7ce1e-121">La valeur `culture` par défaut est **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="7ce1e-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="7ce1e-122">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="7ce1e-122">Example 1</span></span>

<span data-ttu-id="7ce1e-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` renvoie la date du serveur d’applications actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction du format personnalisé spécifié.</span><span class="sxs-lookup"><span data-stu-id="7ce1e-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="7ce1e-124">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="7ce1e-124">Example 2</span></span>

<span data-ttu-id="7ce1e-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` renvoie la date de la session de l’application actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction de la culture allemande et du format sélectionnés spécifiés.</span><span class="sxs-lookup"><span data-stu-id="7ce1e-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string  **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7ce1e-126">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7ce1e-126">Additional resources</span></span>

[<span data-ttu-id="7ce1e-127">Fonctions de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="7ce1e-127">Date and time functions</span></span>](er-functions-category-datetime.md)
