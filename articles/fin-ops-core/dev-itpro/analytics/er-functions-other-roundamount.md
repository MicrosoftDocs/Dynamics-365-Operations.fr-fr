---
title: Fonction ROUNDAMOUNT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction ROUNDAMOUNT États électroniques (ER).
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
ms.openlocfilehash: c68933352da1f9c7dc5dad76e8635981f8a89fce
ms.sourcegitcommit: 9291e6dc0de076a16684980e528c5aa98845bb34
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2918977"
---
# <span data-ttu-id="fed89-103"><a name="ROUNDAMOUNT">Fonction ROUNDAMOUNT ER</a></span><span class="sxs-lookup"><span data-stu-id="fed89-103"><a name="ROUNDAMOUNT">ROUNDAMOUNT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fed89-104">La fonction `ROUNDAMOUNT` renvoie une valeur *Réelle* comme résultat de l'arrondi du nombre spécifié au multiple le plus proche d'un autre nombre selon la règle d'arrondi spécifiée.</span><span class="sxs-lookup"><span data-stu-id="fed89-104">The `ROUNDAMOUNT` function returns a *Real* value as the result of the rounding of the specified number to the nearest multiple of another number according to the specified rounding rule.</span></span>

## <a name="syntax"></a><span data-ttu-id="fed89-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fed89-105">Syntax</span></span>

