---
title: Fonction NUMBERVALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction NUMBERVALUE États électroniques (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 84d7f17f37a83547522cf09047b72100f6f5b859
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755346"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="6c9ad-103">Fonction NUMBERVALUE ER</span><span class="sxs-lookup"><span data-stu-id="6c9ad-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6c9ad-104">La fonction `NUMBERVALUE` renvoie une valeur de *Réel* convertie à partir de la valeur de *Chaîne* spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6c9ad-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="6c9ad-105">Lors de la conversion, les séparateurs de regroupements décimaux et numériques spécifiés sont pris en compte.</span><span class="sxs-lookup"><span data-stu-id="6c9ad-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c9ad-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6c9ad-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="6c9ad-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="6c9ad-107">Arguments</span></span>

<span data-ttu-id="6c9ad-108">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="6c9ad-108">`text`: *String*</span></span>

<span data-ttu-id="6c9ad-109">Valeur de texte qui doit être convertie en nombre *Réel*.</span><span class="sxs-lookup"><span data-stu-id="6c9ad-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="6c9ad-110">`decimal separator` : Chaîne</span><span class="sxs-lookup"><span data-stu-id="6c9ad-110">`decimal separator`: String</span></span>

<span data-ttu-id="6c9ad-111">Séparateur décimal.</span><span class="sxs-lookup"><span data-stu-id="6c9ad-111">A decimal separator.</span></span> <span data-ttu-id="6c9ad-112">Il est utilisé pour séparer les parties entières et fractionnaires d’un nombre décimal.</span><span class="sxs-lookup"><span data-stu-id="6c9ad-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="6c9ad-113">`digit grouping separator` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="6c9ad-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="6c9ad-114">Séparateur de regroupement de chiffres.</span><span class="sxs-lookup"><span data-stu-id="6c9ad-114">A digit grouping separator.</span></span> <span data-ttu-id="6c9ad-115">Il est utilisé comme séparateur de milliers.</span><span class="sxs-lookup"><span data-stu-id="6c9ad-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="6c9ad-116">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="6c9ad-116">Return values</span></span>

<span data-ttu-id="6c9ad-117">*Réel*</span><span class="sxs-lookup"><span data-stu-id="6c9ad-117">*Real*</span></span>

<span data-ttu-id="6c9ad-118">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="6c9ad-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="6c9ad-119">Exemple</span><span class="sxs-lookup"><span data-stu-id="6c9ad-119">Example</span></span>

<span data-ttu-id="6c9ad-120">`NUMBERVALUE( "1 234,56", ",", " ")` renvoie **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="6c9ad-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6c9ad-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6c9ad-121">Additional resources</span></span>

[<span data-ttu-id="6c9ad-122">Fonctions de conversion des types</span><span class="sxs-lookup"><span data-stu-id="6c9ad-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]