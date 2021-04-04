---
title: Fonction ER CONTAINS
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CONTAINS États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: 81964681688cebf870bc9b6c59aff0b7fdd82449
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557518"
---
# <a name="contains-er-function"></a><span data-ttu-id="25c01-103">Fonction ER CONTAINS</span><span class="sxs-lookup"><span data-stu-id="25c01-103">CONTAINS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="25c01-104">La fonction `CONTAINS` détermine si l’entrée spécifiée contient le texte spécifié.</span><span class="sxs-lookup"><span data-stu-id="25c01-104">The `CONTAINS` function determines whether the specified input contains the specified text.</span></span> <span data-ttu-id="25c01-105">Elle renvoie une valeur *Booléenne* **TRUE** si l’entrée spécifiée ne contient pas le texte spécifié.</span><span class="sxs-lookup"><span data-stu-id="25c01-105">It returns a *Boolean* value of **TRUE** if the specified input contains the specified text.</span></span> <span data-ttu-id="25c01-106">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="25c01-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="25c01-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="25c01-107">Syntax</span></span>

```vb
CONTAINS (input, search text)
```

## <a name="arguments"></a><span data-ttu-id="25c01-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="25c01-108">Arguments</span></span>

<span data-ttu-id="25c01-109">`input` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="25c01-109">`input`: *String*</span></span>

<span data-ttu-id="25c01-110">Le chemin valide d’un élément d’une source de données du type *Chaîne* ou d’une constante de chaîne, dont la valeur peut contenir le deuxième argument.</span><span class="sxs-lookup"><span data-stu-id="25c01-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might contain the second argument.</span></span>

<span data-ttu-id="25c01-111">`search text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="25c01-111">`search text`: *String*</span></span>

<span data-ttu-id="25c01-112">Le chemin valide d’une source de données du type de données *Chaîne* ou d’une constante de chaîne, dont la valeur peut être contenue dans le premier argument.</span><span class="sxs-lookup"><span data-stu-id="25c01-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be contained in the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="25c01-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="25c01-113">Return values</span></span>

<span data-ttu-id="25c01-114">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="25c01-114">*Boolean*</span></span>

<span data-ttu-id="25c01-115">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="25c01-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="25c01-116">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="25c01-116">Usage notes</span></span>

<span data-ttu-id="25c01-117">Cette fonction peut être utilisée pour spécifier une expression de condition de la fonction [FILTER](er-functions-list-filter.md) uniquement lorsque le mappage approprié est configuré dans [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) accéder [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="25c01-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="25c01-118">Sinon, une exception est levée au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="25c01-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="25c01-119">Le message que vous recevez vous recommande d’utiliser la fonction [WHERE](er-functions-list-where.md) au lieu de la fonction `FILTER`.</span><span class="sxs-lookup"><span data-stu-id="25c01-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="25c01-120">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="25c01-120">Example 1</span></span>

<span data-ttu-id="25c01-121">L’expression `CONTAINS ("abc", "d")` renvoie **FALSE**, alors que l’expression `CONTAINS ("abc", "C")` renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="25c01-121">The expression `CONTAINS ("abc", "d")` returns **FALSE**, whereas the expression `CONTAINS ("abc", "C")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="25c01-122">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="25c01-122">Example 2</span></span>

<span data-ttu-id="25c01-123">L’expression `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` renvoie **TRUE** si la valeur du champ **Adresse** de la source de données **modèle** contient la chaîne **DEU**.</span><span class="sxs-lookup"><span data-stu-id="25c01-123">The expression `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` returns **TRUE** if the value of the **Address** field of the **model** data source contains the string **DEU**.</span></span> <span data-ttu-id="25c01-124">Sinon, elle renvoie la valeur **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="25c01-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25c01-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="25c01-125">Additional resources</span></span>

[<span data-ttu-id="25c01-126">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="25c01-126">Logical functions</span></span>](er-functions-category-logical.md)
