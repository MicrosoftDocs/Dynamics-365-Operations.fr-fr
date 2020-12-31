---
title: Liste des fonctions ER dans la catégorie logique
description: Cette rubrique fournit des informations sur les fonctions logiques prises en charge dans les États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 08/19/2020
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
ms.openlocfilehash: a37b3341b05fde1283a21a0c52faec26cd1a7030
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686182"
---
# <a name="list-of-er-functions-in-the-logical-category"></a><span data-ttu-id="e5f9c-103">Liste des fonctions ER dans la catégorie logique</span><span class="sxs-lookup"><span data-stu-id="e5f9c-103">List of ER functions in the logical category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e5f9c-104">Les fonctions logiques d’états électronique (ER) peuvent être utilisées pour utiliser des valeurs logiques afin d’effectuer plusieurs comparaisons en une seule expression ou de tester plusieurs conditions.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-104">Electronic reporting (ER) logical functions can be used to work with logical values to perform more than one comparison in a single expression or test multiple conditions.</span></span> <span data-ttu-id="e5f9c-105">Cette rubrique fournit un résumé de ces fonctions.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="e5f9c-106">Liste des fonctions prises en charge</span><span class="sxs-lookup"><span data-stu-id="e5f9c-106">List of supported functions</span></span>

| <span data-ttu-id="e5f9c-107">Fonction</span><span class="sxs-lookup"><span data-stu-id="e5f9c-107">Function</span></span> | <span data-ttu-id="e5f9c-108">Description</span><span class="sxs-lookup"><span data-stu-id="e5f9c-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="e5f9c-109">Et</span><span class="sxs-lookup"><span data-stu-id="e5f9c-109">And</span></span>](er-functions-logical-and.md)                       | <span data-ttu-id="e5f9c-110">Cette fonction renvoie une valeur *Booléenne* de **TRUE** si toutes les conditions spécifiées sont true.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-110">This function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="e5f9c-111">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-111">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="e5f9c-112">Dossier</span><span class="sxs-lookup"><span data-stu-id="e5f9c-112">Case</span></span>](er-functions-logical-case.md)                     | <span data-ttu-id="e5f9c-113">Cette fonction évalue la valeur de l’expression spécifiée par rapport aux options alternatives spécifiées et renvoie le résultat de la première option qui est égale à la valeur de l’expression spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-113">This function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="e5f9c-114">Sinon, elle renvoie un résultat par défaut facultatif, si un résultat par défaut est spécifié comme dernier argument de la fonction appelée qui n’est pas précédé d’une option.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-114">Otherwise, it returns an optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="e5f9c-115">La valeur renvoyée peut être une valeur de n’importe quel type de données pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-115">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="e5f9c-116">Si</span><span class="sxs-lookup"><span data-stu-id="e5f9c-116">If</span></span>](er-functions-logical-if.md)                         | <span data-ttu-id="e5f9c-117">Cette fonction renvoie la première valeur spécifiée si la condition spécifiée est remplie.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-117">This function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="e5f9c-118">Sinon, elle renvoie la deuxième valeur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-118">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="e5f9c-119">La valeur renvoyée peut être une valeur de n’importe quel type de données pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-119">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="e5f9c-120">Non</span><span class="sxs-lookup"><span data-stu-id="e5f9c-120">Not</span></span>](er-functions-logical-not.md)                       | <span data-ttu-id="e5f9c-121">Cette fonction renvoie la valeur logique inversée de la condition spécifiée en tant que valeur *Booléenne*.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-121">This function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span> |
| [<span data-ttu-id="e5f9c-122">Or</span><span class="sxs-lookup"><span data-stu-id="e5f9c-122">Or</span></span>](er-functions-logical-or.md)                         | <span data-ttu-id="e5f9c-123">Cette fonction renvoie une valeur *Booléenne* de **FALSE** si toutes les conditions spécifiées sont false.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-123">This function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="e5f9c-124">Si toutes les conditions spécifiées sont true, la fonction renvoie une valeur *Booléenne* de **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-124">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span> |
| [<span data-ttu-id="e5f9c-125">ValueIn</span><span class="sxs-lookup"><span data-stu-id="e5f9c-125">ValueIn</span></span>](er-functions-logical-valuein.md)               | <span data-ttu-id="e5f9c-126">Cette fonction détermine si l’entrée spécifiée correspond à une valeur quelconque d’un article donné dans la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-126">This function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="e5f9c-127">Elle renvoie une *Booléenne* de **TRUE** si l’entrée spécifiée correspond au résultat de l’exécution de l’expression spécifiée pour au moins un enregistrement de la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-127">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="e5f9c-128">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-128">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="e5f9c-129">ValueInLarge</span><span class="sxs-lookup"><span data-stu-id="e5f9c-129">ValueInLarge</span></span>](er-functions-logical-valueinlarge.md)     | <span data-ttu-id="e5f9c-130">Cette fonction détermine si l’entrée spécifiée de type *Int64* ou *Entier* correspond à une valeur quelconque d’un article donné dans la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-130">This function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="e5f9c-131">Elle renvoie une *Booléenne* de **TRUE** si l’entrée spécifiée correspond au résultat de l’exécution de l’expression spécifiée pour au moins un enregistrement de la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-131">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="e5f9c-132">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="e5f9c-132">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |


## <a name="additional-resources"></a><span data-ttu-id="e5f9c-133">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e5f9c-133">Additional resources</span></span>

[<span data-ttu-id="e5f9c-134">Vue d’ensemble des États électroniques</span><span class="sxs-lookup"><span data-stu-id="e5f9c-134">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="e5f9c-135">Concepteur de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="e5f9c-135">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="e5f9c-136">Langage de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="e5f9c-136">Electronic reporting formula language</span></span>](er-formula-language.md)
