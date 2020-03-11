---
title: Fonction INT64VALUE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction INT64VALUE États électroniques (ER).
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
ms.openlocfilehash: 7fcb8a617507801d82d16175e9e86c9193091a12
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042686"
---
# <span data-ttu-id="f98ad-103"><a name="INT64VALUE">Fonction INT64VALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="f98ad-103"><a name="INT64VALUE">INT64VALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f98ad-104">La fonction `INT64VALUE` renvoie une valeur *Int64* qui représente la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="f98ad-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="f98ad-105">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="f98ad-105">Syntax 1</span></span>

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="f98ad-106">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="f98ad-106">Syntax 2</span></span>

```vb
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="f98ad-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="f98ad-107">Arguments</span></span>

<span data-ttu-id="f98ad-108">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="f98ad-108">`text`: *String*</span></span>

<span data-ttu-id="f98ad-109">Valeur de texte qui doit être convertie en nombre *Int64*.</span><span class="sxs-lookup"><span data-stu-id="f98ad-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="f98ad-110">`number` : *Réel* ou *Entier*</span><span class="sxs-lookup"><span data-stu-id="f98ad-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="f98ad-111">Valeur *Réel* ou *Entier* numérique qui doit être convertie en nombre *Int64*.</span><span class="sxs-lookup"><span data-stu-id="f98ad-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="f98ad-112">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="f98ad-112">Return values</span></span>

<span data-ttu-id="f98ad-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="f98ad-113">*Int64*</span></span>

<span data-ttu-id="f98ad-114">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="f98ad-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f98ad-115">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="f98ad-115">Usage notes</span></span>

<span data-ttu-id="f98ad-116">Les décimales sont tronquées.</span><span class="sxs-lookup"><span data-stu-id="f98ad-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="f98ad-117">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="f98ad-117">Example 1</span></span>

<span data-ttu-id="f98ad-118">`INT64VALUE ("22565422744")` renvoie la valeur *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="f98ad-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="f98ad-119">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="f98ad-119">Example 2</span></span>

<span data-ttu-id="f98ad-120">`INT64VALUE ( VALUE("22565422744.77"))` renvoie la valeur *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="f98ad-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f98ad-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f98ad-121">Additional resources</span></span>

[<span data-ttu-id="f98ad-122">Fonctions de conversion des types</span><span class="sxs-lookup"><span data-stu-id="f98ad-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
