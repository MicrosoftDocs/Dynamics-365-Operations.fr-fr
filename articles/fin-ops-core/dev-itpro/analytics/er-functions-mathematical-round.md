---
title: Fonction ROUND ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ROUND États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 10/21/2020
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
ms.openlocfilehash: 83fb5c04938e0aba1277f2d6017d4b66208a8858
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683254"
---
# <a name="round-er-function"></a><span data-ttu-id="d3179-103">Fonction ROUND ER</span><span class="sxs-lookup"><span data-stu-id="d3179-103">ROUND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d3179-104">La fonction `ROUND` renvoie le nombre spécifié comme valeur *Réelle* une fois qu’il a été arrondi au nombre de décimales spécifié.</span><span class="sxs-lookup"><span data-stu-id="d3179-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="d3179-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d3179-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="d3179-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="d3179-106">Arguments</span></span>

<span data-ttu-id="d3179-107">`number` : *Réel*</span><span class="sxs-lookup"><span data-stu-id="d3179-107">`number`: *Real*</span></span>

<span data-ttu-id="d3179-108">Valeur numérique qui doit être arrondie.</span><span class="sxs-lookup"><span data-stu-id="d3179-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="d3179-109">`decimals` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="d3179-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="d3179-110">Valeur numérique qui représente les nombre de décimales.</span><span class="sxs-lookup"><span data-stu-id="d3179-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="d3179-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="d3179-111">Return values</span></span>

<span data-ttu-id="d3179-112">*Réel*</span><span class="sxs-lookup"><span data-stu-id="d3179-112">*Real*</span></span>

<span data-ttu-id="d3179-113">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="d3179-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d3179-114">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="d3179-114">Usage notes</span></span>

<span data-ttu-id="d3179-115">Si la valeur de l’argument `decimals` est supérieure à 0 (zéro), le numéro spécifié est arrondi au nombre de décimales.</span><span class="sxs-lookup"><span data-stu-id="d3179-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="d3179-116">Si la valeur de l’argument `decimals` est **0** (zéro), le numéro spécifié est arrondi à l’entier pair le plus proche.</span><span class="sxs-lookup"><span data-stu-id="d3179-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest even integer.</span></span>

<span data-ttu-id="d3179-117">Si la valeur de l’argument `decimals` est inférieure à 0 (zéro), le numéro spécifié est arrondi à gauche de la virgule.</span><span class="sxs-lookup"><span data-stu-id="d3179-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="d3179-118">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="d3179-118">Example 1</span></span>

<span data-ttu-id="d3179-119">`ROUND (1200.767, 2)` arrondit à deux décimales et renvoie **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="d3179-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="d3179-120">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="d3179-120">Example 2</span></span>

<span data-ttu-id="d3179-121">`ROUND (1200.767, -3)` arrondit au multiple de 1 000 le plus proche et renvoie **1000**.</span><span class="sxs-lookup"><span data-stu-id="d3179-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="example-3"></a><span data-ttu-id="d3179-122">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="d3179-122">Example 3</span></span>

<span data-ttu-id="d3179-123">`ROUND (1200.5, 0)` arrondit à l’entier pair le plus proche et renvoie **1200**, tandis que `ROUND (1201.5, 0)` fait de même et retourne **1202**.</span><span class="sxs-lookup"><span data-stu-id="d3179-123">`ROUND (1200.5, 0)` rounds to the nearest even integer and returns **1200**, while `ROUND (1201.5, 0)` does the same and returns **1202**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d3179-124">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d3179-124">Additional resources</span></span>

[<span data-ttu-id="d3179-125">Fonctions mathématiques</span><span class="sxs-lookup"><span data-stu-id="d3179-125">Mathematical functions</span></span>](er-functions-category-mathematical.md)
