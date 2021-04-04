---
title: Fonction FILTER ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction FILTER États électroniques (ER).
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
ms.openlocfilehash: 0e90db1836a93dab42be5dc91e9ea478163a1437
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559697"
---
# <a name="filter-er-function"></a><span data-ttu-id="db0e1-103">Fonction FILTER ER</span><span class="sxs-lookup"><span data-stu-id="db0e1-103">FILTER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="db0e1-104">La fonction `FILTER` renvoie la liste spécifiée sous la forme d’une valeur de *Liste des enregistrements* après que la requête a été modifiée afin qu’elle filtre pour la condition spécifiée.</span><span class="sxs-lookup"><span data-stu-id="db0e1-104">The `FILTER` function returns the specified list as a *Record list* value after the query has been changed so that it filters for the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="db0e1-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="db0e1-105">Syntax</span></span>

```vb
FILTER (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="db0e1-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="db0e1-106">Arguments</span></span>

<span data-ttu-id="db0e1-107">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="db0e1-107">`list`: *Record list*</span></span>

<span data-ttu-id="db0e1-108">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="db0e1-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="db0e1-109">`condition` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="db0e1-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="db0e1-110">Expression conditionnelle valide utilisée pour filtrer les enregistrements de la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="db0e1-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="db0e1-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="db0e1-111">Return values</span></span>

<span data-ttu-id="db0e1-112">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="db0e1-112">*Record list*</span></span>

<span data-ttu-id="db0e1-113">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="db0e1-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="db0e1-114">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="db0e1-114">Usage notes</span></span>

<span data-ttu-id="db0e1-115">Cette fonction diffère de la fonction [WHERE](er-functions-list-where.md), car la condition spécifiée est appliquée à toute source de données États électroniques (ER) du type *Enregistrements de table* au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="db0e1-115">This function differs from the [WHERE](er-functions-list-where.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Table records* type at the database level.</span></span> <span data-ttu-id="db0e1-116">La liste et la condition peuvent être définies à l’aide de tables et de relations.</span><span class="sxs-lookup"><span data-stu-id="db0e1-116">The list and condition can be defined by using tables and relations.</span></span>

<span data-ttu-id="db0e1-117">Si l’un ou les deux arguments configurés pour cette fonction (`list` et `condition`) ne permettent pas de traduire cette demande en appel SQL direct, une exception est levée au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="db0e1-117">If one or both arguments that are configured for this function (`list` and `condition`) don't allow this request to be translated to the direct SQL call, an exception is thrown at design time.</span></span> <span data-ttu-id="db0e1-118">Cette exception informe l’utilisateur que `list` ou `condition` ne peut pas être utilisé pour interroger la base de données.</span><span class="sxs-lookup"><span data-stu-id="db0e1-118">This exception informs the user that either `list` or `condition` can't be used to query the database.</span></span>

## <a name="example-1"></a><span data-ttu-id="db0e1-119">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="db0e1-119">Example 1</span></span>

<span data-ttu-id="db0e1-120">Si **Fournisseur** est configuré comme source de données ER qui fait référence à la table VendTable, l’expression `FILTER (Vendors, Vendors.VendGroup = "40")` renvoie la liste des fournisseurs faisant partie uniquement du groupe de fournisseurs 40.</span><span class="sxs-lookup"><span data-stu-id="db0e1-120">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `FILTER (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="db0e1-121">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="db0e1-121">Example 2</span></span>

<span data-ttu-id="db0e1-122">Si **Fournisseur** est configuré comme source de données ER qui fait référence à la table VendTable et si **parmVendorBankGroup** est configuré comme source de données ER qui renvoie une valeur du type de données *Chaîne*, `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` renvoie la liste des comptes fournisseurs appartenant uniquement à un groupe bancaire spécifique.</span><span class="sxs-lookup"><span data-stu-id="db0e1-122">If **Vendor** is configured as an ER data source that refers to the VendTable table, and if **parmVendorBankGroup** is configured as an ER data source that returns a value of the *String* data type, the expression `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` returns a list of only vendor accounts that belong to a specific bank group.</span></span>

## <a name="example-3"></a><span data-ttu-id="db0e1-123">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="db0e1-123">Example 3</span></span>

<span data-ttu-id="db0e1-124">Vous entrez une source de données **DS** du type *Champ calculé* et elle contient l’expression `SPLIT ("A,B,C", ",")`.</span><span class="sxs-lookup"><span data-stu-id="db0e1-124">You enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A,B,C", ",")`.</span></span> <span data-ttu-id="db0e1-125">Vous entrez ensuite une autre expression, `FILTER( DS, DS.Value = "B")`.</span><span class="sxs-lookup"><span data-stu-id="db0e1-125">You then enter another expression, `FILTER( DS, DS.Value = "B")`.</span></span> <span data-ttu-id="db0e1-126">Lorsque vous essayez d’enregistrer cette expression dans le concepteur de formule ER, l’exception suivante est levée : « Erreur de validation : l’expression de liste de la fonction FILTER n’est pas interrogeable. »</span><span class="sxs-lookup"><span data-stu-id="db0e1-126">When you try to save this expression in the ER formula designer, the following exception is thrown: "Validation error: The list expression of FILTER function is not queryable."</span></span>

## <a name="additional-resources"></a><span data-ttu-id="db0e1-127">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="db0e1-127">Additional resources</span></span>

[<span data-ttu-id="db0e1-128">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="db0e1-128">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]