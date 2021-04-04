---
title: Fonction ISEMPTY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ISEMPTY États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: b689e6d4bb849f07db5d00cf8a9dc5c16646a927
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563870"
---
# <a name="isempty-er-function"></a><span data-ttu-id="2497a-103">Fonction ISEMPTY ER</span><span class="sxs-lookup"><span data-stu-id="2497a-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2497a-104">La fonction `ISEMPTY` renvoie une valeur *Booléenne* de **TRUE** si la liste spécifiée ne contient aucun enregistrement.</span><span class="sxs-lookup"><span data-stu-id="2497a-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="2497a-105">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="2497a-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="2497a-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2497a-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="2497a-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="2497a-107">Arguments</span></span>

<span data-ttu-id="2497a-108">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="2497a-108">`list`: *Record list*</span></span>

<span data-ttu-id="2497a-109">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="2497a-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="2497a-110">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="2497a-110">Return values</span></span>

<span data-ttu-id="2497a-111">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="2497a-111">*Boolean*</span></span>

<span data-ttu-id="2497a-112">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="2497a-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="2497a-113">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="2497a-113">Example 1</span></span>

<span data-ttu-id="2497a-114">Si vous entrez une source de données **DS** de type *Champ calculé*, et qu’elle contient l’expression `SPLIT ("A|B|C", "|")`, l’expression `ISEMPTY(DS)` renvoie **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="2497a-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="2497a-115">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="2497a-115">Example 2</span></span>

<span data-ttu-id="2497a-116">L’expression `ISEMPTY (SPLIT ("",1))` renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="2497a-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2497a-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2497a-117">Additional resources</span></span>

[<span data-ttu-id="2497a-118">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="2497a-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]