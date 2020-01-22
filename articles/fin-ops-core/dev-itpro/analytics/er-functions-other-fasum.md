---
title: Fonction FA_SUM ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction FA_SUM États électroniques (ER).
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
ms.openlocfilehash: 32eb07689598a3b6c852f272b480106670b88cd0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916980"
---
# <span data-ttu-id="8f97d-103"><a name="FA_SUM">Fonction FA_SUM ER</a></span><span class="sxs-lookup"><span data-stu-id="8f97d-103"><a name="FA_SUM">FA_SUM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f97d-104">La fonction `FA_SUM` renvoie une valeur de *Conteneur (enregistrement)* constituée des données des montants des immobilisations pour l'élément d'immobilisation spécifié, le code du modèle de valeur et la période des dates.</span><span class="sxs-lookup"><span data-stu-id="8f97d-104">The `FA_SUM` function returns a *Container (record)* value that consists of data for the fixed asset amounts for the specified fixed asset item, value model code, and period of dates.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f97d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8f97d-105">Syntax</span></span>

```
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a><span data-ttu-id="8f97d-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="8f97d-106">Arguments</span></span>

<span data-ttu-id="8f97d-107">`fixed asset code` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="8f97d-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="8f97d-108">Valeur de *Chaîne* qui représente le code d'un élément d'immobilisation pour lequel le solde est calculé.</span><span class="sxs-lookup"><span data-stu-id="8f97d-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="8f97d-109">`value model code` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="8f97d-109">`value model code`: *String*</span></span>

<span data-ttu-id="8f97d-110">Valeur de *Chaîne* qui représente le code d'un modèle de valeur pour lequel le solde est calculé.</span><span class="sxs-lookup"><span data-stu-id="8f97d-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="8f97d-111">`start date` : *Date*</span><span class="sxs-lookup"><span data-stu-id="8f97d-111">`start date`: *Date*</span></span>

<span data-ttu-id="8f97d-112">Valeur de *Date* qui représente la date de début d'une période pour laquelle les montants des immobilisations sont calculés.</span><span class="sxs-lookup"><span data-stu-id="8f97d-112">A *Date* value that represents the start date of a period that the fixed asset amounts are calculated for.</span></span>

<span data-ttu-id="8f97d-113">`end date` : *Date*</span><span class="sxs-lookup"><span data-stu-id="8f97d-113">`end date`: *Date*</span></span>

<span data-ttu-id="8f97d-114">Valeur de *Date* qui représente la date de fin d'une période pour laquelle les montants des immobilisations sont calculés.</span><span class="sxs-lookup"><span data-stu-id="8f97d-114">A *Date* value that represents the end date of a period that the fixed asset amounts are calculated for.</span></span>

## <a name="return-values"></a><span data-ttu-id="8f97d-115">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="8f97d-115">Return values</span></span>

<span data-ttu-id="8f97d-116">*Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="8f97d-116">*Container (record)*</span></span>

<span data-ttu-id="8f97d-117">Valeur de l'enregistrement résultante.</span><span class="sxs-lookup"><span data-stu-id="8f97d-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="8f97d-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="8f97d-118">Example</span></span>

<span data-ttu-id="8f97d-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` renvoie le conteneur de données pour l'immobilisation **COMP-000001** qui a été préparée pour le modèle de valeur **Current** et pour une période de **Date1** à **Date2**.</span><span class="sxs-lookup"><span data-stu-id="8f97d-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returns the data container for fixed asset **COMP-000001** that has been prepared for the **Current** value model and for a period from **Date1** to **Date2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8f97d-120">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8f97d-120">Additional resources</span></span>

[<span data-ttu-id="8f97d-121">Autre fonctions (spécifiques au domaine d'affaires)</span><span class="sxs-lookup"><span data-stu-id="8f97d-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
