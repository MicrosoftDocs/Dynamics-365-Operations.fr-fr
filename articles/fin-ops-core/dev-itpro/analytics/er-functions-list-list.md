---
title: Fonction LIST ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction LIST États électroniques (ER).
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
ms.openlocfilehash: ee51b6da008d1c0fcfb303e9659f507629237333
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042019"
---
# <span data-ttu-id="7e710-103"><a name="LIST">Fonction LIST ER</a></span><span class="sxs-lookup"><span data-stu-id="7e710-103"><a name="LIST">LIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7e710-104">La fonction `LIST` renvoie une valeur *Liste des enregistrements* constituée d'une nouvelle liste d'enregistrements créée à partir des arguments spécifiés.</span><span class="sxs-lookup"><span data-stu-id="7e710-104">The `LIST` function returns a *Record list* value that consists of a new list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="7e710-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7e710-105">Syntax</span></span>

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a><span data-ttu-id="7e710-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="7e710-106">Arguments</span></span>

<span data-ttu-id="7e710-107">`record 1` : *Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="7e710-107">`record 1`: *Container (record)*</span></span>

<span data-ttu-id="7e710-108">Référence à une source de données du type de données *Enregistrement*.</span><span class="sxs-lookup"><span data-stu-id="7e710-108">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="7e710-109">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="7e710-109">This argument is required.</span></span>

<span data-ttu-id="7e710-110">`record N` : *Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="7e710-110">`record N`: *Container (record)*</span></span>

<span data-ttu-id="7e710-111">Référence à une source de données du type de données *Enregistrement*.</span><span class="sxs-lookup"><span data-stu-id="7e710-111">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="7e710-112">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="7e710-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="7e710-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="7e710-113">Return values</span></span>

<span data-ttu-id="7e710-114">*Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="7e710-114">*Record list*</span></span>

<span data-ttu-id="7e710-115">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="7e710-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7e710-116">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="7e710-116">Usage notes</span></span>

<span data-ttu-id="7e710-117">La structure de la liste qui est créée contient uniquement les champs qui sont présentés dans la structure de chaque enregistrement mentionné dans les arguments.</span><span class="sxs-lookup"><span data-stu-id="7e710-117">The structure of the list that is created contains only the fields that are presented in the structure of every record that is mentioned in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="7e710-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="7e710-118">Example</span></span>

<span data-ttu-id="7e710-119">Vous entrez une source de données **Enregistrement 1** du type *Conteneur*.</span><span class="sxs-lookup"><span data-stu-id="7e710-119">You enter data source **Record 1** of the *Container* type.</span></span> <span data-ttu-id="7e710-120">Cette source de données contient les champs imbriqués suivants du type *Champ calculé* :</span><span class="sxs-lookup"><span data-stu-id="7e710-120">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="7e710-121">**Code :** Ce champ contient une expression qui renvoie une valeur de type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="7e710-121">**Code:** This field contains an expression that returns a value of the *String* type.</span></span>
- <span data-ttu-id="7e710-122">**Montant :** Ce champ contient une expression qui renvoie une valeur de type *Réel*.</span><span class="sxs-lookup"><span data-stu-id="7e710-122">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>

<span data-ttu-id="7e710-123">Vous entrez ensuite une source de données **Enregistrement 2** du type *Conteneur*.</span><span class="sxs-lookup"><span data-stu-id="7e710-123">You then enter data source **Record 2** of the *Container* type.</span></span> <span data-ttu-id="7e710-124">Cette source de données contient les champs imbriqués suivants du type *Champ calculé* :</span><span class="sxs-lookup"><span data-stu-id="7e710-124">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="7e710-125">**Montant :** Ce champ contient une expression qui renvoie une valeur de type *Réel*.</span><span class="sxs-lookup"><span data-stu-id="7e710-125">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>
- <span data-ttu-id="7e710-126">**IsValid :** Ce champ contient une expression qui renvoie une valeur de type *Booléen*.</span><span class="sxs-lookup"><span data-stu-id="7e710-126">**IsValid:** This field contains an expression that returns a value of the *Boolean* type.</span></span>

<span data-ttu-id="7e710-127">Dans ce cas, l'expression `LIST('Record 1', 'Record 2')` renvoie une nouvelle liste qui contient deux enregistrements.</span><span class="sxs-lookup"><span data-stu-id="7e710-127">In this case, the expression `LIST('Record 1', 'Record 2')` returns a new list that contains two records.</span></span> <span data-ttu-id="7e710-128">La structure de cette liste se compose d'un seul champ **Montant** de type *Réel*, car ce champ est le seul champ présenté dans chaque argument de la fonction appelée.</span><span class="sxs-lookup"><span data-stu-id="7e710-128">The structure of this list consists of a single **Amount** field of the *Real* type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7e710-129">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7e710-129">Additional resources</span></span>

[<span data-ttu-id="7e710-130">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="7e710-130">List functions</span></span>](er-functions-category-list.md)
