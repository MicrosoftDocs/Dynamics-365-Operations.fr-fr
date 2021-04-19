---
title: Fonction GETCURRENTCOMPANY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction GETCURRENTCOMPANY États électroniques (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 87bef4aa11c01b42af19f7dc20ca8731b9fb4111
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752827"
---
# <a name="getcurrentcompany-er-function"></a><span data-ttu-id="19ade-103">Fonction GETCURRENTCOMPANY ER</span><span class="sxs-lookup"><span data-stu-id="19ade-103">GETCURRENTCOMPANY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19ade-104">La fonction `GETCURRENTCOMPANY` renvoie une valeur de *Chaîne* qui représente le code de l’entité juridique (société) à laquelle un utilisateur est actuellement connecté.</span><span class="sxs-lookup"><span data-stu-id="19ade-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="19ade-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="19ade-105">Syntax</span></span>

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="19ade-106">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="19ade-106">Return values</span></span>

<span data-ttu-id="19ade-107">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="19ade-107">*String*</span></span>

<span data-ttu-id="19ade-108">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="19ade-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="19ade-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="19ade-109">Example</span></span>

<span data-ttu-id="19ade-110">`GETCURRENTCOMPANY ()` renvoie **USMF** pour un utilisateur connecté à la société **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="19ade-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="19ade-111">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="19ade-111">Additional resources</span></span>

[<span data-ttu-id="19ade-112">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="19ade-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]