---
title: Fonction NOW ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction NOW États électroniques (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: c93aa2a0e3f6aa07ab9e843d3c5f11c5265e8c40
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746865"
---
# <a name="now-er-function"></a><span data-ttu-id="363e4-103">Fonction NOW ER</span><span class="sxs-lookup"><span data-stu-id="363e4-103">NOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="363e4-104">La fonction `NOW` renvoie une valeur *DateTime* qui représente la date et l’heure actuelles du serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="363e4-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="363e4-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="363e4-105">Syntax</span></span>

```vb
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="363e4-106">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="363e4-106">Return values</span></span>

<span data-ttu-id="363e4-107">*Date et heure*</span><span class="sxs-lookup"><span data-stu-id="363e4-107">*DateTime*</span></span>

<span data-ttu-id="363e4-108">Valeur de date/heure résultante.</span><span class="sxs-lookup"><span data-stu-id="363e4-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="363e4-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="363e4-109">Example</span></span>

<span data-ttu-id="363e4-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` renvoie la valeur de date/heure du serveur d’applications actuelle, 24 décembre 2015, sous la forme **« 24-12-2015 »**, en fonction du format personnalisé spécifié.</span><span class="sxs-lookup"><span data-stu-id="363e4-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="363e4-111">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="363e4-111">Additional resources</span></span>

[<span data-ttu-id="363e4-112">Fonctions de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="363e4-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]