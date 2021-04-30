---
title: Fonction ROUNDAMOUNT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ROUNDAMOUNT États électroniques (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 7dfc7817eab68e9dd70ce84e68f26d14fd8cf1df
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891207"
---
# <a name="roundamount-er-function"></a><span data-ttu-id="bcee6-103">Fonction ROUNDAMOUNT ER</span><span class="sxs-lookup"><span data-stu-id="bcee6-103">ROUNDAMOUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bcee6-104">La fonction `ROUNDAMOUNT` renvoie une valeur *Réelle* comme résultat de l’arrondi du nombre spécifié au multiple le plus proche d’un autre nombre selon la règle d’arrondi spécifiée.</span><span class="sxs-lookup"><span data-stu-id="bcee6-104">The `ROUNDAMOUNT` function returns a *Real* value as the result of the rounding of the specified number to the nearest multiple of another number according to the specified rounding rule.</span></span>

## <a name="syntax"></a><span data-ttu-id="bcee6-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="bcee6-105">Syntax</span></span>

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a><span data-ttu-id="bcee6-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="bcee6-106">Arguments</span></span>

<span data-ttu-id="bcee6-107">`number` : *Int* ou *Réel*</span><span class="sxs-lookup"><span data-stu-id="bcee6-107">`number`: *Int* or *Real*</span></span>

<span data-ttu-id="bcee6-108">Valeur numérique qui doit être arrondie.</span><span class="sxs-lookup"><span data-stu-id="bcee6-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="bcee6-109">`decimals` : *Int* ou *Réel*</span><span class="sxs-lookup"><span data-stu-id="bcee6-109">`decimals`: *Int* or *Real*</span></span>

<span data-ttu-id="bcee6-110">Nombre dont la valeur du paramètre `number` doit être arrondi à un multiple.</span><span class="sxs-lookup"><span data-stu-id="bcee6-110">The number that the value of the `number` parameter must be rounded to a multiple of.</span></span>

<span data-ttu-id="bcee6-111">`round rule` : *Valeur de l’énumération*</span><span class="sxs-lookup"><span data-stu-id="bcee6-111">`round rule`: *Enum value*</span></span>

<span data-ttu-id="bcee6-112">Valeur d’énumération de l’énumération **RoundOffType** qui définit la règle d’arrondi.</span><span class="sxs-lookup"><span data-stu-id="bcee6-112">An enumeration value of the **RoundOffType** enumeration that defines the rounding rule.</span></span> <span data-ttu-id="bcee6-113">Cette énumération offre les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="bcee6-113">This enumeration offers the following values:</span></span>

- <span data-ttu-id="bcee6-114">Normal (ordinaire)</span><span class="sxs-lookup"><span data-stu-id="bcee6-114">Normal (Ordinary)</span></span>
- <span data-ttu-id="bcee6-115">Arrondi au chiffre inférieur (RoundDown)</span><span class="sxs-lookup"><span data-stu-id="bcee6-115">Downward (RoundDown)</span></span>
- <span data-ttu-id="bcee6-116">Arrondi au chiffre supérieur (RoundUp)</span><span class="sxs-lookup"><span data-stu-id="bcee6-116">Rounding-up (RoundUp)</span></span>

## <a name="return-values"></a><span data-ttu-id="bcee6-117">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="bcee6-117">Return values</span></span>

<span data-ttu-id="bcee6-118">*Réel*</span><span class="sxs-lookup"><span data-stu-id="bcee6-118">*Real*</span></span>

<span data-ttu-id="bcee6-119">La valeur numérique résultante est un multiple de la valeur spécifiée par le paramètre `decimals` et se rapproche le plus de la valeur spécifiée par le paramètre `number`.</span><span class="sxs-lookup"><span data-stu-id="bcee6-119">The resulting numeric value is a multiple of the value specified by the `decimals` parameter and is closest to the value specified by the `number` parameter.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bcee6-120">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="bcee6-120">Usage notes</span></span>

<span data-ttu-id="bcee6-121">Quand le paramètre `number` est zéro, cette fonction renvoie toujours zéro.</span><span class="sxs-lookup"><span data-stu-id="bcee6-121">When the `number` parameter is zero, this function always returns zero.</span></span>

<span data-ttu-id="bcee6-122">Quand le paramètre `decimals` est égal à zéro, cette fonction arrondit à la valeur d’arrondi par défaut.</span><span class="sxs-lookup"><span data-stu-id="bcee6-122">When the `decimals` parameter is zero, this function rounds to the default round-off value.</span></span> <span data-ttu-id="bcee6-123">Quand le paramètre `round rule` est défini sur **RoundOffType.Ordinary**, la valeur d’arrondi par défaut est **0,01**.</span><span class="sxs-lookup"><span data-stu-id="bcee6-123">When the `round rule` parameter is set to **RoundOffType.Ordinary**, the default round-off value is **0.01**.</span></span> <span data-ttu-id="bcee6-124">Sinon, la valeur d’arrondi par défaut est **1,0**.</span><span class="sxs-lookup"><span data-stu-id="bcee6-124">Otherwise, the default round-off value is **1.0**.</span></span>

<span data-ttu-id="bcee6-125">Quand le paramètre `round rule` est défini sur **RoundOffType.Ordinary**, cette fonction arrondit au montant d’arrondi le plus proche.</span><span class="sxs-lookup"><span data-stu-id="bcee6-125">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function rounds to the nearest round-off amount.</span></span>

<span data-ttu-id="bcee6-126">Quand le paramètre `round rule` est défini sur **RoundOffType.RoundDown**, cette fonction arrondit vers zéro au montant d’arrondi le plus proche.</span><span class="sxs-lookup"><span data-stu-id="bcee6-126">When the `round rule` parameter is set to **RoundOffType.RoundDown**, this function rounds towards zero to the nearest round-off amount.</span></span>

<span data-ttu-id="bcee6-127">Quand le paramètre `round rule` est défini sur **RoundOffType.RoundUp**, cette fonction arrondit en s’éloignant de zéro au montant d’arrondi le plus proche.</span><span class="sxs-lookup"><span data-stu-id="bcee6-127">When the `round rule` parameter is set to **RoundOffType.RoundUp**, this function rounds away from zero to the nearest round-off amount.</span></span>

<span data-ttu-id="bcee6-128">Quand le paramètre `round rule` est défini sur **RoundOffType.Ordinary**, cette fonction se comporte comme la fonction Excel [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) et la fonction X++ [ROUND](../dev-ref/xpp-math-run-time-functions.md#round).</span><span class="sxs-lookup"><span data-stu-id="bcee6-128">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function behaves like the [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel function and the [ROUND](../dev-ref/xpp-math-run-time-functions.md#round) X++ function.</span></span>

## <a name="remarks"></a><span data-ttu-id="bcee6-129">Remarques</span><span class="sxs-lookup"><span data-stu-id="bcee6-129">Remarks</span></span>

<span data-ttu-id="bcee6-130">Pour arrondir une valeur numérique à un nombre spécifié de décimales, utilisez la fonction [ROUND](er-functions-mathematical-round.md).</span><span class="sxs-lookup"><span data-stu-id="bcee6-130">To round a numeric value to a specified number of decimal places, use the [ROUND](er-functions-mathematical-round.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="bcee6-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="bcee6-131">Example</span></span>

<span data-ttu-id="bcee6-132">Si le paramètre **model.RoundOff** est défini sur **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` renvoie 7,35.</span><span class="sxs-lookup"><span data-stu-id="bcee6-132">If the **model.RoundOff** parameter is set to **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="bcee6-133">Si le paramètre **model.RoundOff** est défini sur **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` renvoie 7,35.</span><span class="sxs-lookup"><span data-stu-id="bcee6-133">If the **model.RoundOff** parameter is set to **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="bcee6-134">Si le paramètre **model.RoundOff** est défini sur **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` renvoie 8,4.</span><span class="sxs-lookup"><span data-stu-id="bcee6-134">If the **model.RoundOff** parameter is set to **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 8.4.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bcee6-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="bcee6-135">Additional resources</span></span>

[<span data-ttu-id="bcee6-136">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="bcee6-136">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)

[<span data-ttu-id="bcee6-137">Fonctions mathématiques</span><span class="sxs-lookup"><span data-stu-id="bcee6-137">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]