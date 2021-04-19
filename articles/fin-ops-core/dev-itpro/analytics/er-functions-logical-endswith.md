---
title: Fonction ER ENDSWITH
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ENDSWITH États électroniques (ER).
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
ms.openlocfilehash: 2470bd8c75cf690d701957c4c79009659d61f7a5
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557517"
---
# <a name="endswith-er-function"></a><span data-ttu-id="f02fd-103">Fonction ER ENDSWITH</span><span class="sxs-lookup"><span data-stu-id="f02fd-103">ENDSWITH ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f02fd-104">La fonction `ENDSWITH` détermine si l’entrée spécifiée se termine par le texte spécifié.</span><span class="sxs-lookup"><span data-stu-id="f02fd-104">The `ENDSWITH` function determines whether the specified input ends with the specified text.</span></span> <span data-ttu-id="f02fd-105">Elle renvoie une valeur *Booléenne* **TRUE** si l’entrée spécifiée se termine par le texte spécifié.</span><span class="sxs-lookup"><span data-stu-id="f02fd-105">It returns a *Boolean* value of **TRUE** if the specified input ends with the specified text.</span></span> <span data-ttu-id="f02fd-106">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="f02fd-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="f02fd-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f02fd-107">Syntax</span></span>

```vb
ENDSWITH (input, end text)
```

## <a name="arguments"></a><span data-ttu-id="f02fd-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="f02fd-108">Arguments</span></span>

<span data-ttu-id="f02fd-109">`input` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="f02fd-109">`input`: *String*</span></span>

<span data-ttu-id="f02fd-110">Le chemin valide d’un élément d’une source de données du type *Chaîne* ou d’une constante de chaîne, dont la valeur peut se terminer par le deuxième argument.</span><span class="sxs-lookup"><span data-stu-id="f02fd-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might end with the second argument.</span></span>

<span data-ttu-id="f02fd-111">`start text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="f02fd-111">`start text`: *String*</span></span>

<span data-ttu-id="f02fd-112">Le chemin valide d’une source de données du type de données *Chaîne* ou d’une constante de chaîne, dont la valeur peut être à la fin du premier argument.</span><span class="sxs-lookup"><span data-stu-id="f02fd-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be at the end of the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="f02fd-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="f02fd-113">Return values</span></span>

<span data-ttu-id="f02fd-114">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="f02fd-114">*Boolean*</span></span>

<span data-ttu-id="f02fd-115">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="f02fd-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f02fd-116">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="f02fd-116">Usage notes</span></span>

<span data-ttu-id="f02fd-117">Cette fonction peut être utilisée pour spécifier une expression de condition de la fonction [FILTER](er-functions-list-filter.md) uniquement lorsque le mappage approprié est configuré dans [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) accéder [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="f02fd-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="f02fd-118">Sinon, une exception est levée au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="f02fd-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="f02fd-119">Le message que vous recevez vous recommande d’utiliser la fonction [WHERE](er-functions-list-where.md) au lieu de la fonction `FILTER`.</span><span class="sxs-lookup"><span data-stu-id="f02fd-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="f02fd-120">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="f02fd-120">Example 1</span></span>

<span data-ttu-id="f02fd-121">L’expression `ENDSWITH ("abc", "d")` renvoie **FALSE**, alors que l’expression `ENDSWITH ("abc", "C")` renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="f02fd-121">The expression `ENDSWITH ("abc", "d")` returns **FALSE**, whereas the expression `ENDSWITH ("abc", "C")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="f02fd-122">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="f02fd-122">Example 2</span></span>

<span data-ttu-id="f02fd-123">L’expression `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` renvoie **TRUE** si la valeur du champ **Adresse** de la source de données **modèle** se termine par la chaîne **USA**.</span><span class="sxs-lookup"><span data-stu-id="f02fd-123">The expression `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` returns **TRUE** if the value of the **Address** field of the **model** data source ends with the string **USA**.</span></span> <span data-ttu-id="f02fd-124">Sinon, elle renvoie la valeur **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="f02fd-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f02fd-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f02fd-125">Additional resources</span></span>

[<span data-ttu-id="f02fd-126">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="f02fd-126">Logical functions</span></span>](er-functions-category-logical.md)