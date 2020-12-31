---
title: Fonction INDEX ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction INDEX États électroniques (ER).
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
ms.openlocfilehash: a49def8aaa5398fbc7e0f06cc26df8a745207c93
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687989"
---
# <a name="index-er-function"></a><span data-ttu-id="3d7bf-103">Fonction INDEX ER</span><span class="sxs-lookup"><span data-stu-id="3d7bf-103">INDEX ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d7bf-104">La fonction `INDEX` renvoie une valeur de *Conteneur (enregistrement)* sélectionnée à l’aide de l’index numérique spécifié dans la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="3d7bf-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="3d7bf-105">Si l’index est hors des limites pour les enregistrements dans la liste spécifiée, une exception est levée.</span><span class="sxs-lookup"><span data-stu-id="3d7bf-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="3d7bf-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3d7bf-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="3d7bf-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="3d7bf-107">Arguments</span></span>

<span data-ttu-id="3d7bf-108">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="3d7bf-108">`list`: *Record list*</span></span>

<span data-ttu-id="3d7bf-109">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="3d7bf-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="3d7bf-110">`index` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="3d7bf-110">`index`: *Integer*</span></span>

<span data-ttu-id="3d7bf-111">Index numérique qui indique la position de l’enregistrement souhaité dans la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="3d7bf-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="3d7bf-112">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="3d7bf-112">Return values</span></span>

<span data-ttu-id="3d7bf-113">*Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="3d7bf-113">*Container (record)*</span></span>

<span data-ttu-id="3d7bf-114">Valeur de l’enregistrement résultante.</span><span class="sxs-lookup"><span data-stu-id="3d7bf-114">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="3d7bf-115">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="3d7bf-115">Example 1</span></span>

<span data-ttu-id="3d7bf-116">Si vous entrez la source de données **DS** de type *Champ calculé*, et qu’elle contient l’expression `SPLIT ("A|B|C", "|")`, l’expression `DS.Value` retourne la valeur de texte **« B »** pour le second enregistrement de cette liste d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="3d7bf-116">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="3d7bf-117">L’expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` renvoie aussi la valeur texte **« B »**.</span><span class="sxs-lookup"><span data-stu-id="3d7bf-117">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="3d7bf-118">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="3d7bf-118">Example 2</span></span>

<span data-ttu-id="3d7bf-119">Si vous entrez une source de données **DS** de type *Champ calculé*, et qu’elle contient l’expression `SPLIT ("A|B|C", "|")`, l’expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` lève une exception à l’exécution.</span><span class="sxs-lookup"><span data-stu-id="3d7bf-119">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3d7bf-120">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3d7bf-120">Additional resources</span></span>

[<span data-ttu-id="3d7bf-121">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="3d7bf-121">List functions</span></span>](er-functions-category-list.md)
