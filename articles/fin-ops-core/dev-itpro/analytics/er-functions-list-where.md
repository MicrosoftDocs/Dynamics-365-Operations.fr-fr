---
title: Fonction WHERE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction WHERE États électroniques (ER).
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
ms.openlocfilehash: ca218f87eb1f9235ab475809fbbdfecf3fe0c7fb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566040"
---
# <a name="where-er-function"></a><span data-ttu-id="6f9d6-103">Fonction WHERE ER</span><span class="sxs-lookup"><span data-stu-id="6f9d6-103">WHERE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6f9d6-104">La fonction `WHERE` renvoie la liste spécifiée sous la forme d’une *Liste des enregistrements* après avoir été filtrée selon la condition spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6f9d6-104">The `WHERE` function returns the specified list as a *Record list* value after it has been filtered according to the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="6f9d6-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6f9d6-105">Syntax</span></span>

```vb
WHERE (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="6f9d6-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="6f9d6-106">Arguments</span></span>

<span data-ttu-id="6f9d6-107">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="6f9d6-107">`list`: *Record list*</span></span>

<span data-ttu-id="6f9d6-108">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="6f9d6-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="6f9d6-109">`condition` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="6f9d6-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="6f9d6-110">Expression conditionnelle valide utilisée pour filtrer les enregistrements de la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6f9d6-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="6f9d6-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="6f9d6-111">Return values</span></span>

<span data-ttu-id="6f9d6-112">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="6f9d6-112">*Record list*</span></span>

<span data-ttu-id="6f9d6-113">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="6f9d6-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6f9d6-114">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="6f9d6-114">Usage notes</span></span>

<span data-ttu-id="6f9d6-115">Cette fonction diffère de la fonction [FILTER](er-functions-list-filter.md), car la condition spécifiée est appliquée à toute source de données États électroniques (ER) du type *Liste des enregistrements* présent dans la mémoire.</span><span class="sxs-lookup"><span data-stu-id="6f9d6-115">This function differs from the [FILTER](er-functions-list-filter.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="6f9d6-116">Si les arguments configurés pour cette fonction (`list` et `condition`) ne permettent pas de traduire cette demande en appel SQL direct, un message d’avertissement est levé au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="6f9d6-116">If the arguments that are configured for this function (`list` and `condition`) allow this request to be translated to the direct SQL call, a warning message is thrown at design time.</span></span> <span data-ttu-id="6f9d6-117">Ce message informe l’utilisateur que les performances peuvent être améliorées si la fonction [FILTER](er-functions-list-filter.md) est utilisée au lieu de `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="6f9d6-117">This message informs the user that performance might be improved if the [FILTER](er-functions-list-filter.md) function is used instead of `WHERE`.</span></span>

## <a name="example-1"></a><span data-ttu-id="6f9d6-118">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="6f9d6-118">Example 1</span></span>

<span data-ttu-id="6f9d6-119">Si **Fournisseur** est configuré comme source de données ER qui fait référence à la table VendTable, l’expression `WHERE (Vendors, Vendors.VendGroup = "40")` renvoie la liste des fournisseurs faisant partie uniquement du groupe de fournisseurs 40.</span><span class="sxs-lookup"><span data-stu-id="6f9d6-119">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `WHERE (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="6f9d6-120">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="6f9d6-120">Example 2</span></span>

<span data-ttu-id="6f9d6-121">Si vous entrez la source de données **DS** de type *Champ calculé*, et qu’elle contient l’expression `SPLIT ("A|B|C", "|")`, l’expression `WHERE( DS, DS.Value = "B")` retourne une liste d’une seul enregistrement qui contient le texte **« B »** dans le champ **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="6f9d6-121">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `WHERE( DS, DS.Value = "B")` returns a list of only one record that contains the text **"B"** in the **Value** field.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f9d6-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6f9d6-122">Additional resources</span></span>

[<span data-ttu-id="6f9d6-123">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="6f9d6-123">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]