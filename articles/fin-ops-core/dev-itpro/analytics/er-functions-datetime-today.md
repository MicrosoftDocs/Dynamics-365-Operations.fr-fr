---
title: Fonction TODAY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction TODAY États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 9288baf4e6123a7c03152f524a852eae9b671dde
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567914"
---
# <a name="today-er-function"></a><span data-ttu-id="0276e-103">Fonction TODAY ER</span><span class="sxs-lookup"><span data-stu-id="0276e-103">TODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0276e-104">La fonction `TODAY` renvoie une valeur *Date* qui représente la date actuelle du serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="0276e-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="0276e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0276e-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="0276e-106">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="0276e-106">Return values</span></span>

<span data-ttu-id="0276e-107">*date ;*</span><span class="sxs-lookup"><span data-stu-id="0276e-107">*Date*</span></span>

<span data-ttu-id="0276e-108">Valeur de date résultante.</span><span class="sxs-lookup"><span data-stu-id="0276e-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="0276e-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="0276e-109">Example</span></span>

<span data-ttu-id="0276e-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` renvoie la date du serveur d’applications actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction du format personnalisé spécifié.</span><span class="sxs-lookup"><span data-stu-id="0276e-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0276e-111">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0276e-111">Additional resources</span></span>

[<span data-ttu-id="0276e-112">Fonctions de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="0276e-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]