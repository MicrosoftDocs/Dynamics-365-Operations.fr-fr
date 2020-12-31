---
title: Fonction DAYS ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction DAYS États électroniques (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66398e624e4b9d69d4dc3ccf3ee8f97758f4f861
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682339"
---
# <a name="days-er-function"></a><span data-ttu-id="58d43-103">Fonction DAYS ER</span><span class="sxs-lookup"><span data-stu-id="58d43-103">DAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58d43-104">La fonction `DAYS` renvoie une valeur *Entier* qui représente sous forme de nombre entier du nombre de jours entre une date spécifiée et une autre date donnée.</span><span class="sxs-lookup"><span data-stu-id="58d43-104">The `DAYS` function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="58d43-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="58d43-105">Syntax</span></span>

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a><span data-ttu-id="58d43-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="58d43-106">Arguments</span></span>

<span data-ttu-id="58d43-107">`date 1` : *Date*</span><span class="sxs-lookup"><span data-stu-id="58d43-107">`date 1`: *Date*</span></span>

<span data-ttu-id="58d43-108">Valeur de date qui représente la date de début pour le calcul du nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="58d43-108">A date value that represents the start date for the calculation of the number of days.</span></span>

<span data-ttu-id="58d43-109">`date 2` : *Date*</span><span class="sxs-lookup"><span data-stu-id="58d43-109">`date 2`: *Date*</span></span>

<span data-ttu-id="58d43-110">Valeur de date qui représente la date de fin pour le calcul du nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="58d43-110">A date value that represents the end date for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="58d43-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="58d43-111">Return values</span></span>

<span data-ttu-id="58d43-112">*Entier*</span><span class="sxs-lookup"><span data-stu-id="58d43-112">*Integer*</span></span>

<span data-ttu-id="58d43-113">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="58d43-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="58d43-114">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="58d43-114">Usage notes</span></span>

<span data-ttu-id="58d43-115">La fonction `DAYS` renvoie une valeur positive lorsque la première date est postérieure à la deuxième date ; renvoie **0** (zéro) lorsque la première date est égale à la deuxième date ; sinon, renvoie une valeur négative lorsque la première date est antérieure à la deuxième date.</span><span class="sxs-lookup"><span data-stu-id="58d43-115">The `DAYS` function returns a positive value when the first date is later than the second date, it returns **0** (zero) when the first date equals the second date, and it returns a negative value when the first date is earlier than the second date.</span></span>

## <a name="example"></a><span data-ttu-id="58d43-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="58d43-116">Example</span></span>

<span data-ttu-id="58d43-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` renvoie **-1**.</span><span class="sxs-lookup"><span data-stu-id="58d43-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` returns **-1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="58d43-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="58d43-118">Additional resources</span></span>

[<span data-ttu-id="58d43-119">Fonctions de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="58d43-119">Date and time functions</span></span>](er-functions-category-datetime.md)
