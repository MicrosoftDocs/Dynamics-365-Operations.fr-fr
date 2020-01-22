---
title: Fonction REVERSE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction REVERSE États électroniques (ER).
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
ms.openlocfilehash: 3343ad788cef29a79f9b110bf29809cd5f0e5c63
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917233"
---
# <span data-ttu-id="c05c7-103"><a name="REVERSE">Fonction REVERSE ER</a></span><span class="sxs-lookup"><span data-stu-id="c05c7-103"><a name="REVERSE">REVERSE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c05c7-104">La fonction `REVERSE` renvoie la liste spécifiée en tant que valeur de *Liste des enregistrements* dans l'ordre de tri inversé.</span><span class="sxs-lookup"><span data-stu-id="c05c7-104">The `REVERSE` function returns the specified list as a *Record list* value in reversed sort order.</span></span>

## <a name="syntax"></a><span data-ttu-id="c05c7-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c05c7-105">Syntax</span></span>

```
REVERSE (list)
```

## <a name="arguments"></a><span data-ttu-id="c05c7-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="c05c7-106">Arguments</span></span>

<span data-ttu-id="c05c7-107">`list` : *Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="c05c7-107">`list`: *Record list*</span></span>

<span data-ttu-id="c05c7-108">Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="c05c7-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c05c7-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="c05c7-109">Return values</span></span>

<span data-ttu-id="c05c7-110">*Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="c05c7-110">*Record list*</span></span>

<span data-ttu-id="c05c7-111">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="c05c7-111">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="c05c7-112">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="c05c7-112">Example 1</span></span>

<span data-ttu-id="c05c7-113">Si vous entrez une source de données **DS** de type *Champ calculé*, et qu'elle contient l'expression `SPLIT ("C|B|A", "|")`, l'expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` renvoie la valeur de texte **« C »**.</span><span class="sxs-lookup"><span data-stu-id="c05c7-113">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` returns the text value **"C"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="c05c7-114">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="c05c7-114">Example 2</span></span>

<span data-ttu-id="c05c7-115">Si **Fournisseur** est configuré comme source de données d'états électroniques qui fait référence à la table VendTable, l'expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` renvoie une liste de fournisseurs qui est triée par nom dans l'ordre décroissant.</span><span class="sxs-lookup"><span data-stu-id="c05c7-115">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` returns a list of vendors that is sorted by name in descending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c05c7-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c05c7-116">Additional resources</span></span>

[<span data-ttu-id="c05c7-117">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="c05c7-117">List functions</span></span>](er-functions-category-list.md)
