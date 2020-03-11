---
title: Fonction POWER ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction POWER États électroniques (ER).
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
ms.openlocfilehash: c57222d7fcc133faa679bab43431272c984c9d8b
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041628"
---
# <span data-ttu-id="5b5ec-103"><a name="POWER">Fonction POWER ER</a></span><span class="sxs-lookup"><span data-stu-id="5b5ec-103"><a name="POWER">POWER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b5ec-104">La fonction `POWER` renvoie une valeur de *Réel* qui représente le résultat de l'augmentation du nombre positif spécifié à la puissance spécifiée.</span><span class="sxs-lookup"><span data-stu-id="5b5ec-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="5b5ec-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5b5ec-105">Syntax</span></span>

```vb
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="5b5ec-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="5b5ec-106">Arguments</span></span>

<span data-ttu-id="5b5ec-107">`number` : *Réel* ou *Entier*</span><span class="sxs-lookup"><span data-stu-id="5b5ec-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="5b5ec-108">Valeur numérique qui doit être élevée à la puissance spécifiée.</span><span class="sxs-lookup"><span data-stu-id="5b5ec-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="5b5ec-109">`power` : *Réel* ou *Entier*</span><span class="sxs-lookup"><span data-stu-id="5b5ec-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="5b5ec-110">Valeur numérique qui représente la puissance spécifique.</span><span class="sxs-lookup"><span data-stu-id="5b5ec-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="5b5ec-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="5b5ec-111">Return values</span></span>

<span data-ttu-id="5b5ec-112">*Réel*</span><span class="sxs-lookup"><span data-stu-id="5b5ec-112">*Real*</span></span>

<span data-ttu-id="5b5ec-113">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="5b5ec-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="5b5ec-114">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="5b5ec-114">Example 1</span></span>

<span data-ttu-id="5b5ec-115">`POWER (10, 2)` renvoie **100**.</span><span class="sxs-lookup"><span data-stu-id="5b5ec-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="5b5ec-116">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="5b5ec-116">Example 2</span></span>

<span data-ttu-id="5b5ec-117">`POWER (4, 0.5)` renvoie **2**.</span><span class="sxs-lookup"><span data-stu-id="5b5ec-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5b5ec-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5b5ec-118">Additional resources</span></span>

[<span data-ttu-id="5b5ec-119">Fonctions mathématiques</span><span class="sxs-lookup"><span data-stu-id="5b5ec-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)
