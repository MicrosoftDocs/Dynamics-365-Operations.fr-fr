---
title: Fonction NULLDATE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction NULLDATE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 7761342c6759c11591e06fc7c32f0ddd8bef407a
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916313"
---
# <span data-ttu-id="0fc75-103"><a name="NULLDATE">Fonction NULLDATE ER</a></span><span class="sxs-lookup"><span data-stu-id="0fc75-103"><a name="NULLDATE">NULLDATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0fc75-104">La fonction `NULLDATE` renvoie une valeur *Date* qui représente la date **null** (1er janvier 1900).</span><span class="sxs-lookup"><span data-stu-id="0fc75-104">The `NULLDATE` function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span>

## <a name="syntax"></a><span data-ttu-id="0fc75-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0fc75-105">Syntax</span></span>

```
NULLDATE () as 
```

## <a name="return-values"></a><span data-ttu-id="0fc75-106">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="0fc75-106">Return values</span></span>

<span data-ttu-id="0fc75-107">*date ;*</span><span class="sxs-lookup"><span data-stu-id="0fc75-107">*Date*</span></span>

<span data-ttu-id="0fc75-108">Valeur de date résultante.</span><span class="sxs-lookup"><span data-stu-id="0fc75-108">The resulting date value.</span></span>

## <a name="example-1"></a><span data-ttu-id="0fc75-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="0fc75-109">Example 1</span></span>

<span data-ttu-id="0fc75-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` renvoie la date **null**, 1er janvier 1900, comme **« 1900-01-01 »**, basé sur le format personnalisé spécifié.</span><span class="sxs-lookup"><span data-stu-id="0fc75-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returns the **null** date, January 1, 1900, as **"1900-01-01"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="0fc75-111">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="0fc75-111">Example 2</span></span>

<span data-ttu-id="0fc75-112">L'expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` renvoie **True** lorsque la valeur du champ **Date du document** est égale à la date **null**.</span><span class="sxs-lookup"><span data-stu-id="0fc75-112">The expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returns **True** when the value of the **DocumentDate** field equals the **null** date.</span></span> <span data-ttu-id="0fc75-113">Dans cet exemple, **Facture** est une source de données d'états électroniques (ER) de type **Enregistrements Finance/Table** qui fait référence à la table CustInvoiceJour.</span><span class="sxs-lookup"><span data-stu-id="0fc75-113">In this example, **Invoice** is an Electronic reporting (ER) data source of the **Finance/Table records** type, and it refers to the CustInvoiceJour table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0fc75-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0fc75-114">Additional resources</span></span>

[<span data-ttu-id="0fc75-115">Fonctions de date et d'heure</span><span class="sxs-lookup"><span data-stu-id="0fc75-115">Date and time functions</span></span>](er-functions-category-datetime.md)