---
title: Fonction NULLDATE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction NULLDATE États électroniques (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 6ac8da3f18c7793512685d52dd64a9bd55bfb8fc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746841"
---
# <a name="nulldate-er-function"></a><span data-ttu-id="792e8-103">Fonction NULLDATE ER</span><span class="sxs-lookup"><span data-stu-id="792e8-103">NULLDATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="792e8-104">La fonction `NULLDATE` renvoie une valeur *Date* qui représente la date **null** (1er janvier 1900).</span><span class="sxs-lookup"><span data-stu-id="792e8-104">The `NULLDATE` function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span>

## <a name="syntax"></a><span data-ttu-id="792e8-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="792e8-105">Syntax</span></span>

```vb
NULLDATE () as 
```

## <a name="return-values"></a><span data-ttu-id="792e8-106">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="792e8-106">Return values</span></span>

<span data-ttu-id="792e8-107">*date ;*</span><span class="sxs-lookup"><span data-stu-id="792e8-107">*Date*</span></span>

<span data-ttu-id="792e8-108">Valeur de date résultante.</span><span class="sxs-lookup"><span data-stu-id="792e8-108">The resulting date value.</span></span>

## <a name="example-1"></a><span data-ttu-id="792e8-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="792e8-109">Example 1</span></span>

<span data-ttu-id="792e8-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` renvoie la date **null**, 1er janvier 1900, comme **« 1900-01-01 »**, basé sur le format personnalisé spécifié.</span><span class="sxs-lookup"><span data-stu-id="792e8-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returns the **null** date, January 1, 1900, as **"1900-01-01"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="792e8-111">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="792e8-111">Example 2</span></span>

<span data-ttu-id="792e8-112">L’expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` renvoie **True** lorsque la valeur du champ **Date du document** est égale à la date **null**.</span><span class="sxs-lookup"><span data-stu-id="792e8-112">The expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returns **True** when the value of the **DocumentDate** field equals the **null** date.</span></span> <span data-ttu-id="792e8-113">Dans cet exemple, **Facture** est une source de données d’états électroniques (ER) de type **Enregistrements Finance/Table** qui fait référence à la table CustInvoiceJour.</span><span class="sxs-lookup"><span data-stu-id="792e8-113">In this example, **Invoice** is an Electronic reporting (ER) data source of the **Finance/Table records** type, and it refers to the CustInvoiceJour table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="792e8-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="792e8-114">Additional resources</span></span>

[<span data-ttu-id="792e8-115">Fonctions de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="792e8-115">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]