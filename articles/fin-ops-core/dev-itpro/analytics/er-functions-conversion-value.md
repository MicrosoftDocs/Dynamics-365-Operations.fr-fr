---
title: Fonction VALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction VALUE États électroniques (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 2252823d98b63d36d9bb195696abef34ac9c98b6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752578"
---
# <a name="value-er-function"></a><span data-ttu-id="8c0b2-103">Fonction VALUE ER</span><span class="sxs-lookup"><span data-stu-id="8c0b2-103">VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8c0b2-104">La fonction `VALUE` renvoie une valeur de *Réel* convertie à partir de la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-104">The `VALUE` function returns a *Real* value that is converted from the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="8c0b2-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8c0b2-105">Syntax</span></span>

```vb
VALUE (text)
```

## <a name="arguments"></a><span data-ttu-id="8c0b2-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="8c0b2-106">Arguments</span></span>

<span data-ttu-id="8c0b2-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="8c0b2-107">`text`: *String*</span></span>

<span data-ttu-id="8c0b2-108">Valeur de chaîne à convertir en valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-108">A string value that must be converted to a numeric value.</span></span>

## <a name="return-values"></a><span data-ttu-id="8c0b2-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="8c0b2-109">Return values</span></span>

<span data-ttu-id="8c0b2-110">*Réel*</span><span class="sxs-lookup"><span data-stu-id="8c0b2-110">*Real*</span></span>

<span data-ttu-id="8c0b2-111">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8c0b2-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="8c0b2-112">Usage notes</span></span>

<span data-ttu-id="8c0b2-113">Les virgules et les points (.) sont considérés comme des séparateurs de nombres décimaux, et un trait d’union (-) est utilisé comme signe moins.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-113">Commas and dot characters (.) are considered decimal separators, and a leading hyphen (-) is used as a negative sign.</span></span> <span data-ttu-id="8c0b2-114">Une exception est levée à l’exécution si la chaîne spécifiée contient d’autres caractères non numériques.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-114">An exception is thrown at runtime if the specified string contains other non-numeric characters.</span></span>

## <a name="example-1"></a><span data-ttu-id="8c0b2-115">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="8c0b2-115">Example 1</span></span>

<span data-ttu-id="8c0b2-116">`VALUE ("1 234,56")` lève une exception.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-116">`VALUE ("1 234,56")` throws an exception.</span></span>

## <a name="example-2"></a><span data-ttu-id="8c0b2-117">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="8c0b2-117">Example 2</span></span>

<span data-ttu-id="8c0b2-118">`VALUE ("1234,56")` renvoie **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="8c0b2-118">`VALUE ("1234,56")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8c0b2-119">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8c0b2-119">Additional resources</span></span>

[<span data-ttu-id="8c0b2-120">Fonctions de conversion des types</span><span class="sxs-lookup"><span data-stu-id="8c0b2-120">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]