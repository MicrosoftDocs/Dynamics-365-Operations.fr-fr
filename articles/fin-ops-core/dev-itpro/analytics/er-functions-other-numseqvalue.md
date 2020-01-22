---
title: Fonction NUMSEQVALUE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction NUMSEQVALUE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: d68784524a5639d8d447daa2cda940680d795542
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915830"
---
# <span data-ttu-id="07fa4-103"><a name="NUMSEQVALUE">Fonction NUMSEQVALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="07fa4-103"><a name="NUMSEQVALUE">NUMSEQVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="07fa4-104">La fonction `NUMSEQVALUE` renvoie une valeur de *Chaîne* qui représente la nouvelle valeur générée d'une souche de numéros, en fonction de la souche de numéros, de l'étendue et de l'ID d'étendue spécifiés.</span><span class="sxs-lookup"><span data-stu-id="07fa4-104">The `NUMSEQVALUE` function returns a *String* value that represents the new generated value of a number sequence, based on the specified number sequence, scope, and scope ID.</span></span> <span data-ttu-id="07fa4-105">L'ID d'étendue est égal à la société fournie par le contexte sous lequel le format d'états électroniques (ER) est exécuté.</span><span class="sxs-lookup"><span data-stu-id="07fa4-105">The scope ID equals the company code that is supplied by the context that the Electronic reporting (ER) format is run under.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="07fa4-106">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="07fa4-106">Syntax 1</span></span>

```
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a><span data-ttu-id="07fa4-107">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="07fa4-107">Syntax 2</span></span>

```
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a><span data-ttu-id="07fa4-108">Syntaxe 3</span><span class="sxs-lookup"><span data-stu-id="07fa4-108">Syntax 3</span></span>

