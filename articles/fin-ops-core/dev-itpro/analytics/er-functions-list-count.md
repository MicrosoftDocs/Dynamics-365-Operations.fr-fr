---
title: Fonction COUNT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction COUNT États électroniques (ER).
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
ms.openlocfilehash: 72d2ea1b26c295c97575a3c7a479ee4e06762424
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042203"
---
# <span data-ttu-id="478fb-103"><a name="COUNT">Fonction COUNT ER</a></span><span class="sxs-lookup"><span data-stu-id="478fb-103"><a name="COUNT">COUNT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="478fb-104">La fonction `COUNT` renvoie une valeur *Entier* qui représente le nombre d'enregistrements dans la liste spécifiée, si la liste n'est pas vide.</span><span class="sxs-lookup"><span data-stu-id="478fb-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="478fb-105">Si la liste est vide, cette fonction renvoie **0** (zéro).</span><span class="sxs-lookup"><span data-stu-id="478fb-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="478fb-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="478fb-106">Syntax</span></span>

```vb
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="478fb-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="478fb-107">Arguments</span></span>

<span data-ttu-id="478fb-108">`list` : *Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="478fb-108">`list`: *Record list*</span></span>

<span data-ttu-id="478fb-109">Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="478fb-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="478fb-110">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="478fb-110">Return values</span></span>

<span data-ttu-id="478fb-111">*Entier*</span><span class="sxs-lookup"><span data-stu-id="478fb-111">*Integer*</span></span>

<span data-ttu-id="478fb-112">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="478fb-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="478fb-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="478fb-113">Example</span></span>

<span data-ttu-id="478fb-114">`COUNT (SPLIT("abcd" , 3))` renvoie **2**, parce que la fonction `SPLIT` utilisée dans cet exemple crée une liste composée de deux enregistrements.</span><span class="sxs-lookup"><span data-stu-id="478fb-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="478fb-115">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="478fb-115">Additional resources</span></span>

[<span data-ttu-id="478fb-116">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="478fb-116">List functions</span></span>](er-functions-category-list.md)
