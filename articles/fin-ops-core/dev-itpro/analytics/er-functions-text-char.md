---
title: Fonction CHAR ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CHAR États électroniques (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: b008cf6ddf51d816a17e0fae1fa0db464adeabde
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563196"
---
# <a name="char-er-function"></a><span data-ttu-id="d1aba-103">Fonction CHAR ER</span><span class="sxs-lookup"><span data-stu-id="d1aba-103">CHAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d1aba-104">La fonction `CHAR` renvoie une valeur de *Chaîne* qui présente un seul caractère référencé par le numéro Unicode spécifié.</span><span class="sxs-lookup"><span data-stu-id="d1aba-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="d1aba-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d1aba-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="d1aba-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="d1aba-106">Arguments</span></span>

<span data-ttu-id="d1aba-107">`number` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="d1aba-107">`number`: *Integer*</span></span>

<span data-ttu-id="d1aba-108">Nombre qui correspond à un seul caractère attendu.</span><span class="sxs-lookup"><span data-stu-id="d1aba-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="d1aba-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="d1aba-109">Return values</span></span>

<span data-ttu-id="d1aba-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="d1aba-110">*String*</span></span>

<span data-ttu-id="d1aba-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="d1aba-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d1aba-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="d1aba-112">Usage notes</span></span>

<span data-ttu-id="d1aba-113">La chaîne retournée par cette fonction dépend de l’encodage sélectionné dans l’élément de format **FILE** parent.</span><span class="sxs-lookup"><span data-stu-id="d1aba-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="d1aba-114">Pour obtenir une liste des codages pris en charge, consultez [Classe de codage](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="d1aba-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="d1aba-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="d1aba-115">Example</span></span>

<span data-ttu-id="d1aba-116">`CHAR (255)` renvoie **« ÿ »**.</span><span class="sxs-lookup"><span data-stu-id="d1aba-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d1aba-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d1aba-117">Additional resources</span></span>

[<span data-ttu-id="d1aba-118">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="d1aba-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]