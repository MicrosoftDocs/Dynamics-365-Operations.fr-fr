---
title: Fonction CONCATENATE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction CONCATENATE États électroniques (ER)
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
ms.openlocfilehash: e3d3ff87a59632d58a7c34ef96f856b38f005651
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915761"
---
# <span data-ttu-id="8edbc-103"><a name="CONCATENATE">Fonction CONCATENATE ER</a></span><span class="sxs-lookup"><span data-stu-id="8edbc-103"><a name="CONCATENATE">CONCATENATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8edbc-104">La fonction `CONCATENATE` renvoie toutes les chaînes de texte spécifiées en tant que valeur de *Chaîne* après avoir été jointes en une seule chaîne.</span><span class="sxs-lookup"><span data-stu-id="8edbc-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="8edbc-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8edbc-105">Syntax</span></span>

```
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="8edbc-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="8edbc-106">Arguments</span></span>

<span data-ttu-id="8edbc-107">`text 1` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="8edbc-107">`text 1`: *String*</span></span>

<span data-ttu-id="8edbc-108">Référence à une source de données du type de données *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="8edbc-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="8edbc-109">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="8edbc-109">This argument is required.</span></span>

<span data-ttu-id="8edbc-110">`text N` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="8edbc-110">`text N`: *String*</span></span>

<span data-ttu-id="8edbc-111">Référence à une source de données du type de données *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="8edbc-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="8edbc-112">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="8edbc-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="8edbc-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="8edbc-113">Return values</span></span>

<span data-ttu-id="8edbc-114">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="8edbc-114">*String*</span></span>

<span data-ttu-id="8edbc-115">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="8edbc-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="8edbc-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="8edbc-116">Example</span></span>

<span data-ttu-id="8edbc-117">`CONCATENATE ("abc", "def")` renvoie **« abcdef »**.</span><span class="sxs-lookup"><span data-stu-id="8edbc-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8edbc-118">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="8edbc-118">Usage notes</span></span>

<span data-ttu-id="8edbc-119">L'expression `"abc" & "def"` renvoie également **« abcdef »**.</span><span class="sxs-lookup"><span data-stu-id="8edbc-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8edbc-120">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8edbc-120">Additional resources</span></span>

[<span data-ttu-id="8edbc-121">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="8edbc-121">Text functions</span></span>](er-functions-category-text.md)