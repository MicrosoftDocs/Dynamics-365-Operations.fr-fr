---
title: Fonction STRINGJOIN ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction STRINGJOIN États électroniques (ER).
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
ms.openlocfilehash: 10a98e98d913b0b4fe36690f7effd5d8d9a3faf4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041789"
---
# <span data-ttu-id="ee5d9-103"><a name="STRINGJOIN">Fonction STRINGJOIN ER</a></span><span class="sxs-lookup"><span data-stu-id="ee5d9-103"><a name="STRINGJOIN">STRINGJOIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee5d9-104">La fonction `STRINGJOIN` renvoie une valeur de *Chaîne* composée des valeurs concaténées du champ spécifié dans la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ee5d9-104">The `STRINGJOIN` function returns a *String* value that consists of concatenated values of the specified field from the specified list.</span></span> <span data-ttu-id="ee5d9-105">Les valeurs peuvent être séparées par le séparateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="ee5d9-105">The values can be separated by the specified delimiter.</span></span>

## <a name="syntax"></a><span data-ttu-id="ee5d9-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ee5d9-106">Syntax</span></span>

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a><span data-ttu-id="ee5d9-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="ee5d9-107">Arguments</span></span>

<span data-ttu-id="ee5d9-108">`list` : *Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="ee5d9-108">`list`: *Record list*</span></span>

<span data-ttu-id="ee5d9-109">Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="ee5d9-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="ee5d9-110">`field` : *Champ*</span><span class="sxs-lookup"><span data-stu-id="ee5d9-110">`field`: *Field*</span></span>

<span data-ttu-id="ee5d9-111">Chemin d'accès valide d'un champ de type de données *Chaîne* dans la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ee5d9-111">The valid path of a field of the *String* data type in the specified list.</span></span>

<span data-ttu-id="ee5d9-112">`delimiter` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ee5d9-112">`delimiter`: *String*</span></span>

<span data-ttu-id="ee5d9-113">Délimiteur utilisé pour séparer les sous-chaînes.</span><span class="sxs-lookup"><span data-stu-id="ee5d9-113">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="ee5d9-114">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="ee5d9-114">Return values</span></span>

<span data-ttu-id="ee5d9-115">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ee5d9-115">*String*</span></span>

<span data-ttu-id="ee5d9-116">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="ee5d9-116">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="ee5d9-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="ee5d9-117">Example</span></span>

<span data-ttu-id="ee5d9-118">Si vous entrez `SPLIT("abc" , 1)` comme source de données **DS**, l'expression `STRINGJOIN (DS, DS.Value, "-")` renvoie **« abc »**.</span><span class="sxs-lookup"><span data-stu-id="ee5d9-118">If you enter `SPLIT("abc" , 1)` as data source **DS**, the expression `STRINGJOIN (DS, DS.Value, "-")` returns **"a-b-c"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ee5d9-119">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ee5d9-119">Additional resources</span></span>

[<span data-ttu-id="ee5d9-120">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="ee5d9-120">List functions</span></span>](er-functions-category-list.md)
