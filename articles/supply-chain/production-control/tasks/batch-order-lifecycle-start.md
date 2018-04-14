--- 
title: "Cycle de vie d'un lot de commandes de la création au démarrage"
description: "Cette procédure vous guide dans la première partie du cycle de vie d'un lot de commandes."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7f7198ea7f752fbb4aa40e4a39f2c75a205b09ca
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="batch-order-lifecycle-from-create-to-start"></a><span data-ttu-id="8df6e-103">Cycle de vie d'un lot de commandes de la création au démarrage</span><span class="sxs-lookup"><span data-stu-id="8df6e-103">Batch order lifecycle from create to start</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8df6e-104">Cette procédure vous guide dans la première partie du cycle de vie d'un lot de commandes.</span><span class="sxs-lookup"><span data-stu-id="8df6e-104">This procedure takes you through the first part of the life cycle of a batch order.</span></span>

<span data-ttu-id="8df6e-105">De la création, à l'estimation de coût, en passant par la planification des tâches de production, jusqu'au lancement réel d'un lot de commandes.</span><span class="sxs-lookup"><span data-stu-id="8df6e-105">From creation, cost estimation, and over production job scheduling to the actual start of a batch order.</span></span>



<span data-ttu-id="8df6e-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="8df6e-106">The demo data company used to create this procedure is USMF.</span></span> 



<span data-ttu-id="8df6e-107">Les conditions préalables à l'exécution de la procédure avec un autre ensemble de données sont un produit lancé avec une formule active et une version de gamme.</span><span class="sxs-lookup"><span data-stu-id="8df6e-107">The prerequisites for running the procedure with another dataset are a released product with an active formula and route version.</span></span>


## <a name="create-a-batch-order"></a><span data-ttu-id="8df6e-108">Création d'un lot de commandes</span><span class="sxs-lookup"><span data-stu-id="8df6e-108">Create a batch order</span></span>
1. <span data-ttu-id="8df6e-109">Accédez à Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="8df6e-109">Go to All production orders.</span></span>
2. <span data-ttu-id="8df6e-110">Cliquez sur Nouveau lot de commandes.</span><span class="sxs-lookup"><span data-stu-id="8df6e-110">Click New batch order.</span></span>
3. <span data-ttu-id="8df6e-111">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="8df6e-111">In the Item number field, enter or select a value.</span></span>
4. <span data-ttu-id="8df6e-112">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="8df6e-112">Click Create.</span></span>
5. <span data-ttu-id="8df6e-113">Utilisez le filtre rapide pour filtrer sur le champ Production avec une valeur de « b ».</span><span class="sxs-lookup"><span data-stu-id="8df6e-113">Use the Quick Filter to filter on the Production field with a value of 'b'.</span></span>

## <a name="view-production-formula-and-expected-co-products"></a><span data-ttu-id="8df6e-114">Afficher la formule de production et les coproduits prévus</span><span class="sxs-lookup"><span data-stu-id="8df6e-114">View production formula and expected co-products</span></span>
1. <span data-ttu-id="8df6e-115">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="8df6e-115">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8df6e-116">Cliquez sur Formule.</span><span class="sxs-lookup"><span data-stu-id="8df6e-116">Click Formula.</span></span>
3. <span data-ttu-id="8df6e-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8df6e-117">Close the page.</span></span>
4. <span data-ttu-id="8df6e-118">Cliquez sur Co-produits.</span><span class="sxs-lookup"><span data-stu-id="8df6e-118">Click Co-products.</span></span>
5. <span data-ttu-id="8df6e-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8df6e-119">Close the page.</span></span>

## <a name="estimate-the-batch-order"></a><span data-ttu-id="8df6e-120">Estimer le lot de production</span><span class="sxs-lookup"><span data-stu-id="8df6e-120">Estimate the batch order</span></span>
1. <span data-ttu-id="8df6e-121">Cliquez sur Estimer.</span><span class="sxs-lookup"><span data-stu-id="8df6e-121">Click Estimate.</span></span>
2. <span data-ttu-id="8df6e-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="8df6e-122">Click OK.</span></span>
3. <span data-ttu-id="8df6e-123">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="8df6e-123">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="8df6e-124">Cliquez sur Afficher les détails du calcul.</span><span class="sxs-lookup"><span data-stu-id="8df6e-124">Click View calculation details.</span></span>
5. <span data-ttu-id="8df6e-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8df6e-125">Close the page.</span></span>

