---
title: Fonction LEFT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction LEFT États électroniques (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8280a05ea180d9de499d87efa53eca8ca912b0e3
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915646"
---
# <span data-ttu-id="71015-103"><a name="LEFT">Fonction LEFT ER</a></span><span class="sxs-lookup"><span data-stu-id="71015-103"><a name="LEFT">LEFT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71015-104">La fonction `LEFT` renvoie une valeur de *Chaîne* qui présente le nombre de caractères spécifié à partir du début de la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="71015-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="71015-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="71015-105">Syntax</span></span>

```
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="71015-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="71015-106">Arguments</span></span>

<span data-ttu-id="71015-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="71015-107">`text`: *String*</span></span>

<span data-ttu-id="71015-108">Valeur *Chaîne* qui représente le texte d'origine.</span><span class="sxs-lookup"><span data-stu-id="71015-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="71015-109">`number` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="71015-109">`number`: *Integer*</span></span>

<span data-ttu-id="71015-110">Nombre de caractères qui doivent être renvoyés à partir du début du texte d'origine.</span><span class="sxs-lookup"><span data-stu-id="71015-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="71015-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="71015-111">Return values</span></span>

<span data-ttu-id="71015-112">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="71015-112">*String*</span></span>

<span data-ttu-id="71015-113">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="71015-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="71015-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="71015-114">Example</span></span>

<span data-ttu-id="71015-115">`LEFT ("Sample", 3)` renvoie **« Sam »**.</span><span class="sxs-lookup"><span data-stu-id="71015-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71015-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="71015-116">Additional resources</span></span>

[<span data-ttu-id="71015-117">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="71015-117">Text functions</span></span>](er-functions-category-text.md)
