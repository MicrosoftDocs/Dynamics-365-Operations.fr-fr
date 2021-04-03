---
title: Fonction INTVALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction INTVALUE États électroniques (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 64f43ad29d59ade1e124b6800734b003f6ca07df
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561468"
---
# <a name="intvalue-er-function"></a><span data-ttu-id="0a7b8-103">Fonction INTVALUE ER</span><span class="sxs-lookup"><span data-stu-id="0a7b8-103">INTVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a7b8-104">La fonction `INTVALUE` renvoie une valeur *Int* qui représente la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="0a7b8-105">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="0a7b8-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="0a7b8-106">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="0a7b8-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="0a7b8-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="0a7b8-107">Arguments</span></span>

<span data-ttu-id="0a7b8-108">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="0a7b8-108">`text`: *String*</span></span>

<span data-ttu-id="0a7b8-109">Valeur de texte qui doit être convertie en nombre *Int*.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="0a7b8-110">`number` : *Réel* ou *Entier*</span><span class="sxs-lookup"><span data-stu-id="0a7b8-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="0a7b8-111">Valeur *Réel* ou *Entier* numérique qui doit être convertie en nombre *Int*.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="0a7b8-112">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="0a7b8-112">Return values</span></span>

<span data-ttu-id="0a7b8-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="0a7b8-113">*Int*</span></span>

<span data-ttu-id="0a7b8-114">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0a7b8-115">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="0a7b8-115">Usage notes</span></span>

<span data-ttu-id="0a7b8-116">Les décimales sont tronquées.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="0a7b8-117">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="0a7b8-117">Example 1</span></span>

<span data-ttu-id="0a7b8-118">`INTVALUE ("100.77")` renvoie la valeur *Int* **100**.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="0a7b8-119">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="0a7b8-119">Example 2</span></span>

<span data-ttu-id="0a7b8-120">`INTVALUE (-100.77)` renvoie la valeur *Int* **-100**.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0a7b8-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0a7b8-121">Additional resources</span></span>

[<span data-ttu-id="0a7b8-122">Fonctions de conversion des types</span><span class="sxs-lookup"><span data-stu-id="0a7b8-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]