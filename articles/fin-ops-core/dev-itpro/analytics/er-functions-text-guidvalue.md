---
title: Fonction GUIDVALUE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction GUIDVALUE États électroniques (ER).
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
ms.openlocfilehash: a7b8c782aff488a433c40a49ab7f4fe2d0e944e4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041165"
---
# <span data-ttu-id="4ee4d-103"><a name="GUIDVALUE">Fonction GUIDVALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="4ee4d-103"><a name="GUIDVALUE">GUIDVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ee4d-104">La fonction `GUIDVALUE` convertit l'entrée spécifiée du type *Chaîne* en un élément de données du type *GUID*.</span><span class="sxs-lookup"><span data-stu-id="4ee4d-104">The `GUIDVALUE` function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="4ee4d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4ee4d-105">Syntax</span></span>

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a><span data-ttu-id="4ee4d-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="4ee4d-106">Arguments</span></span>

<span data-ttu-id="4ee4d-107">`input` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="4ee4d-107">`input`: *String*</span></span>

<span data-ttu-id="4ee4d-108">Chemin d'accès valide d'une source de données du type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="4ee4d-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="4ee4d-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="4ee4d-109">Return values</span></span>

<span data-ttu-id="4ee4d-110">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4ee4d-110">*GUID*</span></span>

<span data-ttu-id="4ee4d-111">Valeur de l'identificateur global unique (GUID) résultant.</span><span class="sxs-lookup"><span data-stu-id="4ee4d-111">The resulting globally unique identifier (GUID) value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="4ee4d-112">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="4ee4d-112">Usage notes</span></span>

<span data-ttu-id="4ee4d-113">Pour créer une conversion dans la direction opposée (c'est-à-dire, pour convertir l'entrée spécifiée du type de données *GUID* en un élément de données de type de données *Chaîne*), vous pouvez utiliser la fonction [TEXT](er-functions-text-text.md).</span><span class="sxs-lookup"><span data-stu-id="4ee4d-113">To do a conversion in the opposite direction (that is, to convert specified input of the *GUID* data type to a data item of the *String* data type), you can use the [TEXT](er-functions-text-text.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="4ee4d-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="4ee4d-114">Example</span></span>

<span data-ttu-id="4ee4d-115">Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :</span><span class="sxs-lookup"><span data-stu-id="4ee4d-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="4ee4d-116">Source de données **myID** du type *Champ calculé* qui contient l'expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span><span class="sxs-lookup"><span data-stu-id="4ee4d-116">A **myID** data source of the *Calculated field* type that contains the expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span></span>
- <span data-ttu-id="4ee4d-117">Source de données **Users** de type *Enregistrements de la table* qui fait référence à la table UserInfo</span><span class="sxs-lookup"><span data-stu-id="4ee4d-117">A **Users** data source of the *Table records* type that refers to the UserInfo table</span></span>

<span data-ttu-id="4ee4d-118">Vous pouvez ensuite utiliser une expression telle que `FILTER (Users, Users.objectId = myID)` pour filtrer la table UserInfo selon le champ **objectId** du type de données *GUID*.</span><span class="sxs-lookup"><span data-stu-id="4ee4d-118">You can then use an expression such as `FILTER (Users, Users.objectId = myID)` to filter the UserInfo table by the **objectId** field of the *GUID* data type.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ee4d-119">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4ee4d-119">Additional resources</span></span>

[<span data-ttu-id="4ee4d-120">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="4ee4d-120">Text functions</span></span>](er-functions-category-text.md)
