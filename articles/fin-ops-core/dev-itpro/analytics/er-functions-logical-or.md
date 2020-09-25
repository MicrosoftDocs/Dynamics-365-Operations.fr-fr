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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: faf07c5d8b30cd3babe8a6a55ae7effe5ce457a0
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744621"
---
# <a name="or-er-function"></a><span data-ttu-id="e6040-103">Fonction OR ER</span><span class="sxs-lookup"><span data-stu-id="e6040-103">OR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e6040-104">La fonction `OR` renvoie une valeur *Booléenne* de **FALSE** si toutes les conditions spécifiées sont false.</span><span class="sxs-lookup"><span data-stu-id="e6040-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="e6040-105">Si toutes les conditions spécifiées sont true, la fonction renvoie une valeur *Booléenne* de **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="e6040-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6040-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e6040-106">Syntax</span></span>

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="e6040-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="e6040-107">Arguments</span></span>

<span data-ttu-id="e6040-108">`condition 1` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="e6040-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="e6040-109">Expression conditionnelle valide qui doit être testée.</span><span class="sxs-lookup"><span data-stu-id="e6040-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="e6040-110">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="e6040-110">This argument is required.</span></span>

<span data-ttu-id="e6040-111">`condition N` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="e6040-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="e6040-112">Expression conditionnelle valide qui doit être testée.</span><span class="sxs-lookup"><span data-stu-id="e6040-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="e6040-113">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="e6040-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="e6040-114">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="e6040-114">Return values</span></span>

<span data-ttu-id="e6040-115">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="e6040-115">*Boolean*</span></span>

<span data-ttu-id="e6040-116">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="e6040-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="e6040-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="e6040-117">Example</span></span>

<span data-ttu-id="e6040-118">`OR (1=2, "a"="a")` renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="e6040-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e6040-119">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e6040-119">Additional resources</span></span>

[<span data-ttu-id="e6040-120">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="e6040-120">Logical functions</span></span>](er-functions-category-logical.md)
