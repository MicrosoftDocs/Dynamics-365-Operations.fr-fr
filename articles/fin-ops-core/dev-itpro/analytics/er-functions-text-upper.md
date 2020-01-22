---
title: Fonction UPPER ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction UPPER États électroniques (ER).
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
ms.openlocfilehash: ed862ab823cfc3539c420d3066c9397e1e6d870e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916681"
---
# <span data-ttu-id="f26fd-103"><a name="UPPER">Fonction UPPER ER</a></span><span class="sxs-lookup"><span data-stu-id="f26fd-103"><a name="UPPER">UPPER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f26fd-104">La fonction `UPPER` renvoie la chaîne de texte spécifiée sous la forme *Chaîne* après avoir été convertie en lettres majuscules.</span><span class="sxs-lookup"><span data-stu-id="f26fd-104">The `UPPER` function returns the specified text string as a *String* value after it has been converted to uppercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="f26fd-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f26fd-105">Syntax</span></span>

```
UPPER (text )
```

## <a name="arguments"></a><span data-ttu-id="f26fd-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="f26fd-106">Arguments</span></span>

<span data-ttu-id="f26fd-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="f26fd-107">`text`: *String*</span></span>

<span data-ttu-id="f26fd-108">Chemin d'accès valide d'une source de données du type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="f26fd-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="f26fd-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="f26fd-109">Return values</span></span>

<span data-ttu-id="f26fd-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="f26fd-110">*String*</span></span>

<span data-ttu-id="f26fd-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="f26fd-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="f26fd-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="f26fd-112">Example</span></span>

<span data-ttu-id="f26fd-113">`UPPER ("Sample")` renvoie **« EXEMPLE »**.</span><span class="sxs-lookup"><span data-stu-id="f26fd-113">`UPPER ("Sample")` returns **"SAMPLE"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f26fd-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f26fd-114">Additional resources</span></span>

[<span data-ttu-id="f26fd-115">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="f26fd-115">Text functions</span></span>](er-functions-category-text.md)