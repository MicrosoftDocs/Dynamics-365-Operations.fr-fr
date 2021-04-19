---
title: Fonction FA_SUM ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction FA_SUM États électroniques (ER).
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
ms.openlocfilehash: d6f380e384e591e7417cfa40c73f9be6575fb0f6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744293"
---
# <a name="fa_sum-er-function"></a><span data-ttu-id="97b0e-103">Fonction FA_SUM ER</span><span class="sxs-lookup"><span data-stu-id="97b0e-103">FA_SUM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="97b0e-104">La fonction `FA_SUM` renvoie une valeur de *Conteneur (enregistrement)* constituée des données des montants des immobilisations pour l’élément d’immobilisation spécifié, le code du modèle de valeur et la période des dates.</span><span class="sxs-lookup"><span data-stu-id="97b0e-104">The `FA_SUM` function returns a *Container (record)* value that consists of data for the fixed asset amounts for the specified fixed asset item, value model code, and period of dates.</span></span>

## <a name="syntax"></a><span data-ttu-id="97b0e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="97b0e-105">Syntax</span></span>

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a><span data-ttu-id="97b0e-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="97b0e-106">Arguments</span></span>

<span data-ttu-id="97b0e-107">`fixed asset code` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="97b0e-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="97b0e-108">Valeur de *Chaîne* qui représente le code d’un élément d’immobilisation pour lequel le solde est calculé.</span><span class="sxs-lookup"><span data-stu-id="97b0e-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="97b0e-109">`value model code` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="97b0e-109">`value model code`: *String*</span></span>

<span data-ttu-id="97b0e-110">Valeur de *Chaîne* qui représente le code d’un modèle de valeur pour lequel le solde est calculé.</span><span class="sxs-lookup"><span data-stu-id="97b0e-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="97b0e-111">`start date` : *Date*</span><span class="sxs-lookup"><span data-stu-id="97b0e-111">`start date`: *Date*</span></span>

<span data-ttu-id="97b0e-112">Valeur de *Date* qui représente la date de début d’une période pour laquelle les montants des immobilisations sont calculés.</span><span class="sxs-lookup"><span data-stu-id="97b0e-112">A *Date* value that represents the start date of a period that the fixed asset amounts are calculated for.</span></span>

<span data-ttu-id="97b0e-113">`end date` : *Date*</span><span class="sxs-lookup"><span data-stu-id="97b0e-113">`end date`: *Date*</span></span>

<span data-ttu-id="97b0e-114">Valeur de *Date* qui représente la date de fin d’une période pour laquelle les montants des immobilisations sont calculés.</span><span class="sxs-lookup"><span data-stu-id="97b0e-114">A *Date* value that represents the end date of a period that the fixed asset amounts are calculated for.</span></span>

## <a name="return-values"></a><span data-ttu-id="97b0e-115">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="97b0e-115">Return values</span></span>

<span data-ttu-id="97b0e-116">*Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="97b0e-116">*Container (record)*</span></span>

<span data-ttu-id="97b0e-117">Valeur de l’enregistrement résultante.</span><span class="sxs-lookup"><span data-stu-id="97b0e-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="97b0e-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="97b0e-118">Example</span></span>

<span data-ttu-id="97b0e-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` renvoie le conteneur de données pour l’immobilisation **COMP-000001** qui a été préparée pour le modèle de valeur **Current** et pour une période de **Date1** à **Date2**.</span><span class="sxs-lookup"><span data-stu-id="97b0e-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returns the data container for fixed asset **COMP-000001** that has been prepared for the **Current** value model and for a period from **Date1** to **Date2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="97b0e-120">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="97b0e-120">Additional resources</span></span>

[<span data-ttu-id="97b0e-121">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="97b0e-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]