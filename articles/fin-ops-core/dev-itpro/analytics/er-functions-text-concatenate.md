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
ms.openlocfilehash: 04c7b32e2a9578f8864570a552817ec3ce28fa43
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041161"
---
# <span data-ttu-id="78b2c-103"><a name="CONCATENATE">Fonction CONCATENATE ER</a></span><span class="sxs-lookup"><span data-stu-id="78b2c-103"><a name="CONCATENATE">CONCATENATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78b2c-104">La fonction `CONCATENATE` renvoie toutes les chaînes de texte spécifiées en tant que valeur de *Chaîne* après avoir été jointes en une seule chaîne.</span><span class="sxs-lookup"><span data-stu-id="78b2c-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="78b2c-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="78b2c-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="78b2c-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="78b2c-106">Arguments</span></span>

<span data-ttu-id="78b2c-107">`text 1` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="78b2c-107">`text 1`: *String*</span></span>

<span data-ttu-id="78b2c-108">Référence à une source de données du type de données *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="78b2c-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="78b2c-109">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="78b2c-109">This argument is required.</span></span>

<span data-ttu-id="78b2c-110">`text N` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="78b2c-110">`text N`: *String*</span></span>

<span data-ttu-id="78b2c-111">Référence à une source de données du type de données *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="78b2c-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="78b2c-112">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="78b2c-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="78b2c-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="78b2c-113">Return values</span></span>

<span data-ttu-id="78b2c-114">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="78b2c-114">*String*</span></span>

<span data-ttu-id="78b2c-115">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="78b2c-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="78b2c-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="78b2c-116">Example</span></span>

<span data-ttu-id="78b2c-117">`CONCATENATE ("abc", "def")` renvoie **« abcdef »**.</span><span class="sxs-lookup"><span data-stu-id="78b2c-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="78b2c-118">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="78b2c-118">Usage notes</span></span>

<span data-ttu-id="78b2c-119">L'expression `"abc" & "def"` renvoie également **« abcdef »**.</span><span class="sxs-lookup"><span data-stu-id="78b2c-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78b2c-120">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="78b2c-120">Additional resources</span></span>

[<span data-ttu-id="78b2c-121">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="78b2c-121">Text functions</span></span>](er-functions-category-text.md)
