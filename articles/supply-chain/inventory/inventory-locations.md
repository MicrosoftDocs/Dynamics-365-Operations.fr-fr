---
title: Emplacement de stockage
description: "Les emplacements de stockage sont utilisés avec l'entreposage de base (WMS I) pour déterminer où les articles sont enregistrés et où les articles sont prélevés dans un entrepôt WMS I."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSLocation
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 225735f6776281fdf2185de1f7d1c73f50e125b1
ms.contentlocale: fr-fr
ms.lasthandoff: 01/17/2018

---

# <a name="inventory-locations"></a><span data-ttu-id="56e55-103">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="56e55-103">Inventory locations</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="56e55-104">Les emplacements de stockage sont utilisés avec l'entreposage de base (WMS I) pour déterminer où les articles sont enregistrés et où les articles sont prélevés dans un entrepôt WMS I.</span><span class="sxs-lookup"><span data-stu-id="56e55-104">Inventory locations are used with basic warehousing (WMS I) to determine where items are stored and where items are picked from in a WMS I warehouse.</span></span>

<span data-ttu-id="56e55-105">Cette rubrique s'applique aux fonctionnalités du module Gestion des stocks.</span><span class="sxs-lookup"><span data-stu-id="56e55-105">This topic applies to features in the Inventory management module.</span></span> <span data-ttu-id="56e55-106">Elle ne s'applique pas aux fonctionnalités du module Gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="56e55-106">It does not apply to features in the Warehouse management module.</span></span>

<span data-ttu-id="56e55-107">Le terme emplacement fait référence au lieu de stockage et d'extraction des articles.</span><span class="sxs-lookup"><span data-stu-id="56e55-107">The term location refers to the place that items are stored and drawn from.</span></span>

<span data-ttu-id="56e55-108">Pour chaque emplacement, vous pouvez également spécifier le lieu d'insertion de l'article.</span><span class="sxs-lookup"><span data-stu-id="56e55-108">For each location, the place where the item is inserted can also be specified.</span></span> <span data-ttu-id="56e55-109">Par défaut, ces lieux sont identiques.</span><span class="sxs-lookup"><span data-stu-id="56e55-109">By default, they are the same.</span></span> <span data-ttu-id="56e55-110">Généralement, les articles sont insérés et extraits du même côté d'un emplacement mais ce n'est pas toujours le cas.</span><span class="sxs-lookup"><span data-stu-id="56e55-110">Items are usually inserted and drawn from the same side of a location, but not always.</span></span> <span data-ttu-id="56e55-111">Par exemple, les articles stockés dans des casiers à accumulation dynamique sont insérés depuis une allée et extraits depuis une autre.</span><span class="sxs-lookup"><span data-stu-id="56e55-111">For example, items that are stored in live storage racks are inserted from one aisle and drawn from another.</span></span> <span data-ttu-id="56e55-112">La donnée principale est le nom de l'emplacement qui est généralement déterminé par ses coordonnées : entrepôt, allée, rayon, étagère et casier.</span><span class="sxs-lookup"><span data-stu-id="56e55-112">The main input is given by a location name, which is usually determined by its coordinates: warehouse, aisle, rack, shelf, and bin.</span></span> <span data-ttu-id="56e55-113">Ce nom ou cet ID peut être entré manuellement ou généré à partir des coordonnées de l'emplacement (par exemple, 01-02-03-4 pour allée 1, rayon 2, étagère 3, casier 4) dans la page Emplacements de stockage.</span><span class="sxs-lookup"><span data-stu-id="56e55-113">This name or ID can be entered manually or generated from the location coordinates—for example, 01-02-03-4 for aisle 1, rack 2, shelf 3, bin 4 in the Inventory locations page.</span></span>
<span data-ttu-id="56e55-114">Propriétés de l'emplacement</span><span class="sxs-lookup"><span data-stu-id="56e55-114">Location properties</span></span>

<span data-ttu-id="56e55-115">Un emplacement possède les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="56e55-115">A location has the following characteristics:</span></span>
-   <span data-ttu-id="56e55-116">Taille (hauteur, largeur, profondeur et, par conséquent, volume)</span><span class="sxs-lookup"><span data-stu-id="56e55-116">Size (height, width, depth, and thereby volume)</span></span>
-   <span data-ttu-id="56e55-117">Position de l'entrepôt, de l'allée, du rayon, de l'étagère et du casier.</span><span class="sxs-lookup"><span data-stu-id="56e55-117">Warehouse, aisle, rack, shelf, and bin position</span></span>
-   <span data-ttu-id="56e55-118">Type d'emplacement (emplacement de stockage en gros, emplacement de prélèvement, quai d'embarquement, quai de débarquement, emplacement d'entrée en production, emplacement d'inspection ou supermarché kanban)</span><span class="sxs-lookup"><span data-stu-id="56e55-118">Location type (bulk location, picking location, inbound dock, outbound dock, production input location, inspection location, or kanban supermarket)</span></span>

