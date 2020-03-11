---
title: Fonction ROUND ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction ROUND États électroniques (ER).
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
ms.openlocfilehash: 6751c1321fc71419fa8b153145a057371e0f7af5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041605"
---
# <span data-ttu-id="dce0b-103"><a name="ROUND">Fonction ROUND ER</a></span><span class="sxs-lookup"><span data-stu-id="dce0b-103"><a name="ROUND">ROUND ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dce0b-104">La fonction `ROUND` renvoie le nombre spécifié comme valeur *Réelle* une fois qu'il a été arrondi au nombre de décimales spécifié.</span><span class="sxs-lookup"><span data-stu-id="dce0b-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="dce0b-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="dce0b-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="dce0b-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="dce0b-106">Arguments</span></span>

<span data-ttu-id="dce0b-107">`number` : *Réel*</span><span class="sxs-lookup"><span data-stu-id="dce0b-107">`number`: *Real*</span></span>

<span data-ttu-id="dce0b-108">Valeur numérique qui doit être arrondie.</span><span class="sxs-lookup"><span data-stu-id="dce0b-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="dce0b-109">`decimals` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="dce0b-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="dce0b-110">Valeur numérique qui représente les nombre de décimales.</span><span class="sxs-lookup"><span data-stu-id="dce0b-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="dce0b-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="dce0b-111">Return values</span></span>

<span data-ttu-id="dce0b-112">*Réel*</span><span class="sxs-lookup"><span data-stu-id="dce0b-112">*Real*</span></span>

<span data-ttu-id="dce0b-113">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="dce0b-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="dce0b-114">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="dce0b-114">Usage notes</span></span>

<span data-ttu-id="dce0b-115">Si la valeur de l'argument `decimals` est supérieure à 0 (zéro), le numéro spécifié est arrondi au nombre de décimales.</span><span class="sxs-lookup"><span data-stu-id="dce0b-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="dce0b-116">Si la valeur de l'argument `decimals` est **0** (zéro), le numéro spécifié est arrondi à l'entier le plus proche.</span><span class="sxs-lookup"><span data-stu-id="dce0b-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest integer.</span></span>

<span data-ttu-id="dce0b-117">Si la valeur de l'argument `decimals` est inférieure à 0 (zéro), le numéro spécifié est arrondi à gauche de la virgule.</span><span class="sxs-lookup"><span data-stu-id="dce0b-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="dce0b-118">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="dce0b-118">Example 1</span></span>

<span data-ttu-id="dce0b-119">`ROUND (1200.767, 2)` arrondit à deux décimales et renvoie **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="dce0b-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="dce0b-120">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="dce0b-120">Example 2</span></span>

<span data-ttu-id="dce0b-121">`ROUND (1200.767, -3)` arrondit au multiple de 1 000 le plus proche et renvoie **1000**.</span><span class="sxs-lookup"><span data-stu-id="dce0b-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dce0b-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="dce0b-122">Additional resources</span></span>

[<span data-ttu-id="dce0b-123">Fonctions mathématiques</span><span class="sxs-lookup"><span data-stu-id="dce0b-123">Mathematical functions</span></span>](er-functions-category-mathematical.md)
