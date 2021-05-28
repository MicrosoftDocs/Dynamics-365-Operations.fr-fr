---
title: Fonction LISTJOIN ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction LISTJOIN États électroniques (ER).
author: NickSelin
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b300cef0a508f7cc37397480738091158efdead
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027913"
---
# <a name="listjoin-er-function"></a><span data-ttu-id="7d7e2-103">Fonction LISTJOIN ER</span><span class="sxs-lookup"><span data-stu-id="7d7e2-103">LISTJOIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7d7e2-104">La fonction `LISTJOIN` renvoie une valeur *Liste des enregistrements* qui représente une nouvelle liste d’enregistrements créée à partir des arguments spécifiés.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d7e2-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7d7e2-105">Syntax</span></span>

```vb
LISTJOIN (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="7d7e2-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="7d7e2-106">Arguments</span></span>

<span data-ttu-id="7d7e2-107">`list 1` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="7d7e2-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="7d7e2-108">Référence à une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="7d7e2-109">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-109">This argument is mandatory.</span></span>

<span data-ttu-id="7d7e2-110">`list N` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="7d7e2-110">`list N`: *Record list*</span></span>

<span data-ttu-id="7d7e2-111">Référence à une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="7d7e2-112">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="7d7e2-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="7d7e2-113">Return values</span></span>

<span data-ttu-id="7d7e2-114">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="7d7e2-114">*Record list*</span></span>

<span data-ttu-id="7d7e2-115">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7d7e2-116">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="7d7e2-116">Usage notes</span></span>

<span data-ttu-id="7d7e2-117">La structure de la liste qui est créée contient uniquement les champs qui sont présentés dans la structure de chaque enregistrement mentionné dans les arguments.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="7d7e2-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="7d7e2-118">Example</span></span>

<span data-ttu-id="7d7e2-119">Vous entrez une source de données **Enregistrement 1** du type `Container`.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="7d7e2-120">Cette source de données contient les champs imbriqués suivants du type `Calculated field` :</span><span class="sxs-lookup"><span data-stu-id="7d7e2-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="7d7e2-121">**Code** : Ce champ contient une expression qui renvoie une valeur de type `String`.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="7d7e2-122">**Montant** : Ce champ contient une expression qui renvoie une valeur de type `Real`.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="7d7e2-123">Vous entrez ensuite une source de données **Enregistrement 2** du type `Container`.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="7d7e2-124">Cette source de données contient les champs imbriqués suivants du type `Calculated field` :</span><span class="sxs-lookup"><span data-stu-id="7d7e2-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="7d7e2-125">**Montant** : Ce champ contient une expression qui renvoie une valeur de type `Real`.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="7d7e2-126">**IsValid** : Ce champ contient une expression qui renvoie une valeur de type `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

![Page du concepteur de mise en correspondance des modèles ER](./media/er-functions-list-listjoin-image1.gif)

<span data-ttu-id="7d7e2-128">Dans ce cas, l’expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` renvoie une nouvelle liste qui contient deux enregistrements.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-128">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span>

![Page de concepteur de mappage de modèle ER avec deux enregistrements](./media/er-functions-list-listjoin-image2.gif)

<span data-ttu-id="7d7e2-130">La structure de cette liste se compose d’un seul champ **Montant** de type `Real`, car ce champ est le seul champ présenté dans chaque argument de la fonction appelée.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-130">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

![Champ Montant de la page du concepteur de mise en correspondance des modèles ER](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a><span data-ttu-id="7d7e2-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7d7e2-132">Additional resources</span></span>

[<span data-ttu-id="7d7e2-133">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="7d7e2-133">List functions</span></span>](er-functions-category-list.md)

[<span data-ttu-id="7d7e2-134">Déboguer les sources de données d’un format ER exécuté pour analyser le flux de données et la transformation</span><span class="sxs-lookup"><span data-stu-id="7d7e2-134">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>](er-debug-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
