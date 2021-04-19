---
title: Fonction CONVERTCURRENCY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CONVERTCURRENCY États électroniques (ER).
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
ms.openlocfilehash: fb8f7f28f5a9bb27402544efcffa6393238e38d8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744365"
---
# <a name="convertcurrency-er-function"></a><span data-ttu-id="fb039-103">Fonction CONVERTCURRENCY ER</span><span class="sxs-lookup"><span data-stu-id="fb039-103">CONVERTCURRENCY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb039-104">La fonction `CONVERTCURRENCY` renvoie une valeur de *Réel* qui représente le résultat de la conversion du montant en devises spécifié de la devise source spécifiée dans la devise cible spécifiée à l’aide des paramètres de la société spécifiée à la date spécifiée.</span><span class="sxs-lookup"><span data-stu-id="fb039-104">The `CONVERTCURRENCY` function returns a *Real* value that represents the result of converting the specified monetary amount from the specified source currency to the specified target currency by using the settings of the specified company on the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb039-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fb039-105">Syntax</span></span>

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a><span data-ttu-id="fb039-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="fb039-106">Arguments</span></span>

<span data-ttu-id="fb039-107">`amount` : *Entier* ou *Réel*</span><span class="sxs-lookup"><span data-stu-id="fb039-107">`amount`: *Integer* or *Real*</span></span>

<span data-ttu-id="fb039-108">Valeur numérique qui représente le montant en devises qui doit être converti.</span><span class="sxs-lookup"><span data-stu-id="fb039-108">A numeric value that represents the monetary amount that must be converted.</span></span>

<span data-ttu-id="fb039-109">`source currency` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="fb039-109">`source currency`: *String*</span></span>

<span data-ttu-id="fb039-110">Code de la devise source.</span><span class="sxs-lookup"><span data-stu-id="fb039-110">The code of the source currency.</span></span>

<span data-ttu-id="fb039-111">`target currency` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="fb039-111">`target currency`: *String*</span></span>

<span data-ttu-id="fb039-112">Code de la devise cible.</span><span class="sxs-lookup"><span data-stu-id="fb039-112">The code of the target currency.</span></span>

<span data-ttu-id="fb039-113">`date` : *Date*</span><span class="sxs-lookup"><span data-stu-id="fb039-113">`date`: *Date*</span></span>

<span data-ttu-id="fb039-114">Valeur de *Date* qui représente la date utilisée pour déterminer le taux de change pour la conversion.</span><span class="sxs-lookup"><span data-stu-id="fb039-114">A *Date* value that represents the date that is used to determine the exchange rate for the conversion.</span></span>

<span data-ttu-id="fb039-115">`company` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="fb039-115">`company`: *String*</span></span>

<span data-ttu-id="fb039-116">Valeur de *Chaîne* qui représente le code d’une entreprise qui fournit les paramètres utilisés pour la conversion.</span><span class="sxs-lookup"><span data-stu-id="fb039-116">A *String* value that represents the code of a company that supplies the settings that are used for the conversion.</span></span>

## <a name="return-values"></a><span data-ttu-id="fb039-117">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="fb039-117">Return values</span></span>

<span data-ttu-id="fb039-118">*Réel*</span><span class="sxs-lookup"><span data-stu-id="fb039-118">*Real*</span></span>

<span data-ttu-id="fb039-119">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="fb039-119">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="fb039-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="fb039-120">Example</span></span>

<span data-ttu-id="fb039-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` renvoie l’équivalent d’un euro en dollars US à la date de session actuelle, basée sur les paramètre de la société **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="fb039-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` returns the equivalent of one euro in US dollars on the current session date, based on settings for the **DEMF** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fb039-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fb039-122">Additional resources</span></span>

[<span data-ttu-id="fb039-123">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="fb039-123">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]