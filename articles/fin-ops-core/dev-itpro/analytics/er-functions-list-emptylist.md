---
title: Fonction EMPTYLIST ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction EMPTYLIST États électroniques (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 1e2a92d9951c3ad27503cf82f1b45026f16c3835
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746673"
---
# <a name="emptylist-er-function"></a><span data-ttu-id="82d98-103">Fonction EMPTYLIST ER</span><span class="sxs-lookup"><span data-stu-id="82d98-103">EMPTYLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82d98-104">La fonction `EMPTYLIST` renvoie une valeur de *Liste d’enregistrements* à l’aide de la liste spécifiée comme source pour la structure de liste.</span><span class="sxs-lookup"><span data-stu-id="82d98-104">The `EMPTYLIST` function returns an empty *Record list* value by using the specified list as a source for the list structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="82d98-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="82d98-105">Syntax</span></span>

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a><span data-ttu-id="82d98-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="82d98-106">Arguments</span></span>

<span data-ttu-id="82d98-107">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="82d98-107">`list`: *Record list*</span></span>

<span data-ttu-id="82d98-108">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="82d98-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="82d98-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="82d98-109">Return values</span></span>

<span data-ttu-id="82d98-110">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="82d98-110">*Record list*</span></span>

<span data-ttu-id="82d98-111">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="82d98-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="82d98-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="82d98-112">Example</span></span>

<span data-ttu-id="82d98-113">`EMPTYLIST (SPLIT ("abc", 1))` renvoie une nouvelle liste vide ayant la même structure que la liste qui est renvoyée par la fonction `SPLIT` utilisée.</span><span class="sxs-lookup"><span data-stu-id="82d98-113">`EMPTYLIST (SPLIT ("abc", 1))` returns a new empty list that has the same structure as the list that is returned by the `SPLIT` function that is used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="82d98-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="82d98-114">Additional resources</span></span>

[<span data-ttu-id="82d98-115">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="82d98-115">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]