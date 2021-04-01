---
title: Calculer une nomenclature à l’aide d’une même structure de niveaux (février 2016)
description: Cette procédure montre comment calculer le coût d’un produit fini à l’aide d’un éclatement à un seul niveau basé sur la feuille de coûts.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c370c623c29f2b2f3b65ffbd65aabbc941be3cb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239468"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a><span data-ttu-id="d88d9-103">Calculer une nomenclature à l’aide d’une même structure de niveaux (février 2016)</span><span class="sxs-lookup"><span data-stu-id="d88d9-103">Calculate a BOM by using a single level structure (February 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d88d9-104">Cette procédure montre comment calculer le coût d’un produit fini à l’aide d’un éclatement à un seul niveau basé sur la feuille de coûts.</span><span class="sxs-lookup"><span data-stu-id="d88d9-104">This procedure shows how to calculate the cost of a finished product by using single level explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="d88d9-105">Il s’agit de la sixième tâche de la série de calculs des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="d88d9-105">This is the sixth task in the BOM calculation series.</span></span> <span data-ttu-id="d88d9-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="d88d9-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="d88d9-107">Allez dans Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="d88d9-107">Go to Released products.</span></span>
2. <span data-ttu-id="d88d9-108">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d88d9-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d88d9-109">Sélectionnez le produit BOM_1.</span><span class="sxs-lookup"><span data-stu-id="d88d9-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="d88d9-110">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="d88d9-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="d88d9-111">Cliquez sur Prix de l’article.</span><span class="sxs-lookup"><span data-stu-id="d88d9-111">Click Item price.</span></span>
5. <span data-ttu-id="d88d9-112">Cliquez sur Calculer le coût de l’article.</span><span class="sxs-lookup"><span data-stu-id="d88d9-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="d88d9-113">Il vous faudra peut-être cliquer sur les points de suspension (…) pour afficher cette option du menu supérieur.</span><span class="sxs-lookup"><span data-stu-id="d88d9-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="d88d9-114">Dans le champ Version d’évaluation des coûts, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="d88d9-114">In the Costing version field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d88d9-115">Pour cette démonstration, sélectionnez 10.</span><span class="sxs-lookup"><span data-stu-id="d88d9-115">For this demo, select 10.</span></span> <span data-ttu-id="d88d9-116">Il s’agit de la même version d’évaluation des coûts utilisée pour ajouter le prix de revient aux composants.</span><span class="sxs-lookup"><span data-stu-id="d88d9-116">This is the same costing version used for adding the cost price to the components.</span></span>  
7. <span data-ttu-id="d88d9-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d88d9-117">Click OK.</span></span>
8. <span data-ttu-id="d88d9-118">Cliquez sur Afficher les détails du calcul.</span><span class="sxs-lookup"><span data-stu-id="d88d9-118">Click View calculation details.</span></span>
    * <span data-ttu-id="d88d9-119">Il vous faudra peut-être cliquer sur les points de suspension (…) pour afficher cette option du menu supérieur.</span><span class="sxs-lookup"><span data-stu-id="d88d9-119">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>    <span data-ttu-id="d88d9-120">Voici la composition du coût :  \*    10 est dérivé d’ITEM_A, 10 d’ITEM_B, 10 de BOM_2.</span><span class="sxs-lookup"><span data-stu-id="d88d9-120">Here's the composition of the cost:  \*    10 is derived from ITEM_A, 10 from ITEM_B, 10 from BOM_2.</span></span> <span data-ttu-id="d88d9-121">Dans ce cas, il n’existe aucun détail pour BOM_2, car il a été entré comme coût standard de 10 mais n’a pas été obtenu via le calcul.</span><span class="sxs-lookup"><span data-stu-id="d88d9-121">In this case there are no details for BOM_2 because it was entered as a standard cost of 10 but not done through calculation.</span></span>  <span data-ttu-id="d88d9-122">\*    7 est dérivé du temps de réglage, qui est un coût constant, et le chiffre 7 supplémentaire est dérivé de l’opération d’exécution (processus).</span><span class="sxs-lookup"><span data-stu-id="d88d9-122">\*    7 is derived from the setup time, which is a constant cost, and additional 7 is derived from the run-time operation (Process).</span></span>  <span data-ttu-id="d88d9-123">\*    Il existe également d’autres montants qui correspondent aux coûts indirects.</span><span class="sxs-lookup"><span data-stu-id="d88d9-123">\*    There are also other amounts that correspond to indirect costs.</span></span>  
9. <span data-ttu-id="d88d9-124">@SysTaskRecorder:_RequestClose</span><span class="sxs-lookup"><span data-stu-id="d88d9-124">@SysTaskRecorder:_RequestClose</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]