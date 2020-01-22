---
title: Fonction TABLENAME2ID ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction TABLENAME2ID États électroniques (ER).
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
ms.openlocfilehash: 77d889f75f38b3c07855a96bf65f1456ac2f42e2
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915807"
---
# <span data-ttu-id="8e111-103"><a name="TABLENAME2ID">Fonction TABLENAME2ID ER</a></span><span class="sxs-lookup"><span data-stu-id="8e111-103"><a name="TABLENAME2ID">TABLENAME2ID ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8e111-104">La fonction `TABLENAME2ID` renvoie une représentation numérique de l'ID de table pour le nom de table spécifié en tant que valeur *Entier*.</span><span class="sxs-lookup"><span data-stu-id="8e111-104">The `TABLENAME2ID` function returns a numeric representation of the table ID for the specified table name as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="8e111-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8e111-105">Syntax</span></span>

```
TABLENAME2ID (text)
```

## <a name="arguments"></a><span data-ttu-id="8e111-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="8e111-106">Arguments</span></span>

<span data-ttu-id="8e111-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="8e111-107">`text`: *String*</span></span>

<span data-ttu-id="8e111-108">Valeur de texte qui représente un nom de table valide.</span><span class="sxs-lookup"><span data-stu-id="8e111-108">A text value that represents a valid table name.</span></span>

## <a name="return-values"></a><span data-ttu-id="8e111-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="8e111-109">Return values</span></span>

<span data-ttu-id="8e111-110">*Entier*</span><span class="sxs-lookup"><span data-stu-id="8e111-110">*Integer*</span></span>

<span data-ttu-id="8e111-111">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="8e111-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8e111-112">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="8e111-112">Usage notes</span></span>

<span data-ttu-id="8e111-113">L'exécution de cette fonction peut avoir des résultats différents dans différentes instances de Microsoft Dynamics 365 Finance, même si le même nom de société est utilisé.</span><span class="sxs-lookup"><span data-stu-id="8e111-113">Execution of this function can have different results in different instances of Microsoft Dynamics 365 Finance, even if the same company name is used.</span></span>

## <a name="example"></a><span data-ttu-id="8e111-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="8e111-114">Example</span></span>

<span data-ttu-id="8e111-115">`TABLENAME2ID ("Intrastat")` renvoie **1510**.</span><span class="sxs-lookup"><span data-stu-id="8e111-115">`TABLENAME2ID ("Intrastat")` returns **1510**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8e111-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8e111-116">Additional resources</span></span>

[<span data-ttu-id="8e111-117">Autre fonctions (spécifiques au domaine d'affaires)</span><span class="sxs-lookup"><span data-stu-id="8e111-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)