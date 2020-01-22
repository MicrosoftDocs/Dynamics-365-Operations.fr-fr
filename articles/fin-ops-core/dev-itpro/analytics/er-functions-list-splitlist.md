---
title: Fonction SPLITLIST ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction SPLITLIST États électroniques (ER).
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
ms.openlocfilehash: b324d42a53b35074ba62ccf3df7b77cb4db70450
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917210"
---
# <span data-ttu-id="a558b-103"><a name="SPLITLIST">Fonction SPLITLIST ER</a></span><span class="sxs-lookup"><span data-stu-id="a558b-103"><a name="SPLITLIST">SPLITLIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a558b-104">La fonction `SPLITLIST` fractionne la liste spécifiée en sous-listes (ou lots), dont chacun contient le nombre d'enregistrements spécifié.</span><span class="sxs-lookup"><span data-stu-id="a558b-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="a558b-105">Elle renvoie ensuite le résultat en tant que nouvelle valeur de *Liste des enregistrements* constituée des lots.</span><span class="sxs-lookup"><span data-stu-id="a558b-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="a558b-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a558b-106">Syntax</span></span>

```
SPLITLIST (list, number)
```

## <a name="arguments"></a><span data-ttu-id="a558b-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="a558b-107">Arguments</span></span>

<span data-ttu-id="a558b-108">`list` : *Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="a558b-108">`list`: *Record list*</span></span>

<span data-ttu-id="a558b-109">Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="a558b-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="a558b-110">`number` : *Entier*</span><span class="sxs-lookup"><span data-stu-id="a558b-110">`number`: *Integer*</span></span>

<span data-ttu-id="a558b-111">Nombre maximal d'enregistrements par lot.</span><span class="sxs-lookup"><span data-stu-id="a558b-111">The maximum number of records per batch.</span></span>

## <a name="return-values"></a><span data-ttu-id="a558b-112">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="a558b-112">Return values</span></span>

<span data-ttu-id="a558b-113">*Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="a558b-113">*Record list*</span></span>

<span data-ttu-id="a558b-114">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="a558b-114">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a558b-115">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="a558b-115">Usage notes</span></span>

<span data-ttu-id="a558b-116">La liste des traitements par lots renvoyée contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a558b-116">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="a558b-117">**Valeur :** *liste*</span><span class="sxs-lookup"><span data-stu-id="a558b-117">**Value:** *List*</span></span>

    <span data-ttu-id="a558b-118">Liste des enregistrements qui appartiennent au lot en cours.</span><span class="sxs-lookup"><span data-stu-id="a558b-118">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="a558b-119">**Numéro de lot :** *Entier*</span><span class="sxs-lookup"><span data-stu-id="a558b-119">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="a558b-120">Numéro du lot actuel dans la liste renvoyée.</span><span class="sxs-lookup"><span data-stu-id="a558b-120">The number of the current batch in the returned list.</span></span>

## <a name="example"></a><span data-ttu-id="a558b-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="a558b-121">Example</span></span>

<span data-ttu-id="a558b-122">Dans l'illustration suivante, une source de données **Lignes** est créée sous la forme d'une liste avec trois enregistrements.</span><span class="sxs-lookup"><span data-stu-id="a558b-122">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="a558b-123">Cette liste est divisée en lots, dont chacun contient jusqu'à deux enregistrements.</span><span class="sxs-lookup"><span data-stu-id="a558b-123">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="a558b-124">L'illustration suivante présente la structure de format conçue.</span><span class="sxs-lookup"><span data-stu-id="a558b-124">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="a558b-125">Dans cette structure de format, les liaisons à la source de données **Lignes** sont créées pour générer une sortie au format XML.</span><span class="sxs-lookup"><span data-stu-id="a558b-125">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="a558b-126">Cette sortie répertorie les nœuds individuels de chaque lot et les enregistrements qu'il contient.</span><span class="sxs-lookup"><span data-stu-id="a558b-126">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="a558b-127">L'illustration suivante présente le résultat de l'exécution du format conçu.</span><span class="sxs-lookup"><span data-stu-id="a558b-127">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="a558b-128">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a558b-128">Additional resources</span></span>

[<span data-ttu-id="a558b-129">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="a558b-129">List functions</span></span>](er-functions-category-list.md)
