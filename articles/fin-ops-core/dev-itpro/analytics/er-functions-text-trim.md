---
title: Fonction TRIM ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction TRIM États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 908da840ffcb94f4a60bb41ce041f5f263c921eb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688364"
---
# <a name="trim-er-function"></a><span data-ttu-id="b4d6d-103">Fonction TRIM ER</span><span class="sxs-lookup"><span data-stu-id="b4d6d-103">TRIM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b4d6d-104">La fonction `TRIM` renvoie la chaîne de texte spécifiée en tant que valeur de *Chaîne* une fois que les espaces de début et de fin ont été tronqués, et une fois que plusieurs espaces entre les mots ont été supprimés.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4d6d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b4d6d-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="b4d6d-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="b4d6d-106">Arguments</span></span>

<span data-ttu-id="b4d6d-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b4d6d-107">`text`: *String*</span></span>

<span data-ttu-id="b4d6d-108">Chemin d’accès valide d’une source de données du type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="b4d6d-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="b4d6d-109">Return values</span></span>

<span data-ttu-id="b4d6d-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b4d6d-110">*String*</span></span>

<span data-ttu-id="b4d6d-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="b4d6d-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="b4d6d-112">Example</span></span>

<span data-ttu-id="b4d6d-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` renvoie **« Exemple de texte »**.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b4d6d-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b4d6d-114">Additional resources</span></span>

[<span data-ttu-id="b4d6d-115">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="b4d6d-115">Text functions</span></span>](er-functions-category-text.md)
