---
title: Fonction LISTJOIN ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction LISTJOIN États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b5b82917e3083b5ffe4546a6a15fd14938383a
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249033"
---
# <a name=""></a><span data-ttu-id="146ac-103"><a name="LISTJOIN">Fonction LISTJOIN ER</a></span><span class="sxs-lookup"><span data-stu-id="146ac-103"><a name="LISTJOIN">LISTJOIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="146ac-104">La fonction `LISTJOIN` renvoie une valeur *Liste des enregistrements* qui représente une nouvelle liste d'enregistrements créée à partir des arguments spécifiés.</span><span class="sxs-lookup"><span data-stu-id="146ac-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="146ac-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="146ac-105">Syntax</span></span>

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="146ac-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="146ac-106">Arguments</span></span>

<span data-ttu-id="146ac-107">`list 1` : *Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="146ac-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="146ac-108">Référence à une source de données du type de données *Liste d'enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="146ac-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="146ac-109">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="146ac-109">This argument is mandatory.</span></span>

<span data-ttu-id="146ac-110">`list N` : *Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="146ac-110">`list N`: *Record list*</span></span>

<span data-ttu-id="146ac-111">Référence à une source de données du type de données *Liste d'enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="146ac-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="146ac-112">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="146ac-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="146ac-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="146ac-113">Return values</span></span>

<span data-ttu-id="146ac-114">*Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="146ac-114">*Record list*</span></span>

<span data-ttu-id="146ac-115">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="146ac-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="146ac-116">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="146ac-116">Usage notes</span></span>

<span data-ttu-id="146ac-117">La structure de la liste qui est créée contient uniquement les champs qui sont présentés dans la structure de chaque enregistrement mentionné dans les arguments.</span><span class="sxs-lookup"><span data-stu-id="146ac-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="146ac-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="146ac-118">Example</span></span>

<span data-ttu-id="146ac-119">Vous entrez une source de données **Enregistrement 1** du type `Container`.</span><span class="sxs-lookup"><span data-stu-id="146ac-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="146ac-120">Cette source de données contient les champs imbriqués suivants du type `Calculated field` :</span><span class="sxs-lookup"><span data-stu-id="146ac-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="146ac-121">**Code** : Ce champ contient une expression qui renvoie une valeur de type `String`.</span><span class="sxs-lookup"><span data-stu-id="146ac-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="146ac-122">**Montant** : Ce champ contient une expression qui renvoie une valeur de type `Real`.</span><span class="sxs-lookup"><span data-stu-id="146ac-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="146ac-123">Vous entrez ensuite une source de données **Enregistrement 2** du type `Container`.</span><span class="sxs-lookup"><span data-stu-id="146ac-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="146ac-124">Cette source de données contient les champs imbriqués suivants du type `Calculated field` :</span><span class="sxs-lookup"><span data-stu-id="146ac-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="146ac-125">**Montant** : Ce champ contient une expression qui renvoie une valeur de type `Real`.</span><span class="sxs-lookup"><span data-stu-id="146ac-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="146ac-126">**IsValid** : Ce champ contient une expression qui renvoie une valeur de type `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="146ac-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

<span data-ttu-id="146ac-127">Dans ce cas, l'expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` renvoie une nouvelle liste qui contient deux enregistrements.</span><span class="sxs-lookup"><span data-stu-id="146ac-127">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span> <span data-ttu-id="146ac-128">La structure de cette liste se compose d'un seul champ **Montant** de type `Real`, car ce champ est le seul champ présenté dans chaque argument de la fonction appelée.</span><span class="sxs-lookup"><span data-stu-id="146ac-128">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="146ac-129">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="146ac-129">Additional resources</span></span>

[<span data-ttu-id="146ac-130">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="146ac-130">List functions</span></span>](er-functions-category-list.md)
