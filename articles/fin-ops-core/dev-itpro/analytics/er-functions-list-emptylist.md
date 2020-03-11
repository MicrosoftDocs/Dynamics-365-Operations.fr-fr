---
title: Fonction EMPTYLIST ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction EMPTYLIST États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 5fb991eb9ee08aeb418313eb782dbde7fa22b763
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042180"
---
# <span data-ttu-id="b2b87-103"><a name="EMPTYLIST">Fonction EMPTYLIST ER</a></span><span class="sxs-lookup"><span data-stu-id="b2b87-103"><a name="EMPTYLIST">EMPTYLIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2b87-104">La fonction `EMPTYLIST` renvoie une valeur de *Liste d'enregistrements* à l'aide de la liste spécifiée comme source pour la structure de liste.</span><span class="sxs-lookup"><span data-stu-id="b2b87-104">The `EMPTYLIST` function returns an empty *Record list* value by using the specified list as a source for the list structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2b87-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b2b87-105">Syntax</span></span>

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a><span data-ttu-id="b2b87-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="b2b87-106">Arguments</span></span>

<span data-ttu-id="b2b87-107">`list` : *Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="b2b87-107">`list`: *Record list*</span></span>

<span data-ttu-id="b2b87-108">Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="b2b87-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="b2b87-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="b2b87-109">Return values</span></span>

<span data-ttu-id="b2b87-110">*Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="b2b87-110">*Record list*</span></span>

<span data-ttu-id="b2b87-111">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="b2b87-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="b2b87-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="b2b87-112">Example</span></span>

<span data-ttu-id="b2b87-113">`EMPTYLIST (SPLIT ("abc", 1))` renvoie une nouvelle liste vide ayant la même structure que la liste qui est renvoyée par la fonction `SPLIT` utilisée.</span><span class="sxs-lookup"><span data-stu-id="b2b87-113">`EMPTYLIST (SPLIT ("abc", 1))` returns a new empty list that has the same structure as the list that is returned by the `SPLIT` function that is used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2b87-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b2b87-114">Additional resources</span></span>

[<span data-ttu-id="b2b87-115">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="b2b87-115">List functions</span></span>](er-functions-category-list.md)
