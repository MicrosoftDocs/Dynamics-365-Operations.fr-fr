---
title: Fonction SPLITLISTBYLIMIT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction SPLITLISTBYLIMIT États électroniques (ER).
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
ms.openlocfilehash: 5bf13b7c1e7cab7c803b352370084421a8180dee
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743426"
---
# <a name="splitlistbylimit-er-function"></a><span data-ttu-id="2ad27-103">Fonction SPLITLISTBYLIMIT ER</span><span class="sxs-lookup"><span data-stu-id="2ad27-103">SPLITLISTBYLIMIT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ad27-104">La fonction `SPLITLISTBYLIMIT` fractionne la liste spécifiée en une nouvelle liste de sous-listes (lots).</span><span class="sxs-lookup"><span data-stu-id="2ad27-104">The `SPLITLISTBYLIMIT` function splits the specified list into a new list of sublists (batches).</span></span> <span data-ttu-id="2ad27-105">Le nombre d’enregistrements dans chaque lot est calculé dynamiquement.</span><span class="sxs-lookup"><span data-stu-id="2ad27-105">The number of records in each batch is dynamically calculated.</span></span> <span data-ttu-id="2ad27-106">La fonction renvoie ensuite le résultat en tant que nouvelle valeur de *Liste des enregistrements* constituée des lots.</span><span class="sxs-lookup"><span data-stu-id="2ad27-106">The function then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="2ad27-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2ad27-107">Syntax</span></span>

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a><span data-ttu-id="2ad27-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="2ad27-108">Arguments</span></span>

<span data-ttu-id="2ad27-109">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="2ad27-109">`list`: *Record list*</span></span>

<span data-ttu-id="2ad27-110">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="2ad27-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="2ad27-111">`limit value` : *Entier* ou *Réel*</span><span class="sxs-lookup"><span data-stu-id="2ad27-111">`limit value`: *Integer* or *Real*</span></span>

<span data-ttu-id="2ad27-112">Valeur maximale de la limite utilisée pour fractionner la liste d’origine en lots.</span><span class="sxs-lookup"><span data-stu-id="2ad27-112">The maximum value of the limit that is used to split the original list into batches.</span></span>

<span data-ttu-id="2ad27-113">`limit source` : *Champ*</span><span class="sxs-lookup"><span data-stu-id="2ad27-113">`limit source`: *Field*</span></span>

<span data-ttu-id="2ad27-114">Chemin d’accès valide d’un champ de type *Entier* ou *Réel* dans la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="2ad27-114">The valid path of a field of the *Integer* or *Real* type in the specified list.</span></span> <span data-ttu-id="2ad27-115">La valeur de ce champ définit l’étape à laquelle la somme totale est augmentée.</span><span class="sxs-lookup"><span data-stu-id="2ad27-115">The value of this field defines the step that the total sum is increased on.</span></span>

## <a name="return-values"></a><span data-ttu-id="2ad27-116">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="2ad27-116">Return values</span></span>

<span data-ttu-id="2ad27-117">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="2ad27-117">*Record list*</span></span>

<span data-ttu-id="2ad27-118">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="2ad27-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2ad27-119">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="2ad27-119">Usage notes</span></span>

<span data-ttu-id="2ad27-120">La liste des traitements par lots renvoyée contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2ad27-120">The list of batches that is returned contains the following elements:</span></span>

- <span data-ttu-id="2ad27-121">**Valeur** : *liste*</span><span class="sxs-lookup"><span data-stu-id="2ad27-121">**Value**: *List*</span></span>

    <span data-ttu-id="2ad27-122">Liste des enregistrements qui appartiennent au lot en cours.</span><span class="sxs-lookup"><span data-stu-id="2ad27-122">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="2ad27-123">**Numéro de lot** : *Entier*</span><span class="sxs-lookup"><span data-stu-id="2ad27-123">**BatchNumber**: *Integer*</span></span>

    <span data-ttu-id="2ad27-124">Numéro du lot actuel dans la liste renvoyée.</span><span class="sxs-lookup"><span data-stu-id="2ad27-124">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="2ad27-125">La limite n’est pas appliquée à un article unique de la liste d’origine si la source de limite dépasse la limite définie.</span><span class="sxs-lookup"><span data-stu-id="2ad27-125">The limit isn't applied to a single item of the original list if the limit source exceeds the defined limit.</span></span>

## <a name="example"></a><span data-ttu-id="2ad27-126">Exemple</span><span class="sxs-lookup"><span data-stu-id="2ad27-126">Example</span></span>

<span data-ttu-id="2ad27-127">L’illustration suivante présente un format d’états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="2ad27-127">The following illustration shows an Electronic reporting (ER) format.</span></span>

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

<span data-ttu-id="2ad27-128">L’illustration suivante présente les sources de données utilisées pour le format.</span><span class="sxs-lookup"><span data-stu-id="2ad27-128">The following illustration shows the data sources that are used for the format.</span></span>

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

<span data-ttu-id="2ad27-129">L’illustration suivante présente le résultat de l’exécution du format.</span><span class="sxs-lookup"><span data-stu-id="2ad27-129">The following illustration shows the result when the format is run.</span></span> <span data-ttu-id="2ad27-130">Dans ce cas, la sortie est une liste plate des articles de marchandise.</span><span class="sxs-lookup"><span data-stu-id="2ad27-130">In this case, the output is a flat list of commodity items.</span></span>

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

<span data-ttu-id="2ad27-131">Dans les illustrations suivantes, le même format a été ajusté de manière à présenter la liste des articles de marchandise par lots lorsqu’un seul lot doit inclure des marchandises et le poids total ne doit pas dépasser une limite de 9.</span><span class="sxs-lookup"><span data-stu-id="2ad27-131">In the following illustrations, the same format has been adjusted so that it presents the list of commodity items in batches if a single batch must include commodities and the total weight should not exceed a limit of 9.</span></span>

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

<span data-ttu-id="2ad27-132">L’illustration suivante présente le résultat de l’exécution du format ajusté.</span><span class="sxs-lookup"><span data-stu-id="2ad27-132">The following illustration shows the result when the adjusted format is run.</span></span>

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> <span data-ttu-id="2ad27-133">La limite n’est pas appliquée au dernier article de la liste d’origine, car la valeur (**11**) de la source de sa limite (**poids**) dépasse la limite définie (**9**).</span><span class="sxs-lookup"><span data-stu-id="2ad27-133">The limit isn't applied to the last item of the original list, because the value (**11**) of the limit source (**weight**) exceeds the defined limit (**9**).</span></span> <span data-ttu-id="2ad27-134">Pour ignorer les sous-listes lors de la génération d’états, utilisez la fonction `WHERE` ou l’expression **Activé** de l’élément de format correspondant, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2ad27-134">To ignore sublists during report generation, use either the `WHERE` function or the **Enabled** expression of the corresponding format element, as you require.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2ad27-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2ad27-135">Additional resources</span></span>

[<span data-ttu-id="2ad27-136">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="2ad27-136">List functions</span></span>](er-functions-category-list.md)
