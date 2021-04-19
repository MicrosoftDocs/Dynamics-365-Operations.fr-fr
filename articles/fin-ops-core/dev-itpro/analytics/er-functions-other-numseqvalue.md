---
title: Fonction NUMSEQVALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction NUMSEQVALUE États électroniques (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: c3351360d0c1afca9f828ba4fc935096ddfd67f2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744001"
---
# <a name="numseqvalue-er-function"></a><span data-ttu-id="55750-103">Fonction NUMSEQVALUE ER</span><span class="sxs-lookup"><span data-stu-id="55750-103">NUMSEQVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="55750-104">La fonction `NUMSEQVALUE` renvoie une valeur de *Chaîne* qui représente la nouvelle valeur générée d’une souche de numéros, en fonction de la souche de numéros, de l’étendue et de l’ID d’étendue spécifiés.</span><span class="sxs-lookup"><span data-stu-id="55750-104">The `NUMSEQVALUE` function returns a *String* value that represents the new generated value of a number sequence, based on the specified number sequence, scope, and scope ID.</span></span> <span data-ttu-id="55750-105">L’ID d’étendue est égal à la société fournie par le contexte sous lequel le format d’états électroniques (ER) est exécuté.</span><span class="sxs-lookup"><span data-stu-id="55750-105">The scope ID equals the company code that is supplied by the context that the Electronic reporting (ER) format is run under.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="55750-106">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="55750-106">Syntax 1</span></span>

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a><span data-ttu-id="55750-107">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="55750-107">Syntax 2</span></span>

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a><span data-ttu-id="55750-108">Syntaxe 3</span><span class="sxs-lookup"><span data-stu-id="55750-108">Syntax 3</span></span>

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a><span data-ttu-id="55750-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="55750-109">Arguments</span></span>

<span data-ttu-id="55750-110">`number sequence code` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="55750-110">`number sequence code`: *String*</span></span>

<span data-ttu-id="55750-111">Valeur de texte qui représente le code de la souche de numéros dans laquelle une nouvelle valeur est requise.</span><span class="sxs-lookup"><span data-stu-id="55750-111">A text value that represents the code of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="55750-112">`number sequence record ID` : *Int64*</span><span class="sxs-lookup"><span data-stu-id="55750-112">`number sequence record ID`: *Int64*</span></span>

<span data-ttu-id="55750-113">Valeur *Int64* qui représente l’ID d’enregistrement d’un enregistrement dans la table NumberSequenceTable qui contient la définition de la souche de numéros dans laquelle une nouvelle valeur est requise.</span><span class="sxs-lookup"><span data-stu-id="55750-113">An *Int64* value that represents the record ID of a record in the NumberSequenceTable table that contains the definition of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="55750-114">`scope type` : *Valeur de l’énumération*</span><span class="sxs-lookup"><span data-stu-id="55750-114">`scope type`: *Enum value*</span></span>

<span data-ttu-id="55750-115">Valeur d’énumération de l’énumération **ERExpressionNumberSequenceScopeType** qui définit l’étendue de la souche de numéros dans laquelle une nouvelle valeur est requise.</span><span class="sxs-lookup"><span data-stu-id="55750-115">An enumeration value of the **ERExpressionNumberSequenceScopeType** enumeration that defines the scope of the number sequence that a new value is required in.</span></span> <span data-ttu-id="55750-116">Les types d’étendues disponibles sont **Partagé**, **Entité légale** et **Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="55750-116">The available scope types are **Shared**, **Legal entity**, and **Company**.</span></span>

<span data-ttu-id="55750-117">`scope ID` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="55750-117">`scope ID`: *String*</span></span>

<span data-ttu-id="55750-118">Valeur de *Chaîne* qui identifie l’étendue, en fonction du type d’étendue spécifié.</span><span class="sxs-lookup"><span data-stu-id="55750-118">A *String* value that identifies the scope, based on the specified scope type.</span></span>

## <a name="return-values"></a><span data-ttu-id="55750-119">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="55750-119">Return values</span></span>

<span data-ttu-id="55750-120">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="55750-120">*String*</span></span>

<span data-ttu-id="55750-121">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="55750-121">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="55750-122">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="55750-122">Usage notes</span></span>

<span data-ttu-id="55750-123">Pour le type d’étendue **Partagé**, spécifiez une chaîne vide comme ID d’étendue.</span><span class="sxs-lookup"><span data-stu-id="55750-123">For the **Shared** scope type, specify an empty string as the scope ID.</span></span>

<span data-ttu-id="55750-124">Pour les types d’étendues **Société** et **Entité juridique**, spécifiez le code société comme ID d’étendue.</span><span class="sxs-lookup"><span data-stu-id="55750-124">For the **Company** and **Legal entity** scope types, specify the company code as the scope ID.</span></span> <span data-ttu-id="55750-125">Si vous spécifiez une chaîne vide comme ID d’étendue pour ces types d’étendues, le code société actuel est utilisé.</span><span class="sxs-lookup"><span data-stu-id="55750-125">If you specify an empty string as the scope ID for these scope types, the current company code is used.</span></span>

<span data-ttu-id="55750-126">Lorsque la syntaxe 1 est utilisée, la souche de numéros est demandée pour le type d’étendue **Entreprise** et le code société est fourni par le contexte dans lequel le format ER est exécuté.</span><span class="sxs-lookup"><span data-stu-id="55750-126">When syntax 1 is used, the number sequence is requested for the **Company** scope type, and the company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-1"></a><span data-ttu-id="55750-127">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="55750-127">Example 1</span></span>

<span data-ttu-id="55750-128">Dans votre format ER, vous définissez la source de données **AskNumSeq** du type *Paramètre d’entrée utilisateur*.</span><span class="sxs-lookup"><span data-stu-id="55750-128">In your ER format, you define the **AskNumSeq** data source of the *User input parameter* type.</span></span> <span data-ttu-id="55750-129">Cette source de données fait référence au type de données étendu (EDT) **Description**.</span><span class="sxs-lookup"><span data-stu-id="55750-129">This data source refers to the **Description** extended data type (EDT).</span></span> <span data-ttu-id="55750-130">Ensuite, vous définissez la source de données **NumSeq** du type *Champ calculé*.</span><span class="sxs-lookup"><span data-stu-id="55750-130">Next, you define the **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="55750-131">Cette source de données contient l’expression `NUMSEQVALUE (AskNumSeq)`.</span><span class="sxs-lookup"><span data-stu-id="55750-131">This data source contains the expression `NUMSEQVALUE (AskNumSeq)`.</span></span> <span data-ttu-id="55750-132">Quand la source de données **NumSeq** est appelée, elle renvoie la nouvelle valeur générée de la souche de numéros spécifiée au moment de l’exécution en entrant son code dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="55750-132">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that was specified at runtime by entering its code in the dialog box.</span></span> <span data-ttu-id="55750-133">La souche de numéros est demandée pour le type d’étendue **Société**.</span><span class="sxs-lookup"><span data-stu-id="55750-133">The number sequence is requested for the **Company** scope type.</span></span> <span data-ttu-id="55750-134">Le code société est égal à la société fournie par le contexte sous lequel le format ER est exécuté.</span><span class="sxs-lookup"><span data-stu-id="55750-134">The company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-2"></a><span data-ttu-id="55750-135">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="55750-135">Example 2</span></span>

<span data-ttu-id="55750-136">Les sources de données suivantes sont définies dans la mise en correspondance des modèles :</span><span class="sxs-lookup"><span data-stu-id="55750-136">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="55750-137">Source de données **LedgerParms** du type *Table*.</span><span class="sxs-lookup"><span data-stu-id="55750-137">The **LedgerParms** data source of the *Table* type.</span></span> <span data-ttu-id="55750-138">Cette source de données fait référence à la table LedgerParameters.</span><span class="sxs-lookup"><span data-stu-id="55750-138">This data source refers to the LedgerParameters table.</span></span>
- <span data-ttu-id="55750-139">Source de données **NumSeq** du type *Champ calculé*.</span><span class="sxs-lookup"><span data-stu-id="55750-139">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="55750-140">Cette source de données contient l’expression `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span><span class="sxs-lookup"><span data-stu-id="55750-140">This data source contains the expression `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span></span>

<span data-ttu-id="55750-141">Lorsque la source de données **NumSeq** est appelée, elle renvoie la nouvelle valeur générée de la souche de numéros qui a été configurée dans les paramètres de la comptabilité pour la société qui fournit le contexte sous lequel le format ER est exécuté.</span><span class="sxs-lookup"><span data-stu-id="55750-141">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that has been configured in the General ledger parameters for the company that supplies the context that the ER format is run under.</span></span> <span data-ttu-id="55750-142">Cette souche de numéros identifie de manière unique les journaux et sert de numéro de lot qui relie les transactions.</span><span class="sxs-lookup"><span data-stu-id="55750-142">This number sequence uniquely identifies journals and acts as a batch number that links the transactions together.</span></span>

## <a name="example-3"></a><span data-ttu-id="55750-143">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="55750-143">Example 3</span></span>

<span data-ttu-id="55750-144">Les sources de données suivantes sont définies dans la mise en correspondance des modèles :</span><span class="sxs-lookup"><span data-stu-id="55750-144">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="55750-145">Source de données **enumScope** de type *énumération* Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="55750-145">The **enumScope** data source of the Microsoft Dynamics 365 Finance *enumeration* type.</span></span> <span data-ttu-id="55750-146">Cette source de données fait référence au type d’énumération **ERExpressionNumberSequenceScopeType**.</span><span class="sxs-lookup"><span data-stu-id="55750-146">This data source refers to the **ERExpressionNumberSequenceScopeType** enumeration.</span></span>
- <span data-ttu-id="55750-147">Source de données **NumSeq** du type *Champ calculé*.</span><span class="sxs-lookup"><span data-stu-id="55750-147">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="55750-148">Cette source de données contient l’expression `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span><span class="sxs-lookup"><span data-stu-id="55750-148">This data source contains the expression `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span></span>

<span data-ttu-id="55750-149">Lorsque la source de données **NumSeq** est appelée, elle renvoie la nouvelle valeur générée de la souche de numéros **Gene\_1** qui a été configurée pour la société qui fournit le contexte sous lequel le format ER est exécuté.</span><span class="sxs-lookup"><span data-stu-id="55750-149">When the **NumSeq** data source is called, it returns the new generated value of the **Gene\_1** number sequence that has been configured for the company that supplies the context that the ER format is run under.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="55750-150">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="55750-150">Additional resources</span></span>

[<span data-ttu-id="55750-151">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="55750-151">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]