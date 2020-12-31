---
title: Fonction ALLITEMSQUERY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ALLITEMSQUERY États électroniques (ER).
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
ms.openlocfilehash: ed21252fbbe3d4adad106625062e10e3de712bb0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687742"
---
# <a name="allitemsquery-er-function"></a><span data-ttu-id="44f6f-103">Fonction ALLITEMSQUERY ER</span><span class="sxs-lookup"><span data-stu-id="44f6f-103">ALLITEMSQUERY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="44f6f-104">La fonction `ALLITEMSQUERY` s’exécute en tant que requête SQL jointe.</span><span class="sxs-lookup"><span data-stu-id="44f6f-104">The `ALLITEMSQUERY` function runs as a joined SQL query.</span></span> <span data-ttu-id="44f6f-105">Elle renvoie une nouvelle valeur de *Liste des enregistrements* aplatie qui consiste en une liste d’enregistrements qui représente tous les éléments qui correspondent au chemin spécifié.</span><span class="sxs-lookup"><span data-stu-id="44f6f-105">It returns a new flattened *Record list* value that consists of a list of records that represent all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="44f6f-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="44f6f-106">Syntax</span></span>

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a><span data-ttu-id="44f6f-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="44f6f-107">Arguments</span></span>

<span data-ttu-id="44f6f-108">`path` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="44f6f-108">`path`: *Record list*</span></span>

<span data-ttu-id="44f6f-109">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="44f6f-109">The valid path of a data source of the *Record list* data type.</span></span> <span data-ttu-id="44f6f-110">Il doit contenir au moins une relation.</span><span class="sxs-lookup"><span data-stu-id="44f6f-110">It must contain at least one relation.</span></span>

## <a name="return-values"></a><span data-ttu-id="44f6f-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="44f6f-111">Return values</span></span>

<span data-ttu-id="44f6f-112">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="44f6f-112">*Record list*</span></span>

<span data-ttu-id="44f6f-113">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="44f6f-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="44f6f-114">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="44f6f-114">Usage notes</span></span>

<span data-ttu-id="44f6f-115">Le chemin spécifié doit être défini comme le chemin d’accès valide de la source de données vers un élément de source de données d’un type de données de *Liste des enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="44f6f-115">The specified path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="44f6f-116">Il doit également contenir au moins une relation.</span><span class="sxs-lookup"><span data-stu-id="44f6f-116">It must also contain at least one relation.</span></span> <span data-ttu-id="44f6f-117">Les éléments de données tels que la *Chaîne* de chemin d’accès et la *Date* doivent déclencher une erreur dans le générateur d’expression États électroniques ER au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="44f6f-117">Data elements such as the path *String* and *Date* should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="44f6f-118">Lorsque cette fonction est appliquée aux sources de données du type de données *Liste des enregistrements* qui fait référence à un objet d’application qui peut être appelé directement à l’aide de SQL (par exemple, une table, une entité ou une requête), il s’exécute en tant que requête SQL jointe.</span><span class="sxs-lookup"><span data-stu-id="44f6f-118">When this function is applied to data sources of the *Record list* data type that refer to an application object that can be directly called by using SQL (for example, an table, entity, or query), it runs as a joined SQL query.</span></span> <span data-ttu-id="44f6f-119">Sinon, il s’exécute en mémoire en tant que fonction [ALLITEMS](er-functions-list-allitems.md).</span><span class="sxs-lookup"><span data-stu-id="44f6f-119">Otherwise, it runs in memory as the [ALLITEMS](er-functions-list-allitems.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="44f6f-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="44f6f-120">Example</span></span>

<span data-ttu-id="44f6f-121">Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :</span><span class="sxs-lookup"><span data-stu-id="44f6f-121">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="44f6f-122">Source de données **CustInv** de type *Enregistrements de la table* qui fait référence à la table CustInvoiceTable</span><span class="sxs-lookup"><span data-stu-id="44f6f-122">A **CustInv** data source of the *Table records* type that refers to the CustInvoiceTable table</span></span>
- <span data-ttu-id="44f6f-123">Source de données **FilteredInv** du type *Champ calculé* qui contient l’expression `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span><span class="sxs-lookup"><span data-stu-id="44f6f-123">A **FilteredInv** data source of the *Calculated field* type that contains the expression `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span></span>
- <span data-ttu-id="44f6f-124">**JourLines** du type *Champ calculé* qui contient l’expression `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span><span class="sxs-lookup"><span data-stu-id="44f6f-124">A **JourLines** of the *Calculated field* type that contains the expression `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span></span>

<span data-ttu-id="44f6f-125">Lorsque vous exécutez la mise en correspondance des modèles pour appeler la source de données **JourLines**, l’instruction SQL suivante est exécutée :</span><span class="sxs-lookup"><span data-stu-id="44f6f-125">When you run the model mapping to call the **JourLines** data source, the following SQL statement is run:</span></span>

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a><span data-ttu-id="44f6f-126">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="44f6f-126">Additional resources</span></span>

[<span data-ttu-id="44f6f-127">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="44f6f-127">List functions</span></span>](er-functions-category-list.md)
