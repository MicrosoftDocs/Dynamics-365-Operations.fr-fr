---
title: Fonction INT64VALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction INT64VALUE États électroniques (ER).
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
ms.openlocfilehash: 9db2e9abcac36a8331a494c886218bbfc82e93aa
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561492"
---
# <a name="int64value-er-function"></a><span data-ttu-id="80572-103">Fonction INT64VALUE ER</span><span class="sxs-lookup"><span data-stu-id="80572-103">INT64VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="80572-104">La fonction `INT64VALUE` renvoie une valeur *Int64* qui représente la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="80572-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="80572-105">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="80572-105">Syntax 1</span></span>

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="80572-106">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="80572-106">Syntax 2</span></span>

```vb
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="80572-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="80572-107">Arguments</span></span>

<span data-ttu-id="80572-108">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="80572-108">`text`: *String*</span></span>

<span data-ttu-id="80572-109">Valeur de texte qui doit être convertie en nombre *Int64*.</span><span class="sxs-lookup"><span data-stu-id="80572-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="80572-110">`number` : *Réel* ou *Entier*</span><span class="sxs-lookup"><span data-stu-id="80572-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="80572-111">Valeur *Réel* ou *Entier* numérique qui doit être convertie en nombre *Int64*.</span><span class="sxs-lookup"><span data-stu-id="80572-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="80572-112">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="80572-112">Return values</span></span>

<span data-ttu-id="80572-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="80572-113">*Int64*</span></span>

<span data-ttu-id="80572-114">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="80572-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="80572-115">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="80572-115">Usage notes</span></span>

<span data-ttu-id="80572-116">Les décimales sont tronquées.</span><span class="sxs-lookup"><span data-stu-id="80572-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="80572-117">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="80572-117">Example 1</span></span>

<span data-ttu-id="80572-118">`INT64VALUE ("22565422744")` renvoie la valeur *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="80572-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="80572-119">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="80572-119">Example 2</span></span>

<span data-ttu-id="80572-120">`INT64VALUE ( VALUE("22565422744.77"))` renvoie la valeur *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="80572-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="80572-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="80572-121">Additional resources</span></span>

[<span data-ttu-id="80572-122">Fonctions de conversion des types</span><span class="sxs-lookup"><span data-stu-id="80572-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]