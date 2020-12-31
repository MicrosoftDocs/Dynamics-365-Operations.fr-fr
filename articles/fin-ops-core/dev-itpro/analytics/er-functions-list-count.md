---
title: Fonction COUNT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction COUNT États électroniques (ER).
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
ms.openlocfilehash: b3a5bb33964c70c85c7d8571057060c1c2b9d433
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687718"
---
# <a name="count-er-function"></a><span data-ttu-id="359da-103">Fonction COUNT ER</span><span class="sxs-lookup"><span data-stu-id="359da-103">COUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="359da-104">La fonction `COUNT` renvoie une valeur *Entier* qui représente le nombre d’enregistrements dans la liste spécifiée, si la liste n’est pas vide.</span><span class="sxs-lookup"><span data-stu-id="359da-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="359da-105">Si la liste est vide, cette fonction renvoie **0** (zéro).</span><span class="sxs-lookup"><span data-stu-id="359da-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="359da-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="359da-106">Syntax</span></span>

```vb
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="359da-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="359da-107">Arguments</span></span>

<span data-ttu-id="359da-108">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="359da-108">`list`: *Record list*</span></span>

<span data-ttu-id="359da-109">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="359da-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="359da-110">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="359da-110">Return values</span></span>

<span data-ttu-id="359da-111">*Entier*</span><span class="sxs-lookup"><span data-stu-id="359da-111">*Integer*</span></span>

<span data-ttu-id="359da-112">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="359da-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="359da-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="359da-113">Example</span></span>

<span data-ttu-id="359da-114">`COUNT (SPLIT("abcd" , 3))` renvoie **2**, parce que la fonction `SPLIT` utilisée dans cet exemple crée une liste composée de deux enregistrements.</span><span class="sxs-lookup"><span data-stu-id="359da-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="359da-115">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="359da-115">Additional resources</span></span>

[<span data-ttu-id="359da-116">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="359da-116">List functions</span></span>](er-functions-category-list.md)
