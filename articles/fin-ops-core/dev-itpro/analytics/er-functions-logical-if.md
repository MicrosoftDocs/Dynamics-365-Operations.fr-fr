---
title: Fonction IF ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction IF États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 198210f15e75de761dbb03e5087ba7c77a95721a
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041743"
---
# <span data-ttu-id="e4035-103"><a name="IF">Fonction IF ER</a></span><span class="sxs-lookup"><span data-stu-id="e4035-103"><a name="IF">IF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4035-104">La fonction `IF` renvoie la première valeur spécifiée si la condition spécifiée est remplie.</span><span class="sxs-lookup"><span data-stu-id="e4035-104">The `IF` function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="e4035-105">Sinon, elle renvoie la deuxième valeur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e4035-105">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="e4035-106">La valeur renvoyée peut être une valeur de n'importe quel type de données pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e4035-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="e4035-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e4035-107">Syntax</span></span>

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a><span data-ttu-id="e4035-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="e4035-108">Arguments</span></span>

<span data-ttu-id="e4035-109">`condition` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="e4035-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="e4035-110">Expression conditionnelle valide qui doit être testée.</span><span class="sxs-lookup"><span data-stu-id="e4035-110">A valid conditional expression that must be tested.</span></span>

<span data-ttu-id="e4035-111">`first value` : *N'importe lequel des types de données pris en charge*</span><span class="sxs-lookup"><span data-stu-id="e4035-111">`first value`: *Any of the supported data types*</span></span>

<span data-ttu-id="e4035-112">Résultat renvoyé si la condition est remplie.</span><span class="sxs-lookup"><span data-stu-id="e4035-112">The result that is returned if the condition is met.</span></span>

<span data-ttu-id="e4035-113">`second value` : *N'importe lequel des types de données pris en charge*</span><span class="sxs-lookup"><span data-stu-id="e4035-113">`second value`: *Any of the supported data types*</span></span>

<span data-ttu-id="e4035-114">Résultat renvoyé si la condition n'est pas remplie.</span><span class="sxs-lookup"><span data-stu-id="e4035-114">The result that is returned if the condition isn't met.</span></span>

## <a name="return-values"></a><span data-ttu-id="e4035-115">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="e4035-115">Return values</span></span>

<span data-ttu-id="e4035-116">*N'importe lequel des types de données pris en charge*</span><span class="sxs-lookup"><span data-stu-id="e4035-116">*Any of the supported data types*</span></span>

<span data-ttu-id="e4035-117">Valeur résultante de l'un des types de données pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e4035-117">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e4035-118">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="e4035-118">Usage notes</span></span>

<span data-ttu-id="e4035-119">Les arguments `first value` et `second value` doivent être spécifiés en utilisant le même type de données.</span><span class="sxs-lookup"><span data-stu-id="e4035-119">The `first value` and `second value` arguments must be specified by using the same data type.</span></span> <span data-ttu-id="e4035-120">Une exception est levée au moment de la conception si les types de données des valeurs configurées ne correspondent pas.</span><span class="sxs-lookup"><span data-stu-id="e4035-120">An exception is thrown at design time if the data types of the configured values don't match.</span></span>

<span data-ttu-id="e4035-121">Si la première valeur et la seconde valeur sont des valeurs de type de données *Conteneur (enregistrement)* ou *Liste des enregistrements*, le résultat n'a que les champs qui existent dans les deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="e4035-121">If the first value and the second value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="e4035-122">Exemple</span><span class="sxs-lookup"><span data-stu-id="e4035-122">Example</span></span>

<span data-ttu-id="e4035-123">`IF (1=2, "condition is met", "condition is not met")` renvoie la chaîne **la condition n'est pas remplie**.</span><span class="sxs-lookup"><span data-stu-id="e4035-123">`IF (1=2, "condition is met", "condition is not met")` returns the string **"condition is not met"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e4035-124">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e4035-124">Additional resources</span></span>

[<span data-ttu-id="e4035-125">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="e4035-125">Logical functions</span></span>](er-functions-category-logical.md)
