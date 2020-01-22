---
title: Fonction OR ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction OR États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 81a596f5206b23001feea553adcdf6c904572775
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917118"
---
# <span data-ttu-id="f5254-103"><a name="OR">Fonction OR ER</a></span><span class="sxs-lookup"><span data-stu-id="f5254-103"><a name="OR">OR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5254-104">La fonction `OR` renvoie une valeur *Booléenne* de **FALSE** si toutes les conditions spécifiées sont false.</span><span class="sxs-lookup"><span data-stu-id="f5254-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="f5254-105">Si toutes les conditions spécifiées sont true, la fonction renvoie une valeur *Booléenne* de **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="f5254-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="f5254-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f5254-106">Syntax</span></span>

```
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="f5254-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="f5254-107">Arguments</span></span>

<span data-ttu-id="f5254-108">`condition 1` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="f5254-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="f5254-109">Expression conditionnelle valide qui doit être testée.</span><span class="sxs-lookup"><span data-stu-id="f5254-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="f5254-110">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="f5254-110">This argument is required.</span></span>

<span data-ttu-id="f5254-111">`condition N` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="f5254-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="f5254-112">Expression conditionnelle valide qui doit être testée.</span><span class="sxs-lookup"><span data-stu-id="f5254-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="f5254-113">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="f5254-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="f5254-114">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="f5254-114">Return values</span></span>

<span data-ttu-id="f5254-115">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="f5254-115">*Boolean*</span></span>

<span data-ttu-id="f5254-116">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="f5254-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="f5254-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="f5254-117">Example</span></span>

<span data-ttu-id="f5254-118">`OR (1=2, "a"="a")` renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="f5254-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f5254-119">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f5254-119">Additional resources</span></span>

[<span data-ttu-id="f5254-120">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="f5254-120">Logical functions</span></span>](er-functions-category-logical.md)
