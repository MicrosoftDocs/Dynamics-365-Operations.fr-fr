---
title: Fonction ISEMPTY ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction ISEMPTY États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: c8450c17fe2de964016951197b0d4e231c550a99
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916129"
---
# <span data-ttu-id="b2f01-103"><a name="ISEMPTY">Fonction ISEMPTY ER</a></span><span class="sxs-lookup"><span data-stu-id="b2f01-103"><a name="ISEMPTY">ISEMPTY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2f01-104">La fonction `ISEMPTY` renvoie une valeur *Booléenne* de **TRUE** si la liste spécifiée ne contient aucun enregistrement.</span><span class="sxs-lookup"><span data-stu-id="b2f01-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="b2f01-105">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="b2f01-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2f01-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b2f01-106">Syntax</span></span>

```
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="b2f01-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="b2f01-107">Arguments</span></span>

<span data-ttu-id="b2f01-108">`list` : *Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="b2f01-108">`list`: *Record list*</span></span>

<span data-ttu-id="b2f01-109">Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="b2f01-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="b2f01-110">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="b2f01-110">Return values</span></span>

<span data-ttu-id="b2f01-111">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="b2f01-111">*Boolean*</span></span>

<span data-ttu-id="b2f01-112">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="b2f01-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="b2f01-113">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="b2f01-113">Example 1</span></span>

<span data-ttu-id="b2f01-114">Si vous entrez une source de données **DS** de type *Champ calculé*, et qu'elle contient l'expression `SPLIT ("A|B|C", "|")`, l'expression `ISEMPTY(DS)` renvoie **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="b2f01-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="b2f01-115">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="b2f01-115">Example 2</span></span>

<span data-ttu-id="b2f01-116">L'expression `ISEMPTY (SPLIT ("",1))` renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="b2f01-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2f01-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b2f01-117">Additional resources</span></span>

[<span data-ttu-id="b2f01-118">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="b2f01-118">List functions</span></span>](er-functions-category-list.md)
