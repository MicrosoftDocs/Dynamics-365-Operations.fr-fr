---
title: Fonction EMPTYRECORD ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction EMPTYRECORD États électroniques (ER).
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
ms.openlocfilehash: a02cdd085a236065bb3622b36f7d3284144d96e5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041277"
---
# <span data-ttu-id="856de-103"><a name="EMPTYRECORD">Fonction EMPTYRECORD ER</a></span><span class="sxs-lookup"><span data-stu-id="856de-103"><a name="EMPTYRECORD">EMPTYRECORD ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="856de-104">La fonction `EMPTYRECORD` renvoie une valeur de *Conteneur (enregistrement)* nulle avec la même structure que la liste d'enregistrements ou de l'enregistrement spécifiés.</span><span class="sxs-lookup"><span data-stu-id="856de-104">The `EMPTYRECORD` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="856de-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="856de-105">Syntax</span></span>

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a><span data-ttu-id="856de-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="856de-106">Arguments</span></span>

<span data-ttu-id="856de-107">`list` : *Liste des enregistrements* ou *Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="856de-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="856de-108">Chemin d'accès valide d'une source de données de type *Liste des enregistrements* ou *Conteneur (enregistrement)*.</span><span class="sxs-lookup"><span data-stu-id="856de-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="856de-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="856de-109">Return values</span></span>

<span data-ttu-id="856de-110">*Conteneur (enregistrement)*</span><span class="sxs-lookup"><span data-stu-id="856de-110">*Container (record)*</span></span>

<span data-ttu-id="856de-111">Valeur de l'enregistrement résultante.</span><span class="sxs-lookup"><span data-stu-id="856de-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="856de-112">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="856de-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="856de-113">Un enregistrement null est un enregistrement où tous les champs ont une valeur vide.</span><span class="sxs-lookup"><span data-stu-id="856de-113">A null record is a record where all fields have an empty value.</span></span> <span data-ttu-id="856de-114">Une valeur vide correspond à **0** (zéro) pour les nombres, à une chaîne vide pour les chaînes, etc.</span><span class="sxs-lookup"><span data-stu-id="856de-114">An empty value is **0** (zero) for numbers, an empty string for strings, and so on.</span></span>

## <a name="example"></a><span data-ttu-id="856de-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="856de-115">Example</span></span>

<span data-ttu-id="856de-116">`EMPTYRECORD (SPLIT ("abc", 1))` renvoie un nouvel enregistrement vide ayant la même structure que la liste qui est renvoyée par la fonction `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="856de-116">`EMPTYRECORD (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="856de-117">Pour plus d'informations, voir [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="856de-117">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="856de-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="856de-118">Additional resources</span></span>

[<span data-ttu-id="856de-119">Fonctions d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="856de-119">Record functions</span></span>](er-functions-category-record.md)
