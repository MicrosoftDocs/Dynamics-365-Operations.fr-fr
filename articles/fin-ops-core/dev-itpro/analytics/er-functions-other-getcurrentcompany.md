---
title: Fonction GETCURRENTCOMPANY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction GETCURRENTCOMPANY États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 7e3c164c6d54d8387eed5018219da5fd82c765c8
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744118"
---
# <a name="getcurrentcompany-er-function"></a><span data-ttu-id="27ba5-103">Fonction GETCURRENTCOMPANY ER</span><span class="sxs-lookup"><span data-stu-id="27ba5-103">GETCURRENTCOMPANY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="27ba5-104">La fonction `GETCURRENTCOMPANY` renvoie une valeur de *Chaîne* qui représente le code de l’entité juridique (société) à laquelle un utilisateur est actuellement connecté.</span><span class="sxs-lookup"><span data-stu-id="27ba5-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="27ba5-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="27ba5-105">Syntax</span></span>

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="27ba5-106">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="27ba5-106">Return values</span></span>

<span data-ttu-id="27ba5-107">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="27ba5-107">*String*</span></span>

<span data-ttu-id="27ba5-108">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="27ba5-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="27ba5-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="27ba5-109">Example</span></span>

<span data-ttu-id="27ba5-110">`GETCURRENTCOMPANY ()` renvoie **USMF** pour un utilisateur connecté à la société **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="27ba5-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="27ba5-111">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="27ba5-111">Additional resources</span></span>

[<span data-ttu-id="27ba5-112">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="27ba5-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
