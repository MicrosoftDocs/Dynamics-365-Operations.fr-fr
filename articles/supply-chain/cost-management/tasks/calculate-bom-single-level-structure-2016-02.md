--- 
title: "Calculer une nomenclature à l'aide d'une structure à un seul niveau (février 2016 uniquement)"
description: "Cette procédure montre comment calculer le coût d'un produit fini à l'aide d'un éclatement à un seul niveau basé sur la feuille de coûts."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3a318b2308f8cd5c3650a392aed53185df6f81dc
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016-only"></a><span data-ttu-id="a48cd-103">Calculer une nomenclature à l'aide d'une structure à un seul niveau (février 2016 uniquement)</span><span class="sxs-lookup"><span data-stu-id="a48cd-103">Calculate a BOM by using a single level structure (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a48cd-104">Cette procédure montre comment calculer le coût d'un produit fini à l'aide d'un éclatement à un seul niveau basé sur la feuille de coûts.</span><span class="sxs-lookup"><span data-stu-id="a48cd-104">This procedure shows how to calculate the cost of a finished product by using single level explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="a48cd-105">Il s'agit de la sixième tâche de la série de calculs des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="a48cd-105">This is the sixth task in the BOM calculation series.</span></span> <span data-ttu-id="a48cd-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="a48cd-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="a48cd-107">Allez dans Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="a48cd-107">Go to Released products.</span></span>
2. <span data-ttu-id="a48cd-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a48cd-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a48cd-109">Sélectionnez le produit BOM_1.</span><span class="sxs-lookup"><span data-stu-id="a48cd-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="a48cd-110">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="a48cd-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="a48cd-111">Cliquez sur Prix de l'article.</span><span class="sxs-lookup"><span data-stu-id="a48cd-111">Click Item price.</span></span>
5. <span data-ttu-id="a48cd-112">Cliquez sur Calculer le coût de l'article.</span><span class="sxs-lookup"><span data-stu-id="a48cd-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="a48cd-113">Il vous faudra peut-être cliquer sur les points de suspension (…) pour afficher cette option du menu supérieur.</span><span class="sxs-lookup"><span data-stu-id="a48cd-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="a48cd-114">Dans le champ Version d'évaluation des coûts, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="a48cd-114">In the Costing version field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a48cd-115">Pour cette démonstration, sélectionnez 10.</span><span class="sxs-lookup"><span data-stu-id="a48cd-115">For this demo, select 10.</span></span> <span data-ttu-id="a48cd-116">Il s'agit de la même version d'évaluation des coûts utilisée pour ajouter le prix de revient aux composants.</span><span class="sxs-lookup"><span data-stu-id="a48cd-116">This is the same costing version used for adding the cost price to the components.</span></span>  
7. <span data-ttu-id="a48cd-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a48cd-117">Click OK.</span></span>
8. <span data-ttu-id="a48cd-118">Cliquez sur Afficher les détails du calcul.</span><span class="sxs-lookup"><span data-stu-id="a48cd-118">Click View calculation details.</span></span>
    * <span data-ttu-id="a48cd-119">Il vous faudra peut-être cliquer sur les points de suspension (…) pour afficher cette option du menu supérieur.</span><span class="sxs-lookup"><span data-stu-id="a48cd-119">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>    <span data-ttu-id="a48cd-120">Voici la composition du coût : •    10 est dérivé d'ITEM_A, 10 d'ITEM_B, 10 de BOM_2.</span><span class="sxs-lookup"><span data-stu-id="a48cd-120">Here's the composition of the cost:  •    10 is derived from ITEM_A, 10 from ITEM_B, 10 from BOM_2.</span></span> <span data-ttu-id="a48cd-121">Dans ce cas, il n'existe aucun détail pour BOM_2, car il a été entré comme coût standard de 10 mais n'a pas été obtenu via le calcul.</span><span class="sxs-lookup"><span data-stu-id="a48cd-121">In this case there are no details for BOM_2 because it was entered as a standard cost of 10 but not done through calculation.</span></span>  <span data-ttu-id="a48cd-122">•  7 est dérivé du temps de réglage, qui est un coût constant, et le chiffre 7 supplémentaire est dérivé de l'opération d'exécution (processus).</span><span class="sxs-lookup"><span data-stu-id="a48cd-122">•  7 is derived from the setup time, which is a constant cost, and additional 7 is derived from the run-time operation (Process).</span></span>  <span data-ttu-id="a48cd-123">•   Il existe également d'autres montants qui correspondent aux coûts indirects.</span><span class="sxs-lookup"><span data-stu-id="a48cd-123">•   There are also other amounts that correspond to indirect costs.</span></span>  
9. @SysTaskRecorder:_RequestClose


