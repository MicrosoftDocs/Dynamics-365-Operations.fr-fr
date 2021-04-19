---
title: Fonction NUMERALSTOTEXT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction NUMERALSTOTEXT États électroniques (ER).
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: e26890a0d99e0df631a3b3350d284e63aaed8e09
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746145"
---
# <a name="numeralstotext-er-function"></a><span data-ttu-id="42f3e-103">Fonction NUMERALSTOTEXT ER</span><span class="sxs-lookup"><span data-stu-id="42f3e-103">NUMERALSTOTEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42f3e-104">La fonction `NUMERALSTOTEXT` renvoie le nombre spécifié sous la forme *Chaîne* après avoir été épelée (c’est-à-dire convertie en chaînes de texte) dans la langue spécifiée.</span><span class="sxs-lookup"><span data-stu-id="42f3e-104">The `NUMERALSTOTEXT` function returns the specified number as a *String* value after it has been spelled out (that is, converted to text strings) in the specified language.</span></span>

## <a name="syntax"></a><span data-ttu-id="42f3e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="42f3e-105">Syntax</span></span>

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a><span data-ttu-id="42f3e-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="42f3e-106">Arguments</span></span>

<span data-ttu-id="42f3e-107">`number` : *Entier* ou *Réel*</span><span class="sxs-lookup"><span data-stu-id="42f3e-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="42f3e-108">Valeur numérique qui spécifie le numéro qui doit être épelé.</span><span class="sxs-lookup"><span data-stu-id="42f3e-108">A numeric value that specifies the number that must be spelled out.</span></span>

<span data-ttu-id="42f3e-109">`language` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="42f3e-109">`language`: *String*</span></span>

<span data-ttu-id="42f3e-110">Valeur *Chaîne* qui représente le code langue.</span><span class="sxs-lookup"><span data-stu-id="42f3e-110">A *String* value that represents the language code.</span></span>

<span data-ttu-id="42f3e-111">`currency` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="42f3e-111">`currency`: *String*</span></span>

<span data-ttu-id="42f3e-112">Valeur *Chaîne* qui représente le code devise.</span><span class="sxs-lookup"><span data-stu-id="42f3e-112">A *String* value that represents the currency code.</span></span>

<span data-ttu-id="42f3e-113">`print currency name flag` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="42f3e-113">`print currency name flag`: *Boolean*</span></span>

<span data-ttu-id="42f3e-114">Valeur *Booléenne* qui indique si un nom de devise doit être ajouté au texte épelé.</span><span class="sxs-lookup"><span data-stu-id="42f3e-114">A *Boolean* value that indicates whether a currency name must be added to the spelled-out text.</span></span>

<span data-ttu-id="42f3e-115">`decimal points` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="42f3e-115">`decimal points`: *Integer*</span></span>

<span data-ttu-id="42f3e-116">Valeur *Entier* qui indique le nombre de décimales que doit contenir le texte épelé.</span><span class="sxs-lookup"><span data-stu-id="42f3e-116">An *Integer* value that indicates the number of decimal places that the spelled-out text should have.</span></span>

## <a name="return-values"></a><span data-ttu-id="42f3e-117">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="42f3e-117">Return values</span></span>

<span data-ttu-id="42f3e-118">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="42f3e-118">*String*</span></span>

<span data-ttu-id="42f3e-119">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="42f3e-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="42f3e-120">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="42f3e-120">Usage notes</span></span>

<span data-ttu-id="42f3e-121">Le code langue est facultatif.</span><span class="sxs-lookup"><span data-stu-id="42f3e-121">The language code is optional.</span></span> <span data-ttu-id="42f3e-122">S’il est défini comme une chaîne vide, le code langue du contexte d’exécution est utilisé.</span><span class="sxs-lookup"><span data-stu-id="42f3e-122">If it's defined as an empty string, the language code for the running context is used.</span></span> <span data-ttu-id="42f3e-123">Le code langue par défaut est **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="42f3e-123">The default language code is **EN-US**.</span></span> <span data-ttu-id="42f3e-124">Le code langue pour le contexte en cours d’exécution est défini dans un élément **Dossier** ou **Fichier** du format d’états électroniques (ER) en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="42f3e-124">The language code for the running context is defined in a **Folder** or **File** element of the Electronic reporting (ER) format that is running.</span></span>

<span data-ttu-id="42f3e-125">Le code devise est facultatif.</span><span class="sxs-lookup"><span data-stu-id="42f3e-125">The currency code is optional.</span></span> <span data-ttu-id="42f3e-126">S’il est défini comme une chaîne vide, la devis d’entreprise du contexte d’exécution est utilisé.</span><span class="sxs-lookup"><span data-stu-id="42f3e-126">If it's defined as an empty string, the company currency for the running context is used.</span></span>

> [!NOTE] 
> <span data-ttu-id="42f3e-127">Les arguments `print currency name flag` et `decimal points` sont analysés pour les codes de langue suivants uniquement : **CS**, **ET**, **HU**, **LT**, **LV**, **PL** et **RU**.</span><span class="sxs-lookup"><span data-stu-id="42f3e-127">The `print currency name flag` and `decimal points` arguments are analyzed only for the following language codes: **CS**, **ET**, **HU**, **LT**, **LV**, **PL**, and **RU**.</span></span> <span data-ttu-id="42f3e-128">En outre, l’arguments `print currency name flag` est analysé uniquement pour les sociétés où le contexte du pays ou de la région prend en charge la déclinaison des noms de devise.</span><span class="sxs-lookup"><span data-stu-id="42f3e-128">Additionally, the `print currency name flag` argument is analyzed only for companies where the country's or region's context supports declension of currency names.</span></span>

## <a name="example-1"></a><span data-ttu-id="42f3e-129">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="42f3e-129">Example 1</span></span>

<span data-ttu-id="42f3e-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` renvoie **"Mille deux cent trente-quatre et 56"**.</span><span class="sxs-lookup"><span data-stu-id="42f3e-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` returns **"One Thousand Two Hundred Thirty Four and 56"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="42f3e-131">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="42f3e-131">Example 2</span></span>

<span data-ttu-id="42f3e-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` renvoie **"Sto dwadzieścia"**.</span><span class="sxs-lookup"><span data-stu-id="42f3e-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` returns **"Sto dwadzieścia"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="42f3e-133">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="42f3e-133">Example 3</span></span>

<span data-ttu-id="42f3e-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` renvoie **"Сто двадцать евро 21 евроцент"**.</span><span class="sxs-lookup"><span data-stu-id="42f3e-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` returns **"Сто двадцать евро 21 евроцент"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="42f3e-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="42f3e-135">Additional resources</span></span>

[<span data-ttu-id="42f3e-136">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="42f3e-136">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]