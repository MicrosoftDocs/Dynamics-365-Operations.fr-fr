---
title: Fonction GUIDVALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction GUIDVALUE États électroniques (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 552c6a42dd0e189f2f8404ce5d7f7a68fec1b216
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564336"
---
# <a name="guidvalue-er-function"></a><span data-ttu-id="24632-103">Fonction GUIDVALUE ER</span><span class="sxs-lookup"><span data-stu-id="24632-103">GUIDVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="24632-104">La fonction `GUIDVALUE` convertit l’entrée spécifiée du type *Chaîne* en un élément de données du type *GUID*.</span><span class="sxs-lookup"><span data-stu-id="24632-104">The `GUIDVALUE` function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="24632-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="24632-105">Syntax</span></span>

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a><span data-ttu-id="24632-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="24632-106">Arguments</span></span>

<span data-ttu-id="24632-107">`input` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="24632-107">`input`: *String*</span></span>

<span data-ttu-id="24632-108">Chemin d’accès valide d’une source de données du type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="24632-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="24632-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="24632-109">Return values</span></span>

<span data-ttu-id="24632-110">*GUID*</span><span class="sxs-lookup"><span data-stu-id="24632-110">*GUID*</span></span>

<span data-ttu-id="24632-111">Valeur de l’identificateur global unique (GUID) résultant.</span><span class="sxs-lookup"><span data-stu-id="24632-111">The resulting globally unique identifier (GUID) value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="24632-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="24632-112">Usage notes</span></span>

<span data-ttu-id="24632-113">Pour créer une conversion dans la direction opposée (c’est-à-dire, pour convertir l’entrée spécifiée du type de données *GUID* en un élément de données de type de données *Chaîne*), vous pouvez utiliser la fonction [TEXT](er-functions-text-text.md).</span><span class="sxs-lookup"><span data-stu-id="24632-113">To do a conversion in the opposite direction (that is, to convert specified input of the *GUID* data type to a data item of the *String* data type), you can use the [TEXT](er-functions-text-text.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="24632-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="24632-114">Example</span></span>

<span data-ttu-id="24632-115">Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :</span><span class="sxs-lookup"><span data-stu-id="24632-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="24632-116">Source de données **myID** du type *Champ calculé* qui contient l’expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span><span class="sxs-lookup"><span data-stu-id="24632-116">A **myID** data source of the *Calculated field* type that contains the expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span></span>
- <span data-ttu-id="24632-117">Source de données **Users** de type *Enregistrements de la table* qui fait référence à la table UserInfo</span><span class="sxs-lookup"><span data-stu-id="24632-117">A **Users** data source of the *Table records* type that refers to the UserInfo table</span></span>

<span data-ttu-id="24632-118">Vous pouvez ensuite utiliser une expression telle que `FILTER (Users, Users.objectId = myID)` pour filtrer la table UserInfo selon le champ **objectId** du type de données *GUID*.</span><span class="sxs-lookup"><span data-stu-id="24632-118">You can then use an expression such as `FILTER (Users, Users.objectId = myID)` to filter the UserInfo table by the **objectId** field of the *GUID* data type.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="24632-119">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="24632-119">Additional resources</span></span>

[<span data-ttu-id="24632-120">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="24632-120">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]