---
title: Fonction FA_BALANCE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction FA_BALANCE États électroniques (ER).
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
ms.openlocfilehash: 6a969e3a484208388fd82d7a714bee27b7fe64a9
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744165"
---
# <a name="fa_balance-er-function"></a><span data-ttu-id="2e9df-103">Fonction FA_BALANCE ER</span><span class="sxs-lookup"><span data-stu-id="2e9df-103">FA_BALANCE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2e9df-104">La fonction `FA_BALANCE` renvoie une valeur de *Conteneur (enregistrement)* constituée des données relatives au solde des immobilisations pour l’élément d’immobilisation spécifié, le code du modèle de valeur, l’année de déclaration et la date de déclaration.</span><span class="sxs-lookup"><span data-stu-id="2e9df-104">The `FA_BALANCE` function returns a *Container (record)* value that consists of data for the fixed asset balance for the specified fixed asset item, value model code, reporting year, and reporting date.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e9df-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2e9df-105">Syntax</span></span>

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a><span data-ttu-id="2e9df-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="2e9df-106">Arguments</span></span>

<span data-ttu-id="2e9df-107">`fixed asset code` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="2e9df-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="2e9df-108">Valeur de *Chaîne* qui représente le code d’un élément d’immobilisation pour lequel le solde est calculé.</span><span class="sxs-lookup"><span data-stu-id="2e9df-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="2e9df-109">`value model code` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="2e9df-109">`value model code`: *String*</span></span>

<span data-ttu-id="2e9df-110">Valeur de *Chaîne* qui représente le code d’un modèle de valeur pour lequel le solde est calculé.</span><span class="sxs-lookup"><span data-stu-id="2e9df-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="2e9df-111">`reporting year` : *Valeur d’énumération*</span><span class="sxs-lookup"><span data-stu-id="2e9df-111">`reporting year`: *Enumeration value*</span></span>

<span data-ttu-id="2e9df-112">Valeur d’énumération de l’énumération d’application **AssetYear** qui définit une période pour le calcul du solde.</span><span class="sxs-lookup"><span data-stu-id="2e9df-112">An enumeration value of the **AssetYear** application enumeration that defines a period for the balance calculation.</span></span>

<span data-ttu-id="2e9df-113">`reporting date` : *Date*</span><span class="sxs-lookup"><span data-stu-id="2e9df-113">`reporting date`: *Date*</span></span>

<span data-ttu-id="2e9df-114">Valeur de *Date* qui définit une date pour le calcul du solde.</span><span class="sxs-lookup"><span data-stu-id="2e9df-114">A *Date* value that defines a date for the balance calculation.</span></span>

## <a name="return-values"></a><span data-ttu-id="2e9df-115">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="2e9df-115">Return values</span></span>

<span data-ttu-id="2e9df-116">*Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="2e9df-116">*Container (record)*</span></span>

<span data-ttu-id="2e9df-117">Valeur de l’enregistrement résultante.</span><span class="sxs-lookup"><span data-stu-id="2e9df-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="2e9df-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="2e9df-118">Example</span></span>

<span data-ttu-id="2e9df-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` renvoie le conteneur de données des soldes de l’immobilisation **COMP-000001** préparé pour le modèle de valeur **Current** à la date de la session de l’application actuelle.</span><span class="sxs-lookup"><span data-stu-id="2e9df-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` returns the data container of balances for fixed asset **COMP-000001** that has been prepared for the **Current** value model on the current application session date.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2e9df-120">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2e9df-120">Additional resources</span></span>

[<span data-ttu-id="2e9df-121">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="2e9df-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
