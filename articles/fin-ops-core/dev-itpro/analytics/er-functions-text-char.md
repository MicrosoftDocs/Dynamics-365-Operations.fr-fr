---
title: Fonction CHAR ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CHAR États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: a9f0f70c250592bf74b1a1df823e66803e853a64
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682989"
---
# <a name="char-er-function"></a><span data-ttu-id="d2eaa-103">Fonction CHAR ER</span><span class="sxs-lookup"><span data-stu-id="d2eaa-103">CHAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d2eaa-104">La fonction `CHAR` renvoie une valeur de *Chaîne* qui présente un seul caractère référencé par le numéro Unicode spécifié.</span><span class="sxs-lookup"><span data-stu-id="d2eaa-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="d2eaa-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d2eaa-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="d2eaa-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="d2eaa-106">Arguments</span></span>

<span data-ttu-id="d2eaa-107">`number` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="d2eaa-107">`number`: *Integer*</span></span>

<span data-ttu-id="d2eaa-108">Nombre qui correspond à un seul caractère attendu.</span><span class="sxs-lookup"><span data-stu-id="d2eaa-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="d2eaa-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="d2eaa-109">Return values</span></span>

<span data-ttu-id="d2eaa-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="d2eaa-110">*String*</span></span>

<span data-ttu-id="d2eaa-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="d2eaa-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d2eaa-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="d2eaa-112">Usage notes</span></span>

<span data-ttu-id="d2eaa-113">La chaîne retournée par cette fonction dépend de l’encodage sélectionné dans l’élément de format **FILE** parent.</span><span class="sxs-lookup"><span data-stu-id="d2eaa-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="d2eaa-114">Pour obtenir une liste des codages pris en charge, consultez [Classe de codage](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="d2eaa-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="d2eaa-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="d2eaa-115">Example</span></span>

<span data-ttu-id="d2eaa-116">`CHAR (255)` renvoie **« ÿ »**.</span><span class="sxs-lookup"><span data-stu-id="d2eaa-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d2eaa-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d2eaa-117">Additional resources</span></span>

[<span data-ttu-id="d2eaa-118">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="d2eaa-118">Text functions</span></span>](er-functions-category-text.md)
