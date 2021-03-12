---
title: Cycle de vie d'un lot de commandes de la création au démarrage
description: Cette procédure vous guide dans la première partie du cycle de vie d'un lot de commandes.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5fd04587c95ba8a48750f96302a11aeaf82308d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981404"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a><span data-ttu-id="17f68-103">Cycle de vie d'un lot de commandes de la création au démarrage</span><span class="sxs-lookup"><span data-stu-id="17f68-103">Batch order lifecycle from create to start</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="17f68-104">Cette procédure vous guide dans la première partie du cycle de vie d'un lot de commandes.</span><span class="sxs-lookup"><span data-stu-id="17f68-104">This procedure takes you through the first part of the life cycle of a batch order.</span></span>

<span data-ttu-id="17f68-105">De la création, à l'estimation de coût, en passant par la planification des tâches de production, jusqu'au lancement réel d'un lot de commandes.</span><span class="sxs-lookup"><span data-stu-id="17f68-105">From creation, cost estimation, and over production job scheduling to the actual start of a batch order.</span></span>



<span data-ttu-id="17f68-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="17f68-106">The demo data company used to create this procedure is USMF.</span></span> 



<span data-ttu-id="17f68-107">Les conditions préalables à l'exécution de la procédure avec un autre ensemble de données sont un produit lancé avec une formule active et une version de gamme.</span><span class="sxs-lookup"><span data-stu-id="17f68-107">The prerequisites for running the procedure with another dataset are a released product with an active formula and route version.</span></span>


## <a name="create-a-batch-order"></a><span data-ttu-id="17f68-108">Création d'un lot de commandes</span><span class="sxs-lookup"><span data-stu-id="17f68-108">Create a batch order</span></span>
1. <span data-ttu-id="17f68-109">Accédez à Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="17f68-109">Go to All production orders.</span></span>
2. <span data-ttu-id="17f68-110">Cliquez sur Nouveau lot de commandes.</span><span class="sxs-lookup"><span data-stu-id="17f68-110">Click New batch order.</span></span>
3. <span data-ttu-id="17f68-111">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="17f68-111">In the Item number field, enter or select a value.</span></span>
4. <span data-ttu-id="17f68-112">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="17f68-112">Click Create.</span></span>
5. <span data-ttu-id="17f68-113">Utilisez le filtre rapide pour filtrer sur le champ Production avec une valeur de « b ».</span><span class="sxs-lookup"><span data-stu-id="17f68-113">Use the Quick Filter to filter on the Production field with a value of 'b'.</span></span>

## <a name="view-production-formula-and-expected-co-products"></a><span data-ttu-id="17f68-114">Afficher la formule de production et les coproduits prévus</span><span class="sxs-lookup"><span data-stu-id="17f68-114">View production formula and expected co-products</span></span>
1. <span data-ttu-id="17f68-115">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="17f68-115">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="17f68-116">Cliquez sur Formule.</span><span class="sxs-lookup"><span data-stu-id="17f68-116">Click Formula.</span></span>
3. <span data-ttu-id="17f68-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="17f68-117">Close the page.</span></span>
4. <span data-ttu-id="17f68-118">Cliquez sur Co-produits.</span><span class="sxs-lookup"><span data-stu-id="17f68-118">Click Co-products.</span></span>
5. <span data-ttu-id="17f68-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="17f68-119">Close the page.</span></span>

## <a name="estimate-the-batch-order"></a><span data-ttu-id="17f68-120">Estimer le lot de production</span><span class="sxs-lookup"><span data-stu-id="17f68-120">Estimate the batch order</span></span>
1. <span data-ttu-id="17f68-121">Cliquez sur Estimer.</span><span class="sxs-lookup"><span data-stu-id="17f68-121">Click Estimate.</span></span>
2. <span data-ttu-id="17f68-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="17f68-122">Click OK.</span></span>
3. <span data-ttu-id="17f68-123">Cliquez sur Gérer les coûts dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="17f68-123">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="17f68-124">Cliquez sur Afficher les détails du calcul.</span><span class="sxs-lookup"><span data-stu-id="17f68-124">Click View calculation details.</span></span>
5. <span data-ttu-id="17f68-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="17f68-125">Close the page.</span></span>

