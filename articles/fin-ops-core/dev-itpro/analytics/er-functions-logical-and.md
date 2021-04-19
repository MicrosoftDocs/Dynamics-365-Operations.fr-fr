---
title: Fonction AND ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction AND États électroniques (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 9851321137b4c7744634df30f85aa3a0b1a0a588
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745471"
---
# <a name="and-er-function"></a><span data-ttu-id="70bf3-103">Fonction AND ER</span><span class="sxs-lookup"><span data-stu-id="70bf3-103">AND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70bf3-104">La fonction `AND` renvoie une valeur *Booléenne* de **TRUE** si toutes les conditions spécifiées sont true.</span><span class="sxs-lookup"><span data-stu-id="70bf3-104">The `AND` function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="70bf3-105">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="70bf3-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="70bf3-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="70bf3-106">Syntax</span></span>

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="70bf3-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="70bf3-107">Arguments</span></span>

<span data-ttu-id="70bf3-108">`condition 1` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="70bf3-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="70bf3-109">Expression conditionnelle valide qui doit être testée.</span><span class="sxs-lookup"><span data-stu-id="70bf3-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="70bf3-110">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="70bf3-110">This argument is required.</span></span>

<span data-ttu-id="70bf3-111">`condition N` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="70bf3-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="70bf3-112">Expression conditionnelle valide qui doit être testée.</span><span class="sxs-lookup"><span data-stu-id="70bf3-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="70bf3-113">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="70bf3-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="70bf3-114">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="70bf3-114">Return values</span></span>

<span data-ttu-id="70bf3-115">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="70bf3-115">*Boolean*</span></span>

<span data-ttu-id="70bf3-116">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="70bf3-116">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="70bf3-117">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="70bf3-117">Usage notes</span></span>

<span data-ttu-id="70bf3-118">Dans les arguments des fonctions logiques, vous pouvez utiliser des références de sources de données, des valeurs numériques et texte, des valeurs booléennes, des opérateurs de comparaison et d’autres fonctions des états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="70bf3-118">In the arguments of logical functions, you can use data source references, numeric and text values, Boolean values, comparison operators, and other Electronic reporting (ER) functions.</span></span> <span data-ttu-id="70bf3-119">Cependant, tous les arguments doivent être évalués en valeur *Booléenne* de **TRUE** ou **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="70bf3-119">However, all the arguments must be evaluated to a *Boolean* value of **TRUE** or **FALSE**.</span></span>

## <a name="example"></a><span data-ttu-id="70bf3-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="70bf3-120">Example</span></span>

<span data-ttu-id="70bf3-121">`AND (1=1, "a"="a")` renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="70bf3-121">`AND (1=1, "a"="a")` returns **TRUE**.</span></span>

<span data-ttu-id="70bf3-122">`AND (1=2, "a"="a")` renvoie **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="70bf3-122">`AND (1=2, "a"="a")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="70bf3-123">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="70bf3-123">Additional resources</span></span>

[<span data-ttu-id="70bf3-124">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="70bf3-124">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]