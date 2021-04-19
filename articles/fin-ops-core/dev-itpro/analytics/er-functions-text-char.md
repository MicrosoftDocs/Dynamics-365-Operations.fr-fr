---
title: Fonction CHAR ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CHAR États électroniques (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: a621328817171be7df0622507c84f5c6f6fe90a1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746433"
---
# <a name="char-er-function"></a><span data-ttu-id="4e410-103">Fonction CHAR ER</span><span class="sxs-lookup"><span data-stu-id="4e410-103">CHAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4e410-104">La fonction `CHAR` renvoie une valeur de *Chaîne* qui présente un seul caractère référencé par le numéro Unicode spécifié.</span><span class="sxs-lookup"><span data-stu-id="4e410-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e410-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4e410-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="4e410-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="4e410-106">Arguments</span></span>

<span data-ttu-id="4e410-107">`number` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="4e410-107">`number`: *Integer*</span></span>

<span data-ttu-id="4e410-108">Nombre qui correspond à un seul caractère attendu.</span><span class="sxs-lookup"><span data-stu-id="4e410-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="4e410-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="4e410-109">Return values</span></span>

<span data-ttu-id="4e410-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="4e410-110">*String*</span></span>

<span data-ttu-id="4e410-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="4e410-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="4e410-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="4e410-112">Usage notes</span></span>

<span data-ttu-id="4e410-113">La chaîne retournée par cette fonction dépend de l’encodage sélectionné dans l’élément de format **FILE** parent.</span><span class="sxs-lookup"><span data-stu-id="4e410-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="4e410-114">Pour obtenir une liste des codages pris en charge, consultez [Classe de codage](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="4e410-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="4e410-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="4e410-115">Example</span></span>

<span data-ttu-id="4e410-116">`CHAR (255)` renvoie **« ÿ »**.</span><span class="sxs-lookup"><span data-stu-id="4e410-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4e410-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4e410-117">Additional resources</span></span>

[<span data-ttu-id="4e410-118">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="4e410-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]