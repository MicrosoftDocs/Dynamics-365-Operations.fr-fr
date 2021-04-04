---
title: Fonction TEXT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction TEXT États électroniques (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 5da7375020be827f432ba97740da37abe48962fc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560059"
---
# <a name="text-er-function"></a><span data-ttu-id="9387f-103">Fonction TEXT ER</span><span class="sxs-lookup"><span data-stu-id="9387f-103">TEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9387f-104">La fonction `TEXT` renvoie le nombre spécifié comme valeur de *Chaîne* une fois qu’elle a été convertie en une chaîne de texte qui est mise en forme en fonction des paramètres régionaux du serveur de l’instance d’application actuelle.</span><span class="sxs-lookup"><span data-stu-id="9387f-104">The `TEXT` function returns the specified number as a *String* value after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span>

## <a name="syntax"></a><span data-ttu-id="9387f-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9387f-105">Syntax</span></span>

```vb
TEXT (number)
```

## <a name="arguments"></a><span data-ttu-id="9387f-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="9387f-106">Arguments</span></span>

<span data-ttu-id="9387f-107">`number` : *Entier* ou *Réel*</span><span class="sxs-lookup"><span data-stu-id="9387f-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="9387f-108">Nombre qui doit être converti en chaîne de texte.</span><span class="sxs-lookup"><span data-stu-id="9387f-108">A number that must be converted to a text string.</span></span>

## <a name="return-values"></a><span data-ttu-id="9387f-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="9387f-109">Return values</span></span>

<span data-ttu-id="9387f-110">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="9387f-110">*String*</span></span>

<span data-ttu-id="9387f-111">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="9387f-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9387f-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="9387f-112">Usage notes</span></span>

<span data-ttu-id="9387f-113">Pour les valeurs de type *Réel*, la conversion de chaîne est limitée à deux décimales.</span><span class="sxs-lookup"><span data-stu-id="9387f-113">For values of the *Real* type, the string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="9387f-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="9387f-114">Example</span></span>

<span data-ttu-id="9387f-115">Si les paramètres régionaux du serveur de l’instance Microsoft Dynamics 365 Finance sont définis comme **EN-US**, `TEXT (NOW ())` renvoie la date de la session de Finance actuelle, 17 décembre 2015, comme chaîne de texte **"12/17/2015 07:59:23 AM"**.</span><span class="sxs-lookup"><span data-stu-id="9387f-115">If the server locale of the Microsoft Dynamics 365 Finance instance is defined as **EN-US**, `TEXT (NOW ())` returns the current Finance session date, December 17, 2015, as the text string **"12/17/2015 07:59:23 AM"**.</span></span> <span data-ttu-id="9387f-116">`TEXT (1/3)` renvoie **« 0.33 »**.</span><span class="sxs-lookup"><span data-stu-id="9387f-116">`TEXT (1/3)` returns **"0.33"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9387f-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9387f-117">Additional resources</span></span>

[<span data-ttu-id="9387f-118">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="9387f-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]