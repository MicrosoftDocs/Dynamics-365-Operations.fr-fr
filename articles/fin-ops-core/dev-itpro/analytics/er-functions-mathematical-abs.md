---
title: Fonction ABS ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction ABS États électroniques (ER).
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
ms.openlocfilehash: 214fb2808f024487795f27de45de1d4de8cead2d
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041651"
---
# <span data-ttu-id="d128e-103"><a name="ABS">Fonction ABS ER</a></span><span class="sxs-lookup"><span data-stu-id="d128e-103"><a name="ABS">ABS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d128e-104">La fonction `ABS` renvoie la valeur absolue (module) du nombre spécifié en tant que valeur *Réelle*.</span><span class="sxs-lookup"><span data-stu-id="d128e-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="d128e-105">En d'autres termes, elle renvoie le nombre sans son signe.</span><span class="sxs-lookup"><span data-stu-id="d128e-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="d128e-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d128e-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="d128e-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="d128e-107">Arguments</span></span>

<span data-ttu-id="d128e-108">`number` : *Réel*</span><span class="sxs-lookup"><span data-stu-id="d128e-108">`number`: *Real*</span></span>

<span data-ttu-id="d128e-109">Valeur numérique dont vous voulez le module.</span><span class="sxs-lookup"><span data-stu-id="d128e-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="d128e-110">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="d128e-110">Return values</span></span>

<span data-ttu-id="d128e-111">*Réel*</span><span class="sxs-lookup"><span data-stu-id="d128e-111">*Real*</span></span>

<span data-ttu-id="d128e-112">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="d128e-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="d128e-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="d128e-113">Example</span></span>

<span data-ttu-id="d128e-114">`ABS (-1)` renvoie **1**.</span><span class="sxs-lookup"><span data-stu-id="d128e-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d128e-115">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d128e-115">Additional resources</span></span>

[<span data-ttu-id="d128e-116">Fonctions mathématiques</span><span class="sxs-lookup"><span data-stu-id="d128e-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)
