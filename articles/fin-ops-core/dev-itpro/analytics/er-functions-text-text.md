---
title: Fonction TEXT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction TEXT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: c08aca949ffc7e62009bf3f6c664d96b368f43e7
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040892"
---
# <span data-ttu-id="b904b-103"><a name="TEXT">Fonction TEXT ER</a></span><span class="sxs-lookup"><span data-stu-id="b904b-103"><a name="TEXT">TEXT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b904b-104">La fonction `TEXT` renvoie le nombre spécifié comme valeur de *Chaîne* une fois qu'elle a été convertie en une chaîne de texte qui est mise en forme en fonction des paramètres régionaux du serveur de l'instance d'application actuelle.</span><span class="sxs-lookup"><span data-stu-id="b904b-104">The `TEXT` function returns the specified number as a *String* value after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span>

## <a name="syntax"></a><span data-ttu-id="b904b-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b904b-105">Syntax</span></span>

```vb
TEXT (number)
```

## <a name="arguments"></a><span data-ttu-id="b904b-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="b904b-106">Arguments</span></span>

<span data-ttu-id="b904b-107">`number` : *Entier* ou *Réel*</span><span class="sxs-lookup"><span data-stu-id="b904b-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="b904b-108">Nombre qui doit être converti en chaîne de texte.</span><span class="sxs-lookup"><span data-stu-id="b904b-108">A number that must be converted to a text string.</span></span>

## <a name="return-values"></a><span data-ttu-id="b904b-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="b904b-109">Return values</span></span>

<span data-ttu-id="b904b-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b904b-110">*String*</span></span>

<span data-ttu-id="b904b-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="b904b-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b904b-112">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="b904b-112">Usage notes</span></span>

<span data-ttu-id="b904b-113">Pour les valeurs de type *Réel*, la conversion de chaîne est limitée à deux décimales.</span><span class="sxs-lookup"><span data-stu-id="b904b-113">For values of the *Real* type, the string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="b904b-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="b904b-114">Example</span></span>

<span data-ttu-id="b904b-115">Si les paramètres régionaux du serveur de l'instance Microsoft Dynamics 365 Finance sont définis comme **EN-US**, `TEXT (NOW ())` renvoie la date de la session de Finance actuelle, 17 décembre 2015, comme chaîne de texte **"12/17/2015 07:59:23 AM"**.</span><span class="sxs-lookup"><span data-stu-id="b904b-115">If the server locale of the Microsoft Dynamics 365 Finance instance is defined as **EN-US**, `TEXT (NOW ())` returns the current Finance session date, December 17, 2015, as the text string **"12/17/2015 07:59:23 AM"**.</span></span> <span data-ttu-id="b904b-116">`TEXT (1/3)` renvoie **« 0.33 »**.</span><span class="sxs-lookup"><span data-stu-id="b904b-116">`TEXT (1/3)` returns **"0.33"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b904b-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b904b-117">Additional resources</span></span>

[<span data-ttu-id="b904b-118">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="b904b-118">Text functions</span></span>](er-functions-category-text.md)
