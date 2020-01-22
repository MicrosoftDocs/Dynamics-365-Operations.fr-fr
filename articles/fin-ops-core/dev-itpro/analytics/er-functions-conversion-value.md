---
title: Fonction VALUE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction VALUE États électroniques (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 160dd81baa43702b2deea1e3eea20080fca122ca
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917624"
---
# <span data-ttu-id="0dcc8-103"><a name="VALUE">Fonction VALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="0dcc8-103"><a name="VALUE">VALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0dcc8-104">La fonction `VALUE` renvoie une valeur de *Réel* convertie à partir de la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="0dcc8-104">The `VALUE` function returns a *Real* value that is converted from the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="0dcc8-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0dcc8-105">Syntax</span></span>

```
VALUE (text)
```

## <a name="arguments"></a><span data-ttu-id="0dcc8-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="0dcc8-106">Arguments</span></span>

<span data-ttu-id="0dcc8-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="0dcc8-107">`text`: *String*</span></span>

<span data-ttu-id="0dcc8-108">Valeur de chaîne à convertir en valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="0dcc8-108">A string value that must be converted to a numeric value.</span></span>

## <a name="return-values"></a><span data-ttu-id="0dcc8-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="0dcc8-109">Return values</span></span>

<span data-ttu-id="0dcc8-110">*Réel*</span><span class="sxs-lookup"><span data-stu-id="0dcc8-110">*Real*</span></span>

<span data-ttu-id="0dcc8-111">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="0dcc8-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0dcc8-112">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="0dcc8-112">Usage notes</span></span>

<span data-ttu-id="0dcc8-113">Les virgules et les points (.) sont considérés comme des séparateurs de nombres décimaux, et un trait d'union (-) est utilisé comme signe moins.</span><span class="sxs-lookup"><span data-stu-id="0dcc8-113">Commas and dot characters (.) are considered decimal separators, and a leading hyphen (-) is used as a negative sign.</span></span> <span data-ttu-id="0dcc8-114">Une exception est levée à l'exécution si la chaîne spécifiée contient d'autres caractères non numériques.</span><span class="sxs-lookup"><span data-stu-id="0dcc8-114">An exception is thrown at runtime if the specified string contains other non-numeric characters.</span></span>

## <a name="example-1"></a><span data-ttu-id="0dcc8-115">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="0dcc8-115">Example 1</span></span>

<span data-ttu-id="0dcc8-116">`VALUE ("1 234,56")` lève une exception.</span><span class="sxs-lookup"><span data-stu-id="0dcc8-116">`VALUE ("1 234,56")` throws an exception.</span></span>

## <a name="example-2"></a><span data-ttu-id="0dcc8-117">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="0dcc8-117">Example 2</span></span>

<span data-ttu-id="0dcc8-118">`VALUE ("1234,56")` renvoie **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="0dcc8-118">`VALUE ("1234,56")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0dcc8-119">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0dcc8-119">Additional resources</span></span>

[<span data-ttu-id="0dcc8-120">Fonctions de conversion des types</span><span class="sxs-lookup"><span data-stu-id="0dcc8-120">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
