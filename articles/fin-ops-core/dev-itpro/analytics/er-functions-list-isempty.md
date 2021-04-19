---
title: Fonction ISEMPTY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ISEMPTY États électroniques (ER).
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
ms.openlocfilehash: 9c33e8b613bf5bf5bc17a42a7668d4cc4ee58e53
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750434"
---
# <a name="isempty-er-function"></a><span data-ttu-id="58a05-103">Fonction ISEMPTY ER</span><span class="sxs-lookup"><span data-stu-id="58a05-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58a05-104">La fonction `ISEMPTY` renvoie une valeur *Booléenne* de **TRUE** si la liste spécifiée ne contient aucun enregistrement.</span><span class="sxs-lookup"><span data-stu-id="58a05-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="58a05-105">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="58a05-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="58a05-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="58a05-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="58a05-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="58a05-107">Arguments</span></span>

<span data-ttu-id="58a05-108">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="58a05-108">`list`: *Record list*</span></span>

<span data-ttu-id="58a05-109">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="58a05-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="58a05-110">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="58a05-110">Return values</span></span>

<span data-ttu-id="58a05-111">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="58a05-111">*Boolean*</span></span>

<span data-ttu-id="58a05-112">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="58a05-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="58a05-113">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="58a05-113">Example 1</span></span>

<span data-ttu-id="58a05-114">Si vous entrez une source de données **DS** de type *Champ calculé*, et qu’elle contient l’expression `SPLIT ("A|B|C", "|")`, l’expression `ISEMPTY(DS)` renvoie **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="58a05-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="58a05-115">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="58a05-115">Example 2</span></span>

<span data-ttu-id="58a05-116">L’expression `ISEMPTY (SPLIT ("",1))` renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="58a05-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="58a05-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="58a05-117">Additional resources</span></span>

[<span data-ttu-id="58a05-118">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="58a05-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]