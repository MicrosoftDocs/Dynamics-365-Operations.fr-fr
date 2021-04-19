---
title: Fonction LEFT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction LEFT États électroniques (ER).
author: NickSelin
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
ms.openlocfilehash: 69b1d95ea0e82b1947b665b0724cff6c5b319633
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746337"
---
# <a name="left-er-function"></a><span data-ttu-id="feefe-103">Fonction LEFT ER</span><span class="sxs-lookup"><span data-stu-id="feefe-103">LEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="feefe-104">La fonction `LEFT` renvoie une valeur de *Chaîne* qui présente le nombre de caractères spécifié à partir du début de la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="feefe-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="feefe-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="feefe-105">Syntax</span></span>

```vb
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="feefe-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="feefe-106">Arguments</span></span>

<span data-ttu-id="feefe-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="feefe-107">`text`: *String*</span></span>

<span data-ttu-id="feefe-108">Valeur *Chaîne* qui représente le texte d’origine.</span><span class="sxs-lookup"><span data-stu-id="feefe-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="feefe-109">`number` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="feefe-109">`number`: *Integer*</span></span>

<span data-ttu-id="feefe-110">Nombre de caractères qui doivent être renvoyés à partir du début du texte d’origine.</span><span class="sxs-lookup"><span data-stu-id="feefe-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="feefe-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="feefe-111">Return values</span></span>

<span data-ttu-id="feefe-112">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="feefe-112">*String*</span></span>

<span data-ttu-id="feefe-113">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="feefe-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="feefe-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="feefe-114">Example</span></span>

<span data-ttu-id="feefe-115">`LEFT ("Sample", 3)` renvoie **« Sam »**.</span><span class="sxs-lookup"><span data-stu-id="feefe-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="feefe-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="feefe-116">Additional resources</span></span>

[<span data-ttu-id="feefe-117">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="feefe-117">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]