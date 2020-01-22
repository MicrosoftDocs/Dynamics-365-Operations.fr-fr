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
ms.openlocfilehash: c7e9917dcdc45a52e0ad490f5fa194d5390cc437
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917417"
---
# <span data-ttu-id="25155-103"><a name="TODAY">Fonction TODAY ER</a></span><span class="sxs-lookup"><span data-stu-id="25155-103"><a name="TODAY">TODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="25155-104">La fonction `TODAY` renvoie une valeur *Date* qui représente la date actuelle du serveur d'applications.</span><span class="sxs-lookup"><span data-stu-id="25155-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="25155-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="25155-105">Syntax</span></span>

```
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="25155-106">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="25155-106">Return values</span></span>

<span data-ttu-id="25155-107">*date ;*</span><span class="sxs-lookup"><span data-stu-id="25155-107">*Date*</span></span>

<span data-ttu-id="25155-108">Valeur de date résultante.</span><span class="sxs-lookup"><span data-stu-id="25155-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="25155-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="25155-109">Example</span></span>

<span data-ttu-id="25155-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` renvoie la date du serveur d'applications actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction du format personnalisé spécifié.</span><span class="sxs-lookup"><span data-stu-id="25155-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25155-111">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="25155-111">Additional resources</span></span>

[<span data-ttu-id="25155-112">Fonctions de date et d'heure</span><span class="sxs-lookup"><span data-stu-id="25155-112">Date and time functions</span></span>](er-functions-category-datetime.md)