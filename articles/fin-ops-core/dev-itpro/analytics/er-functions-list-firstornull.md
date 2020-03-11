---
title: Fonction FIRSTORNULL ER
description: Cette rubrique explique l'utilisation de la fonction FIRSTORNULL États électroniques (ER)
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 86c8a0ae21ffeb6268efbbd198f7c709c2ad54f6
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042111"
---
# <span data-ttu-id="29c0a-103"><a name="FIRSTORNULL">Fonction FIRSTORNULL ER</a></span><span class="sxs-lookup"><span data-stu-id="29c0a-103"><a name="FIRSTORNULL">FIRSTORNULL ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="29c0a-104">La fonction `FIRSTORNULL` renvoie le premier enregistrement de la liste spécifiée sous la forme d'une valeur de *Conteneur (enregistrement)*, si cet enregistrement n'est pas vide.</span><span class="sxs-lookup"><span data-stu-id="29c0a-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="29c0a-105">Si l'enregistrement est vide, cette fonction renvoie une valeur de *Conteneur (enregistrement)* null.</span><span class="sxs-lookup"><span data-stu-id="29c0a-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="29c0a-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="29c0a-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="29c0a-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="29c0a-107">Arguments</span></span>

<span data-ttu-id="29c0a-108">`list` : *Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="29c0a-108">`list`: *Record list*</span></span>

<span data-ttu-id="29c0a-109">Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="29c0a-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="29c0a-110">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="29c0a-110">Return values</span></span>

<span data-ttu-id="29c0a-111">*Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="29c0a-111">*Container (record)*</span></span>

<span data-ttu-id="29c0a-112">Valeur de l'enregistrement résultante.</span><span class="sxs-lookup"><span data-stu-id="29c0a-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="29c0a-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="29c0a-113">Example</span></span>

<span data-ttu-id="29c0a-114">L'expression `FIRSTORNULL(SPLIT("",1)).Value` renvoie une chaîne vide (**""**).</span><span class="sxs-lookup"><span data-stu-id="29c0a-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="29c0a-115">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="29c0a-115">Additional resources</span></span>

[<span data-ttu-id="29c0a-116">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="29c0a-116">List functions</span></span>](er-functions-category-list.md)
