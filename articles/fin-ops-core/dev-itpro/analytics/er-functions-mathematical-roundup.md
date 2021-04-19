---
title: Fonction ROUNDUP ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ROUNDUP États électroniques (ER).
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
ms.openlocfilehash: 4898f596108ff3c563da55a567a10da987d62d33
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744437"
---
# <a name="roundup-er-function"></a><span data-ttu-id="87ebf-103">Fonction ROUNDUP ER</span><span class="sxs-lookup"><span data-stu-id="87ebf-103">ROUNDUP ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87ebf-104">La fonction `ROUNDUP` renvoie le nombre spécifié comme valeur *Réelle* une fois qu’il a été arrondi au nombre supérieur de décimales spécifié.</span><span class="sxs-lookup"><span data-stu-id="87ebf-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="87ebf-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="87ebf-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="87ebf-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="87ebf-106">Arguments</span></span>

<span data-ttu-id="87ebf-107">`number` : *Réel*</span><span class="sxs-lookup"><span data-stu-id="87ebf-107">`number`: *Real*</span></span>

<span data-ttu-id="87ebf-108">Valeur numérique qui doit être arrondie.</span><span class="sxs-lookup"><span data-stu-id="87ebf-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="87ebf-109">`decimals` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="87ebf-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="87ebf-110">Valeur numérique qui représente les nombre de décimales.</span><span class="sxs-lookup"><span data-stu-id="87ebf-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="87ebf-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="87ebf-111">Return values</span></span>

<span data-ttu-id="87ebf-112">*Réel*</span><span class="sxs-lookup"><span data-stu-id="87ebf-112">*Real*</span></span>

<span data-ttu-id="87ebf-113">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="87ebf-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="87ebf-114">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="87ebf-114">Usage notes</span></span>

<span data-ttu-id="87ebf-115">Cette fonction se comporte comme [ROUND](er-functions-mathematical-round.md), mais elle arrondit toujours le nombre spécifié vers le haut (loin de zéro).</span><span class="sxs-lookup"><span data-stu-id="87ebf-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="87ebf-116">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="87ebf-116">Example 1</span></span>

<span data-ttu-id="87ebf-117">`ROUNDUP (1200.763, 2)` arrondit vers le haut à deux décimales et renvoie **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="87ebf-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="87ebf-118">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="87ebf-118">Example 2</span></span>

<span data-ttu-id="87ebf-119">`ROUNDUP (1200.767, -3)` arrondit vers le haut au multiple de 1 000 le plus proche et renvoie **2 000**.</span><span class="sxs-lookup"><span data-stu-id="87ebf-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="87ebf-120">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="87ebf-120">Additional resources</span></span>

[<span data-ttu-id="87ebf-121">Fonctions mathématiques</span><span class="sxs-lookup"><span data-stu-id="87ebf-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]