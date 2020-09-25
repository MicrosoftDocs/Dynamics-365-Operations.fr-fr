---
title: Fonction ROUND ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ROUND États électroniques (ER).
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
ms.openlocfilehash: 12af71a024a76fca98fc2e876da9b59e5762cf07
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744549"
---
# <a name="round-er-function"></a><span data-ttu-id="0dfdf-103">Fonction ROUND ER</span><span class="sxs-lookup"><span data-stu-id="0dfdf-103">ROUND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0dfdf-104">La fonction `ROUND` renvoie le nombre spécifié comme valeur *Réelle* une fois qu’il a été arrondi au nombre de décimales spécifié.</span><span class="sxs-lookup"><span data-stu-id="0dfdf-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="0dfdf-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0dfdf-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="0dfdf-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="0dfdf-106">Arguments</span></span>

<span data-ttu-id="0dfdf-107">`number` : *Réel*</span><span class="sxs-lookup"><span data-stu-id="0dfdf-107">`number`: *Real*</span></span>

<span data-ttu-id="0dfdf-108">Valeur numérique qui doit être arrondie.</span><span class="sxs-lookup"><span data-stu-id="0dfdf-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="0dfdf-109">`decimals` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="0dfdf-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="0dfdf-110">Valeur numérique qui représente les nombre de décimales.</span><span class="sxs-lookup"><span data-stu-id="0dfdf-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="0dfdf-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="0dfdf-111">Return values</span></span>

<span data-ttu-id="0dfdf-112">*Réel*</span><span class="sxs-lookup"><span data-stu-id="0dfdf-112">*Real*</span></span>

<span data-ttu-id="0dfdf-113">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="0dfdf-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0dfdf-114">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="0dfdf-114">Usage notes</span></span>

<span data-ttu-id="0dfdf-115">Si la valeur de l’argument `decimals` est supérieure à 0 (zéro), le numéro spécifié est arrondi au nombre de décimales.</span><span class="sxs-lookup"><span data-stu-id="0dfdf-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="0dfdf-116">Si la valeur de l’argument `decimals` est **0** (zéro), le numéro spécifié est arrondi à l’entier le plus proche.</span><span class="sxs-lookup"><span data-stu-id="0dfdf-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest integer.</span></span>

<span data-ttu-id="0dfdf-117">Si la valeur de l’argument `decimals` est inférieure à 0 (zéro), le numéro spécifié est arrondi à gauche de la virgule.</span><span class="sxs-lookup"><span data-stu-id="0dfdf-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="0dfdf-118">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="0dfdf-118">Example 1</span></span>

<span data-ttu-id="0dfdf-119">`ROUND (1200.767, 2)` arrondit à deux décimales et renvoie **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="0dfdf-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="0dfdf-120">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="0dfdf-120">Example 2</span></span>

<span data-ttu-id="0dfdf-121">`ROUND (1200.767, -3)` arrondit au multiple de 1 000 le plus proche et renvoie **1000**.</span><span class="sxs-lookup"><span data-stu-id="0dfdf-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0dfdf-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0dfdf-122">Additional resources</span></span>

[<span data-ttu-id="0dfdf-123">Fonctions mathématiques</span><span class="sxs-lookup"><span data-stu-id="0dfdf-123">Mathematical functions</span></span>](er-functions-category-mathematical.md)
