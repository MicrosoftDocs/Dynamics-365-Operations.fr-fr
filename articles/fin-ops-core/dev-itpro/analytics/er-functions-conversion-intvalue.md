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
ms.openlocfilehash: 5e06236bf1d158a4cf579b8b89cc0a5f7d815c38
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042647"
---
# <span data-ttu-id="fb302-103"><a name="INTVALUE">Fonction INTVALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="fb302-103"><a name="INTVALUE">INTVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb302-104">La fonction `INTVALUE` renvoie une valeur *Int* qui représente la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="fb302-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="fb302-105">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="fb302-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="fb302-106">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="fb302-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="fb302-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="fb302-107">Arguments</span></span>

<span data-ttu-id="fb302-108">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="fb302-108">`text`: *String*</span></span>

<span data-ttu-id="fb302-109">Valeur de texte qui doit être convertie en nombre *Int*.</span><span class="sxs-lookup"><span data-stu-id="fb302-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="fb302-110">`number` : *Réel* ou *Entier*</span><span class="sxs-lookup"><span data-stu-id="fb302-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="fb302-111">Valeur *Réel* ou *Entier* numérique qui doit être convertie en nombre *Int*.</span><span class="sxs-lookup"><span data-stu-id="fb302-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="fb302-112">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="fb302-112">Return values</span></span>

<span data-ttu-id="fb302-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="fb302-113">*Int*</span></span>

<span data-ttu-id="fb302-114">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="fb302-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fb302-115">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="fb302-115">Usage notes</span></span>

<span data-ttu-id="fb302-116">Les décimales sont tronquées.</span><span class="sxs-lookup"><span data-stu-id="fb302-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="fb302-117">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="fb302-117">Example 1</span></span>

<span data-ttu-id="fb302-118">`INTVALUE ("100.77")` renvoie la valeur *Int* **100**.</span><span class="sxs-lookup"><span data-stu-id="fb302-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="fb302-119">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="fb302-119">Example 2</span></span>

<span data-ttu-id="fb302-120">`INTVALUE (-100.77)` renvoie la valeur *Int* **-100**.</span><span class="sxs-lookup"><span data-stu-id="fb302-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fb302-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fb302-121">Additional resources</span></span>

[<span data-ttu-id="fb302-122">Fonctions de conversion des types</span><span class="sxs-lookup"><span data-stu-id="fb302-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
