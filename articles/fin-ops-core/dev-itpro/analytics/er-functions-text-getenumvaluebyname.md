---
title: Fonction GETENUMVALUEBYNAME ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction GETENUMVALUEBYNAME États électroniques (ER).
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
ms.openlocfilehash: 33ccf358dc5355cd00d5ff41ebd8148a334cba38
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743853"
---
# <a name="getenumvaluebyname-er-function"></a><span data-ttu-id="ea869-103">Fonction GETENUMVALUEBYNAME ER</span><span class="sxs-lookup"><span data-stu-id="ea869-103">GETENUMVALUEBYNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea869-104">La fonction `GETENUMVALUEBYNAME` recherche une valeur *Enum* spécifique dans la source de données d’énumération spécifiée à l’aide du nom d’énumération spécifié en tant que valeur de *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="ea869-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="ea869-105">Si la valeur *Enum*, la fonction la renvoie.</span><span class="sxs-lookup"><span data-stu-id="ea869-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="ea869-106">Sinon, la fonction renvoie la valeur d’énumération **null**.</span><span class="sxs-lookup"><span data-stu-id="ea869-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="ea869-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ea869-107">Syntax</span></span>

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="ea869-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="ea869-108">Arguments</span></span>

<span data-ttu-id="ea869-109">`enumeration data source path` : *Énumération*</span><span class="sxs-lookup"><span data-stu-id="ea869-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="ea869-110">Chemin d’accès valide d’une source de données de l’un des types d’énumération suivants :</span><span class="sxs-lookup"><span data-stu-id="ea869-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="ea869-111">Énumération du modèle de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="ea869-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="ea869-112">Énumération de format ER</span><span class="sxs-lookup"><span data-stu-id="ea869-112">ER format enumeration</span></span>
- <span data-ttu-id="ea869-113">Énumération Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="ea869-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="ea869-114">`enumeration value text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ea869-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="ea869-115">Valeur de chaîne qui représente le nom d’une seule valeur d’énumération.</span><span class="sxs-lookup"><span data-stu-id="ea869-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="ea869-116">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="ea869-116">Return values</span></span>

<span data-ttu-id="ea869-117">*Enum* pouvant être null</span><span class="sxs-lookup"><span data-stu-id="ea869-117">Nullable *Enum*</span></span>

<span data-ttu-id="ea869-118">Valeur d’énumération résultante.</span><span class="sxs-lookup"><span data-stu-id="ea869-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ea869-119">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="ea869-119">Usage notes</span></span>

<span data-ttu-id="ea869-120">Aucune exception n’est levée si aucune valeur *Enum* n’est trouvée en utilisant le nom de la valeur d’énumération spécifié en tant que valeur de *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="ea869-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example"></a><span data-ttu-id="ea869-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="ea869-121">Example</span></span>

<span data-ttu-id="ea869-122">Dans l’illustration suivante, l’énumération **ReportDirection** est présentée dans un modèle de données.</span><span class="sxs-lookup"><span data-stu-id="ea869-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="ea869-123">Notez que les étiquettes sont définies pour les valeurs d’énumération.</span><span class="sxs-lookup"><span data-stu-id="ea869-123">Notice that labels are defined for the enumeration values.</span></span>

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="ea869-124">Les détails suivants sont illustrés dans le graphique ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="ea869-124">The following illustration shows these details:</span></span>

- <span data-ttu-id="ea869-125">La source de données **$Direction** est configurée dans un état ER.</span><span class="sxs-lookup"><span data-stu-id="ea869-125">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="ea869-126">Cette source de données est configurée en fonction de l’énumération du modèle **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="ea869-126">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="ea869-127">L’expression `$IsArrivals` est conçue pour utiliser la source de données **$Direction** basée sur l’énumération du modèle comme paramètre de cette fonction.</span><span class="sxs-lookup"><span data-stu-id="ea869-127">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="ea869-128">La valeur de cette expression de comparaison est **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="ea869-128">The value of this comparison expression is **TRUE**.</span></span>

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a><span data-ttu-id="ea869-129">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ea869-129">Additional resources</span></span>

[<span data-ttu-id="ea869-130">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="ea869-130">Text functions</span></span>](er-functions-category-text.md)
