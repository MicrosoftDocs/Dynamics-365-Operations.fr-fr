---
title: Fonction LISTOFFIRSTITEM ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction LISTOFFIRSTITEM États électroniques (ER).
author: NickSelin
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
ms.openlocfilehash: 6dd6c84b43bea36bf922ae9348f95b450e882832
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750178"
---
# <a name="listoffirstitem-er-function"></a><span data-ttu-id="5ed65-103">Fonction LISTOFFIRSTITEM ER</span><span class="sxs-lookup"><span data-stu-id="5ed65-103">LISTOFFIRSTITEM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ed65-104">La fonction `LISTOFFIRSTITEM` renvoie une valeur *Liste des enregistrements* constituée uniquement du premier enregistrement de la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="5ed65-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ed65-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5ed65-105">Syntax</span></span>

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="5ed65-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="5ed65-106">Arguments</span></span>

<span data-ttu-id="5ed65-107">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="5ed65-107">`list`: *Record list*</span></span>

<span data-ttu-id="5ed65-108">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="5ed65-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="5ed65-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="5ed65-109">Return values</span></span>

<span data-ttu-id="5ed65-110">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="5ed65-110">*Record list*</span></span>

<span data-ttu-id="5ed65-111">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="5ed65-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="5ed65-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="5ed65-112">Example</span></span>

<span data-ttu-id="5ed65-113">L’expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` renvoie la valeur texte **« A »**.</span><span class="sxs-lookup"><span data-stu-id="5ed65-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ed65-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5ed65-114">Additional resources</span></span>

[<span data-ttu-id="5ed65-115">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="5ed65-115">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]