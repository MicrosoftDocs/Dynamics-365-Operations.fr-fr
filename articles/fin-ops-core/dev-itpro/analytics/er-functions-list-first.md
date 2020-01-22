---
title: Fonction FIRST ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction FIRST États électroniques (ER).
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
ms.openlocfilehash: 211891a0ad5dc6152ce8d980bcd40a9a6bc7e3e6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917348"
---
# <span data-ttu-id="31eb6-103"><a name="FIRST">Fonction FIRST ER</a></span><span class="sxs-lookup"><span data-stu-id="31eb6-103"><a name="FIRST">FIRST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31eb6-104">La fonction `FIRST` renvoie le premier enregistrement de la liste spécifiée sous la forme d'une valeur de *Conteneur (enregistrement)*, si cette liste n'est pas vide.</span><span class="sxs-lookup"><span data-stu-id="31eb6-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="31eb6-105">Si la liste est vide, cette fonction lève une exception.</span><span class="sxs-lookup"><span data-stu-id="31eb6-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="31eb6-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="31eb6-106">Syntax</span></span>

```
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="31eb6-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="31eb6-107">Arguments</span></span>

<span data-ttu-id="31eb6-108">`list` : *Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="31eb6-108">`list`: *Record list*</span></span>

<span data-ttu-id="31eb6-109">Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="31eb6-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="31eb6-110">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="31eb6-110">Return values</span></span>

<span data-ttu-id="31eb6-111">*Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="31eb6-111">*Container (record)*</span></span>

<span data-ttu-id="31eb6-112">Valeur de l'enregistrement résultante.</span><span class="sxs-lookup"><span data-stu-id="31eb6-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="31eb6-113">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="31eb6-113">Example 1</span></span>

<span data-ttu-id="31eb6-114">L'expression `FIRST(SPLIT("ABC",1)).Value` renvoie la valeur texte **« A »**.</span><span class="sxs-lookup"><span data-stu-id="31eb6-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="31eb6-115">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="31eb6-115">Example 2</span></span>

<span data-ttu-id="31eb6-116">L'expression `FIRST(SPLIT("",1)).Value` lève une exception lors de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="31eb6-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="31eb6-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="31eb6-117">Additional resources</span></span>

[<span data-ttu-id="31eb6-118">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="31eb6-118">List functions</span></span>](er-functions-category-list.md)