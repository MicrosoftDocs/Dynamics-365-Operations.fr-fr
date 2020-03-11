---
title: Fonction DATETODATETIME ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction DATETODATETIME États électroniques (ER).
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
ms.openlocfilehash: 961ccd18e70d4f9851027492366a7d9408a668c5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042410"
---
# <span data-ttu-id="3596b-103"><a name="DATETODATETIME">Fonction DATETODATETIME ER</a></span><span class="sxs-lookup"><span data-stu-id="3596b-103"><a name="DATETODATETIME">DATETODATETIME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3596b-104">La fonction `DATETODATETIME` renvoie une valeur de *DateTime* qui est convertie d'une valeur de date donnée en une valeur de date/heure en temps universel coordonné (Heure de Greenwich, \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="3596b-104">The `DATETODATETIME` function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="3596b-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3596b-105">Syntax</span></span>

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a><span data-ttu-id="3596b-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="3596b-106">Arguments</span></span>

<span data-ttu-id="3596b-107">`date` : *Date*</span><span class="sxs-lookup"><span data-stu-id="3596b-107">`date`: *Date*</span></span>

<span data-ttu-id="3596b-108">Valeur de date qui représente la date à convertir.</span><span class="sxs-lookup"><span data-stu-id="3596b-108">A date value that represents the date to convert.</span></span>

## <a name="return-values"></a><span data-ttu-id="3596b-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="3596b-109">Return values</span></span>

<span data-ttu-id="3596b-110">*Date et heure*</span><span class="sxs-lookup"><span data-stu-id="3596b-110">*DateTime*</span></span>

<span data-ttu-id="3596b-111">Valeur de date/heure résultante.</span><span class="sxs-lookup"><span data-stu-id="3596b-111">The resulting date/time value.</span></span>

## <a name="example-1"></a><span data-ttu-id="3596b-112">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="3596b-112">Example 1</span></span>

<span data-ttu-id="3596b-113">`DATETODATETIME (CompInfo. 'getCurrentDate()')` renvoie la date de la session Microsoft Dynamics 365 Finance actuelle, le 24 décembre 2015, **12/24/2015 12:00:00 AM**.</span><span class="sxs-lookup"><span data-stu-id="3596b-113">`DATETODATETIME (CompInfo. 'getCurrentDate()')` returns the date of the current Microsoft Dynamics 365 Finance session, December 24, 2015, as **12/24/2015 12:00:00 AM**.</span></span> <span data-ttu-id="3596b-114">Dans cet exemple, **CompInfo** est une source de données de génération d'états électroniques de type **Finance and Operations/Table** qui fait référence à la table CompanyInfo.</span><span class="sxs-lookup"><span data-stu-id="3596b-114">In this example, **CompInfo** is an Electronic reporting (ER) data source of the **Finance and Operations/Table** type, and it refers to the CompanyInfo table.</span></span>

## <a name="example-2"></a><span data-ttu-id="3596b-115">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="3596b-115">Example 2</span></span>

<span data-ttu-id="3596b-116">`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` renvoie la valeur de date/heure **11/12/2019 12:00:00 AM**.</span><span class="sxs-lookup"><span data-stu-id="3596b-116">`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` returns the date/time value **11/12/2019 12:00:00 AM**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3596b-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3596b-117">Additional resources</span></span>

[<span data-ttu-id="3596b-118">Fonctions de date et d'heure</span><span class="sxs-lookup"><span data-stu-id="3596b-118">Date and time functions</span></span>](er-functions-category-datetime.md)
