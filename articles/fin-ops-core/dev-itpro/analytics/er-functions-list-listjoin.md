---
title: Fonction LISTJOIN ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction LISTJOIN États électroniques (ER).
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
ms.openlocfilehash: c7f78b687865e63e658c1c1c4f148b50595bf063
ms.sourcegitcommit: 54bdcf8e9b6d1b1aae2a244f7a82754879d12053
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2020
ms.locfileid: "3740661"
---
# <a name=""></a><span data-ttu-id="2741a-103"><a name="LISTJOIN">Fonction LISTJOIN ER</a></span><span class="sxs-lookup"><span data-stu-id="2741a-103"><a name="LISTJOIN">LISTJOIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2741a-104">La fonction `LISTJOIN` renvoie une valeur *Liste des enregistrements* qui représente une nouvelle liste d’enregistrements créée à partir des arguments spécifiés.</span><span class="sxs-lookup"><span data-stu-id="2741a-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="2741a-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2741a-105">Syntax</span></span>

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="2741a-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="2741a-106">Arguments</span></span>

<span data-ttu-id="2741a-107">`list 1` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="2741a-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="2741a-108">Référence à une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="2741a-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="2741a-109">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="2741a-109">This argument is mandatory.</span></span>

<span data-ttu-id="2741a-110">`list N` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="2741a-110">`list N`: *Record list*</span></span>

<span data-ttu-id="2741a-111">Référence à une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="2741a-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="2741a-112">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="2741a-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="2741a-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="2741a-113">Return values</span></span>

<span data-ttu-id="2741a-114">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="2741a-114">*Record list*</span></span>

<span data-ttu-id="2741a-115">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="2741a-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2741a-116">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="2741a-116">Usage notes</span></span>

<span data-ttu-id="2741a-117">La structure de la liste qui est créée contient uniquement les champs qui sont présentés dans la structure de chaque enregistrement mentionné dans les arguments.</span><span class="sxs-lookup"><span data-stu-id="2741a-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="2741a-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="2741a-118">Example</span></span>

<span data-ttu-id="2741a-119">Vous entrez une source de données **Enregistrement 1** du type `Container`.</span><span class="sxs-lookup"><span data-stu-id="2741a-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="2741a-120">Cette source de données contient les champs imbriqués suivants du type `Calculated field` :</span><span class="sxs-lookup"><span data-stu-id="2741a-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="2741a-121">**Code** : Ce champ contient une expression qui renvoie une valeur de type `String`.</span><span class="sxs-lookup"><span data-stu-id="2741a-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="2741a-122">**Montant** : Ce champ contient une expression qui renvoie une valeur de type `Real`.</span><span class="sxs-lookup"><span data-stu-id="2741a-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="2741a-123">Vous entrez ensuite une source de données **Enregistrement 2** du type `Container`.</span><span class="sxs-lookup"><span data-stu-id="2741a-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="2741a-124">Cette source de données contient les champs imbriqués suivants du type `Calculated field` :</span><span class="sxs-lookup"><span data-stu-id="2741a-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="2741a-125">**Montant** : Ce champ contient une expression qui renvoie une valeur de type `Real`.</span><span class="sxs-lookup"><span data-stu-id="2741a-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="2741a-126">**IsValid** : Ce champ contient une expression qui renvoie une valeur de type `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="2741a-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

![Page du concepteur de mise en correspondance des modèles ER](./media/er-functions-list-listjoin-image1.gif)

<span data-ttu-id="2741a-128">Dans ce cas, l’expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` renvoie une nouvelle liste qui contient deux enregistrements.</span><span class="sxs-lookup"><span data-stu-id="2741a-128">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span>

![Page du concepteur de mise en correspondance des modèles ER](./media/er-functions-list-listjoin-image2.gif)

<span data-ttu-id="2741a-130">La structure de cette liste se compose d’un seul champ **Montant** de type `Real`, car ce champ est le seul champ présenté dans chaque argument de la fonction appelée.</span><span class="sxs-lookup"><span data-stu-id="2741a-130">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

![Page du concepteur de mise en correspondance des modèles ER](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a><span data-ttu-id="2741a-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2741a-132">Additional resources</span></span>

[<span data-ttu-id="2741a-133">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="2741a-133">List functions</span></span>](er-functions-category-list.md)

[<span data-ttu-id="2741a-134">Déboguer les sources de données d’un format ER exécuté pour analyser le flux de données et la transformation</span><span class="sxs-lookup"><span data-stu-id="2741a-134">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>](er-debug-data-sources.md)
