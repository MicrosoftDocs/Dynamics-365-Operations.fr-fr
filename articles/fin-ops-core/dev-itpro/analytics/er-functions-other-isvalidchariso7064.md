---
title: Fonction ISVALIDCHARACTERISO7064 ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ISVALIDCHARACTERISO7064 États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: c3bceb15bbe1dc65abc88c1229459707a6166482
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680660"
---
# <a name="isvalidcharacteriso7064-er-function"></a><span data-ttu-id="4a239-103">Fonction ISVALIDCHARACTERISO7064 ER</span><span class="sxs-lookup"><span data-stu-id="4a239-103">ISVALIDCHARACTERISO7064 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4a239-104">La fonction `ISVALIDCHARACTERISO7064` renvoie une valeur *Booléenne* de **TRUE** si la chaîne donnée représente un numéro de compte bancaire international (IBAN) valide.</span><span class="sxs-lookup"><span data-stu-id="4a239-104">The `ISVALIDCHARACTERISO7064` function returns a *Boolean* value of **TRUE** if the specified string represents a valid international bank account number (IBAN).</span></span> <span data-ttu-id="4a239-105">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="4a239-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a239-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4a239-106">Syntax</span></span>

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a><span data-ttu-id="4a239-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="4a239-107">Arguments</span></span>

<span data-ttu-id="4a239-108">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="4a239-108">`text`: *String*</span></span>

<span data-ttu-id="4a239-109">Valeur de texte qui représente un IBAN.</span><span class="sxs-lookup"><span data-stu-id="4a239-109">A text value that represents an IBAN.</span></span>

## <a name="return-values"></a><span data-ttu-id="4a239-110">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="4a239-110">Return values</span></span>

<span data-ttu-id="4a239-111">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="4a239-111">*String*</span></span>

<span data-ttu-id="4a239-112">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="4a239-112">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="4a239-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="4a239-113">Example</span></span>

<span data-ttu-id="4a239-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="4a239-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returns **TRUE**.</span></span> 

<span data-ttu-id="4a239-115">`ISVALIDCHARACTERISO7064 ("AT61")` renvoie **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="4a239-115">`ISVALIDCHARACTERISO7064 ("AT61")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4a239-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4a239-116">Additional resources</span></span>

[<span data-ttu-id="4a239-117">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="4a239-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
