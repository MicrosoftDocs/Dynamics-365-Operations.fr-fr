---
title: Fonction ORDERBY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ORDERBY États électroniques (ER).
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
ms.openlocfilehash: 6ff280d66fd2c418984f2d7fd31a32609932e89c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745007"
---
# <a name="orderby-er-function"></a><span data-ttu-id="62f10-103">Fonction ORDERBY ER</span><span class="sxs-lookup"><span data-stu-id="62f10-103">ORDERBY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62f10-104">La fonction `ORDERBY` renvoie la liste spécifiée sous la forme d’une *Liste des enregistrements* après avoir été triée selon les arguments spécifiés.</span><span class="sxs-lookup"><span data-stu-id="62f10-104">The `ORDERBY` function returns the specified list as a *Record list* value after it has been sorted according to the specified arguments.</span></span> <span data-ttu-id="62f10-105">Ces arguments peuvent être définis comme expressions.</span><span class="sxs-lookup"><span data-stu-id="62f10-105">These arguments can be defined as expressions.</span></span>

## <a name="syntax"></a><span data-ttu-id="62f10-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="62f10-106">Syntax</span></span>

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a><span data-ttu-id="62f10-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="62f10-107">Arguments</span></span>

<span data-ttu-id="62f10-108">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="62f10-108">`list`: *Record list*</span></span>

<span data-ttu-id="62f10-109">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="62f10-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="62f10-110">`expression 1` : *Champ*</span><span class="sxs-lookup"><span data-stu-id="62f10-110">`expression 1`: *Field*</span></span>

<span data-ttu-id="62f10-111">Chemin valide d’un champ de la source de données référencé par l’argument `list` de la fonction appelée.</span><span class="sxs-lookup"><span data-stu-id="62f10-111">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="62f10-112">Le champ référencé doit être un champ du type de données primitif.</span><span class="sxs-lookup"><span data-stu-id="62f10-112">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="62f10-113">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="62f10-113">This argument is required.</span></span>

<span data-ttu-id="62f10-114">`expression N` : *Champ*</span><span class="sxs-lookup"><span data-stu-id="62f10-114">`expression N`: *Field*</span></span>

<span data-ttu-id="62f10-115">Chemin valide d’un champ de la source de données référencé par l’argument `list` de la fonction appelée.</span><span class="sxs-lookup"><span data-stu-id="62f10-115">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="62f10-116">Le champ référencé doit être un champ du type de données primitif.</span><span class="sxs-lookup"><span data-stu-id="62f10-116">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="62f10-117">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="62f10-117">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="62f10-118">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="62f10-118">Return values</span></span>

<span data-ttu-id="62f10-119">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="62f10-119">*Record list*</span></span>

<span data-ttu-id="62f10-120">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="62f10-120">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="62f10-121">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="62f10-121">Example 1</span></span>

<span data-ttu-id="62f10-122">Si vous entrez une source de données **DS** de type *Champ calculé*, et qu’elle contient l’expression `SPLIT ("C|B|A", "|")`, l’expression `FIRST( ORDERBY( DS, DS. Value)).Value` renvoie la valeur de texte **« A »**.</span><span class="sxs-lookup"><span data-stu-id="62f10-122">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( ORDERBY( DS, DS. Value)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="62f10-123">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="62f10-123">Example 2</span></span>

<span data-ttu-id="62f10-124">Si **Fournisseur** est configuré comme source de données d’états électroniques qui fait référence à la table VendTable, l’expression `ORDERBY (Vendors, Vendors.'name()')` renvoie une liste de fournisseurs qui est triée par nom dans l’ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="62f10-124">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `ORDERBY (Vendors, Vendors.'name()')` returns a list of vendors that is sorted by name in ascending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="62f10-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="62f10-125">Additional resources</span></span>

[<span data-ttu-id="62f10-126">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="62f10-126">List functions</span></span>](er-functions-category-list.md)
