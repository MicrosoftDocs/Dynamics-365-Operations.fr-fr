---
title: Fonction ROUNDUP ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction ROUNDUP États électroniques (ER).
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
ms.openlocfilehash: 84a62639b49db17fef1abcda75bc5ad7f08d1005
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917049"
---
# <span data-ttu-id="bf1d1-103"><a name="ROUNDUP">Fonction ROUNDUP ER</a></span><span class="sxs-lookup"><span data-stu-id="bf1d1-103"><a name="ROUNDUP">ROUNDUP ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bf1d1-104">La fonction `ROUNDUP` renvoie le nombre spécifié comme valeur *Réelle* une fois qu'il a été arrondi au nombre supérieur de décimales spécifié.</span><span class="sxs-lookup"><span data-stu-id="bf1d1-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf1d1-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="bf1d1-105">Syntax</span></span>

```
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="bf1d1-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="bf1d1-106">Arguments</span></span>

<span data-ttu-id="bf1d1-107">`number` : *Réel*</span><span class="sxs-lookup"><span data-stu-id="bf1d1-107">`number`: *Real*</span></span>

<span data-ttu-id="bf1d1-108">Valeur numérique qui doit être arrondie.</span><span class="sxs-lookup"><span data-stu-id="bf1d1-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="bf1d1-109">`decimals` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="bf1d1-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="bf1d1-110">Valeur numérique qui représente les nombre de décimales.</span><span class="sxs-lookup"><span data-stu-id="bf1d1-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="bf1d1-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="bf1d1-111">Return values</span></span>

<span data-ttu-id="bf1d1-112">*Réel*</span><span class="sxs-lookup"><span data-stu-id="bf1d1-112">*Real*</span></span>

<span data-ttu-id="bf1d1-113">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="bf1d1-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bf1d1-114">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="bf1d1-114">Usage notes</span></span>

<span data-ttu-id="bf1d1-115">Cette fonction se comporte comme [ROUND](er-functions-mathematical-round.md), mais elle arrondit toujours le nombre spécifié vers le haut (loin de zéro).</span><span class="sxs-lookup"><span data-stu-id="bf1d1-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="bf1d1-116">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="bf1d1-116">Example 1</span></span>

<span data-ttu-id="bf1d1-117">`ROUNDUP (1200.763, 2)` arrondit vers le haut à deux décimales et renvoie **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="bf1d1-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="bf1d1-118">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="bf1d1-118">Example 2</span></span>

<span data-ttu-id="bf1d1-119">`ROUNDUP (1200.767, -3)` arrondit vers le haut au multiple de 1 000 le plus proche et renvoie **2 000**.</span><span class="sxs-lookup"><span data-stu-id="bf1d1-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bf1d1-120">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="bf1d1-120">Additional resources</span></span>

[<span data-ttu-id="bf1d1-121">Fonctions mathématiques</span><span class="sxs-lookup"><span data-stu-id="bf1d1-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
