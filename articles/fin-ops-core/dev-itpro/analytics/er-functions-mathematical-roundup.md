---
title: Fonction ROUNDUP ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ROUNDUP États électroniques (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: d23a984bd59c4d2d37c407e3fcfed9c7017dcc7f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569333"
---
# <a name="roundup-er-function"></a><span data-ttu-id="ccbd3-103">Fonction ROUNDUP ER</span><span class="sxs-lookup"><span data-stu-id="ccbd3-103">ROUNDUP ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ccbd3-104">La fonction `ROUNDUP` renvoie le nombre spécifié comme valeur *Réelle* une fois qu’il a été arrondi au nombre supérieur de décimales spécifié.</span><span class="sxs-lookup"><span data-stu-id="ccbd3-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="ccbd3-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ccbd3-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="ccbd3-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="ccbd3-106">Arguments</span></span>

<span data-ttu-id="ccbd3-107">`number` : *Réel*</span><span class="sxs-lookup"><span data-stu-id="ccbd3-107">`number`: *Real*</span></span>

<span data-ttu-id="ccbd3-108">Valeur numérique qui doit être arrondie.</span><span class="sxs-lookup"><span data-stu-id="ccbd3-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="ccbd3-109">`decimals` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="ccbd3-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="ccbd3-110">Valeur numérique qui représente les nombre de décimales.</span><span class="sxs-lookup"><span data-stu-id="ccbd3-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="ccbd3-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="ccbd3-111">Return values</span></span>

<span data-ttu-id="ccbd3-112">*Réel*</span><span class="sxs-lookup"><span data-stu-id="ccbd3-112">*Real*</span></span>

<span data-ttu-id="ccbd3-113">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="ccbd3-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ccbd3-114">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="ccbd3-114">Usage notes</span></span>

<span data-ttu-id="ccbd3-115">Cette fonction se comporte comme [ROUND](er-functions-mathematical-round.md), mais elle arrondit toujours le nombre spécifié vers le haut (loin de zéro).</span><span class="sxs-lookup"><span data-stu-id="ccbd3-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="ccbd3-116">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="ccbd3-116">Example 1</span></span>

<span data-ttu-id="ccbd3-117">`ROUNDUP (1200.763, 2)` arrondit vers le haut à deux décimales et renvoie **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="ccbd3-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="ccbd3-118">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="ccbd3-118">Example 2</span></span>

<span data-ttu-id="ccbd3-119">`ROUNDUP (1200.767, -3)` arrondit vers le haut au multiple de 1 000 le plus proche et renvoie **2 000**.</span><span class="sxs-lookup"><span data-stu-id="ccbd3-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ccbd3-120">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ccbd3-120">Additional resources</span></span>

[<span data-ttu-id="ccbd3-121">Fonctions mathématiques</span><span class="sxs-lookup"><span data-stu-id="ccbd3-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]