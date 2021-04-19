---
title: Fonction FIRSTORNULL ER
description: Cette rubrique explique l’utilisation de la fonction FIRSTORNULL États électroniques (ER)
author: NickSelin
ms.date: 11/29/2019
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
ms.openlocfilehash: 1ccc094fc468470ffc857c729b6d8402796785d7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753214"
---
# <a name="firstornull-er-function"></a><span data-ttu-id="7d188-103">Fonction FIRSTORNULL ER</span><span class="sxs-lookup"><span data-stu-id="7d188-103">FIRSTORNULL ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7d188-104">La fonction `FIRSTORNULL` renvoie le premier enregistrement de la liste spécifiée sous la forme d’une valeur de *Conteneur (enregistrement)*, si cet enregistrement n’est pas vide.</span><span class="sxs-lookup"><span data-stu-id="7d188-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="7d188-105">Si l’enregistrement est vide, cette fonction renvoie une valeur de *Conteneur (enregistrement)* null.</span><span class="sxs-lookup"><span data-stu-id="7d188-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d188-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7d188-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="7d188-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="7d188-107">Arguments</span></span>

<span data-ttu-id="7d188-108">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="7d188-108">`list`: *Record list*</span></span>

<span data-ttu-id="7d188-109">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="7d188-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="7d188-110">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="7d188-110">Return values</span></span>

<span data-ttu-id="7d188-111">*Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="7d188-111">*Container (record)*</span></span>

<span data-ttu-id="7d188-112">Valeur de l’enregistrement résultante.</span><span class="sxs-lookup"><span data-stu-id="7d188-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="7d188-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="7d188-113">Example</span></span>

<span data-ttu-id="7d188-114">L’expression `FIRSTORNULL(SPLIT("",1)).Value` renvoie une chaîne vide (**""**).</span><span class="sxs-lookup"><span data-stu-id="7d188-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7d188-115">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7d188-115">Additional resources</span></span>

[<span data-ttu-id="7d188-116">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="7d188-116">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]