<span data-ttu-id="56e55-119">Un libellé de contrôle peut être utilisé dans les systèmes en ligne pour vérifier que l'opérateur a bien sélectionné le bon emplacement pour un article spécifique.</span><span class="sxs-lookup"><span data-stu-id="56e55-119">Check text can be used in online systems to verify that the operator has selected the correct location for a specific item.</span></span> <span data-ttu-id="56e55-120">Ce libellé de contrôle peut être créé manuellement ou par défaut.</span><span class="sxs-lookup"><span data-stu-id="56e55-120">This check text can be created manually or by default.</span></span>

## <a name="sort-codes"></a><span data-ttu-id="56e55-121">Priorités</span><span class="sxs-lookup"><span data-stu-id="56e55-121">Sort codes</span></span>
<span data-ttu-id="56e55-122">Les priorités permettent d'optimiser la gestion des lignes de prélèvement, qui décrivent les informations requises pour le prélèvement des articles du stock, notamment l'ordre de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="56e55-122">Use sort codes to optimize the handling of picking lines, which describe the information that is required for picking items from inventory, including the picking order.</span></span> <span data-ttu-id="56e55-123">Les priorités peuvent être spécifiées par l'aile ou d'autres coordonnées ou attribuées manuellement pour l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="56e55-123">Sort codes can be specified by the aisle and other coordinates, or assigned manually for the location.</span></span>

## <a name="blocked-locations"></a><span data-ttu-id="56e55-124">Emplacements bloqués</span><span class="sxs-lookup"><span data-stu-id="56e55-124">Blocked locations</span></span>
<span data-ttu-id="56e55-125">Vous souhaitez parfois indiquer qu'un emplacement est bloqué pour une période donnée, par exemple, pour permettre des réparations.</span><span class="sxs-lookup"><span data-stu-id="56e55-125">Occasionally, you might want to indicate that a location is blocked for a period of time, for example, to allow for repairs.</span></span> <span data-ttu-id="56e55-126">Ou bien, vous pouvez indiquer que seule l'entrée ou la sortie est bloquée.</span><span class="sxs-lookup"><span data-stu-id="56e55-126">At other times, you may want to indicate blocking of only the input or only output.</span></span>

## <a name="tree-structure"></a><span data-ttu-id="56e55-127">Structure arborescente</span><span class="sxs-lookup"><span data-stu-id="56e55-127">Tree structure</span></span>

<span data-ttu-id="56e55-128">Dans la page Emplacements de stockage, vous pouvez afficher la disposition d'entrepôt dans une structure arborescente basée sur les coordonnées des emplacements de stockage, dans un format d'affichage défini.</span><span class="sxs-lookup"><span data-stu-id="56e55-128">In the Inventory locations page, you can view the warehouse layout in a tree structure based on the coordinates of inventory locations, in a defined display format.</span></span>

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a><span data-ttu-id="56e55-129">Tenir à jour les emplacements de stockage via l'écran Entrepôt</span><span class="sxs-lookup"><span data-stu-id="56e55-129">Maintain inventory locations via the warehouse form</span></span>

<span data-ttu-id="56e55-130">Il est possible de copier des emplacements d'un entrepôt à un autre et de créer des emplacements via un assistant.</span><span class="sxs-lookup"><span data-stu-id="56e55-130">It is possible to copy locations from one warehouse to another and to create locations via a wizard.</span></span> <span data-ttu-id="56e55-131">Avant d'exécuter l'assistant, vous devez veiller à définir les noms d'emplacement par défaut dans la page Entrepôt.</span><span class="sxs-lookup"><span data-stu-id="56e55-131">Before you run the wizard you should make sure that you have defined the default location names on the Warehouse page.</span></span>



<a name="see-also"></a><span data-ttu-id="56e55-132">Voir également :</span><span class="sxs-lookup"><span data-stu-id="56e55-132">See also</span></span>
--------

[<span data-ttu-id="56e55-133">Créer une structure d'entrepôt (guide de tâche)</span><span class="sxs-lookup"><span data-stu-id="56e55-133">Create a new warehouse layout (Task guide)</span></span>](tasks/create-new-warehouse-layout.md)

