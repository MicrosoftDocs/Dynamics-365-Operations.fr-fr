---
title: Fonction NOT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction NOT États électroniques (ER).
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
ms.openlocfilehash: 7c10ed61b97dcd4d4a66a530bb3d08c539659233
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751708"
---
# <a name="not-er-function"></a><span data-ttu-id="fee79-103">Fonction NOT ER</span><span class="sxs-lookup"><span data-stu-id="fee79-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fee79-104">La fonction `NOT` renvoie la valeur logique inversée de la condition spécifiée en tant que valeur *Booléenne*.</span><span class="sxs-lookup"><span data-stu-id="fee79-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="fee79-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fee79-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="fee79-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="fee79-106">Arguments</span></span>

<span data-ttu-id="fee79-107">`condition` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="fee79-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="fee79-108">Expression conditionnelle valide qui doit être inversée.</span><span class="sxs-lookup"><span data-stu-id="fee79-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="fee79-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="fee79-109">Return values</span></span>

<span data-ttu-id="fee79-110">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="fee79-110">*Boolean*</span></span>

<span data-ttu-id="fee79-111">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="fee79-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="fee79-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="fee79-112">Example</span></span>

<span data-ttu-id="fee79-113">`NOT (TRUE)` renvoie **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="fee79-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fee79-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fee79-114">Additional resources</span></span>

[<span data-ttu-id="fee79-115">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="fee79-115">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]