```
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a><span data-ttu-id="fed89-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="fed89-106">Arguments</span></span>

<span data-ttu-id="fed89-107">`number` : *Int* ou *Réel*</span><span class="sxs-lookup"><span data-stu-id="fed89-107">`number`: *Int* or *Real*</span></span>

<span data-ttu-id="fed89-108">Valeur numérique qui doit être arrondie.</span><span class="sxs-lookup"><span data-stu-id="fed89-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="fed89-109">`decimals` : *Int* ou *Réel*</span><span class="sxs-lookup"><span data-stu-id="fed89-109">`decimals`: *Int* or *Real*</span></span>

<span data-ttu-id="fed89-110">Nombre dont la valeur du paramètre `number` doit être arrondi à un multiple.</span><span class="sxs-lookup"><span data-stu-id="fed89-110">The number that the value of the `number` parameter must be rounded to a multiple of.</span></span>

<span data-ttu-id="fed89-111">`round rule` : *Valeur de l'énumération*</span><span class="sxs-lookup"><span data-stu-id="fed89-111">`round rule`: *Enum value*</span></span>

<span data-ttu-id="fed89-112">Valeur d'énumération de l'énumération **RoundOffType** qui définit la règle d'arrondi.</span><span class="sxs-lookup"><span data-stu-id="fed89-112">An enumeration value of the **RoundOffType** enumeration that defines the rounding rule.</span></span> <span data-ttu-id="fed89-113">Cette énumération offre les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fed89-113">This enumeration offers the following values:</span></span>

- <span data-ttu-id="fed89-114">Normal (ordinaire)</span><span class="sxs-lookup"><span data-stu-id="fed89-114">Normal (Ordinary)</span></span>
- <span data-ttu-id="fed89-115">Arrondi au chiffre inférieur (RoundDown)</span><span class="sxs-lookup"><span data-stu-id="fed89-115">Downward (RoundDown)</span></span>
- <span data-ttu-id="fed89-116">Arrondi au chiffre supérieur (RoundUp)</span><span class="sxs-lookup"><span data-stu-id="fed89-116">Rounding-up (RoundUp)</span></span>

## <a name="return-values"></a><span data-ttu-id="fed89-117">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="fed89-117">Return values</span></span>

<span data-ttu-id="fed89-118">*Réel*</span><span class="sxs-lookup"><span data-stu-id="fed89-118">*Real*</span></span>

<span data-ttu-id="fed89-119">La valeur numérique résultante est un multiple de la valeur spécifiée par le paramètre `decimals` et se rapproche le plus de la valeur spécifiée par le paramètre `number`.</span><span class="sxs-lookup"><span data-stu-id="fed89-119">The resulting numeric value is a multiple of the value specified by the `decimals` parameter and is closest to the value specified by the `number` parameter.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fed89-120">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="fed89-120">Usage notes</span></span>

<span data-ttu-id="fed89-121">Quand le paramètre `number` est zéro, cette fonction renvoie toujours zéro.</span><span class="sxs-lookup"><span data-stu-id="fed89-121">When the `number` parameter is zero, this function always returns zero.</span></span>

<span data-ttu-id="fed89-122">Quand le paramètre `decimals` est égal à zéro, cette fonction arrondit à la valeur d'arrondi par défaut.</span><span class="sxs-lookup"><span data-stu-id="fed89-122">When the `decimals` parameter is zero, this function rounds to the default round-off value.</span></span> <span data-ttu-id="fed89-123">Quand le paramètre `round rule` est défini sur **RoundOffType.Ordinary**, la valeur d'arrondi par défaut est **0,01**.</span><span class="sxs-lookup"><span data-stu-id="fed89-123">When the `round rule` parameter is set to **RoundOffType.Ordinary**, the default round-off value is **0.01**.</span></span> <span data-ttu-id="fed89-124">Sinon, la valeur d'arrondi par défaut est **1,0**.</span><span class="sxs-lookup"><span data-stu-id="fed89-124">Otherwise, the default round-off value is **1.0**.</span></span>

<span data-ttu-id="fed89-125">Quand le paramètre `round rule` est défini sur **RoundOffType.Ordinary**, cette fonction arrondit au montant d'arrondi le plus proche.</span><span class="sxs-lookup"><span data-stu-id="fed89-125">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function rounds to the nearest round-off amount.</span></span>

<span data-ttu-id="fed89-126">Quand le paramètre `round rule` est défini sur **RoundOffType.RoundDown**, cette fonction arrondit vers zéro au montant d'arrondi le plus proche.</span><span class="sxs-lookup"><span data-stu-id="fed89-126">When the `round rule` parameter is set to **RoundOffType.RoundDown**, this function rounds towards zero to the nearest round-off amount.</span></span>

<span data-ttu-id="fed89-127">Quand le paramètre `round rule` est défini sur **RoundOffType.RoundUp**, cette fonction arrondit en s'éloignant de zéro au montant d'arrondi le plus proche.</span><span class="sxs-lookup"><span data-stu-id="fed89-127">When the `round rule` parameter is set to **RoundOffType.RoundUp**, this function rounds away from zero to the nearest round-off amount.</span></span>

<span data-ttu-id="fed89-128">Quand le paramètre `round rule` est défini sur **RoundOffType.Ordinary**, cette fonction se comporte comme la fonction Excel [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) et la fonction X++ [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round).</span><span class="sxs-lookup"><span data-stu-id="fed89-128">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function behaves like the [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel function and the [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) X++ function.</span></span>

## <a name="remarks"></a><span data-ttu-id="fed89-129">Remarques</span><span class="sxs-lookup"><span data-stu-id="fed89-129">Remarks</span></span>

<span data-ttu-id="fed89-130">Pour arrondir une valeur numérique à un nombre spécifié de décimales, utilisez la fonction [ROUND](er-functions-mathematical-round.md).</span><span class="sxs-lookup"><span data-stu-id="fed89-130">To round a numeric value to a specified number of decimal places, use the [ROUND](er-functions-mathematical-round.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="fed89-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="fed89-131">Example</span></span>

<span data-ttu-id="fed89-132">Si le paramètre **model.RoundOff** est défini sur **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` renvoie 7,35.</span><span class="sxs-lookup"><span data-stu-id="fed89-132">If the **model.RoundOff** parameter is set to **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="fed89-133">Si le paramètre **model.RoundOff** est défini sur **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` renvoie 7,35.</span><span class="sxs-lookup"><span data-stu-id="fed89-133">If the **model.RoundOff** parameter is set to **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="fed89-134">Si le paramètre **model.RoundOff** est défini sur **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` renvoie 8,4.</span><span class="sxs-lookup"><span data-stu-id="fed89-134">If the **model.RoundOff** parameter is set to **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 8.4.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fed89-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fed89-135">Additional resources</span></span>

[<span data-ttu-id="fed89-136">Autre fonctions (spécifiques au domaine d'affaires)</span><span class="sxs-lookup"><span data-stu-id="fed89-136">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)

[<span data-ttu-id="fed89-137">Fonctions mathématiques</span><span class="sxs-lookup"><span data-stu-id="fed89-137">Mathematical functions</span></span>](er-functions-category-mathematical.md)