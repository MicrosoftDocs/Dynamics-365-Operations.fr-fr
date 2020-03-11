---
title: Fonction ROUNDDOWN ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction ROUNDDOWN États électroniques (ER).
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
ms.openlocfilehash: 92150bb23e76f82907e0f3e8f0738b25801958bf
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041559"
---
# <span data-ttu-id="f69b6-103"><a name="ROUNDDOWN">Fonction ROUNDDOWN ER</a></span><span class="sxs-lookup"><span data-stu-id="f69b6-103"><a name="ROUNDDOWN">ROUNDDOWN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f69b6-104">La fonction `ROUNDDOWN` renvoie le nombre spécifié comme valeur *Réelle* une fois qu'il a été arrondi au nombre inférieur de décimales spécifié.</span><span class="sxs-lookup"><span data-stu-id="f69b6-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="f69b6-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f69b6-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="f69b6-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="f69b6-106">Arguments</span></span>

<span data-ttu-id="f69b6-107">`number` : *Réel*</span><span class="sxs-lookup"><span data-stu-id="f69b6-107">`number`: *Real*</span></span>

<span data-ttu-id="f69b6-108">Valeur numérique qui doit être arrondie.</span><span class="sxs-lookup"><span data-stu-id="f69b6-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="f69b6-109">`decimals` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="f69b6-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="f69b6-110">Valeur numérique qui représente les nombre de décimales.</span><span class="sxs-lookup"><span data-stu-id="f69b6-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="f69b6-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="f69b6-111">Return values</span></span>

<span data-ttu-id="f69b6-112">*Réel*</span><span class="sxs-lookup"><span data-stu-id="f69b6-112">*Real*</span></span>

<span data-ttu-id="f69b6-113">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="f69b6-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f69b6-114">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="f69b6-114">Usage notes</span></span>

<span data-ttu-id="f69b6-115">Cette fonction se comporte comme [ROUND](er-functions-mathematical-round.md), mais elle arrondit toujours le nombre spécifié vers le bas (vers zéro).</span><span class="sxs-lookup"><span data-stu-id="f69b6-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="f69b6-116">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="f69b6-116">Example 1</span></span>

<span data-ttu-id="f69b6-117">`ROUNDDOWN (1200.767, 2)` arrondit vers le bas à deux décimales et renvoie **1200,76**.</span><span class="sxs-lookup"><span data-stu-id="f69b6-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="f69b6-118">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="f69b6-118">Example 2</span></span>

<span data-ttu-id="f69b6-119">`ROUNDDOWN (1700.767, -3)` arrondit vers le bas au multiple de 1 000 le plus proche et renvoie **2 000**.</span><span class="sxs-lookup"><span data-stu-id="f69b6-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f69b6-120">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f69b6-120">Additional resources</span></span>

[<span data-ttu-id="f69b6-121">Fonctions mathématiques</span><span class="sxs-lookup"><span data-stu-id="f69b6-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
