---
title: Fonction SESSIONTODAY ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction SESSIONTODAY États électroniques (ER).
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
ms.openlocfilehash: bcfb36d6e3fb8475546f7cfb420c4aca848ac896
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917463"
---
# <span data-ttu-id="fd440-103"><a name="SESSIONTODAY">Fonction SESSIONTODAY ER</a></span><span class="sxs-lookup"><span data-stu-id="fd440-103"><a name="SESSIONTODAY">SESSIONTODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fd440-104">La fonction `SESSIONTODAY` renvoie une valeur *Date* qui représente la date actuelle de la session de l'application.</span><span class="sxs-lookup"><span data-stu-id="fd440-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="fd440-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fd440-105">Syntax</span></span>

```
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="fd440-106">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="fd440-106">Return values</span></span>

<span data-ttu-id="fd440-107">*Date*</span><span class="sxs-lookup"><span data-stu-id="fd440-107">*Date*</span></span>

<span data-ttu-id="fd440-108">Valeur de date résultante.</span><span class="sxs-lookup"><span data-stu-id="fd440-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="fd440-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="fd440-109">Example</span></span>

<span data-ttu-id="fd440-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` renvoie la date de la session de l'application actuelle, 24 décembre 2015, sous la forme de la chaîne **« 24-12-2015 »**, en fonction de la culture allemande et du format sélectionnés spécifiés.</span><span class="sxs-lookup"><span data-stu-id="fd440-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fd440-111">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fd440-111">Additional resources</span></span>

[<span data-ttu-id="fd440-112">Fonctions de date et d'heure</span><span class="sxs-lookup"><span data-stu-id="fd440-112">Date and time functions</span></span>](er-functions-category-datetime.md)