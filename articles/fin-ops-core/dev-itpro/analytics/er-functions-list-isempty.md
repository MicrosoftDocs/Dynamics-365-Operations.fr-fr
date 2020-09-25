---
title: Fonction ISEMPTY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ISEMPTY États électroniques (ER).
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
ms.openlocfilehash: 5b6fde7cbadec7aae052742ef598e1af4dbae793
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745127"
---
# <a name="isempty-er-function"></a><span data-ttu-id="572ec-103">Fonction ISEMPTY ER</span><span class="sxs-lookup"><span data-stu-id="572ec-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="572ec-104">La fonction `ISEMPTY` renvoie une valeur *Booléenne* de **TRUE** si la liste spécifiée ne contient aucun enregistrement.</span><span class="sxs-lookup"><span data-stu-id="572ec-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="572ec-105">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="572ec-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="572ec-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="572ec-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="572ec-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="572ec-107">Arguments</span></span>

<span data-ttu-id="572ec-108">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="572ec-108">`list`: *Record list*</span></span>

<span data-ttu-id="572ec-109">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="572ec-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="572ec-110">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="572ec-110">Return values</span></span>

<span data-ttu-id="572ec-111">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="572ec-111">*Boolean*</span></span>

<span data-ttu-id="572ec-112">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="572ec-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="572ec-113">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="572ec-113">Example 1</span></span>

<span data-ttu-id="572ec-114">Si vous entrez une source de données **DS** de type *Champ calculé*, et qu’elle contient l’expression `SPLIT ("A|B|C", "|")`, l’expression `ISEMPTY(DS)` renvoie **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="572ec-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="572ec-115">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="572ec-115">Example 2</span></span>

<span data-ttu-id="572ec-116">L’expression `ISEMPTY (SPLIT ("",1))` renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="572ec-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="572ec-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="572ec-117">Additional resources</span></span>

[<span data-ttu-id="572ec-118">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="572ec-118">List functions</span></span>](er-functions-category-list.md)
