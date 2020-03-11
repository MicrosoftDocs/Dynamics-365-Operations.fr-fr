---
title: Fonction NULLDATETIME ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction NULLDATETIME États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 3cd4c152d4e220a2f6315265ed5e44d148134279
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042253"
---
# <span data-ttu-id="0cba6-103"><a name="NULLDATETIME">Fonction NULLDATETIME ER</a></span><span class="sxs-lookup"><span data-stu-id="0cba6-103"><a name="NULLDATETIME">NULLDATETIME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0cba6-104">La fonction `NULLDATETIME` renvoie une valeur de *DateTime* qui représente la valeur de date/heure **null** (1er janvier 1900) en temps universel coordonné (heure moyenne de Greenwich \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="0cba6-104">The `NULLDATETIME` function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="0cba6-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0cba6-105">Syntax</span></span>

```vb
NULLDATETIME ()
```

## <a name="return-values"></a><span data-ttu-id="0cba6-106">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="0cba6-106">Return values</span></span>

<span data-ttu-id="0cba6-107">*Date et heure*</span><span class="sxs-lookup"><span data-stu-id="0cba6-107">*DateTime*</span></span>

<span data-ttu-id="0cba6-108">Valeur de date/heure résultante.</span><span class="sxs-lookup"><span data-stu-id="0cba6-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="0cba6-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="0cba6-109">Example</span></span>

<span data-ttu-id="0cba6-110">`DATETIMEFORMAT( NULLDATETIME(), "O")` renvoie la valeur de chaîne **1900-01-01T00:00:00.0000000+00:00** lorsqu'il est appelé lors d'un processus qui a été lancé par un utilisateur d'application qui a la valeur de fuseau horaire **(GMT) Temps universel coordonné** dans la section **Préférences de langue et paramètres locaux**.</span><span class="sxs-lookup"><span data-stu-id="0cba6-110">`DATETIMEFORMAT( NULLDATETIME(), "O")` returns the string value **1900-01-01T00:00:00.0000000+00:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT) Coordinated Universal Time** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0cba6-111">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0cba6-111">Additional resources</span></span>

[<span data-ttu-id="0cba6-112">Fonctions de date et d'heure</span><span class="sxs-lookup"><span data-stu-id="0cba6-112">Date and time functions</span></span>](er-functions-category-datetime.md)
