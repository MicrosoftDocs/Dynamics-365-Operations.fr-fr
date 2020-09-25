---
title: Fonction ADDDAYS ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ADDDAYS États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 998cf2c0dac67040814d4a32e433b465ec51f88c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743373"
---
# <a name="adddays-er-function"></a><span data-ttu-id="4104d-103">Fonction ADDDAYS ER</span><span class="sxs-lookup"><span data-stu-id="4104d-103">ADDDAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4104d-104">La fonction `ADDDAYS` calcule une valeur de *DateTime* qui est le nombre de jours spécifié avant ou après une date de début spécifiée.</span><span class="sxs-lookup"><span data-stu-id="4104d-104">The `ADDDAYS` function calculates a *DateTime* value that is the specified number of days before or after a specified start date.</span></span>

## <a name="syntax"></a><span data-ttu-id="4104d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4104d-105">Syntax</span></span>

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a><span data-ttu-id="4104d-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="4104d-106">Arguments</span></span>

<span data-ttu-id="4104d-107">`datetime` : *DateTime*</span><span class="sxs-lookup"><span data-stu-id="4104d-107">`datetime`: *DateTime*</span></span>

<span data-ttu-id="4104d-108">Valeur de date/heure qui représente la date de début.</span><span class="sxs-lookup"><span data-stu-id="4104d-108">A date/time value that represents the start date.</span></span>

<span data-ttu-id="4104d-109">`days` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="4104d-109">`days`: *Integer*</span></span>

<span data-ttu-id="4104d-110">Nombre de jours avant ou après `datetime`.</span><span class="sxs-lookup"><span data-stu-id="4104d-110">The number of days before or after `datetime`.</span></span>

## <a name="return-values"></a><span data-ttu-id="4104d-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="4104d-111">Return values</span></span>

<span data-ttu-id="4104d-112">*Date et heure*</span><span class="sxs-lookup"><span data-stu-id="4104d-112">*DateTime*</span></span>

<span data-ttu-id="4104d-113">Valeur de date/heure résultante.</span><span class="sxs-lookup"><span data-stu-id="4104d-113">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="4104d-114">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="4104d-114">Usage notes</span></span>

<span data-ttu-id="4104d-115">Une valeur positive pour `days` donne une date future.</span><span class="sxs-lookup"><span data-stu-id="4104d-115">A positive value for `days` yields a future date.</span></span> <span data-ttu-id="4104d-116">Une valeur négative donne une date passée.</span><span class="sxs-lookup"><span data-stu-id="4104d-116">A negative value yields a past date.</span></span>

## <a name="example-1"></a><span data-ttu-id="4104d-117">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="4104d-117">Example 1</span></span>

<span data-ttu-id="4104d-118">`ADDDAYS (NOW(), 7)` renvoie la date et l’heure, sept jours dans le futur.</span><span class="sxs-lookup"><span data-stu-id="4104d-118">`ADDDAYS (NOW(), 7)` returns the date and time seven days in the future.</span></span>

## <a name="example-2"></a><span data-ttu-id="4104d-119">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="4104d-119">Example 2</span></span>

<span data-ttu-id="4104d-120">`ADDDAYS (NOW(), -3)` renvoie la date et l’heure, trois jours dans le passé.</span><span class="sxs-lookup"><span data-stu-id="4104d-120">`ADDDAYS (NOW(), -3)` returns the date and time three days in the past.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4104d-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4104d-121">Additional resources</span></span>

[<span data-ttu-id="4104d-122">Fonctions de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="4104d-122">Date and time functions</span></span>](er-functions-category-datetime.md)
