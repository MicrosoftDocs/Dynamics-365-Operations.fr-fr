---
title: Fonction CHAR ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction CHAR États électroniques (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7813b0c6002e47aef6a8c119c72728a49584401b
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041226"
---
# <span data-ttu-id="bbb49-103"><a name="CHAR">Fonction CHAR ER</a></span><span class="sxs-lookup"><span data-stu-id="bbb49-103"><a name="CHAR">CHAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bbb49-104">La fonction `CHAR` renvoie une valeur de *Chaîne* qui présente un seul caractère référencé par le numéro Unicode spécifié.</span><span class="sxs-lookup"><span data-stu-id="bbb49-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="bbb49-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="bbb49-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="bbb49-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="bbb49-106">Arguments</span></span>

<span data-ttu-id="bbb49-107">`number` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="bbb49-107">`number`: *Integer*</span></span>

<span data-ttu-id="bbb49-108">Nombre qui correspond à un seul caractère attendu.</span><span class="sxs-lookup"><span data-stu-id="bbb49-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="bbb49-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="bbb49-109">Return values</span></span>

<span data-ttu-id="bbb49-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="bbb49-110">*String*</span></span>

<span data-ttu-id="bbb49-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="bbb49-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bbb49-112">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="bbb49-112">Usage notes</span></span>

<span data-ttu-id="bbb49-113">La chaîne retournée par cette fonction dépend de l'encodage sélectionné dans l'élément de format **FILE** parent.</span><span class="sxs-lookup"><span data-stu-id="bbb49-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="bbb49-114">Pour obtenir une liste des codages pris en charge, consultez [Classe de codage](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="bbb49-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="bbb49-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="bbb49-115">Example</span></span>

<span data-ttu-id="bbb49-116">`CHAR (255)` renvoie **« ÿ »**.</span><span class="sxs-lookup"><span data-stu-id="bbb49-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bbb49-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="bbb49-117">Additional resources</span></span>

[<span data-ttu-id="bbb49-118">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="bbb49-118">Text functions</span></span>](er-functions-category-text.md)
