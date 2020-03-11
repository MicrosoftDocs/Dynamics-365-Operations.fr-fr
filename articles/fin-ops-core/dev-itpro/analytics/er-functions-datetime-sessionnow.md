---
title: Fonction SESSIONNOW ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction SESSIONNOW États électroniques (ER).
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
ms.openlocfilehash: 5489fab61791654c2e583fc11b27aba09fb90c86
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042295"
---
# <span data-ttu-id="43b4d-103"><a name="">Fonction SESSIONNOW ER</a></span><span class="sxs-lookup"><span data-stu-id="43b4d-103"><a name="">SESSIONNOW ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43b4d-104">La fonction `SESSIONNOW` renvoie une valeur *DateTime* qui représente la date et l'heure actuelles de la session de l'application.</span><span class="sxs-lookup"><span data-stu-id="43b4d-104">The `SESSIONNOW` function returns a *DateTime* value that represents the current application session date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="43b4d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="43b4d-105">Syntax</span></span>

```vb
SESSIONNOW ()
```

## <a name="return-values"></a><span data-ttu-id="43b4d-106">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="43b4d-106">Return values</span></span>

<span data-ttu-id="43b4d-107">*Date et heure*</span><span class="sxs-lookup"><span data-stu-id="43b4d-107">*DateTime*</span></span>

<span data-ttu-id="43b4d-108">Valeur de date/heure résultante.</span><span class="sxs-lookup"><span data-stu-id="43b4d-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="43b4d-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="43b4d-109">Example</span></span>

<span data-ttu-id="43b4d-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` renvoie la valeur de date/heure de la session de l'application actuelle, 24 décembre 2015, sous la forme de **« 24.12.2015 »**, en fonction de la culture allemande et du format sélectionnés spécifiés.</span><span class="sxs-lookup"><span data-stu-id="43b4d-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="43b4d-111">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="43b4d-111">Additional resources</span></span>

[<span data-ttu-id="43b4d-112">Fonctions de date et d'heure</span><span class="sxs-lookup"><span data-stu-id="43b4d-112">Date and time functions</span></span>](er-functions-category-datetime.md)
