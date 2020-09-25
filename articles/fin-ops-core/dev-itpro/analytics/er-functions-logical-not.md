---
title: Fonction NOT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction NOT États électroniques (ER).
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
ms.openlocfilehash: af588c3714069040fa339d3121e6eb404b9be979
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744645"
---
# <a name="not-er-function"></a><span data-ttu-id="173ce-103">Fonction NOT ER</span><span class="sxs-lookup"><span data-stu-id="173ce-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="173ce-104">La fonction `NOT` renvoie la valeur logique inversée de la condition spécifiée en tant que valeur *Booléenne*.</span><span class="sxs-lookup"><span data-stu-id="173ce-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="173ce-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="173ce-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="173ce-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="173ce-106">Arguments</span></span>

<span data-ttu-id="173ce-107">`condition` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="173ce-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="173ce-108">Expression conditionnelle valide qui doit être inversée.</span><span class="sxs-lookup"><span data-stu-id="173ce-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="173ce-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="173ce-109">Return values</span></span>

<span data-ttu-id="173ce-110">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="173ce-110">*Boolean*</span></span>

<span data-ttu-id="173ce-111">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="173ce-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="173ce-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="173ce-112">Example</span></span>

<span data-ttu-id="173ce-113">`NOT (TRUE)` renvoie **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="173ce-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="173ce-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="173ce-114">Additional resources</span></span>

[<span data-ttu-id="173ce-115">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="173ce-115">Logical functions</span></span>](er-functions-category-logical.md)
