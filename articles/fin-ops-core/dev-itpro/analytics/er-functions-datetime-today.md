---
title: Fonction TODAY ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction TODAY États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 94ef15d1971287e8bf13944bc8f693b567950031
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411435"
---
# <a name=""></a><span data-ttu-id="2524d-103"><a name="TODAY">Fonction TODAY ER</a></span><span class="sxs-lookup"><span data-stu-id="2524d-103"><a name="TODAY">TODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2524d-104">La fonction `TODAY` renvoie une valeur *Date* qui représente la date actuelle du serveur d'applications.</span><span class="sxs-lookup"><span data-stu-id="2524d-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="2524d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2524d-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="2524d-106">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="2524d-106">Return values</span></span>

<span data-ttu-id="2524d-107">*date ;*</span><span class="sxs-lookup"><span data-stu-id="2524d-107">*Date*</span></span>

<span data-ttu-id="2524d-108">Valeur de date résultante.</span><span class="sxs-lookup"><span data-stu-id="2524d-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="2524d-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="2524d-109">Example</span></span>

<span data-ttu-id="2524d-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` renvoie la date du serveur d'applications actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction du format personnalisé spécifié.</span><span class="sxs-lookup"><span data-stu-id="2524d-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2524d-111">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2524d-111">Additional resources</span></span>

[<span data-ttu-id="2524d-112">Fonctions de date et d'heure</span><span class="sxs-lookup"><span data-stu-id="2524d-112">Date and time functions</span></span>](er-functions-category-datetime.md)
