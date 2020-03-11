---
title: Fonction ER RIGHT
description: Cette rubrique fournit des informations sur l'utilisation de la fonction RIGHT États électroniques (ER).
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
ms.openlocfilehash: 7169d9d3d2cdfb9f36bb77c1688922549e79ff32
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040869"
---
# <span data-ttu-id="593dd-103"><a name="RIGHT">Fonction ER RIGHT</a></span><span class="sxs-lookup"><span data-stu-id="593dd-103"><a name="RIGHT">RIGHT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="593dd-104">La fonction `RIGHT` renvoie une valeur de *Chaîne* qui présente le nombre de caractères spécifié à partir de la fin de la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="593dd-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="593dd-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="593dd-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="593dd-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="593dd-106">Arguments</span></span>

<span data-ttu-id="593dd-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="593dd-107">`text`: *String*</span></span>

<span data-ttu-id="593dd-108">Valeur *Chaîne* qui représente le texte d'origine.</span><span class="sxs-lookup"><span data-stu-id="593dd-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="593dd-109">`number` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="593dd-109">`number`: *Integer*</span></span>

<span data-ttu-id="593dd-110">Nombre de caractères qui doivent être renvoyés à partir de la fin du texte d'origine.</span><span class="sxs-lookup"><span data-stu-id="593dd-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="593dd-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="593dd-111">Return values</span></span>

<span data-ttu-id="593dd-112">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="593dd-112">*String*</span></span>

<span data-ttu-id="593dd-113">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="593dd-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="593dd-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="593dd-114">Example</span></span>

<span data-ttu-id="593dd-115">`RIGHT ("Sample", 3)` renvoie **« ple »**.</span><span class="sxs-lookup"><span data-stu-id="593dd-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="593dd-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="593dd-116">Additional resources</span></span>

[<span data-ttu-id="593dd-117">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="593dd-117">Text functions</span></span>](er-functions-category-text.md)
