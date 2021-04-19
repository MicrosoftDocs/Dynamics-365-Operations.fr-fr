---
title: Fonction CH_BANK_MOD_10 ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CH_BANK_MOD_10 États électroniques (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 92750ca7e7396077d8c56c3b336f495c228dddce
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744413"
---
# <a name="ch_bank_mod_10-er-function"></a><span data-ttu-id="ea08c-103">Fonction CH_BANK_MOD_10 ER</span><span class="sxs-lookup"><span data-stu-id="ea08c-103">CH_BANK_MOD_10 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea08c-104">La fonction `CH_BANK_MOD_10` renvoie une valeur *Chaîne* qui représente une référence de créancier en tant qu’expression MOD10, sur la base des chiffres du numéro de facture spécifié.</span><span class="sxs-lookup"><span data-stu-id="ea08c-104">The `CH_BANK_MOD_10` function returns a *String* value that represents a creditor reference as an MOD10 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="ea08c-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ea08c-105">Syntax</span></span>

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="ea08c-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="ea08c-106">Arguments</span></span>

<span data-ttu-id="ea08c-107">`invoice number digits` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ea08c-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="ea08c-108">Valeur de texte qui représente les chiffres d’un numéro de facture.</span><span class="sxs-lookup"><span data-stu-id="ea08c-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="ea08c-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="ea08c-109">Return values</span></span>

<span data-ttu-id="ea08c-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ea08c-110">*String*</span></span>

<span data-ttu-id="ea08c-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="ea08c-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="ea08c-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="ea08c-112">Example</span></span>

<span data-ttu-id="ea08c-113">`CH_BANK_MOD_10 ("VEND-200002")` renvoie **3**.</span><span class="sxs-lookup"><span data-stu-id="ea08c-113">`CH_BANK_MOD_10 ("VEND-200002")` returns **3**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ea08c-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ea08c-114">Additional resources</span></span>

[<span data-ttu-id="ea08c-115">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="ea08c-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]