---
title: Fonction DAYS ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction DAYS États électroniques (ER).
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
ms.openlocfilehash: 4f8c12a22f7654285d5598064473bf86689ed207
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916290"
---
# <span data-ttu-id="87a9d-103"><a name="DAYS">Fonction DAYS ER</a></span><span class="sxs-lookup"><span data-stu-id="87a9d-103"><a name="DAYS">DAYS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87a9d-104">La fonction `DAYS` renvoie une valeur *Entier* qui représente sous forme de nombre entier du nombre de jours entre une date spécifiée et une autre date donnée.</span><span class="sxs-lookup"><span data-stu-id="87a9d-104">The `DAYS` function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="87a9d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="87a9d-105">Syntax</span></span>

```
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a><span data-ttu-id="87a9d-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="87a9d-106">Arguments</span></span>

<span data-ttu-id="87a9d-107">`date 1` : *Date*</span><span class="sxs-lookup"><span data-stu-id="87a9d-107">`date 1`: *Date*</span></span>

<span data-ttu-id="87a9d-108">Valeur de date qui représente la date de début pour le calcul du nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="87a9d-108">A date value that represents the start date for the calculation of the number of days.</span></span>

<span data-ttu-id="87a9d-109">`date 2` : *Date*</span><span class="sxs-lookup"><span data-stu-id="87a9d-109">`date 2`: *Date*</span></span>

<span data-ttu-id="87a9d-110">Valeur de date qui représente la date de fin pour le calcul du nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="87a9d-110">A date value that represents the end date for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="87a9d-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="87a9d-111">Return values</span></span>

<span data-ttu-id="87a9d-112">*Entier*</span><span class="sxs-lookup"><span data-stu-id="87a9d-112">*Integer*</span></span>

<span data-ttu-id="87a9d-113">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="87a9d-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="87a9d-114">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="87a9d-114">Usage notes</span></span>

<span data-ttu-id="87a9d-115">La fonction `DAYS` renvoie une valeur positive lorsque la première date est postérieure à la deuxième date ; renvoie **0** (zéro) lorsque la première date est égale à la deuxième date ; sinon, renvoie une valeur négative lorsque la première date est antérieure à la deuxième date.</span><span class="sxs-lookup"><span data-stu-id="87a9d-115">The `DAYS` function returns a positive value when the first date is later than the second date, it returns **0** (zero) when the first date equals the second date, and it returns a negative value when the first date is earlier than the second date.</span></span>

## <a name="example"></a><span data-ttu-id="87a9d-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="87a9d-116">Example</span></span>

<span data-ttu-id="87a9d-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` renvoie **-1**.</span><span class="sxs-lookup"><span data-stu-id="87a9d-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` returns **-1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="87a9d-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="87a9d-118">Additional resources</span></span>

[<span data-ttu-id="87a9d-119">Fonctions de date et d'heure</span><span class="sxs-lookup"><span data-stu-id="87a9d-119">Date and time functions</span></span>](er-functions-category-datetime.md)