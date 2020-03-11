---
title: Fonction JSONVALUE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction JSONVALUE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 75f20632074cb4dead98991fd6522ab9b20b9965
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041214"
---
# <span data-ttu-id="b5019-103"><a name="JSONVALUE">Fonction JSONVALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="b5019-103"><a name="JSONVALUE">JSONVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b5019-104">La fonction `JSONVALUE` analyse les données au format JavaScript Object Notation (JSON) qui sont accessibles au chemin d'accès spécifié et extrait une valeur scalaire avec l'ID spécifié.</span><span class="sxs-lookup"><span data-stu-id="b5019-104">The `JSONVALUE` function parses data in JavaScript Object Notation (JSON) format that is accessed at the specified path, and it extracts a scalar value that has the specified ID.</span></span> <span data-ttu-id="b5019-105">Elle renvoie ensuite la valeur scalaire extraite sous forme de valeur de *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="b5019-105">It then returns the extracted scalar value as a *String* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="b5019-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b5019-106">Syntax</span></span>

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a><span data-ttu-id="b5019-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="b5019-107">Arguments</span></span>

<span data-ttu-id="b5019-108">`input` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b5019-108">`input`: *String*</span></span>

<span data-ttu-id="b5019-109">Chemin d'accès valide d'une source de données du type *Chaîne* contenant des données JSON.</span><span class="sxs-lookup"><span data-stu-id="b5019-109">The valid path of a data source of the *String* type that contains JSON data.</span></span>

<span data-ttu-id="b5019-110">`path` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b5019-110">`path`: *String*</span></span>

<span data-ttu-id="b5019-111">Identificateur d'une valeur scalaire de données JSON.</span><span class="sxs-lookup"><span data-stu-id="b5019-111">The identifier of a scalar value of JSON data.</span></span>

## <a name="return-values"></a><span data-ttu-id="b5019-112">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="b5019-112">Return values</span></span>

<span data-ttu-id="b5019-113">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="b5019-113">*String*</span></span>

<span data-ttu-id="b5019-114">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="b5019-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="b5019-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="b5019-115">Example</span></span>

<span data-ttu-id="b5019-116">La source de données **$JsonField** contient les données suivantes au format JSON : **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span><span class="sxs-lookup"><span data-stu-id="b5019-116">The **JsonField** data source contains the following data in JSON format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span></span> <span data-ttu-id="b5019-117">Dans ce cas, l'expression `JSONVALUE (JsonField, "BuildNumber")` renvoie la valeur suivante de type de données *Chaîne* : **"7.3.1234.1"**.</span><span class="sxs-lookup"><span data-stu-id="b5019-117">In this case, the expression `JSONVALUE (JsonField, "BuildNumber")` returns the following value of the *String* data type: **"7.3.1234.1"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b5019-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b5019-118">Additional resources</span></span>

[<span data-ttu-id="b5019-119">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="b5019-119">Text functions</span></span>](er-functions-category-text.md)
