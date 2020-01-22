---
title: Fonction DAYOFYEAR ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction DAYOFYEAR États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 1080a1c2e30cd7ca64ea43120c11eb90d3c99416
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916336"
---
# <span data-ttu-id="d02ac-103"><a name="DAYOFYEAR">Fonction DAYOFYEAR ER</a></span><span class="sxs-lookup"><span data-stu-id="d02ac-103"><a name="DAYOFYEAR">DAYOFYEAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d02ac-104">La fonction `DAYOFYEAR` renvoie une valeur *Entier* qui représente sous forme de nombre entier du nombre de jours entre le 1er janvier et la date spécifiée.</span><span class="sxs-lookup"><span data-stu-id="d02ac-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="d02ac-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d02ac-105">Syntax</span></span>

```
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="d02ac-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="d02ac-106">Arguments</span></span>

<span data-ttu-id="d02ac-107">`date` : *Date*</span><span class="sxs-lookup"><span data-stu-id="d02ac-107">`date`: *Date*</span></span>

<span data-ttu-id="d02ac-108">Valeur de date qui représente la date à utiliser pour le calcul du nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="d02ac-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="d02ac-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="d02ac-109">Return values</span></span>

<span data-ttu-id="d02ac-110">*Entier*</span><span class="sxs-lookup"><span data-stu-id="d02ac-110">*Integer*</span></span>

<span data-ttu-id="d02ac-111">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="d02ac-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="d02ac-112">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="d02ac-112">Example 1</span></span>

<span data-ttu-id="d02ac-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` renvoie **61**.</span><span class="sxs-lookup"><span data-stu-id="d02ac-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="d02ac-114">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="d02ac-114">Example 2</span></span>

<span data-ttu-id="d02ac-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` renvoie **1**.</span><span class="sxs-lookup"><span data-stu-id="d02ac-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d02ac-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d02ac-116">Additional resources</span></span>

[<span data-ttu-id="d02ac-117">Fonctions de date et d'heure</span><span class="sxs-lookup"><span data-stu-id="d02ac-117">Date and time functions</span></span>](er-functions-category-datetime.md)