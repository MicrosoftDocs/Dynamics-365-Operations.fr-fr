---
title: Fonction PADLEFT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction PADLEFT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 3f8a8e2006fe279b25bbf154c6e1802babf51117
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744357"
---
# <a name="padleft-er-function"></a><span data-ttu-id="fb25d-103">Fonction PADLEFT ER</span><span class="sxs-lookup"><span data-stu-id="fb25d-103">PADLEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb25d-104">La fonction `PADLEFT` renvoie une valeur de *Chaîne* de longueur spécifique, où le début de la chaîne spécifiée est entouré par les caractères spécifiés.</span><span class="sxs-lookup"><span data-stu-id="fb25d-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb25d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fb25d-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="fb25d-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="fb25d-106">Arguments</span></span>

<span data-ttu-id="fb25d-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="fb25d-107">`text`: *String*</span></span>

<span data-ttu-id="fb25d-108">Valeur *Chaîne* qui représente le texte d’origine.</span><span class="sxs-lookup"><span data-stu-id="fb25d-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="fb25d-109">`length` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="fb25d-109">`length`: *Integer*</span></span>

<span data-ttu-id="fb25d-110">Valeur *Entier* qui représente le nombre final de caractères dans la chaîne entourée.</span><span class="sxs-lookup"><span data-stu-id="fb25d-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="fb25d-111">`padding chars` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="fb25d-111">`padding chars`: *String*</span></span>

<span data-ttu-id="fb25d-112">Les caractères à utiliser pour entourer.</span><span class="sxs-lookup"><span data-stu-id="fb25d-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="fb25d-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="fb25d-113">Return values</span></span>

<span data-ttu-id="fb25d-114">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="fb25d-114">*String*</span></span>

<span data-ttu-id="fb25d-115">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="fb25d-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="fb25d-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="fb25d-116">Example</span></span>

<span data-ttu-id="fb25d-117">`PADLEFT ("1234", 10, "`&nbsp;`")` renvoie la chaîne de texte **« &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234 »**.</span><span class="sxs-lookup"><span data-stu-id="fb25d-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fb25d-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fb25d-118">Additional resources</span></span>

[<span data-ttu-id="fb25d-119">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="fb25d-119">Text functions</span></span>](er-functions-category-text.md)
