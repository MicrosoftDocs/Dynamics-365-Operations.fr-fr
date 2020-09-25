---
title: Fonction CURCREDREF ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CURCREDREF États électroniques (ER).
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
ms.openlocfilehash: 95e90289f43896b83ba98a6edefe0cd6028f4043
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744189"
---
# <a name="curcredref-er-function"></a><span data-ttu-id="2061d-103">Fonction CURCREDREF ER</span><span class="sxs-lookup"><span data-stu-id="2061d-103">CURCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2061d-104">La fonction `CURCREDREF` renvoie une valeur *Chaîne* qui représente une référence de créancier, sur la base des chiffres du numéro de facture spécifié.</span><span class="sxs-lookup"><span data-stu-id="2061d-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="2061d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2061d-105">Syntax</span></span>

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="2061d-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="2061d-106">Arguments</span></span>

<span data-ttu-id="2061d-107">`invoice number digits` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="2061d-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="2061d-108">Valeur de texte qui représente les chiffres d’un numéro de facture.</span><span class="sxs-lookup"><span data-stu-id="2061d-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="2061d-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="2061d-109">Return values</span></span>

<span data-ttu-id="2061d-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="2061d-110">*String*</span></span>

<span data-ttu-id="2061d-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="2061d-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="2061d-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="2061d-112">Example</span></span>

<span data-ttu-id="2061d-113">`CURCredRef ("VEND-200002")` renvoie **« 2200002 »**.</span><span class="sxs-lookup"><span data-stu-id="2061d-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2061d-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2061d-114">Additional resources</span></span>

[<span data-ttu-id="2061d-115">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="2061d-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
