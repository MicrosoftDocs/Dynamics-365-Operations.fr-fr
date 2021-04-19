---
title: Fonction SPLITLIST ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction SPLITLIST États électroniques (ER).
author: NickSelin
ms.date: 03/15/2021
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
ms.openlocfilehash: 99e199e238b3132622a8b305895637b430e8f6d2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745567"
---
# <a name="splitlist-er-function"></a><span data-ttu-id="95df2-103">Fonction SPLITLIST ER</span><span class="sxs-lookup"><span data-stu-id="95df2-103">SPLITLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95df2-104">La fonction `SPLITLIST` fractionne la liste spécifiée en sous-listes (ou lots), dont chacun contient le nombre d’enregistrements spécifié.</span><span class="sxs-lookup"><span data-stu-id="95df2-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="95df2-105">Elle renvoie ensuite le résultat en tant que nouvelle valeur de *Liste des enregistrements* constituée des lots.</span><span class="sxs-lookup"><span data-stu-id="95df2-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="95df2-106">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="95df2-106">Syntax 1</span></span>

```vb
SPLITLIST (list, number)
```

## <a name="syntax-2"></a><span data-ttu-id="95df2-107">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="95df2-107">Syntax 2</span></span>

```vb
SPLITLIST (list, number, on-demand reading flag)
```

## <a name="arguments"></a><span data-ttu-id="95df2-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="95df2-108">Arguments</span></span>

<span data-ttu-id="95df2-109">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="95df2-109">`list`: *Record list*</span></span>

<span data-ttu-id="95df2-110">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="95df2-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="95df2-111">`number` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="95df2-111">`number`: *Integer*</span></span>

<span data-ttu-id="95df2-112">Nombre maximal d’enregistrements par lot.</span><span class="sxs-lookup"><span data-stu-id="95df2-112">The maximum number of records per batch.</span></span>

<span data-ttu-id="95df2-113">`on-demand reading flag` : *Booléen*</span><span class="sxs-lookup"><span data-stu-id="95df2-113">`on-demand reading flag`: *Boolean*</span></span>

<span data-ttu-id="95df2-114">Une valeur *Booléenne* qui spécifie si les éléments des sous-listes doivent être générés à la demande.</span><span class="sxs-lookup"><span data-stu-id="95df2-114">A *Boolean* value that specifies whether elements of sublists should be generated on demand.</span></span>

## <a name="return-values"></a><span data-ttu-id="95df2-115">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="95df2-115">Return values</span></span>

<span data-ttu-id="95df2-116">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="95df2-116">*Record list*</span></span>

<span data-ttu-id="95df2-117">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="95df2-117">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="95df2-118">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="95df2-118">Usage notes</span></span>

<span data-ttu-id="95df2-119">La liste des traitements par lots renvoyée contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="95df2-119">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="95df2-120">**Valeur :** *liste*</span><span class="sxs-lookup"><span data-stu-id="95df2-120">**Value:** *List*</span></span>

    <span data-ttu-id="95df2-121">Liste des enregistrements qui appartiennent au lot en cours.</span><span class="sxs-lookup"><span data-stu-id="95df2-121">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="95df2-122">**Numéro de lot :** *Entier*</span><span class="sxs-lookup"><span data-stu-id="95df2-122">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="95df2-123">Numéro du lot actuel dans la liste renvoyée.</span><span class="sxs-lookup"><span data-stu-id="95df2-123">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="95df2-124">Lorsque l’indicateur de lecture à la demande est défini sur **True**, les sous-listes sont générées sur demande, ce qui permet de réduire la consommation de mémoire mais peut entraîner une dégradation des performances si les éléments ne sont pas utilisés séquentiellement.</span><span class="sxs-lookup"><span data-stu-id="95df2-124">When the on-demand reading flag is set to **True**, sublists are generated upon request which allows for a reduction in memory consumption but may cause performance degradation if elements aren't used sequentially.</span></span>

## <a name="example"></a><span data-ttu-id="95df2-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="95df2-125">Example</span></span>

<span data-ttu-id="95df2-126">Dans l’illustration suivante, une source de données **Lignes** est créée sous la forme d’une liste avec trois enregistrements.</span><span class="sxs-lookup"><span data-stu-id="95df2-126">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="95df2-127">Cette liste est divisée en lots, dont chacun contient jusqu’à deux enregistrements.</span><span class="sxs-lookup"><span data-stu-id="95df2-127">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="95df2-128">L’illustration suivante présente la structure de format conçue.</span><span class="sxs-lookup"><span data-stu-id="95df2-128">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="95df2-129">Dans cette structure de format, les liaisons à la source de données **Lignes** sont créées pour générer une sortie au format XML.</span><span class="sxs-lookup"><span data-stu-id="95df2-129">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="95df2-130">Cette sortie répertorie les nœuds individuels de chaque lot et les enregistrements qu’il contient.</span><span class="sxs-lookup"><span data-stu-id="95df2-130">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="95df2-131">L’illustration suivante présente le résultat de l’exécution du format conçu.</span><span class="sxs-lookup"><span data-stu-id="95df2-131">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="95df2-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="95df2-132">Additional resources</span></span>

[<span data-ttu-id="95df2-133">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="95df2-133">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
