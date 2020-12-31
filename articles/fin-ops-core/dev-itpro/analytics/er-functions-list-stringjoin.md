---
title: Fonction STRINGJOIN ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction STRINGJOIN États électroniques (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 586dbcb98d237325188f4b0384580613ab7a9347
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683731"
---
# <a name="stringjoin-er-function"></a><span data-ttu-id="577c0-103">Fonction STRINGJOIN ER</span><span class="sxs-lookup"><span data-stu-id="577c0-103">STRINGJOIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="577c0-104">La fonction `STRINGJOIN` renvoie une valeur de *Chaîne* composée des valeurs concaténées du champ spécifié dans la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="577c0-104">The `STRINGJOIN` function returns a *String* value that consists of concatenated values of the specified field from the specified list.</span></span> <span data-ttu-id="577c0-105">Les valeurs peuvent être séparées par le séparateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="577c0-105">The values can be separated by the specified delimiter.</span></span>

## <a name="syntax"></a><span data-ttu-id="577c0-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="577c0-106">Syntax</span></span>

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a><span data-ttu-id="577c0-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="577c0-107">Arguments</span></span>

<span data-ttu-id="577c0-108">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="577c0-108">`list`: *Record list*</span></span>

<span data-ttu-id="577c0-109">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="577c0-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="577c0-110">`field` : *Champ*</span><span class="sxs-lookup"><span data-stu-id="577c0-110">`field`: *Field*</span></span>

<span data-ttu-id="577c0-111">Chemin d’accès valide d’un champ de type de données *Chaîne* dans la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="577c0-111">The valid path of a field of the *String* data type in the specified list.</span></span>

<span data-ttu-id="577c0-112">`delimiter` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="577c0-112">`delimiter`: *String*</span></span>

<span data-ttu-id="577c0-113">Délimiteur utilisé pour séparer les sous-chaînes.</span><span class="sxs-lookup"><span data-stu-id="577c0-113">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="577c0-114">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="577c0-114">Return values</span></span>

<span data-ttu-id="577c0-115">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="577c0-115">*String*</span></span>

<span data-ttu-id="577c0-116">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="577c0-116">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="577c0-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="577c0-117">Example</span></span>

<span data-ttu-id="577c0-118">Si vous entrez `SPLIT("abc" , 1)` comme source de données **DS**, l’expression `STRINGJOIN (DS, DS.Value, "-")` renvoie **« abc »**.</span><span class="sxs-lookup"><span data-stu-id="577c0-118">If you enter `SPLIT("abc" , 1)` as data source **DS**, the expression `STRINGJOIN (DS, DS.Value, "-")` returns **"a-b-c"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="577c0-119">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="577c0-119">Additional resources</span></span>

[<span data-ttu-id="577c0-120">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="577c0-120">List functions</span></span>](er-functions-category-list.md)
