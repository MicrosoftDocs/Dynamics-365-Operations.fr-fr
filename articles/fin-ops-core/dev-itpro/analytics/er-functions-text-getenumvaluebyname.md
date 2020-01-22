---
title: Fonction GETENUMVALUEBYNAME ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction GETENUMVALUEBYNAME États électroniques (ER).
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
ms.openlocfilehash: 4ded0c62b4556b21e731cd9b98db2863ec6ec442
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916842"
---
# <span data-ttu-id="52f15-103"><a name="GETENUMVALUEBYNAME">Fonction GETENUMVALUEBYNAME ER</a></span><span class="sxs-lookup"><span data-stu-id="52f15-103"><a name="GETENUMVALUEBYNAME">GETENUMVALUEBYNAME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52f15-104">La fonction `GETENUMVALUEBYNAME` recherche une valeur *Enum* spécifique dans la source de données d'énumération spécifiée à l'aide du nom d'énumération spécifié en tant que valeur de *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="52f15-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="52f15-105">Si la valeur *Enum*, la fonction la renvoie.</span><span class="sxs-lookup"><span data-stu-id="52f15-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="52f15-106">Sinon, la fonction renvoie la valeur d'énumération **null**.</span><span class="sxs-lookup"><span data-stu-id="52f15-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="52f15-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="52f15-107">Syntax</span></span>

```
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="52f15-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="52f15-108">Arguments</span></span>

<span data-ttu-id="52f15-109">`enumeration data source path` : *Énumération*</span><span class="sxs-lookup"><span data-stu-id="52f15-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="52f15-110">Chemin d'accès valide d'une source de données de l'un des types d'énumération suivants :</span><span class="sxs-lookup"><span data-stu-id="52f15-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="52f15-111">Énumération du modèle de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="52f15-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="52f15-112">Énumération de format ER</span><span class="sxs-lookup"><span data-stu-id="52f15-112">ER format enumeration</span></span>
- <span data-ttu-id="52f15-113">Énumération Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="52f15-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="52f15-114">`enumeration value text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="52f15-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="52f15-115">Valeur de chaîne qui représente le nom d'une seule valeur d'énumération.</span><span class="sxs-lookup"><span data-stu-id="52f15-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="52f15-116">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="52f15-116">Return values</span></span>

<span data-ttu-id="52f15-117">*Enum* pouvant être null</span><span class="sxs-lookup"><span data-stu-id="52f15-117">Nullable *Enum*</span></span>

<span data-ttu-id="52f15-118">Valeur d'énumération résultante.</span><span class="sxs-lookup"><span data-stu-id="52f15-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="52f15-119">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="52f15-119">Usage notes</span></span>

<span data-ttu-id="52f15-120">Aucune exception n'est levée si aucune valeur *Enum* n'est trouvée en utilisant le nom de la valeur d'énumération spécifié en tant que valeur de *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="52f15-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example"></a><span data-ttu-id="52f15-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="52f15-121">Example</span></span>

<span data-ttu-id="52f15-122">Dans l'illustration suivante, l'énumération **ReportDirection** est présentée dans un modèle de données.</span><span class="sxs-lookup"><span data-stu-id="52f15-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="52f15-123">Notez que les étiquettes sont définies pour les valeurs d'énumération.</span><span class="sxs-lookup"><span data-stu-id="52f15-123">Notice that labels are defined for the enumeration values.</span></span>

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="52f15-124">Les détails suivants sont illustrés dans le graphique ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="52f15-124">The following illustration shows these details:</span></span>

- <span data-ttu-id="52f15-125">La source de données **$Direction** est configurée dans un état ER.</span><span class="sxs-lookup"><span data-stu-id="52f15-125">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="52f15-126">Cette source de données est configurée en fonction de l'énumération du modèle **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="52f15-126">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="52f15-127">L'expression `$IsArrivals` est conçue pour utiliser la source de données **$Direction** basée sur l'énumération du modèle comme paramètre de cette fonction.</span><span class="sxs-lookup"><span data-stu-id="52f15-127">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="52f15-128">La valeur de cette expression de comparaison est **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="52f15-128">The value of this comparison expression is **TRUE**.</span></span>

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a><span data-ttu-id="52f15-129">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="52f15-129">Additional resources</span></span>

[<span data-ttu-id="52f15-130">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="52f15-130">Text functions</span></span>](er-functions-category-text.md)
