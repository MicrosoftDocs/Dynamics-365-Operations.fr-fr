---
title: Fonction NUMBERFORMAT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction NUMBERFORMAT États électroniques (ER).
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
ms.openlocfilehash: 392135abaf7db05d5ac591ab56312a0e0f6ae5ff
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916796"
---
# <span data-ttu-id="6cdea-103"><a name="NUMBERFORMAT">Fonction NUMBERFORMAT ER</a></span><span class="sxs-lookup"><span data-stu-id="6cdea-103"><a name="NUMBERFORMAT">NUMBERFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6cdea-104">La fonction `NUMBERFORMAT` renvoie une valeur de *Chaîne* qui présente le nombre spécifié dans le format spécifié et dans une [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) éventuellement spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6cdea-104">The `NUMBERFORMAT` function returns a *String* value that presents the specified number in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="6cdea-105">Pour plus d'informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="6cdea-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="6cdea-106">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="6cdea-106">Syntax 1</span></span>

```
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a><span data-ttu-id="6cdea-107">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="6cdea-107">Syntax 2</span></span>

```
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="6cdea-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="6cdea-108">Arguments</span></span>

<span data-ttu-id="6cdea-109">`number` : *Entier* ou *Réel*</span><span class="sxs-lookup"><span data-stu-id="6cdea-109">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="6cdea-110">Valeur numérique qui spécifie le numéro qui doit être mis en forme.</span><span class="sxs-lookup"><span data-stu-id="6cdea-110">A numeric value that specifies the number that must be formatted.</span></span>

<span data-ttu-id="6cdea-111">`format` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="6cdea-111">`format` : *String*</span></span>

<span data-ttu-id="6cdea-112">Valeur *Chaîne* qui représente le format.</span><span class="sxs-lookup"><span data-stu-id="6cdea-112">A *String* value that represents the format.</span></span>

<span data-ttu-id="6cdea-113">`culture` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="6cdea-113">`culture`: *String*</span></span>

<span data-ttu-id="6cdea-114">Valeur de *Chaîne* qui représente la culture à utiliser pour la mise en forme.</span><span class="sxs-lookup"><span data-stu-id="6cdea-114">A *String* value that represents the culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="6cdea-115">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="6cdea-115">Return values</span></span>

<span data-ttu-id="6cdea-116">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="6cdea-116">*String*</span></span>

<span data-ttu-id="6cdea-117">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="6cdea-117">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6cdea-118">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="6cdea-118">Usage notes</span></span>

<span data-ttu-id="6cdea-119">Si la culture n'est pas définie comme argument de la fonction appelée, le contexte dans lequel cette fonction est exécutée détermine la culture utilisée pour formater les nombres.</span><span class="sxs-lookup"><span data-stu-id="6cdea-119">If the culture isn't defined as an argument of the called function, the context that this function is run in determines the culture that is used to format numbers.</span></span>

## <a name="example-1"></a><span data-ttu-id="6cdea-120">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="6cdea-120">Example 1</span></span>

<span data-ttu-id="6cdea-121">Pour la culture **EN-US**, `NUMBERFORMAT (0.45, "p")` renvoie **"45,00 %"** et `NUMBERFORMAT (10.45, "#")` renvoie **"10"**.</span><span class="sxs-lookup"><span data-stu-id="6cdea-121">For the **EN-US** culture, `NUMBERFORMAT (0.45, "p")` returns **"45.00 %"**, and `NUMBERFORMAT (10.45, "#")` returns **"10"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="6cdea-122">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="6cdea-122">Example 2</span></span>

<span data-ttu-id="6cdea-123">`NUMBERFORMAT (10/3, "F2", "de")` renvoie **3,33**, tandis que `NUMBERFORMAT (10/3, "F2", "en-us")` renvoie **3,33**.</span><span class="sxs-lookup"><span data-stu-id="6cdea-123">`NUMBERFORMAT (10/3, "F2", "de")` returns **3,33**, whereas `NUMBERFORMAT (10/3, "F2", "en-us")` returns **3.33**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6cdea-124">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6cdea-124">Additional resources</span></span>

[<span data-ttu-id="6cdea-125">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="6cdea-125">Text functions</span></span>](er-functions-category-text.md)