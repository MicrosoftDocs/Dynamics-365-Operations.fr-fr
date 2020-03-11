---
title: Fonction CH_BANK_MOD_10 ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction CH_BANK_MOD_10 États électroniques (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 808e328bfcc35c96091da9a69850429b82a71070
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070573"
---
# <span data-ttu-id="5cfe6-103"><a name="CH_BANK_MOD_10">Fonction CH_BANK_MOD_10 ER</a></span><span class="sxs-lookup"><span data-stu-id="5cfe6-103"><a name="CH_BANK_MOD_10">CH_BANK_MOD_10 ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5cfe6-104">La fonction `CH_BANK_MOD_10` renvoie une valeur *Chaîne* qui représente une référence de créancier en tant qu'expression MOD10, sur la base des chiffres du numéro de facture spécifié.</span><span class="sxs-lookup"><span data-stu-id="5cfe6-104">The `CH_BANK_MOD_10` function returns a *String* value that represents a creditor reference as an MOD10 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="5cfe6-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5cfe6-105">Syntax</span></span>

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="5cfe6-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="5cfe6-106">Arguments</span></span>

<span data-ttu-id="5cfe6-107">`invoice number digits` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="5cfe6-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="5cfe6-108">Valeur de texte qui représente les chiffres d'un numéro de facture.</span><span class="sxs-lookup"><span data-stu-id="5cfe6-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="5cfe6-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="5cfe6-109">Return values</span></span>

<span data-ttu-id="5cfe6-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="5cfe6-110">*String*</span></span>

<span data-ttu-id="5cfe6-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="5cfe6-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="5cfe6-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="5cfe6-112">Example</span></span>

<span data-ttu-id="5cfe6-113">`CH_BANK_MOD_10 ("VEND-200002")` renvoie **3**.</span><span class="sxs-lookup"><span data-stu-id="5cfe6-113">`CH_BANK_MOD_10 ("VEND-200002")` returns **3**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5cfe6-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5cfe6-114">Additional resources</span></span>

[<span data-ttu-id="5cfe6-115">Autre fonctions (spécifiques au domaine d'affaires)</span><span class="sxs-lookup"><span data-stu-id="5cfe6-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
