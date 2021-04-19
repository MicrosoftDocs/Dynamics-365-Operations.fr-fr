---
title: Fonction COUNT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction COUNT États électroniques (ER).
author: NickSelin
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
ms.openlocfilehash: a0b780051684ef52d06a9baf78d9b513d9ac1f0e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746625"
---
# <a name="count-er-function"></a><span data-ttu-id="5e719-103">Fonction COUNT ER</span><span class="sxs-lookup"><span data-stu-id="5e719-103">COUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e719-104">La fonction `COUNT` renvoie une valeur *Entier* qui représente le nombre d’enregistrements dans la liste spécifiée, si la liste n’est pas vide.</span><span class="sxs-lookup"><span data-stu-id="5e719-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="5e719-105">Si la liste est vide, cette fonction renvoie **0** (zéro).</span><span class="sxs-lookup"><span data-stu-id="5e719-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="5e719-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5e719-106">Syntax</span></span>

```vb
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="5e719-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="5e719-107">Arguments</span></span>

<span data-ttu-id="5e719-108">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="5e719-108">`list`: *Record list*</span></span>

<span data-ttu-id="5e719-109">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="5e719-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="5e719-110">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="5e719-110">Return values</span></span>

<span data-ttu-id="5e719-111">*Entier*</span><span class="sxs-lookup"><span data-stu-id="5e719-111">*Integer*</span></span>

<span data-ttu-id="5e719-112">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="5e719-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="5e719-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="5e719-113">Example</span></span>

<span data-ttu-id="5e719-114">`COUNT (SPLIT("abcd" , 3))` renvoie **2**, parce que la fonction `SPLIT` utilisée dans cet exemple crée une liste composée de deux enregistrements.</span><span class="sxs-lookup"><span data-stu-id="5e719-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5e719-115">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5e719-115">Additional resources</span></span>

[<span data-ttu-id="5e719-116">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="5e719-116">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]