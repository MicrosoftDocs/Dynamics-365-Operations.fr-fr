---
title: Fonction ER STARTSWITH
description: Cette rubrique fournit des informations sur l’utilisation de la fonction STARTSWITH États électroniques (ER).
author: NickSelin
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 50883bb604d2d1f2947545ce27fa02099e70b0e6
ms.sourcegitcommit: 17cee26b03f7b5afe8a089a0a9b2380e8d377d70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2021
ms.locfileid: "6048840"
---
# <a name="startswith-er-function"></a><span data-ttu-id="089e2-103">Fonction ER STARTSWITH</span><span class="sxs-lookup"><span data-stu-id="089e2-103">STARTSWITH ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="089e2-104">La fonction `STARTSWITH` détermine si l’entrée spécifiée commence par le texte spécifié.</span><span class="sxs-lookup"><span data-stu-id="089e2-104">The `STARTSWITH` function determines whether the specified input starts with the specified text.</span></span> <span data-ttu-id="089e2-105">Elle renvoie une valeur *Booléenne* **TRUE** si l’entrée spécifiée commence par le texte spécifié.</span><span class="sxs-lookup"><span data-stu-id="089e2-105">It returns a *Boolean* value of **TRUE** if the specified input starts with the specified text.</span></span> <span data-ttu-id="089e2-106">Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="089e2-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="089e2-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="089e2-107">Syntax</span></span>

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a><span data-ttu-id="089e2-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="089e2-108">Arguments</span></span>

<span data-ttu-id="089e2-109">`input` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="089e2-109">`input`: *String*</span></span>

<span data-ttu-id="089e2-110">Le chemin valide d’un élément d’une source de données du type *Chaîne* ou d’une constante de chaîne, dont la valeur peut commencer par le deuxième argument.</span><span class="sxs-lookup"><span data-stu-id="089e2-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might start with the second argument.</span></span>

<span data-ttu-id="089e2-111">`start text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="089e2-111">`start text`: *String*</span></span>

<span data-ttu-id="089e2-112">Le chemin valide d’une source de données du type de données *Chaîne* ou d’une constante de chaîne, dont la valeur peut être au début du premier argument.</span><span class="sxs-lookup"><span data-stu-id="089e2-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be at the beginning of the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="089e2-113">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="089e2-113">Return values</span></span>

<span data-ttu-id="089e2-114">*Booléen*</span><span class="sxs-lookup"><span data-stu-id="089e2-114">*Boolean*</span></span>

<span data-ttu-id="089e2-115">Valeur *Booléenne* résultante.</span><span class="sxs-lookup"><span data-stu-id="089e2-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="089e2-116">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="089e2-116">Usage notes</span></span>

<span data-ttu-id="089e2-117">Cette fonction peut être utilisée pour spécifier une expression de condition de la fonction [FILTER](er-functions-list-filter.md) uniquement lorsque le mappage approprié est configuré dans [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) accéder [Microsoft Dataverse](/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="089e2-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](/power-platform/admin/data-integrator).</span></span> <span data-ttu-id="089e2-118">Sinon, une exception est levée au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="089e2-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="089e2-119">Le message que vous recevez vous recommande d’utiliser la fonction [WHERE](er-functions-list-where.md) au lieu de la fonction `FILTER`.</span><span class="sxs-lookup"><span data-stu-id="089e2-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="089e2-120">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="089e2-120">Example 1</span></span>

<span data-ttu-id="089e2-121">L’expression `STARTSWITH ("abc", "d")` renvoie **FALSE**, alors que l’expression `STARTSWITH ("abc", "A")` renvoie **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="089e2-121">The expression `STARTSWITH ("abc", "d")` returns **FALSE**, whereas the expression `STARTSWITH ("abc", "A")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="089e2-122">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="089e2-122">Example 2</span></span>

<span data-ttu-id="089e2-123">L’expression `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` renvoie **TRUE** si la valeur du champ **Adresse** de la source de données **modèle** commence par la chaîne **123 Coffee Street**.</span><span class="sxs-lookup"><span data-stu-id="089e2-123">The expression `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` returns **TRUE** if the value of the **Address** field of the **model** data source starts with the string **123 Coffee Street**.</span></span> <span data-ttu-id="089e2-124">Sinon, elle renvoie la valeur **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="089e2-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="089e2-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="089e2-125">Additional resources</span></span>

[<span data-ttu-id="089e2-126">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="089e2-126">Logical functions</span></span>](er-functions-category-logical.md)
