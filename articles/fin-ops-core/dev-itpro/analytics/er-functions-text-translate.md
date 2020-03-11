---
title: Fonction TRANSLATE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction TRANSLATE États électroniques (ER).
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
ms.openlocfilehash: 07fe19c5f66c33e336f76f3a72d3bbda0c7e8d86
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040915"
---
# <span data-ttu-id="cff5d-103"><a name="TRANSLATE">Fonction TRANSLATE ER</a></span><span class="sxs-lookup"><span data-stu-id="cff5d-103"><a name="TRANSLATE">TRANSLATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cff5d-104">La fonction `TRANSLATE` renvoie la chaîne de texte spécifiée sous la forme d'une valeur de *Chaîne* après que tout ou partie de celui-ci a été remplacé par une autre chaîne.</span><span class="sxs-lookup"><span data-stu-id="cff5d-104">The `TRANSLATE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="cff5d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cff5d-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="cff5d-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="cff5d-106">Arguments</span></span>

<span data-ttu-id="cff5d-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="cff5d-107">`text`: *String*</span></span>

<span data-ttu-id="cff5d-108">Chemin d'accès valide d'une source de données du type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="cff5d-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="cff5d-109">`pattern` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="cff5d-109">`pattern`: *String*</span></span>

<span data-ttu-id="cff5d-110">Texte qui doit être remplacé.</span><span class="sxs-lookup"><span data-stu-id="cff5d-110">The text that must be replaced.</span></span>

<span data-ttu-id="cff5d-111">`replacement` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="cff5d-111">`replacement`: *String*</span></span>

<span data-ttu-id="cff5d-112">Texte à utiliser en remplacement.</span><span class="sxs-lookup"><span data-stu-id="cff5d-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="cff5d-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="cff5d-113">Return values</span></span>

<span data-ttu-id="cff5d-114">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="cff5d-114">*String*</span></span>

<span data-ttu-id="cff5d-115">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="cff5d-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="cff5d-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="cff5d-116">Example</span></span>

<span data-ttu-id="cff5d-117">`TRANSLATE ("abcdef", "cd", "GH")` remplace le modèle **cd** par la chaîne **« GH »** et renvoie **abGHef**.</span><span class="sxs-lookup"><span data-stu-id="cff5d-117">`TRANSLATE ("abcdef", "cd", "GH")` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cff5d-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="cff5d-118">Additional resources</span></span>

[<span data-ttu-id="cff5d-119">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="cff5d-119">Text functions</span></span>](er-functions-category-text.md)
