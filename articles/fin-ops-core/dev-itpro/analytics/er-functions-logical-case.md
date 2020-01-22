---
title: Fonction CASE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction CASE États électroniques (ER).
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
ms.openlocfilehash: 38b51a4d8bf8dc997bae2ae9206d8e71ca48dec6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916060"
---
# <span data-ttu-id="31160-103"><a name="CASE">Fonction CASE ER</a></span><span class="sxs-lookup"><span data-stu-id="31160-103"><a name="CASE">CASE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31160-104">La fonction `CASE` évalue la valeur de l'expression spécifiée par rapport aux options alternatives spécifiées et renvoie le résultat de la première option qui est égale à la valeur de l'expression spécifiée.</span><span class="sxs-lookup"><span data-stu-id="31160-104">The `CASE` function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="31160-105">Sinon, elle renvoie le résultat par défaut facultatif, si un résultat par défaut est spécifié comme dernier argument de la fonction appelée qui n'est pas précédé d'une option.</span><span class="sxs-lookup"><span data-stu-id="31160-105">Otherwise, it returns the optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="31160-106">La valeur renvoyée peut être une valeur de n'importe quel type de données pris en charge.</span><span class="sxs-lookup"><span data-stu-id="31160-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="31160-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="31160-107">Syntax</span></span>

```
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a><span data-ttu-id="31160-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="31160-108">Arguments</span></span>

<span data-ttu-id="31160-109">`expression` : *Type de données primitif* (Booléen, numérique ou texte)</span><span class="sxs-lookup"><span data-stu-id="31160-109">`expression`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="31160-110">Expression valide qui renvoie une valeur du type de données primitif.</span><span class="sxs-lookup"><span data-stu-id="31160-110">A valid expression that returns a value of the primitive data type.</span></span>

<span data-ttu-id="31160-111">`option 1` : *Type de données primitif* (Booléen, numérique ou texte)</span><span class="sxs-lookup"><span data-stu-id="31160-111">`option 1`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="31160-112">Expression valide qui renvoie une valeur du même type de données primitif que l'argument `expression` de la fonction appelée.</span><span class="sxs-lookup"><span data-stu-id="31160-112">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="31160-113">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="31160-113">This argument is required.</span></span>

<span data-ttu-id="31160-114">`result 1` : *N'importe lequel des types de données pris en charge*</span><span class="sxs-lookup"><span data-stu-id="31160-114">`result 1`: *Any of the supported data types*</span></span>

<span data-ttu-id="31160-115">Résultat renvoyé qui correspond à l'option précédente.</span><span class="sxs-lookup"><span data-stu-id="31160-115">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="31160-116">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="31160-116">This argument is required.</span></span>

<span data-ttu-id="31160-117">`option N` : *Type de données primitif* (Booléen, numérique ou texte)</span><span class="sxs-lookup"><span data-stu-id="31160-117">`option N`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="31160-118">Expression valide qui renvoie une valeur du même type de données primitif que l'argument `expression` de la fonction appelée.</span><span class="sxs-lookup"><span data-stu-id="31160-118">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="31160-119">Cet argument est facultatif.</span><span class="sxs-lookup"><span data-stu-id="31160-119">This argument is optional.</span></span>

<span data-ttu-id="31160-120">`result N` : *N'importe lequel des types de données pris en charge*</span><span class="sxs-lookup"><span data-stu-id="31160-120">`result N`: *Any of the supported data types*</span></span>

<span data-ttu-id="31160-121">Résultat renvoyé qui correspond à l'option précédente.</span><span class="sxs-lookup"><span data-stu-id="31160-121">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="31160-122">Cet argument est facultatif.</span><span class="sxs-lookup"><span data-stu-id="31160-122">This argument is optional.</span></span>

<span data-ttu-id="31160-123">`default result` : *N'importe lequel des types de données pris en charge*</span><span class="sxs-lookup"><span data-stu-id="31160-123">`default result`: *Any of the supported data types*</span></span>

<span data-ttu-id="31160-124">Résultat qui doit être renvoyé s'il n'y a pas de correspondance.</span><span class="sxs-lookup"><span data-stu-id="31160-124">The result that should be returned if there is no match.</span></span> <span data-ttu-id="31160-125">Cet argument est facultatif.</span><span class="sxs-lookup"><span data-stu-id="31160-125">This argument is optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="31160-126">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="31160-126">Return values</span></span>

<span data-ttu-id="31160-127">*N'importe lequel des types de données pris en charge*</span><span class="sxs-lookup"><span data-stu-id="31160-127">*Any of the supported data types*</span></span>

<span data-ttu-id="31160-128">Valeur résultante de l'un des types de données pris en charge.</span><span class="sxs-lookup"><span data-stu-id="31160-128">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="31160-129">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="31160-129">Usage notes</span></span>

<span data-ttu-id="31160-130">Une exception est levée au moment de l'exécution s'il n'y a pas de correspondance et qu'un résultat par défaut facultatif n'est pas défini.</span><span class="sxs-lookup"><span data-stu-id="31160-130">An exception is thrown at runtime if there is no match and an optional default result isn't defined.</span></span>

<span data-ttu-id="31160-131">Tous les résultats doivent être spécifiés en utilisant le même type de données.</span><span class="sxs-lookup"><span data-stu-id="31160-131">All results must be specified by using the same data type.</span></span> <span data-ttu-id="31160-132">Une exception est levée au moment de la conception si les types de données des résultats configurés ne correspondent pas.</span><span class="sxs-lookup"><span data-stu-id="31160-132">An exception is thrown at design time if the data types of the configured results don't match.</span></span>

<span data-ttu-id="31160-133">Si la première valeur de résultat et la *N*ième valeur de résultat sont des valeurs de type de données *Conteneur (enregistrement)* ou *Liste des enregistrements*, le résultat n'a que les champs qui existent dans les deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="31160-133">If the first result value and the *N*th result value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="31160-134">Exemple</span><span class="sxs-lookup"><span data-stu-id="31160-134">Example</span></span>

<span data-ttu-id="31160-135">`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` renvoie la chaîne **"HIVER"** si la date de la session de l'application actuelle se situe entre octobre et décembre.</span><span class="sxs-lookup"><span data-stu-id="31160-135">`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` returns the string **"WINTER"** if the current application session date is between October and December.</span></span> <span data-ttu-id="31160-136">Sinon, elle renvoie une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="31160-136">Otherwise, it returns a blank string.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="31160-137">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="31160-137">Additional resources</span></span>

[<span data-ttu-id="31160-138">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="31160-138">Logical functions</span></span>](er-functions-category-logical.md)
