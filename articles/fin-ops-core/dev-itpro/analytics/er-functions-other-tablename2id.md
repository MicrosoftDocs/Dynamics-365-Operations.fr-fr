---
title: Fonction TABLENAME2ID ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction TABLENAME2ID États électroniques (ER).
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
ms.openlocfilehash: a68a8e1f4afa378ab446eae12bc90cdb3aba8b19
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681156"
---
# <a name="tablename2id-er-function"></a><span data-ttu-id="5e082-103">Fonction TABLENAME2ID ER</span><span class="sxs-lookup"><span data-stu-id="5e082-103">TABLENAME2ID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e082-104">La fonction `TABLENAME2ID` renvoie une représentation numérique de l’ID de table pour le nom de table spécifié en tant que valeur *Entier*.</span><span class="sxs-lookup"><span data-stu-id="5e082-104">The `TABLENAME2ID` function returns a numeric representation of the table ID for the specified table name as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e082-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5e082-105">Syntax</span></span>

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a><span data-ttu-id="5e082-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="5e082-106">Arguments</span></span>

<span data-ttu-id="5e082-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="5e082-107">`text`: *String*</span></span>

<span data-ttu-id="5e082-108">Valeur de texte qui représente un nom de table valide.</span><span class="sxs-lookup"><span data-stu-id="5e082-108">A text value that represents a valid table name.</span></span>

## <a name="return-values"></a><span data-ttu-id="5e082-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="5e082-109">Return values</span></span>

<span data-ttu-id="5e082-110">*Entier*</span><span class="sxs-lookup"><span data-stu-id="5e082-110">*Integer*</span></span>

<span data-ttu-id="5e082-111">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="5e082-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5e082-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="5e082-112">Usage notes</span></span>

<span data-ttu-id="5e082-113">L’exécution de cette fonction peut avoir des résultats différents dans différentes instances de Microsoft Dynamics 365 Finance, même si le même nom de société est utilisé.</span><span class="sxs-lookup"><span data-stu-id="5e082-113">Execution of this function can have different results in different instances of Microsoft Dynamics 365 Finance, even if the same company name is used.</span></span>

## <a name="example"></a><span data-ttu-id="5e082-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="5e082-114">Example</span></span>

<span data-ttu-id="5e082-115">`TABLENAME2ID ("Intrastat")` renvoie **1510**.</span><span class="sxs-lookup"><span data-stu-id="5e082-115">`TABLENAME2ID ("Intrastat")` returns **1510**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5e082-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5e082-116">Additional resources</span></span>

[<span data-ttu-id="5e082-117">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="5e082-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
