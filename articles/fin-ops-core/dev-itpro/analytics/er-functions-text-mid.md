---
title: Fonction MID ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction MID États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: e178b01740954b46e2afbd2a2be6200a652a18c0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915600"
---
# <span data-ttu-id="9484d-103"><a name="MID">Fonction MID ER</a></span><span class="sxs-lookup"><span data-stu-id="9484d-103"><a name="MID">MID ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9484d-104">La fonction `MID` renvoie une valeur de *Chaîne* qui présente le nombre de caractères spécifié à partir de la chaîne spécifiée, à partir de la position donnée.</span><span class="sxs-lookup"><span data-stu-id="9484d-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="9484d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9484d-105">Syntax</span></span>

```
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="9484d-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="9484d-106">Arguments</span></span>

<span data-ttu-id="9484d-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="9484d-107">`text`: *String*</span></span>

<span data-ttu-id="9484d-108">Valeur de *Chaîne* qui spécifie le texte à partir duquel retourner les caractères.</span><span class="sxs-lookup"><span data-stu-id="9484d-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="9484d-109">`starting position` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="9484d-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="9484d-110">Valeur *Entier* qui spécifie la position du premier caractère qui doit être renvoyé à partir du texte spécifié.</span><span class="sxs-lookup"><span data-stu-id="9484d-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="9484d-111">`number of characters` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="9484d-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="9484d-112">Valeur *Entier* qui spécifie le nombre de caractères qui doit être renvoyé, à partir de la position de début spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9484d-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="9484d-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="9484d-113">Return values</span></span>

<span data-ttu-id="9484d-114">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="9484d-114">*String*</span></span>

<span data-ttu-id="9484d-115">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="9484d-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9484d-116">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="9484d-116">Usage notes</span></span>

<span data-ttu-id="9484d-117">Si la valeur de l'argument `starting position` est inférieure à 0 (zéro), les caractères renvoyés sont comptés à partir de la première position de la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9484d-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="9484d-118">Si la valeur de l'argument `starting position` dépasse la longueur de la chaîne spécifiée, une chaîne vide est renvoyée.</span><span class="sxs-lookup"><span data-stu-id="9484d-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="9484d-119">Exemple</span><span class="sxs-lookup"><span data-stu-id="9484d-119">Example</span></span>

<span data-ttu-id="9484d-120">`MID ("Sample", 2, 3)` renvoie **"amp"**.</span><span class="sxs-lookup"><span data-stu-id="9484d-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9484d-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9484d-121">Additional resources</span></span>

[<span data-ttu-id="9484d-122">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="9484d-122">Text functions</span></span>](er-functions-category-text.md)