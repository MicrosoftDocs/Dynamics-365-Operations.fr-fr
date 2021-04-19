---
title: CN_GBT_ADDITIONALDIMENSIONID ER, fonction
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CN_GBT_ADDITIONALDIMENSIONID États électroniques (ER).
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
ms.openlocfilehash: ac0b54476265171b3826e43600f99097701231e1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744389"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a><span data-ttu-id="9ef62-103">CN_GBT_ADDITIONALDIMENSIONID ER, fonction</span><span class="sxs-lookup"><span data-stu-id="9ef62-103">CN_GBT_ADDITIONALDIMENSIONID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ef62-104">La fonction `CN_GBT_ADDITIONALDIMENSIONID` renvoie une valeur de *Chaîne* qui représente un ID de dimension financière unique extrait de la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9ef62-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="9ef62-105">La chaîne spécifiée présente toutes les dimensions sous la forme d’une liste d’ID séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="9ef62-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="9ef62-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9ef62-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="9ef62-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="9ef62-107">Arguments</span></span>

<span data-ttu-id="9ef62-108">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="9ef62-108">`text`: *String*</span></span>

<span data-ttu-id="9ef62-109">Valeur de *Chaîne* qui présente toutes les dimensions sous la forme d’une liste d’ID séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="9ef62-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="9ef62-110">`number` : Entier</span><span class="sxs-lookup"><span data-stu-id="9ef62-110">`number`: Integer</span></span>

<span data-ttu-id="9ef62-111">Valeur *Entier* qui définit le code souche de la dimension demandée dans la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9ef62-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="9ef62-112">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="9ef62-112">Return values</span></span>

<span data-ttu-id="9ef62-113">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="9ef62-113">*String*</span></span>

<span data-ttu-id="9ef62-114">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="9ef62-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="9ef62-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="9ef62-115">Example</span></span>

<span data-ttu-id="9ef62-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` renvoie **« CC »**.</span><span class="sxs-lookup"><span data-stu-id="9ef62-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9ef62-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9ef62-117">Additional resources</span></span>

[<span data-ttu-id="9ef62-118">Autre fonctions (spécifiques au domaine d’affaires)</span><span class="sxs-lookup"><span data-stu-id="9ef62-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]