## <a name="release-the-batch-order"></a><span data-ttu-id="17f68-126">Lancer le lot de production</span><span class="sxs-lookup"><span data-stu-id="17f68-126">Release the batch order</span></span>
1. <span data-ttu-id="17f68-127">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="17f68-127">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="17f68-128">Cliquez sur Lancement.</span><span class="sxs-lookup"><span data-stu-id="17f68-128">Click Release.</span></span>
3. <span data-ttu-id="17f68-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="17f68-129">Click OK.</span></span>

## <a name="schedule-production-jobs"></a><span data-ttu-id="17f68-130">Planifier les tâches de production</span><span class="sxs-lookup"><span data-stu-id="17f68-130">Schedule production jobs</span></span>
1. <span data-ttu-id="17f68-131">Dans le volet Actions, cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="17f68-131">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="17f68-132">Cliquez sur Planifier les tâches.</span><span class="sxs-lookup"><span data-stu-id="17f68-132">Click Schedule jobs.</span></span>
3. <span data-ttu-id="17f68-133">Dans le champ Capacité finie, sélectionnez Non.</span><span class="sxs-lookup"><span data-stu-id="17f68-133">Select No in the Finite capacity field.</span></span>
4. <span data-ttu-id="17f68-134">Dans le champ Matières limitées, sélectionnez Non.</span><span class="sxs-lookup"><span data-stu-id="17f68-134">Select No in the Finite material field.</span></span>
5. <span data-ttu-id="17f68-135">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="17f68-135">Click OK.</span></span>
6. <span data-ttu-id="17f68-136">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="17f68-136">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="17f68-137">Cliquez sur Toutes les tâches.</span><span class="sxs-lookup"><span data-stu-id="17f68-137">Click All jobs.</span></span>
8. <span data-ttu-id="17f68-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="17f68-138">Close the page.</span></span>

## <a name="start-the-batch-order"></a><span data-ttu-id="17f68-139">Démarrer le lot de commandes</span><span class="sxs-lookup"><span data-stu-id="17f68-139">Start the batch order</span></span>
1. <span data-ttu-id="17f68-140">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="17f68-140">Click Start.</span></span>
2. <span data-ttu-id="17f68-141">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="17f68-141">Click the General tab.</span></span>
3. <span data-ttu-id="17f68-142">Sélectionnez Non dans le champ Valider immédiatement les prélèvements.</span><span class="sxs-lookup"><span data-stu-id="17f68-142">Select No in the Post picking list now field.</span></span>
4. <span data-ttu-id="17f68-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="17f68-143">Click OK.</span></span>
5. <span data-ttu-id="17f68-144">Cliquez sur Afficher dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="17f68-144">On the Action Pane, click View.</span></span>
6. <span data-ttu-id="17f68-145">Cliquez sur Prélèvements.</span><span class="sxs-lookup"><span data-stu-id="17f68-145">Click Picking list.</span></span>
7. <span data-ttu-id="17f68-146">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="17f68-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="17f68-147">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="17f68-147">Close the page.</span></span>
9. <span data-ttu-id="17f68-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="17f68-148">Close the page.</span></span>
10. <span data-ttu-id="17f68-149">Cliquez sur Fiche production.</span><span class="sxs-lookup"><span data-stu-id="17f68-149">Click Route card.</span></span>
11. <span data-ttu-id="17f68-150">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="17f68-150">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="17f68-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="17f68-151">Close the page.</span></span>
13. <span data-ttu-id="17f68-152">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="17f68-152">Close the page.</span></span>

