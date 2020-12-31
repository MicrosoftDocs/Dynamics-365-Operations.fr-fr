---
title: Fonction NUMBERVALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction NUMBERVALUE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: d3eec6dc5a472f366c9029456fe05cf1e431e1c5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685977"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="87933-103">Fonction NUMBERVALUE ER</span><span class="sxs-lookup"><span data-stu-id="87933-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87933-104">La fonction `NUMBERVALUE` renvoie une valeur de *Réel* convertie à partir de la valeur de *Chaîne* spécifiée.</span><span class="sxs-lookup"><span data-stu-id="87933-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="87933-105">Lors de la conversion, les séparateurs de regroupements décimaux et numériques spécifiés sont pris en compte.</span><span class="sxs-lookup"><span data-stu-id="87933-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="87933-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="87933-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="87933-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="87933-107">Arguments</span></span>

<span data-ttu-id="87933-108">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="87933-108">`text`: *String*</span></span>

<span data-ttu-id="87933-109">Valeur de texte qui doit être convertie en nombre *Réel*.</span><span class="sxs-lookup"><span data-stu-id="87933-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="87933-110">`decimal separator` : Chaîne</span><span class="sxs-lookup"><span data-stu-id="87933-110">`decimal separator`: String</span></span>

<span data-ttu-id="87933-111">Séparateur décimal.</span><span class="sxs-lookup"><span data-stu-id="87933-111">A decimal separator.</span></span> <span data-ttu-id="87933-112">Il est utilisé pour séparer les parties entières et fractionnaires d’un nombre décimal.</span><span class="sxs-lookup"><span data-stu-id="87933-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="87933-113">`digit grouping separator` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="87933-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="87933-114">Séparateur de regroupement de chiffres.</span><span class="sxs-lookup"><span data-stu-id="87933-114">A digit grouping separator.</span></span> <span data-ttu-id="87933-115">Il est utilisé comme séparateur de milliers.</span><span class="sxs-lookup"><span data-stu-id="87933-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="87933-116">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="87933-116">Return values</span></span>

<span data-ttu-id="87933-117">*Réel*</span><span class="sxs-lookup"><span data-stu-id="87933-117">*Real*</span></span>

<span data-ttu-id="87933-118">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="87933-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="87933-119">Exemple</span><span class="sxs-lookup"><span data-stu-id="87933-119">Example</span></span>

<span data-ttu-id="87933-120">`NUMBERVALUE( "1 234,56", ",", " ")` renvoie **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="87933-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="87933-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="87933-121">Additional resources</span></span>

[<span data-ttu-id="87933-122">Fonctions de conversion des types</span><span class="sxs-lookup"><span data-stu-id="87933-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
