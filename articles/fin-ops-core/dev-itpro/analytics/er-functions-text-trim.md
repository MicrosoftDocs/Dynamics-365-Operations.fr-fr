---
title: Fonction TRIM ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction TRIM États électroniques (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 93b08792a7aab7245d0443da05e0330bf8b2d56e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746047"
---
# <a name="trim-er-function"></a><span data-ttu-id="463a0-103">Fonction TRIM ER</span><span class="sxs-lookup"><span data-stu-id="463a0-103">TRIM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="463a0-104">La fonction `TRIM` renvoie la chaîne de texte spécifiée en tant que valeur de *Chaîne* une fois que les espaces de début et de fin ont été tronqués, et une fois que plusieurs espaces entre les mots ont été supprimés.</span><span class="sxs-lookup"><span data-stu-id="463a0-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="463a0-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="463a0-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="463a0-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="463a0-106">Arguments</span></span>

<span data-ttu-id="463a0-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="463a0-107">`text`: *String*</span></span>

<span data-ttu-id="463a0-108">Chemin d’accès valide d’une source de données du type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="463a0-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="463a0-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="463a0-109">Return values</span></span>

<span data-ttu-id="463a0-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="463a0-110">*String*</span></span>

<span data-ttu-id="463a0-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="463a0-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="463a0-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="463a0-112">Example</span></span>

<span data-ttu-id="463a0-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` renvoie **« Exemple de texte »**.</span><span class="sxs-lookup"><span data-stu-id="463a0-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="463a0-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="463a0-114">Additional resources</span></span>

[<span data-ttu-id="463a0-115">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="463a0-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]