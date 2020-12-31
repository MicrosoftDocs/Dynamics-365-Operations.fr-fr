---
title: Fonction LEFT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction LEFT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 9e9cdff9bb5c22c74803cf17c056c0ff1af5ef43
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685881"
---
# <a name="left-er-function"></a><span data-ttu-id="67377-103">Fonction LEFT ER</span><span class="sxs-lookup"><span data-stu-id="67377-103">LEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="67377-104">La fonction `LEFT` renvoie une valeur de *Chaîne* qui présente le nombre de caractères spécifié à partir du début de la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="67377-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="67377-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="67377-105">Syntax</span></span>

```vb
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="67377-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="67377-106">Arguments</span></span>

<span data-ttu-id="67377-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="67377-107">`text`: *String*</span></span>

<span data-ttu-id="67377-108">Valeur *Chaîne* qui représente le texte d’origine.</span><span class="sxs-lookup"><span data-stu-id="67377-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="67377-109">`number` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="67377-109">`number`: *Integer*</span></span>

<span data-ttu-id="67377-110">Nombre de caractères qui doivent être renvoyés à partir du début du texte d’origine.</span><span class="sxs-lookup"><span data-stu-id="67377-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="67377-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="67377-111">Return values</span></span>

<span data-ttu-id="67377-112">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="67377-112">*String*</span></span>

<span data-ttu-id="67377-113">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="67377-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="67377-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="67377-114">Example</span></span>

<span data-ttu-id="67377-115">`LEFT ("Sample", 3)` renvoie **« Sam »**.</span><span class="sxs-lookup"><span data-stu-id="67377-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="67377-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="67377-116">Additional resources</span></span>

[<span data-ttu-id="67377-117">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="67377-117">Text functions</span></span>](er-functions-category-text.md)
