---
title: Fonction EMPTYRECORD ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction EMPTYRECORD États électroniques (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d50b31fcbbb99050fca46b0a5ce10cc3fd243691
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684809"
---
# <a name="emptyrecord-er-function"></a><span data-ttu-id="e676f-103">Fonction EMPTYRECORD ER</span><span class="sxs-lookup"><span data-stu-id="e676f-103">EMPTYRECORD ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e676f-104">La fonction `EMPTYRECORD` renvoie une valeur de *Conteneur (enregistrement)* nulle avec la même structure que la liste d’enregistrements ou de l’enregistrement spécifiés.</span><span class="sxs-lookup"><span data-stu-id="e676f-104">The `EMPTYRECORD` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="e676f-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e676f-105">Syntax</span></span>

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a><span data-ttu-id="e676f-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="e676f-106">Arguments</span></span>

<span data-ttu-id="e676f-107">`list` : *Liste des enregistrements* ou *Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="e676f-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="e676f-108">Chemin d’accès valide d’une source de données de type *Liste des enregistrements* ou *Conteneur (enregistrement)*.</span><span class="sxs-lookup"><span data-stu-id="e676f-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="e676f-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="e676f-109">Return values</span></span>

<span data-ttu-id="e676f-110">*Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="e676f-110">*Container (record)*</span></span>

<span data-ttu-id="e676f-111">Valeur de l’enregistrement résultante.</span><span class="sxs-lookup"><span data-stu-id="e676f-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e676f-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="e676f-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="e676f-113">Un enregistrement null est un enregistrement où tous les champs ont une valeur vide.</span><span class="sxs-lookup"><span data-stu-id="e676f-113">A null record is a record where all fields have an empty value.</span></span> <span data-ttu-id="e676f-114">Une valeur vide correspond à **0** (zéro) pour les nombres, à une chaîne vide pour les chaînes, etc.</span><span class="sxs-lookup"><span data-stu-id="e676f-114">An empty value is **0** (zero) for numbers, an empty string for strings, and so on.</span></span>

## <a name="example"></a><span data-ttu-id="e676f-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="e676f-115">Example</span></span>

<span data-ttu-id="e676f-116">`EMPTYRECORD (SPLIT ("abc", 1))` renvoie un nouvel enregistrement vide ayant la même structure que la liste qui est renvoyée par la fonction `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="e676f-116">`EMPTYRECORD (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="e676f-117">Pour plus d’informations, voir [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="e676f-117">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e676f-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e676f-118">Additional resources</span></span>

[<span data-ttu-id="e676f-119">Fonctions d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="e676f-119">Record functions</span></span>](er-functions-category-record.md)
