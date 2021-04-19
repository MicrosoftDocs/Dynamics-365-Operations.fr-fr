---
title: Calculer une nomenclature à l’aide d’une structure à plusieurs niveaux (février 2016)
description: Cette procédure montre comment calculer le coût d’un produit fini à l’aide d’un éclatement à plusieurs niveaux basé sur la feuille de coûts.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 859f7b7c828dcdad1aa836044d2cc26847630f1e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821415"
---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016"></a><span data-ttu-id="4c783-103">Calculer une nomenclature à l’aide d’une structure à plusieurs niveaux (février 2016)</span><span class="sxs-lookup"><span data-stu-id="4c783-103">Calculate a BOM by using a multilevel structure (February 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4c783-104">Cette procédure montre comment calculer le coût d’un produit fini à l’aide d’un éclatement à plusieurs niveaux basé sur la feuille de coûts.</span><span class="sxs-lookup"><span data-stu-id="4c783-104">This procedure shows how to calculate the cost of a finished product by using multilevel explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="4c783-105">Il s’agit de la septième tâche de la série de calculs des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="4c783-105">It is the seventh task in the BOM calculation series.</span></span> <span data-ttu-id="4c783-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="4c783-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="4c783-107">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="4c783-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="4c783-108">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="4c783-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4c783-109">Sélectionnez le produit BOM_1.</span><span class="sxs-lookup"><span data-stu-id="4c783-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="4c783-110">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="4c783-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="4c783-111">Cliquez sur Prix de l’article.</span><span class="sxs-lookup"><span data-stu-id="4c783-111">Click Item price.</span></span>
5. <span data-ttu-id="4c783-112">Cliquez sur Calculer le coût de l’article.</span><span class="sxs-lookup"><span data-stu-id="4c783-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="4c783-113">Il vous faudra peut-être cliquer sur les points de suspension (…) pour afficher cette option du menu supérieur.</span><span class="sxs-lookup"><span data-stu-id="4c783-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="4c783-114">Dans le champ Version d’évaluation des coûts, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4c783-114">In the Costing version field, enter or select a value.</span></span>
    * <span data-ttu-id="4c783-115">Sélectionnez Version d’évaluation des coûts 20, car elle est de type Coût prévu et le mode Éclatement est Plusieurs niveaux.</span><span class="sxs-lookup"><span data-stu-id="4c783-115">Select Costing version 20, because it's Planned cost type and Explosion mode is Multilevel.</span></span>   <span data-ttu-id="4c783-116">Le mode Éclatement à plusieurs niveaux est pour les coûts planifiés et les simulations.</span><span class="sxs-lookup"><span data-stu-id="4c783-116">The Multilevel explosion mode is for planned costs and simulations.</span></span> <span data-ttu-id="4c783-117">Il n’est pas utilisé pour le coût standard.</span><span class="sxs-lookup"><span data-stu-id="4c783-117">It is not used for standard cost.</span></span>  
7. <span data-ttu-id="4c783-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4c783-118">Click OK.</span></span>
8. <span data-ttu-id="4c783-119">Cliquez sur Afficher les détails du calcul.</span><span class="sxs-lookup"><span data-stu-id="4c783-119">Click View calculation details.</span></span>
    * <span data-ttu-id="4c783-120">Il vous faudra peut-être cliquer sur les points de suspension (…) pour afficher cette option du menu supérieur.</span><span class="sxs-lookup"><span data-stu-id="4c783-120">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  <span data-ttu-id="4c783-121">Dans ce cas, notez la façon dont BOM_2 a été calculé, en prenant en compte la matière première, le processus, et les frais généraux avec un total de 29,40 au lieu du coût standard de 10 qui a été activé dans le premier Guide de tâche de cette série.</span><span class="sxs-lookup"><span data-stu-id="4c783-121">In this case, notice how BOM_2 has been calculated taking into account the raw material, process, and overhead with a total of 29,40 instead of the standard cost of 10 that was activated in the initial task guide in this series.</span></span>  
9. <span data-ttu-id="4c783-122">Cliquez sur l’onglet Feuille de coûts.</span><span class="sxs-lookup"><span data-stu-id="4c783-122">Click the Costing sheet tab.</span></span>
    * <span data-ttu-id="4c783-123">Dans l’onglet Feuille de coûts, les totaux par groupe de coûts sont différents comparés au calcul effectué dans le Guide de tâche précédent.</span><span class="sxs-lookup"><span data-stu-id="4c783-123">Moving to the Costing sheet tab, the totals per cost group are different compared to the calculation done in previous task guide.</span></span>  
10. <span data-ttu-id="4c783-124">Dans le champ Niveau, sélectionnez Multi.</span><span class="sxs-lookup"><span data-stu-id="4c783-124">In the Level field, select 'Multi'.</span></span>
    * <span data-ttu-id="4c783-125">En sélectionnant Multi, les coûts sont classés selon la composition de BOM_2, où 10 est dérivé du groupe de coûts M1 (ITEM_C), et 15,60 est dérivé de sa fabrication dans lequel le groupe de coûts est L2.</span><span class="sxs-lookup"><span data-stu-id="4c783-125">When selecting Multi, the costs are classified according to the composition of BOM_2, where 10 is derived from the M1 cost group (ITEM_C), and 15,60 is derived from its manufacturing where the cost group is L2.</span></span> <span data-ttu-id="4c783-126">Les coûts indirects varient également.</span><span class="sxs-lookup"><span data-stu-id="4c783-126">Indirect costs also vary.</span></span>  
11. <span data-ttu-id="4c783-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4c783-127">Close the page.</span></span>
12. <span data-ttu-id="4c783-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4c783-128">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]