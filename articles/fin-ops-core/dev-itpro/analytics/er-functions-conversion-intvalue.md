---
title: Fonction INTVALUE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction INTVALUE États électroniques (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2b279de39cf91c3919145735518034fc60cd3341
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917716"
---
# <span data-ttu-id="7d6cc-103"><a name="INTVALUE">Fonction INTVALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="7d6cc-103"><a name="INTVALUE">INTVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7d6cc-104">La fonction `INTVALUE` renvoie une valeur *Int* qui représente la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="7d6cc-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="7d6cc-105">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="7d6cc-105">Syntax 1</span></span>

```
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="7d6cc-106">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="7d6cc-106">Syntax 2</span></span>

```
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="7d6cc-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="7d6cc-107">Arguments</span></span>

<span data-ttu-id="7d6cc-108">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="7d6cc-108">`text`: *String*</span></span>

<span data-ttu-id="7d6cc-109">Valeur de texte qui doit être convertie en nombre *Int*.</span><span class="sxs-lookup"><span data-stu-id="7d6cc-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="7d6cc-110">`number` : *Réel* ou *Entier*</span><span class="sxs-lookup"><span data-stu-id="7d6cc-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="7d6cc-111">Valeur *Réel* ou *Entier* numérique qui doit être convertie en nombre *Int*.</span><span class="sxs-lookup"><span data-stu-id="7d6cc-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="7d6cc-112">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="7d6cc-112">Return values</span></span>

<span data-ttu-id="7d6cc-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="7d6cc-113">*Int*</span></span>

<span data-ttu-id="7d6cc-114">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="7d6cc-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7d6cc-115">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="7d6cc-115">Usage notes</span></span>

<span data-ttu-id="7d6cc-116">Les décimales sont tronquées.</span><span class="sxs-lookup"><span data-stu-id="7d6cc-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="7d6cc-117">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="7d6cc-117">Example 1</span></span>

<span data-ttu-id="7d6cc-118">`INTVALUE ("100.77")` renvoie la valeur *Int* **100**.</span><span class="sxs-lookup"><span data-stu-id="7d6cc-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="7d6cc-119">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="7d6cc-119">Example 2</span></span>

<span data-ttu-id="7d6cc-120">`INTVALUE (-100.77)` renvoie la valeur *Int* **-100**.</span><span class="sxs-lookup"><span data-stu-id="7d6cc-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7d6cc-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7d6cc-121">Additional resources</span></span>

[<span data-ttu-id="7d6cc-122">Fonctions de conversion des types</span><span class="sxs-lookup"><span data-stu-id="7d6cc-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
