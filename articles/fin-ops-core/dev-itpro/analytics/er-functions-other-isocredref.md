---
title: Fonction ISOCREDREF ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ISOCREDREF États électroniques (ER).
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
ms.openlocfilehash: d6e5d025e7de15c27b19711ea5b597d75bdf3d41
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744093"
---
# <a name="isocredref-er-function"></a><span data-ttu-id="bc988-103">Fonction ISOCREDREF ER</span><span class="sxs-lookup"><span data-stu-id="bc988-103">ISOCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bc988-104">La fonction `ISOCREDREF` renvoie une valeur de *Chaîne* qui représente une référence créditeur ISO (Organisation internationale de normalisation), en fonction des chiffres et des symboles alphabétiques du numéro de facture spécifié.</span><span class="sxs-lookup"><span data-stu-id="bc988-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="bc988-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="bc988-105">Syntax</span></span>

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="bc988-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="bc988-106">Arguments</span></span>

<span data-ttu-id="bc988-107">`invoice number digits` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="bc988-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="bc988-108">Valeur de texte qui représente les chiffres d’un numéro de facture.</span><span class="sxs-lookup"><span data-stu-id="bc988-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="bc988-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="bc988-109">Return values</span></span>

<span data-ttu-id="bc988-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="bc988-110">*String*</span></span>

<span data-ttu-id="bc988-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="bc988-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bc988-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="bc988-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="bc988-113">Pour éliminer des symboles de l’alphabet qui ne sont pas conformes à la norme ISO, l’argument `invoice number digits` doit être traduit avant d’être transmis à cette fonction.</span><span class="sxs-lookup"><span data-stu-id="bc988-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="bc988-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="bc988-114">Example</span></span>

<span data-ttu-id="bc988-115">`ISOCredRef ("VEND-200002")` renvoie **« RF23VEND-200002 »**.</span><span class="sxs-lookup"><span data-stu-id="bc988-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bc988-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="bc988-116">Additional resources</span></span>

[<span data-ttu-id="bc988-117">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="bc988-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
