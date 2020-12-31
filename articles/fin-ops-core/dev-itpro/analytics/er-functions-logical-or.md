---
title: Fonction OR ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction OR États électroniques (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 107241dbf9a5127d61343fc1cf42c3bab577adb3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686976"
---
# <a name="or-er-function"></a><span data-ttu-id="fa81e-103">Fonction OR ER</span><span class="sxs-lookup"><span data-stu-id="fa81e-103">OR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa81e-104">La fonction `OR` renvoie une valeur *Booléenne* de **FALSE** si toutes les conditions spécifiées sont false.</span><span class="sxs-lookup"><span data-stu-id="fa81e-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="fa81e-105">Si toutes les conditions spécifiées sont true, la fonction renvoie une valeur *Booléenne* de **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="fa81e-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa81e-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fa81e-106">Syntax</span></span>

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="fa81e-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="fa81e-107">Arguments</span></span>

<span data-ttu-id="fa81e-108">`condition 1` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="fa81e-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="fa81e-109">Expression conditionnelle valide qui doit être testée.</span><span class="sxs-lookup"><span data-stu-id="fa81e-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="fa81e-110">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="fa81e-110">This argument is required.</span></span>

<span data-ttu-id="fa81e-111">`condition N` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="fa81e-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="fa81e-112">Expression conditionnelle valide qui doit être testée.</span><span class="sxs-lookup"><span data-stu-id="fa81e-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="fa81e-113">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="fa81e-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="fa81e-114">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="fa81e-114">Return values</span></span>

<span data-ttu-id="fa81e-115">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="fa81e-115">*Boolean*</span></span>

<span data-ttu-id="fa81e-116">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="fa81e-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="fa81e-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="fa81e-117">Example</span></span>

<span data-ttu-id="fa81e-118">`OR (1=2, "a"="a")` renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="fa81e-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fa81e-119">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fa81e-119">Additional resources</span></span>

[<span data-ttu-id="fa81e-120">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="fa81e-120">Logical functions</span></span>](er-functions-category-logical.md)