## <a name="release-the-batch-order"></a><span data-ttu-id="8df6e-126">Lancer le lot de production</span><span class="sxs-lookup"><span data-stu-id="8df6e-126">Release the batch order</span></span>
1. <span data-ttu-id="8df6e-127">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="8df6e-127">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8df6e-128">Cliquez sur Lancement.</span><span class="sxs-lookup"><span data-stu-id="8df6e-128">Click Release.</span></span>
3. <span data-ttu-id="8df6e-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="8df6e-129">Click OK.</span></span>

## <a name="schedule-production-jobs"></a><span data-ttu-id="8df6e-130">Planifier les tâches de production</span><span class="sxs-lookup"><span data-stu-id="8df6e-130">Schedule production jobs</span></span>
1. <span data-ttu-id="8df6e-131">Dans le volet Actions, cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="8df6e-131">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="8df6e-132">Cliquez sur Planifier les tâches.</span><span class="sxs-lookup"><span data-stu-id="8df6e-132">Click Schedule jobs.</span></span>
3. <span data-ttu-id="8df6e-133">Dans le champ Capacité finie, sélectionnez Non.</span><span class="sxs-lookup"><span data-stu-id="8df6e-133">Select No in the Finite capacity field.</span></span>
4. <span data-ttu-id="8df6e-134">Dans le champ Matières limitées, sélectionnez Non.</span><span class="sxs-lookup"><span data-stu-id="8df6e-134">Select No in the Finite material field.</span></span>
5. <span data-ttu-id="8df6e-135">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="8df6e-135">Click OK.</span></span>
6. <span data-ttu-id="8df6e-136">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="8df6e-136">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="8df6e-137">Cliquez sur Toutes les tâches.</span><span class="sxs-lookup"><span data-stu-id="8df6e-137">Click All jobs.</span></span>
8. <span data-ttu-id="8df6e-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8df6e-138">Close the page.</span></span>

## <a name="start-the-batch-order"></a><span data-ttu-id="8df6e-139">Démarrer le lot de commandes</span><span class="sxs-lookup"><span data-stu-id="8df6e-139">Start the batch order</span></span>
1. <span data-ttu-id="8df6e-140">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="8df6e-140">Click Start.</span></span>
2. <span data-ttu-id="8df6e-141">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="8df6e-141">Click the General tab.</span></span>
3. <span data-ttu-id="8df6e-142">Sélectionnez Non dans le champ Valider immédiatement les prélèvements.</span><span class="sxs-lookup"><span data-stu-id="8df6e-142">Select No in the Post picking list now field.</span></span>
4. <span data-ttu-id="8df6e-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="8df6e-143">Click OK.</span></span>
5. <span data-ttu-id="8df6e-144">Cliquez sur Afficher dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="8df6e-144">On the Action Pane, click View.</span></span>
6. <span data-ttu-id="8df6e-145">Cliquez sur Prélèvements.</span><span class="sxs-lookup"><span data-stu-id="8df6e-145">Click Picking list.</span></span>
7. <span data-ttu-id="8df6e-146">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8df6e-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8df6e-147">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8df6e-147">Close the page.</span></span>
9. <span data-ttu-id="8df6e-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8df6e-148">Close the page.</span></span>
10. <span data-ttu-id="8df6e-149">Cliquez sur Fiche production.</span><span class="sxs-lookup"><span data-stu-id="8df6e-149">Click Route card.</span></span>
11. <span data-ttu-id="8df6e-150">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8df6e-150">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="8df6e-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8df6e-151">Close the page.</span></span>
13. <span data-ttu-id="8df6e-152">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8df6e-152">Close the page.</span></span>


