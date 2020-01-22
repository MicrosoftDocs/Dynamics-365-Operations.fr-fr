---
title: Fonction NOT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction NOT États électroniques (ER).
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
ms.openlocfilehash: b15277dba26dc7864193b11a127944daca6b989f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916037"
---
# <span data-ttu-id="348f2-103"><a name="NOT">Fonction NOT ER</a></span><span class="sxs-lookup"><span data-stu-id="348f2-103"><a name="NOT">NOT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="348f2-104">La fonction `NOT` renvoie la valeur logique inversée de la condition spécifiée en tant que valeur *Booléenne*.</span><span class="sxs-lookup"><span data-stu-id="348f2-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="348f2-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="348f2-105">Syntax</span></span>

```
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="348f2-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="348f2-106">Arguments</span></span>

<span data-ttu-id="348f2-107">`condition` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="348f2-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="348f2-108">Expression conditionnelle valide qui doit être inversée.</span><span class="sxs-lookup"><span data-stu-id="348f2-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="348f2-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="348f2-109">Return values</span></span>

<span data-ttu-id="348f2-110">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="348f2-110">*Boolean*</span></span>

<span data-ttu-id="348f2-111">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="348f2-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="348f2-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="348f2-112">Example</span></span>

<span data-ttu-id="348f2-113">`NOT (TRUE)` renvoie **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="348f2-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="348f2-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="348f2-114">Additional resources</span></span>

[<span data-ttu-id="348f2-115">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="348f2-115">Logical functions</span></span>](er-functions-category-logical.md)
