---
title: Fonction TABLENAME2ID ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction TABLENAME2ID États électroniques (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 49370af4ebb7552dd3aff4512890fd93fa67c72d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563268"
---
# <a name="tablename2id-er-function"></a><span data-ttu-id="e06dc-103">Fonction TABLENAME2ID ER</span><span class="sxs-lookup"><span data-stu-id="e06dc-103">TABLENAME2ID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e06dc-104">La fonction `TABLENAME2ID` renvoie une représentation numérique de l’ID de table pour le nom de table spécifié en tant que valeur *Entier*.</span><span class="sxs-lookup"><span data-stu-id="e06dc-104">The `TABLENAME2ID` function returns a numeric representation of the table ID for the specified table name as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="e06dc-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e06dc-105">Syntax</span></span>

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a><span data-ttu-id="e06dc-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="e06dc-106">Arguments</span></span>

<span data-ttu-id="e06dc-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="e06dc-107">`text`: *String*</span></span>

<span data-ttu-id="e06dc-108">Valeur de texte qui représente un nom de table valide.</span><span class="sxs-lookup"><span data-stu-id="e06dc-108">A text value that represents a valid table name.</span></span>

## <a name="return-values"></a><span data-ttu-id="e06dc-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="e06dc-109">Return values</span></span>

<span data-ttu-id="e06dc-110">*Entier*</span><span class="sxs-lookup"><span data-stu-id="e06dc-110">*Integer*</span></span>

<span data-ttu-id="e06dc-111">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="e06dc-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e06dc-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="e06dc-112">Usage notes</span></span>

<span data-ttu-id="e06dc-113">L’exécution de cette fonction peut avoir des résultats différents dans différentes instances de Microsoft Dynamics 365 Finance, même si le même nom de société est utilisé.</span><span class="sxs-lookup"><span data-stu-id="e06dc-113">Execution of this function can have different results in different instances of Microsoft Dynamics 365 Finance, even if the same company name is used.</span></span>

## <a name="example"></a><span data-ttu-id="e06dc-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="e06dc-114">Example</span></span>

<span data-ttu-id="e06dc-115">`TABLENAME2ID ("Intrastat")` renvoie **1510**.</span><span class="sxs-lookup"><span data-stu-id="e06dc-115">`TABLENAME2ID ("Intrastat")` returns **1510**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e06dc-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e06dc-116">Additional resources</span></span>

[<span data-ttu-id="e06dc-117">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="e06dc-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]