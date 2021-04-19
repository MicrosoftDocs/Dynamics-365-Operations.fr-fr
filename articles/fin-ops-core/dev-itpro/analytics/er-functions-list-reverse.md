---
title: Fonction REVERSE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction REVERSE États électroniques (ER).
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
ms.openlocfilehash: 746a736c8797c1c1c5bd71d7d803be4212984595
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755202"
---
# <a name="reverse-er-function"></a><span data-ttu-id="077e0-103">Fonction REVERSE ER</span><span class="sxs-lookup"><span data-stu-id="077e0-103">REVERSE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="077e0-104">La fonction `REVERSE` renvoie la liste spécifiée en tant que valeur de *Liste des enregistrements* dans l’ordre de tri inversé.</span><span class="sxs-lookup"><span data-stu-id="077e0-104">The `REVERSE` function returns the specified list as a *Record list* value in reversed sort order.</span></span>

## <a name="syntax"></a><span data-ttu-id="077e0-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="077e0-105">Syntax</span></span>

```vb
REVERSE (list)
```

## <a name="arguments"></a><span data-ttu-id="077e0-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="077e0-106">Arguments</span></span>

<span data-ttu-id="077e0-107">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="077e0-107">`list`: *Record list*</span></span>

<span data-ttu-id="077e0-108">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="077e0-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="077e0-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="077e0-109">Return values</span></span>

<span data-ttu-id="077e0-110">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="077e0-110">*Record list*</span></span>

<span data-ttu-id="077e0-111">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="077e0-111">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="077e0-112">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="077e0-112">Example 1</span></span>

<span data-ttu-id="077e0-113">Si vous entrez une source de données **DS** de type *Champ calculé*, et qu’elle contient l’expression `SPLIT ("C|B|A", "|")`, l’expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` renvoie la valeur de texte **« C »**.</span><span class="sxs-lookup"><span data-stu-id="077e0-113">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` returns the text value **"C"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="077e0-114">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="077e0-114">Example 2</span></span>

<span data-ttu-id="077e0-115">Si **Fournisseur** est configuré comme source de données d’états électroniques qui fait référence à la table VendTable, l’expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` renvoie une liste de fournisseurs qui est triée par nom dans l’ordre décroissant.</span><span class="sxs-lookup"><span data-stu-id="077e0-115">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` returns a list of vendors that is sorted by name in descending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="077e0-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="077e0-116">Additional resources</span></span>

[<span data-ttu-id="077e0-117">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="077e0-117">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]