```
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a><span data-ttu-id="07fa4-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="07fa4-109">Arguments</span></span>

<span data-ttu-id="07fa4-110">`number sequence code` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="07fa4-110">`number sequence code`: *String*</span></span>

<span data-ttu-id="07fa4-111">Valeur de texte qui représente le code de la souche de numéros dans laquelle une nouvelle valeur est requise.</span><span class="sxs-lookup"><span data-stu-id="07fa4-111">A text value that represents the code of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="07fa4-112">`number sequence record ID` : *Int64*</span><span class="sxs-lookup"><span data-stu-id="07fa4-112">`number sequence record ID`: *Int64*</span></span>

<span data-ttu-id="07fa4-113">Valeur *Int64* qui représente l'ID d'enregistrement d'un enregistrement dans la table NumberSequenceTable qui contient la définition de la souche de numéros dans laquelle une nouvelle valeur est requise.</span><span class="sxs-lookup"><span data-stu-id="07fa4-113">An *Int64* value that represents the record ID of a record in the NumberSequenceTable table that contains the definition of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="07fa4-114">`scope type` : *Valeur de l'énumération*</span><span class="sxs-lookup"><span data-stu-id="07fa4-114">`scope type`: *Enum value*</span></span>

<span data-ttu-id="07fa4-115">Valeur d'énumération de l'énumération **ERExpressionNumberSequenceScopeType** qui définit l'étendue de la souche de numéros dans laquelle une nouvelle valeur est requise.</span><span class="sxs-lookup"><span data-stu-id="07fa4-115">An enumeration value of the **ERExpressionNumberSequenceScopeType** enumeration that defines the scope of the number sequence that a new value is required in.</span></span> <span data-ttu-id="07fa4-116">Les types d'étendues disponibles sont **Partagé**, **Entité légale** et **Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="07fa4-116">The available scope types are **Shared**, **Legal entity**, and **Company**.</span></span>

<span data-ttu-id="07fa4-117">`scope ID` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="07fa4-117">`scope ID`: *String*</span></span>

<span data-ttu-id="07fa4-118">Valeur de *Chaîne* qui identifie l'étendue, en fonction du type d'étendue spécifié.</span><span class="sxs-lookup"><span data-stu-id="07fa4-118">A *String* value that identifies the scope, based on the specified scope type.</span></span>

## <a name="return-values"></a><span data-ttu-id="07fa4-119">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="07fa4-119">Return values</span></span>

<span data-ttu-id="07fa4-120">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="07fa4-120">*String*</span></span>

<span data-ttu-id="07fa4-121">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="07fa4-121">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="07fa4-122">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="07fa4-122">Usage notes</span></span>

<span data-ttu-id="07fa4-123">Pour le type d'étendue **Partagé**, spécifiez une chaîne vide comme ID d'étendue.</span><span class="sxs-lookup"><span data-stu-id="07fa4-123">For the **Shared** scope type, specify an empty string as the scope ID.</span></span>

<span data-ttu-id="07fa4-124">Pour les types d'étendues **Société** et **Entité juridique**, spécifiez le code société comme ID d'étendue.</span><span class="sxs-lookup"><span data-stu-id="07fa4-124">For the **Company** and **Legal entity** scope types, specify the company code as the scope ID.</span></span> <span data-ttu-id="07fa4-125">Si vous spécifiez une chaîne vide comme ID d'étendue pour ces types d'étendues, le code société actuel est utilisé.</span><span class="sxs-lookup"><span data-stu-id="07fa4-125">If you specify an empty string as the scope ID for these scope types, the current company code is used.</span></span>

<span data-ttu-id="07fa4-126">Lorsque la syntaxe 1 est utilisée, la souche de numéros est demandée pour le type d'étendue **Entreprise** et le code société est fourni par le contexte dans lequel le format ER est exécuté.</span><span class="sxs-lookup"><span data-stu-id="07fa4-126">When syntax 1 is used, the number sequence is requested for the **Company** scope type, and the company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-1"></a><span data-ttu-id="07fa4-127">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="07fa4-127">Example 1</span></span>

<span data-ttu-id="07fa4-128">Dans votre format ER, vous définissez la source de données **AskNumSeq** du type *Paramètre d'entrée utilisateur*.</span><span class="sxs-lookup"><span data-stu-id="07fa4-128">In your ER format, you define the **AskNumSeq** data source of the *User input parameter* type.</span></span> <span data-ttu-id="07fa4-129">Cette source de données fait référence au type de données étendu (EDT) **Description**.</span><span class="sxs-lookup"><span data-stu-id="07fa4-129">This data source refers to the **Description** extended data type (EDT).</span></span> <span data-ttu-id="07fa4-130">Ensuite, vous définissez la source de données **NumSeq** du type *Champ calculé*.</span><span class="sxs-lookup"><span data-stu-id="07fa4-130">Next, you define the **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="07fa4-131">Cette source de données contient l'expression `NUMSEQVALUE (AskNumSeq)`.</span><span class="sxs-lookup"><span data-stu-id="07fa4-131">This data source contains the expression `NUMSEQVALUE (AskNumSeq)`.</span></span> <span data-ttu-id="07fa4-132">Quand la source de données **NumSeq** est appelée, elle renvoie la nouvelle valeur générée de la souche de numéros spécifiée au moment de l'exécution en entrant son code dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="07fa4-132">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that was specified at runtime by entering its code in the dialog box.</span></span> <span data-ttu-id="07fa4-133">La souche de numéros est demandée pour le type d'étendue **Société**.</span><span class="sxs-lookup"><span data-stu-id="07fa4-133">The number sequence is requested for the **Company** scope type.</span></span> <span data-ttu-id="07fa4-134">Le code société est égal à la société fournie par le contexte sous lequel le format ER est exécuté.</span><span class="sxs-lookup"><span data-stu-id="07fa4-134">The company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-2"></a><span data-ttu-id="07fa4-135">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="07fa4-135">Example 2</span></span>

<span data-ttu-id="07fa4-136">Les sources de données suivantes sont définies dans la mise en correspondance des modèles :</span><span class="sxs-lookup"><span data-stu-id="07fa4-136">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="07fa4-137">Source de données **LedgerParms** du type *Table*.</span><span class="sxs-lookup"><span data-stu-id="07fa4-137">The **LedgerParms** data source of the *Table* type.</span></span> <span data-ttu-id="07fa4-138">Cette source de données fait référence à la table LedgerParameters.</span><span class="sxs-lookup"><span data-stu-id="07fa4-138">This data source refers to the LedgerParameters table.</span></span>
- <span data-ttu-id="07fa4-139">Source de données **NumSeq** du type *Champ calculé*.</span><span class="sxs-lookup"><span data-stu-id="07fa4-139">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="07fa4-140">Cette source de données contient l'expression `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span><span class="sxs-lookup"><span data-stu-id="07fa4-140">This data source contains the expression `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span></span>

<span data-ttu-id="07fa4-141">Lorsque la source de données **NumSeq** est appelée, elle renvoie la nouvelle valeur générée de la souche de numéros qui a été configurée dans les paramètres de la comptabilité pour la société qui fournit le contexte sous lequel le format ER est exécuté.</span><span class="sxs-lookup"><span data-stu-id="07fa4-141">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that has been configured in the General ledger parameters for the company that supplies the context that the ER format is run under.</span></span> <span data-ttu-id="07fa4-142">Cette souche de numéros identifie de manière unique les journaux et sert de numéro de lot qui relie les transactions.</span><span class="sxs-lookup"><span data-stu-id="07fa4-142">This number sequence uniquely identifies journals and acts as a batch number that links the transactions together.</span></span>

## <a name="example-3"></a><span data-ttu-id="07fa4-143">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="07fa4-143">Example 3</span></span>

<span data-ttu-id="07fa4-144">Les sources de données suivantes sont définies dans la mise en correspondance des modèles :</span><span class="sxs-lookup"><span data-stu-id="07fa4-144">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="07fa4-145">Source de données **enumScope** de type *énumération* Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="07fa4-145">The **enumScope** data source of the Microsoft Dynamics 365 Finance *enumeration* type.</span></span> <span data-ttu-id="07fa4-146">Cette source de données fait référence au type d'énumération **ERExpressionNumberSequenceScopeType**.</span><span class="sxs-lookup"><span data-stu-id="07fa4-146">This data source refers to the **ERExpressionNumberSequenceScopeType** enumeration.</span></span>
- <span data-ttu-id="07fa4-147">Source de données **NumSeq** du type *Champ calculé*.</span><span class="sxs-lookup"><span data-stu-id="07fa4-147">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="07fa4-148">Cette source de données contient l'expression `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span><span class="sxs-lookup"><span data-stu-id="07fa4-148">This data source contains the expression `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span></span>

<span data-ttu-id="07fa4-149">Lorsque la source de données **NumSeq** est appelée, elle renvoie la nouvelle valeur générée de la souche de numéros **Gene\_1** qui a été configurée pour la société qui fournit le contexte sous lequel le format ER est exécuté.</span><span class="sxs-lookup"><span data-stu-id="07fa4-149">When the **NumSeq** data source is called, it returns the new generated value of the **Gene\_1** number sequence that has been configured for the company that supplies the context that the ER format is run under.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="07fa4-150">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="07fa4-150">Additional resources</span></span>

[<span data-ttu-id="07fa4-151">Autre fonctions (spécifiques au domaine d'affaires)</span><span class="sxs-lookup"><span data-stu-id="07fa4-151">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
