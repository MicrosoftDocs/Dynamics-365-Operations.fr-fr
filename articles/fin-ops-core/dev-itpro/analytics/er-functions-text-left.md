---
title: Fonction LEFT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction LEFT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 6f1ec7a21a16c3a34bed9779b05f20f21815ab9d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569990"
---
# <a name="left-er-function"></a><span data-ttu-id="82b60-103">Fonction LEFT ER</span><span class="sxs-lookup"><span data-stu-id="82b60-103">LEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82b60-104">La fonction `LEFT` renvoie une valeur de *Chaîne* qui présente le nombre de caractères spécifié à partir du début de la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="82b60-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="82b60-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="82b60-105">Syntax</span></span>

```vb
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="82b60-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="82b60-106">Arguments</span></span>

<span data-ttu-id="82b60-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="82b60-107">`text`: *String*</span></span>

<span data-ttu-id="82b60-108">Valeur *Chaîne* qui représente le texte d’origine.</span><span class="sxs-lookup"><span data-stu-id="82b60-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="82b60-109">`number` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="82b60-109">`number`: *Integer*</span></span>

<span data-ttu-id="82b60-110">Nombre de caractères qui doivent être renvoyés à partir du début du texte d’origine.</span><span class="sxs-lookup"><span data-stu-id="82b60-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="82b60-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="82b60-111">Return values</span></span>

<span data-ttu-id="82b60-112">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="82b60-112">*String*</span></span>

<span data-ttu-id="82b60-113">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="82b60-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="82b60-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="82b60-114">Example</span></span>

<span data-ttu-id="82b60-115">`LEFT ("Sample", 3)` renvoie **« Sam »**.</span><span class="sxs-lookup"><span data-stu-id="82b60-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="82b60-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="82b60-116">Additional resources</span></span>

[<span data-ttu-id="82b60-117">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="82b60-117">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]